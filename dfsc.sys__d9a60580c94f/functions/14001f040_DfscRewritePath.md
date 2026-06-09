# DfscRewritePath

- ea: `0x14001f040`
- end: `0x14001f52c`
- name: `DfscRewritePath`
- size: `1260`
- prototype: `__int64 __fastcall(__int64, __int16 *, const UNICODE_STRING *, char)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011c80`
- `0x14001e3d0`
- `0x140020660`
- `0x1400284a0`

## callees

- `0x1400026a4`
- `0x140002aa0`
- `0x140002fcc`
- `0x140006080`
- `0x14001f040`
- `0x14001f540`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001f4a8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001f4a8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f122`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f45b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f122`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f45b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f15e`
- `ntoskrnl!ExAllocatePool2` at `0x14001f0c5`
- `ntoskrnl!ExAllocatePool2` at `0x14001f0c5`

## pseudocode

```c
__int64 __fastcall DfscRewritePath(__int64 a1, __int16 *a2, const UNICODE_STRING *a3, char a4)
{
  unsigned int v7; // ebx
  int Length; // r8d
  bool v9; // al
  unsigned int v10; // edi
  WCHAR *Pool2; // rsi
  const void *v12; // rdx
  unsigned int appended; // r13d
  void *v14; // rcx
  _WORD *v15; // rax
  char v16; // r10
  PWSTR Buffer; // r9
  __int64 v18; // rcx
  unsigned int v19; // r8d
  _WORD *v20; // rax
  char v21; // r10
  PWSTR v22; // r9
  __int64 v23; // rax
  unsigned int v24; // r8d
  __int64 v26; // rax
  __int64 v27; // rcx
  unsigned int PathComponents; // eax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v31; // [rsp+A0h] [rbp+50h]
  bool v32; // [rsp+A8h] [rbp+58h]

  Destination = 0;
  Source = 0;
  if ( a4 && (v26 = *(_QWORD *)(a1 + 272)) != 0 && (v27 = *(_QWORD *)(v26 + 16), *(_DWORD *)(v27 + 8) == 1) )
  {
    DfscGetPathComponents((__int16 *)(v27 + 144), 0, &Source, 0, 0);
    PathComponents = DfscGetPathComponents(a2, &Destination, 0, 0, 0);
    v7 = Destination.Length + 4;
    v31 = PathComponents;
  }
  else
  {
    v7 = (unsigned __int16)*a2;
    v31 = 0;
  }
  Length = a3->Length;
  if ( (_WORD)Length )
  {
    if ( *a3->Buffer == 92 )
    {
      v9 = 0;
    }
    else if ( Source.Length )
    {
      v9 = 1;
    }
    else
    {
      v9 = *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * ((unsigned __int64)v7 >> 1) - 2) != 92;
    }
  }
  else
  {
    v9 = 0;
  }
  v32 = v9;
  v10 = Source.Length + v7 + Length + 2 * (v9 + 1);
  if ( v10 > 0xFFFF )
    return 3221225734LL;
  Pool2 = (WCHAR *)ExAllocatePool2(258, v10, 1799579204);
  if ( !Pool2 )
    return 3221225626LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a8b72ae5a54533de05be1b18d60e4877_Traceguids, a1, Pool2);
  v12 = (const void *)*((_QWORD *)a2 + 1);
  Destination.Buffer = Pool2;
  Destination.Length = v7;
  Destination.MaximumLength = v10;
  memmove(Pool2, v12, v7);
  if ( Source.Length )
    appended = RtlAppendUnicodeStringToString(&Destination, &Source);
  else
    appended = v31;
  if ( a3->Length )
  {
    if ( v32 )
      RtlAppendUnicodeToString(&Destination, L"\\");
    appended = RtlAppendUnicodeStringToString(&Destination, a3);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_a8b72ae5a54533de05be1b18d60e4877_Traceguids,
      a1,
      (__int64)&Destination);
  v14 = *(void **)(a1 + 104);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 80) = 0;
  *(_OWORD *)(a1 + 112) = 0;
  *(_OWORD *)(a1 + 128) = 0;
  *(_OWORD *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 160) = 0;
  *(_OWORD *)(a1 + 176) = 0;
  *(_OWORD *)(a1 + 192) = 0;
  *(_OWORD *)(a1 + 208) = 0;
  *(_WORD *)(a1 + 226) = 0;
  *(struct _UNICODE_STRING *)(a1 + 96) = Destination;
  if ( (int)DfscGetPathComponents(
              (__int16 *)(a1 + 96),
              (struct _UNICODE_STRING *)(a1 + 16),
              (struct _UNICODE_STRING *)(a1 + 32),
              (struct _UNICODE_STRING *)(a1 + 64),
              (PUNICODE_STRING)(a1 + 48)) >= 0
    && a1 != -16
    && *(_WORD *)(a1 + 16)
    && (v15 = *(_WORD **)(a1 + 24)) != 0
    && *v15 )
  {
    if ( !*(_WORD *)(a1 + 48) )
      goto LABEL_26;
    v16 = 0;
    Buffer = Destination.Buffer;
    v18 = (Destination.Length >> 1) - 1;
    v19 = *(unsigned __int16 *)(a1 + 64) >> 1;
    *(_QWORD *)(a1 + 88) = Destination.Buffer;
    if ( (unsigned int)v18 < v19 )
      goto LABEL_26;
    do
    {
      if ( Buffer[v18] == 58 )
      {
        v16 = 1;
        *(_WORD *)(a1 + 82) = 2 * v18;
        *(_WORD *)(a1 + 80) = 2 * v18;
      }
      if ( Buffer[v18] == 92 )
        break;
      v18 = (unsigned int)(v18 - 1);
    }
    while ( (unsigned int)v18 >= v19 );
    if ( !v16 )
LABEL_26:
      *(struct _UNICODE_STRING *)(a1 + 80) = Destination;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids, &Destination);
  }
  *(struct _UNICODE_STRING *)(a1 + 192) = Destination;
  if ( (int)DfscGetPathComponents(
              (__int16 *)(a1 + 192),
              (struct _UNICODE_STRING *)(a1 + 112),
              (struct _UNICODE_STRING *)(a1 + 128),
              (struct _UNICODE_STRING *)(a1 + 160),
              (PUNICODE_STRING)(a1 + 144)) >= 0
    && a1 != -112
    && *(_WORD *)(a1 + 112)
    && (v20 = *(_WORD **)(a1 + 120)) != 0
    && *v20 )
  {
    if ( !*(_WORD *)(a1 + 144) )
      goto LABEL_39;
    v21 = 0;
    v22 = Destination.Buffer;
    v23 = (Destination.Length >> 1) - 1;
    v24 = *(unsigned __int16 *)(a1 + 160) >> 1;
    *(_QWORD *)(a1 + 184) = Destination.Buffer;
    if ( (unsigned int)v23 < v24 )
      goto LABEL_39;
    do
    {
      if ( v22[v23] == 58 )
      {
        v21 = 1;
        *(_WORD *)(a1 + 178) = 2 * v23;
        *(_WORD *)(a1 + 176) = 2 * v23;
      }
      if ( v22[v23] == 92 )
        break;
      v23 = (unsigned int)(v23 - 1);
    }
    while ( (unsigned int)v23 >= v24 );
    if ( !v21 )
LABEL_39:
      *(struct _UNICODE_STRING *)(a1 + 176) = Destination;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids, &Destination);
  }
  return appended;
}

