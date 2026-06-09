# Smb2CheckPath_Start

- ea: `0x1400328a0`
- end: `0x140032b29`
- name: `Smb2CheckPath_Start`
- size: `649`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000e700`
- `0x1400328a0`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400329ae`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140032a98`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400329ae`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140032a98`
- `rdbss!RxFreeMdl` at `0x140032aff`
- `rdbss!RxFreeMdl` at `0x140032b0d`
- `rdbss!RxFreeMdl` at `0x140032aff`
- `rdbss!RxFreeMdl` at `0x140032b0d`
- `rdbss!RxAllocateMdl2` at `0x14003298d`
- `rdbss!RxAllocateMdl2` at `0x140032a76`
- `rdbss!RxAllocateMdl2` at `0x14003298d`
- `rdbss!RxAllocateMdl2` at `0x140032a76`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140032a0c`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140032aea`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140032a0c`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x140032aea`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400329f0`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140032ad2`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400329f0`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140032ad2`

## pseudocode

```c
__int64 __fastcall Smb2CheckPath_Start(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rdi
  unsigned int v4; // r11d
  __int64 v5; // rax
  const void *v6; // rdx
  _WORD *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  char v10; // r8
  struct _MDL *Mdl2; // rax
  struct _MDL *v12; // rdi
  int v13; // ebx
  __m128i si128; // xmm0
  __int64 v15; // r11
  struct _MDL *v16; // rax
  __int64 v18; // [rsp+28h] [rbp-60h]
  __int64 v19; // [rsp+38h] [rbp-50h]
  int v20; // [rsp+40h] [rbp-48h]

  v1 = a1 + 3972;
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 3792) + 8LL);
  SmbCeBuildSmb2Header(a1, a1 + 3972, 64);
  v5 = *(_QWORD *)(a1 + 3792);
  v6 = (const void *)(v3 + 2);
  *(_WORD *)(a1 + 3984) = 5;
  *(_WORD *)(a1 + 4036) = 57;
  *(_WORD *)(a1 + 4080) = 120;
  v7 = *(_WORD **)(v5 + 8);
  v8 = v4 - 2;
  if ( *v7 != 92 )
  {
    v8 = v4;
    v6 = (const void *)v3;
  }
  v9 = v8;
  memmove((void *)(a1 + 4092), v6, v8);
  v10 = *(_BYTE *)(a1 + 3800);
  *(_WORD *)(a1 + 4082) = v9;
  *(_WORD *)(a1 + 4038) = 0;
  *(_DWORD *)(a1 + 4064) = 0;
  *(_DWORD *)(a1 + 4068) = 7;
  *(_DWORD *)(a1 + 4072) = 1;
  *(_DWORD *)(a1 + 4040) = 0;
  *(_DWORD *)(a1 + 4060) = v10 != 0 ? 32 : 128;
  *(_DWORD *)(a1 + 4076) = v10 != 0;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(v1, v9 + 120, 0, 0, 0);
  v12 = Mdl2;
  if ( !Mdl2 )
    goto LABEL_4;
  MmBuildMdlForNonPagedPool(Mdl2);
  v13 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1024, a1, v12, v9 + 120, 0, 0, 0, 0, 0, 4);
  if ( !v13 )
  {
    v12 = 0;
    v13 = SmbCseSubmitBufferContext(a1 + 1024);
    if ( v13 < 0 )
      goto LABEL_11;
    SmbCeBuildSmb2Header(a1, a1 + 3852, 64);
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *(_WORD *)(a1 + 3864) = 6;
    *(_WORD *)(a1 + 3916) = 24;
    *(_DWORD *)(a1 + 3920) = 0;
    *(__m128i *)(a1 + 3924) = si128;
    v16 = (struct _MDL *)RxAllocateMdl2(v15, 88, 0, 0, 0);
    v12 = v16;
    if ( !v16 )
    {
LABEL_4:
      v13 = -1073741670;
LABEL_11:
      RxFreeMdl(v12);
      RxFreeMdl(0);
      return (unsigned int)v13;
    }
    MmBuildMdlForNonPagedPool(v16);
    LOWORD(v20) = 0;
    LODWORD(v19) = 0;
    LODWORD(v18) = 0;
    v13 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 2408, a1, v12, 88, 0, v18, 0, v19, v20, 4);
    if ( !v13 )
    {
      v12 = 0;
      v13 = SmbCseSubmitBufferContext(a1 + 2408);
    }
  }
  if ( v13 < 0 )
    goto LABEL_11;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400328a0  push    rbx
