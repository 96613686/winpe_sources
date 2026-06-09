# ClientOperation::HcsGetOperationProperties(_GUID const &,ushort const *,ushort * *)

- ea: `0x18002a744`
- end: `0x18002ab04`
- name: `?HcsGetOperationProperties@ClientOperation@@QEAAJAEBU_GUID@@PEBGPEAPEAG@Z`
- size: `960`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015fc0`

## callees

- `0x1800067c0`
- `0x18000f1b4`
- `0x18002a744`
- `0x18002b26c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a781`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a781`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a7ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a80d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a93c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002aa2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002aacd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a7ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a80d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002a93c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002aa2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002aacd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a88b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a88b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a883`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a94b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a9e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aadc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a7bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a883`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a94b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a9e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aadc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a9ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a9ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa6c`

## string_xrefs

- `0x18002a791`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x18002a7f8`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x18002a8db`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x18002a9a8`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`

## pseudocode

```c
__int64 __fastcall ClientOperation::HcsGetOperationProperties(
        PSRWLOCK SRWLock,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 *Ptr; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r13
  volatile signed __int32 *v11; // rdi
  PVOID v12; // r12
  int v13; // eax
  unsigned int v14; // r14d
  int v15; // [rsp+20h] [rbp-79h]
  int v18[2]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v19; // [rsp+88h] [rbp-11h]
  __int64 v20; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  AcquireSRWLockShared(SRWLock);
  if ( HIDWORD(SRWLock[1].Ptr) != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\clientoperation.cpp",
      (const char *)0x80370105LL,
      v15);
    ReleaseSRWLockShared(SRWLock);
    return 2151088389LL;
  }
  Ptr = (__int64 *)SRWLock[2].Ptr;
  if ( !Ptr )
  {
    v8 = 194;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\clientoperation.cpp",
      (const char *)0x80070057LL,
      v15);
    ReleaseSRWLockShared(SRWLock);
    return 2147942487LL;
  }
  if ( !SRWLock[26].Ptr )
  {
    v8 = 195;
    goto LABEL_9;
  }
  if ( !a4 )
  {
    v8 = 196;
    goto LABEL_9;
  }
  v9 = Ptr[1];
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  v10 = *Ptr;
  v11 = (volatile signed __int32 *)Ptr[1];
  v12 = SRWLock[26].Ptr;
  *(RTL_SRWLOCK *)v18 = SRWLock[10];
  v20 = 0;
  v19 = 0;
  v13 = (*(__int64 (__fastcall **)(PVOID, const struct _GUID *, _QWORD, const unsigned __int16 *))(*(_QWORD *)v12 + 272LL))(
          v12,
          a2,
          *(_QWORD *)(v10 + 40),
          a3);
  v14 = v13;
  if ( v13 >= 0 )
  {
    *a4 = 0;
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    ReleaseSRWLockShared(SRWLock);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\clientoperation.cpp",
      (const char *)(unsigned int)v13,
      (int)v18);
    if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
    ReleaseSRWLockShared(SRWLock);
    return v14;
  }
}

