# CscSidMapCreateInMemoryAccessList

- ea: `0x14008e1e0`
- end: `0x14008e621`
- name: `CscSidMapCreateInMemoryAccessList`
- size: `1089`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14002d2fc`
- `0x14002dcd4`
- `0x14002dfbc`
- `0x14002e2e8`

## callees

- `0x140005390`
- `0x140007420`
- `0x140016a04`
- `0x140025b68`
- `0x1400287bc`
- `0x14002b1a8`
- `0x14002f010`
- `0x14002f140`
- `0x14008e1e0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14008e320`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14008e320`
- `ntoskrnl!ExAllocatePool2` at `0x14008e347`
- `ntoskrnl!ExAllocatePool2` at `0x14008e388`
- `ntoskrnl!ExAllocatePool2` at `0x14008e4a6`
- `ntoskrnl!ExAllocatePool2` at `0x14008e347`
- `ntoskrnl!ExAllocatePool2` at `0x14008e388`
- `ntoskrnl!ExAllocatePool2` at `0x14008e4a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008e53c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008e53c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e57a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e57a`

## pseudocode

```c
__int64 __fastcall CscSidMapCreateInMemoryAccessList(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // r14d
  int v7; // ebx
  char v8; // r13
  unsigned __int16 v9; // di
  _DWORD *v10; // r12
  PVOID v11; // rax
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // r9
  _DWORD *v15; // r14
  _DWORD *Pool2; // rax
  __int64 v17; // r11
  unsigned __int16 v18; // dx
  __int64 v19; // rax
  char v20; // r10
  int v21; // r8d
  int v22; // ecx
  __int16 v23; // cx
  __int64 v24; // rcx
  __int64 v25; // rbx
  void *v26; // rax
  _BYTE v28[4]; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int16 v29; // [rsp+44h] [rbp-85h] BYREF
  int v30; // [rsp+48h] [rbp-81h] BYREF
  int v31; // [rsp+4Ch] [rbp-7Dh]
  int v32; // [rsp+50h] [rbp-79h]
  size_t Size; // [rsp+58h] [rbp-71h]
  __int64 v34; // [rsp+60h] [rbp-69h]
  PVOID P; // [rsp+68h] [rbp-61h]
  unsigned int v36; // [rsp+70h] [rbp-59h]
  __int64 v37; // [rsp+80h] [rbp-49h]
  __int64 v38; // [rsp+88h] [rbp-41h]
  __int64 v39; // [rsp+90h] [rbp-39h]
  _WORD v40[32]; // [rsp+A0h] [rbp-29h] BYREF

  v4 = 0;
  v28[0] = 0;
  v31 = 0;
  LOWORD(v30) = 0;
  v7 = 0;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  P = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, a1);
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  if ( !a1 )
  {
    v4 = 1218;
    v11 = 0;
    goto LABEL_37;
  }
  CscEnpMainAcquireExclusive(a1);
  v37 = *(_QWORD *)(a1 + 432);
  if ( v37 )
  {
    v8 = *(_BYTE *)(a1 + 442);
    v9 = *(_WORD *)(a1 + 444);
    LOWORD(v31) = v9;
  }
  else
  {
    v12 = CscEnUserQueryInMemoryAccessList(a1, v28, &v30, v40, &v29);
    v8 = v28[0];
    v7 = v12;
    v9 = v29;
    if ( v12 < 0 )
    {
      v4 = 1231;
      v31 = (unsigned __int16)v30;
      goto LABEL_31;
    }
    v37 = 0;
    v31 = (unsigned __int16)v30;
    v4 = 0;
  }
  v34 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL);
  ExAcquireResourceSharedLite(*(PERESOURCE *)(v34 + 8), 1u);
  if ( !v9 )
    goto LABEL_27;
  P = (PVOID)ExAllocatePool2(256, 8LL * v9, 557871939, v13);
  v15 = P;
  if ( P )
  {
    v36 = v9;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 16 * (unsigned int)v9 + 8, 591426371, v14);
    v10 = Pool2;
    if ( !Pool2 )
    {
      v7 = -1073741670;
      v4 = 1260;
      goto LABEL_30;
    }
    v17 = v34;
    v18 = 0;
    *Pool2 = v9;
    v19 = 0;
    v7 = 0;
    v30 = 0;
    while ( 1 )
    {
      v32 = v19;
      if ( (unsigned int)v19 >= v36 )
        break;
      if ( v37 )
      {
        v20 = *(_BYTE *)(v37 + 16LL * (unsigned int)v19 + 12);
        v29 = *(_WORD *)(v37 + 16LL * (unsigned int)v19);
        LODWORD(Size) = *(_DWORD *)(v37 + 16LL * (unsigned int)v19 + 4);
        v21 = *(_DWORD *)(v37 + 16LL * (unsigned int)v19 + 8);
        v22 = Size;
      }
      else
      {
        v23 = v40[4 * v19 + 1];
        v20 = HIBYTE(v40[4 * v19 + 3]);
        v29 = v40[4 * v19];
        v22 = v23 & 0x1FF | ((v23 & 0x3E00) << 7);
        v21 = v40[4 * v19 + 2] & 0x1FF | ((v40[4 * v19 + 2] & 0x3E00) << 7);
      }
      v15[2 * v19] = v22 | v21;
      v15[2 * v19 + 1] = v20 & 1;
      v24 = *(_QWORD *)(v17 + 56);
      if ( (unsigned int)(unsigned __int16)(v29 - 1) < *(_DWORD *)(v24 + 4) )
      {
        v38 = 16LL * (unsigned __int16)(v29 - 1);
        v25 = 4LL * v18;
        v39 = v25 * 4;
        Size = *(unsigned int *)(v38 + v24 + 8);
        v26 = (void *)ExAllocatePool2(258, (unsigned int)Size, 591426371, 1);
        *(_QWORD *)&v10[v25 + 4] = v26;
        if ( !v26 )
        {
          v7 = -1073741670;
          v4 = 1316;
          goto LABEL_30;
        }
        v7 = 0;
        LOWORD(v30) = v30 + 1;
        memmove(v26, *(const void **)(v38 + *(_QWORD *)(v34 + 56) + 16), Size);
        v18 = v30;
        v17 = v34;
        *(_DWORD *)((char *)v10 + v39 + 8) = Size;
      }
      v19 = (unsigned int)(v32 + 1);
    }
    v9 = v18;
    v10[1] = v18;
    v4 = 0;
LABEL_27:
    if ( v8 && v9 == (_WORD)v31 )
      *(_DWORD *)a2 |= 1u;
    goto LABEL_30;
  }
  v7 = -1073741670;
  v4 = 1254;
LABEL_30:
  ExReleaseResourceLite(*(PERESOURCE *)(v34 + 8));
LABEL_31:
  CscEnpMainRelease(a1);
  if ( v7 >= 0 )
  {
    v11 = P;
  }
  else
  {
    v9 = 0;
    if ( v10 )
    {
      CscSidMappDestroySidArray(v10);
      v10 = 0;
    }
    v11 = P;
    if ( P )
    {
      ExFreePoolWithTag(P, 0x21407343u);
      v11 = 0;
    }
  }
LABEL_37:
  *(_DWORD *)(a2 + 8) = v9;
  *(_DWORD *)(a2 + 4) = v9;
  *(_QWORD *)(a2 + 16) = v10;
  *(_QWORD *)(a2 + 24) = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    LOBYTE(a4) = v8 != 0 ? 89 : 78;
    WPP_SF_cDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_238132d70db8346a917bc6570ec5eca2_Traceguids,
      a4,
      (unsigned __int16)v31,
      v9,
      v7,
      v4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14008e1e0  mov     [rsp-8+arg_10], rbx
0x14008e1e5  push    rbp
0x14008e1e6  push    rsi
0x14008e1e7  push    rdi
0x14008e1e8  push    r12
0x14008e1ea  push    r13
0x14008e1ec  push    r14
0x14008e1ee  push    r15
0x14008e1f0  lea     rbp, [rsp-27h]
0x14008e1f5  sub     rsp, 0F0h
0x14008e1fc  mov     rax, cs:__security_cookie
0x14008e203  xor     rax, rsp
0x14008e206  mov     [rbp+57h+var_40], rax
0x14008e20a  xor     r14d, r14d
0x14008e20d  mov     r15, rdx
0x14008e210  mov     eax, r14d
0x14008e213  mov     [rsp+120h+var_E0], r14b
0x14008e218  mov     [rbp+57h+var_D4], eax
0x14008e21b  mov     rsi, rcx
0x14008e21e  mov     word ptr [rsp+120h+var_D8], ax
0x14008e223  mov     ebx, r14d
0x14008e226  mov     r13b, r14b
0x14008e229  mov     [rsp+120h+var_DC], r14w
0x14008e22f  mov     edi, r14d
0x14008e232  mov     [rbp+57h+P], r14
0x14008e236  mov     r12d, r14d
0x14008e239  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e240  lea     rax, WPP_GLOBAL_Control
0x14008e247  cmp     rcx, rax
0x14008e24a  jz      short loc_14008E26C
0x14008e24c  test    dword ptr [rcx+2Ch], 40000h
0x14008e253  jz      short loc_14008E26C
0x14008e255  mov     rcx, [rcx+18h]
0x14008e259  lea     edx, [r14+13h]
0x14008e25d  mov     r9, rsi
0x14008e260  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14008e267  call    WPP_SF_q
0x14008e26c  xorps   xmm0, xmm0
0x14008e26f  movups  xmmword ptr [r15], xmm0
0x14008e273  movups  xmmword ptr [r15+10h], xmm0
0x14008e278  test    rsi, rsi
0x14008e27b  jnz     short loc_14008E28B
0x14008e27d  mov     r14d, 4C2h
0x14008e283  mov     rax, rbx
0x14008e286  jmp     loc_14008E58E
0x14008e28b  mov     rcx, rsi
0x14008e28e  call    CscEnpMainAcquireExclusive
0x14008e293  mov     rax, [rsi+1B0h]
0x14008e29a  mov     [rbp+57h+var_A0], rax
0x14008e29e  test    rax, rax
0x14008e2a1  jnz     short loc_14008E2F9
0x14008e2a3  lea     rax, [rsp+120h+var_DC]
0x14008e2a8  mov     rcx, rsi
0x14008e2ab  lea     r9, [rbp+57h+var_80]
0x14008e2af  mov     [rsp+120h+var_100], rax
0x14008e2b4  lea     r8, [rsp+120h+var_D8]
0x14008e2b9  lea     rdx, [rsp+120h+var_E0]
0x14008e2be  call    CscEnUserQueryInMemoryAccessList
0x14008e2c3  mov     r13b, [rsp+120h+var_E0]
0x14008e2c8  mov     ebx, eax
0x14008e2ca  movzx   edi, [rsp+120h+var_DC]
0x14008e2cf  test    eax, eax
0x14008e2d1  jns     short loc_14008E2E6
0x14008e2d3  movzx   eax, word ptr [rsp+120h+var_D8]
0x14008e2d8  mov     r14d, 4CFh
0x14008e2de  mov     [rbp+57h+var_D4], eax
0x14008e2e1  jmp     loc_14008E548
0x14008e2e6  mov     [rbp+57h+var_A0], r14
0x14008e2ea  movzx   r14d, word ptr [rsp+120h+var_D8]
0x14008e2f0  mov     [rbp+57h+var_D4], r14d
0x14008e2f4  xor     r14d, r14d
0x14008e2f7  jmp     short loc_14008E30E
0x14008e2f9  movzx   eax, word ptr [rsi+1BCh]
0x14008e300  mov     r13b, [rsi+1BAh]
0x14008e307  movzx   edi, ax
0x14008e30a  mov     word ptr [rbp+57h+var_D4], ax
0x14008e30e  mov     rax, [rsi+8]
0x14008e312  mov     dl, 1; Wait
0x14008e314  mov     rax, [rax+38h]
0x14008e318  mov     [rbp+57h+var_C0], rax
0x14008e31c  mov     rcx, [rax+8]; Resource
0x14008e320  call    cs:__imp_ExAcquireResourceSharedLite
0x14008e327  nop     dword ptr [rax+rax+00h]
0x14008e32c  test    di, di
0x14008e32f  jz      loc_14008E525
0x14008e335  movzx   edx, di
0x14008e338  mov     ecx, 100h
0x14008e33d  shl     rdx, 3
0x14008e341  mov     r8d, 21407343h
0x14008e347  call    cs:__imp_ExAllocatePool2
0x14008e34e  nop     dword ptr [rax+rax+00h]
0x14008e353  mov     [rbp+57h+P], rax
0x14008e357  mov     r14, rax
0x14008e35a  test    rax, rax
0x14008e35d  jnz     short loc_14008E36F
0x14008e35f  mov     ebx, 0C000009Ah
0x14008e364  mov     r14d, 4E6h
0x14008e36a  jmp     loc_14008E534
0x14008e36f  movzx   ebx, di
0x14008e372  mov     ecx, 100h
0x14008e377  mov     edx, ebx
0x14008e379  mov     [rbp+57h+var_B0], ebx
0x14008e37c  shl     edx, 4
0x14008e37f  mov     r8d, 23407343h
0x14008e385  add     edx, 8
0x14008e388  call    cs:__imp_ExAllocatePool2
0x14008e38f  nop     dword ptr [rax+rax+00h]
0x14008e394  mov     r12, rax
0x14008e397  test    rax, rax
0x14008e39a  jnz     short loc_14008E3AC
0x14008e39c  mov     ebx, 0C000009Ah
0x14008e3a1  mov     r14d, 4ECh
0x14008e3a7  jmp     loc_14008E534
0x14008e3ac  mov     r11, [rbp+57h+var_C0]
0x14008e3b0  xor     edx, edx
0x14008e3b2  mov     [rax], ebx
0x14008e3b4  xor     eax, eax
0x14008e3b6  xor     ebx, ebx
0x14008e3b8  mov     [rsp+120h+var_D8], edx
0x14008e3bc  mov     [rbp+57h+var_D0], eax
0x14008e3bf  cmp     eax, [rbp+57h+var_B0]
0x14008e3c2  jnb     loc_14008E517
0x14008e3c8  mov     ecx, eax
0x14008e3ca  lea     r9, ds:0[rax*8]
0x14008e3d2  mov     rax, [rbp+57h+var_A0]
0x14008e3d6  test    rax, rax
0x14008e3d9  jz      short loc_14008E401
0x14008e3db  add     rcx, rcx
0x14008e3de  movzx   r8d, word ptr [rax+rcx*8]
0x14008e3e3  mov     r10b, [rax+rcx*8+0Ch]
0x14008e3e8  mov     [rsp+120h+var_DC], r8w
0x14008e3ee  mov     r8d, [rax+rcx*8+4]
0x14008e3f3  mov     dword ptr [rbp+57h+Size], r8d
0x14008e3f7  mov     r8d, [rax+rcx*8+8]
0x14008e3fc  mov     ecx, dword ptr [rbp+57h+Size]
0x14008e3ff  jmp     short loc_14008E446
0x14008e401  movzx   eax, [rbp+r9+57h+var_7E]
0x14008e407  movzx   r8d, [rbp+r9+57h+var_80]
0x14008e40d  mov     ecx, eax
0x14008e40f  mov     r10b, [rbp+r9+57h+var_79]
0x14008e414  and     eax, 1FFh
0x14008e419  mov     [rsp+120h+var_DC], r8w
0x14008e41f  and     ecx, 3E00h
0x14008e425  shl     ecx, 7
0x14008e428  or      ecx, eax
0x14008e42a  movzx   eax, [rbp+r9+57h+var_7C]
0x14008e430  mov     r8d, eax
0x14008e433  and     eax, 1FFh
0x14008e438  and     r8d, 3E00h
0x14008e43f  shl     r8d, 7
0x14008e443  or      r8d, eax
0x14008e446  or      r8d, ecx
0x14008e449  and     r10b, 1
0x14008e44d  mov     [r14+r9], r8d
0x14008e451  movzx   eax, r10b
0x14008e455  mov     [r14+r9+4], eax
0x14008e45a  mov     r9d, 1
0x14008e460  movzx   eax, [rsp+120h+var_DC]
0x14008e465  mov     rcx, [r11+38h]
0x14008e469  sub     ax, r9w
0x14008e46d  movzx   r8d, ax
0x14008e471  cmp     r8d, [rcx+4]
0x14008e475  jnb     loc_14008E4FF
0x14008e47b  mov     eax, r8d
0x14008e47e  movzx   ebx, dx
0x14008e481  shl     rax, 4
0x14008e485  mov     r8d, 23407343h
0x14008e48b  mov     [rbp+57h+var_98], rax
0x14008e48f  shl     rbx, 4
0x14008e493  mov     [rbp+57h+var_90], rbx
0x14008e497  mov     eax, [rax+rcx+8]
0x14008e49b  mov     ecx, 102h
0x14008e4a0  mov     edx, eax
0x14008e4a2  mov     [rbp+57h+Size], rax
0x14008e4a6  call    cs:__imp_ExAllocatePool2
0x14008e4ad  nop     dword ptr [rax+rax+00h]
0x14008e4b2  mov     [rbx+r12+10h], rax
0x14008e4b7  mov     r9, rax
0x14008e4ba  test    rax, rax
0x14008e4bd  jz      short loc_14008E50A
0x14008e4bf  mov     rcx, [rbp+57h+var_98]
0x14008e4c3  xor     ebx, ebx
0x14008e4c5  mov     r8, [rbp+57h+Size]; Size
0x14008e4c9  lea     eax, [rbx+1]
0x14008e4cc  add     word ptr [rsp+120h+var_D8], ax
0x14008e4d1  mov     rax, [rbp+57h+var_C0]
0x14008e4d5  mov     rdx, [rax+38h]
0x14008e4d9  mov     rdx, [rcx+rdx+10h]; Src
0x14008e4de  mov     rcx, r9; void *
0x14008e4e1  call    memmove
0x14008e4e6  mov     rax, [rbp+57h+var_90]
0x14008e4ea  lea     r9d, [rbx+1]
0x14008e4ee  mov     rcx, [rbp+57h+Size]
0x14008e4f2  mov     edx, [rsp+120h+var_D8]
0x14008e4f6  mov     r11, [rbp+57h+var_C0]
0x14008e4fa  mov     [rax+r12+8], ecx
0x14008e4ff  mov     eax, [rbp+57h+var_D0]
0x14008e502  add     eax, r9d
0x14008e505  jmp     loc_14008E3BC
0x14008e50a  mov     ebx, 0C000009Ah
0x14008e50f  mov     r14d, 524h
0x14008e515  jmp     short loc_14008E534
0x14008e517  movzx   eax, dx
0x14008e51a  movzx   edi, dx
0x14008e51d  mov     [r12+4], eax
0x14008e522  xor     r14d, r14d
0x14008e525  test    r13b, r13b
0x14008e528  jz      short loc_14008E534
0x14008e52a  cmp     di, word ptr [rbp+57h+var_D4]
0x14008e52e  jnz     short loc_14008E534
0x14008e530  or      dword ptr [r15], 1
0x14008e534  mov     rax, [rbp+57h+var_C0]
0x14008e538  mov     rcx, [rax+8]; Resource
0x14008e53c  call    cs:__imp_ExReleaseResourceLite
0x14008e543  nop     dword ptr [rax+rax+00h]
0x14008e548  mov     rcx, rsi
0x14008e54b  call    CscEnpMainRelease
0x14008e550  test    ebx, ebx
0x14008e552  jns     short loc_14008E58A
0x14008e554  xor     eax, eax
0x14008e556  movzx   edi, ax
0x14008e559  test    r12, r12
0x14008e55c  jz      short loc_14008E569
0x14008e55e  mov     rcx, r12; P
0x14008e561  call    CscSidMappDestroySidArray
0x14008e566  xor     r12d, r12d
0x14008e569  mov     rax, [rbp+57h+P]
0x14008e56d  test    rax, rax
0x14008e570  jz      short loc_14008E58E
0x14008e572  mov     edx, 21407343h; Tag
0x14008e577  mov     rcx, rax; P
0x14008e57a  call    cs:__imp_ExFreePoolWithTag
0x14008e581  nop     dword ptr [rax+rax+00h]
0x14008e586  xor     eax, eax
0x14008e588  jmp     short loc_14008E58E
0x14008e58a  mov     rax, [rbp+57h+P]
0x14008e58e  movzx   r10d, di
0x14008e592  mov     [r15+8], r10d
0x14008e596  mov     [r15+4], r10d
0x14008e59a  mov     [r15+10h], r12
0x14008e59e  mov     [r15+18h], rax
0x14008e5a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008e5a9  lea     rax, WPP_GLOBAL_Control
0x14008e5b0  cmp     rcx, rax
0x14008e5b3  jz      short loc_14008E5F7
0x14008e5b5  test    dword ptr [rcx+2Ch], 40000h
0x14008e5bc  jz      short loc_14008E5F7
0x14008e5be  movzx   eax, word ptr [rbp+57h+var_D4]
0x14008e5c2  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14008e5c9  mov     rcx, [rcx+18h]
0x14008e5cd  neg     r13b
0x14008e5d0  mov     [rsp+120h+var_E8], r14d
0x14008e5d5  mov     edx, 14h
0x14008e5da  sbb     r9b, r9b
0x14008e5dd  mov     [rsp+120h+var_F0], ebx
0x14008e5e1  and     r9b, 0Bh
0x14008e5e5  mov     [rsp+120h+var_F8], r10d
0x14008e5ea  add     r9b, 4Eh ; 'N'
0x14008e5ee  mov     dword ptr [rsp+120h+var_100], eax
0x14008e5f2  call    WPP_SF_cDDDD
0x14008e5f7  mov     eax, ebx
0x14008e5f9  mov     rcx, [rbp+57h+var_40]
0x14008e5fd  xor     rcx, rsp; StackCookie
0x14008e600  call    __security_check_cookie
0x14008e605  mov     rbx, [rsp+120h+arg_10]
0x14008e60d  add     rsp, 0F0h
0x14008e614  pop     r15
0x14008e616  pop     r14
0x14008e618  pop     r13
0x14008e61a  pop     r12
0x14008e61c  pop     rdi
0x14008e61d  pop     rsi
0x14008e61e  pop     rbp
0x14008e61f  retn
```
