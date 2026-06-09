# RtlpResolveAssemblyStorageMapEntry

- ea: `0x1800cee30`
- end: `0x1800cf4fc`
- name: `RtlpResolveAssemblyStorageMapEntry`
- size: `1740`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800ce740`

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001c520`
- `0x18001d490`
- `0x180021fe0`
- `0x18002b2a0`
- `0x18005c670`
- `0x1800cee30`
- `0x1800cf510`
- `0x1800cf8f4`
- `0x1800cfa84`
- `0x18012cc90`
- `0x18015e4b0`
- `0x18015e930`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## string_xrefs

- `0x1800cf276`: `SXS: Attempt to translate DOS path name "%S" to NT format failed\n`
- `0x1800cf3a8`: `SXS: Unable to resolve storage root for assembly directory %wZ in %Iu tries\n`
- `0x1800cf43b`: `SXS: Attempt to probe assembly storage root %wZ for assembly directory %wZ failed with status = 0x%08lx\n`
- `0x1800cf315`: `SXS: Unable to open assembly directory under storage root "%S"; Status = 0x%08lx\n`
- `0x1800cf487`: `SXS: Assembly directory name stored in assembly information too long (%lu bytes) - ACTIVATION_CONTEXT_DATA at %p\n`
- `0x1800cf4cb`: `SXS: Attempt to probe known root of assembly storage ("%wZ") failed; Status = 0x%08lx\n`
- `0x1800cf4e8`: `SXS: Attempt to insert well known storage root into assembly storage map assembly roster index %lu failed; Status = 0x%08lx\n`

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
0x1800cee30  mov     [rsp-8+arg_18], rbx
0x1800cee35  push    rbp
0x1800cee36  push    rsi
0x1800cee37  push    rdi
0x1800cee38  push    r12
0x1800cee3a  push    r13
0x1800cee3c  push    r14
0x1800cee3e  push    r15
0x1800cee40  lea     rbp, [rsp-4A0h]
0x1800cee48  sub     rsp, 5A0h
0x1800cee4f  mov     rax, cs:__security_cookie
0x1800cee56  xor     rax, rsp
0x1800cee59  mov     [rbp+4D0h+var_40], rax
0x1800cee60  mov     r13, [rbp+4D0h+arg_20]
0x1800cee67  mov     rdi, rdx
0x1800cee6a  xor     edx, edx; Val
0x1800cee6c  mov     esi, r8d
0x1800cee6f  mov     r14, rcx
0x1800cee72  mov     [rbp+4D0h+var_4E0], r13
0x1800cee76  lea     rcx, [rbp+4D0h+var_540]; void *
0x1800cee7a  lea     r8d, [rdx+40h]; Size
0x1800cee7e  call    memset$thunk$772440563353939046
0x1800cee83  xor     r10d, r10d
0x1800cee86  mov     [rbp+4D0h+var_4F0], 2080000h
0x1800cee8e  mov     [rsp+5D0h+var_568], r10
0x1800cee93  xorps   xmm0, xmm0
0x1800cee96  mov     [rsp+5D0h+var_590], r10
0x1800cee9b  xorps   xmm1, xmm1
0x1800cee9e  mov     [rsp+5D0h+Handle], r10
0x1800ceea3  lea     rax, [rbp+4D0h+var_250]
0x1800ceeaa  mov     qword ptr [rsp+5D0h+var_580], r10
0x1800ceeaf  mov     r12d, r10d
0x1800ceeb2  mov     [rsp+5D0h+var_570], r10
0x1800ceeb7  mov     [rbp+4D0h+var_4E8], rax
0x1800ceebb  mov     [rsp+5D0h+var_560], r10
0x1800ceec0  mov     qword ptr [rsp+5D0h+var_580+8], r10
0x1800ceec5  movups  [rbp+4D0h+var_500], xmm0
0x1800ceec9  movups  [rbp+4D0h+var_4D8], xmm0
0x1800ceecd  movups  [rbp+4D0h+var_4C8], xmm0
0x1800ceed1  movups  xmmword ptr [rbp+4D0h+ObjectAttributes.Length], xmm1
0x1800ceed5  movups  xmmword ptr [rbp+4D0h+ObjectAttributes.ObjectName], xmm1
0x1800ceed9  movups  xmmword ptr [rbp+4D0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800ceedd  movups  xmmword ptr [rbp+4D0h+IoStatusBlock.___u0], xmm0
0x1800ceee1  test    r14, r14
0x1800ceee4  jnz     short loc_1800CEF54
0x1800ceee6  mov     eax, r10d
0x1800ceee9  mov     [rsp+5D0h+var_598], eax
0x1800ceeed  lea     r9, aRtlpresolveass; "RtlpResolveAssemblyStorageMapEntry"
0x1800ceef4  xor     edx, edx
0x1800ceef6  mov     dword ptr [rsp+5D0h+var_5A0], esi
0x1800ceefa  mov     qword ptr [rsp+5D0h+OpenOptions], rdi
0x1800ceeff  lea     r8, aSxsSBadParamet_3; "SXS: %s() bad parameters\nSXS:   Map   "...
0x1800cef06  mov     qword ptr [rsp+5D0h+ShareAccess], r14
0x1800cef0b  lea     ecx, [rdx+33h]
0x1800cef0e  call    DbgPrintEx
0x1800cef13  mov     ebx, 0C000000Dh
0x1800cef18  mov     rcx, [rsp+5D0h+var_560]
0x1800cef1d  test    rcx, rcx
0x1800cef20  jz      short loc_1800CEF27
0x1800cef22  call    RtlpSysVolFree
0x1800cef27  mov     rcx, [rsp+5D0h+Handle]; Handle
0x1800cef2c  test    rcx, rcx
0x1800cef2f  jz      short loc_1800CEF36
0x1800cef31  call    NtClose
0x1800cef36  test    r12, r12
0x1800cef39  jz      short loc_1800CEF77
0x1800cef3b  mov     rcx, gs:60h
0x1800cef44  mov     r8, r12
0x1800cef47  xor     edx, edx
0x1800cef49  mov     rcx, [rcx+30h]
0x1800cef4d  call    RtlFreeHeap_0
0x1800cef52  jmp     short loc_1800CEF77
0x1800cef54  test    rdi, rdi
0x1800cef57  jz      short loc_1800CEFA4
0x1800cef59  mov     r15d, 1
0x1800cef5f  cmp     esi, r15d
0x1800cef62  jb      short loc_1800CEFA4
0x1800cef64  cmp     esi, [r14+4]
0x1800cef68  ja      short loc_1800CEFA4
0x1800cef6a  mov     rax, [r14+8]
0x1800cef6e  mov     ebx, r10d
0x1800cef71  cmp     [rax+rsi*8], r10
0x1800cef75  jz      short loc_1800CEFAD
0x1800cef77  mov     eax, ebx
0x1800cef79  mov     rcx, [rbp+4D0h+var_40]
0x1800cef80  xor     rcx, rsp; StackCookie
0x1800cef83  call    __security_check_cookie
0x1800cef88  mov     rbx, [rsp+5D0h+arg_18]
0x1800cef90  add     rsp, 5A0h
0x1800cef97  pop     r15
0x1800cef99  pop     r14
0x1800cef9b  pop     r13
0x1800cef9d  pop     r12
0x1800cef9f  pop     rdi
0x1800cefa0  pop     rsi
0x1800cefa1  pop     rbp
0x1800cefa2  retn
0x1800cefa4  mov     eax, [r14+4]
0x1800cefa8  jmp     loc_1800CEEE9
0x1800cefad  lfence
0x1800cefb0  mov     r8d, [rdi+18h]
0x1800cefb4  lea     rcx, [rsi+rsi*2]
0x1800cefb8  mov     eax, [r8+rdi+0Ch]
0x1800cefbd  add     rax, rdi
0x1800cefc0  mov     edx, [rax+rcx*8+10h]
0x1800cefc4  mov     r9d, [rdx+rdi+50h]
0x1800cefc9  cmp     r9d, 0FFFEh
0x1800cefd0  ja      loc_1800CF480
0x1800cefd6  mov     ecx, [r8+rdi+10h]
0x1800cefdb  add     rcx, rdi
0x1800cefde  test    byte ptr [rdx+rdi+4], 10h
0x1800cefe3  jz      loc_1800CF0CD
0x1800cefe9  lea     rax, [rbp+4D0h+var_4F0]
0x1800cefed  mov     [rsp+5D0h+var_590], rax
0x1800ceff2  mov     edi, [rdx+rdi+18h]
0x1800ceff6  add     rdi, rcx
0x1800ceff9  jz      loc_1800CF4A0
0x1800cefff  mov     edx, 5Ch ; '\'; Ch
0x1800cf004  mov     rcx, rdi; Str
0x1800cf007  call    wcsrchr
0x1800cf00c  xor     r10d, r10d
0x1800cf00f  test    rax, rax
0x1800cf012  jz      loc_1800CF4A0
0x1800cf018  sub     rax, rdi
0x1800cf01b  lea     r12d, [r10+2]
0x1800cf01f  sar     rax, 1
0x1800cf022  add     ax, r12w
0x1800cf026  add     ax, ax
0x1800cf029  movzx   ebx, ax
0x1800cf02c  mov     eax, 208h
0x1800cf031  cmp     bx, ax
0x1800cf034  ja      loc_1800CF3C6
0x1800cf03a  mov     rcx, [rsp+5D0h+var_590]
0x1800cf03f  mov     rcx, [rcx+8]; void *
0x1800cf043  lea     r8, [rbx-2]; Size
0x1800cf047  mov     rdx, rdi; Src
0x1800cf04a  mov     r15b, r10b
0x1800cf04d  mov     r13, r10
0x1800cf050  call    memmove
0x1800cf055  mov     rax, [rsp+5D0h+var_590]
0x1800cf05a  mov     rdx, rbx
0x1800cf05d  shr     rdx, 1
0x1800cf060  xor     r10d, r10d
0x1800cf063  sub     bx, r12w
0x1800cf067  mov     rcx, [rax+8]
0x1800cf06b  mov     [rcx+rdx*2-2], r10w
0x1800cf071  mov     rax, [rsp+5D0h+var_590]
0x1800cf076  mov     [rax], bx
0x1800cf079  cmp     [rsp+5D0h+Handle], r10
0x1800cf07e  jz      loc_1800CF224
0x1800cf084  mov     r8, [rsp+5D0h+var_590]
0x1800cf089  lea     r9, [rsp+5D0h+Handle]
0x1800cf08e  mov     edx, esi
0x1800cf090  mov     rcx, r14
0x1800cf093  call    RtlpInsertAssemblyStorageMapEntry
0x1800cf098  xor     r10d, r10d
0x1800cf09b  mov     ebx, eax
0x1800cf09d  test    eax, eax
0x1800cf09f  js      loc_1800CF45E
0x1800cf0a5  mov     ebx, r10d
0x1800cf0a8  test    r15b, r15b
0x1800cf0ab  jz      short loc_1800CF0C3
0x1800cf0ad  mov     r8, [rbp+4D0h+var_4E0]
0x1800cf0b1  lea     rdx, [rbp+4D0h+var_540]
0x1800cf0b5  mov     ecx, 4
0x1800cf0ba  mov     [rbp+4D0h+var_540], r13
0x1800cf0be  call    RtlpAssemblyStorageMapResolutionDefaultCallback
0x1800cf0c3  mov     r12, [rsp+5D0h+var_570]
0x1800cf0c8  jmp     loc_1800CEF18
0x1800cf0cd  mov     [rsp+5D0h+var_590], r10
0x1800cf0d2  mov     r8, r13
0x1800cf0d5  movzx   eax, word ptr [rdx+rdi+50h]
0x1800cf0da  mov     ebx, 216h
0x1800cf0df  mov     word ptr [rbp+4D0h+var_500], ax
0x1800cf0e3  mov     word ptr [rbp+4D0h+var_500+2], ax
0x1800cf0e7  mov     eax, [rdx+rdi+54h]
0x1800cf0eb  lea     rdx, [rbp+4D0h+var_540]
0x1800cf0ef  add     rax, rcx
0x1800cf0f2  mov     [rbp+4D0h+var_540], rdi
0x1800cf0f6  mov     qword ptr [rbp+4D0h+var_500+8], rax
0x1800cf0fa  mov     ecx, r15d
0x1800cf0fd  lea     rax, [rbp+4D0h+var_470]
0x1800cf101  mov     [rbp+4D0h+var_538], esi
0x1800cf104  mov     [rbp+4D0h+var_520], rax
0x1800cf108  mov     [rbp+4D0h+var_530], r10
0x1800cf10c  mov     [rbp+4D0h+var_528], 2160000h
0x1800cf113  mov     [rbp+4D0h+var_518], r10b
0x1800cf117  mov     [rbp+4D0h+var_508], r10b
0x1800cf11b  mov     [rbp+4D0h+var_510], r10
0x1800cf11f  call    RtlpAssemblyStorageMapResolutionDefaultCallback
0x1800cf124  xor     r10d, r10d
0x1800cf127  cmp     [rbp+4D0h+var_508], r10b
0x1800cf12b  jnz     loc_1800CF4B7
0x1800cf131  cmp     [rbp+4D0h+var_518], r10b
0x1800cf135  jnz     loc_1800CF333
0x1800cf13b  mov     rax, [rbp+4D0h+var_530]
0x1800cf13f  lea     r12d, [r10+2]
0x1800cf143  mov     r13, [rbp+4D0h+var_510]
0x1800cf147  mov     edi, r10d
0x1800cf14a  mov     qword ptr [rsp+5D0h+var_558], rax
0x1800cf14f  cmp     rdi, r13
0x1800cf152  jnb     loc_1800CF1F7
0x1800cf158  mov     r8, [rbp+4D0h+var_4E0]
0x1800cf15c  lea     rdx, [rbp+4D0h+var_540]
0x1800cf160  mov     [rbp+4D0h+var_540], rax
0x1800cf164  mov     ecx, r12d
0x1800cf167  mov     rax, rdi
0x1800cf16a  mov     [rbp+4D0h+var_538], edi
0x1800cf16d  shr     rax, 20h
0x1800cf171  mov     [rbp+4D0h+var_534], eax
0x1800cf174  lea     rax, [rbp+4D0h+var_470]
0x1800cf178  mov     [rbp+4D0h+var_520], rax
0x1800cf17c  mov     [rbp+4D0h+var_528], 2160000h
0x1800cf183  mov     word ptr [rbp+4D0h+var_530], 0
0x1800cf189  call    RtlpAssemblyStorageMapResolutionDefaultCallback
0x1800cf18e  xor     r10d, r10d
0x1800cf191  cmp     byte ptr [rbp+4D0h+var_530], r10b
0x1800cf195  jnz     loc_1800CF454
0x1800cf19b  movzx   eax, word ptr [rbp+4D0h+var_528]
0x1800cf19f  cmp     byte ptr [rbp+4D0h+var_530+1], r10b
0x1800cf1a3  jnz     loc_1800CF394
0x1800cf1a9  test    ax, ax
0x1800cf1ac  jz      short loc_1800CF217
0x1800cf1ae  mov     rcx, [rsp+5D0h+Handle]; Handle
0x1800cf1b3  test    rcx, rcx
0x1800cf1b6  jnz     loc_1800CF41A
0x1800cf1bc  lea     rax, [rsp+5D0h+Handle]
0x1800cf1c1  mov     [rsp+5D0h+var_5A0], rax
0x1800cf1c6  lea     r9, [rbp+4D0h+var_4F0]
0x1800cf1ca  lea     rax, [rsp+5D0h+var_590]
0x1800cf1cf  mov     qword ptr [rsp+5D0h+OpenOptions], rax
0x1800cf1d4  lea     r8, [rbp+4D0h+var_500]
0x1800cf1d8  lea     rax, [rsp+5D0h+var_568]
0x1800cf1dd  lea     rdx, [rbp+4D0h+var_528]
0x1800cf1e1  mov     qword ptr [rsp+5D0h+ShareAccess], rax
0x1800cf1e6  call    RtlpProbeAssemblyStorageRootForAssembly
0x1800cf1eb  xor     r10d, r10d
0x1800cf1ee  mov     ebx, eax
0x1800cf1f0  test    eax, eax
0x1800cf1f2  js      short loc_1800CF207
0x1800cf1f4  cmp     rdi, r13
0x1800cf1f7  jz      loc_1800CF39D
0x1800cf1fd  mov     r13, qword ptr [rsp+5D0h+var_558]
0x1800cf202  jmp     loc_1800CF079
0x1800cf207  cmp     eax, 0C0150004h
0x1800cf20c  jnz     loc_1800CF42D
0x1800cf212  mov     ebx, 216h
0x1800cf217  mov     rax, qword ptr [rsp+5D0h+var_558]
0x1800cf21c  add     rdi, r15
0x1800cf21f  jmp     loc_1800CF14F
0x1800cf224  mov     rdx, [rsp+5D0h+var_590]
0x1800cf229  lea     rcx, [rsp+5D0h+var_558]
0x1800cf22e  xorps   xmm0, xmm0
0x1800cf231  movups  [rsp+5D0h+var_558], xmm0
0x1800cf236  mov     rdx, [rdx+8]
0x1800cf23a  call    RtlInitUnicodeStringEx
0x1800cf23f  xor     edi, edi
0x1800cf241  test    eax, eax
0x1800cf243  js      short loc_1800CF271
0x1800cf245  lea     rax, [rbp+4D0h+var_4D8]
0x1800cf249  xor     r8d, r8d
0x1800cf24c  mov     [rsp+5D0h+var_5A0], rax
0x1800cf251  lea     r9, [rsp+5D0h+var_580]
0x1800cf256  mov     qword ptr [rsp+5D0h+OpenOptions], rdi
0x1800cf25b  lea     rdx, [rsp+5D0h+var_558]
0x1800cf260  mov     ecx, r12d
0x1800cf263  mov     qword ptr [rsp+5D0h+ShareAccess], rdi
0x1800cf268  call    RtlpDosPathNameToRelativeNtPathName
0x1800cf26d  test    eax, eax
0x1800cf26f  jns     short loc_1800CF295
0x1800cf271  mov     r9, [rsp+5D0h+var_590]
0x1800cf276  lea     r8, aSxsAttemptToTr; "SXS: Attempt to translate DOS path name"...
0x1800cf27d  xor     edx, edx
0x1800cf27f  mov     r9, [r9+8]
0x1800cf283  lea     ecx, [rdx+33h]
0x1800cf286  call    DbgPrintEx
0x1800cf28b  mov     ebx, 0C000003Ah
0x1800cf290  jmp     loc_1800CF0A8
0x1800cf295  mov     rax, qword ptr [rsp+5D0h+var_580+8]
0x1800cf29a  mov     [rsp+5D0h+var_570], rax
0x1800cf29f  movzx   eax, word ptr [rbp+4D0h+var_4D8]
0x1800cf2a3  test    ax, ax
0x1800cf2a6  jnz     loc_1800CF3F3
0x1800cf2ac  mov     rax, rdi
0x1800cf2af  mov     qword ptr [rbp+4D0h+var_4C8], rax
0x1800cf2b3  mov     [rbp+4D0h+ObjectAttributes.RootDirectory], rax
0x1800cf2b7  lea     r9, [rbp+4D0h+IoStatusBlock]; IoStatusBlock
0x1800cf2bb  lea     rax, [rsp+5D0h+var_580]
0x1800cf2c0  mov     [rsp+5D0h+OpenOptions], 21h ; '!'; OpenOptions
0x1800cf2c8  xorps   xmm0, xmm0
0x1800cf2cb  mov     [rbp+4D0h+ObjectAttributes.ObjectName], rax
0x1800cf2cf  lea     r8, [rbp+4D0h+ObjectAttributes]; ObjectAttributes
0x1800cf2d3  mov     [rbp+4D0h+ObjectAttributes.Length], 30h ; '0'
0x1800cf2da  mov     edx, 100020h; DesiredAccess
0x1800cf2df  mov     [rbp+4D0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800cf2e6  lea     rcx, [rsp+5D0h+Handle]; FileHandle
0x1800cf2eb  mov     [rsp+5D0h+ShareAccess], 3; ShareAccess
0x1800cf2f3  movdqu  xmmword ptr [rbp+4D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800cf2f8  call    NtOpenFile
0x1800cf2fd  lea     rcx, [rbp+4D0h+var_4D8]
  ... truncated ...
```