```

## disassembly

```asm
0x14001f040  push    rbp
0x14001f042  push    rbx
0x14001f043  push    rdi
0x14001f044  push    r12
0x14001f046  push    r13
0x14001f048  push    r14
0x14001f04a  push    r15
0x14001f04c  mov     rbp, rsp
0x14001f04f  sub     rsp, 50h
0x14001f053  xorps   xmm0, xmm0
0x14001f056  xorps   xmm1, xmm1
0x14001f059  mov     r15, r8
0x14001f05c  mov     r13, rdx
0x14001f05f  mov     r14, rcx
0x14001f062  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x14001f066  movups  xmmword ptr [rbp+Source.Length], xmm1
0x14001f06a  test    r9b, r9b
0x14001f06d  jnz     loc_14001F3D3
0x14001f073  movzx   ebx, word ptr [rdx]
0x14001f076  xor     r12d, r12d
0x14001f079  mov     [rbp+arg_10], r12d
0x14001f07d  movzx   r8d, word ptr [r15]
0x14001f081  movzx   r9d, [rbp+Source.Length]
0x14001f086  test    r8w, r8w
0x14001f08a  jnz     loc_14001F43D
0x14001f090  xor     al, al
0x14001f092  movzx   edi, al
0x14001f095  inc     edi
0x14001f097  mov     [rbp+arg_18], al
0x14001f09a  lea     eax, [rbx+r8]
0x14001f09e  lea     edi, [rax+rdi*2]
0x14001f0a1  add     edi, r9d
0x14001f0a4  cmp     edi, 0FFFFh
0x14001f0aa  ja      loc_14001F3BD
0x14001f0b0  mov     edx, edi
0x14001f0b2  mov     ecx, 102h
0x14001f0b7  mov     r8d, 6B436644h
0x14001f0bd  mov     [rsp+50h+arg_0], rsi
0x14001f0c5  call    cs:__imp_ExAllocatePool2
0x14001f0cc  nop     dword ptr [rax+rax+00h]
0x14001f0d1  mov     rsi, rax
0x14001f0d4  test    rax, rax
0x14001f0d7  jz      loc_14001F46F
0x14001f0dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0e4  lea     rax, WPP_GLOBAL_Control
0x14001f0eb  cmp     rcx, rax
0x14001f0ee  jnz     loc_14001F38E
0x14001f0f4  mov     rdx, [r13+8]; Src
0x14001f0f8  mov     rcx, rsi; void *
0x14001f0fb  mov     r8d, ebx; Size
0x14001f0fe  mov     [rbp+Destination.Buffer], rsi
0x14001f102  mov     [rbp+Destination.Length], bx
0x14001f106  mov     [rbp+Destination.MaximumLength], di
0x14001f10a  call    memmove
0x14001f10f  cmp     [rbp+Source.Length], 0
0x14001f114  jz      loc_14001F434
0x14001f11a  lea     rdx, [rbp+Source]; Source
0x14001f11e  lea     rcx, [rbp+Destination]; Destination
0x14001f122  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001f129  nop     dword ptr [rax+rax+00h]
0x14001f12e  mov     r13d, eax
0x14001f131  cmp     word ptr [r15], 0
0x14001f136  jnz     loc_14001F44E
0x14001f13c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f143  lea     r15, WPP_GLOBAL_Control
0x14001f14a  cmp     rcx, r15
0x14001f14d  jnz     loc_14001F35B
0x14001f153  mov     rcx, [r14+68h]; P
0x14001f157  test    rcx, rcx
0x14001f15a  jz      short loc_14001F16A
0x14001f15c  xor     edx, edx; Tag
0x14001f15e  call    cs:__imp_ExFreePoolWithTag
0x14001f165  nop     dword ptr [rax+rax+00h]
0x14001f16a  xorps   xmm0, xmm0
0x14001f16d  lea     rbx, [r14+70h]
0x14001f171  movups  xmmword ptr [r14+10h], xmm0
0x14001f176  lea     rdi, [r14+10h]
0x14001f17a  movups  xmmword ptr [r14+20h], xmm0
0x14001f17f  lea     rcx, [rdi+50h]
0x14001f183  mov     rdx, rdi
0x14001f186  movups  xmmword ptr [r14+30h], xmm0
0x14001f18b  lea     rsi, [rdi+20h]
0x14001f18f  movups  xmmword ptr [r14+40h], xmm0
0x14001f194  lea     r8, [rdi+10h]
0x14001f198  mov     [rsp+50h+var_30], rsi
0x14001f19d  movups  xmmword ptr [r14+50h], xmm0
0x14001f1a2  lea     r9, [rdi+30h]
0x14001f1a6  movups  xmmword ptr [rbx], xmm0
0x14001f1a9  movups  xmmword ptr [rbx+10h], xmm0
0x14001f1ad  movups  xmmword ptr [rbx+20h], xmm0
0x14001f1b1  movups  xmmword ptr [rbx+30h], xmm0
0x14001f1b5  movups  xmmword ptr [rbx+40h], xmm0
0x14001f1b9  movups  xmmword ptr [rbx+50h], xmm0
0x14001f1bd  movups  xmmword ptr [r14+0D0h], xmm0
0x14001f1c5  mov     [r14+0E2h], r12w
0x14001f1cd  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x14001f1d1  movups  xmmword ptr [rcx], xmm0
0x14001f1d4  call    DfscGetPathComponents
0x14001f1d9  test    eax, eax
0x14001f1db  js      loc_14001F4B6
0x14001f1e1  test    rdi, rdi
0x14001f1e4  jz      loc_14001F4B6
0x14001f1ea  cmp     word ptr [rdi], 0
0x14001f1ee  jz      loc_14001F4B6
0x14001f1f4  mov     rax, [rdi+8]
0x14001f1f8  test    rax, rax
0x14001f1fb  jz      loc_14001F4B6
0x14001f201  cmp     word ptr [rax], 0
0x14001f205  jz      loc_14001F4B6
0x14001f20b  cmp     word ptr [rsi], 0
0x14001f20f  jz      short loc_14001F262
0x14001f211  movzx   ecx, [rbp+Destination.Length]
0x14001f215  xor     r10b, r10b
0x14001f218  movzx   r8d, word ptr [rdi+30h]
0x14001f21d  mov     r9, [rbp+Destination.Buffer]
0x14001f221  shr     ecx, 1
0x14001f223  dec     ecx
0x14001f225  shr     r8d, 1
0x14001f228  mov     [rdi+48h], r9
0x14001f22c  cmp     ecx, r8d
0x14001f22f  jb      short loc_14001F262
0x14001f231  nop     dword ptr [rax+00h]
0x14001f235  nop     word ptr [rax+rax+00000000h]
0x14001f240  cmp     word ptr [r9+rcx*2], 3Ah ; ':'
0x14001f246  lea     rdx, [r9+rcx*2]
0x14001f24a  jz      loc_14001F332
0x14001f250  cmp     word ptr [rdx], 5Ch ; '\'
0x14001f254  jz      short loc_14001F25D
0x14001f256  dec     ecx
0x14001f258  cmp     ecx, r8d
0x14001f25b  jnb     short loc_14001F240
0x14001f25d  test    r10b, r10b
0x14001f260  jnz     short loc_14001F26A
0x14001f262  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x14001f266  movups  xmmword ptr [rdi+40h], xmm0
0x14001f26a  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x14001f26e  lea     rcx, [rbx+50h]
0x14001f272  mov     rdx, rbx
0x14001f275  lea     rdi, [rbx+20h]
0x14001f279  lea     r8, [rbx+10h]
0x14001f27d  mov     [rsp+50h+var_30], rdi
0x14001f282  lea     r9, [rbx+30h]
0x14001f286  movups  xmmword ptr [rcx], xmm0
0x14001f289  call    DfscGetPathComponents
0x14001f28e  test    eax, eax
0x14001f290  js      loc_14001F4F1
0x14001f296  test    rbx, rbx
0x14001f299  jz      loc_14001F4F1
0x14001f29f  cmp     word ptr [rbx], 0
0x14001f2a3  jz      loc_14001F4F1
0x14001f2a9  mov     rax, [rbx+8]
0x14001f2ad  test    rax, rax
0x14001f2b0  jz      loc_14001F4F1
0x14001f2b6  cmp     word ptr [rax], 0
0x14001f2ba  jz      loc_14001F4F1
0x14001f2c0  cmp     word ptr [rdi], 0
0x14001f2c4  jz      short loc_14001F30E
0x14001f2c6  movzx   eax, [rbp+Destination.Length]
0x14001f2ca  xor     r10b, r10b
0x14001f2cd  movzx   r8d, word ptr [rbx+30h]
0x14001f2d2  mov     r9, [rbp+Destination.Buffer]
0x14001f2d6  shr     eax, 1
0x14001f2d8  dec     eax
0x14001f2da  shr     r8d, 1
0x14001f2dd  mov     [rbx+48h], r9
0x14001f2e1  cmp     eax, r8d
0x14001f2e4  jb      short loc_14001F30E
0x14001f2e6  nop     word ptr [rax+rax+00000000h]
0x14001f2f0  cmp     word ptr [r9+rax*2], 3Ah ; ':'
0x14001f2f6  lea     rdx, [r9+rax*2]
0x14001f2fa  jz      short loc_14001F348
0x14001f2fc  cmp     word ptr [rdx], 5Ch ; '\'
0x14001f300  jz      short loc_14001F309
0x14001f302  dec     eax
0x14001f304  cmp     eax, r8d
0x14001f307  jnb     short loc_14001F2F0
0x14001f309  test    r10b, r10b
0x14001f30c  jnz     short loc_14001F316
0x14001f30e  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x14001f312  movups  xmmword ptr [rbx+40h], xmm0
0x14001f316  mov     eax, r13d
0x14001f319  mov     rsi, [rsp+50h+arg_0]
0x14001f321  add     rsp, 50h
0x14001f325  pop     r15
0x14001f327  pop     r14
0x14001f329  pop     r13
0x14001f32b  pop     r12
0x14001f32d  pop     rdi
0x14001f32e  pop     rbx
0x14001f32f  pop     rbp
0x14001f330  retn
0x14001f332  movzx   eax, cx
0x14001f335  mov     r10b, 1
0x14001f338  add     ax, ax
0x14001f33b  mov     [rdi+42h], ax
0x14001f33f  mov     [rdi+40h], ax
0x14001f343  jmp     loc_14001F250
0x14001f348  movzx   ecx, ax
0x14001f34b  mov     r10b, 1
0x14001f34e  add     cx, cx
0x14001f351  mov     [rbx+42h], cx
0x14001f355  mov     [rbx+40h], cx
0x14001f359  jmp     short loc_14001F2FC
0x14001f35b  test    dword ptr [rcx+2Ch], 400000h
0x14001f362  jz      loc_14001F153
0x14001f368  mov     rcx, [rcx+18h]
0x14001f36c  lea     rax, [rbp+Destination]
0x14001f370  mov     edx, 0Bh
0x14001f375  mov     [rsp+50h+var_30], rax
0x14001f37a  mov     r9, r14
0x14001f37d  lea     r8, WPP_a8b72ae5a54533de05be1b18d60e4877_Traceguids
0x14001f384  call    WPP_SF_qZ
0x14001f389  jmp     loc_14001F153
0x14001f38e  test    dword ptr [rcx+2Ch], 400000h
0x14001f395  jz      loc_14001F0F4
0x14001f39b  mov     rcx, [rcx+18h]
0x14001f39f  lea     r8, WPP_a8b72ae5a54533de05be1b18d60e4877_Traceguids
0x14001f3a6  mov     edx, 0Ah
0x14001f3ab  mov     [rsp+50h+var_30], rsi
0x14001f3b0  mov     r9, r14
0x14001f3b3  call    WPP_SF_qq
0x14001f3b8  jmp     loc_14001F0F4
0x14001f3bd  mov     eax, 0C0000106h
0x14001f3c2  add     rsp, 50h
0x14001f3c6  pop     r15
0x14001f3c8  pop     r14
0x14001f3ca  pop     r13
0x14001f3cc  pop     r12
0x14001f3ce  pop     rdi
0x14001f3cf  pop     rbx
0x14001f3d0  pop     rbp
0x14001f3d1  retn
0x14001f3d3  mov     rax, [rcx+110h]
0x14001f3da  test    rax, rax
0x14001f3dd  jz      loc_14001F073
0x14001f3e3  mov     rcx, [rax+10h]
0x14001f3e7  cmp     dword ptr [rcx+8], 1
0x14001f3eb  jnz     loc_14001F073
0x14001f3f1  xor     r12d, r12d
0x14001f3f4  lea     r8, [rbp+Source]
0x14001f3f8  add     rcx, 90h
0x14001f3ff  mov     [rsp+50h+var_30], r12
0x14001f404  xor     r9d, r9d
0x14001f407  xor     edx, edx
0x14001f409  call    DfscGetPathComponents
0x14001f40e  xor     r9d, r9d
0x14001f411  mov     [rsp+50h+var_30], r12
0x14001f416  xor     r8d, r8d
0x14001f419  lea     rdx, [rbp+Destination]
0x14001f41d  mov     rcx, r13
0x14001f420  call    DfscGetPathComponents
0x14001f425  movzx   ebx, [rbp+Destination.Length]
0x14001f429  add     ebx, 4
0x14001f42c  mov     [rbp+arg_10], eax
0x14001f42f  jmp     loc_14001F07D
0x14001f434  mov     r13d, [rbp+arg_10]
0x14001f438  jmp     loc_14001F131
0x14001f43d  mov     rax, [r15+8]
0x14001f441  cmp     word ptr [rax], 5Ch ; '\'
0x14001f445  jnz     short loc_14001F479
0x14001f447  xor     al, al
0x14001f449  jmp     loc_14001F092
0x14001f44e  cmp     [rbp+arg_18], 0
0x14001f452  jnz     short loc_14001F49D
0x14001f454  mov     rdx, r15; Source
0x14001f457  lea     rcx, [rbp+Destination]; Destination
0x14001f45b  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001f462  nop     dword ptr [rax+rax+00h]
0x14001f467  mov     r13d, eax
0x14001f46a  jmp     loc_14001F13C
0x14001f46f  mov     eax, 0C000009Ah
0x14001f474  jmp     loc_14001F319
0x14001f479  test    r9w, r9w
0x14001f47d  jz      short loc_14001F486
0x14001f47f  mov     al, 1
0x14001f481  jmp     loc_14001F092
0x14001f486  mov     rax, [r13+8]
0x14001f48a  mov     ecx, ebx
0x14001f48c  shr     rcx, 1
0x14001f48f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14001f495  setnz   al
0x14001f498  jmp     loc_14001F092
0x14001f49d  lea     rdx, Source; "\\"
0x14001f4a4  lea     rcx, [rbp+Destination]; Destination
0x14001f4a8  call    cs:__imp_RtlAppendUnicodeToString
0x14001f4af  nop     dword ptr [rax+rax+00h]
0x14001f4b4  jmp     short loc_14001F454
0x14001f4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f4bd  cmp     rcx, r15
0x14001f4c0  jz      loc_14001F26A
0x14001f4c6  test    dword ptr [rcx+2Ch], 100000h
0x14001f4cd  jz      loc_14001F26A
0x14001f4d3  mov     rcx, [rcx+18h]
0x14001f4d7  lea     r9, [rbp+Destination]
0x14001f4db  mov     edx, 0Ah
0x14001f4e0  lea     r8, WPP_1bce9a35ce9f35cd7964d25412ee5844_Traceguids
0x14001f4e7  call    WPP_SF_Z
0x14001f4ec  jmp     loc_14001F26A
0x14001f4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f4f8  cmp     rcx, r15
  ... truncated ...
```
