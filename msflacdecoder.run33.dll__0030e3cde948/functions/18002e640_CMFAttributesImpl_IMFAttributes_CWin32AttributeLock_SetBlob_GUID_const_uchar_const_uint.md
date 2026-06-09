# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x18002e640`
- end: `0x18002e6e3`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016b0c`
- `0x18002b05c`
- `0x18002e640`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e6cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e6cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e65f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e65f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e682`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(
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
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
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
0x18002e640  push    rbx
0x18002e642  push    rbp
0x18002e643  push    rsi
0x18002e644  push    rdi
0x18002e645  push    r12
0x18002e647  push    r14
0x18002e649  push    r15
0x18002e64b  sub     rsp, 20h
0x18002e64f  mov     rdi, rcx
0x18002e652  mov     r15d, r9d
0x18002e655  add     rcx, 8; lpCriticalSection
0x18002e659  mov     r12, r8
0x18002e65c  mov     rbx, rdx
0x18002e65f  call    cs:__imp_EnterCriticalSection
0x18002e665  mov     rdx, rbx
0x18002e668  mov     rcx, rdi
0x18002e66b  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18002e670  mov     rsi, rax
0x18002e673  test    rax, rax
0x18002e676  jnz     short loc_18002E67F
0x18002e678  mov     ebx, 8007000Eh
0x18002e67d  jmp     short loc_18002E6C8
0x18002e67f  mov     rcx, r15; cb
0x18002e682  call    cs:__imp_CoTaskMemAlloc
0x18002e688  mov     [rsi+10h], rax
0x18002e68c  test    rax, rax
0x18002e68f  jnz     short loc_18002E6A8
0x18002e691  mov     rax, [rdi]
0x18002e694  mov     rdx, rbx
0x18002e697  mov     rcx, rdi
0x18002e69a  mov     rax, [rax+98h]
0x18002e6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6a6  jmp     short loc_18002E678
0x18002e6a8  xor     ebx, ebx
0x18002e6aa  mov     r8, r15; Size
0x18002e6ad  mov     rdx, r12; Src
0x18002e6b0  mov     rcx, rax; void *
0x18002e6b3  call    memcpy_0
0x18002e6b8  mov     word ptr [rsi], 1011h
0x18002e6bd  mov     [rsi+8], r15d
0x18002e6c1  mov     dword ptr [rdi+40h], 1
0x18002e6c8  lea     rcx, [rdi+8]; lpCriticalSection
0x18002e6cc  call    cs:__imp_LeaveCriticalSection
0x18002e6d2  mov     eax, ebx
0x18002e6d4  add     rsp, 20h
0x18002e6d8  pop     r15
0x18002e6da  pop     r14
0x18002e6dc  pop     r12
0x18002e6de  pop     rdi
0x18002e6df  pop     rsi
0x18002e6e0  pop     rbp
0x18002e6e1  pop     rbx
0x18002e6e2  retn
```
