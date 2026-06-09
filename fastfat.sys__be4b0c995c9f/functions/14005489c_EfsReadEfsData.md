# EfsReadEfsData

- ea: `0x14005489c`
- end: `0x140054cdd`
- name: `EfsReadEfsData`
- size: `1089`
- prototype: ``
- caller_count: `10`
- callee_count: `13`
- tags: ``

## callers

- `0x14004eff0`
- `0x14004fa4c`
- `0x1400501d0`
- `0x140050780`
- `0x140050cf0`
- `0x1400538dc`
- `0x140053f20`
- `0x140054480`
- `0x140055380`
- `0x140056ccc`

## callees

- `0x1400034f0`
- `0x14000363c`
- `0x140004144`
- `0x140004498`
- `0x140004518`
- `0x14000c230`
- `0x14000c380`
- `0x14004f910`
- `0x140050ae0`
- `0x14005489c`
- `0x140055b6c`
- `0x14005625c`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140054c4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054cab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060651`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060695`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054c4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054cab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060651`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060695`
- `ntoskrnl!ExAllocatePool2` at `0x140054a7b`
- `ntoskrnl!ExAllocatePool2` at `0x140054a7b`

## pseudocode

```c
__int64 __fastcall EfsReadEfsData(__int64 a1, _WORD *a2, char a3, void **a4, _DWORD *a5, _DWORD *a6)
{
  char v8; // r13
  __int64 Length; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // r12d
  __int64 v14; // rcx
  __int64 Pool2; // rax
  __int64 v16; // rcx
  _OWORD *v17; // r14
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  size_t v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  char v28; // [rsp+40h] [rbp-108h] BYREF
  char v29; // [rsp+41h] [rbp-107h]
  __int64 v30; // [rsp+48h] [rbp-100h] BYREF
  int v31; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v32; // [rsp+58h] [rbp-F0h]
  void *Src; // [rsp+60h] [rbp-E8h] BYREF
  __int128 v34; // [rsp+68h] [rbp-E0h] BYREF
  __int128 v35; // [rsp+78h] [rbp-D0h]
  _OWORD v36[2]; // [rsp+88h] [rbp-C0h] BYREF
  PVOID P[2]; // [rsp+A8h] [rbp-A0h]
  __int64 v38; // [rsp+B8h] [rbp-90h]
  _OWORD *v39; // [rsp+C0h] [rbp-88h]
  _DWORD *v40; // [rsp+C8h] [rbp-80h]
  _WORD *v41; // [rsp+D0h] [rbp-78h]
  void **v42; // [rsp+D8h] [rbp-70h]
  __int64 v43[2]; // [rsp+E0h] [rbp-68h] BYREF
  __int128 v44; // [rsp+F0h] [rbp-58h]

  v29 = a3;
  v41 = a2;
  v42 = a4;
  v40 = a6;
  v30 = 0;
  Src = 0;
  v34 = 0;
  v35 = 0;
  v31 = 0;
  v28 = 0;
  v8 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v32 = 0;
  memset(v36, 0, sizeof(v36));
  *(_OWORD *)P = 0;
  if ( a4 )
    *a4 = 0;
  if ( (int)NtOfsCreateAttributeEx(a2, a1, &DestinationString, 256, 2, 1, &v30) < 0 )
  {
    *a6 = 512;
    goto LABEL_35;
  }
  v38 = 0;
  Length = NtOfsQueryLength(v30);
  v13 = Length;
  v38 = Length;
  if ( Length >= 0 )
  {
    if ( (unsigned __int64)Length <= 0x20 || Length > 0x40000 )
      goto LABEL_6;
    *a5 = Length;
    *((_QWORD *)&v35 + 1) = 0;
    NtOfsMapAttribute(a2, v30, 0, (unsigned int)Length, &Src, &v34);
    if ( (int)EfspGetHeaderType(Src, v13, &v31, &v28) < 0 )
      goto LABEL_10;
    if ( !v28 )
    {
      v14 = 1;
      if ( (unsigned int)(v31 - 2) <= 1 )
        v8 = 1;
    }
    if ( a4 )
    {
      if ( v8 )
        *a5 += 32;
      Pool2 = ExAllocatePool2(256, (unsigned int)*a5, 1836279365);
      v17 = (_OWORD *)Pool2;
      *a4 = (void *)Pool2;
      if ( !Pool2 )
      {
        NtOfsReleaseMap(v16, &v34);
        NtOfsCloseAttribute((__int64)a2, v30, v18, v19);
        *a6 = 2048;
        v20 = -1073741670;
        goto LABEL_36;
      }
      v39 = (_OWORD *)Pool2;
      if ( v8 )
      {
        if ( (int)EfspGetSetPFileInfo(Src, v13, (__int64)v43, 32) < 0 )
        {
LABEL_21:
          NtOfsReleaseMap(v21, &v34);
          NtOfsCloseAttribute((__int64)a2, v30, v22, v23);
          *a6 = 4096;
          goto LABEL_35;
        }
        LODWORD(v43[0]) = *a5;
        *v17 = *(_OWORD *)v43;
        v17[1] = v44;
        v17 += 2;
        v39 = v17;
      }
      memmove(v17, Src, v13);
      v24 = (unsigned int)*a5;
      v14 = (__int64)*a4;
      if ( *(_DWORD *)*a4 > (unsigned int)v24 )
      {
        EfspTraceLogAssert(v14, 6, 483, 3221227787LL);
        goto LABEL_21;
      }
      if ( (unsigned int)(v31 - 1) <= 1 && v29 )
      {
        if ( (int)EfsGetEfsStreamInfo((void *)v14, v24, 8) < 0 )
          goto LABEL_10;
        if ( (_DWORD)v32 != 1 || (v32 & 0x300000000LL) == 0 )
          goto LABEL_33;
        LODWORD(v32) = 0;
        BYTE4(v32) = 0;
        if ( (int)EfsSetEfsStreamInfo(*a4, (unsigned int)*a5, 8) < 0
          || (memset((char *)v36 + 8, 0, 20),
              LODWORD(v36[0]) |= 1u,
              (int)EfsSetEfsStreamInfo(*a4, (unsigned int)*a5, 48) < 0) )
        {
LABEL_10:
          NtOfsReleaseMap(v14, &v34);
          goto LABEL_6;
        }
        ExFreePoolWithTag(*a4, 0);
        *a4 = P[0];
        P[0] = 0;
        *a5 = P[1];
      }
    }
LABEL_33:
    NtOfsReleaseMap(v14, &v34);
    NtOfsCloseAttribute((__int64)a2, v30, v25, v26);
    *a6 = 0x10000;
    goto LABEL_35;
  }
  EfspTraceLogAssert(v10, 6, 311, 3221225473LL);
LABEL_6:
  NtOfsCloseAttribute((__int64)a2, v30, v11, v12);
  *a6 = 4096;
LABEL_35:
  v20 = 0;
LABEL_36:
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0);
  return v20;
}

```

