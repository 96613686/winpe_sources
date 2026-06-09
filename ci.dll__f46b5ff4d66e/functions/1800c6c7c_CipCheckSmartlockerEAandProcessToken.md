# CipCheckSmartlockerEAandProcessToken

- ea: `0x1800c6c7c`
- end: `0x1800c72d8`
- name: `CipCheckSmartlockerEAandProcessToken`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c6340`

## callees

- `0x18002c040`
- `0x18007281c`
- `0x180073540`
- `0x1800735d4`
- `0x1800bd14c`
- `0x1800bd1c4`
- `0x1800c6c08`
- `0x1800c6c7c`
- `0x1800c7354`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800c716b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800c716b`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6d48`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6dce`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6e70`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6f94`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6d48`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6dce`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6e70`
- `ntoskrnl!ExAllocatePool2` at `0x1800c6f94`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800c6d7d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800c6d7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6ed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6f4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6f62`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6ff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c723b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c7272`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c7289`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c72a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6ed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6f4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6f62`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c6ff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c723b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c7272`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c7289`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c72a2`
- `ntoskrnl!wcsncpy_s` at `0x1800c7218`
- `ntoskrnl!wcsncpy_s` at `0x1800c7218`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c6ea9`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c6fcd`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c6ea9`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c6fcd`

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
    ValidEA = CipSmartlockerGetValidEA(a1, &Size, &Src, &P);
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
0x1800c6c7c  mov     [rsp-8+arg_0], rbx
0x1800c6c81  mov     [rsp-8+arg_8], rdx
0x1800c6c86  push    rbp
0x1800c6c87  push    rsi
0x1800c6c88  push    rdi
0x1800c6c89  push    r12
0x1800c6c8b  push    r13
0x1800c6c8d  push    r14
0x1800c6c8f  push    r15
0x1800c6c91  lea     rbp, [rsp-1Fh]
0x1800c6c96  sub     rsp, 0A0h
0x1800c6c9d  mov     rsi, [rbp+4Fh+arg_20]
0x1800c6ca1  xor     edi, edi
0x1800c6ca3  mov     dword ptr [rbp+4Fh+Size], 248h
0x1800c6caa  xorps   xmm0, xmm0
0x1800c6cad  mov     [rbp+4Fh+P], 0
0x1800c6cb5  mov     r15, r8
0x1800c6cb8  mov     [rbp+4Fh+var_68], 0
0x1800c6cc0  mov     ebx, 0C0000001h
0x1800c6cc5  mov     [rbp+4Fh+Src], 0
0x1800c6ccd  mov     [rbp+4Fh+var_78], 0
0x1800c6cd5  mov     dword ptr [rbp+4Fh+Size+4], 0
0x1800c6cdc  mov     [rbp+4Fh+arg_18], edi
0x1800c6cdf  mov     [rbp+4Fh+var_60], rdi
0x1800c6ce3  mov     [rbp+4Fh+var_50], rdi
0x1800c6ce7  mov     dword ptr [rbp+4Fh+arg_10], edi
0x1800c6cea  mov     [rbp+4Fh+var_88], rdi
0x1800c6cee  mov     [rbp+4Fh+var_58], 0FFFFFFFFh
0x1800c6cf5  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800c6cf9  test    r9d, r9d
0x1800c6cfc  jnz     loc_1800C6E4F
0x1800c6d02  mov     r13, [r8+0CF0h]
0x1800c6d09  lea     r9, [rbp+4Fh+P]
0x1800c6d0d  lea     r8, [rbp+4Fh+Src]
0x1800c6d11  lea     rdx, [rbp+4Fh+Size]
0x1800c6d15  call    CipSmartlockerGetValidEA
0x1800c6d1a  mov     r14, [rbp+4Fh+Src]
0x1800c6d1e  xor     ebx, ebx
0x1800c6d20  cmp     eax, 0C0000225h
0x1800c6d25  cmovnz  ebx, eax
0x1800c6d28  cmp     [r15+910h], rdi
0x1800c6d2f  jnz     short loc_1800C6D78
0x1800c6d31  test    r14, r14
0x1800c6d34  jz      short loc_1800C6D78
0x1800c6d36  mov     r12d, dword ptr [rbp+4Fh+Size]
0x1800c6d3a  mov     r8d, 63734943h
0x1800c6d40  mov     edx, r12d
0x1800c6d43  mov     ecx, 102h
0x1800c6d48  call    cs:__imp_ExAllocatePool2
0x1800c6d4f  nop     dword ptr [rax+rax+00h]
0x1800c6d54  mov     [r15+910h], rax
0x1800c6d5b  test    rax, rax
0x1800c6d5e  jnz     short loc_1800C6D6A
0x1800c6d60  mov     ebx, 0C0000017h
0x1800c6d65  jmp     loc_1800C7262
0x1800c6d6a  mov     r8, r12; Size
0x1800c6d6d  mov     rdx, r14; Src
0x1800c6d70  mov     rcx, rax; void *
0x1800c6d73  call    memmove
0x1800c6d78  test    r13, r13
0x1800c6d7b  jnz     short loc_1800C6D8C
0x1800c6d7d  call    cs:__imp_PsGetCurrentProcess
0x1800c6d84  nop     dword ptr [rax+rax+00h]
0x1800c6d89  mov     r13, rax
0x1800c6d8c  cmp     [r15+918h], rdi
0x1800c6d93  jnz     short loc_1800C6DF8
0x1800c6d95  lea     r9, [rbp+4Fh+var_68]
0x1800c6d99  mov     rcx, r13
0x1800c6d9c  lea     r8, [rbp+4Fh+var_78]
0x1800c6da0  lea     rdx, [rbp+4Fh+Size+4]
0x1800c6da4  call    CipGetOriginClaimByProcess
0x1800c6da9  mov     r13, [rbp+4Fh+var_78]
0x1800c6dad  xor     ebx, ebx
0x1800c6daf  cmp     eax, 0C0000225h
0x1800c6db4  cmovnz  ebx, eax
0x1800c6db7  test    r13, r13
0x1800c6dba  jz      short loc_1800C6DF8
0x1800c6dbc  mov     r12d, dword ptr [rbp+4Fh+Size+4]
0x1800c6dc0  mov     r8d, 63734943h
0x1800c6dc6  mov     edx, r12d
0x1800c6dc9  mov     ecx, 102h
0x1800c6dce  call    cs:__imp_ExAllocatePool2
0x1800c6dd5  nop     dword ptr [rax+rax+00h]
0x1800c6dda  mov     [r15+918h], rax
0x1800c6de1  test    rax, rax
0x1800c6de4  jz      loc_1800C6D60
0x1800c6dea  mov     r8d, r12d; Size
0x1800c6ded  mov     rdx, r13; Src
0x1800c6df0  mov     rcx, rax; void *
0x1800c6df3  call    memmove
0x1800c6df8  test    r14, r14
0x1800c6dfb  jz      short loc_1800C6E4F
0x1800c6dfd  lea     rcx, [r14+3Ch]; SourceString
0x1800c6e01  mov     rdx, rsi
0x1800c6e04  call    CiTrustedInstallerValid
0x1800c6e09  mov     cl, al
0x1800c6e0b  mov     eax, cs:g_trustedOriginClaimId
0x1800c6e11  cmp     [r14+34h], eax
0x1800c6e15  jb      short loc_1800C6E4A
0x1800c6e17  test    cl, cl
0x1800c6e19  jz      short loc_1800C6E4A
0x1800c6e1b  mov     eax, [r14+8]
0x1800c6e1f  cmp     eax, 2
0x1800c6e22  jz      short loc_1800C6E4A
0x1800c6e24  cmp     eax, 0FFFFFFFFh
0x1800c6e27  jle     short loc_1800C6E4A
0x1800c6e29  cmp     eax, 5
0x1800c6e2c  jge     short loc_1800C6E4A
0x1800c6e2e  mov     ecx, [r14+4]
0x1800c6e32  xor     ebx, ebx
0x1800c6e34  test    ecx, ecx
0x1800c6e36  jz      short loc_1800C6E45
0x1800c6e38  cmp     ecx, 1
0x1800c6e3b  jnz     short loc_1800C6E4A
0x1800c6e3d  or      dword ptr [rsi], 1002h
0x1800c6e43  jmp     short loc_1800C6E4F
0x1800c6e45  or      dword ptr [rsi], 1
0x1800c6e48  jmp     short loc_1800C6E4F
0x1800c6e4a  mov     ebx, 0C0000001h
0x1800c6e4f  mov     r13, [rbp+4Fh+arg_8]
0x1800c6e53  mov     r14d, 2B6h
0x1800c6e59  test    r13, r13
0x1800c6e5c  jz      loc_1800C725B
0x1800c6e62  mov     edx, r14d
0x1800c6e65  mov     ecx, 102h
0x1800c6e6a  mov     r8d, 41746D73h
0x1800c6e70  call    cs:__imp_ExAllocatePool2
0x1800c6e77  nop     dword ptr [rax+rax+00h]
0x1800c6e7c  mov     rdi, rax
0x1800c6e7f  test    rax, rax
0x1800c6e82  jz      loc_1800C6D60
0x1800c6e88  lea     rax, [rbp+4Fh+arg_18]
0x1800c6e8c  mov     r9, rdi
0x1800c6e8f  mov     [rsp+0D0h+var_A8], rax
0x1800c6e94  lea     rdx, a24_0; "24"
0x1800c6e9b  mov     r8d, 1
0x1800c6ea1  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800c6ea6  mov     rcx, r13
0x1800c6ea9  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800c6eb0  nop     dword ptr [rax+rax+00h]
0x1800c6eb5  mov     r12d, 4
0x1800c6ebb  cmp     eax, 0C0000023h
0x1800c6ec0  jnz     short loc_1800C6EE9
0x1800c6ec2  cmp     r14d, [rbp+4Fh+arg_18]
0x1800c6ec6  jnb     loc_1800C6F5A
0x1800c6ecc  mov     r14d, [rbp+4Fh+arg_18]
0x1800c6ed0  mov     edx, 41746D73h; Tag
0x1800c6ed5  mov     rcx, rdi; P
0x1800c6ed8  call    cs:__imp_ExFreePoolWithTag
0x1800c6edf  nop     dword ptr [rax+rax+00h]
0x1800c6ee4  jmp     loc_1800C6E62
0x1800c6ee9  test    eax, eax
0x1800c6eeb  js      short loc_1800C6F5A
0x1800c6eed  cmp     dword ptr [rdi+4], 0
0x1800c6ef1  mov     edx, 0C0000001h
0x1800c6ef6  mov     ebx, edx
0x1800c6ef8  jbe     short loc_1800C6F44
0x1800c6efa  mov     rax, [rdi+8]
0x1800c6efe  cmp     word ptr [rax+10h], 10h
0x1800c6f03  jnz     short loc_1800C6F44
0x1800c6f05  mov     rcx, [rax+20h]
0x1800c6f09  cmp     dword ptr [rcx+8], 40h ; '@'
0x1800c6f0d  jb      short loc_1800C6F44
0x1800c6f0f  mov     rcx, [rcx]
0x1800c6f12  mov     eax, [rcx+8]
0x1800c6f15  test    eax, 0FFFFFFFCh
0x1800c6f1a  jnz     short loc_1800C6F21
0x1800c6f1c  cmp     eax, 2
0x1800c6f1f  jnz     short loc_1800C6F26
0x1800c6f21  cmp     eax, r12d
0x1800c6f24  jnz     short loc_1800C6F44
0x1800c6f26  mov     ecx, [rcx+4]
0x1800c6f29  xor     ebx, ebx
0x1800c6f2b  test    ecx, ecx
0x1800c6f2d  jz      short loc_1800C6F3E
0x1800c6f2f  cmp     ecx, 1
0x1800c6f32  jz      short loc_1800C6F38
0x1800c6f34  mov     ebx, edx
0x1800c6f36  jmp     short loc_1800C6F44
0x1800c6f38  bts     dword ptr [rsi], 0Dh
0x1800c6f3c  jmp     short loc_1800C6F44
0x1800c6f3e  or      dword ptr [rsi], 4001h
0x1800c6f44  mov     edx, 41746D73h; Tag
0x1800c6f49  mov     rcx, rdi; P
0x1800c6f4c  call    cs:__imp_ExFreePoolWithTag
0x1800c6f53  nop     dword ptr [rax+rax+00h]
0x1800c6f58  jmp     short loc_1800C6F73
0x1800c6f5a  mov     edx, 41746D73h; Tag
0x1800c6f5f  mov     rcx, rdi; P
0x1800c6f62  call    cs:__imp_ExFreePoolWithTag
0x1800c6f69  nop     dword ptr [rax+rax+00h]
0x1800c6f6e  mov     ebx, 0C0000001h
0x1800c6f73  mov     eax, [r15]
0x1800c6f76  xor     edi, edi
0x1800c6f78  mov     r14d, 2A6h
0x1800c6f7e  test    al, 10h
0x1800c6f80  jz      loc_1800C725B
0x1800c6f86  mov     edx, r14d
0x1800c6f89  mov     ecx, 102h
0x1800c6f8e  mov     r8d, 41746D73h
0x1800c6f94  call    cs:__imp_ExAllocatePool2
0x1800c6f9b  nop     dword ptr [rax+rax+00h]
0x1800c6fa0  mov     rdi, rax
0x1800c6fa3  test    rax, rax
0x1800c6fa6  jz      loc_1800C724B
0x1800c6fac  lea     rax, [rbp+4Fh+arg_18]
0x1800c6fb0  mov     r9, rdi
0x1800c6fb3  mov     [rsp+0D0h+var_A8], rax
0x1800c6fb8  lea     rdx, aB_1; "`b"
0x1800c6fbf  mov     r8d, 1
0x1800c6fc5  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800c6fca  mov     rcx, r13
0x1800c6fcd  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800c6fd4  nop     dword ptr [rax+rax+00h]
0x1800c6fd9  mov     ebx, eax
0x1800c6fdb  cmp     eax, 0C0000023h
0x1800c6fe0  jnz     short loc_1800C7006
0x1800c6fe2  cmp     r14d, [rbp+4Fh+arg_18]
0x1800c6fe6  jnb     loc_1800C7233
0x1800c6fec  mov     r14d, [rbp+4Fh+arg_18]
0x1800c6ff0  mov     edx, 41746D73h; Tag
0x1800c6ff5  mov     rcx, rdi; P
0x1800c6ff8  call    cs:__imp_ExFreePoolWithTag
0x1800c6fff  nop     dword ptr [rax+rax+00h]
0x1800c7004  jmp     short loc_1800C6F86
0x1800c7006  test    eax, eax
0x1800c7008  js      loc_1800C7233
0x1800c700e  cmp     dword ptr [rdi+4], 0
0x1800c7012  jbe     loc_1800C7250
0x1800c7018  mov     rax, [rdi+8]
0x1800c701c  cmp     word ptr [rax+10h], 10h
0x1800c7021  jnz     loc_1800C7250
0x1800c7027  mov     r14, [rax+20h]
0x1800c702b  cmp     dword ptr [r14+8], 20Ch
0x1800c7033  jnz     loc_1800C7250
0x1800c7039  mov     r14, [r14]
0x1800c703c  xor     eax, eax
0x1800c703e  mov     rcx, r14
0x1800c7041  mov     edx, 80h
0x1800c7046  mov     [r14+20Ah], ax
0x1800c704e  lea     rax, [r15+600h]
0x1800c7055  movups  xmm0, xmmword ptr [rcx]
0x1800c7058  movups  xmmword ptr [rax], xmm0
0x1800c705b  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c705f  movups  xmmword ptr [rax+10h], xmm1
0x1800c7063  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c7067  movups  xmmword ptr [rax+20h], xmm0
0x1800c706b  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c706f  movups  xmmword ptr [rax+30h], xmm1
0x1800c7073  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c7077  movups  xmmword ptr [rax+40h], xmm0
0x1800c707b  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c707f  movups  xmmword ptr [rax+50h], xmm1
0x1800c7083  movups  xmm0, xmmword ptr [rcx+60h]
0x1800c7087  movups  xmmword ptr [rax+60h], xmm0
0x1800c708b  movups  xmm1, xmmword ptr [rcx+70h]
0x1800c708f  add     rcx, rdx
0x1800c7092  movups  xmmword ptr [rax+70h], xmm1
0x1800c7096  add     rax, rdx
0x1800c7099  sub     r12, 1
0x1800c709d  jnz     short loc_1800C7055
0x1800c709f  movups  xmm0, xmmword ptr [rcx-4]
0x1800c70a3  mov     dword ptr [r15+5F8h], 1
0x1800c70ae  movups  xmmword ptr [rax-4], xmm0
0x1800c70b2  test    cs:g_CiPolicyState, 4000h
0x1800c70bc  jnz     short loc_1800C70EF
0x1800c70be  mov     ecx, [r14]
0x1800c70c1  mov     eax, ecx
0x1800c70c3  and     al, 22h
0x1800c70c5  cmp     al, 2
0x1800c70c7  jnz     short loc_1800C70D3
0x1800c70c9  xor     ebx, ebx
0x1800c70cb  or      dword ptr [rsi], 1002h
0x1800c70d1  jmp     short loc_1800C70EF
0x1800c70d3  test    cl, 10h
0x1800c70d6  jz      short loc_1800C70E2
0x1800c70d8  xor     ebx, ebx
0x1800c70da  or      dword ptr [rsi], 8002h
0x1800c70e0  jmp     short loc_1800C70EF
0x1800c70e2  test    cl, 8
0x1800c70e5  jz      short loc_1800C70EF
0x1800c70e7  xor     ebx, ebx
0x1800c70e9  or      dword ptr [rsi], 10002h
0x1800c70ef  mov     eax, [r14]
0x1800c70f2  test    dl, al
0x1800c70f4  jz      short loc_1800C7112
0x1800c70f6  bts     dword ptr [rsi], 0Ah
0x1800c70fa  lea     rcx, [r14+4]
0x1800c70fe  lea     rdx, DangerousExtensions
0x1800c7105  call    CipCheckForExtensionAgainstList
0x1800c710a  test    eax, eax
0x1800c710c  jz      short loc_1800C7112
0x1800c710e  bts     dword ptr [rsi], 0Bh
0x1800c7112  lea     r12, [r14+4]
0x1800c7116  mov     rcx, r12
0x1800c7119  lea     rdx, InstallerExtensions
0x1800c7120  call    CipCheckForExtensionAgainstList
0x1800c7125  mov     r13d, eax
0x1800c7128  test    eax, eax
0x1800c712a  jnz     short loc_1800C7138
  ... truncated ...
```
