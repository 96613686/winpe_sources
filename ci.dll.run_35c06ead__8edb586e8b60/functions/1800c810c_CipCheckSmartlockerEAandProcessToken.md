# CipCheckSmartlockerEAandProcessToken

- ea: `0x1800c810c`
- end: `0x1800c8768`
- name: `CipCheckSmartlockerEAandProcessToken`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c77d0`

## callees

- `0x18002c200`
- `0x180073dac`
- `0x180074ad0`
- `0x180074b64`
- `0x1800be46c`
- `0x1800be4e4`
- `0x1800c8098`
- `0x1800c810c`
- `0x1800c87e4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800c85fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800c85fb`
- `ntoskrnl!ExAllocatePool2` at `0x1800c81d8`
- `ntoskrnl!ExAllocatePool2` at `0x1800c825e`
- `ntoskrnl!ExAllocatePool2` at `0x1800c8300`
- `ntoskrnl!ExAllocatePool2` at `0x1800c8424`
- `ntoskrnl!ExAllocatePool2` at `0x1800c81d8`
- `ntoskrnl!ExAllocatePool2` at `0x1800c825e`
- `ntoskrnl!ExAllocatePool2` at `0x1800c8300`
- `ntoskrnl!ExAllocatePool2` at `0x1800c8424`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800c820d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800c820d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c86cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8702`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8719`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8732`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c83f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c86cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8702`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8719`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800c8732`
- `ntoskrnl!wcsncpy_s` at `0x1800c86a8`
- `ntoskrnl!wcsncpy_s` at `0x1800c86a8`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c8339`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c845d`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c8339`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1800c845d`

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
    CurrentProcess = *(_QWORD *)(a3 + 3328);
    ValidEA = CipSmartlockerGetValidEA(a1, &Size, &Src, &P);
    v11 = Src;
    v8 = 0;
    if ( ValidEA != -1073741275 )
      v8 = ValidEA;
    if ( !*(_QWORD *)(a3 + 2328) && Src )
    {
      v12 = (unsigned int)Size;
      Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1668499779);
      *(_QWORD *)(a3 + 2328) = Pool2;
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
    if ( !*(_QWORD *)(a3 + 2336) )
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
        *(_QWORD *)(a3 + 2336) = v17;
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
                  if ( (*(_DWORD *)(a3 + 2368) & 0x800) != 0 )
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
                          *(struct _KPROCESS **)(a3 + 3328),
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
                    *(_DWORD *)(a3 + 2368) |= 0x800u;
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
0x1800c810c  mov     [rsp-8+arg_0], rbx
0x1800c8111  mov     [rsp-8+arg_8], rdx
0x1800c8116  push    rbp
0x1800c8117  push    rsi
0x1800c8118  push    rdi
0x1800c8119  push    r12
0x1800c811b  push    r13
0x1800c811d  push    r14
0x1800c811f  push    r15
0x1800c8121  lea     rbp, [rsp-1Fh]
0x1800c8126  sub     rsp, 0A0h
0x1800c812d  mov     rsi, [rbp+4Fh+arg_20]
0x1800c8131  xor     edi, edi
0x1800c8133  mov     dword ptr [rbp+4Fh+Size], 248h
0x1800c813a  xorps   xmm0, xmm0
0x1800c813d  mov     [rbp+4Fh+P], 0
0x1800c8145  mov     r15, r8
0x1800c8148  mov     [rbp+4Fh+var_68], 0
0x1800c8150  mov     ebx, 0C0000001h
0x1800c8155  mov     [rbp+4Fh+Src], 0
0x1800c815d  mov     [rbp+4Fh+var_78], 0
0x1800c8165  mov     dword ptr [rbp+4Fh+Size+4], 0
0x1800c816c  mov     [rbp+4Fh+arg_18], edi
0x1800c816f  mov     [rbp+4Fh+var_60], rdi
0x1800c8173  mov     [rbp+4Fh+var_50], rdi
0x1800c8177  mov     dword ptr [rbp+4Fh+arg_10], edi
0x1800c817a  mov     [rbp+4Fh+var_88], rdi
0x1800c817e  mov     [rbp+4Fh+var_58], 0FFFFFFFFh
0x1800c8185  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800c8189  test    r9d, r9d
0x1800c818c  jnz     loc_1800C82DF
0x1800c8192  mov     r13, [r8+0D00h]
0x1800c8199  lea     r9, [rbp+4Fh+P]
0x1800c819d  lea     r8, [rbp+4Fh+Src]
0x1800c81a1  lea     rdx, [rbp+4Fh+Size]
0x1800c81a5  call    CipSmartlockerGetValidEA
0x1800c81aa  mov     r14, [rbp+4Fh+Src]
0x1800c81ae  xor     ebx, ebx
0x1800c81b0  cmp     eax, 0C0000225h
0x1800c81b5  cmovnz  ebx, eax
0x1800c81b8  cmp     [r15+918h], rdi
0x1800c81bf  jnz     short loc_1800C8208
0x1800c81c1  test    r14, r14
0x1800c81c4  jz      short loc_1800C8208
0x1800c81c6  mov     r12d, dword ptr [rbp+4Fh+Size]
0x1800c81ca  mov     r8d, 63734943h
0x1800c81d0  mov     edx, r12d
0x1800c81d3  mov     ecx, 102h
0x1800c81d8  call    cs:__imp_ExAllocatePool2
0x1800c81df  nop     dword ptr [rax+rax+00h]
0x1800c81e4  mov     [r15+918h], rax
0x1800c81eb  test    rax, rax
0x1800c81ee  jnz     short loc_1800C81FA
0x1800c81f0  mov     ebx, 0C0000017h
0x1800c81f5  jmp     loc_1800C86F2
0x1800c81fa  mov     r8, r12; Size
0x1800c81fd  mov     rdx, r14; Src
0x1800c8200  mov     rcx, rax; void *
0x1800c8203  call    memmove
0x1800c8208  test    r13, r13
0x1800c820b  jnz     short loc_1800C821C
0x1800c820d  call    cs:__imp_PsGetCurrentProcess
0x1800c8214  nop     dword ptr [rax+rax+00h]
0x1800c8219  mov     r13, rax
0x1800c821c  cmp     [r15+920h], rdi
0x1800c8223  jnz     short loc_1800C8288
0x1800c8225  lea     r9, [rbp+4Fh+var_68]
0x1800c8229  mov     rcx, r13
0x1800c822c  lea     r8, [rbp+4Fh+var_78]
0x1800c8230  lea     rdx, [rbp+4Fh+Size+4]
0x1800c8234  call    CipGetOriginClaimByProcess
0x1800c8239  mov     r13, [rbp+4Fh+var_78]
0x1800c823d  xor     ebx, ebx
0x1800c823f  cmp     eax, 0C0000225h
0x1800c8244  cmovnz  ebx, eax
0x1800c8247  test    r13, r13
0x1800c824a  jz      short loc_1800C8288
0x1800c824c  mov     r12d, dword ptr [rbp+4Fh+Size+4]
0x1800c8250  mov     r8d, 63734943h
0x1800c8256  mov     edx, r12d
0x1800c8259  mov     ecx, 102h
0x1800c825e  call    cs:__imp_ExAllocatePool2
0x1800c8265  nop     dword ptr [rax+rax+00h]
0x1800c826a  mov     [r15+920h], rax
0x1800c8271  test    rax, rax
0x1800c8274  jz      loc_1800C81F0
0x1800c827a  mov     r8d, r12d; Size
0x1800c827d  mov     rdx, r13; Src
0x1800c8280  mov     rcx, rax; void *
0x1800c8283  call    memmove
0x1800c8288  test    r14, r14
0x1800c828b  jz      short loc_1800C82DF
0x1800c828d  lea     rcx, [r14+3Ch]; SourceString
0x1800c8291  mov     rdx, rsi
0x1800c8294  call    CiTrustedInstallerValid
0x1800c8299  mov     cl, al
0x1800c829b  mov     eax, cs:g_trustedOriginClaimId
0x1800c82a1  cmp     [r14+34h], eax
0x1800c82a5  jb      short loc_1800C82DA
0x1800c82a7  test    cl, cl
0x1800c82a9  jz      short loc_1800C82DA
0x1800c82ab  mov     eax, [r14+8]
0x1800c82af  cmp     eax, 2
0x1800c82b2  jz      short loc_1800C82DA
0x1800c82b4  cmp     eax, 0FFFFFFFFh
0x1800c82b7  jle     short loc_1800C82DA
0x1800c82b9  cmp     eax, 5
0x1800c82bc  jge     short loc_1800C82DA
0x1800c82be  mov     ecx, [r14+4]
0x1800c82c2  xor     ebx, ebx
0x1800c82c4  test    ecx, ecx
0x1800c82c6  jz      short loc_1800C82D5
0x1800c82c8  cmp     ecx, 1
0x1800c82cb  jnz     short loc_1800C82DA
0x1800c82cd  or      dword ptr [rsi], 1002h
0x1800c82d3  jmp     short loc_1800C82DF
0x1800c82d5  or      dword ptr [rsi], 1
0x1800c82d8  jmp     short loc_1800C82DF
0x1800c82da  mov     ebx, 0C0000001h
0x1800c82df  mov     r13, [rbp+4Fh+arg_8]
0x1800c82e3  mov     r14d, 2B6h
0x1800c82e9  test    r13, r13
0x1800c82ec  jz      loc_1800C86EB
0x1800c82f2  mov     edx, r14d
0x1800c82f5  mov     ecx, 102h
0x1800c82fa  mov     r8d, 41746D73h
0x1800c8300  call    cs:__imp_ExAllocatePool2
0x1800c8307  nop     dword ptr [rax+rax+00h]
0x1800c830c  mov     rdi, rax
0x1800c830f  test    rax, rax
0x1800c8312  jz      loc_1800C81F0
0x1800c8318  lea     rax, [rbp+4Fh+arg_18]
0x1800c831c  mov     r9, rdi
0x1800c831f  mov     [rsp+0D0h+var_A8], rax
0x1800c8324  lea     rdx, a24_0; "24"
0x1800c832b  mov     r8d, 1
0x1800c8331  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800c8336  mov     rcx, r13
0x1800c8339  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800c8340  nop     dword ptr [rax+rax+00h]
0x1800c8345  mov     r12d, 4
0x1800c834b  cmp     eax, 0C0000023h
0x1800c8350  jnz     short loc_1800C8379
0x1800c8352  cmp     r14d, [rbp+4Fh+arg_18]
0x1800c8356  jnb     loc_1800C83EA
0x1800c835c  mov     r14d, [rbp+4Fh+arg_18]
0x1800c8360  mov     edx, 41746D73h; Tag
0x1800c8365  mov     rcx, rdi; P
0x1800c8368  call    cs:__imp_ExFreePoolWithTag
0x1800c836f  nop     dword ptr [rax+rax+00h]
0x1800c8374  jmp     loc_1800C82F2
0x1800c8379  test    eax, eax
0x1800c837b  js      short loc_1800C83EA
0x1800c837d  cmp     dword ptr [rdi+4], 0
0x1800c8381  mov     edx, 0C0000001h
0x1800c8386  mov     ebx, edx
0x1800c8388  jbe     short loc_1800C83D4
0x1800c838a  mov     rax, [rdi+8]
0x1800c838e  cmp     word ptr [rax+10h], 10h
0x1800c8393  jnz     short loc_1800C83D4
0x1800c8395  mov     rcx, [rax+20h]
0x1800c8399  cmp     dword ptr [rcx+8], 40h ; '@'
0x1800c839d  jb      short loc_1800C83D4
0x1800c839f  mov     rcx, [rcx]
0x1800c83a2  mov     eax, [rcx+8]
0x1800c83a5  test    eax, 0FFFFFFFCh
0x1800c83aa  jnz     short loc_1800C83B1
0x1800c83ac  cmp     eax, 2
0x1800c83af  jnz     short loc_1800C83B6
0x1800c83b1  cmp     eax, r12d
0x1800c83b4  jnz     short loc_1800C83D4
0x1800c83b6  mov     ecx, [rcx+4]
0x1800c83b9  xor     ebx, ebx
0x1800c83bb  test    ecx, ecx
0x1800c83bd  jz      short loc_1800C83CE
0x1800c83bf  cmp     ecx, 1
0x1800c83c2  jz      short loc_1800C83C8
0x1800c83c4  mov     ebx, edx
0x1800c83c6  jmp     short loc_1800C83D4
0x1800c83c8  bts     dword ptr [rsi], 0Dh
0x1800c83cc  jmp     short loc_1800C83D4
0x1800c83ce  or      dword ptr [rsi], 4001h
0x1800c83d4  mov     edx, 41746D73h; Tag
0x1800c83d9  mov     rcx, rdi; P
0x1800c83dc  call    cs:__imp_ExFreePoolWithTag
0x1800c83e3  nop     dword ptr [rax+rax+00h]
0x1800c83e8  jmp     short loc_1800C8403
0x1800c83ea  mov     edx, 41746D73h; Tag
0x1800c83ef  mov     rcx, rdi; P
0x1800c83f2  call    cs:__imp_ExFreePoolWithTag
0x1800c83f9  nop     dword ptr [rax+rax+00h]
0x1800c83fe  mov     ebx, 0C0000001h
0x1800c8403  mov     eax, [r15]
0x1800c8406  xor     edi, edi
0x1800c8408  mov     r14d, 2A6h
0x1800c840e  test    al, 10h
0x1800c8410  jz      loc_1800C86EB
0x1800c8416  mov     edx, r14d
0x1800c8419  mov     ecx, 102h
0x1800c841e  mov     r8d, 41746D73h
0x1800c8424  call    cs:__imp_ExAllocatePool2
0x1800c842b  nop     dword ptr [rax+rax+00h]
0x1800c8430  mov     rdi, rax
0x1800c8433  test    rax, rax
0x1800c8436  jz      loc_1800C86DB
0x1800c843c  lea     rax, [rbp+4Fh+arg_18]
0x1800c8440  mov     r9, rdi
0x1800c8443  mov     [rsp+0D0h+var_A8], rax
0x1800c8448  lea     rdx, aB_1; "`b"
0x1800c844f  mov     r8d, 1
0x1800c8455  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800c845a  mov     rcx, r13
0x1800c845d  call    cs:__imp_SeQuerySecurityAttributesToken
0x1800c8464  nop     dword ptr [rax+rax+00h]
0x1800c8469  mov     ebx, eax
0x1800c846b  cmp     eax, 0C0000023h
0x1800c8470  jnz     short loc_1800C8496
0x1800c8472  cmp     r14d, [rbp+4Fh+arg_18]
0x1800c8476  jnb     loc_1800C86C3
0x1800c847c  mov     r14d, [rbp+4Fh+arg_18]
0x1800c8480  mov     edx, 41746D73h; Tag
0x1800c8485  mov     rcx, rdi; P
0x1800c8488  call    cs:__imp_ExFreePoolWithTag
0x1800c848f  nop     dword ptr [rax+rax+00h]
0x1800c8494  jmp     short loc_1800C8416
0x1800c8496  test    eax, eax
0x1800c8498  js      loc_1800C86C3
0x1800c849e  cmp     dword ptr [rdi+4], 0
0x1800c84a2  jbe     loc_1800C86E0
0x1800c84a8  mov     rax, [rdi+8]
0x1800c84ac  cmp     word ptr [rax+10h], 10h
0x1800c84b1  jnz     loc_1800C86E0
0x1800c84b7  mov     r14, [rax+20h]
0x1800c84bb  cmp     dword ptr [r14+8], 20Ch
0x1800c84c3  jnz     loc_1800C86E0
0x1800c84c9  mov     r14, [r14]
0x1800c84cc  xor     eax, eax
0x1800c84ce  mov     rcx, r14
0x1800c84d1  mov     edx, 80h
0x1800c84d6  mov     [r14+20Ah], ax
0x1800c84de  lea     rax, [r15+600h]
0x1800c84e5  movups  xmm0, xmmword ptr [rcx]
0x1800c84e8  movups  xmmword ptr [rax], xmm0
0x1800c84eb  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c84ef  movups  xmmword ptr [rax+10h], xmm1
0x1800c84f3  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c84f7  movups  xmmword ptr [rax+20h], xmm0
0x1800c84fb  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c84ff  movups  xmmword ptr [rax+30h], xmm1
0x1800c8503  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c8507  movups  xmmword ptr [rax+40h], xmm0
0x1800c850b  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c850f  movups  xmmword ptr [rax+50h], xmm1
0x1800c8513  movups  xmm0, xmmword ptr [rcx+60h]
0x1800c8517  movups  xmmword ptr [rax+60h], xmm0
0x1800c851b  movups  xmm1, xmmword ptr [rcx+70h]
0x1800c851f  add     rcx, rdx
0x1800c8522  movups  xmmword ptr [rax+70h], xmm1
0x1800c8526  add     rax, rdx
0x1800c8529  sub     r12, 1
0x1800c852d  jnz     short loc_1800C84E5
0x1800c852f  movups  xmm0, xmmword ptr [rcx-4]
0x1800c8533  mov     dword ptr [r15+5F8h], 1
0x1800c853e  movups  xmmword ptr [rax-4], xmm0
0x1800c8542  test    cs:g_CiPolicyState, 4000h
0x1800c854c  jnz     short loc_1800C857F
0x1800c854e  mov     ecx, [r14]
0x1800c8551  mov     eax, ecx
0x1800c8553  and     al, 22h
0x1800c8555  cmp     al, 2
0x1800c8557  jnz     short loc_1800C8563
0x1800c8559  xor     ebx, ebx
0x1800c855b  or      dword ptr [rsi], 1002h
0x1800c8561  jmp     short loc_1800C857F
0x1800c8563  test    cl, 10h
0x1800c8566  jz      short loc_1800C8572
0x1800c8568  xor     ebx, ebx
0x1800c856a  or      dword ptr [rsi], 8002h
0x1800c8570  jmp     short loc_1800C857F
0x1800c8572  test    cl, 8
0x1800c8575  jz      short loc_1800C857F
0x1800c8577  xor     ebx, ebx
0x1800c8579  or      dword ptr [rsi], 10002h
0x1800c857f  mov     eax, [r14]
0x1800c8582  test    dl, al
0x1800c8584  jz      short loc_1800C85A2
0x1800c8586  bts     dword ptr [rsi], 0Ah
0x1800c858a  lea     rcx, [r14+4]
0x1800c858e  lea     rdx, DangerousExtensions
0x1800c8595  call    CipCheckForExtensionAgainstList
0x1800c859a  test    eax, eax
0x1800c859c  jz      short loc_1800C85A2
0x1800c859e  bts     dword ptr [rsi], 0Bh
0x1800c85a2  lea     r12, [r14+4]
0x1800c85a6  mov     rcx, r12
0x1800c85a9  lea     rdx, InstallerExtensions
0x1800c85b0  call    CipCheckForExtensionAgainstList
0x1800c85b5  mov     r13d, eax
0x1800c85b8  test    eax, eax
0x1800c85ba  jnz     short loc_1800C85C8
  ... truncated ...
```