```

## disassembly

```asm
0x18002a744  push    rbp
0x18002a746  push    rbx
0x18002a747  push    rsi
0x18002a748  push    rdi
0x18002a749  push    r12
0x18002a74b  push    r13
0x18002a74d  push    r14
0x18002a74f  push    r15
0x18002a751  lea     rbp, [rsp-1Fh]
0x18002a756  sub     rsp, 0B8h
0x18002a75d  mov     rax, cs:__security_cookie
0x18002a764  xor     rax, rsp
0x18002a767  mov     [rbp+57h+var_50], rax
0x18002a76b  mov     r15, r9
0x18002a76e  mov     [rbp+57h+var_90], r8
0x18002a772  mov     [rbp+57h+var_88], rdx
0x18002a776  mov     rsi, rcx
0x18002a779  mov     [rbp+57h+hMem], 0
0x18002a781  call    cs:__imp_AcquireSRWLockShared
0x18002a787  cmp     dword ptr [rsi+0Ch], 1
0x18002a78b  jz      short loc_18002A7C9
0x18002a78d  mov     rcx, [rbp+5Fh]; this
0x18002a791  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\dll\\lib\\core\\c"...
0x18002a798  mov     ebx, 80370105h
0x18002a79d  mov     edx, 0C1h; void *
0x18002a7a2  mov     r9d, ebx; char *
0x18002a7a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a7aa  mov     rcx, rsi; SRWLock
0x18002a7ad  call    cs:__imp_ReleaseSRWLockShared
0x18002a7b3  mov     rcx, [rbp+57h+hMem]; hMem
0x18002a7b7  test    rcx, rcx
0x18002a7ba  jz      short loc_18002A7C2
0x18002a7bc  call    cs:__imp_LocalFree
0x18002a7c2  mov     eax, ebx
0x18002a7c4  jmp     loc_18002AAE4
0x18002a7c9  mov     rdi, [rsi+10h]
0x18002a7cd  test    rdi, rdi
0x18002a7d0  jnz     short loc_18002A7D9
0x18002a7d2  mov     edx, 0C2h
0x18002a7d7  jmp     short loc_18002A7F4
0x18002a7d9  cmp     qword ptr [rsi+0D0h], 0
0x18002a7e1  jnz     short loc_18002A7EA
0x18002a7e3  mov     edx, 0C3h
0x18002a7e8  jmp     short loc_18002A7F4
0x18002a7ea  test    r15, r15
0x18002a7ed  jnz     short loc_18002A82C
0x18002a7ef  mov     edx, 0C4h; void *
0x18002a7f4  mov     rcx, [rbp+5Fh]; this
0x18002a7f8  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\dll\\lib\\core\\c"...
0x18002a7ff  mov     r9d, 80070057h; char *
0x18002a805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a80a  mov     rcx, rsi; SRWLock
0x18002a80d  call    cs:__imp_ReleaseSRWLockShared
0x18002a813  mov     rcx, [rbp+57h+hMem]; hMem
0x18002a817  test    rcx, rcx
0x18002a81a  jz      short loc_18002A822
0x18002a81c  call    cs:__imp_LocalFree
0x18002a822  mov     eax, 80070057h
0x18002a827  jmp     loc_18002AAE4
0x18002a82c  mov     rax, [rdi+8]
0x18002a830  test    rax, rax
0x18002a833  jz      short loc_18002A839
0x18002a835  lock inc dword ptr [rax+8]
0x18002a839  mov     r13, [rdi]
0x18002a83c  xorps   xmm0, xmm0
0x18002a83f  mov     rdi, [rdi+8]
0x18002a843  mov     rax, [rsi+50h]
0x18002a847  mov     r12, [rsi+0D0h]
0x18002a84e  mov     r14, [rbp+57h+hMem]
0x18002a852  mov     qword ptr [rbp+57h+var_70], rax
0x18002a856  xor     eax, eax
0x18002a858  mov     [rbp+57h+var_58], rax
0x18002a85c  mov     [rbp+57h+var_78], rax
0x18002a860  movups  [rbp+57h+var_68], xmm0
0x18002a864  mov     rax, [r12]
0x18002a868  mov     rax, [rax+110h]
0x18002a86f  mov     [rbp+57h+var_98], rax
0x18002a873  test    r14, r14
0x18002a876  jz      short loc_18002A895
0x18002a878  call    cs:__imp_GetLastError
0x18002a87e  mov     rcx, r14; hMem
0x18002a881  mov     ebx, eax
0x18002a883  call    cs:__imp_LocalFree
0x18002a889  mov     ecx, ebx; dwErrCode
0x18002a88b  call    cs:__imp_SetLastError
0x18002a891  mov     rax, [rbp+57h+var_98]
0x18002a895  mov     r9, [rbp+57h+var_90]
0x18002a899  lea     rcx, [rbp+57h+var_78]
0x18002a89d  mov     rdx, [rbp+57h+var_88]
0x18002a8a1  mov     [rsp+0F0h+var_C0], rcx
0x18002a8a6  lea     rcx, [rbp+57h+hMem]
0x18002a8aa  mov     [rsp+0F0h+var_C8], rcx
0x18002a8af  lea     rcx, [rbp+57h+var_70]
0x18002a8b3  mov     qword ptr [rsp+0F0h+var_D0], rcx; int
0x18002a8b8  mov     rcx, r12
0x18002a8bb  mov     [rbp+57h+hMem], 0
0x18002a8c3  mov     r8, [r13+28h]
0x18002a8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8cc  mov     r14d, eax
0x18002a8cf  test    eax, eax
0x18002a8d1  jns     loc_18002A959
0x18002a8d7  mov     rcx, [rbp+5Fh]; this
0x18002a8db  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\dll\\lib\\core\\c"...
0x18002a8e2  mov     r9d, eax; char *
0x18002a8e5  mov     edx, 0CAh; void *
0x18002a8ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a8ef  mov     rcx, [rbp+57h+var_78]; hMem
0x18002a8f3  test    rcx, rcx
0x18002a8f6  jz      short loc_18002A8FE
0x18002a8f8  call    cs:__imp_LocalFree
0x18002a8fe  test    rdi, rdi
0x18002a901  jz      short loc_18002A939
0x18002a903  or      ebx, 0FFFFFFFFh
0x18002a906  mov     eax, ebx
0x18002a908  lock xadd [rdi+8], eax
0x18002a90d  add     eax, ebx
0x18002a90f  jnz     short loc_18002A939
0x18002a911  mov     rax, [rdi]
0x18002a914  mov     rcx, rdi
0x18002a917  mov     rax, [rax]
0x18002a91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a91f  mov     eax, ebx
0x18002a921  lock xadd [rdi+0Ch], eax
0x18002a926  add     eax, ebx
0x18002a928  jnz     short loc_18002A939
0x18002a92a  mov     rax, [rdi]
0x18002a92d  mov     rcx, rdi
0x18002a930  mov     rax, [rax+8]
0x18002a934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a939  mov     rcx, rsi; SRWLock
0x18002a93c  call    cs:__imp_ReleaseSRWLockShared
0x18002a942  mov     rcx, [rbp+57h+hMem]; hMem
0x18002a946  test    rcx, rcx
0x18002a949  jz      short loc_18002A951
0x18002a94b  call    cs:__imp_LocalFree
0x18002a951  mov     eax, r14d
0x18002a954  jmp     loc_18002AAE4
0x18002a959  mov     ecx, [rsi+68h]
0x18002a95c  xorps   xmm0, xmm0
0x18002a95f  mov     rdx, [rbp+57h+hMem]; unsigned __int16 *
0x18002a963  and     ecx, 1
0x18002a966  mov     [rbp+57h+var_AC], 0
0x18002a96d  mov     [rbp+57h+var_B0], ecx
0x18002a970  movdqu  xmmword ptr [rbp+57h+pv], xmm0
0x18002a975  test    rdx, rdx
0x18002a978  jz      loc_18002AA48
0x18002a97e  lea     rcx, [rbp+57h+var_B0]; this
0x18002a982  call    ?make_string_nothrow@ClientStringAllocator@Details@@QEAAXPEBG@Z; Details::ClientStringAllocator::make_string_nothrow(ushort const *)
0x18002a987  mov     ecx, [rbp+57h+var_B0]
0x18002a98a  test    ecx, ecx
0x18002a98c  mov     r14, [rbp+57h+pv+8]
0x18002a990  mov     rbx, [rbp+57h+pv]
0x18002a994  mov     rax, r14
0x18002a997  cmovz   rax, rbx
0x18002a99b  test    rax, rax
0x18002a99e  jnz     loc_18002AA50
0x18002a9a4  mov     rcx, [rbp+5Fh]; this
0x18002a9a8  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\dll\\lib\\core\\c"...
0x18002a9af  mov     r15d, 8037011Ah
0x18002a9b5  mov     edx, 0D5h; void *
0x18002a9ba  mov     r9d, r15d; char *
0x18002a9bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a9c2  test    r14, r14
0x18002a9c5  jz      short loc_18002A9D0
0x18002a9c7  mov     rcx, r14; pv
0x18002a9ca  call    cs:__imp_CoTaskMemFree
0x18002a9d0  test    rbx, rbx
0x18002a9d3  jz      short loc_18002A9DE
0x18002a9d5  mov     rcx, rbx; hMem
0x18002a9d8  call    cs:__imp_LocalFree
0x18002a9de  mov     rcx, [rbp+57h+var_78]; hMem
0x18002a9e2  test    rcx, rcx
0x18002a9e5  jz      short loc_18002A9ED
0x18002a9e7  call    cs:__imp_LocalFree
0x18002a9ed  test    rdi, rdi
0x18002a9f0  jz      short loc_18002AA28
0x18002a9f2  or      ebx, 0FFFFFFFFh
0x18002a9f5  mov     eax, ebx
0x18002a9f7  lock xadd [rdi+8], eax
0x18002a9fc  add     eax, ebx
0x18002a9fe  jnz     short loc_18002AA28
0x18002aa00  mov     rax, [rdi]
0x18002aa03  mov     rcx, rdi
0x18002aa06  mov     rax, [rax]
0x18002aa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa0e  mov     eax, ebx
0x18002aa10  lock xadd [rdi+0Ch], eax
0x18002aa15  add     eax, ebx
0x18002aa17  jnz     short loc_18002AA28
0x18002aa19  mov     rax, [rdi]
0x18002aa1c  mov     rcx, rdi
0x18002aa1f  mov     rax, [rax+8]
0x18002aa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa28  mov     rcx, rsi; SRWLock
0x18002aa2b  call    cs:__imp_ReleaseSRWLockShared
0x18002aa31  mov     rcx, [rbp+57h+hMem]; hMem
0x18002aa35  test    rcx, rcx
0x18002aa38  jz      short loc_18002AA40
0x18002aa3a  call    cs:__imp_LocalFree
0x18002aa40  mov     eax, r15d
0x18002aa43  jmp     loc_18002AAE4
0x18002aa48  mov     r14, [rbp+57h+pv+8]
0x18002aa4c  mov     rbx, [rbp+57h+pv]
0x18002aa50  test    ecx, ecx
0x18002aa52  jnz     short loc_18002AA5B
0x18002aa54  mov     rax, rbx
0x18002aa57  xor     ebx, ebx
0x18002aa59  jmp     short loc_18002AA61
0x18002aa5b  mov     rax, r14
0x18002aa5e  xor     r14d, r14d
0x18002aa61  mov     [r15], rax
0x18002aa64  test    r14, r14
0x18002aa67  jz      short loc_18002AA72
0x18002aa69  mov     rcx, r14; pv
0x18002aa6c  call    cs:__imp_CoTaskMemFree
0x18002aa72  test    rbx, rbx
0x18002aa75  jz      short loc_18002AA80
0x18002aa77  mov     rcx, rbx; hMem
0x18002aa7a  call    cs:__imp_LocalFree
0x18002aa80  mov     rcx, [rbp+57h+var_78]; hMem
0x18002aa84  test    rcx, rcx
0x18002aa87  jz      short loc_18002AA8F
0x18002aa89  call    cs:__imp_LocalFree
0x18002aa8f  test    rdi, rdi
0x18002aa92  jz      short loc_18002AACA
0x18002aa94  or      ebx, 0FFFFFFFFh
0x18002aa97  mov     eax, ebx
0x18002aa99  lock xadd [rdi+8], eax
0x18002aa9e  add     eax, ebx
0x18002aaa0  jnz     short loc_18002AACA
0x18002aaa2  mov     rax, [rdi]
0x18002aaa5  mov     rcx, rdi
0x18002aaa8  mov     rax, [rax]
0x18002aaab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aab0  mov     eax, ebx
0x18002aab2  lock xadd [rdi+0Ch], eax
0x18002aab7  add     eax, ebx
0x18002aab9  jnz     short loc_18002AACA
0x18002aabb  mov     rax, [rdi]
0x18002aabe  mov     rcx, rdi
0x18002aac1  mov     rax, [rax+8]
0x18002aac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaca  mov     rcx, rsi; SRWLock
0x18002aacd  call    cs:__imp_ReleaseSRWLockShared
0x18002aad3  mov     rcx, [rbp+57h+hMem]; hMem
0x18002aad7  test    rcx, rcx
0x18002aada  jz      short loc_18002AAE2
0x18002aadc  call    cs:__imp_LocalFree
0x18002aae2  xor     eax, eax
0x18002aae4  mov     rcx, [rbp+57h+var_50]
0x18002aae8  xor     rcx, rsp; StackCookie
0x18002aaeb  call    __security_check_cookie
0x18002aaf0  add     rsp, 0B8h
0x18002aaf7  pop     r15
0x18002aaf9  pop     r14
0x18002aafb  pop     r13
0x18002aafd  pop     r12
0x18002aaff  pop     rdi
0x18002ab00  pop     rsi
0x18002ab01  pop     rbx
0x18002ab02  pop     rbp
0x18002ab03  retn
```
