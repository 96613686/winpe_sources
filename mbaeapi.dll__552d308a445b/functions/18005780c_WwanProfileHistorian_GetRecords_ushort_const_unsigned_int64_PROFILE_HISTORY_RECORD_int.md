# WwanProfileHistorian::GetRecords(ushort const *,unsigned __int64,PROFILE_HISTORY_RECORD *,int *)

- ea: `0x18005780c`
- end: `0x1800579e5`
- name: `?GetRecords@WwanProfileHistorian@@QEAAJPEBG_KPEAUPROFILE_HISTORY_RECORD@@PEAH@Z`
- size: `473`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, LPCOLESTR lpsz@<rdx>, unsigned __int64@<r8>, struct PROFILE_HISTORY_RECORD *@<r9>, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d880`

## callees

- `0x1800024e0`
- `0x180055448`
- `0x180055470`
- `0x18005780c`
- `0x180057c74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057997`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057997`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005787e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005787e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005789c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005789c`

## pseudocode

```c
__int64 __fastcall WwanProfileHistorian::GetRecords(
        LPCRITICAL_SECTION lpCriticalSection,
        LPCOLESTR lpsz,
        unsigned __int64 a3,
        struct PROFILE_HISTORY_RECORD *a4,
        int *a5)
{
  HRESULT v9; // edi
  __int64 v10; // rdx
  __int64 v11; // r8
  int OwningThread; // eax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // r11
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rax
  _OWORD *v19; // rcx
  __int128 v20; // xmm1
  GUID pclsid; // [rsp+20h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_59efe20e95083d54484ef368743a0c87_Traceguids);
  *a5 = 0;
  pclsid = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
  {
    v9 = CLSIDFromString(lpsz, &pclsid);
    if ( v9 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, lpsz);
      OwningThread = (int)lpCriticalSection[1].OwningThread;
      if ( a3 )
      {
        v13 = 0;
        v14 = 0;
        if ( OwningThread > 0 )
        {
          v15 = *(_QWORD *)pclsid.Data4;
          v16 = *(_QWORD *)&pclsid.Data1;
          do
          {
            if ( v13 >= a3 )
              break;
            v17 = *(_QWORD *)&lpCriticalSection[1].LockCount + 536LL * v14;
            if ( *(_QWORD *)(v17 + 520) == v16 && *(_QWORD *)(v17 + 528) == v15 )
            {
              v18 = 4;
              v19 = (_OWORD *)((char *)a4 + 520 * v13);
              do
              {
                *v19 = *(_OWORD *)v17;
                v19[1] = *(_OWORD *)(v17 + 16);
                v19[2] = *(_OWORD *)(v17 + 32);
                v19[3] = *(_OWORD *)(v17 + 48);
                v19[4] = *(_OWORD *)(v17 + 64);
                v19[5] = *(_OWORD *)(v17 + 80);
                v19[6] = *(_OWORD *)(v17 + 96);
                v20 = *(_OWORD *)(v17 + 112);
                v17 += 128;
                v19[7] = v20;
                v19 += 8;
                --v18;
              }
              while ( v18 );
              ++v13;
              *(_QWORD *)v19 = *(_QWORD *)v17;
            }
            ++v14;
          }
          while ( v14 < SLODWORD(lpCriticalSection[1].OwningThread) );
        }
        *a5 = v13;
      }
      else
      {
        *a5 = OwningThread;
      }
    }
  }
  else
  {
    v9 = -2147019873;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_59efe20e95083d54484ef368743a0c87_Traceguids,
      (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005780c  push    rbx
0x18005780e  push    rbp
0x18005780f  push    rsi
0x180057810  push    rdi
0x180057811  push    r13
0x180057813  push    r14
0x180057815  push    r15
0x180057817  sub     rsp, 40h
0x18005781b  mov     rax, cs:__security_cookie
0x180057822  xor     rax, rsp
0x180057825  mov     [rsp+78h+var_48], rax
0x18005782a  mov     r14, [rsp+78h+arg_20]
0x180057832  mov     r15, r9
0x180057835  mov     rbp, r8
0x180057838  mov     rsi, rdx
0x18005783b  mov     rbx, rcx
0x18005783e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057845  lea     r13, WPP_GLOBAL_Control
0x18005784c  cmp     rcx, r13
0x18005784f  jz      short loc_18005786C
0x180057851  test    byte ptr [rcx+1Ch], 10h
0x180057855  jz      short loc_18005786C
0x180057857  mov     rcx, [rcx+10h]
0x18005785b  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x180057862  mov     edx, 16h
0x180057867  call    WPP_SF_
0x18005786c  xorps   xmm0, xmm0
0x18005786f  mov     dword ptr [r14], 0
0x180057876  mov     rcx, rbx; lpCriticalSection
0x180057879  movups  xmmword ptr [rsp+78h+pclsid.Data1], xmm0
0x18005787e  call    cs:__imp_EnterCriticalSection
0x180057884  cmp     byte ptr [rbx+28h], 0
0x180057888  jnz     short loc_180057894
0x18005788a  mov     edi, 8007139Fh
0x18005788f  jmp     loc_180057994
0x180057894  lea     rdx, [rsp+78h+pclsid]; pclsid
0x180057899  mov     rcx, rsi; lpsz
0x18005789c  call    cs:__imp_CLSIDFromString
0x1800578a2  mov     edi, eax
0x1800578a4  test    eax, eax
0x1800578a6  js      loc_180057994
0x1800578ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800578b3  cmp     rcx, r13
0x1800578b6  jz      short loc_1800578CA
0x1800578b8  test    byte ptr [rcx+1Ch], 10h
0x1800578bc  jz      short loc_1800578CA
0x1800578be  mov     rcx, [rcx+10h]
0x1800578c2  mov     r9, rsi
0x1800578c5  call    WPP_SF_S
0x1800578ca  mov     eax, [rbx+38h]
0x1800578cd  test    rbp, rbp
0x1800578d0  jnz     short loc_1800578DA
0x1800578d2  mov     [r14], eax
0x1800578d5  jmp     loc_180057994
0x1800578da  xor     r8d, r8d
0x1800578dd  xor     r9d, r9d
0x1800578e0  test    eax, eax
0x1800578e2  jle     loc_180057991
0x1800578e8  mov     r11, qword ptr [rsp+78h+pclsid.Data4]
0x1800578ed  mov     rsi, qword ptr [rsp+78h+pclsid.Data1]
0x1800578f2  movsxd  r10, r8d
0x1800578f5  cmp     r10, rbp
0x1800578f8  jnb     loc_180057991
0x1800578fe  movsxd  rax, r9d
0x180057901  imul    rdx, rax, 218h
0x180057908  add     rdx, [rbx+30h]
0x18005790c  cmp     [rdx+208h], rsi
0x180057913  jnz     short loc_180057984
0x180057915  cmp     [rdx+210h], r11
0x18005791c  jnz     short loc_180057984
0x18005791e  imul    rcx, r10, 208h
0x180057925  mov     eax, 4
0x18005792a  add     rcx, r15
0x18005792d  lea     r10d, [rax+7Ch]
0x180057931  movups  xmm0, xmmword ptr [rdx]
0x180057934  movups  xmmword ptr [rcx], xmm0
0x180057937  movups  xmm1, xmmword ptr [rdx+10h]
0x18005793b  movups  xmmword ptr [rcx+10h], xmm1
0x18005793f  movups  xmm0, xmmword ptr [rdx+20h]
0x180057943  movups  xmmword ptr [rcx+20h], xmm0
0x180057947  movups  xmm1, xmmword ptr [rdx+30h]
0x18005794b  movups  xmmword ptr [rcx+30h], xmm1
0x18005794f  movups  xmm0, xmmword ptr [rdx+40h]
0x180057953  movups  xmmword ptr [rcx+40h], xmm0
0x180057957  movups  xmm1, xmmword ptr [rdx+50h]
0x18005795b  movups  xmmword ptr [rcx+50h], xmm1
0x18005795f  movups  xmm0, xmmword ptr [rdx+60h]
0x180057963  movups  xmmword ptr [rcx+60h], xmm0
0x180057967  movups  xmm1, xmmword ptr [rdx+70h]
0x18005796b  add     rdx, r10
0x18005796e  movups  xmmword ptr [rcx+70h], xmm1
0x180057972  add     rcx, r10
0x180057975  sub     rax, 1
0x180057979  jnz     short loc_180057931
0x18005797b  mov     rax, [rdx]
0x18005797e  inc     r8d
0x180057981  mov     [rcx], rax
0x180057984  inc     r9d
0x180057987  cmp     r9d, [rbx+38h]
0x18005798b  jl      loc_1800578F2
0x180057991  mov     [r14], r8d
0x180057994  mov     rcx, rbx; lpCriticalSection
0x180057997  call    cs:__imp_LeaveCriticalSection
0x18005799d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579a4  cmp     rcx, r13
0x1800579a7  jz      short loc_1800579C7
0x1800579a9  test    byte ptr [rcx+1Ch], 10h
0x1800579ad  jz      short loc_1800579C7
0x1800579af  mov     rcx, [rcx+10h]
0x1800579b3  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x1800579ba  mov     edx, 18h
0x1800579bf  mov     r9d, edi
0x1800579c2  call    WPP_SF_d
0x1800579c7  mov     eax, edi
0x1800579c9  mov     rcx, [rsp+78h+var_48]
0x1800579ce  xor     rcx, rsp; StackCookie
0x1800579d1  call    __security_check_cookie
0x1800579d6  add     rsp, 40h
0x1800579da  pop     r15
0x1800579dc  pop     r14
0x1800579de  pop     r13
0x1800579e0  pop     rdi
0x1800579e1  pop     rsi
0x1800579e2  pop     rbp
0x1800579e3  pop     rbx
0x1800579e4  retn
```
