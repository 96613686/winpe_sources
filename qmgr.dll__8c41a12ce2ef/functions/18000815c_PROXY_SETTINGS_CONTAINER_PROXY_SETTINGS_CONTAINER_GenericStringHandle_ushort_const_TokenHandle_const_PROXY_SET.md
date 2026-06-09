# PROXY_SETTINGS_CONTAINER::PROXY_SETTINGS_CONTAINER(GenericStringHandle<ushort> const &,TokenHandle const &,PROXY_SETTINGS const *)

- ea: `0x18000815c`
- end: `0x180008499`
- name: `??0PROXY_SETTINGS_CONTAINER@@QEAA@AEBV?$GenericStringHandle@G@@AEBVTokenHandle@@PEBUPROXY_SETTINGS@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(PROXY_SETTINGS_CONTAINER *this)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006b40`
- `0x1800073f0`
- `0x1800074d0`

## callees

- `0x1800065ac`
- `0x18000815c`
- `0x180008b70`
- `0x18000db20`
- `0x180033480`
- `0x18003acd8`
- `0x180077798`
- `0x180080430`
- `0x180092f5c`
- `0x18009b668`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800082a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000834e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000834e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083cc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008344`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008344`
- `WINHTTP!WinHttpCloseHandle` at `0x180008430`
- `WINHTTP!WinHttpCloseHandle` at `0x180008430`
- `WINHTTP!WinHttpOpen` at `0x1800083ac`
- `WINHTTP!WinHttpOpen` at `0x1800083ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
PROXY_SETTINGS_CONTAINER *__fastcall PROXY_SETTINGS_CONTAINER::PROXY_SETTINGS_CONTAINER(
        PROXY_SETTINGS_CONTAINER *this,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  int v6; // eax
  __int64 v7; // rax
  _DWORD *v8; // rax
  signed int LastError; // eax
  HINTERNET v10; // r15
  unsigned int v11; // eax
  void *v12; // r14
  HoldCritSec *v13; // rdi
  void **pExceptionObject; // [rsp+38h] [rbp-69h] BYREF
  __int128 v16; // [rsp+40h] [rbp-61h]
  int v17; // [rsp+50h] [rbp-51h]
  int v18; // [rsp+54h] [rbp-4Dh]
  int v19; // [rsp+58h] [rbp-49h]
  void **v20; // [rsp+98h] [rbp-9h] BYREF
  char v21; // [rsp+A0h] [rbp-1h]
  __int64 v22; // [rsp+A8h] [rbp+7h]
  __int64 v23; // [rsp+B0h] [rbp+Fh]
  _DWORD *v24; // [rsp+B8h] [rbp+17h]
  __int64 v25; // [rsp+C0h] [rbp+1Fh]
  void *v26; // [rsp+C8h] [rbp+27h]
  PROXY_SETTINGS_CONTAINER *v27; // [rsp+108h] [rbp+67h] BYREF
  HoldCritSec *v28; // [rsp+110h] [rbp+6Fh]

  v27 = this;
  if ( !*(_DWORD *)a4 )
    goto LABEL_5;
  if ( *(_DWORD *)a4 != 1 )
  {
    if ( *(_DWORD *)a4 == 2 )
    {
      v6 = 3;
      goto LABEL_6;
    }
    if ( *(_DWORD *)a4 == 3 )
    {
LABEL_5:
      v6 = 0;
      goto LABEL_6;
    }
  }
  v6 = 1;
LABEL_6:
  *(_DWORD *)this = v6;
  _InterlockedAdd(&dword_180145058, 1u);
  *((_QWORD *)this + 1) = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedAdd(&dword_180145058, 1u);
  *((_QWORD *)this + 2) = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedAdd(&dword_180145058, 1u);
  *((_QWORD *)this + 4) = &GenericStringHandle<unsigned short>::s_EmptyString;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  v7 = *a3;
  *((_QWORD *)this + 8) = *a3;
  _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
  _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)a2 + 8LL), 1u);
  *((_QWORD *)this + 9) = *(_QWORD *)a2;
  CCritSec2::CCritSec2((PROXY_SETTINGS_CONTAINER *)((char *)this + 80), a2);
  *((_QWORD *)this + 16) = 0;
  *((_BYTE *)this + 136) = 0;
  if ( *(_DWORD *)this )
  {
    if ( *(_DWORD *)this == 1 )
    {
LABEL_10:
      PROXY_SETTINGS_CONTAINER::ResetCurrentProxy(this);
      return this;
    }
    if ( *(_DWORD *)this == 3 )
    {
      GenericStringHandle<unsigned short>::operator=((char *)this + 16, *(_QWORD *)(a4 + 8));
      GenericStringHandle<unsigned short>::operator=((char *)this + 8, *(_QWORD *)(a4 + 16));
      goto LABEL_10;
    }
  }
  else
  {
    CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v20);
    v21 = 0;
    v22 = *((_QWORD *)this + 8);
    _InterlockedAdd((volatile signed __int32 *)(v22 + 8), 1u);
    v23 = 0;
    v8 = HeapAlloc(hBitsHeap, 8u, 4u);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
      v16 = 0;
      pExceptionObject = &ComError::`vftable';
      v17 = -2147024882;
      v18 = 0;
      v19 = 1;
      throw (ComError *)&pExceptionObject;
    }
    *v8 = 1;
    v24 = v8;
    v25 = 0;
    _InterlockedAdd(&dword_180145058, 1u);
    v26 = &GenericStringHandle<unsigned short>::s_EmptyString;
    if ( !v21 )
    {
      if ( !ImpersonateLoggedOnUser(*(HANDLE *)v22) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = 0;
        pExceptionObject = &ComError::`vftable';
        v17 = LastError;
        v18 = 0;
        v19 = 1;
        throw (ComError *)&pExceptionObject;
      }
      v21 = 1;
    }
    v10 = WinHttpOpen(L"Microsoft BITS/7.8", 0, 0, 0, 0x10000000u);
    if ( !v10 )
    {
      if ( (int)GetLastError() > 0 )
        v11 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v11 = GetLastError();
      v16 = 0;
      pExceptionObject = &ComError::`vftable';
      v17 = v11;
      v18 = 576;
      v19 = 1;
      throw (ComError *)&pExceptionObject;
    }
    LockableHINTERNET::ScopedHandleLock((LPCRITICAL_SECTION)this + 2);
    v12 = (void *)*((_QWORD *)this + 16);
    if ( v12 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v27);
      WinHttpCloseHandle(v12);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v27);
    }
    *((_QWORD *)this + 16) = v10;
    v13 = v28;
    if ( v28 )
    {
      HoldCritSec::~HoldCritSec(v28);
      operator delete(v13, 0x10u);
    }
    *((_BYTE *)this + 136) = *(_DWORD *)a4 == 3;
    CNestedImpersonation::~CNestedImpersonation(&v20);
  }
  return this;
}

