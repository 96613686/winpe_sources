# RtlpProbeAssemblyStorageRootForAssembly

- ea: `0x1800d11b4`
- end: `0x1800d1642`
- name: `RtlpProbeAssemblyStorageRootForAssembly`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800d0560`

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001c520`
- `0x18001d490`
- `0x180021fd0`
- `0x18002a5b0`
- `0x180079050`
- `0x1800d11b4`
- `0x18015ecc0`
- `0x18015f140`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x1800d1355`: `SXS: Attempt to translate DOS path name "%S" to NT format failed\n`
- `0x1800d1553`: `SXS: Unable to open assembly directory under storage root "%S"; Status = 0x%08lx\n`
- `0x1800d1569`: `SXS: Assembly storage resolution failing probe because combined path length does not fit in an UNICODE_STRING.\n`
- `0x1800d1609`: `SXS: %s() bad parameters\nSXS:  Flags:               0x%lx\nSXS:  Root:                %p\nSXS:  AssemblyDirectory:   %p\nSXS:  PreAllocatedString:  %p\nSXS:  DynamicString:       %p\nSXS:  StringUsed:          %p\nSXS:  OpenDirectoryHandle: %p\n`
- `0x1800d1514`: `SXS: Assembly storage resolution failing probe because attempt to allocate %u bytes failed.\n`

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
0x1800d11b4  mov     [rsp-8+arg_0], rbx
0x1800d11b9  push    rbp
0x1800d11ba  push    rsi
0x1800d11bb  push    rdi
0x1800d11bc  push    r12
0x1800d11be  push    r13
0x1800d11c0  push    r14
0x1800d11c2  push    r15
0x1800d11c4  lea     rbp, [rsp-230h]
0x1800d11cc  sub     rsp, 330h
0x1800d11d3  mov     rax, cs:__security_cookie
0x1800d11da  xor     rax, rsp
0x1800d11dd  mov     [rbp+260h+var_40], rax
0x1800d11e4  mov     rax, [rbp+260h+arg_28]
0x1800d11eb  xorps   xmm0, xmm0
0x1800d11ee  mov     r13, [rbp+260h+arg_20]
0x1800d11f5  xorps   xmm1, xmm1
0x1800d11f8  mov     r12, [rbp+260h+arg_30]
0x1800d11ff  xor     ecx, ecx
0x1800d1201  mov     qword ptr [rsp+360h+var_2F0], r8
0x1800d1206  mov     r15, r9
0x1800d1209  mov     [rbp+260h+var_2B0], rax
0x1800d120d  mov     rdi, rdx
0x1800d1210  mov     [rsp+360h+FileHandle], rcx
0x1800d1215  movups  [rbp+260h+var_2A8], xmm0
0x1800d1219  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm1
0x1800d121d  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm1
0x1800d1221  movups  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800d1225  movups  xmmword ptr [rbp+260h+IoStatusBlock.___u0], xmm0
0x1800d1229  movups  [rbp+260h+var_2E0], xmm1
0x1800d122d  movups  [rbp+260h+var_2D0], xmm0
0x1800d1231  movups  [rbp+260h+var_2C0], xmm0
0x1800d1235  test    rax, rax
0x1800d1238  jz      short loc_1800D123D
0x1800d123a  mov     [rax], rcx
0x1800d123d  test    r12, r12
0x1800d1240  jz      short loc_1800D1246
0x1800d1242  mov     [r12], rcx
0x1800d1246  test    rdi, rdi
0x1800d1249  jz      loc_1800D15E7
0x1800d124f  test    r8, r8
0x1800d1252  jz      loc_1800D15E7
0x1800d1258  test    r15, r15
0x1800d125b  jz      loc_1800D15E7
0x1800d1261  test    r13, r13
0x1800d1264  jz      loc_1800D15E7
0x1800d126a  test    rax, rax
0x1800d126d  jz      loc_1800D15E7
0x1800d1273  test    r12, r12
0x1800d1276  jz      loc_1800D15E7
0x1800d127c  movzx   edx, word ptr [rdx]
0x1800d127f  mov     r9d, 5Ch ; '\'
0x1800d1285  mov     [rsp+360h+var_300], cl
0x1800d1289  test    dx, dx
0x1800d128c  jnz     loc_1800D14A7
0x1800d1292  movzx   r14d, word ptr [r8]
0x1800d1296  add     r14, 4
0x1800d129a  add     r14, rdx
0x1800d129d  cmp     r14, 0FFFEh
0x1800d12a4  ja      loc_1800D1567
0x1800d12aa  cmp     r14, 208h
0x1800d12b1  ja      loc_1800D14FA
0x1800d12b7  lea     rbx, [rbp+260h+Src]
0x1800d12bb  movzx   r8d, word ptr [rdi]; Size
0x1800d12bf  mov     rcx, rbx; void *
0x1800d12c2  mov     rdx, [rdi+8]; Src
0x1800d12c6  call    memmove
0x1800d12cb  movzx   esi, word ptr [rdi]
0x1800d12ce  add     rsi, rbx
0x1800d12d1  cmp     [rsp+360h+var_300], 0
0x1800d12d6  jnz     loc_1800D1586
0x1800d12dc  mov     rax, qword ptr [rsp+360h+var_2F0]
0x1800d12e1  mov     rcx, rsi; void *
0x1800d12e4  movzx   r8d, word ptr [rax]; Size
0x1800d12e8  mov     rdx, [rax+8]; Src
0x1800d12ec  call    memmove
0x1800d12f1  mov     rdx, qword ptr [rsp+360h+var_2F0]
0x1800d12f6  xor     eax, eax
0x1800d12f8  xorps   xmm0, xmm0
0x1800d12fb  movups  [rsp+360h+var_2F0], xmm0
0x1800d1300  movzx   ecx, word ptr [rdx]
0x1800d1303  mov     [rcx+rsi], ax
0x1800d1307  lea     rcx, [rsp+360h+var_2F0]
0x1800d130c  movzx   esi, [rsp+360h+var_300]
0x1800d1311  add     si, si
0x1800d1314  add     si, [rdx]
0x1800d1317  mov     rdx, rbx
0x1800d131a  add     si, [rdi]
0x1800d131d  call    RtlInitUnicodeStringEx
0x1800d1322  xor     edi, edi
0x1800d1324  test    eax, eax
0x1800d1326  js      short loc_1800D1353
0x1800d1328  lea     rax, [rbp+260h+var_2D0]
0x1800d132c  xor     r8d, r8d
0x1800d132f  mov     [rsp+360h+var_330], rax
0x1800d1334  lea     r9, [rbp+260h+var_2E0]
0x1800d1338  mov     qword ptr [rsp+360h+OpenOptions], rdi
0x1800d133d  lea     rdx, [rsp+360h+var_2F0]
0x1800d1342  lea     ecx, [rdi+2]
0x1800d1345  mov     qword ptr [rsp+360h+ShareAccess], rdi
0x1800d134a  call    RtlpDosPathNameToRelativeNtPathName
0x1800d134f  test    eax, eax
0x1800d1351  jns     short loc_1800D1371
0x1800d1353  xor     edx, edx
0x1800d1355  lea     r8, aSxsAttemptToTr; "SXS: Attempt to translate DOS path name"...
0x1800d135c  mov     r9, rbx
0x1800d135f  lea     ecx, [rdx+33h]
0x1800d1362  call    DbgPrintEx
0x1800d1367  mov     edi, 0C000003Ah
0x1800d136c  jmp     loc_1800D145A
0x1800d1371  mov     rax, qword ptr [rbp+260h+var_2E0+8]
0x1800d1375  mov     qword ptr [rsp+360h+var_2F0], rax
0x1800d137a  movzx   eax, word ptr [rbp+260h+var_2D0]
0x1800d137e  test    ax, ax
0x1800d1381  jnz     loc_1800D14D7
0x1800d1387  mov     rax, rdi
0x1800d138a  mov     qword ptr [rbp+260h+var_2C0], rax
0x1800d138e  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x1800d1392  lea     r9, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x1800d1396  lea     rax, [rbp+260h+var_2E0]
0x1800d139a  mov     [rsp+360h+OpenOptions], 21h ; '!'; OpenOptions
0x1800d13a2  xorps   xmm0, xmm0
0x1800d13a5  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1800d13a9  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1800d13ad  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1800d13b4  mov     edx, 100020h; DesiredAccess
0x1800d13b9  mov     [rbp+260h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d13c0  lea     rcx, [rsp+360h+FileHandle]; FileHandle
0x1800d13c5  mov     [rsp+360h+ShareAccess], 3; ShareAccess
0x1800d13cd  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d13d2  call    NtOpenFile
0x1800d13d7  lea     rcx, [rbp+260h+var_2D0]
0x1800d13db  mov     edi, eax
0x1800d13dd  call    RtlReleaseRelativeName
0x1800d13e2  xor     ecx, ecx
0x1800d13e4  test    edi, edi
0x1800d13e6  js      loc_1800D152F
0x1800d13ec  movzx   eax, word ptr [r15+2]
0x1800d13f1  cmp     r14, rax
0x1800d13f4  ja      loc_1800D159E
0x1800d13fa  mov     rcx, [r15+8]; void *
0x1800d13fe  mov     rdx, rbx; Src
0x1800d1401  movzx   r8d, si; Size
0x1800d1405  call    memmove
0x1800d140a  mov     r9, [rbp+260h+var_2B0]
0x1800d140e  xor     edi, edi
0x1800d1410  movzx   edx, si
0x1800d1413  add     si, 2
0x1800d1417  mov     [r9], r15
0x1800d141a  mov     rcx, [r15+8]
0x1800d141e  mov     dword ptr [rcx+rdx], 5Ch ; '\'
0x1800d1425  mov     rax, [r9]
0x1800d1428  mov     [rax], si
0x1800d142b  mov     rax, [rsp+360h+FileHandle]
0x1800d1430  mov     [r12], rax
0x1800d1434  mov     [rsp+360h+FileHandle], rdi
0x1800d1439  mov     rax, qword ptr [rsp+360h+var_2F0]
0x1800d143e  test    rax, rax
0x1800d1441  jz      short loc_1800D145A
0x1800d1443  mov     rcx, gs:60h
0x1800d144c  mov     r8, rax
0x1800d144f  xor     edx, edx
0x1800d1451  mov     rcx, [rcx+30h]
0x1800d1455  call    RtlFreeHeap_0
0x1800d145a  test    rbx, rbx
0x1800d145d  jz      short loc_1800D146C
0x1800d145f  lea     rax, [rbp+260h+Src]
0x1800d1463  cmp     rbx, rax
0x1800d1466  jnz     loc_1800D162B
0x1800d146c  mov     rcx, [rsp+360h+FileHandle]; Handle
0x1800d1471  test    rcx, rcx
0x1800d1474  jnz     loc_1800D1638
0x1800d147a  mov     eax, edi
0x1800d147c  mov     rcx, [rbp+260h+var_40]
0x1800d1483  xor     rcx, rsp; StackCookie
0x1800d1486  call    __security_check_cookie
0x1800d148b  mov     rbx, [rsp+360h+arg_0]
0x1800d1493  add     rsp, 330h
0x1800d149a  pop     r15
0x1800d149c  pop     r14
0x1800d149e  pop     r13
0x1800d14a0  pop     r12
0x1800d14a2  pop     rdi
0x1800d14a3  pop     rsi
0x1800d14a4  pop     rbp
0x1800d14a5  retn
0x1800d14a7  mov     rax, [rdi+8]
0x1800d14ab  mov     rcx, rdx
0x1800d14ae  shr     rcx, 1
0x1800d14b1  cmp     [rax+rcx*2-2], r9w
0x1800d14b7  jz      loc_1800D1292
0x1800d14bd  cmp     word ptr [rax+rcx*2-2], 2Fh ; '/'
0x1800d14c3  jz      loc_1800D1292
0x1800d14c9  mov     [rsp+360h+var_300], 1
0x1800d14ce  add     rdx, 2
0x1800d14d2  jmp     loc_1800D1292
0x1800d14d7  mov     word ptr [rbp+260h+var_2E0], ax
0x1800d14db  mov     eax, dword ptr [rbp+260h+var_2D0+2]
0x1800d14de  mov     dword ptr [rbp+260h+var_2E0+2], eax
0x1800d14e1  movzx   eax, word ptr [rbp+260h+var_2D0+6]
0x1800d14e5  mov     word ptr [rbp+260h+var_2E0+6], ax
0x1800d14e9  mov     rax, qword ptr [rbp+260h+var_2D0+8]
0x1800d14ed  mov     qword ptr [rbp+260h+var_2E0+8], rax
0x1800d14f1  mov     rax, qword ptr [rbp+260h+var_2C0]
0x1800d14f5  jmp     loc_1800D138E
0x1800d14fa  movzx   esi, r14w
0x1800d14fe  mov     ecx, esi
0x1800d1500  call    RtlpAllocateAtom
0x1800d1505  mov     rbx, rax
0x1800d1508  test    rax, rax
0x1800d150b  jnz     loc_1800D12BB
0x1800d1511  mov     r9d, esi
0x1800d1514  lea     r8, aSxsAssemblySto; "SXS: Assembly storage resolution failin"...
0x1800d151b  xor     edx, edx
0x1800d151d  lea     ecx, [rax+33h]
0x1800d1520  call    DbgPrintEx
0x1800d1525  mov     edi, 0C0000017h
0x1800d152a  jmp     loc_1800D145A
0x1800d152f  lea     eax, [rdi+3FFFFFF1h]
0x1800d1535  cmp     eax, 2Bh ; '+'
0x1800d1538  ja      short loc_1800D154A
0x1800d153a  mov     rcx, 82000000001h
0x1800d1544  bt      rcx, rax
0x1800d1548  jb      short loc_1800D1594
0x1800d154a  xor     edx, edx
0x1800d154c  mov     [rsp+360h+ShareAccess], edi
0x1800d1550  mov     r9, rbx
0x1800d1553  lea     r8, aSxsUnableToOpe_0; "SXS: Unable to open assembly directory "...
0x1800d155a  lea     ecx, [rdx+33h]
0x1800d155d  call    DbgPrintEx
0x1800d1562  jmp     loc_1800D1439
0x1800d1567  xor     edx, edx
0x1800d1569  lea     r8, aSxsAssemblySto_3; "SXS: Assembly storage resolution failin"...
0x1800d1570  lea     ecx, [rdx+33h]
0x1800d1573  call    DbgPrintEx
0x1800d1578  mov     edi, 0C0000106h
0x1800d157d  mov     rbx, qword ptr [rbp+260h+var_2A8+8]
0x1800d1581  jmp     loc_1800D145A
0x1800d1586  mov     word ptr [rsi], 5Ch ; '\'
0x1800d158b  add     rsi, 2
0x1800d158f  jmp     loc_1800D12DC
0x1800d1594  mov     edi, 0C0150004h
0x1800d1599  jmp     loc_1800D1439
0x1800d159e  lea     rax, [rbp+260h+Src]
0x1800d15a2  cmp     rbx, rax
0x1800d15a5  jz      short loc_1800D15B0
0x1800d15a7  mov     [r13+8], rbx
0x1800d15ab  mov     rbx, rcx
0x1800d15ae  jmp     short loc_1800D15DA
0x1800d15b0  mov     rcx, r14
0x1800d15b3  call    RtlpAllocateAtom
0x1800d15b8  mov     [r13+8], rax
0x1800d15bc  test    rax, rax
0x1800d15bf  jnz     short loc_1800D15CB
0x1800d15c1  mov     edi, 0C0000017h
0x1800d15c6  jmp     loc_1800D1439
0x1800d15cb  movzx   r8d, si; Size
0x1800d15cf  mov     rdx, rbx; Src
0x1800d15d2  mov     rcx, rax; void *
0x1800d15d5  call    memmove
0x1800d15da  mov     [r13+2], r14w
0x1800d15df  mov     r15, r13
0x1800d15e2  jmp     loc_1800D140A
0x1800d15e7  mov     [rsp+360h+var_310], r12
0x1800d15ec  lea     r9, aRtlpprobeassem; "RtlpProbeAssemblyStorageRootForAssembly"
0x1800d15f3  mov     [rsp+360h+var_318], rax
0x1800d15f8  xor     edx, edx
0x1800d15fa  mov     [rsp+360h+var_320], r13
0x1800d15ff  mov     [rsp+360h+var_328], r15
0x1800d1604  mov     [rsp+360h+var_330], r8
0x1800d1609  lea     r8, aSxsSBadParamet_4; "SXS: %s() bad parameters\nSXS:  Flags: "...
0x1800d1610  mov     qword ptr [rsp+360h+OpenOptions], rdi
0x1800d1615  mov     [rsp+360h+ShareAccess], ecx
0x1800d1619  lea     ecx, [rdx+33h]
0x1800d161c  call    DbgPrintEx
0x1800d1621  mov     edi, 0C000000Dh
0x1800d1626  jmp     loc_1800D157D
0x1800d162b  mov     rcx, rbx
0x1800d162e  call    RtlpSysVolFree
0x1800d1633  jmp     loc_1800D146C
0x1800d1638  call    NtClose
0x1800d163d  jmp     loc_1800D147A
```
