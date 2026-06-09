# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x18001ca30`
- end: `0x18001cae6`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003705`
- `0x18000ede4`
- `0x18001ca30`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cac8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ca78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ca78`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  __int64 Item; // rsi
  unsigned int v9; // ebx
  void *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = CoTaskMemAlloc(v5);
    *(_QWORD *)(Item + 16) = v10;
    if ( v10 )
    {
      v9 = 0;
      memcpy_0(v10, a3, v5);
      *(_WORD *)Item = 4113;
      *(_DWORD *)(Item + 8) = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v9 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v9;
}

```

## disassembly

```asm
0x18001ca30  push    rbx
0x18001ca32  push    rbp
0x18001ca33  push    rsi
0x18001ca34  push    rdi
0x18001ca35  push    r12
0x18001ca37  push    r14
0x18001ca39  push    r15
0x18001ca3b  sub     rsp, 20h
0x18001ca3f  mov     rdi, rcx
0x18001ca42  mov     r15d, r9d
0x18001ca45  add     rcx, 8; lpCriticalSection
0x18001ca49  mov     r12, r8
0x18001ca4c  mov     rbx, rdx
0x18001ca4f  call    cs:__imp_EnterCriticalSection
0x18001ca56  nop     dword ptr [rax+rax+00h]
0x18001ca5b  mov     rdx, rbx
0x18001ca5e  mov     rcx, rdi
0x18001ca61  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001ca66  mov     rsi, rax
0x18001ca69  test    rax, rax
0x18001ca6c  jnz     short loc_18001CA75
0x18001ca6e  mov     ebx, 8007000Eh
0x18001ca73  jmp     short loc_18001CAC4
0x18001ca75  mov     rcx, r15; cb
0x18001ca78  call    cs:__imp_CoTaskMemAlloc
0x18001ca7f  nop     dword ptr [rax+rax+00h]
0x18001ca84  mov     [rsi+10h], rax
0x18001ca88  test    rax, rax
0x18001ca8b  jnz     short loc_18001CAA4
0x18001ca8d  mov     rax, [rdi]
0x18001ca90  mov     rdx, rbx
0x18001ca93  mov     rcx, rdi
0x18001ca96  mov     rax, [rax+98h]
0x18001ca9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caa2  jmp     short loc_18001CA6E
0x18001caa4  xor     ebx, ebx
0x18001caa6  mov     r8, r15; Size
0x18001caa9  mov     rdx, r12; Src
0x18001caac  mov     rcx, rax; void *
0x18001caaf  call    memcpy_0
0x18001cab4  mov     word ptr [rsi], 1011h
0x18001cab9  mov     [rsi+8], r15d
0x18001cabd  mov     dword ptr [rdi+40h], 1
0x18001cac4  lea     rcx, [rdi+8]; lpCriticalSection
0x18001cac8  call    cs:__imp_LeaveCriticalSection
0x18001cacf  nop     dword ptr [rax+rax+00h]
0x18001cad4  mov     eax, ebx
0x18001cad6  add     rsp, 20h
0x18001cada  pop     r15
0x18001cadc  pop     r14
0x18001cade  pop     r12
0x18001cae0  pop     rdi
0x18001cae1  pop     rsi
0x18001cae2  pop     rbp
0x18001cae3  pop     rbx
0x18001cae4  retn
```
