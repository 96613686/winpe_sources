# OpenTunnelFilterHandleInternal

- ea: `0x1800327ac`
- end: `0x18003299b`
- name: `OpenTunnelFilterHandleInternal`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014c30`

## callees

- `0x18000e510`
- `0x1800175dc`
- `0x1800316dc`
- `0x180032224`
- `0x1800322b8`
- `0x1800327ac`
- `0x180043764`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032831`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032831`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003296c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003296c`

## pseudocode

```c
__int64 __fastcall OpenTunnelFilterHandleInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 *v5; // r14
  __int64 v6; // rsi
  unsigned int v9; // edi
  _QWORD *i; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int128 v14; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  v5 = a5;
  v6 = 0;
  v15 = 0;
  if ( !a5 )
    return 87;
  v9 = ValidateTunnelFilter(a3);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v9);
  }
  else
  {
    EnterCriticalSection(&gcSPDSection);
    for ( i = gpIniTnFilter; i; i = (_QWORD *)i[36] )
    {
      if ( (unsigned int)EqualTnFilterPKeys(i, a3) && (unsigned int)EqualTnFilterNonPKeys(i, a3) )
      {
        if ( *((_DWORD *)i + 61) )
        {
          v9 = 13020;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v12 = 99;
LABEL_25:
            WPP_SF_d(v11[2], v12, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v9);
            goto LABEL_26;
          }
        }
        else
        {
          v14 = *(_OWORD *)(a3 + 4);
          v9 = CreateTnFilterHandle(i, &v14, &v15);
          if ( !v9 )
          {
            ++*((_DWORD *)i + 59);
            v13 = v15;
            *(_QWORD *)(v15 + 32) = gpTnFilterHandle;
            gpTnFilterHandle = v13;
            *v5 = v13;
            LeaveCriticalSection(&gcSPDSection);
            return v9;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v9);
          }
          v6 = v15;
        }
        goto LABEL_26;
      }
    }
    v9 = 13017;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = 98;
      goto LABEL_25;
    }
LABEL_26:
    LeaveCriticalSection(&gcSPDSection);
    if ( v6 )
      SPDApiBufferFree(v6);
  }
  *v5 = 0;
  return v9;
}

```

## disassembly

