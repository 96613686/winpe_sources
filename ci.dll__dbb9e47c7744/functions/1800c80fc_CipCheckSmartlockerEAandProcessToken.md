# CipCheckSmartlockerEAandProcessToken

- ea: `0x1800c80fc`
- end: `0x1800c8758`
- name: `CipCheckSmartlockerEAandProcessToken`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c77c0`

## callees

- `0x18002c080`
- `0x180073acc`
- `0x1800747f0`
- `0x180074884`
- `0x1800be5cc`
- `0x1800be644`
- `0x1800c8088`
- `0x1800c80fc`
- `0x1800c87d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800c85eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800c85eb`
- `ntoskrnl!ExAllocatePool2` at `0x1800c81c8`
- `ntoskrnl!ExAllocatePool2` at `0x1800c824e`
- `ntoskrnl!ExAllocatePool2` at `0x1800c82f0`
- `ntoskrnl!ExAllocatePool2` at `0x1800c8414`
- `ntoskrnl!ExAllocatePool2` at `0x1800c81c8`
- `ntoskrnl!ExAllocatePool2` at `0x1800c824e`
- `ntoskrnl!ExAllocatePool2` at `0x1800c82f0`
- `ntoskrnl!ExAllocatePool2` at `0x1800c8414`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800c81fd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800c81fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8358`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8478`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c86bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c86f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8709`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8722`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8358`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8478`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c86bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c86f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8709`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8722`
- `ntoskrnl!wcsncpy_s` at `0x1800c8698`
- `ntoskrnl!wcsncpy_s` at `0x1800c8698`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c8329`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c844d`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c8329`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c844d`

## pseudocode

```c
__int64 __fastcall CipCheckSmartlockerEAandProcessToken(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  _DWORD *v5; // rsi
  __int64 v6; // rdi
  unsigned int v8; // ebx
  __int64 CurrentProcess; // r13
  unsigned int ValidEA; // eax
  void *v11; // r14
  size_t v12; // r12
  void *Pool2; // rax
  unsigned int OriginClaimByProcess; // eax
  void *v15; // r13
  unsigned int v16; // r12d
  void *v17; // rax
  char v18; // cl
  unsigned int v19; // eax
  int v20; // ecx
  unsigned int v21; // r14d
  int v22; // eax
  __int64 v23; // r12
  __int64 v24; // rax
  __int64 *v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // ecx
  unsigned int v29; // r14d
  int v30; // eax
  __int64 v31; // rax
  int **v32; // r14
  int *v33; // r14
  _OWORD *v34; // rcx
  _OWORD *v35; // rax
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  int v38; // ecx
  const wchar_t *v39; // r12
  int v40; // r13d
  unsigned int v41; // r14d
  NTSTATUS v42; // eax
  PVOID v43; // r8
  unsigned int v44; // edx
  size_t Size; // [rsp+40h] [rbp-41h] BYREF
  PVOID v47; // [rsp+48h] [rbp-39h] BYREF
  void *Src; // [rsp+50h] [rbp-31h] BYREF
  void *v49; // [rsp+58h] [rbp-29h] BYREF
  PVOID P; // [rsp+60h] [rbp-21h] BYREF
  PVOID v51; // [rsp+68h] [rbp-19h] BYREF
  __int64 v52; // [rsp+70h] [rbp-11h] BYREF
  int v53; // [rsp+78h] [rbp-9h]
  __int64 v54; // [rsp+80h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp+7h] BYREF
  __int64 v57; // [rsp+F0h] [rbp+6Fh] BYREF
  unsigned int v58; // [rsp+F8h] [rbp+77h] BYREF

  v5 = a5;
  v6 = 0;
  Size = 584;
  P = 0;
  v51 = 0;
  v8 = -1073741823;
  Src = 0;
  v49 = 0;
  v58 = 0;
  v52 = 0;
  v54 = 0;
  LODWORD(v57) = 0;
  v47 = 0;
  v53 = -1;
  DestinationString = 0;
  if ( !a4 )
  {
    CurrentProcess = *(_QWORD *)(a3 + 3312);
    ValidEA = CipSmartlockerGetValidEA(a1, &Size, (const char **)&Src, (char **)&P);
    v11 = Src;
    v8 = 0;
    if ( ValidEA != -1073741275 )
      v8 = ValidEA;
    if ( !*(_QWORD *)(a3 + 2320) && Src )
    {
      v12 = (unsigned int)Size;
      Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1668499779);
      *(_QWORD *)(a3 + 2320) = Pool2;
      if ( !Pool2 )
      {
LABEL_7:
        v8 = -1073741801;
        goto LABEL_82;
      }
      memmove(Pool2, v11, v12);
    }
    if ( !CurrentProcess )
      CurrentProcess = PsGetCurrentProcess();
    if ( !*(_QWORD *)(a3 + 2328) )
    {
      OriginClaimByProcess = CipGetOriginClaimByProcess(CurrentProcess, (char *)&Size + 4, &v49, &v51);
      v15 = v49;
      v8 = 0;
      if ( OriginClaimByProcess != -1073741275 )
        v8 = OriginClaimByProcess;
      if ( v49 )
      {
        v16 = HIDWORD(Size);
        v17 = (void *)ExAllocatePool2(258, HIDWORD(Size), 1668499779);
        *(_QWORD *)(a3 + 2328) = v17;
        if ( !v17 )
          goto LABEL_7;
        memmove(v17, v15, v16);
      }
    }
    if ( v11 )
    {
      v18 = CiTrustedInstallerValid((PCWSTR)v11 + 30);
      if ( *((_DWORD *)v11 + 13) >= (unsigned int)g_trustedOriginClaimId )
      {
        if ( v18 )
        {
          v19 = *((_DWORD *)v11 + 2);
          if ( v19 != 2 && v19 <= 4 )
          {
            v20 = *((_DWORD *)v11 + 1);
            v8 = 0;
            if ( !v20 )
            {
              *v5 |= 1u;
              goto LABEL_27;
            }
            if ( v20 == 1 )
            {
              *v5 |= 0x1002u;
              goto LABEL_27;
            }
          }
        }
      }
      v8 = -1073741823;
    }
  }
