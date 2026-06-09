# RtlpProbeAssemblyStorageRootForAssembly

- ea: `0x1800cfa84`
- end: `0x1800cff12`
- name: `RtlpProbeAssemblyStorageRootForAssembly`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800cee30`

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001c520`
- `0x18001d490`
- `0x180021fe0`
- `0x18002b2a0`
- `0x18005c670`
- `0x1800cfa84`
- `0x18015e4b0`
- `0x18015e930`
- `0x180162000`
- `0x180163a80`

## string_xrefs

- `0x1800cfc25`: `SXS: Attempt to translate DOS path name "%S" to NT format failed\n`
- `0x1800cfe23`: `SXS: Unable to open assembly directory under storage root "%S"; Status = 0x%08lx\n`
- `0x1800cfe39`: `SXS: Assembly storage resolution failing probe because combined path length does not fit in an UNICODE_STRING.\n`
- `0x1800cfed9`: `SXS: %s() bad parameters\nSXS:  Flags:               0x%lx\nSXS:  Root:                %p\nSXS:  AssemblyDirectory:   %p\nSXS:  PreAllocatedString:  %p\nSXS:  DynamicString:       %p\nSXS:  StringUsed:          %p\nSXS:  OpenDirectoryHandle: %p\n`
- `0x1800cfde4`: `SXS: Assembly storage resolution failing probe because attempt to allocate %u bytes failed.\n`

## pseudocode

