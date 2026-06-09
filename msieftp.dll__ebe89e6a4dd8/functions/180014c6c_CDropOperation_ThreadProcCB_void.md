# CDropOperation::_ThreadProcCB(void)

- ea: `0x180014c6c`
- end: `0x180014d8e`
- name: `?_ThreadProcCB@CDropOperation@@IEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CDropOperation *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012bcc`
- `0x180012f28`
- `0x180014c60`

## callees

- `0x180013f20`
- `0x18001465c`
- `0x180014c6c`
- `0x180023ce4`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014d6e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014d6e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014c7f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014c9e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014c7f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014c9e`

## pseudocode

```c
__int64 __fastcall CDropOperation::_ThreadProcCB(CDropOperation *this)
{
  HRESULT v2; // eax
  HRESULT v3; // ebx
  struct IProgressDialog *Instance; // rax
  __int64 v5; // rdx
  int v6; // esi
  __int64 v7; // r8
  unsigned int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  v2 = CoInitializeEx(0, 6u);
  v3 = v2;
  if ( v2 == 1 )
    goto LABEL_4;
  if ( v2 != -2147417850 )
    goto LABEL_7;
  v3 = CoInitializeEx(0, 4u);
  if ( v3 == 1 )
  {
LABEL_4:
    v3 = 0;
  }
  else if ( v3 == -2147417850 )
  {
    v3 = 1;
  }
LABEL_7:
  Instance = CProgressDialog_CreateInstance(0x4Au);
  *((_QWORD *)this + 9) = Instance;
  if ( Instance )
    ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD, __int64, _QWORD))Instance->lpVtbl->SetAnimation)(
      Instance,
      *((_QWORD *)this + 4),
      0,
      2,
      0);
  v6 = CDropOperation::_CalcUploadProgress(this);
  if ( v6 >= 0 )
  {
    v9 = *((_QWORD *)this + 9);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 72LL))(
        v9,
        *((_QWORD *)this + 7),
        *((_QWORD *)this + 8));
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 9) + 96LL))(*((_QWORD *)this + 9), 1, 0);
    }
    v6 = CDropOperation::_DoCopyIteration(this, v5, v7, v8);
  }
  v10 = *((_QWORD *)this + 9);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
    v11 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( !v3 )
    CoUninitialize();
  (*(void (__fastcall **)(CDropOperation *))(*(_QWORD *)this + 16LL))(this);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014c6c  push    rbx
0x180014c6e  push    rbp
0x180014c6f  push    rsi
0x180014c70  push    rdi
0x180014c71  sub     rsp, 38h
0x180014c75  mov     rdi, rcx
0x180014c78  mov     edx, 6; dwCoInit
0x180014c7d  xor     ecx, ecx; pvReserved
0x180014c7f  call    cs:__imp_CoInitializeEx
0x180014c85  mov     ebp, 1
0x180014c8a  mov     ebx, eax
0x180014c8c  cmp     eax, ebp
0x180014c8e  jz      short loc_180014CAA
0x180014c90  mov     esi, 80010106h
0x180014c95  cmp     eax, esi
0x180014c97  jnz     short loc_180014CB3
0x180014c99  lea     edx, [rbp+3]; dwCoInit
0x180014c9c  xor     ecx, ecx; pvReserved
0x180014c9e  call    cs:__imp_CoInitializeEx
0x180014ca4  mov     ebx, eax
0x180014ca6  cmp     eax, ebp
0x180014ca8  jnz     short loc_180014CAE
0x180014caa  xor     ebx, ebx
0x180014cac  jmp     short loc_180014CB3
0x180014cae  cmp     ebx, esi
0x180014cb0  cmovz   ebx, ebp
0x180014cb3  mov     ecx, 4Ah ; 'J'; uID
0x180014cb8  call    ?CProgressDialog_CreateInstance@@YAPEAUIProgressDialog@@II@Z; CProgressDialog_CreateInstance(uint,uint)
0x180014cbd  mov     [rdi+48h], rax
0x180014cc1  mov     r10, rax
0x180014cc4  test    rax, rax
0x180014cc7  jz      short loc_180014CEE
0x180014cc9  mov     rcx, [rax]
0x180014ccc  mov     r9d, 2
0x180014cd2  mov     rdx, [rdi+20h]
0x180014cd6  xor     r8d, r8d
0x180014cd9  mov     [rsp+58h+var_38], 0
0x180014ce2  mov     rax, [rcx+18h]
0x180014ce6  mov     rcx, r10
0x180014ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cee  mov     rcx, rdi; this
0x180014cf1  call    ?_CalcUploadProgress@CDropOperation@@IEAAJXZ; CDropOperation::_CalcUploadProgress(void)
0x180014cf6  mov     esi, eax
0x180014cf8  test    eax, eax
0x180014cfa  js      short loc_180014D38
0x180014cfc  mov     rcx, [rdi+48h]
0x180014d00  test    rcx, rcx
0x180014d03  jz      short loc_180014D2E
0x180014d05  mov     rax, [rcx]
0x180014d08  mov     r8, [rdi+40h]
0x180014d0c  mov     rdx, [rdi+38h]
0x180014d10  mov     rax, [rax+48h]
0x180014d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d19  mov     rcx, [rdi+48h]
0x180014d1d  xor     r8d, r8d
0x180014d20  mov     edx, ebp
0x180014d22  mov     rax, [rcx]
0x180014d25  mov     rax, [rax+60h]
0x180014d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d2e  mov     rcx, rdi; this
0x180014d31  call    ?_DoCopyIteration@CDropOperation@@IEAAJXZ; CDropOperation::_DoCopyIteration(void)
0x180014d36  mov     esi, eax
0x180014d38  mov     rcx, [rdi+48h]
0x180014d3c  test    rcx, rcx
0x180014d3f  jz      short loc_180014D6A
0x180014d41  mov     rax, [rcx]
0x180014d44  mov     rax, [rax+20h]
0x180014d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d4d  mov     rcx, [rdi+48h]
0x180014d51  mov     qword ptr [rdi+48h], 0
0x180014d59  test    rcx, rcx
0x180014d5c  jz      short loc_180014D6A
0x180014d5e  mov     rax, [rcx]
0x180014d61  mov     rax, [rax+10h]
0x180014d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d6a  test    ebx, ebx
0x180014d6c  jnz     short loc_180014D74
0x180014d6e  call    cs:__imp_CoUninitialize
0x180014d74  mov     rax, [rdi]
0x180014d77  mov     rcx, rdi
0x180014d7a  mov     rax, [rax+10h]
0x180014d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d83  mov     eax, esi
0x180014d85  add     rsp, 38h
0x180014d89  pop     rdi
0x180014d8a  pop     rsi
0x180014d8b  pop     rbp
0x180014d8c  pop     rbx
0x180014d8d  retn
```