LABEL_27:
  v21 = 694;
  if ( a2 )
  {
    while ( 1 )
    {
      v6 = ExAllocatePool2(258, v21, 1098149235);
      if ( !v6 )
        goto LABEL_7;
      v22 = SeQuerySecurityAttributesToken(a2, L"24", 1, v6, v21, &v58);
      v23 = 4;
      if ( v22 != -1073741789 )
      {
        if ( v22 < 0 )
        {
LABEL_45:
          ExFreePoolWithTag((PVOID)v6, 0x41746D73u);
          v8 = -1073741823;
        }
        else
        {
          v8 = -1073741823;
          if ( *(_DWORD *)(v6 + 4) )
          {
            v24 = *(_QWORD *)(v6 + 8);
            if ( *(_WORD *)(v24 + 16) == 16 )
            {
              v25 = *(__int64 **)(v24 + 32);
              if ( *((_DWORD *)v25 + 2) >= 0x40u )
              {
                if ( (v26 = *v25, v27 = *(_DWORD *)(v26 + 8), (v27 & 0xFFFFFFFC) == 0) && v27 != 2 || v27 == 4 )
                {
                  v28 = *(_DWORD *)(v26 + 4);
                  v8 = 0;
                  if ( v28 )
                  {
                    if ( v28 == 1 )
                      *v5 |= 0x2000u;
                    else
                      v8 = -1073741823;
                  }
                  else
                  {
                    *v5 |= 0x4001u;
                  }
                }
              }
            }
          }
          ExFreePoolWithTag((PVOID)v6, 0x41746D73u);
        }
        v6 = 0;
        v29 = 678;
        if ( (*(_DWORD *)a3 & 0x10) != 0 )
        {
          while ( 1 )
          {
            v6 = ExAllocatePool2(258, v29, 1098149235);
            if ( !v6 )
            {
              v8 = -1073741801;
              goto LABEL_79;
            }
            v30 = SeQuerySecurityAttributesToken(a2, L"`b", 1, v6, v29, &v58);
            v8 = v30;
            if ( v30 != -1073741789 )
              break;
            if ( v29 >= v58 )
              goto LABEL_77;
            v29 = v58;
            ExFreePoolWithTag((PVOID)v6, 0x41746D73u);
          }
          if ( v30 < 0 )
          {
LABEL_77:
            ExFreePoolWithTag((PVOID)v6, 0x41746D73u);
            v6 = 0;
          }
          else if ( *(_DWORD *)(v6 + 4) )
          {
            v31 = *(_QWORD *)(v6 + 8);
            if ( *(_WORD *)(v31 + 16) == 16 )
            {
              v32 = *(int ***)(v31 + 32);
              if ( *((_DWORD *)v32 + 2) == 524 )
              {
                v33 = *v32;
                v34 = v33;
                *((_WORD *)v33 + 261) = 0;
                v35 = (_OWORD *)(a3 + 1536);
                do
                {
                  *v35 = *v34;
                  v35[1] = v34[1];
                  v35[2] = v34[2];
                  v35[3] = v34[3];
                  v35[4] = v34[4];
                  v35[5] = v34[5];
                  v35[6] = v34[6];
                  v36 = v34[7];
                  v34 += 8;
                  v35[7] = v36;
                  v35 += 8;
                  --v23;
                }
                while ( v23 );
                v37 = *(_OWORD *)((char *)v34 - 4);
                *(_DWORD *)(a3 + 1528) = 1;
                *(_OWORD *)((char *)v35 - 4) = v37;
                if ( (g_CiPolicyState & 0x4000) == 0 )
                {
                  v38 = *v33;
                  if ( (*v33 & 0x22) == 2 )
                  {
                    v8 = 0;
                    *v5 |= 0x1002u;
                  }
                  else if ( (v38 & 0x10) != 0 )
                  {
                    v8 = 0;
                    *v5 |= 0x8002u;
                  }
                  else if ( (v38 & 8) != 0 )
                  {
                    v8 = 0;
                    *v5 |= 0x10002u;
                  }
                }
                if ( (*v33 & 0x80) != 0 )
                {
                  *v5 |= 0x400u;
                  if ( (unsigned int)CipCheckForExtensionAgainstList(v33 + 1, DangerousExtensions) )
                    *v5 |= 0x800u;
                }
                v39 = (const wchar_t *)(v33 + 1);
                v40 = CipCheckForExtensionAgainstList(v33 + 1, &InstallerExtensions);
                if ( v40 || (*v5 & 0x800) != 0 )
                {
                  if ( (*(_DWORD *)(a3 + 2360) & 0x800) != 0 )
                  {
                    v41 = *(_DWORD *)(a3 + 2204);
LABEL_71:
                    if ( v41 > 1 )
                      goto LABEL_79;
                    goto LABEL_72;
                  }
                  RtlInitUnicodeString(&DestinationString, (PCWSTR)v33 + 2);
                  v42 = CiCatDbSmartlockerDefenderCheck(
                          &DestinationString,
                          *(struct _KPROCESS **)(a3 + 3312),
                          0,
                          0,
                          (unsigned int *)&v57,
                          &v47,
                          &v52,
                          &v54);
                  *(_DWORD *)(a3 + 2200) = v42;
                  if ( v42 >= 0 )
                  {
                    v41 = v53;
                    v43 = v47;
                    v44 = v57;
                    *(_DWORD *)(a3 + 2360) |= 0x800u;
                    *(_DWORD *)(a3 + 2204) = v41;
                    v8 = CiHandleDefenderSignals(a3, v44, (__int64)v43, 1);
                    if ( !v40 || v41 != 1 )
                      goto LABEL_71;
                    *(_DWORD *)(a3 + 992) = 64;
                    wcsncpy_s((wchar_t *)(a3 + 996), 0x104u, v39, 0x104u);
                    *(_WORD *)(a3 + 1514) = 0;
LABEL_72:
                    *v5 &= ~0x800u;
                  }
                }
              }
            }
          }
LABEL_79:
          *(_DWORD *)(a3 + 1532) = 1;
        }
        break;
      }
      if ( v21 >= v58 )
        goto LABEL_45;
      v21 = v58;
      ExFreePoolWithTag((PVOID)v6, 0x41746D73u);
    }
  }
  if ( *v5 )
    v8 = 0;
