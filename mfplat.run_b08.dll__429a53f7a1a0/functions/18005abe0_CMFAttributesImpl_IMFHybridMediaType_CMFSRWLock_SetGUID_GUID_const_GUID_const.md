# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18005abe0`
- end: `0x18005acb4`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180149a90`

## callees

- `0x18002f160`
- `0x18005abe0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ac10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ac10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ac9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ac9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005abf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005abf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ac38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ac38`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::SetGUID(__int64 a1, __int64 a2, _OWORD *a3)
{
  DWORD CurrentThreadId; // edi
  __int64 Item; // r14
  unsigned int v8; // edi
  _OWORD *v9; // rax
  int v10; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( *(_DWORD *)(a1 + 24) == CurrentThreadId )
  {
    ++*(_DWORD *)(a1 + 28);
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    *(_DWORD *)(a1 + 24) = CurrentThreadId;
  }
  Item = CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v9 = CoTaskMemAlloc(0x10u);
    *(_QWORD *)(Item + 8) = v9;
    if ( v9 )
    {
      *(_WORD *)Item = 72;
      v8 = 0;
      *v9 = *a3;
      *(_DWORD *)(a1 + 48) = 1;
    }
    else
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
      v8 = -2147024882;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  v10 = *(_DWORD *)(a1 + 28);
  if ( v10 )
  {
    result = v8;
    *(_DWORD *)(a1 + 28) = v10 - 1;
  }
  else
  {
    *(_DWORD *)(a1 + 24) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18005abe0  push    rbx
0x18005abe2  push    rbp
0x18005abe3  push    rsi
0x18005abe4  push    rdi
0x18005abe5  push    r14
0x18005abe7  push    r15
0x18005abe9  sub     rsp, 28h
0x18005abed  mov     r15, r8
0x18005abf0  mov     rbp, rdx
0x18005abf3  mov     rsi, rcx
0x18005abf6  call    cs:__imp_GetCurrentThreadId
0x18005abfc  mov     r9d, [rsi+18h]
0x18005ac00  mov     edi, eax
0x18005ac02  cmp     r9d, eax
0x18005ac05  jnz     short loc_18005AC0C
0x18005ac07  inc     dword ptr [rsi+1Ch]
0x18005ac0a  jmp     short loc_18005AC19
0x18005ac0c  lea     rcx, [rsi+10h]; SRWLock
0x18005ac10  call    cs:__imp_AcquireSRWLockExclusive
0x18005ac16  mov     [rsi+18h], edi
0x18005ac19  mov     rdx, rbp
0x18005ac1c  mov     rcx, rsi
0x18005ac1f  call    ?CreateItem@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CreateItem(_GUID const &)
0x18005ac24  mov     r14, rax
0x18005ac27  test    rax, rax
0x18005ac2a  jnz     short loc_18005AC33
0x18005ac2c  mov     edi, 8007000Eh
0x18005ac31  jmp     short loc_18005AC79
0x18005ac33  mov     ecx, 10h; cb
0x18005ac38  call    cs:__imp_CoTaskMemAlloc
0x18005ac3e  mov     [r14+8], rax
0x18005ac42  test    rax, rax
0x18005ac45  jnz     short loc_18005AC63
0x18005ac47  mov     rax, [rsi]
0x18005ac4a  mov     rdx, rbp
0x18005ac4d  mov     rcx, rsi
0x18005ac50  mov     rax, [rax+98h]
0x18005ac57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac5c  mov     edi, 8007000Eh
0x18005ac61  jmp     short loc_18005AC79
0x18005ac63  mov     word ptr [r14], 48h ; 'H'
0x18005ac69  xor     edi, edi
0x18005ac6b  movups  xmm0, xmmword ptr [r15]
0x18005ac6f  movups  xmmword ptr [rax], xmm0
0x18005ac72  mov     dword ptr [rsi+30h], 1
0x18005ac79  mov     ecx, [rsi+1Ch]
0x18005ac7c  test    ecx, ecx
0x18005ac7e  jz      short loc_18005AC94
0x18005ac80  dec     ecx
0x18005ac82  mov     eax, edi
0x18005ac84  mov     [rsi+1Ch], ecx
0x18005ac87  add     rsp, 28h
0x18005ac8b  pop     r15
0x18005ac8d  pop     r14
0x18005ac8f  pop     rdi
0x18005ac90  pop     rsi
0x18005ac91  pop     rbp
0x18005ac92  pop     rbx
0x18005ac93  retn
0x18005ac94  lea     rcx, [rsi+10h]; SRWLock
0x18005ac98  mov     dword ptr [rsi+18h], 0
0x18005ac9f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005aca5  mov     eax, edi
0x18005aca7  add     rsp, 28h
0x18005acab  pop     r15
0x18005acad  pop     r14
0x18005acaf  pop     rdi
0x18005acb0  pop     rsi
0x18005acb1  pop     rbp
0x18005acb2  pop     rbx
0x18005acb3  retn
```
