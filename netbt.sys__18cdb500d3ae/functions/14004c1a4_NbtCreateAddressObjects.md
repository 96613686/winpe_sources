# NbtCreateAddressObjects

- ea: `0x14004c1a4`
- end: `0x14004c4a0`
- name: `NbtCreateAddressObjects`
- size: `764`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140012694`
- `0x140045254`

## callees

- `0x1400248f8`
- `0x140028068`
- `0x140031440`
- `0x1400456f4`
- `0x14004c1a4`
- `0x14004c4a8`
- `0x14004cc48`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004c3cf`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c3f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c3cf`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c417`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c417`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1d3`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1d3`

## pseudocode

```c
__int64 __fastcall NbtCreateAddressObjects(int a1, int a2, __int64 a3)
{
  int v5; // esi
  __int64 Pool2; // rax
  __int64 v7; // rdi
  int v8; // eax
  unsigned int v9; // esi
  unsigned int CurrentThreadCompartmentId; // ebp
  int v11; // esi
  signed __int8 v12; // r8
  unsigned __int8 v13; // r9
  CCHAR v14; // r9
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  int v20; // [rsp+30h] [rbp-38h]
  int v21; // [rsp+30h] [rbp-38h]
  int v22; // [rsp+30h] [rbp-38h]
  char v23; // [rsp+73h] [rbp+Bh]

  v23 = HIBYTE(a1);
  v5 = a1;
  Pool2 = ExAllocatePool2(64, 128, 959668814);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset((void *)(Pool2 + 4), 0, 0x7Cu);
  *(_DWORD *)v7 = 1;
  if ( *(_DWORD *)(a3 + 860) )
  {
    v8 = -1;
    if ( a2 == -1 )
      goto LABEL_4;
  }
  if ( byte_140039642 )
  {
    v8 = dword_14003961C;
LABEL_4:
    *(_DWORD *)(a3 + 496) = v8;
    goto LABEL_5;
  }
  *(_DWORD *)(a3 + 496) = ~a2 | a2 & v5;
LABEL_5:
  *(_DWORD *)(a3 + 488) = v5;
  *(_DWORD *)(a3 + 492) = a2;
  if ( v23 < 0 )
  {
    if ( (v23 & 0xC0) == 0x80 )
    {
      v5 &= 0xFFFF0000;
    }
    else if ( (v23 & 0xE0) == 0xC0 )
    {
      v5 &= 0xFFFFFF00;
    }
  }
  else
  {
    v5 &= 0xFF000000;
  }
  *(_DWORD *)(a3 + 500) = v5;
  v9 = *(_DWORD *)(a3 + 568);
  CurrentThreadCompartmentId = NdisGetCurrentThreadCompartmentId();
  if ( v9 == CurrentThreadCompartmentId )
  {
    CurrentThreadCompartmentId = 0;
  }
  else
  {
    v11 = NdisSetCurrentThreadCompartmentId(v9);
    if ( v11 < 0 )
    {
LABEL_26:
      v16 = *(void **)(v7 + 24);
      if ( v16 )
      {
        ObfDereferenceObject(v16);
        v17 = *(void **)(v7 + 8);
        *(_QWORD *)(v7 + 24) = 0;
        NTZwCloseFile(v17);
      }
      v18 = *(void **)(v7 + 48);
      if ( v18 )
      {
        ObfDereferenceObject(v18);
        v19 = *(void **)(v7 + 32);
        *(_QWORD *)(v7 + 48) = 0;
        NTZwCloseFile(v19);
      }
      ExFreePoolWithTag((PVOID)v7, 0);
      *(_QWORD *)(a3 + 488) = 0;
      *(_DWORD *)(a3 + 500) = 0;
      goto LABEL_20;
    }
  }
  v11 = NbtTdiOpenAddress(
          (void **)(v7 + 32),
          (PDEVICE_OBJECT *)(v7 + 40),
          (struct _FILE_OBJECT **)(v7 + 48),
          a3,
          138,
          *(_DWORD *)(a3 + 488),
          v20,
          0);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = NbtTdiOpenAddress(
          (void **)(v7 + 8),
          (PDEVICE_OBJECT *)(v7 + 16),
          (struct _FILE_OBJECT **)(v7 + 24),
          a3,
          137,
          *(_DWORD *)(a3 + 488),
          v21,
          0);
  if ( v11 < 0 )
    goto LABEL_26;
  v11 = NbtTdiOpenAddress(
          (void **)(a3 + 624),
          (PDEVICE_OBJECT *)(a3 + 632),
          (struct _FILE_OBJECT **)(a3 + 640),
          a3,
          139,
          *(_DWORD *)(a3 + 488),
          v22,
          3);
  if ( v11 < 0 )
    goto LABEL_26;
  GetExtendedAttributes(a3);
  *(_QWORD *)(a3 + 616) = v7;
  v12 = *(_BYTE *)(*(_QWORD *)(v7 + 16) + 76LL);
  if ( *(char *)(*(_QWORD *)(v7 + 40) + 76LL) > v12 )
    v12 = *(_BYTE *)(*(_QWORD *)(v7 + 40) + 76LL);
  v13 = v12;
  if ( (unsigned __int8)v12 <= *(char *)(*(_QWORD *)(a3 + 632) + 76LL) )
    v13 = *(_BYTE *)(*(_QWORD *)(a3 + 632) + 76LL);
  if ( *(char *)(a3 + 76) <= (int)v13 )
  {
    v14 = v13 + 1;
    *(_BYTE *)(a3 + 76) = v14;
  }
  else
  {
    v14 = *(_BYTE *)(a3 + 76);
  }
  if ( (unsigned __int8)StackSize < v14 )
    StackSize = v14;
LABEL_20:
  if ( CurrentThreadCompartmentId )
    NdisSetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14004c1a4  mov     [rsp+arg_8], rbx
0x14004c1a9  mov     [rsp+arg_10], rbp
0x14004c1ae  mov     [rsp+arg_0], ecx
0x14004c1b2  push    rsi
0x14004c1b3  push    rdi
0x14004c1b4  push    r12
0x14004c1b6  push    r14
0x14004c1b8  push    r15
0x14004c1ba  sub     rsp, 40h
0x14004c1be  mov     ebp, edx
0x14004c1c0  mov     rbx, r8
0x14004c1c3  mov     edx, 80h
0x14004c1c8  mov     esi, ecx
0x14004c1ca  mov     r8d, 3933624Eh
0x14004c1d0  lea     ecx, [rdx-40h]
0x14004c1d3  call    cs:__imp_ExAllocatePool2
0x14004c1da  nop     dword ptr [rax+rax+00h]
0x14004c1df  mov     rdi, rax
0x14004c1e2  test    rax, rax
0x14004c1e5  jz      loc_14004C467
0x14004c1eb  xor     edx, edx; Val
0x14004c1ed  lea     rcx, [rax+4]; void *
0x14004c1f1  lea     r8d, [rdx+7Ch]; Size
0x14004c1f5  call    memset
0x14004c1fa  mov     dword ptr [rdi], 1
0x14004c200  cmp     dword ptr [rbx+35Ch], 0
0x14004c207  jz      loc_14004C393
0x14004c20d  or      eax, 0FFFFFFFFh
0x14004c210  cmp     ebp, eax
0x14004c212  jnz     loc_14004C393
0x14004c218  mov     [rbx+1F0h], eax
0x14004c21e  mov     cl, byte ptr [rsp+68h+arg_0+3]
0x14004c222  mov     [rbx+1E8h], esi
0x14004c228  mov     [rbx+1ECh], ebp
0x14004c22e  test    cl, cl
0x14004c230  js      loc_14004C448
0x14004c236  and     esi, 0FF000000h
0x14004c23c  mov     [rbx+1F4h], esi
0x14004c242  mov     esi, [rbx+238h]
0x14004c248  call    NdisGetCurrentThreadCompartmentId
0x14004c24d  mov     ebp, eax
0x14004c24f  cmp     esi, eax
0x14004c251  jnz     loc_14004C3B5
0x14004c257  xor     ebp, ebp
0x14004c259  mov     eax, [rbx+1E8h]
0x14004c25f  lea     r8, [rdi+30h]
0x14004c263  mov     [rsp+68h+var_30], 0
0x14004c26b  lea     rcx, [rdi+20h]
0x14004c26f  mov     [rsp+68h+var_40], eax
0x14004c273  lea     rdx, [rdi+28h]
0x14004c277  mov     r9, rbx
0x14004c27a  mov     [rsp+68h+var_48], 8Ah
0x14004c281  call    NbtTdiOpenAddress
0x14004c286  mov     esi, eax
0x14004c288  test    eax, eax
0x14004c28a  js      loc_14004C3C6
0x14004c290  mov     eax, [rbx+1E8h]
0x14004c296  lea     r8, [rdi+18h]
0x14004c29a  mov     [rsp+68h+var_30], 0
0x14004c2a2  lea     rcx, [rdi+8]
0x14004c2a6  mov     [rsp+68h+var_40], eax
0x14004c2aa  lea     rdx, [rdi+10h]
0x14004c2ae  mov     r9, rbx
0x14004c2b1  mov     [rsp+68h+var_48], 89h
0x14004c2b8  call    NbtTdiOpenAddress
0x14004c2bd  mov     esi, eax
0x14004c2bf  test    eax, eax
0x14004c2c1  js      loc_14004C3C6
0x14004c2c7  mov     eax, [rbx+1E8h]
0x14004c2cd  lea     r14, [rbx+278h]
0x14004c2d4  mov     [rsp+68h+var_30], 3
0x14004c2dc  lea     r8, [rbx+280h]
0x14004c2e3  mov     [rsp+68h+var_40], eax
0x14004c2e7  lea     rcx, [rbx+270h]
0x14004c2ee  mov     rdx, r14
0x14004c2f1  mov     [rsp+68h+var_48], 8Bh
0x14004c2f8  mov     r9, rbx
0x14004c2fb  call    NbtTdiOpenAddress
0x14004c300  mov     esi, eax
0x14004c302  test    eax, eax
0x14004c304  js      loc_14004C3C6
0x14004c30a  mov     rcx, rbx
0x14004c30d  call    GetExtendedAttributes
0x14004c312  mov     [rbx+268h], rdi
0x14004c319  mov     rax, [rdi+10h]
0x14004c31d  movzx   r8d, byte ptr [rax+4Ch]
0x14004c322  mov     rax, [rdi+28h]
0x14004c326  movzx   ecx, byte ptr [rax+4Ch]
0x14004c32a  mov     rax, [r14]
0x14004c32d  cmp     cl, r8b
0x14004c330  cmovg   r8d, ecx
0x14004c334  movzx   r9d, r8b
0x14004c338  movzx   edx, byte ptr [rax+4Ch]
0x14004c33c  movsx   ecx, dl
0x14004c33f  movzx   eax, r8b
0x14004c343  cmp     eax, ecx
0x14004c345  cmovle  r9d, edx
0x14004c349  movsx   edx, byte ptr [rbx+4Ch]
0x14004c34d  movzx   eax, r9b
0x14004c351  cmp     edx, eax
0x14004c353  jle     loc_14004C47C
0x14004c359  mov     r9b, dl
0x14004c35c  movzx   eax, cs:StackSize
0x14004c363  movsx   ecx, r9b
0x14004c367  cmp     eax, ecx
0x14004c369  jl      loc_14004C488
0x14004c36f  test    ebp, ebp
0x14004c371  jnz     loc_14004C494
0x14004c377  mov     eax, esi
0x14004c379  lea     r11, [rsp+68h+var_28]
0x14004c37e  mov     rbx, [r11+38h]
0x14004c382  mov     rbp, [r11+40h]
0x14004c386  mov     rsp, r11
0x14004c389  pop     r15
0x14004c38b  pop     r14
0x14004c38d  pop     r12
0x14004c38f  pop     rdi
0x14004c390  pop     rsi
0x14004c391  retn
0x14004c393  cmp     cs:byte_140039642, 0
0x14004c39a  jnz     loc_14004C43D
0x14004c3a0  mov     ecx, esi
0x14004c3a2  mov     eax, ebp
0x14004c3a4  and     ecx, ebp
0x14004c3a6  not     eax
0x14004c3a8  or      ecx, eax
0x14004c3aa  mov     [rbx+1F0h], ecx
0x14004c3b0  jmp     loc_14004C21E
0x14004c3b5  mov     ecx, esi
0x14004c3b7  call    NdisSetCurrentThreadCompartmentId
0x14004c3bc  mov     esi, eax
0x14004c3be  test    eax, eax
0x14004c3c0  jns     loc_14004C259
0x14004c3c6  mov     rcx, [rdi+18h]; Object
0x14004c3ca  test    rcx, rcx
0x14004c3cd  jz      short loc_14004C3EC
0x14004c3cf  call    cs:__imp_ObfDereferenceObject
0x14004c3d6  nop     dword ptr [rax+rax+00h]
0x14004c3db  mov     rcx, [rdi+8]; Handle
0x14004c3df  mov     qword ptr [rdi+18h], 0
0x14004c3e7  call    NTZwCloseFile
0x14004c3ec  mov     rcx, [rdi+30h]; Object
0x14004c3f0  test    rcx, rcx
0x14004c3f3  jz      short loc_14004C412
0x14004c3f5  call    cs:__imp_ObfDereferenceObject
0x14004c3fc  nop     dword ptr [rax+rax+00h]
0x14004c401  mov     rcx, [rdi+20h]; Handle
0x14004c405  mov     qword ptr [rdi+30h], 0
0x14004c40d  call    NTZwCloseFile
0x14004c412  xor     edx, edx; Tag
0x14004c414  mov     rcx, rdi; P
0x14004c417  call    cs:__imp_ExFreePoolWithTag
0x14004c41e  nop     dword ptr [rax+rax+00h]
0x14004c423  mov     qword ptr [rbx+1E8h], 0
0x14004c42e  mov     dword ptr [rbx+1F4h], 0
0x14004c438  jmp     loc_14004C36F
0x14004c43d  mov     eax, cs:dword_14003961C
0x14004c443  jmp     loc_14004C218
0x14004c448  mov     al, cl
0x14004c44a  and     al, 0C0h
0x14004c44c  cmp     al, 80h
0x14004c44e  jz      short loc_14004C471
0x14004c450  and     cl, 0E0h
0x14004c453  cmp     cl, 0C0h
0x14004c456  jnz     loc_14004C23C
0x14004c45c  and     esi, 0FFFFFF00h
0x14004c462  jmp     loc_14004C23C
0x14004c467  mov     eax, 0C000009Ah
0x14004c46c  jmp     loc_14004C379
0x14004c471  and     esi, 0FFFF0000h
0x14004c477  jmp     loc_14004C23C
0x14004c47c  inc     r9b
0x14004c47f  mov     [rbx+4Ch], r9b
0x14004c483  jmp     loc_14004C35C
0x14004c488  mov     cs:StackSize, r9b
0x14004c48f  jmp     loc_14004C36F
0x14004c494  mov     ecx, ebp
0x14004c496  call    NdisSetCurrentThreadCompartmentId
0x14004c49b  jmp     loc_14004C377
```