LABEL_82:
  if ( P )
    ExFreePoolWithTag(P, 0x45746D73u);
  if ( v51 )
    ExFreePoolWithTag(v51, 0x45746D73u);
  if ( v6 )
    ExFreePoolWithTag((PVOID)v6, 0x41746D73u);
  CiCatDbFreeExtraInfoFromDefender(v47);
  return v8;
}

```

## disassembly

```asm
0x1800c80fc  mov     [rsp-8+arg_0], rbx
0x1800c8101  mov     [rsp-8+arg_8], rdx
0x1800c8106  push    rbp
0x1800c8107  push    rsi
0x1800c8108  push    rdi
0x1800c8109  push    r12
0x1800c810b  push    r13
0x1800c810d  push    r14
0x1800c810f  push    r15
0x1800c8111  lea     rbp, [rsp-1Fh]
0x1800c8116  sub     rsp, 0A0h
0x1800c811d  mov     rsi, [rbp+4Fh+arg_20]
0x1800c8121  xor     edi, edi
0x1800c8123  mov     dword ptr [rbp+4Fh+Size], 248h
0x1800c812a  xorps   xmm0, xmm0
0x1800c812d  mov     [rbp+4Fh+P], 0
0x1800c8135  mov     r15, r8
0x1800c8138  mov     [rbp+4Fh+var_68], 0
0x1800c8140  mov     ebx, 0C0000001h
0x1800c8145  mov     [rbp+4Fh+Src], 0
0x1800c814d  mov     [rbp+4Fh+var_78], 0
0x1800c8155  mov     dword ptr [rbp+4Fh+Size+4], 0
0x1800c815c  mov     [rbp+4Fh+arg_18], edi
0x1800c815f  mov     [rbp+4Fh+var_60], rdi
0x1800c8163  mov     [rbp+4Fh+var_50], rdi
0x1800c8167  mov     dword ptr [rbp+4Fh+arg_10], edi
0x1800c816a  mov     [rbp+4Fh+var_88], rdi
0x1800c816e  mov     [rbp+4Fh+var_58], 0FFFFFFFFh
0x1800c8175  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800c8179  test    r9d, r9d
0x1800c817c  jnz     loc_1800C82CF
0x1800c8182  mov     r13, [r8+0CF0h]
0x1800c8189  lea     r9, [rbp+4Fh+P]
0x1800c818d  lea     r8, [rbp+4Fh+Src]
0x1800c8191  lea     rdx, [rbp+4Fh+Size]
0x1800c8195  call    CipSmartlockerGetValidEA
0x1800c819a  mov     r14, [rbp+4Fh+Src]
0x1800c819e  xor     ebx, ebx
0x1800c81a0  cmp     eax, 0C0000225h
0x1800c81a5  cmovnz  ebx, eax
0x1800c81a8  cmp     [r15+910h], rdi
0x1800c81af  jnz     short loc_1800C81F8
0x1800c81b1  test    r14, r14
0x1800c81b4  jz      short loc_1800C81F8
0x1800c81b6  mov     r12d, dword ptr [rbp+4Fh+Size]
0x1800c81ba  mov     r8d, 63734943h
0x1800c81c0  mov     edx, r12d
0x1800c81c3  mov     ecx, 102h
0x1800c81c8  call    cs:__imp_ExAllocatePool2
0x1800c81cf  nop     dword ptr [rax+rax+00h]
0x1800c81d4  mov     [r15+910h], rax
0x1800c81db  test    rax, rax
0x1800c81de  jnz     short loc_1800C81EA
0x1800c81e0  mov     ebx, 0C0000017h
0x1800c81e5  jmp     loc_1800C86E2
0x1800c81ea  mov     r8, r12; Size
0x1800c81ed  mov     rdx, r14; Src
0x1800c81f0  mov     rcx, rax; void *
0x1800c81f3  call    memmove
0x1800c81f8  test    r13, r13
0x1800c81fb  jnz     short loc_1800C820C
0x1800c81fd  call    cs:__imp_PsGetCurrentProcess
0x1800c8204  nop     dword ptr [rax+rax+00h]
0x1800c8209  mov     r13, rax
0x1800c820c  cmp     [r15+918h], rdi
0x1800c8213  jnz     short loc_1800C8278
0x1800c8215  lea     r9, [rbp+4Fh+var_68]
0x1800c8219  mov     rcx, r13
0x1800c821c  lea     r8, [rbp+4Fh+var_78]
0x1800c8220  lea     rdx, [rbp+4Fh+Size+4]
0x1800c8224  call    CipGetOriginClaimByProcess
0x1800c8229  mov     r13, [rbp+4Fh+var_78]
0x1800c822d  xor     ebx, ebx
0x1800c822f  cmp     eax, 0C0000225h
0x1800c8234  cmovnz  ebx, eax
0x1800c8237  test    r13, r13
0x1800c823a  jz      short loc_1800C8278
0x1800c823c  mov     r12d, dword ptr [rbp+4Fh+Size+4]
0x1800c8240  mov     r8d, 63734943h
0x1800c8246  mov     edx, r12d
0x1800c8249  mov     ecx, 102h
0x1800c824e  call    cs:__imp_ExAllocatePool2
0x1800c8255  nop     dword ptr [rax+rax+00h]
0x1800c825a  mov     [r15+918h], rax
0x1800c8261  test    rax, rax
0x1800c8264  jz      loc_1800C81E0
0x1800c826a  mov     r8d, r12d; Size
0x1800c826d  mov     rdx, r13; Src
0x1800c8270  mov     rcx, rax; void *
0x1800c8273  call    memmove
0x1800c8278  test    r14, r14
0x1800c827b  jz      short loc_1800C82CF
0x1800c827d  lea     rcx, [r14+3Ch]; SourceString
0x1800c8281  mov     rdx, rsi
0x1800c8284  call    CiTrustedInstallerValid
0x1800c8289  mov     cl, al
0x1800c828b  mov     eax, cs:g_trustedOriginClaimId
0x1800c8291  cmp     [r14+34h], eax
0x1800c8295  jb      short loc_1800C82CA
0x1800c8297  test    cl, cl
0x1800c8299  jz      short loc_1800C82CA
0x1800c829b  mov     eax, [r14+8]
0x1800c829f  cmp     eax, 2
0x1800c82a2  jz      short loc_1800C82CA
0x1800c82a4  cmp     eax, 0FFFFFFFFh
0x1800c82a7  jle     short loc_1800C82CA
0x1800c82a9  cmp     eax, 5
0x1800c82ac  jge     short loc_1800C82CA
0x1800c82ae  mov     ecx, [r14+4]
0x1800c82b2  xor     ebx, ebx
0x1800c82b4  test    ecx, ecx
0x1800c82b6  jz      short loc_1800C82C5
0x1800c82b8  cmp     ecx, 1
0x1800c82bb  jnz     short loc_1800C82CA
0x1800c82bd  or      dword ptr [rsi], 1002h
0x1800c82c3  jmp     short loc_1800C82CF
0x1800c82c5  or      dword ptr [rsi], 1
0x1800c82c8  jmp     short loc_1800C82CF
0x1800c82ca  mov     ebx, 0C0000001h
0x1800c82cf  mov     r13, [rbp+4Fh+arg_8]
0x1800c82d3  mov     r14d, 2B6h
0x1800c82d9  test    r13, r13
0x1800c82dc  jz      loc_1800C86DB
0x1800c82e2  mov     edx, r14d
0x1800c82e5  mov     ecx, 102h
0x1800c82ea  mov     r8d, 41746D73h
0x1800c82f0  call    cs:__imp_ExAllocatePool2
0x1800c82f7  nop     dword ptr [rax+rax+00h]
0x1800c82fc  mov     rdi, rax
0x1800c82ff  test    rax, rax
0x1800c8302  jz      loc_1800C81E0
0x1800c8308  lea     rax, [rbp+4Fh+arg_18]
0x1800c830c  mov     r9, rdi
0x1800c830f  mov     [rsp+0D0h+var_A8], rax
0x1800c8314  lea     rdx, a24_0; "24"
0x1800c831b  mov     r8d, 1
0x1800c8321  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800c8326  mov     rcx, r13
0x1800c8329  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800c8330  nop     dword ptr [rax+rax+00h]
0x1800c8335  mov     r12d, 4
0x1800c833b  cmp     eax, 0C0000023h
0x1800c8340  jnz     short loc_1800C8369
0x1800c8342  cmp     r14d, [rbp+4Fh+arg_18]
0x1800c8346  jnb     loc_1800C83DA
0x1800c834c  mov     r14d, [rbp+4Fh+arg_18]
0x1800c8350  mov     edx, 41746D73h; Tag
0x1800c8355  mov     rcx, rdi; P
0x1800c8358  call    cs:__imp_ExFreePoolWithTag
0x1800c835f  nop     dword ptr [rax+rax+00h]
0x1800c8364  jmp     loc_1800C82E2
0x1800c8369  test    eax, eax
0x1800c836b  js      short loc_1800C83DA
0x1800c836d  cmp     dword ptr [rdi+4], 0
0x1800c8371  mov     edx, 0C0000001h
0x1800c8376  mov     ebx, edx
0x1800c8378  jbe     short loc_1800C83C4
0x1800c837a  mov     rax, [rdi+8]
0x1800c837e  cmp     word ptr [rax+10h], 10h
0x1800c8383  jnz     short loc_1800C83C4
0x1800c8385  mov     rcx, [rax+20h]
0x1800c8389  cmp     dword ptr [rcx+8], 40h ; '@'
0x1800c838d  jb      short loc_1800C83C4
0x1800c838f  mov     rcx, [rcx]
0x1800c8392  mov     eax, [rcx+8]
0x1800c8395  test    eax, 0FFFFFFFCh
0x1800c839a  jnz     short loc_1800C83A1
0x1800c839c  cmp     eax, 2
0x1800c839f  jnz     short loc_1800C83A6
0x1800c83a1  cmp     eax, r12d
0x1800c83a4  jnz     short loc_1800C83C4
0x1800c83a6  mov     ecx, [rcx+4]
0x1800c83a9  xor     ebx, ebx
0x1800c83ab  test    ecx, ecx
0x1800c83ad  jz      short loc_1800C83BE
0x1800c83af  cmp     ecx, 1
0x1800c83b2  jz      short loc_1800C83B8
0x1800c83b4  mov     ebx, edx
0x1800c83b6  jmp     short loc_1800C83C4
0x1800c83b8  bts     dword ptr [rsi], 0Dh
0x1800c83bc  jmp     short loc_1800C83C4
0x1800c83be  or      dword ptr [rsi], 4001h
0x1800c83c4  mov     edx, 41746D73h; Tag
0x1800c83c9  mov     rcx, rdi; P
0x1800c83cc  call    cs:__imp_ExFreePoolWithTag
0x1800c83d3  nop     dword ptr [rax+rax+00h]
0x1800c83d8  jmp     short loc_1800C83F3
0x1800c83da  mov     edx, 41746D73h; Tag
0x1800c83df  mov     rcx, rdi; P
0x1800c83e2  call    cs:__imp_ExFreePoolWithTag
0x1800c83e9  nop     dword ptr [rax+rax+00h]
0x1800c83ee  mov     ebx, 0C0000001h
0x1800c83f3  mov     eax, [r15]
0x1800c83f6  xor     edi, edi
0x1800c83f8  mov     r14d, 2A6h
0x1800c83fe  test    al, 10h
0x1800c8400  jz      loc_1800C86DB
0x1800c8406  mov     edx, r14d
0x1800c8409  mov     ecx, 102h
0x1800c840e  mov     r8d, 41746D73h
0x1800c8414  call    cs:__imp_ExAllocatePool2
0x1800c841b  nop     dword ptr [rax+rax+00h]
0x1800c8420  mov     rdi, rax
0x1800c8423  test    rax, rax
0x1800c8426  jz      loc_1800C86CB
0x1800c842c  lea     rax, [rbp+4Fh+arg_18]
0x1800c8430  mov     r9, rdi
0x1800c8433  mov     [rsp+0D0h+var_A8], rax
0x1800c8438  lea     rdx, aB_1; "`b"
0x1800c843f  mov     r8d, 1
0x1800c8445  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800c844a  mov     rcx, r13
0x1800c844d  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800c8454  nop     dword ptr [rax+rax+00h]
0x1800c8459  mov     ebx, eax
0x1800c845b  cmp     eax, 0C0000023h
0x1800c8460  jnz     short loc_1800C8486
0x1800c8462  cmp     r14d, [rbp+4Fh+arg_18]
0x1800c8466  jnb     loc_1800C86B3
0x1800c846c  mov     r14d, [rbp+4Fh+arg_18]
0x1800c8470  mov     edx, 41746D73h; Tag
0x1800c8475  mov     rcx, rdi; P
0x1800c8478  call    cs:__imp_ExFreePoolWithTag
0x1800c847f  nop     dword ptr [rax+rax+00h]
0x1800c8484  jmp     short loc_1800C8406
0x1800c8486  test    eax, eax
0x1800c8488  js      loc_1800C86B3
0x1800c848e  cmp     dword ptr [rdi+4], 0
0x1800c8492  jbe     loc_1800C86D0
0x1800c8498  mov     rax, [rdi+8]
0x1800c849c  cmp     word ptr [rax+10h], 10h
0x1800c84a1  jnz     loc_1800C86D0
0x1800c84a7  mov     r14, [rax+20h]
0x1800c84ab  cmp     dword ptr [r14+8], 20Ch
0x1800c84b3  jnz     loc_1800C86D0
0x1800c84b9  mov     r14, [r14]
0x1800c84bc  xor     eax, eax
0x1800c84be  mov     rcx, r14
0x1800c84c1  mov     edx, 80h
0x1800c84c6  mov     [r14+20Ah], ax
0x1800c84ce  lea     rax, [r15+600h]
0x1800c84d5  movups  xmm0, xmmword ptr [rcx]
0x1800c84d8  movups  xmmword ptr [rax], xmm0
0x1800c84db  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c84df  movups  xmmword ptr [rax+10h], xmm1
0x1800c84e3  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c84e7  movups  xmmword ptr [rax+20h], xmm0
0x1800c84eb  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c84ef  movups  xmmword ptr [rax+30h], xmm1
0x1800c84f3  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c84f7  movups  xmmword ptr [rax+40h], xmm0
0x1800c84fb  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c84ff  movups  xmmword ptr [rax+50h], xmm1
0x1800c8503  movups  xmm0, xmmword ptr [rcx+60h]
0x1800c8507  movups  xmmword ptr [rax+60h], xmm0
0x1800c850b  movups  xmm1, xmmword ptr [rcx+70h]
0x1800c850f  add     rcx, rdx
0x1800c8512  movups  xmmword ptr [rax+70h], xmm1
0x1800c8516  add     rax, rdx
0x1800c8519  sub     r12, 1
0x1800c851d  jnz     short loc_1800C84D5
0x1800c851f  movups  xmm0, xmmword ptr [rcx-4]
0x1800c8523  mov     dword ptr [r15+5F8h], 1
0x1800c852e  movups  xmmword ptr [rax-4], xmm0
0x1800c8532  test    cs:g_CiPolicyState, 4000h
0x1800c853c  jnz     short loc_1800C856F
0x1800c853e  mov     ecx, [r14]
0x1800c8541  mov     eax, ecx
0x1800c8543  and     al, 22h
0x1800c8545  cmp     al, 2
0x1800c8547  jnz     short loc_1800C8553
0x1800c8549  xor     ebx, ebx
0x1800c854b  or      dword ptr [rsi], 1002h
0x1800c8551  jmp     short loc_1800C856F
0x1800c8553  test    cl, 10h
0x1800c8556  jz      short loc_1800C8562
0x1800c8558  xor     ebx, ebx
0x1800c855a  or      dword ptr [rsi], 8002h
0x1800c8560  jmp     short loc_1800C856F
0x1800c8562  test    cl, 8
0x1800c8565  jz      short loc_1800C856F
0x1800c8567  xor     ebx, ebx
0x1800c8569  or      dword ptr [rsi], 10002h
0x1800c856f  mov     eax, [r14]
0x1800c8572  test    dl, al
0x1800c8574  jz      short loc_1800C8592
0x1800c8576  bts     dword ptr [rsi], 0Ah
0x1800c857a  lea     rcx, [r14+4]
0x1800c857e  lea     rdx, DangerousExtensions
0x1800c8585  call    CipCheckForExtensionAgainstList
0x1800c858a  test    eax, eax
0x1800c858c  jz      short loc_1800C8592
0x1800c858e  bts     dword ptr [rsi], 0Bh
0x1800c8592  lea     r12, [r14+4]
0x1800c8596  mov     rcx, r12
0x1800c8599  lea     rdx, InstallerExtensions
0x1800c85a0  call    CipCheckForExtensionAgainstList
0x1800c85a5  mov     r13d, eax
0x1800c85a8  test    eax, eax
0x1800c85aa  jnz     short loc_1800C85B8
  ... truncated ...
```
