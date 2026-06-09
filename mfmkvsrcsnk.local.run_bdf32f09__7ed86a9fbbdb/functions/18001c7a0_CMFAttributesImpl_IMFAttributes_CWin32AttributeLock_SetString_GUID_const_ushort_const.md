# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x18001c7a0`
- end: `0x18001c86d`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036c5`
- `0x18000e798`
- `0x18001c7a0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c80f`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 Item; // rax
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  size_t v11; // rbp
  void *v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  v7 = Item;
  if ( !a3 )
    goto LABEL_2;
  if ( !Item )
  {
LABEL_4:
    v8 = -2147024882;
    goto LABEL_11;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 2 * v9 + 2;
  if ( v10 < 0xFFFFFFFF )
  {
    v11 = (unsigned int)v10;
    v12 = CoTaskMemAlloc((unsigned int)v10);
    *(_QWORD *)(v7 + 8) = v12;
    if ( v12 )
    {
      v8 = 0;
      memcpy_0(v12, a3, v11);
      *(_WORD *)v7 = 31;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_11;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_4;
  }
LABEL_2:
  v8 = -2147024809;
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x18001c7a0  push    rbx
0x18001c7a2  push    rbp
0x18001c7a3  push    rsi
0x18001c7a4  push    rdi
0x18001c7a5  push    r12
0x18001c7a7  push    r14
0x18001c7a9  push    r15
0x18001c7ab  sub     rsp, 20h
0x18001c7af  mov     rdi, rcx
0x18001c7b2  mov     r14, r8
0x18001c7b5  add     rcx, 8; lpCriticalSection
0x18001c7b9  mov     rbx, rdx
0x18001c7bc  call    cs:__imp_EnterCriticalSection
0x18001c7c2  mov     rdx, rbx
0x18001c7c5  mov     rcx, rdi
0x18001c7c8  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001c7cd  xor     r12d, r12d
0x18001c7d0  mov     rsi, rax
0x18001c7d3  test    r14, r14
0x18001c7d6  jnz     short loc_18001C7DF
0x18001c7d8  mov     ebx, 80070057h
0x18001c7dd  jmp     short loc_18001C852
0x18001c7df  test    rsi, rsi
0x18001c7e2  jnz     short loc_18001C7EB
0x18001c7e4  mov     ebx, 8007000Eh
0x18001c7e9  jmp     short loc_18001C852
0x18001c7eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c7ef  inc     rax
0x18001c7f2  cmp     [r14+rax*2], r12w
0x18001c7f7  jnz     short loc_18001C7EF
0x18001c7f9  lea     rax, ds:2[rax*2]
0x18001c801  mov     ecx, 0FFFFFFFFh
0x18001c806  cmp     rax, rcx
0x18001c809  jnb     short loc_18001C7D8
0x18001c80b  mov     ecx, eax; cb
0x18001c80d  mov     ebp, eax
0x18001c80f  call    cs:__imp_CoTaskMemAlloc
0x18001c815  mov     [rsi+8], rax
0x18001c819  test    rax, rax
0x18001c81c  jnz     short loc_18001C835
0x18001c81e  mov     rax, [rdi]
0x18001c821  mov     rdx, rbx
0x18001c824  mov     rcx, rdi
0x18001c827  mov     rax, [rax+98h]
0x18001c82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c833  jmp     short loc_18001C7E4
0x18001c835  mov     r8, rbp; Size
0x18001c838  mov     rdx, r14; Src
0x18001c83b  mov     rcx, rax; void *
0x18001c83e  mov     ebx, r12d
0x18001c841  call    memcpy_0
0x18001c846  mov     word ptr [rsi], 1Fh
0x18001c84b  mov     dword ptr [rdi+40h], 1
0x18001c852  lea     rcx, [rdi+8]; lpCriticalSection
0x18001c856  call    cs:__imp_LeaveCriticalSection
0x18001c85c  mov     eax, ebx
0x18001c85e  add     rsp, 20h
0x18001c862  pop     r15
0x18001c864  pop     r14
0x18001c866  pop     r12
0x18001c868  pop     rdi
0x18001c869  pop     rsi
0x18001c86a  pop     rbp
0x18001c86b  pop     rbx
0x18001c86c  retn
```