0x1400328a2  push    rbp
0x1400328a3  push    rsi
0x1400328a4  push    rdi
0x1400328a5  push    r14
0x1400328a7  push    r15
0x1400328a9  sub     rsp, 58h
0x1400328ad  mov     rax, [rcx+0ED0h]
0x1400328b4  lea     rsi, [rcx+0F84h]
0x1400328bb  mov     r8d, 40h ; '@'
0x1400328c1  mov     rdx, rsi
0x1400328c4  mov     rbp, rcx
0x1400328c7  movzx   r11d, word ptr [rax]
0x1400328cb  mov     rdi, [rax+8]
0x1400328cf  call    SmbCeBuildSmb2Header
0x1400328d4  mov     rax, [rbp+0ED0h]
0x1400328db  lea     rdx, [rdi+2]
0x1400328df  mov     word ptr [rbp+0F90h], 5
0x1400328e8  mov     word ptr [rbp+0FC4h], 39h ; '9'
0x1400328f1  mov     word ptr [rbp+0FF0h], 78h ; 'x'
0x1400328fa  mov     rcx, [rax+8]
0x1400328fe  lea     eax, [r11-2]
0x140032902  cmp     word ptr [rcx], 5Ch ; '\'
0x140032906  lea     rcx, [rbp+0FFCh]; void *
0x14003290d  cmovnz  eax, r11d
0x140032911  cmovnz  rdx, rdi; Src
0x140032915  mov     r8d, eax; Size
0x140032918  mov     ebx, eax
0x14003291a  call    memmove
0x14003291f  mov     r8b, [rbp+0ED8h]
0x140032926  xor     r15d, r15d
0x140032929  mov     al, r8b
0x14003292c  mov     [rbp+0FF2h], bx
0x140032933  neg     al
0x140032935  mov     [rbp+0FC6h], r15w
0x14003293d  mov     eax, r15d
0x140032940  mov     [rbp+0FE0h], r15d
0x140032947  sbb     edx, edx
0x140032949  mov     dword ptr [rbp+0FE4h], 7
0x140032953  and     edx, 0FFFFFFA0h
0x140032956  mov     dword ptr [rbp+0FE8h], 1
0x140032960  sub     edx, 0FFFFFF80h
0x140032963  mov     [rbp+0FC8h], r15d
0x14003296a  test    r8b, r8b
0x14003296d  mov     [rbp+0FDCh], edx
0x140032973  lea     edx, [rbx+78h]
0x140032976  mov     [rsp+88h+var_68], r15
0x14003297b  setnz   al
0x14003297e  mov     rcx, rsi
0x140032981  xor     r9d, r9d
0x140032984  mov     [rbp+0FECh], eax
0x14003298a  xor     r8d, r8d
0x14003298d  call    cs:__imp_RxAllocateMdl2
0x140032994  nop     dword ptr [rax+rax+00h]
0x140032999  mov     rdi, rax
0x14003299c  test    rax, rax
0x14003299f  jnz     short loc_1400329AB
0x1400329a1  mov     ebx, 0C000009Ah
0x1400329a6  jmp     loc_140032AFC
0x1400329ab  mov     rcx, rdi; MemoryDescriptorList
0x1400329ae  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400329b5  nop     dword ptr [rax+rax+00h]
0x1400329ba  mov     [rsp+88h+var_40], 4
0x1400329c2  lea     rsi, [rbp+400h]
0x1400329c9  mov     [rsp+88h+var_48], r15w
0x1400329cf  lea     r9d, [rbx+78h]
0x1400329d3  mov     dword ptr [rsp+88h+var_50], r15d
0x1400329d8  mov     r8, rdi
0x1400329db  mov     [rsp+88h+var_58], r15
0x1400329e0  mov     rdx, rbp
0x1400329e3  mov     dword ptr [rsp+88h+var_60], r15d
0x1400329e8  mov     rcx, rsi
0x1400329eb  mov     [rsp+88h+var_68], r15
0x1400329f0  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x1400329f7  nop     dword ptr [rax+rax+00h]
0x1400329fc  mov     ebx, eax
0x1400329fe  test    eax, eax
0x140032a00  jnz     loc_140032AF8
0x140032a06  mov     rcx, rsi
0x140032a09  mov     rdi, r15
0x140032a0c  call    cs:__imp_SmbCseSubmitBufferContext
0x140032a13  nop     dword ptr [rax+rax+00h]
0x140032a18  mov     ebx, eax
0x140032a1a  test    eax, eax
0x140032a1c  js      loc_140032AFC
0x140032a22  lea     r11, [rbp+0F0Ch]
0x140032a29  mov     r8d, 40h ; '@'
0x140032a2f  mov     rdx, r11
0x140032a32  mov     rcx, rbp
0x140032a35  call    SmbCeBuildSmb2Header
0x140032a3a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140032a42  xor     r9d, r9d
0x140032a45  mov     word ptr [rbp+0F18h], 6
0x140032a4e  xor     r8d, r8d
0x140032a51  mov     word ptr [rbp+0F4Ch], 18h
0x140032a5a  mov     rcx, r11
0x140032a5d  mov     [rbp+0F50h], r15d
0x140032a64  lea     ebx, [r9+58h]
0x140032a68  mov     [rsp+88h+var_68], r15
0x140032a6d  mov     edx, ebx
0x140032a6f  movups  xmmword ptr [rbp+0F54h], xmm0
0x140032a76  call    cs:__imp_RxAllocateMdl2
0x140032a7d  nop     dword ptr [rax+rax+00h]
0x140032a82  mov     rdi, rax
0x140032a85  test    rax, rax
0x140032a88  jz      loc_1400329A1
0x140032a8e  mov     rcx, rax; MemoryDescriptorList
0x140032a91  lea     rsi, [rbp+968h]
0x140032a98  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140032a9f  nop     dword ptr [rax+rax+00h]
0x140032aa4  mov     [rsp+88h+var_40], 4
0x140032aac  mov     r9d, ebx
0x140032aaf  mov     [rsp+88h+var_48], r15w
0x140032ab5  mov     r8, rdi
0x140032ab8  mov     dword ptr [rsp+88h+var_50], r15d
0x140032abd  mov     rdx, rbp
0x140032ac0  mov     [rsp+88h+var_58], r15
0x140032ac5  mov     rcx, rsi
0x140032ac8  mov     dword ptr [rsp+88h+var_60], r15d
0x140032acd  mov     [rsp+88h+var_68], r15
0x140032ad2  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x140032ad9  nop     dword ptr [rax+rax+00h]
0x140032ade  mov     ebx, eax
0x140032ae0  test    eax, eax
0x140032ae2  jnz     short loc_140032AF8
0x140032ae4  mov     rcx, rsi
0x140032ae7  mov     rdi, r15
0x140032aea  call    cs:__imp_SmbCseSubmitBufferContext
0x140032af1  nop     dword ptr [rax+rax+00h]
0x140032af6  mov     ebx, eax
0x140032af8  test    ebx, ebx
0x140032afa  jns     short loc_140032B19
0x140032afc  mov     rcx, rdi
0x140032aff  call    cs:__imp_RxFreeMdl
0x140032b06  nop     dword ptr [rax+rax+00h]
0x140032b0b  xor     ecx, ecx
0x140032b0d  call    cs:__imp_RxFreeMdl
0x140032b14  nop     dword ptr [rax+rax+00h]
0x140032b19  mov     eax, ebx
0x140032b1b  add     rsp, 58h
0x140032b1f  pop     r15
0x140032b21  pop     r14
0x140032b23  pop     rdi
0x140032b24  pop     rsi
0x140032b25  pop     rbp
0x140032b26  pop     rbx
0x140032b27  retn
```