## disassembly

```asm
0x14005489c  mov     r11, rsp
0x14005489f  push    rbx
0x1400548a0  push    rsi
0x1400548a1  push    rdi
0x1400548a2  push    r12
0x1400548a4  push    r13
0x1400548a6  push    r14
0x1400548a8  push    r15
0x1400548aa  sub     rsp, 110h
0x1400548b1  mov     rax, cs:__security_cookie
0x1400548b8  xor     rax, rsp
0x1400548bb  mov     [rsp+148h+var_48], rax
0x1400548c3  mov     rsi, r9
0x1400548c6  mov     [rsp+148h+var_107], r8b
0x1400548cb  mov     rdi, rdx
0x1400548ce  mov     [rsp+148h+var_78], rdx
0x1400548d6  mov     [rsp+148h+var_70], r9
0x1400548de  mov     r15, [rsp+148h+arg_20]
0x1400548e6  mov     rbx, [rsp+148h+arg_28]
0x1400548ee  mov     [rsp+148h+var_80], rbx
0x1400548f6  xor     r14d, r14d
0x1400548f9  mov     [rsp+148h+var_100], r14
0x1400548fe  mov     [rsp+148h+Src], r14
0x140054903  xorps   xmm0, xmm0
0x140054906  movups  [rsp+148h+var_E0], xmm0
0x14005490b  movups  [rsp+148h+var_D0], xmm0
0x140054910  mov     [rsp+148h+var_F8], r14d
0x140054915  mov     [rsp+148h+var_108], r14b
0x14005491a  movzx   r13d, r14b
0x14005491e  movups  xmmword ptr [r11-68h], xmm0
0x140054923  movups  xmmword ptr [r11-58h], xmm0
0x140054928  mov     [rsp+148h+var_F0], r14
0x14005492d  xorps   xmm1, xmm1
0x140054930  movups  [rsp+148h+var_C0], xmm1
0x140054938  movups  [rsp+148h+var_B0], xmm1
0x140054940  movups  xmmword ptr [rsp+148h+P], xmm1
0x140054948  test    r9, r9
0x14005494b  jz      short loc_140054950
0x14005494d  mov     [r9], r14
0x140054950  lea     rax, [rsp+148h+var_100]
0x140054955  mov     [rsp+148h+var_118], rax
0x14005495a  mov     [rsp+148h+var_120], 1
0x140054962  mov     dword ptr [rsp+148h+var_128], 2
0x14005496a  mov     r9d, 100h
0x140054970  lea     r8, DestinationString
0x140054977  mov     rdx, rcx
0x14005497a  mov     rcx, rdi
0x14005497d  call    NtOfsCreateAttributeEx
0x140054982  test    eax, eax
0x140054984  js      loc_140054C93
0x14005498a  mov     [rsp+148h+var_90], r14
0x140054992  mov     rcx, [rsp+148h+var_100]
0x140054997  call    NtOfsQueryLength
0x14005499c  mov     r12, rax
0x14005499f  mov     [rsp+148h+var_90], rax
0x1400549a7  test    rax, rax
0x1400549aa  jns     short loc_1400549DA
0x1400549ac  mov     edx, 6
0x1400549b1  mov     r9d, 0C0000001h
0x1400549b7  mov     r8d, 137h
0x1400549bd  call    EfspTraceLogAssert
0x1400549c2  mov     rdx, [rsp+148h+var_100]
0x1400549c7  mov     rcx, rdi
0x1400549ca  call    NtOfsCloseAttribute
0x1400549cf  mov     dword ptr [rbx], 1000h
0x1400549d5  jmp     loc_140054C99
0x1400549da  cmp     r12, 20h ; ' '
0x1400549de  jbe     short loc_1400549C2
0x1400549e0  cmp     r12, 40000h
0x1400549e7  jg      short loc_1400549C2
0x1400549e9  mov     [r15], r12d
0x1400549ec  mov     qword ptr [rsp+148h+var_D0+8], r14
0x1400549f4  lea     rax, [rsp+148h+var_E0]
0x1400549f9  mov     qword ptr [rsp+148h+var_120], rax
0x1400549fe  lea     rax, [rsp+148h+Src]
0x140054a03  mov     [rsp+148h+var_128], rax
0x140054a08  mov     r9d, r12d
0x140054a0b  xor     r8d, r8d
0x140054a0e  mov     rdx, [rsp+148h+var_100]
0x140054a13  mov     rcx, rdi
0x140054a16  call    NtOfsMapAttribute
0x140054a1b  lea     r9, [rsp+148h+var_108]
0x140054a20  lea     r8, [rsp+148h+var_F8]
0x140054a25  mov     edx, r12d
0x140054a28  mov     rcx, [rsp+148h+Src]
0x140054a2d  call    EfspGetHeaderType
0x140054a32  test    eax, eax
0x140054a34  jns     short loc_140054A42
0x140054a36  lea     rdx, [rsp+148h+var_E0]
0x140054a3b  call    NtOfsReleaseMap
0x140054a40  jmp     short loc_1400549C2
0x140054a42  cmp     [rsp+148h+var_108], r14b
0x140054a47  jnz     short loc_140054A5B
0x140054a49  mov     eax, [rsp+148h+var_F8]
0x140054a4d  add     eax, 0FFFFFFFEh
0x140054a50  mov     ecx, 1
0x140054a55  cmp     eax, ecx
0x140054a57  cmovbe  r13d, ecx
0x140054a5b  test    rsi, rsi
0x140054a5e  jz      loc_140054C74
0x140054a64  test    r13b, r13b
0x140054a67  jz      short loc_140054A6D
0x140054a69  add     dword ptr [r15], 20h ; ' '
0x140054a6d  mov     edx, [r15]
0x140054a70  mov     ecx, 100h
0x140054a75  mov     r8d, 6D736645h
0x140054a7b  call    cs:__imp_ExAllocatePool2
0x140054a82  nop     dword ptr [rax+rax+00h]
0x140054a87  mov     r14, rax
0x140054a8a  mov     [rsi], rax
0x140054a8d  test    rax, rax
0x140054a90  jnz     short loc_140054AB9
0x140054a92  lea     rdx, [rsp+148h+var_E0]
0x140054a97  call    NtOfsReleaseMap
0x140054a9c  mov     rdx, [rsp+148h+var_100]
0x140054aa1  mov     rcx, rdi
0x140054aa4  call    NtOfsCloseAttribute
0x140054aa9  mov     dword ptr [rbx], 800h
0x140054aaf  mov     ebx, 0C000009Ah
0x140054ab4  jmp     loc_140054C9C
0x140054ab9  mov     [rsp+148h+var_88], r14
0x140054ac1  test    r13b, r13b
0x140054ac4  mov     r13d, 1
0x140054aca  jz      loc_140054B51
0x140054ad0  mov     [rsp+148h+var_120], 20h ; ' '; int
0x140054ad8  lea     rax, [rsp+148h+var_68]
0x140054ae0  mov     [rsp+148h+var_128], rax; __int64
0x140054ae5  mov     r9b, r13b
0x140054ae8  lea     r8d, [r13+5]
0x140054aec  mov     edx, r12d; Size
0x140054aef  mov     rcx, [rsp+148h+Src]; Src
0x140054af4  call    EfspGetSetPFileInfo
0x140054af9  test    eax, eax
0x140054afb  jns     short loc_140054B22
0x140054afd  lea     rdx, [rsp+148h+var_E0]
0x140054b02  call    NtOfsReleaseMap
0x140054b07  mov     rdx, [rsp+148h+var_100]
0x140054b0c  mov     rcx, rdi
0x140054b0f  call    NtOfsCloseAttribute
0x140054b14  mov     dword ptr [rbx], 1000h
0x140054b1a  xor     r14d, r14d
0x140054b1d  jmp     loc_140054C99
0x140054b22  mov     eax, [r15]
0x140054b25  mov     dword ptr [rsp+148h+var_68], eax
0x140054b2c  movups  xmm0, xmmword ptr [rsp+148h+var_68]
0x140054b34  movups  xmmword ptr [r14], xmm0
0x140054b38  movups  xmm1, [rsp+148h+var_58]
0x140054b40  movups  xmmword ptr [r14+10h], xmm1
0x140054b45  add     r14, 20h ; ' '
0x140054b49  mov     [rsp+148h+var_88], r14
0x140054b51  mov     r8d, r12d; Size
0x140054b54  mov     rdx, [rsp+148h+Src]; Src
0x140054b59  mov     rcx, r14; void *
0x140054b5c  call    memmove
0x140054b61  mov     edx, [r15]; Size
0x140054b64  mov     rcx, [rsi]; Src
0x140054b67  cmp     [rcx], edx
0x140054b69  jbe     short loc_140054B86
0x140054b6b  mov     edx, 6
0x140054b70  mov     r9d, 0C000090Bh
0x140054b76  mov     r8d, 1E3h
0x140054b7c  call    EfspTraceLogAssert
0x140054b81  jmp     loc_140054AFD
0x140054b86  mov     eax, [rsp+148h+var_F8]
0x140054b8a  dec     eax
0x140054b8c  xor     r14d, r14d
0x140054b8f  cmp     eax, r13d
0x140054b92  ja      loc_140054C74
0x140054b98  cmp     [rsp+148h+var_107], r14b
0x140054b9d  jz      loc_140054C74
0x140054ba3  lea     r12d, [r14+8]
0x140054ba7  mov     dword ptr [rsp+148h+var_128], r12d; int
0x140054bac  lea     r9, [rsp+148h+var_F0]
0x140054bb1  lea     r8d, [r14+0Bh]
0x140054bb5  call    EfsGetEfsStreamInfo
0x140054bba  test    eax, eax
0x140054bbc  js      loc_140054A36
0x140054bc2  cmp     dword ptr [rsp+148h+var_F0], r13d
0x140054bc7  jnz     loc_140054C74
0x140054bcd  test    byte ptr [rsp+148h+var_F0+4], 3
0x140054bd2  jz      loc_140054C74
0x140054bd8  mov     dword ptr [rsp+148h+var_F0], r14d
0x140054bdd  mov     byte ptr [rsp+148h+var_F0+4], r14b
0x140054be2  mov     dword ptr [rsp+148h+var_128], r12d; int
0x140054be7  lea     r9, [rsp+148h+var_F0]
0x140054bec  lea     r8d, [r14+0Bh]
0x140054bf0  mov     edx, [r15]; Size
0x140054bf3  mov     rcx, [rsi]; Src
0x140054bf6  call    EfsSetEfsStreamInfo
0x140054bfb  test    eax, eax
0x140054bfd  js      loc_140054A36
0x140054c03  xorps   xmm0, xmm0
0x140054c06  movdqu  [rsp+148h+var_C0+8], xmm0
0x140054c0f  mov     dword ptr [rsp+148h+var_B0+8], r14d
0x140054c17  or      dword ptr [rsp+148h+var_C0], r13d
0x140054c1f  mov     dword ptr [rsp+148h+var_128], 30h ; '0'; int
0x140054c27  lea     r9, [rsp+148h+var_C0]
0x140054c2f  lea     r8d, [r14+0Ah]
0x140054c33  mov     edx, [r15]; Size
0x140054c36  mov     rcx, [rsi]; Src
0x140054c39  call    EfsSetEfsStreamInfo
0x140054c3e  test    eax, eax
0x140054c40  js      loc_140054A36
0x140054c46  xor     edx, edx; Tag
0x140054c48  mov     rcx, [rsi]; P
0x140054c4b  call    cs:__imp_ExFreePoolWithTag
0x140054c52  nop     dword ptr [rax+rax+00h]
0x140054c57  mov     rax, [rsp+148h+P]
0x140054c5f  mov     [rsi], rax
0x140054c62  mov     [rsp+148h+P], r14
0x140054c6a  mov     eax, dword ptr [rsp+148h+P+8]
0x140054c71  mov     [r15], eax
0x140054c74  lea     rdx, [rsp+148h+var_E0]
0x140054c79  call    NtOfsReleaseMap
0x140054c7e  mov     rdx, [rsp+148h+var_100]
0x140054c83  mov     rcx, rdi
0x140054c86  call    NtOfsCloseAttribute
0x140054c8b  mov     dword ptr [rbx], 10000h
0x140054c91  jmp     short loc_140054C99
0x140054c93  mov     dword ptr [rbx], 200h
0x140054c99  mov     ebx, r14d
0x140054c9c  mov     rcx, [rsp+148h+P]; P
0x140054ca4  test    rcx, rcx
0x140054ca7  jz      short loc_140054CB7
0x140054ca9  xor     edx, edx; Tag
0x140054cab  call    cs:__imp_ExFreePoolWithTag
0x140054cb2  nop     dword ptr [rax+rax+00h]
0x140054cb7  mov     eax, ebx
0x140054cb9  mov     rcx, [rsp+148h+var_48]
0x140054cc1  xor     rcx, rsp; StackCookie
0x140054cc4  call    __security_check_cookie
0x140054cc9  add     rsp, 110h
0x140054cd0  pop     r15
0x140054cd2  pop     r14
0x140054cd4  pop     r13
0x140054cd6  pop     r12
0x140054cd8  pop     rdi
0x140054cd9  pop     rsi
0x140054cda  pop     rbx
0x140054cdb  retn
0x1400605f6  push    rbx
0x1400605f8  push    rbp
0x1400605f9  push    rdi
0x1400605fa  sub     rsp, 40h
0x1400605fe  mov     rbp, rdx
0x140060601  movzx   eax, cl
0x140060604  test    cl, cl
0x140060606  jz      short loc_140060687
0x140060608  mov     rax, [rbp+0C8h]
0x14006060f  mov     dword ptr [rax], 2000h
0x140060615  mov     rdi, [rbp+0D0h]
0x14006061c  mov     eax, [rdi+48h]
0x14006061f  cmp     eax, 0C0000010h
0x140060624  jnz     short loc_14006063A
0x140060626  mov     edx, 6
0x14006062b  mov     r9d, eax
0x14006062e  mov     r8d, 261h
0x140060634  call    EfspTraceLogAssert
0x140060639  nop
0x14006063a  mov     rbx, [rbp+0D8h]
0x140060641  test    rbx, rbx
0x140060644  jz      short loc_140060664
0x140060646  cmp     qword ptr [rbx], 0
0x14006064a  jz      short loc_140060664
0x14006064c  xor     edx, edx; Tag
0x14006064e  mov     rcx, [rbx]; P
0x140060651  call    cs:__imp_ExFreePoolWithTag
0x140060658  nop     dword ptr [rax+rax+00h]
0x14006065d  mov     qword ptr [rbx], 0
0x140060664  cmp     qword ptr [rbp+60h], 0
0x140060669  jz      short loc_140060675
0x14006066b  lea     rdx, [rbp+68h]
0x14006066f  call    NtOfsReleaseMap
0x140060674  nop
0x140060675  mov     rdx, [rbp+48h]
0x140060679  test    rdx, rdx
0x14006067c  jz      short loc_140060687
0x14006067e  mov     rcx, rdi
0x140060681  call    NtOfsCloseAttribute
0x140060686  nop
0x140060687  mov     rcx, [rbp+0A8h]; P
0x14006068e  test    rcx, rcx
0x140060691  jz      short loc_1400606A2
0x140060693  xor     edx, edx; Tag
0x140060695  call    cs:__imp_ExFreePoolWithTag
0x14006069c  nop     dword ptr [rax+rax+00h]
0x1400606a1  nop
0x1400606a2  add     rsp, 40h
0x1400606a6  pop     rdi
0x1400606a7  pop     rbp
0x1400606a8  pop     rbx
0x1400606a9  retn
```