```c
__int64 __fastcall RtlpProbeAssemblyStorageRootForAssembly(
        __int64 a1,
        const void **a2,
        unsigned __int16 *a3,
        const void *a4,
        __int64 a5,
        __int64 *a6,
        HANDLE *a7)
{
  __int64 v7; // r15
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r14
  _BYTE *Atom; // rbx
  _WORD *v12; // rsi
  _WORD *v13; // rdx
  unsigned __int16 v14; // si
  NTSTATUS v15; // edi
  void *v16; // rax
  __int64 *v17; // r9
  _WORD *v19; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  void *v22; // rax
  unsigned __int8 v23; // [rsp+60h] [rbp-A0h]
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  __int128 v26; // [rsp+80h] [rbp-80h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int64 *v29; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+B8h] [rbp-48h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE Src[528]; // [rsp+110h] [rbp+10h] BYREF

  *(_QWORD *)&v25 = a3;
  v7 = (__int64)a4;
  v29 = a6;
  FileHandle = 0;
  v30 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: %s() bad parameters\n"
      "SXS:  Flags:               0x%lx\n"
      "SXS:  Root:                %p\n"
      "SXS:  AssemblyDirectory:   %p\n"
      "SXS:  PreAllocatedString:  %p\n"
      "SXS:  DynamicString:       %p\n"
      "SXS:  StringUsed:          %p\n"
      "SXS:  OpenDirectoryHandle: %p\n",
      "RtlpProbeAssemblyStorageRootForAssembly",
      0,
      a2,
      a3,
      a4,
      (const void *)a5,
      a6,
      a7);
    v15 = -1073741811;
    goto LABEL_44;
  }
  v9 = *(unsigned __int16 *)a2;
  v23 = 0;
  if ( (_WORD)v9 )
  {
    v19 = a2[1];
    if ( v19[(v9 >> 1) - 1] != 92 && v19[(v9 >> 1) - 1] != 47 )
    {
      v23 = 1;
      v9 += 2LL;
    }
  }
  v10 = v9 + *a3 + 4LL;
  if ( v10 > 0xFFFE )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: Assembly storage resolution failing probe because combined path length does not fit in an UNICODE_STRING.\n",
      92);
    v15 = -1073741562;
LABEL_44:
    Atom = (_BYTE *)*((_QWORD *)&v30 + 1);
    goto LABEL_28;
  }
  if ( v10 > 0x208 )
  {
    Atom = (_BYTE *)RtlpAllocateAtom((unsigned __int16)v10);
    if ( !Atom )
    {
      DbgPrintEx(
        51,
        0,
        "SXS: Assembly storage resolution failing probe because attempt to allocate %u bytes failed.\n",
        (unsigned __int16)v10);
      v15 = -1073741801;
      goto LABEL_28;
    }
  }
  else
  {
    Atom = Src;
  }
  memmove(Atom, a2[1], *(unsigned __int16 *)a2);
  v12 = &Atom[*(unsigned __int16 *)a2];
  if ( v23 )
    *v12++ = 92;
  memmove(v12, *(const void **)(v25 + 8), *(unsigned __int16 *)v25);
  v13 = (_WORD *)v25;
  v25 = 0;
  *(_WORD *)((char *)v12 + (unsigned __int16)*v13) = 0;
  v14 = *(_WORD *)a2 + *v13 + 2 * v23;
  if ( (int)RtlInitUnicodeStringEx(&v25, Atom) < 0
    || (int)RtlpDosPathNameToRelativeNtPathName(2, (unsigned int)&v25, 0, (unsigned int)&v26, 0, 0, (__int64)&v27) < 0 )
  {
    DbgPrintEx(51, 0, "SXS: Attempt to translate DOS path name \"%S\" to NT format failed\n", (const wchar_t *)Atom);
    v15 = -1073741766;
    goto LABEL_28;
  }
  *(_QWORD *)&v25 = *((_QWORD *)&v26 + 1);
  if ( (_WORD)v27 )
  {
    v26 = v27;
    v16 = (void *)v28;
  }
  else
  {
    v16 = 0;
    *(_QWORD *)&v28 = 0;
  }
  ObjectAttributes.RootDirectory = v16;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v26;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = NtOpenFile(&FileHandle, 0x100020u, &ObjectAttributes, &IoStatusBlock, 3u, 0x21u);
  RtlReleaseRelativeName(&v27);
  if ( v15 < 0 )
  {
    v20 = (unsigned int)(v15 + 1073741809);
    if ( (unsigned int)v20 <= 0x2B && (v21 = 0x82000000001LL, _bittest64(&v21, v20)) )
      v15 = -1072365564;
    else
      DbgPrintEx(
        51,
        0,
        "SXS: Unable to open assembly directory under storage root \"%S\"; Status = 0x%08lx\n",
        (const wchar_t *)Atom,
        v15);
  }
  else
  {
    if ( v10 <= *(unsigned __int16 *)(v7 + 2) )
    {
      memmove(*(void **)(v7 + 8), Atom, v14);
LABEL_25:
      v17 = v29;
      v15 = 0;
      *v29 = v7;
      *(_DWORD *)(*(_QWORD *)(v7 + 8) + v14) = 92;
      *(_WORD *)*v17 = v14 + 2;
      *a7 = FileHandle;
      FileHandle = 0;
      goto LABEL_26;
    }
    if ( Atom != Src )
    {
      *(_QWORD *)(a5 + 8) = Atom;
      Atom = 0;
LABEL_51:
      *(_WORD *)(a5 + 2) = v10;
      v7 = a5;
      goto LABEL_25;
    }
    v22 = (void *)RtlpAllocateAtom(v10);
    *(_QWORD *)(a5 + 8) = v22;
    if ( v22 )
    {
      memmove(v22, Atom, v14);
      goto LABEL_51;
    }
    v15 = -1073741801;
  }
LABEL_26:
  if ( (_QWORD)v25 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v25);
LABEL_28:
  if ( Atom && Atom != Src )
    RtlpSysVolFree(Atom);
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800cfa84  mov     [rsp-8+arg_0], rbx
0x1800cfa89  push    rbp
0x1800cfa8a  push    rsi
0x1800cfa8b  push    rdi
0x1800cfa8c  push    r12
0x1800cfa8e  push    r13
0x1800cfa90  push    r14
0x1800cfa92  push    r15
0x1800cfa94  lea     rbp, [rsp-230h]
0x1800cfa9c  sub     rsp, 330h
0x1800cfaa3  mov     rax, cs:__security_cookie
0x1800cfaaa  xor     rax, rsp
0x1800cfaad  mov     [rbp+260h+var_40], rax
0x1800cfab4  mov     rax, [rbp+260h+arg_28]
0x1800cfabb  xorps   xmm0, xmm0
0x1800cfabe  mov     r13, [rbp+260h+arg_20]
0x1800cfac5  xorps   xmm1, xmm1
0x1800cfac8  mov     r12, [rbp+260h+arg_30]
0x1800cfacf  xor     ecx, ecx
0x1800cfad1  mov     qword ptr [rsp+360h+var_2F0], r8
0x1800cfad6  mov     r15, r9
0x1800cfad9  mov     [rbp+260h+var_2B0], rax
0x1800cfadd  mov     rdi, rdx
0x1800cfae0  mov     [rsp+360h+FileHandle], rcx
0x1800cfae5  movups  [rbp+260h+var_2A8], xmm0
0x1800cfae9  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm1
0x1800cfaed  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm1
0x1800cfaf1  movups  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800cfaf5  movups  xmmword ptr [rbp+260h+IoStatusBlock.___u0], xmm0
0x1800cfaf9  movups  [rbp+260h+var_2E0], xmm1
0x1800cfafd  movups  [rbp+260h+var_2D0], xmm0
0x1800cfb01  movups  [rbp+260h+var_2C0], xmm0
0x1800cfb05  test    rax, rax
0x1800cfb08  jz      short loc_1800CFB0D
0x1800cfb0a  mov     [rax], rcx
0x1800cfb0d  test    r12, r12
0x1800cfb10  jz      short loc_1800CFB16
0x1800cfb12  mov     [r12], rcx
0x1800cfb16  test    rdi, rdi
0x1800cfb19  jz      loc_1800CFEB7
0x1800cfb1f  test    r8, r8
0x1800cfb22  jz      loc_1800CFEB7
0x1800cfb28  test    r15, r15
0x1800cfb2b  jz      loc_1800CFEB7
0x1800cfb31  test    r13, r13
0x1800cfb34  jz      loc_1800CFEB7
0x1800cfb3a  test    rax, rax
0x1800cfb3d  jz      loc_1800CFEB7
0x1800cfb43  test    r12, r12
0x1800cfb46  jz      loc_1800CFEB7
0x1800cfb4c  movzx   edx, word ptr [rdx]
0x1800cfb4f  mov     r9d, 5Ch ; '\'
0x1800cfb55  mov     [rsp+360h+var_300], cl
0x1800cfb59  test    dx, dx
0x1800cfb5c  jnz     loc_1800CFD77
0x1800cfb62  movzx   r14d, word ptr [r8]
0x1800cfb66  add     r14, 4
0x1800cfb6a  add     r14, rdx
0x1800cfb6d  cmp     r14, 0FFFEh
0x1800cfb74  ja      loc_1800CFE37
0x1800cfb7a  cmp     r14, 208h
0x1800cfb81  ja      loc_1800CFDCA
0x1800cfb87  lea     rbx, [rbp+260h+Src]
0x1800cfb8b  movzx   r8d, word ptr [rdi]; Size
0x1800cfb8f  mov     rcx, rbx; void *
0x1800cfb92  mov     rdx, [rdi+8]; Src
0x1800cfb96  call    memmove
0x1800cfb9b  movzx   esi, word ptr [rdi]
0x1800cfb9e  add     rsi, rbx
0x1800cfba1  cmp     [rsp+360h+var_300], 0
0x1800cfba6  jnz     loc_1800CFE56
0x1800cfbac  mov     rax, qword ptr [rsp+360h+var_2F0]
0x1800cfbb1  mov     rcx, rsi; void *
0x1800cfbb4  movzx   r8d, word ptr [rax]; Size
0x1800cfbb8  mov     rdx, [rax+8]; Src
0x1800cfbbc  call    memmove
0x1800cfbc1  mov     rdx, qword ptr [rsp+360h+var_2F0]
0x1800cfbc6  xor     eax, eax
0x1800cfbc8  xorps   xmm0, xmm0
0x1800cfbcb  movups  [rsp+360h+var_2F0], xmm0
0x1800cfbd0  movzx   ecx, word ptr [rdx]
0x1800cfbd3  mov     [rcx+rsi], ax
0x1800cfbd7  lea     rcx, [rsp+360h+var_2F0]
0x1800cfbdc  movzx   esi, [rsp+360h+var_300]
0x1800cfbe1  add     si, si
0x1800cfbe4  add     si, [rdx]
0x1800cfbe7  mov     rdx, rbx
0x1800cfbea  add     si, [rdi]
0x1800cfbed  call    RtlInitUnicodeStringEx
0x1800cfbf2  xor     edi, edi
0x1800cfbf4  test    eax, eax
0x1800cfbf6  js      short loc_1800CFC23
0x1800cfbf8  lea     rax, [rbp+260h+var_2D0]
0x1800cfbfc  xor     r8d, r8d
0x1800cfbff  mov     [rsp+360h+var_330], rax
0x1800cfc04  lea     r9, [rbp+260h+var_2E0]
0x1800cfc08  mov     qword ptr [rsp+360h+OpenOptions], rdi
0x1800cfc0d  lea     rdx, [rsp+360h+var_2F0]
0x1800cfc12  lea     ecx, [rdi+2]
0x1800cfc15  mov     qword ptr [rsp+360h+ShareAccess], rdi
0x1800cfc1a  call    RtlpDosPathNameToRelativeNtPathName
0x1800cfc1f  test    eax, eax
0x1800cfc21  jns     short loc_1800CFC41
0x1800cfc23  xor     edx, edx
0x1800cfc25  lea     r8, aSxsAttemptToTr; "SXS: Attempt to translate DOS path name"...
0x1800cfc2c  mov     r9, rbx
0x1800cfc2f  lea     ecx, [rdx+33h]
0x1800cfc32  call    DbgPrintEx
0x1800cfc37  mov     edi, 0C000003Ah
0x1800cfc3c  jmp     loc_1800CFD2A
0x1800cfc41  mov     rax, qword ptr [rbp+260h+var_2E0+8]
0x1800cfc45  mov     qword ptr [rsp+360h+var_2F0], rax
0x1800cfc4a  movzx   eax, word ptr [rbp+260h+var_2D0]
0x1800cfc4e  test    ax, ax
0x1800cfc51  jnz     loc_1800CFDA7
0x1800cfc57  mov     rax, rdi
0x1800cfc5a  mov     qword ptr [rbp+260h+var_2C0], rax
0x1800cfc5e  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x1800cfc62  lea     r9, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x1800cfc66  lea     rax, [rbp+260h+var_2E0]
0x1800cfc6a  mov     [rsp+360h+OpenOptions], 21h ; '!'; OpenOptions
0x1800cfc72  xorps   xmm0, xmm0
0x1800cfc75  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1800cfc79  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1800cfc7d  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1800cfc84  mov     edx, 100020h; DesiredAccess
0x1800cfc89  mov     [rbp+260h+ObjectAttributes.Attributes], 40h ; '@'
0x1800cfc90  lea     rcx, [rsp+360h+FileHandle]; FileHandle
0x1800cfc95  mov     [rsp+360h+ShareAccess], 3; ShareAccess
0x1800cfc9d  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800cfca2  call    NtOpenFile
0x1800cfca7  lea     rcx, [rbp+260h+var_2D0]
0x1800cfcab  mov     edi, eax
0x1800cfcad  call    RtlReleaseRelativeName
0x1800cfcb2  xor     ecx, ecx
0x1800cfcb4  test    edi, edi
0x1800cfcb6  js      loc_1800CFDFF
0x1800cfcbc  movzx   eax, word ptr [r15+2]
0x1800cfcc1  cmp     r14, rax
0x1800cfcc4  ja      loc_1800CFE6E
0x1800cfcca  mov     rcx, [r15+8]; void *
0x1800cfcce  mov     rdx, rbx; Src
0x1800cfcd1  movzx   r8d, si; Size
0x1800cfcd5  call    memmove
0x1800cfcda  mov     r9, [rbp+260h+var_2B0]
0x1800cfcde  xor     edi, edi
0x1800cfce0  movzx   edx, si
0x1800cfce3  add     si, 2
0x1800cfce7  mov     [r9], r15
0x1800cfcea  mov     rcx, [r15+8]
0x1800cfcee  mov     dword ptr [rcx+rdx], 5Ch ; '\'
0x1800cfcf5  mov     rax, [r9]
0x1800cfcf8  mov     [rax], si
0x1800cfcfb  mov     rax, [rsp+360h+FileHandle]
0x1800cfd00  mov     [r12], rax
0x1800cfd04  mov     [rsp+360h+FileHandle], rdi
0x1800cfd09  mov     rax, qword ptr [rsp+360h+var_2F0]
0x1800cfd0e  test    rax, rax
0x1800cfd11  jz      short loc_1800CFD2A
0x1800cfd13  mov     rcx, gs:60h
0x1800cfd1c  mov     r8, rax
0x1800cfd1f  xor     edx, edx
0x1800cfd21  mov     rcx, [rcx+30h]
0x1800cfd25  call    RtlFreeHeap_0
0x1800cfd2a  test    rbx, rbx
0x1800cfd2d  jz      short loc_1800CFD3C
0x1800cfd2f  lea     rax, [rbp+260h+Src]
0x1800cfd33  cmp     rbx, rax
0x1800cfd36  jnz     loc_1800CFEFB
0x1800cfd3c  mov     rcx, [rsp+360h+FileHandle]; Handle
0x1800cfd41  test    rcx, rcx
0x1800cfd44  jnz     loc_1800CFF08
0x1800cfd4a  mov     eax, edi
0x1800cfd4c  mov     rcx, [rbp+260h+var_40]
0x1800cfd53  xor     rcx, rsp; StackCookie
0x1800cfd56  call    __security_check_cookie
0x1800cfd5b  mov     rbx, [rsp+360h+arg_0]
0x1800cfd63  add     rsp, 330h
0x1800cfd6a  pop     r15
0x1800cfd6c  pop     r14
0x1800cfd6e  pop     r13
0x1800cfd70  pop     r12
0x1800cfd72  pop     rdi
0x1800cfd73  pop     rsi
0x1800cfd74  pop     rbp
0x1800cfd75  retn
0x1800cfd77  mov     rax, [rdi+8]
0x1800cfd7b  mov     rcx, rdx
0x1800cfd7e  shr     rcx, 1
0x1800cfd81  cmp     [rax+rcx*2-2], r9w
0x1800cfd87  jz      loc_1800CFB62
0x1800cfd8d  cmp     word ptr [rax+rcx*2-2], 2Fh ; '/'
0x1800cfd93  jz      loc_1800CFB62
0x1800cfd99  mov     [rsp+360h+var_300], 1
0x1800cfd9e  add     rdx, 2
0x1800cfda2  jmp     loc_1800CFB62
0x1800cfda7  mov     word ptr [rbp+260h+var_2E0], ax
0x1800cfdab  mov     eax, dword ptr [rbp+260h+var_2D0+2]
0x1800cfdae  mov     dword ptr [rbp+260h+var_2E0+2], eax
0x1800cfdb1  movzx   eax, word ptr [rbp+260h+var_2D0+6]
0x1800cfdb5  mov     word ptr [rbp+260h+var_2E0+6], ax
0x1800cfdb9  mov     rax, qword ptr [rbp+260h+var_2D0+8]
0x1800cfdbd  mov     qword ptr [rbp+260h+var_2E0+8], rax
0x1800cfdc1  mov     rax, qword ptr [rbp+260h+var_2C0]
0x1800cfdc5  jmp     loc_1800CFC5E
0x1800cfdca  movzx   esi, r14w
0x1800cfdce  mov     ecx, esi
0x1800cfdd0  call    RtlpAllocateAtom
0x1800cfdd5  mov     rbx, rax
0x1800cfdd8  test    rax, rax
0x1800cfddb  jnz     loc_1800CFB8B
0x1800cfde1  mov     r9d, esi
0x1800cfde4  lea     r8, aSxsAssemblySto; "SXS: Assembly storage resolution failin"...
0x1800cfdeb  xor     edx, edx
0x1800cfded  lea     ecx, [rax+33h]
0x1800cfdf0  call    DbgPrintEx
0x1800cfdf5  mov     edi, 0C0000017h
0x1800cfdfa  jmp     loc_1800CFD2A
0x1800cfdff  lea     eax, [rdi+3FFFFFF1h]
0x1800cfe05  cmp     eax, 2Bh ; '+'
0x1800cfe08  ja      short loc_1800CFE1A
0x1800cfe0a  mov     rcx, 82000000001h
0x1800cfe14  bt      rcx, rax
0x1800cfe18  jb      short loc_1800CFE64
0x1800cfe1a  xor     edx, edx
0x1800cfe1c  mov     [rsp+360h+ShareAccess], edi
0x1800cfe20  mov     r9, rbx
0x1800cfe23  lea     r8, aSxsUnableToOpe_0; "SXS: Unable to open assembly directory "...
0x1800cfe2a  lea     ecx, [rdx+33h]
0x1800cfe2d  call    DbgPrintEx
0x1800cfe32  jmp     loc_1800CFD09
0x1800cfe37  xor     edx, edx
0x1800cfe39  lea     r8, aSxsAssemblySto_3; "SXS: Assembly storage resolution failin"...
0x1800cfe40  lea     ecx, [rdx+33h]
0x1800cfe43  call    DbgPrintEx
0x1800cfe48  mov     edi, 0C0000106h
0x1800cfe4d  mov     rbx, qword ptr [rbp+260h+var_2A8+8]
0x1800cfe51  jmp     loc_1800CFD2A
0x1800cfe56  mov     word ptr [rsi], 5Ch ; '\'
0x1800cfe5b  add     rsi, 2
0x1800cfe5f  jmp     loc_1800CFBAC
0x1800cfe64  mov     edi, 0C0150004h
0x1800cfe69  jmp     loc_1800CFD09
0x1800cfe6e  lea     rax, [rbp+260h+Src]
0x1800cfe72  cmp     rbx, rax
0x1800cfe75  jz      short loc_1800CFE80
0x1800cfe77  mov     [r13+8], rbx
0x1800cfe7b  mov     rbx, rcx
0x1800cfe7e  jmp     short loc_1800CFEAA
0x1800cfe80  mov     rcx, r14
0x1800cfe83  call    RtlpAllocateAtom
0x1800cfe88  mov     [r13+8], rax
0x1800cfe8c  test    rax, rax
0x1800cfe8f  jnz     short loc_1800CFE9B
0x1800cfe91  mov     edi, 0C0000017h
0x1800cfe96  jmp     loc_1800CFD09
0x1800cfe9b  movzx   r8d, si; Size
0x1800cfe9f  mov     rdx, rbx; Src
0x1800cfea2  mov     rcx, rax; void *
0x1800cfea5  call    memmove
0x1800cfeaa  mov     [r13+2], r14w
0x1800cfeaf  mov     r15, r13
0x1800cfeb2  jmp     loc_1800CFCDA
0x1800cfeb7  mov     [rsp+360h+var_310], r12
0x1800cfebc  lea     r9, aRtlpprobeassem; "RtlpProbeAssemblyStorageRootForAssembly"
0x1800cfec3  mov     [rsp+360h+var_318], rax
0x1800cfec8  xor     edx, edx
0x1800cfeca  mov     [rsp+360h+var_320], r13
0x1800cfecf  mov     [rsp+360h+var_328], r15
0x1800cfed4  mov     [rsp+360h+var_330], r8
0x1800cfed9  lea     r8, aSxsSBadParamet_4; "SXS: %s() bad parameters\nSXS:  Flags: "...
0x1800cfee0  mov     qword ptr [rsp+360h+OpenOptions], rdi
0x1800cfee5  mov     [rsp+360h+ShareAccess], ecx
0x1800cfee9  lea     ecx, [rdx+33h]
0x1800cfeec  call    DbgPrintEx
0x1800cfef1  mov     edi, 0C000000Dh
0x1800cfef6  jmp     loc_1800CFE4D
0x1800cfefb  mov     rcx, rbx
0x1800cfefe  call    RtlpSysVolFree
0x1800cff03  jmp     loc_1800CFD3C
0x1800cff08  call    NtClose
0x1800cff0d  jmp     loc_1800CFD4A
```