```

## disassembly

```asm
0x18000815c  mov     rax, rsp
0x18000815f  mov     [rax+18h], rbx
0x180008163  mov     [rax+20h], rsi
0x180008167  mov     [rax+8], rcx
0x18000816b  push    rbp
0x18000816c  push    rdi
0x18000816d  push    r13
0x18000816f  push    r14
0x180008171  push    r15
0x180008173  lea     rbp, [rax-5Fh]
0x180008177  sub     rsp, 0D0h
0x18000817e  mov     rsi, r9
0x180008181  mov     rbx, rcx
0x180008184  mov     ecx, [r9]
0x180008187  mov     r13d, 1
0x18000818d  test    ecx, ecx
0x18000818f  jz      short loc_1800081AC
0x180008191  sub     ecx, r13d
0x180008194  jz      loc_180008266
0x18000819a  sub     ecx, r13d
0x18000819d  jz      loc_18000825C
0x1800081a3  cmp     ecx, r13d
0x1800081a6  jnz     loc_180008266
0x1800081ac  xor     eax, eax
0x1800081ae  mov     [rbx], eax
0x1800081b0  lock add cs:dword_180145058, r13d
0x1800081b8  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x1800081bf  mov     [rbx+8], rax
0x1800081c3  lock add cs:dword_180145058, r13d
0x1800081cb  mov     [rbx+10h], rax
0x1800081cf  lock add cs:dword_180145058, r13d
0x1800081d7  mov     [rbx+20h], rax
0x1800081db  mov     qword ptr [rbx+30h], 0
0x1800081e3  mov     qword ptr [rbx+38h], 0
0x1800081eb  mov     rax, [r8]
0x1800081ee  mov     [rbx+40h], rax
0x1800081f2  lock add [rax+8], r13d
0x1800081f7  mov     rax, [rdx]
0x1800081fa  lock add [rax+8], r13d
0x1800081ff  mov     rax, [rdx]
0x180008202  mov     [rbx+48h], rax
0x180008206  lea     rcx, [rbx+50h]; this
0x18000820a  call    ??0CCritSec2@@QEAA@_N@Z; CCritSec2::CCritSec2(bool)
0x18000820f  mov     qword ptr [rbx+80h], 0
0x18000821a  mov     byte ptr [rbx+88h], 0
0x180008221  mov     edx, [rbx]
0x180008223  test    edx, edx
0x180008225  jz      short loc_18000826E
0x180008227  sub     edx, 1
0x18000822a  jz      short loc_18000824F
0x18000822c  cmp     edx, 2
0x18000822f  jnz     loc_18000847A
0x180008235  mov     rdx, [rsi+8]
0x180008239  lea     rcx, [rbx+10h]
0x18000823d  call    ??4?$GenericStringHandle@G@@QEAAXPEBG@Z; GenericStringHandle<ushort>::operator=(ushort const *)
0x180008242  mov     rdx, [rsi+10h]
0x180008246  lea     rcx, [rbx+8]
0x18000824a  call    ??4?$GenericStringHandle@G@@QEAAXPEBG@Z; GenericStringHandle<ushort>::operator=(ushort const *)
0x18000824f  mov     rcx, rbx; this
0x180008252  call    ?ResetCurrentProxy@PROXY_SETTINGS_CONTAINER@@QEAAXXZ; PROXY_SETTINGS_CONTAINER::ResetCurrentProxy(void)
0x180008257  jmp     loc_18000847A
0x18000825c  mov     eax, 3
0x180008261  jmp     loc_1800081AE
0x180008266  mov     eax, r13d
0x180008269  jmp     loc_1800081AE
0x18000826e  lea     rcx, [rbp+57h+var_60]; this
0x180008272  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x180008277  nop
0x180008278  mov     [rbp+57h+var_58], 0
0x18000827c  mov     rax, [rbx+40h]
0x180008280  mov     [rbp+57h+var_50], rax
0x180008284  lock add [rax+8], r13d
0x180008289  mov     [rbp+57h+var_48], 0
0x180008291  mov     r14d, 4
0x180008297  mov     r8d, r14d; dwBytes
0x18000829a  lea     edx, [r14+4]; dwFlags
0x18000829e  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800082a5  call    cs:__imp_HeapAlloc
0x1800082ab  test    rax, rax
0x1800082ae  jnz     short loc_180008315
0x1800082b0  lea     rax, WPP_GLOBAL_Control
0x1800082b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082be  cmp     rcx, rax
0x1800082c1  jz      short loc_1800082E0
0x1800082c3  test    [rcx+1Ch], r14b
0x1800082c7  jz      short loc_1800082E0
0x1800082c9  lea     edx, [r14+6]
0x1800082cd  mov     r9d, r14d
0x1800082d0  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800082d7  mov     rcx, [rcx+10h]
0x1800082db  call    WPP_SF_d
0x1800082e0  xorps   xmm0, xmm0
0x1800082e3  movups  [rbp+57h+var_B8], xmm0
0x1800082e7  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800082ee  mov     [rbp+57h+pExceptionObject], rcx
0x1800082f2  mov     [rbp+57h+var_A8], 8007000Eh
0x1800082f9  mov     [rbp+57h+var_A4], 0
0x180008300  mov     [rbp+57h+var_A0], r13d
0x180008304  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000830b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000830f  call    _CxxThrowException_0
0x180008315  mov     [rax], r13d
0x180008318  mov     [rbp+57h+var_40], rax
0x18000831c  mov     [rbp+57h+var_38], 0
0x180008324  lock add cs:dword_180145058, r13d
0x18000832c  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180008333  mov     [rbp+57h+var_30], rax
0x180008337  cmp     [rbp+57h+var_58], 0
0x18000833b  jnz     short loc_180008395
0x18000833d  mov     rcx, [rbp+57h+var_50]
0x180008341  mov     rcx, [rcx]; hToken
0x180008344  call    cs:__imp_ImpersonateLoggedOnUser
0x18000834a  test    eax, eax
0x18000834c  jnz     short loc_180008391
0x18000834e  call    cs:__imp_GetLastError
0x180008354  test    eax, eax
0x180008356  jle     short loc_180008360
0x180008358  movzx   eax, ax
0x18000835b  or      eax, 80070000h
0x180008360  xorps   xmm0, xmm0
0x180008363  movups  [rbp+57h+var_B8], xmm0
0x180008367  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000836e  mov     [rbp+57h+pExceptionObject], rcx
0x180008372  mov     [rbp+57h+var_A8], eax
0x180008375  mov     [rbp+57h+var_A4], 0
0x18000837c  mov     [rbp+57h+var_A0], r13d
0x180008380  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180008387  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000838b  call    _CxxThrowException_0
0x180008391  mov     [rbp+57h+var_58], r13b
0x180008395  mov     [rsp+0F0h+dwFlags], 10000000h; dwFlags
0x18000839d  xor     r9d, r9d; pszProxyBypassW
0x1800083a0  xor     r8d, r8d; pszProxyW
0x1800083a3  xor     edx, edx; dwAccessType
0x1800083a5  lea     rcx, pszAgentW; "Microsoft BITS/7.8"
0x1800083ac  call    cs:__imp_WinHttpOpen
0x1800083b2  mov     r15, rax
0x1800083b5  test    rax, rax
0x1800083b8  jnz     short loc_18000840B
0x1800083ba  call    cs:__imp_GetLastError
0x1800083c0  test    eax, eax
0x1800083c2  jg      short loc_1800083CC
0x1800083c4  call    cs:__imp_GetLastError
0x1800083ca  jmp     short loc_1800083DA
0x1800083cc  call    cs:__imp_GetLastError
0x1800083d2  movzx   eax, ax
0x1800083d5  or      eax, 80070000h
0x1800083da  xorps   xmm0, xmm0
0x1800083dd  movups  [rbp+57h+var_B8], xmm0
0x1800083e1  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800083e8  mov     [rbp+57h+pExceptionObject], rcx
0x1800083ec  mov     [rbp+57h+var_A8], eax
0x1800083ef  mov     [rbp+57h+var_A4], 240h
0x1800083f6  mov     [rbp+57h+var_A0], r13d
0x1800083fa  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180008401  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180008405  call    _CxxThrowException_0
0x18000840b  lea     rdx, [rbp+57h+arg_8]
0x18000840f  lea     rcx, [rbx+50h]; lpCriticalSection
0x180008413  call    ?ScopedHandleLock@LockableHINTERNET@@QEAA?AV?$unique_ptr@VHoldCritSec@@U?$default_delete@VHoldCritSec@@@std@@@std@@XZ; LockableHINTERNET::ScopedHandleLock(void)
0x180008418  mov     r14, [rbx+80h]
0x18000841f  test    r14, r14
0x180008422  jz      short loc_18000843F
0x180008424  lea     rcx, [rbp+57h+arg_0]; this
0x180008428  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000842d  mov     rcx, r14; hInternet
0x180008430  call    cs:__imp_WinHttpCloseHandle
0x180008436  lea     rcx, [rbp+57h+arg_0]; this
0x18000843a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000843f  mov     [rbx+80h], r15
0x180008446  mov     rdi, [rbp+57h+arg_8]
0x18000844a  test    rdi, rdi
0x18000844d  jz      short loc_180008464
0x18000844f  mov     rcx, rdi; this
0x180008452  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x180008457  mov     edx, 10h; unsigned __int64
0x18000845c  mov     rcx, rdi; void *
0x18000845f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008464  cmp     dword ptr [rsi], 3
0x180008467  setz    al
0x18000846a  mov     [rbx+88h], al
0x180008470  lea     rcx, [rbp+57h+var_60]; this
0x180008474  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x180008479  nop
0x18000847a  mov     rax, rbx
0x18000847d  lea     r11, [rsp+0F0h+var_20]
0x180008485  mov     rbx, [r11+40h]
0x180008489  mov     rsi, [r11+48h]
0x18000848d  mov     rsp, r11
0x180008490  pop     r15
0x180008492  pop     r14
0x180008494  pop     r13
0x180008496  pop     rdi
0x180008497  pop     rbp
0x180008498  retn
```
