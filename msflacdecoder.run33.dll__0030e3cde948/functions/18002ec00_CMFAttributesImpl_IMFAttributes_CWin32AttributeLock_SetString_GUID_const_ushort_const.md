# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x18002ec00`
- end: `0x18002eccd`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016b0c`
- `0x18002b05c`
- `0x18002ec00`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ecb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ecb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ec6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ec6f`

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
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
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
0x18002ec00  push    rbx
0x18002ec02  push    rbp
0x18002ec03  push    rsi
0x18002ec04  push    rdi
0x18002ec05  push    r12
0x18002ec07  push    r14
0x18002ec09  push    r15
0x18002ec0b  sub     rsp, 20h
0x18002ec0f  mov     rdi, rcx
0x18002ec12  mov     r14, r8
0x18002ec15  add     rcx, 8; lpCriticalSection
0x18002ec19  mov     rbx, rdx
0x18002ec1c  call    cs:__imp_EnterCriticalSection
0x18002ec22  mov     rdx, rbx
0x18002ec25  mov     rcx, rdi
0x18002ec28  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18002ec2d  xor     r12d, r12d
0x18002ec30  mov     rsi, rax
0x18002ec33  test    r14, r14
0x18002ec36  jnz     short loc_18002EC3F
0x18002ec38  mov     ebx, 80070057h
0x18002ec3d  jmp     short loc_18002ECB2
0x18002ec3f  test    rsi, rsi
0x18002ec42  jnz     short loc_18002EC4B
0x18002ec44  mov     ebx, 8007000Eh
0x18002ec49  jmp     short loc_18002ECB2
0x18002ec4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ec4f  inc     rax
0x18002ec52  cmp     [r14+rax*2], r12w
0x18002ec57  jnz     short loc_18002EC4F
0x18002ec59  lea     rax, ds:2[rax*2]
0x18002ec61  mov     ecx, 0FFFFFFFFh
0x18002ec66  cmp     rax, rcx
0x18002ec69  jnb     short loc_18002EC38
0x18002ec6b  mov     ecx, eax; cb
0x18002ec6d  mov     ebp, eax
0x18002ec6f  call    cs:__imp_CoTaskMemAlloc
0x18002ec75  mov     [rsi+8], rax
0x18002ec79  test    rax, rax
0x18002ec7c  jnz     short loc_18002EC95
0x18002ec7e  mov     rax, [rdi]
0x18002ec81  mov     rdx, rbx
0x18002ec84  mov     rcx, rdi
0x18002ec87  mov     rax, [rax+98h]
0x18002ec8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec93  jmp     short loc_18002EC44
0x18002ec95  mov     r8, rbp; Size
0x18002ec98  mov     rdx, r14; Src
0x18002ec9b  mov     rcx, rax; void *
0x18002ec9e  mov     ebx, r12d
0x18002eca1  call    memcpy_0
0x18002eca6  mov     word ptr [rsi], 1Fh
0x18002ecab  mov     dword ptr [rdi+40h], 1
0x18002ecb2  lea     rcx, [rdi+8]; lpCriticalSection
0x18002ecb6  call    cs:__imp_LeaveCriticalSection
0x18002ecbc  mov     eax, ebx
0x18002ecbe  add     rsp, 20h
0x18002ecc2  pop     r15
0x18002ecc4  pop     r14
0x18002ecc6  pop     r12
0x18002ecc8  pop     rdi
0x18002ecc9  pop     rsi
0x18002ecca  pop     rbp
0x18002eccb  pop     rbx
0x18002eccc  retn
```
