# CCscWmiProgressHelper::FireProgress(PROGRESS_REASON,long,ushort const *)

- ea: `0x180019220`
- end: `0x1800194ad`
- name: `?FireProgress@CCscWmiProgressHelper@@QEAAJW4PROGRESS_REASON@@JPEBG@Z`
- size: `653`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001889c`
- `0x180019084`
- `0x1800195ac`
- `0x180019660`
- `0x180019a30`

## callees

- `0x1800084e0`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180019220`
- `0x18001bf5c`
- `0x18002a304`
- `0x18002a33c`
- `0x18002a3e8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019284`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800193bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800193bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019390`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019390`
- `OLEAUT32!__imp_SysAllocString` at `0x180019377`
- `OLEAUT32!__imp_SysAllocString` at `0x180019377`
- `OLEAUT32!__imp_SysFreeString` at `0x1800193f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800193f6`

## pseudocode

```c
__int64 __fastcall CCscWmiProgressHelper::FireProgress(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  int v10; // eax
  int v11; // edi
  __int64 i; // rax
  unsigned int v13; // r8d
  int v14; // eax
  void *v15; // rdx
  void *v16; // rdx
  OLECHAR *v17; // rsi
  __int64 v18; // rcx
  void *lpMem; // [rsp+30h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-28h] BYREF
  struct IWbemObjectSink *v22; // [rsp+40h] [rbp-20h] BYREF
  struct IWbemServices *v23; // [rsp+48h] [rbp-18h] BYREF
  struct IWbemContext *v24; // [rsp+50h] [rbp-10h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_DWORD *)(v8 + 28) & 0x4000000) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        32,
        WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
        CurrentThreadId);
    }
  }
  v23 = 0;
  v24 = 0;
  v22 = 0;
  v10 = CCscWmiProgressHelper::_UnmarshalWbemInterfaces((CCscWmiProgressHelper *)a1, &v23, &v24, &v22);
  v11 = v10;
  if ( v10 >= 0 )
  {
    lpMem = 0;
    for ( i = 0; !(_DWORD)i; i = 1 )
    {
      if ( LODWORD(qword_18003AE90[i]) == a3 )
      {
        v13 = HIDWORD(qword_18003AE90[i]);
        if ( v13 )
        {
          v14 = CscUtil_FormatStringID((LPWSTR)&lpMem, g_hInstance, v13);
          goto LABEL_15;
        }
        break;
      }
    }
    v14 = CscUtil_FormatSystemError((unsigned __int16 **)&lpMem, a3);
LABEL_15:
    v11 = v14;
    if ( v14 >= 0 )
    {
      psz = 0;
      if ( !a4 )
        a4 = &qword_18003ADA8;
      v11 = CscUtil_FormatString(&psz, L"%1!d!:%2!d!:%3:%4", a2, a3, lpMem, a4);
      if ( v11 >= 0 )
      {
        v17 = SysAllocString(psz);
        if ( v17 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
          v11 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, _QWORD, OLECHAR *, _QWORD))v22->lpVtbl->SetStatus)(
                  v22,
                  2,
                  0,
                  v17,
                  0);
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
          if ( v11 < 0
            && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              33,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              (unsigned int)v11);
          }
          SysFreeString(v17);
        }
        else
        {
          v11 = -2147024882;
        }
        CscUtil_HeapFree(psz, v16);
      }
      CscUtil_HeapFree(lpMem, v15);
    }
    ((void (__fastcall *)(struct IWbemServices *))v23->lpVtbl->Release)(v23);
    ((void (__fastcall *)(struct IWbemObjectSink *))v22->lpVtbl->Release)(v22);
    if ( v24 )
      ((void (__fastcall *)(struct IWbemContext *))v24->lpVtbl->Release)(v24);
    goto LABEL_33;
  }
  v18 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v11;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v10);
LABEL_33:
    v18 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_DWORD *)(v18 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v18 + 16), 35, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019220  push    rbp
0x180019222  push    rbx
0x180019223  push    rsi
0x180019224  push    rdi
0x180019225  push    r13
0x180019227  push    r14
0x180019229  push    r15
0x18001922b  mov     rbp, rsp
0x18001922e  sub     rsp, 60h
0x180019232  mov     rsi, r9
0x180019235  mov     ebx, r8d
0x180019238  mov     r15d, edx
0x18001923b  mov     r14, rcx
0x18001923e  mov     rax, cs:WPP_GLOBAL_Control
0x180019245  lea     r13, WPP_GLOBAL_Control
0x18001924c  cmp     rax, r13
0x18001924f  jz      short loc_1800192A9
0x180019251  test    dword ptr [rax+1Ch], 4000000h
0x180019258  jz      short loc_180019276
0x18001925a  mov     rcx, [rax+10h]
0x18001925e  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019265  mov     edx, 1Fh
0x18001926a  call    WPP_SF_
0x18001926f  mov     rax, cs:WPP_GLOBAL_Control
0x180019276  cmp     rax, r13
0x180019279  jz      short loc_1800192A9
0x18001927b  test    dword ptr [rax+1Ch], 4000000h
0x180019282  jz      short loc_1800192A9
0x180019284  call    cs:__imp_GetCurrentThreadId
0x18001928a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019291  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019298  mov     edx, 20h ; ' '
0x18001929d  mov     r9d, eax
0x1800192a0  mov     rcx, [rcx+10h]
0x1800192a4  call    WPP_SF_d
0x1800192a9  lea     r9, [rbp+var_20]; struct IWbemObjectSink **
0x1800192ad  mov     [rbp+var_18], 0
0x1800192b5  lea     r8, [rbp+var_10]; struct IWbemContext **
0x1800192b9  mov     [rbp+var_10], 0
0x1800192c1  lea     rdx, [rbp+var_18]; struct IWbemServices **
0x1800192c5  mov     [rbp+var_20], 0
0x1800192cd  mov     rcx, r14; this
0x1800192d0  call    ?_UnmarshalWbemInterfaces@CCscWmiProgressHelper@@AEAAJPEAPEAUIWbemServices@@PEAPEAUIWbemContext@@PEAPEAUIWbemObjectSink@@@Z; CCscWmiProgressHelper::_UnmarshalWbemInterfaces(IWbemServices * *,IWbemContext * *,IWbemObjectSink * *)
0x1800192d5  mov     edi, eax
0x1800192d7  test    eax, eax
0x1800192d9  js      loc_180019445
0x1800192df  mov     [rbp+lpMem], 0
0x1800192e7  lea     rcx, qword_18003AE90
0x1800192ee  xor     eax, eax
0x1800192f0  cmp     eax, 1
0x1800192f3  jnb     short loc_18001931A
0x1800192f5  cmp     [rcx+rax*8], ebx
0x1800192f8  jz      short loc_1800192FE
0x1800192fa  inc     eax
0x1800192fc  jmp     short loc_1800192F0
0x1800192fe  mov     r8d, [rcx+rax*8+4]; unsigned int
0x180019303  test    r8d, r8d
0x180019306  jz      short loc_18001931A
0x180019308  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18001930f  lea     rcx, [rbp+lpMem]; lpBuffer
0x180019313  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180019318  jmp     short loc_180019325
0x18001931a  mov     edx, ebx; unsigned int
0x18001931c  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x180019320  call    ?CscUtil_FormatSystemError@@YAJPEAPEAGK@Z; CscUtil_FormatSystemError(ushort * *,ulong)
0x180019325  mov     edi, eax
0x180019327  test    eax, eax
0x180019329  js      loc_18001940E
0x18001932f  lea     rax, qword_18003ADA8
0x180019336  mov     [rbp+psz], 0
0x18001933e  test    rsi, rsi
0x180019341  lea     rdx, a1D2D34; "%1!d!:%2!d!:%3:%4"
0x180019348  mov     r9d, ebx
0x18001934b  lea     rcx, [rbp+psz]; unsigned __int16 **
0x18001934f  cmovz   rsi, rax
0x180019353  mov     r8d, r15d
0x180019356  mov     rax, [rbp+lpMem]
0x18001935a  mov     [rsp+60h+var_38], rsi
0x18001935f  mov     [rsp+60h+var_40], rax
0x180019364  call    ?CscUtil_FormatString@@YAJPEAPEAGPEBGZZ; CscUtil_FormatString(ushort * *,ushort const *,...)
0x180019369  mov     edi, eax
0x18001936b  test    eax, eax
0x18001936d  js      loc_180019405
0x180019373  mov     rcx, [rbp+psz]; psz
0x180019377  call    cs:__imp_SysAllocString
0x18001937d  mov     rsi, rax
0x180019380  test    rax, rax
0x180019383  jnz     short loc_18001938C
0x180019385  mov     edi, 8007000Eh
0x18001938a  jmp     short loc_1800193FC
0x18001938c  lea     rcx, [r14+20h]; lpCriticalSection
0x180019390  call    cs:__imp_EnterCriticalSection
0x180019396  mov     rcx, [rbp+var_20]
0x18001939a  xor     r8d, r8d
0x18001939d  mov     r9, rsi
0x1800193a0  mov     [rsp+60h+var_40], 0
0x1800193a9  mov     rax, [rcx]
0x1800193ac  lea     edx, [r8+2]
0x1800193b0  mov     rax, [rax+20h]
0x1800193b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193b9  lea     rcx, [r14+20h]; lpCriticalSection
0x1800193bd  mov     edi, eax
0x1800193bf  call    cs:__imp_LeaveCriticalSection
0x1800193c5  test    edi, edi
0x1800193c7  jns     short loc_1800193F3
0x1800193c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193d0  cmp     rcx, r13
0x1800193d3  jz      short loc_1800193F3
0x1800193d5  test    byte ptr [rcx+1Ch], 2
0x1800193d9  jz      short loc_1800193F3
0x1800193db  mov     rcx, [rcx+10h]
0x1800193df  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x1800193e6  mov     edx, 21h ; '!'
0x1800193eb  mov     r9d, edi
0x1800193ee  call    WPP_SF_d
0x1800193f3  mov     rcx, rsi; bstrString
0x1800193f6  call    cs:__imp_SysFreeString
0x1800193fc  mov     rcx, [rbp+psz]; lpMem
0x180019400  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180019405  mov     rcx, [rbp+lpMem]; lpMem
0x180019409  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001940e  mov     rcx, [rbp+var_18]
0x180019412  mov     rax, [rcx]
0x180019415  mov     rax, [rax+10h]
0x180019419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001941e  mov     rcx, [rbp+var_20]
0x180019422  mov     rax, [rcx]
0x180019425  mov     rax, [rax+10h]
0x180019429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001942e  mov     rcx, [rbp+var_10]
0x180019432  test    rcx, rcx
0x180019435  jz      short loc_18001946F
0x180019437  mov     rax, [rcx]
0x18001943a  mov     rax, [rax+10h]
0x18001943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019443  jmp     short loc_18001946F
0x180019445  mov     rcx, cs:WPP_GLOBAL_Control
0x18001944c  cmp     rcx, r13
0x18001944f  jz      short loc_18001949C
0x180019451  test    byte ptr [rcx+1Ch], 2
0x180019455  jz      short loc_180019476
0x180019457  mov     rcx, [rcx+10h]
0x18001945b  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019462  mov     edx, 22h ; '"'
0x180019467  mov     r9d, eax
0x18001946a  call    WPP_SF_d
0x18001946f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019476  cmp     rcx, r13
0x180019479  jz      short loc_18001949C
0x18001947b  test    dword ptr [rcx+1Ch], 4000000h
0x180019482  jz      short loc_18001949C
0x180019484  mov     rcx, [rcx+10h]
0x180019488  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001948f  mov     edx, 23h ; '#'
0x180019494  mov     r9d, edi
0x180019497  call    WPP_SF_d
0x18001949c  mov     eax, edi
0x18001949e  add     rsp, 60h
0x1800194a2  pop     r15
0x1800194a4  pop     r14
0x1800194a6  pop     r13
0x1800194a8  pop     rdi
0x1800194a9  pop     rsi
0x1800194aa  pop     rbx
0x1800194ab  pop     rbp
0x1800194ac  retn
```
