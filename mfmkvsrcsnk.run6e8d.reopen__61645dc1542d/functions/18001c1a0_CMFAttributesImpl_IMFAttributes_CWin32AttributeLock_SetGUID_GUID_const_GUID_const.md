# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x18001c1a0`
- end: `0x18001c230`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e798`
- `0x18001c1a0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c1b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c1b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c21d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c21d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c1dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c1dd`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetGUID(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 Item; // rsi
  unsigned int v7; // ebx
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v8 = CoTaskMemAlloc(0x10u);
    *(_QWORD *)(Item + 8) = v8;
    if ( v8 )
    {
      *(_WORD *)Item = 72;
      v7 = 0;
      *v8 = *a3;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v7 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x18001c1a0  push    rbx
0x18001c1a2  push    rbp
0x18001c1a3  push    rsi
0x18001c1a4  push    rdi
0x18001c1a5  push    r14
0x18001c1a7  sub     rsp, 20h
0x18001c1ab  mov     rdi, rcx
0x18001c1ae  mov     r14, r8
0x18001c1b1  add     rcx, 8; lpCriticalSection
0x18001c1b5  mov     rbx, rdx
0x18001c1b8  call    cs:__imp_EnterCriticalSection
0x18001c1be  mov     rdx, rbx
0x18001c1c1  mov     rcx, rdi
0x18001c1c4  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18001c1c9  mov     rsi, rax
0x18001c1cc  test    rax, rax
0x18001c1cf  jnz     short loc_18001C1D8
0x18001c1d1  mov     ebx, 8007000Eh
0x18001c1d6  jmp     short loc_18001C219
0x18001c1d8  mov     ecx, 10h; cb
0x18001c1dd  call    cs:__imp_CoTaskMemAlloc
0x18001c1e3  mov     [rsi+8], rax
0x18001c1e7  test    rax, rax
0x18001c1ea  jnz     short loc_18001C203
0x18001c1ec  mov     rax, [rdi]
0x18001c1ef  mov     rdx, rbx
0x18001c1f2  mov     rcx, rdi
0x18001c1f5  mov     rax, [rax+98h]
0x18001c1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c201  jmp     short loc_18001C1D1
0x18001c203  mov     word ptr [rsi], 48h ; 'H'
0x18001c208  xor     ebx, ebx
0x18001c20a  movups  xmm0, xmmword ptr [r14]
0x18001c20e  movdqu  xmmword ptr [rax], xmm0
0x18001c212  mov     dword ptr [rdi+40h], 1
0x18001c219  lea     rcx, [rdi+8]; lpCriticalSection
0x18001c21d  call    cs:__imp_LeaveCriticalSection
0x18001c223  mov     eax, ebx
0x18001c225  add     rsp, 20h
0x18001c229  pop     r14
0x18001c22b  pop     rdi
0x18001c22c  pop     rsi
0x18001c22d  pop     rbp
0x18001c22e  pop     rbx
0x18001c22f  retn
```