```asm
0x1800327ac  mov     rax, rsp
0x1800327af  mov     [rax+8], rbx
0x1800327b3  mov     [rax+10h], rbp
0x1800327b7  mov     [rax+20h], r9
0x1800327bb  push    rsi
0x1800327bc  push    rdi
0x1800327bd  push    r14
0x1800327bf  sub     rsp, 30h
0x1800327c3  mov     r14, [rsp+48h+arg_20]
0x1800327c8  xor     esi, esi
0x1800327ca  mov     [rax+20h], rsi
0x1800327ce  mov     rbp, r8
0x1800327d1  test    r14, r14
0x1800327d4  jnz     short loc_1800327DE
0x1800327d6  lea     eax, [rsi+57h]
0x1800327d9  jmp     loc_180032988
0x1800327de  mov     rcx, rbp
0x1800327e1  call    ValidateTunnelFilter
0x1800327e6  mov     edi, eax
0x1800327e8  test    eax, eax
0x1800327ea  jz      short loc_18003282A
0x1800327ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327f3  lea     rax, WPP_GLOBAL_Control
0x1800327fa  cmp     rcx, rax
0x1800327fd  jz      loc_18003297F
0x180032803  test    byte ptr [rcx+1Ch], 10h
0x180032807  jz      loc_18003297F
0x18003280d  mov     rcx, [rcx+10h]
0x180032811  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180032818  mov     edx, 61h ; 'a'
0x18003281d  mov     r9d, edi
0x180032820  call    WPP_SF_d
0x180032825  jmp     loc_18003297F
0x18003282a  lea     rcx, gcSPDSection; lpCriticalSection
0x180032831  call    cs:__imp_EnterCriticalSection
0x180032837  mov     rbx, cs:gpIniTnFilter
0x18003283e  test    rbx, rbx
0x180032841  jz      loc_18003292F
0x180032847  mov     rdx, rbp
0x18003284a  mov     rcx, rbx
0x18003284d  call    EqualTnFilterPKeys
0x180032852  test    eax, eax
0x180032854  jz      short loc_180032865
0x180032856  mov     rdx, rbp
0x180032859  mov     rcx, rbx
0x18003285c  call    EqualTnFilterNonPKeys
0x180032861  test    eax, eax
0x180032863  jnz     short loc_18003286E
0x180032865  mov     rbx, [rbx+120h]
0x18003286c  jmp     short loc_18003283E
0x18003286e  cmp     [rbx+0F4h], esi
0x180032874  jz      short loc_1800328A6
0x180032876  mov     edi, 32DCh
0x18003287b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032882  lea     rax, WPP_GLOBAL_Control
0x180032889  cmp     rcx, rax
0x18003288c  jz      loc_180032965
0x180032892  test    byte ptr [rcx+1Ch], 10h
0x180032896  jz      loc_180032965
0x18003289c  mov     edx, 63h ; 'c'
0x1800328a1  jmp     loc_180032952
0x1800328a6  movups  xmm0, xmmword ptr [rbp+4]
0x1800328aa  lea     r8, [rsp+48h+arg_18]
0x1800328af  mov     rcx, rbx
0x1800328b2  lea     rdx, [rsp+48h+var_28]
0x1800328b7  movdqu  [rsp+48h+var_28], xmm0
0x1800328bd  call    CreateTnFilterHandle
0x1800328c2  mov     edi, eax
0x1800328c4  test    eax, eax
0x1800328c6  jz      short loc_180032900
0x1800328c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328cf  lea     rax, WPP_GLOBAL_Control
0x1800328d6  cmp     rcx, rax
0x1800328d9  jz      short loc_1800328F9
0x1800328db  test    byte ptr [rcx+1Ch], 10h
0x1800328df  jz      short loc_1800328F9
0x1800328e1  mov     rcx, [rcx+10h]
0x1800328e5  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x1800328ec  mov     edx, 64h ; 'd'
0x1800328f1  mov     r9d, edi
0x1800328f4  call    WPP_SF_d
0x1800328f9  mov     rsi, [rsp+48h+arg_18]
0x1800328fe  jmp     short loc_180032965
0x180032900  inc     dword ptr [rbx+0ECh]
0x180032906  mov     rcx, [rsp+48h+arg_18]
0x18003290b  mov     rax, cs:gpTnFilterHandle
0x180032912  mov     [rcx+20h], rax
0x180032916  mov     cs:gpTnFilterHandle, rcx
0x18003291d  mov     [r14], rcx
0x180032920  lea     rcx, gcSPDSection; lpCriticalSection
0x180032927  call    cs:__imp_LeaveCriticalSection
0x18003292d  jmp     short loc_180032986
0x18003292f  mov     edi, 32D9h
0x180032934  mov     rcx, cs:WPP_GLOBAL_Control
0x18003293b  lea     rax, WPP_GLOBAL_Control
0x180032942  cmp     rcx, rax
0x180032945  jz      short loc_180032965
0x180032947  test    byte ptr [rcx+1Ch], 10h
0x18003294b  jz      short loc_180032965
0x18003294d  mov     edx, 62h ; 'b'
0x180032952  mov     rcx, [rcx+10h]
0x180032956  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x18003295d  mov     r9d, edi
0x180032960  call    WPP_SF_d
0x180032965  lea     rcx, gcSPDSection; lpCriticalSection
0x18003296c  call    cs:__imp_LeaveCriticalSection
0x180032972  test    rsi, rsi
0x180032975  jz      short loc_18003297F
0x180032977  mov     rcx, rsi
0x18003297a  call    SPDApiBufferFree
0x18003297f  mov     qword ptr [r14], 0
0x180032986  mov     eax, edi
0x180032988  mov     rbx, [rsp+48h+arg_0]
0x18003298d  mov     rbp, [rsp+48h+arg_8]
0x180032992  add     rsp, 30h
0x180032996  pop     r14
0x180032998  pop     rdi
0x180032999  pop     rsi
0x18003299a  retn
```
