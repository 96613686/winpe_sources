# RtlpResolveAssemblyStorageMapEntry

- ea: `0x1800d0560`
- end: `0x1800d0c2c`
- name: `RtlpResolveAssemblyStorageMapEntry`
- size: `1740`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800cfe70`

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001c520`
- `0x18001d490`
- `0x180021fd0`
- `0x18002a5b0`
- `0x180079050`
- `0x1800d0560`
- `0x1800d0c40`
- `0x1800d1024`
- `0x1800d11b4`
- `0x18012d780`
- `0x18015ecc0`
- `0x18015f140`
- `0x180162810`
- `0x180164280`
- `0x18016f030`

## string_xrefs

- `0x1800d09a6`: `SXS: Attempt to translate DOS path name "%S" to NT format failed\n`
- `0x1800d0ad8`: `SXS: Unable to resolve storage root for assembly directory %wZ in %Iu tries\n`
- `0x1800d0b6b`: `SXS: Attempt to probe assembly storage root %wZ for assembly directory %wZ failed with status = 0x%08lx\n`
- `0x1800d0a45`: `SXS: Unable to open assembly directory under storage root "%S"; Status = 0x%08lx\n`
- `0x1800d0bb7`: `SXS: Assembly directory name stored in assembly information too long (%lu bytes) - ACTIVATION_CONTEXT_DATA at %p\n`
- `0x1800d0bfb`: `SXS: Attempt to probe known root of assembly storage ("%wZ") failed; Status = 0x%08lx\n`
- `0x1800d0c18`: `SXS: Attempt to insert well known storage root into assembly storage map assembly roster index %lu failed; Status = 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall RtlpResolveAssemblyStorageMapEntry(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rsi
  __int64 v8; // r12
  int v9; // eax
  NTSTATUS v10; // ebx
  char v11; // r15
  __int64 v13; // r8
  __int64 v14; // rdx
  unsigned int v15; // r9d
  char *v16; // rcx
  const wchar_t *v17; // rdi
  wchar_t *v18; // rax
  unsigned __int64 v19; // rbx
  __int64 *v20; // rcx
  unsigned int *v21; // r13
  int v22; // eax
  __int64 v23; // rax
  int v24; // ecx
  unsigned int *v25; // rax
  unsigned __int64 v26; // r13
  unsigned __int64 v27; // rdi
  bool v28; // zf
  int v29; // ecx
  int v30; // eax
  void *v31; // rax
  int v32; // eax
  int inserted; // eax
  ULONG ShareAccess[2]; // [rsp+20h] [rbp-E0h]
  ULONG OpenOptions[2]; // [rsp+28h] [rbp-D8h]
  __int64 *v36; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 Atom; // [rsp+70h] [rbp-90h]
  __int128 v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned int *v43; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v44; // [rsp+98h] [rbp-68h]
  unsigned int *v45; // [rsp+A0h] [rbp-60h]
  int v46; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v47; // [rsp+B0h] [rbp-50h]
  char v48; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v49; // [rsp+C0h] [rbp-40h]
  char v50; // [rsp+C8h] [rbp-38h]
  __int128 v51; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v52[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v53; // [rsp+F0h] [rbp-10h]
  __int128 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v55; // [rsp+108h] [rbp+8h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+118h] [rbp+18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v58[544]; // [rsp+160h] [rbp+60h] BYREF
  char v59; // [rsp+380h] [rbp+280h] BYREF

  v6 = a3;
  v53 = a5;
  memset_thunk_772440563353939046(&v43, 0, 0x40u);
  v52[0] = 34078720;
  v40 = 0;
  v36 = 0;
  Handle = 0;
  v38 = 0u;
  v8 = 0;
  v39 = 0;
  v52[1] = &v59;
  Atom = 0;
  v51 = 0;
  v54 = 0;
  v55 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( a1 )
  {
    if ( !a2 || (v11 = 1, !(_DWORD)v6) || (unsigned int)v6 > *(_DWORD *)(a1 + 4) )
    {
      v9 = *(_DWORD *)(a1 + 4);
      goto LABEL_3;
    }
    v10 = 0;
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v6) )
      return (unsigned int)v10;
    _mm_lfence();
    v13 = a2[6];
    v14 = *(unsigned int *)((char *)&a2[6 * v6 + 4] + *(unsigned int *)((char *)a2 + v13 + 12));
    v15 = *(unsigned int *)((char *)a2 + v14 + 80);
    if ( v15 > 0xFFFE )
    {
      DbgPrintEx(
        51,
        0,
        "SXS: Assembly directory name stored in assembly information too long (%lu bytes) - ACTIVATION_CONTEXT_DATA at %p\n",
        v15,
        a2);
      v10 = -1073741562;
      goto LABEL_4;
    }
    v16 = (char *)a2 + *(unsigned int *)((char *)a2 + v13 + 16);
    if ( (*((_BYTE *)a2 + v14 + 4) & 0x10) == 0 )
    {
      v36 = 0;
      LOWORD(v51) = *(_WORD *)((char *)a2 + v14 + 80);
      WORD1(v51) = v51;
      v23 = *(unsigned int *)((char *)a2 + v14 + 84);
      v43 = a2;
      *((_QWORD *)&v51 + 1) = &v16[v23];
      LODWORD(v44) = v6;
      v47 = v58;
      v45 = 0;
      v46 = 34996224;
      v48 = 0;
      v50 = 0;
      v49 = 0;
      RtlpAssemblyStorageMapResolutionDefaultCallback(1, &v43, a5);
      if ( v50 )
      {
        v10 = -1073741536;
        goto LABEL_4;
      }
      if ( v48 )
      {
        v32 = RtlpProbeAssemblyStorageRootForAssembly(
                v24,
                (unsigned int)&v46,
                (unsigned int)&v51,
                (unsigned int)v52,
                (__int64)&v40,
                (__int64)&v36,
                (__int64)&Handle);
        v10 = v32;
        if ( v32 < 0 )
        {
          ShareAccess[0] = v32;
          DbgPrintEx(
            51,
            0,
            "SXS: Attempt to probe known root of assembly storage (\"%wZ\") failed; Status = 0x%08lx\n",
            &v46,
            *(_QWORD *)ShareAccess);
        }
        else
        {
          inserted = RtlpInsertAssemblyStorageMapEntry(a1, (unsigned int)v6, &v46, &Handle);
          v10 = inserted;
          if ( inserted < 0 )
            DbgPrintEx(
              51,
              0,
              "SXS: Attempt to insert well known storage root into assembly storage map assembly roster index %lu failed;"
              " Status = 0x%08lx\n",
              v6,
              inserted);
          else
            v10 = 0;
        }
        goto LABEL_4;
      }
      v25 = v45;
      v26 = v49;
      v27 = 0;
      *(_QWORD *)&v42 = v45;
      while ( 1 )
      {
        v28 = v27 == v26;
        if ( v27 >= v26 )
          goto LABEL_40;
        v43 = v25;
        v44 = v27;
        v47 = v58;
        v46 = 34996224;
        LOWORD(v45) = 0;
        RtlpAssemblyStorageMapResolutionDefaultCallback(2, &v43, v53);
        if ( (_BYTE)v45 )
          break;
        if ( BYTE1(v45) )
        {
          if ( !(_WORD)v46 )
            goto LABEL_55;
          v26 = v27 + 1;
        }
        if ( (_WORD)v46 )
        {
          v29 = (int)Handle;
          if ( Handle )
          {
            NtClose(Handle);
            Handle = 0;
          }
          v30 = RtlpProbeAssemblyStorageRootForAssembly(
                  v29,
                  (unsigned int)&v46,
                  (unsigned int)&v51,
                  (unsigned int)v52,
                  (__int64)&v40,
                  (__int64)&v36,
                  (__int64)&Handle);
          v10 = v30;
          if ( v30 >= 0 )
          {
            v28 = v27 == v26;
LABEL_40:
            if ( !v28 )
            {
              v21 = (unsigned int *)v42;
              goto LABEL_23;
            }
LABEL_55:
            DbgPrintEx(
              51,
              0,
              "SXS: Unable to resolve storage root for assembly directory %wZ in %Iu tries\n",
              &v51,
              v27);
            v10 = -1072365564;
            goto LABEL_56;
          }
          if ( v30 != -1072365564 )
          {
            OpenOptions[0] = v30;
            DbgPrintEx(
              51,
              0,
              "SXS: Attempt to probe assembly storage root %wZ for assembly directory %wZ failed with status = 0x%08lx\n",
              &v46,
              &v51,
              *(_QWORD *)OpenOptions);
            goto LABEL_56;
          }
        }
        v25 = (unsigned int *)v42;
        ++v27;
      }
      v10 = -1073741536;
LABEL_56:
      v21 = (unsigned int *)v42;
      goto LABEL_27;
    }
    v36 = v52;
    v17 = (const wchar_t *)&v16[*(unsigned int *)((char *)a2 + v14 + 24)];
    if ( !v17 || (v18 = wcsrchr(v17, 0x5Cu)) == 0 )
    {
      v10 = -1073741595;
      goto LABEL_4;
    }
    v19 = (unsigned __int16)(2 * (v18 - v17 + 2));
    if ( (unsigned __int16)v19 > 0x208u )
    {
      WORD1(v40) = 2 * (v18 - v17 + 2);
      Atom = RtlpAllocateAtom(v19);
      if ( !Atom )
      {
        v10 = -1073741801;
        v8 = 0;
        goto LABEL_4;
      }
      v20 = &v40;
      v36 = &v40;
    }
    else
    {
      v20 = v36;
    }
    v11 = 0;
    v21 = 0;
    memmove((void *)v20[1], v17, v19 - 2);
    *(_WORD *)(v36[1] + 2 * (v19 >> 1) - 2) = 0;
    *(_WORD *)v36 = v19 - 2;
LABEL_23:
    if ( Handle )
      goto LABEL_24;
    v42 = 0;
    if ( (int)RtlInitUnicodeStringEx(&v42, v36[1]) < 0
      || (int)RtlpDosPathNameToRelativeNtPathName(2, (unsigned int)&v42, 0, (unsigned int)&v38, 0, 0, (__int64)&v54) < 0 )
    {
      DbgPrintEx(51, 0, "SXS: Attempt to translate DOS path name \"%S\" to NT format failed\n", (const wchar_t *)v36[1]);
      v10 = -1073741766;
      goto LABEL_26;
    }
    v39 = *((_QWORD *)&v38 + 1);
    if ( (_WORD)v54 )
    {
      v38 = v54;
      v31 = (void *)v55;
    }
    else
    {
      v31 = 0;
      *(_QWORD *)&v55 = 0;
    }
    ObjectAttributes.RootDirectory = v31;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v38;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = NtOpenFile(&Handle, 0x100020u, &ObjectAttributes, &IoStatusBlock, 3u, 0x21u);
    RtlReleaseRelativeName(&v54);
    if ( v10 >= 0 )
    {
LABEL_24:
      v22 = RtlpInsertAssemblyStorageMapEntry(a1, (unsigned int)v6, v36, &Handle);
      v10 = v22;
      if ( v22 < 0 )
        DbgPrintEx(51, 0, "SXS: Storage resolution failed to insert entry to storage map; Status = 0x%08lx\n", v22);
      else
        v10 = 0;
    }
    else
    {
      DbgPrintEx(
        51,
        0,
        "SXS: Unable to open assembly directory under storage root \"%S\"; Status = 0x%08lx\n",
        (const wchar_t *)v36[1],
        v10);
    }
LABEL_26:
    if ( !v11 )
    {
LABEL_28:
      v8 = v39;
      goto LABEL_4;
    }
LABEL_27:
    v43 = v21;
    RtlpAssemblyStorageMapResolutionDefaultCallback(4, &v43, v53);
    goto LABEL_28;
  }
  v9 = 0;
LABEL_3:
  DbgPrintEx(
    51,
    0,
    "SXS: %s() bad parameters\n"
    "SXS:   Map                : %p\n"
    "SXS:   Data               : %p\n"
    "SXS:   AssemblyRosterIndex: 0x%lx\n"
    "SXS:   Map->AssemblyCount : 0x%lx\n",
    "RtlpResolveAssemblyStorageMapEntry",
    (const void *)a1,
    a2,
    v6,
    v9);
  v10 = -1073741811;
LABEL_4:
  if ( Atom )
    RtlpSysVolFree(Atom);
  if ( Handle )
    NtClose(Handle);
  if ( v8 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800d0560  mov     [rsp-8+arg_18], rbx
0x1800d0565  push    rbp
0x1800d0566  push    rsi
0x1800d0567  push    rdi
0x1800d0568  push    r12
0x1800d056a  push    r13
0x1800d056c  push    r14
0x1800d056e  push    r15
0x1800d0570  lea     rbp, [rsp-4A0h]
0x1800d0578  sub     rsp, 5A0h
0x1800d057f  mov     rax, cs:__security_cookie
0x1800d0586  xor     rax, rsp
0x1800d0589  mov     [rbp+4D0h+var_40], rax
0x1800d0590  mov     r13, [rbp+4D0h+arg_20]
0x1800d0597  mov     rdi, rdx
0x1800d059a  xor     edx, edx; Val
0x1800d059c  mov     esi, r8d
0x1800d059f  mov     r14, rcx
0x1800d05a2  mov     [rbp+4D0h+var_4E0], r13
0x1800d05a6  lea     rcx, [rbp+4D0h+var_540]; void *
0x1800d05aa  lea     r8d, [rdx+40h]; Size
0x1800d05ae  call    memset$thunk$772440563353939046
0x1800d05b3  xor     r10d, r10d
0x1800d05b6  mov     [rbp+4D0h+var_4F0], 2080000h
0x1800d05be  mov     [rsp+5D0h+var_568], r10
0x1800d05c3  xorps   xmm0, xmm0
0x1800d05c6  mov     [rsp+5D0h+var_590], r10
0x1800d05cb  xorps   xmm1, xmm1
0x1800d05ce  mov     [rsp+5D0h+Handle], r10
0x1800d05d3  lea     rax, [rbp+4D0h+var_250]
0x1800d05da  mov     qword ptr [rsp+5D0h+var_580], r10
0x1800d05df  mov     r12d, r10d
0x1800d05e2  mov     [rsp+5D0h+var_570], r10
0x1800d05e7  mov     [rbp+4D0h+var_4E8], rax
0x1800d05eb  mov     [rsp+5D0h+var_560], r10
0x1800d05f0  mov     qword ptr [rsp+5D0h+var_580+8], r10
0x1800d05f5  movups  [rbp+4D0h+var_500], xmm0
0x1800d05f9  movups  [rbp+4D0h+var_4D8], xmm0
0x1800d05fd  movups  [rbp+4D0h+var_4C8], xmm0
0x1800d0601  movups  xmmword ptr [rbp+4D0h+ObjectAttributes.Length], xmm1
0x1800d0605  movups  xmmword ptr [rbp+4D0h+ObjectAttributes.ObjectName], xmm1
0x1800d0609  movups  xmmword ptr [rbp+4D0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800d060d  movups  xmmword ptr [rbp+4D0h+IoStatusBlock.___u0], xmm0
0x1800d0611  test    r14, r14
0x1800d0614  jnz     short loc_1800D0684
0x1800d0616  mov     eax, r10d
0x1800d0619  mov     [rsp+5D0h+var_598], eax
0x1800d061d  lea     r9, aRtlpresolveass; "RtlpResolveAssemblyStorageMapEntry"
0x1800d0624  xor     edx, edx
0x1800d0626  mov     dword ptr [rsp+5D0h+var_5A0], esi
0x1800d062a  mov     qword ptr [rsp+5D0h+OpenOptions], rdi
0x1800d062f  lea     r8, aSxsSBadParamet_3; "SXS: %s() bad parameters\nSXS:   Map   "...
0x1800d0636  mov     qword ptr [rsp+5D0h+ShareAccess], r14
0x1800d063b  lea     ecx, [rdx+33h]
0x1800d063e  call    DbgPrintEx
0x1800d0643  mov     ebx, 0C000000Dh
0x1800d0648  mov     rcx, [rsp+5D0h+var_560]
0x1800d064d  test    rcx, rcx
0x1800d0650  jz      short loc_1800D0657
0x1800d0652  call    RtlpSysVolFree
0x1800d0657  mov     rcx, [rsp+5D0h+Handle]; Handle
0x1800d065c  test    rcx, rcx
0x1800d065f  jz      short loc_1800D0666
0x1800d0661  call    NtClose
0x1800d0666  test    r12, r12
0x1800d0669  jz      short loc_1800D06A7
0x1800d066b  mov     rcx, gs:60h
0x1800d0674  mov     r8, r12
0x1800d0677  xor     edx, edx
0x1800d0679  mov     rcx, [rcx+30h]
0x1800d067d  call    RtlFreeHeap_0
0x1800d0682  jmp     short loc_1800D06A7
0x1800d0684  test    rdi, rdi
0x1800d0687  jz      short loc_1800D06D4
0x1800d0689  mov     r15d, 1
0x1800d068f  cmp     esi, r15d
0x1800d0692  jb      short loc_1800D06D4
0x1800d0694  cmp     esi, [r14+4]
0x1800d0698  ja      short loc_1800D06D4
0x1800d069a  mov     rax, [r14+8]
0x1800d069e  mov     ebx, r10d
0x1800d06a1  cmp     [rax+rsi*8], r10
0x1800d06a5  jz      short loc_1800D06DD
0x1800d06a7  mov     eax, ebx
0x1800d06a9  mov     rcx, [rbp+4D0h+var_40]
0x1800d06b0  xor     rcx, rsp; StackCookie
0x1800d06b3  call    __security_check_cookie
0x1800d06b8  mov     rbx, [rsp+5D0h+arg_18]
0x1800d06c0  add     rsp, 5A0h
0x1800d06c7  pop     r15
0x1800d06c9  pop     r14
0x1800d06cb  pop     r13
0x1800d06cd  pop     r12
0x1800d06cf  pop     rdi
0x1800d06d0  pop     rsi
0x1800d06d1  pop     rbp
0x1800d06d2  retn
0x1800d06d4  mov     eax, [r14+4]
0x1800d06d8  jmp     loc_1800D0619
0x1800d06dd  lfence
0x1800d06e0  mov     r8d, [rdi+18h]
0x1800d06e4  lea     rcx, [rsi+rsi*2]
0x1800d06e8  mov     eax, [r8+rdi+0Ch]
0x1800d06ed  add     rax, rdi
0x1800d06f0  mov     edx, [rax+rcx*8+10h]
0x1800d06f4  mov     r9d, [rdx+rdi+50h]
0x1800d06f9  cmp     r9d, 0FFFEh
0x1800d0700  ja      loc_1800D0BB0
0x1800d0706  mov     ecx, [r8+rdi+10h]
0x1800d070b  add     rcx, rdi
0x1800d070e  test    byte ptr [rdx+rdi+4], 10h
0x1800d0713  jz      loc_1800D07FD
0x1800d0719  lea     rax, [rbp+4D0h+var_4F0]
0x1800d071d  mov     [rsp+5D0h+var_590], rax
0x1800d0722  mov     edi, [rdx+rdi+18h]
0x1800d0726  add     rdi, rcx
0x1800d0729  jz      loc_1800D0BD0
0x1800d072f  mov     edx, 5Ch ; '\'; Ch
0x1800d0734  mov     rcx, rdi; Str
0x1800d0737  call    wcsrchr
0x1800d073c  xor     r10d, r10d
0x1800d073f  test    rax, rax
0x1800d0742  jz      loc_1800D0BD0
0x1800d0748  sub     rax, rdi
0x1800d074b  lea     r12d, [r10+2]
0x1800d074f  sar     rax, 1
0x1800d0752  add     ax, r12w
0x1800d0756  add     ax, ax
0x1800d0759  movzx   ebx, ax
0x1800d075c  mov     eax, 208h
0x1800d0761  cmp     bx, ax
0x1800d0764  ja      loc_1800D0AF6
0x1800d076a  mov     rcx, [rsp+5D0h+var_590]
0x1800d076f  mov     rcx, [rcx+8]; void *
0x1800d0773  lea     r8, [rbx-2]; Size
0x1800d0777  mov     rdx, rdi; Src
0x1800d077a  mov     r15b, r10b
0x1800d077d  mov     r13, r10
0x1800d0780  call    memmove
0x1800d0785  mov     rax, [rsp+5D0h+var_590]
0x1800d078a  mov     rdx, rbx
0x1800d078d  shr     rdx, 1
0x1800d0790  xor     r10d, r10d
0x1800d0793  sub     bx, r12w
0x1800d0797  mov     rcx, [rax+8]
0x1800d079b  mov     [rcx+rdx*2-2], r10w
0x1800d07a1  mov     rax, [rsp+5D0h+var_590]
0x1800d07a6  mov     [rax], bx
0x1800d07a9  cmp     [rsp+5D0h+Handle], r10
0x1800d07ae  jz      loc_1800D0954
0x1800d07b4  mov     r8, [rsp+5D0h+var_590]
0x1800d07b9  lea     r9, [rsp+5D0h+Handle]
0x1800d07be  mov     edx, esi
0x1800d07c0  mov     rcx, r14
0x1800d07c3  call    RtlpInsertAssemblyStorageMapEntry
0x1800d07c8  xor     r10d, r10d
0x1800d07cb  mov     ebx, eax
0x1800d07cd  test    eax, eax
0x1800d07cf  js      loc_1800D0B8E
0x1800d07d5  mov     ebx, r10d
0x1800d07d8  test    r15b, r15b
0x1800d07db  jz      short loc_1800D07F3
0x1800d07dd  mov     r8, [rbp+4D0h+var_4E0]
0x1800d07e1  lea     rdx, [rbp+4D0h+var_540]
0x1800d07e5  mov     ecx, 4
0x1800d07ea  mov     [rbp+4D0h+var_540], r13
0x1800d07ee  call    RtlpAssemblyStorageMapResolutionDefaultCallback
0x1800d07f3  mov     r12, [rsp+5D0h+var_570]
0x1800d07f8  jmp     loc_1800D0648
0x1800d07fd  mov     [rsp+5D0h+var_590], r10
0x1800d0802  mov     r8, r13
0x1800d0805  movzx   eax, word ptr [rdx+rdi+50h]
0x1800d080a  mov     ebx, 216h
0x1800d080f  mov     word ptr [rbp+4D0h+var_500], ax
0x1800d0813  mov     word ptr [rbp+4D0h+var_500+2], ax
0x1800d0817  mov     eax, [rdx+rdi+54h]
0x1800d081b  lea     rdx, [rbp+4D0h+var_540]
0x1800d081f  add     rax, rcx
0x1800d0822  mov     [rbp+4D0h+var_540], rdi
0x1800d0826  mov     qword ptr [rbp+4D0h+var_500+8], rax
0x1800d082a  mov     ecx, r15d
0x1800d082d  lea     rax, [rbp+4D0h+var_470]
0x1800d0831  mov     [rbp+4D0h+var_538], esi
0x1800d0834  mov     [rbp+4D0h+var_520], rax
0x1800d0838  mov     [rbp+4D0h+var_530], r10
0x1800d083c  mov     [rbp+4D0h+var_528], 2160000h
0x1800d0843  mov     [rbp+4D0h+var_518], r10b
0x1800d0847  mov     [rbp+4D0h+var_508], r10b
0x1800d084b  mov     [rbp+4D0h+var_510], r10
0x1800d084f  call    RtlpAssemblyStorageMapResolutionDefaultCallback
0x1800d0854  xor     r10d, r10d
0x1800d0857  cmp     [rbp+4D0h+var_508], r10b
0x1800d085b  jnz     loc_1800D0BE7
0x1800d0861  cmp     [rbp+4D0h+var_518], r10b
0x1800d0865  jnz     loc_1800D0A63
0x1800d086b  mov     rax, [rbp+4D0h+var_530]
0x1800d086f  lea     r12d, [r10+2]
0x1800d0873  mov     r13, [rbp+4D0h+var_510]
0x1800d0877  mov     edi, r10d
0x1800d087a  mov     qword ptr [rsp+5D0h+var_558], rax
0x1800d087f  cmp     rdi, r13
0x1800d0882  jnb     loc_1800D0927
0x1800d0888  mov     r8, [rbp+4D0h+var_4E0]
0x1800d088c  lea     rdx, [rbp+4D0h+var_540]
0x1800d0890  mov     [rbp+4D0h+var_540], rax
0x1800d0894  mov     ecx, r12d
0x1800d0897  mov     rax, rdi
0x1800d089a  mov     [rbp+4D0h+var_538], edi
0x1800d089d  shr     rax, 20h
0x1800d08a1  mov     [rbp+4D0h+var_534], eax
0x1800d08a4  lea     rax, [rbp+4D0h+var_470]
0x1800d08a8  mov     [rbp+4D0h+var_520], rax
0x1800d08ac  mov     [rbp+4D0h+var_528], 2160000h
0x1800d08b3  mov     word ptr [rbp+4D0h+var_530], 0
0x1800d08b9  call    RtlpAssemblyStorageMapResolutionDefaultCallback
0x1800d08be  xor     r10d, r10d
0x1800d08c1  cmp     byte ptr [rbp+4D0h+var_530], r10b
0x1800d08c5  jnz     loc_1800D0B84
0x1800d08cb  movzx   eax, word ptr [rbp+4D0h+var_528]
0x1800d08cf  cmp     byte ptr [rbp+4D0h+var_530+1], r10b
0x1800d08d3  jnz     loc_1800D0AC4
0x1800d08d9  test    ax, ax
0x1800d08dc  jz      short loc_1800D0947
0x1800d08de  mov     rcx, [rsp+5D0h+Handle]; Handle
0x1800d08e3  test    rcx, rcx
0x1800d08e6  jnz     loc_1800D0B4A
0x1800d08ec  lea     rax, [rsp+5D0h+Handle]
0x1800d08f1  mov     [rsp+5D0h+var_5A0], rax
0x1800d08f6  lea     r9, [rbp+4D0h+var_4F0]
0x1800d08fa  lea     rax, [rsp+5D0h+var_590]
0x1800d08ff  mov     qword ptr [rsp+5D0h+OpenOptions], rax
0x1800d0904  lea     r8, [rbp+4D0h+var_500]
0x1800d0908  lea     rax, [rsp+5D0h+var_568]
0x1800d090d  lea     rdx, [rbp+4D0h+var_528]
0x1800d0911  mov     qword ptr [rsp+5D0h+ShareAccess], rax
0x1800d0916  call    RtlpProbeAssemblyStorageRootForAssembly
0x1800d091b  xor     r10d, r10d
0x1800d091e  mov     ebx, eax
0x1800d0920  test    eax, eax
0x1800d0922  js      short loc_1800D0937
0x1800d0924  cmp     rdi, r13
0x1800d0927  jz      loc_1800D0ACD
0x1800d092d  mov     r13, qword ptr [rsp+5D0h+var_558]
0x1800d0932  jmp     loc_1800D07A9
0x1800d0937  cmp     eax, 0C0150004h
0x1800d093c  jnz     loc_1800D0B5D
0x1800d0942  mov     ebx, 216h
0x1800d0947  mov     rax, qword ptr [rsp+5D0h+var_558]
0x1800d094c  add     rdi, r15
0x1800d094f  jmp     loc_1800D087F
0x1800d0954  mov     rdx, [rsp+5D0h+var_590]
0x1800d0959  lea     rcx, [rsp+5D0h+var_558]
0x1800d095e  xorps   xmm0, xmm0
0x1800d0961  movups  [rsp+5D0h+var_558], xmm0
0x1800d0966  mov     rdx, [rdx+8]
0x1800d096a  call    RtlInitUnicodeStringEx
0x1800d096f  xor     edi, edi
0x1800d0971  test    eax, eax
0x1800d0973  js      short loc_1800D09A1
0x1800d0975  lea     rax, [rbp+4D0h+var_4D8]
0x1800d0979  xor     r8d, r8d
0x1800d097c  mov     [rsp+5D0h+var_5A0], rax
0x1800d0981  lea     r9, [rsp+5D0h+var_580]
0x1800d0986  mov     qword ptr [rsp+5D0h+OpenOptions], rdi
0x1800d098b  lea     rdx, [rsp+5D0h+var_558]
0x1800d0990  mov     ecx, r12d
0x1800d0993  mov     qword ptr [rsp+5D0h+ShareAccess], rdi
0x1800d0998  call    RtlpDosPathNameToRelativeNtPathName
0x1800d099d  test    eax, eax
0x1800d099f  jns     short loc_1800D09C5
0x1800d09a1  mov     r9, [rsp+5D0h+var_590]
0x1800d09a6  lea     r8, aSxsAttemptToTr; "SXS: Attempt to translate DOS path name"...
0x1800d09ad  xor     edx, edx
0x1800d09af  mov     r9, [r9+8]
0x1800d09b3  lea     ecx, [rdx+33h]
0x1800d09b6  call    DbgPrintEx
0x1800d09bb  mov     ebx, 0C000003Ah
0x1800d09c0  jmp     loc_1800D07D8
0x1800d09c5  mov     rax, qword ptr [rsp+5D0h+var_580+8]
0x1800d09ca  mov     [rsp+5D0h+var_570], rax
0x1800d09cf  movzx   eax, word ptr [rbp+4D0h+var_4D8]
0x1800d09d3  test    ax, ax
0x1800d09d6  jnz     loc_1800D0B23
0x1800d09dc  mov     rax, rdi
0x1800d09df  mov     qword ptr [rbp+4D0h+var_4C8], rax
0x1800d09e3  mov     [rbp+4D0h+ObjectAttributes.RootDirectory], rax
0x1800d09e7  lea     r9, [rbp+4D0h+IoStatusBlock]; IoStatusBlock
0x1800d09eb  lea     rax, [rsp+5D0h+var_580]
0x1800d09f0  mov     [rsp+5D0h+OpenOptions], 21h ; '!'; OpenOptions
0x1800d09f8  xorps   xmm0, xmm0
0x1800d09fb  mov     [rbp+4D0h+ObjectAttributes.ObjectName], rax
0x1800d09ff  lea     r8, [rbp+4D0h+ObjectAttributes]; ObjectAttributes
0x1800d0a03  mov     [rbp+4D0h+ObjectAttributes.Length], 30h ; '0'
0x1800d0a0a  mov     edx, 100020h; DesiredAccess
0x1800d0a0f  mov     [rbp+4D0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d0a16  lea     rcx, [rsp+5D0h+Handle]; FileHandle
0x1800d0a1b  mov     [rsp+5D0h+ShareAccess], 3; ShareAccess
0x1800d0a23  movdqu  xmmword ptr [rbp+4D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d0a28  call    NtOpenFile
0x1800d0a2d  lea     rcx, [rbp+4D0h+var_4D8]
  ... truncated ...
```
