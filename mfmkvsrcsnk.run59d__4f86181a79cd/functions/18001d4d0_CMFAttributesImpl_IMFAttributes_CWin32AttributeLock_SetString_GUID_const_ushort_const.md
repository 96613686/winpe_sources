# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x18001d4d0`
- end: `0x18001d5b0`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003705`
- `0x18000ede4`
- `0x18001d4d0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d592`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d545`

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
0x18001d4d0  push    rbx
0x18001d4d2  push    rbp
0x18001d4d3  push    rsi
0x18001d4d4  push    rdi
0x18001d4d5  push    r12
0x18001d4d7  push    r14
0x18001d4d9  push    r15
0x18001d4db  sub     rsp, 20h
0x18001d4df  mov     rdi, rcx
0x18001d4e2  mov     r14, r8
0x18001d4e5  add     rcx, 8; lpCriticalSection
0x18001d4e9  mov     rbx, rdx
0x18001d4ec  call    cs:__imp_EnterCriticalSection
0x18001d4f3  nop     dword ptr [rax+rax+00h]
0x18001d4f8  mov     rdx, rbx
0x18001d4fb  mov     rcx, rdi
0x18001d4fe  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001d503  xor     r12d, r12d
0x18001d506  mov     rsi, rax
0x18001d509  test    r14, r14
0x18001d50c  jnz     short loc_18001D515
0x18001d50e  mov     ebx, 80070057h
0x18001d513  jmp     short loc_18001D58E
0x18001d515  test    rsi, rsi
0x18001d518  jnz     short loc_18001D521
0x18001d51a  mov     ebx, 8007000Eh
0x18001d51f  jmp     short loc_18001D58E
0x18001d521  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d525  inc     rax
0x18001d528  cmp     [r14+rax*2], r12w
0x18001d52d  jnz     short loc_18001D525
0x18001d52f  lea     rax, ds:2[rax*2]
0x18001d537  mov     ecx, 0FFFFFFFFh
0x18001d53c  cmp     rax, rcx
0x18001d53f  jnb     short loc_18001D50E
0x18001d541  mov     ecx, eax; cb
0x18001d543  mov     ebp, eax
0x18001d545  call    cs:__imp_CoTaskMemAlloc
0x18001d54c  nop     dword ptr [rax+rax+00h]
0x18001d551  mov     [rsi+8], rax
0x18001d555  test    rax, rax
0x18001d558  jnz     short loc_18001D571
0x18001d55a  mov     rax, [rdi]
0x18001d55d  mov     rdx, rbx
0x18001d560  mov     rcx, rdi
0x18001d563  mov     rax, [rax+98h]
0x18001d56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d56f  jmp     short loc_18001D51A
0x18001d571  mov     r8, rbp; Size
0x18001d574  mov     rdx, r14; Src
0x18001d577  mov     rcx, rax; void *
0x18001d57a  mov     ebx, r12d
0x18001d57d  call    memcpy_0
0x18001d582  mov     word ptr [rsi], 1Fh
0x18001d587  mov     dword ptr [rdi+40h], 1
0x18001d58e  lea     rcx, [rdi+8]; lpCriticalSection
0x18001d592  call    cs:__imp_LeaveCriticalSection
0x18001d599  nop     dword ptr [rax+rax+00h]
0x18001d59e  mov     eax, ebx
0x18001d5a0  add     rsp, 20h
0x18001d5a4  pop     r15
0x18001d5a6  pop     r14
0x18001d5a8  pop     r12
0x18001d5aa  pop     rdi
0x18001d5ab  pop     rsi
0x18001d5ac  pop     rbp
0x18001d5ad  pop     rbx
0x18001d5ae  retn
```
