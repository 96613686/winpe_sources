# FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1

- ea: `0x1800067b0`
- end: `0x180006a6f`
- name: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180006638`

## callees

- `0x180002b80`
- `0x1800067b0`
- `0x180006a78`
- `0x180006acc`
- `0x1800071fc`
- `0x180007e38`
- `0x18000f440`
- `0x180011500`

## string_xrefs

- `0x180006885`: `FwppDeepCopyFromVerIndependent_UINT16`
- `0x180006a0f`: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1`
- `0x180006a5b`: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1`
- `0x180006a23`: `FwppDeepCopyFromVerIndependent_UINT32`
- `0x180006a3b`: `FwppDeepCopyFromVerIndependent_UINT32`
- `0x18000692f`: `FwppDeepCopyFromVerIndependent_FWP_IP_VERSION`
- `0x180006947`: `FwppDeepCopyFromVerIndependent_FWP_IP_VERSION`
- `0x18000698c`: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_FLAGS`
- `0x1800069a4`: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_FLAGS`
- `0x1800069b3`: `FwppDeepCopyFromVerIndependent_UINT8`
- `0x1800069cb`: `FwppDeepCopyFromVerIndependent_UINT8`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rdi
  _DWORD *v4; // rax
  _DWORD *v5; // r14
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  void *v10; // rcx
  __int64 v11; // rax
  __int64 v13; // rax
  const char *v14; // rdx

  v3 = a1;
  if ( !a1 || !a2 )
  {
    v11 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1", 3223453724LL);
LABEL_30:
    v7 = v11;
    if ( !v11 )
      return v7;
    goto LABEL_50;
  }
  *a2 = *a1;
  v4 = a1 + 1;
  if ( a1 == (_QWORD *)-8LL || (a1 = a2 + 1, a2 == (_QWORD *)-8LL) )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_FLAGS", 3223453724LL);
    v7 = v13;
    if ( v13 )
    {
      v14 = "FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_FLAGS";
      goto LABEL_49;
    }
  }
  else
  {
    *(_DWORD *)a1 = *v4;
  }
  v5 = (_DWORD *)v3 + 3;
  if ( v3 == (_QWORD *)-12LL || (a1 = (_QWORD *)((char *)a2 + 12), a2 == (_QWORD *)-12LL) )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWP_IP_VERSION", 3223453724LL);
    v7 = v13;
    if ( !v13 )
      goto LABEL_9;
    v14 = "FwppDeepCopyFromVerIndependent_FWP_IP_VERSION";
LABEL_49:
    WfpReportError(v13, v14);
    goto LABEL_50;
  }
  *(_DWORD *)a1 = *v5;
LABEL_9:
  if ( v3 != (_QWORD *)-16LL )
  {
    a1 = a2 + 2;
    if ( a2 != (_QWORD *)-16LL )
    {
      *(_BYTE *)a1 = *((_BYTE *)v3 + 16);
      goto LABEL_12;
    }
  }
  v13 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_UINT8", 3223453724LL);
  v7 = v13;
  if ( v13 )
  {
    v14 = "FwppDeepCopyFromVerIndependent_UINT8";
    goto LABEL_49;
  }
LABEL_12:
  if ( *v5 )
  {
    if ( *v5 != 1 )
      goto LABEL_15;
    v6 = FwppDeepCopyToVerIndependent_FWP_IPV6_ADDRESS((char *)v3 + 20, (char *)a2 + 20);
  }
  else
  {
    v6 = FwppDeepCopyToVerIndependent_FWP_IPV4_ADDRESS((char *)v3 + 20, (char *)a2 + 20);
  }
  v7 = v6;
  if ( v6 )
    goto LABEL_50;
LABEL_15:
  v8 = (unsigned int)*v5;
  if ( (_DWORD)v8 )
  {
    if ( (_DWORD)v8 != 1 )
      goto LABEL_18;
    v9 = FwppDeepCopyToVerIndependent_FWP_IPV6_ADDRESS((char *)v3 + 36, (char *)a2 + 36);
  }
  else
  {
    v9 = FwppDeepCopyToVerIndependent_FWP_IPV4_ADDRESS((char *)v3 + 36, (char *)a2 + 36);
  }
  v7 = v9;
  if ( v9 )
    goto LABEL_50;
LABEL_18:
  if ( v3 == (_QWORD *)-52LL || (v8 = (unsigned __int64)a2 + 52, a2 == (_QWORD *)-52LL) )
  {
    v13 = WfpReportSysErrorAsNtStatus(v8, "FwppDeepCopyFromVerIndependent_UINT16", 3223453724LL);
    v7 = v13;
    if ( v13 )
    {
LABEL_43:
      v14 = "FwppDeepCopyFromVerIndependent_UINT16";
      goto LABEL_49;
    }
  }
  else
  {
    *(_WORD *)v8 = *((_WORD *)v3 + 26);
  }
  if ( v3 == (_QWORD *)-54LL || (v8 = (unsigned __int64)a2 + 54, a2 == (_QWORD *)-54LL) )
  {
    v13 = WfpReportSysErrorAsNtStatus(v8, "FwppDeepCopyFromVerIndependent_UINT16", 3223453724LL);
    v7 = v13;
    if ( !v13 )
      goto LABEL_24;
    goto LABEL_43;
  }
  *(_WORD *)v8 = *((_WORD *)v3 + 27);
LABEL_24:
  if ( v3 != (_QWORD *)-56LL )
  {
    v8 = (unsigned __int64)(a2 + 7);
    if ( a2 != (_QWORD *)-56LL )
    {
      *(_DWORD *)v8 = *((_DWORD *)v3 + 14);
      goto LABEL_27;
    }
  }
  v13 = WfpReportSysErrorAsNtStatus(v8, "FwppDeepCopyFromVerIndependent_UINT32", 3223453724LL);
  v7 = v13;
  if ( v13 )
  {
    v14 = "FwppDeepCopyFromVerIndependent_UINT32";
    goto LABEL_49;
  }
LABEL_27:
  v7 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(v3 + 8, a2 + 8);
  if ( !v7 )
  {
    v10 = (void *)v3[10];
    if ( !v10 )
      return v7;
    v11 = FwppAllocAndDeepCopyToVerIndependent_SID(v10, a2 + 10);
    goto LABEL_30;
  }
LABEL_50:
  FwppDeepFreeContentsOnly_FWPM_NET_EVENT_HEADER1(a2);
  if ( v7 )
    WfpReportError(v7, "FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_HEADER1");
  return v7;
}

```

## disassembly

```asm
0x1800067b0  push    rbx
0x1800067b2  push    rbp
0x1800067b3  push    rsi
0x1800067b4  push    rdi
0x1800067b5  push    r14
0x1800067b7  sub     rsp, 20h
0x1800067bb  mov     rsi, rdx
0x1800067be  mov     rdi, rcx
0x1800067c1  test    rcx, rcx
0x1800067c4  jz      loc_180006A09
0x1800067ca  test    rdx, rdx
0x1800067cd  jz      loc_180006A09
0x1800067d3  mov     rax, [rcx]
0x1800067d6  mov     ebp, 0C022001Ch
0x1800067db  mov     [rdx], rax
0x1800067de  lea     rax, [rcx+8]
0x1800067e2  test    rax, rax
0x1800067e5  jz      loc_180006989
0x1800067eb  lea     rcx, [rdx+8]
0x1800067ef  test    rcx, rcx
0x1800067f2  jz      loc_180006989
0x1800067f8  mov     eax, [rax]
0x1800067fa  mov     [rcx], eax
0x1800067fc  lea     r14, [rdi+0Ch]
0x180006800  test    r14, r14
0x180006803  jz      loc_18000692C
0x180006809  lea     rcx, [rsi+0Ch]
0x18000680d  test    rcx, rcx
0x180006810  jz      loc_18000692C
0x180006816  mov     eax, [r14]
0x180006819  mov     [rcx], eax
0x18000681b  lea     rax, [rdi+10h]
0x18000681f  test    rax, rax
0x180006822  jz      loc_1800069B0
0x180006828  lea     rcx, [rsi+10h]
0x18000682c  test    rcx, rcx
0x18000682f  jz      loc_1800069B0
0x180006835  mov     al, [rax]
0x180006837  mov     [rcx], al
0x180006839  mov     ecx, [r14]
0x18000683c  test    ecx, ecx
0x18000683e  jnz     loc_180006953
0x180006844  lea     rdx, [rsi+14h]
0x180006848  lea     rcx, [rdi+14h]
0x18000684c  call    FwppDeepCopyToVerIndependent_FWP_IPV4_ADDRESS
0x180006851  mov     rbx, rax
0x180006854  test    rax, rax
0x180006857  jnz     loc_180006A4A
0x18000685d  mov     ecx, [r14]
0x180006860  test    ecx, ecx
0x180006862  jnz     loc_18000696E
0x180006868  lea     rdx, [rsi+24h]
0x18000686c  lea     rcx, [rdi+24h]
0x180006870  call    FwppDeepCopyToVerIndependent_FWP_IPV4_ADDRESS
0x180006875  mov     rbx, rax
0x180006878  test    rax, rax
0x18000687b  jnz     loc_180006A4A
0x180006881  lea     rax, [rdi+34h]
0x180006885  lea     r14, aFwppdeepcopyfr_58; "FwppDeepCopyFromVerIndependent_UINT16"
0x18000688c  test    rax, rax
0x18000688f  jz      loc_1800069D4
0x180006895  lea     rcx, [rsi+34h]
0x180006899  test    rcx, rcx
0x18000689c  jz      loc_1800069D4
0x1800068a2  movzx   eax, word ptr [rax]
0x1800068a5  mov     [rcx], ax
0x1800068a8  lea     rax, [rdi+36h]
0x1800068ac  test    rax, rax
0x1800068af  jz      loc_1800069F0
0x1800068b5  lea     rcx, [rsi+36h]
0x1800068b9  test    rcx, rcx
0x1800068bc  jz      loc_1800069F0
0x1800068c2  movzx   eax, word ptr [rax]
0x1800068c5  mov     [rcx], ax
0x1800068c8  lea     rax, [rdi+38h]
0x1800068cc  test    rax, rax
0x1800068cf  jz      loc_180006A20
0x1800068d5  lea     rcx, [rsi+38h]
0x1800068d9  test    rcx, rcx
0x1800068dc  jz      loc_180006A20
0x1800068e2  mov     eax, [rax]
0x1800068e4  mov     [rcx], eax
0x1800068e6  lea     rdx, [rsi+40h]
0x1800068ea  lea     rcx, [rdi+40h]
0x1800068ee  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x1800068f3  mov     rbx, rax
0x1800068f6  test    rax, rax
0x1800068f9  jnz     loc_180006A4A
0x1800068ff  mov     rcx, [rdi+50h]; SourceSid
0x180006903  test    rcx, rcx
0x180006906  jz      short loc_18000691D
0x180006908  lea     rdx, [rsi+50h]
0x18000690c  call    FwppAllocAndDeepCopyToVerIndependent_SID
0x180006911  mov     rbx, rax
0x180006914  test    rax, rax
0x180006917  jnz     loc_180006A4A
0x18000691d  mov     rax, rbx
0x180006920  add     rsp, 20h
0x180006924  pop     r14
0x180006926  pop     rdi
0x180006927  pop     rsi
0x180006928  pop     rbp
0x180006929  pop     rbx
0x18000692a  retn
0x18000692c  mov     r8d, ebp
0x18000692f  lea     rdx, aFwppdeepcopyfr_16; "FwppDeepCopyFromVerIndependent_FWP_IP_V"...
0x180006936  call    WfpReportSysErrorAsNtStatus
0x18000693b  mov     rbx, rax
0x18000693e  test    rax, rax
0x180006941  jz      loc_18000681B
0x180006947  lea     rdx, aFwppdeepcopyfr_16; "FwppDeepCopyFromVerIndependent_FWP_IP_V"...
0x18000694e  jmp     loc_180006A42
0x180006953  cmp     ecx, 1
0x180006956  jnz     loc_18000685D
0x18000695c  lea     rdx, [rsi+14h]
0x180006960  lea     rcx, [rdi+14h]
0x180006964  call    FwppDeepCopyToVerIndependent_FWP_IPV6_ADDRESS
0x180006969  jmp     loc_180006851
0x18000696e  cmp     ecx, 1
0x180006971  jnz     loc_180006881
0x180006977  lea     rdx, [rsi+24h]
0x18000697b  lea     rcx, [rdi+24h]
0x18000697f  call    FwppDeepCopyToVerIndependent_FWP_IPV6_ADDRESS
0x180006984  jmp     loc_180006875
0x180006989  mov     r8d, ebp
0x18000698c  lea     rdx, aFwppdeepcopyfr_83; "FwppDeepCopyFromVerIndependent_FWPM_NET"...
0x180006993  call    WfpReportSysErrorAsNtStatus
0x180006998  mov     rbx, rax
0x18000699b  test    rax, rax
0x18000699e  jz      loc_1800067FC
0x1800069a4  lea     rdx, aFwppdeepcopyfr_83; "FwppDeepCopyFromVerIndependent_FWPM_NET"...
0x1800069ab  jmp     loc_180006A42
0x1800069b0  mov     r8d, ebp
0x1800069b3  lea     rdx, aFwppdeepcopyfr_171; "FwppDeepCopyFromVerIndependent_UINT8"
0x1800069ba  call    WfpReportSysErrorAsNtStatus
0x1800069bf  mov     rbx, rax
0x1800069c2  test    rax, rax
0x1800069c5  jz      loc_180006839
0x1800069cb  lea     rdx, aFwppdeepcopyfr_171; "FwppDeepCopyFromVerIndependent_UINT8"
0x1800069d2  jmp     short loc_180006A42
0x1800069d4  mov     r8d, ebp
0x1800069d7  mov     rdx, r14
0x1800069da  call    WfpReportSysErrorAsNtStatus
0x1800069df  mov     rbx, rax
0x1800069e2  test    rax, rax
0x1800069e5  jz      loc_1800068A8
0x1800069eb  mov     rdx, r14
0x1800069ee  jmp     short loc_180006A42
0x1800069f0  mov     r8d, ebp
0x1800069f3  mov     rdx, r14
0x1800069f6  call    WfpReportSysErrorAsNtStatus
0x1800069fb  mov     rbx, rax
0x1800069fe  test    rax, rax
0x180006a01  jz      loc_1800068C8
0x180006a07  jmp     short loc_1800069EB
0x180006a09  mov     r8d, 0C022001Ch
0x180006a0f  lea     rdx, aFwppdeepcopyfr_133; "FwppDeepCopyFromVerIndependent_FWPM_NET"...
0x180006a16  call    WfpReportSysErrorAsNtStatus
0x180006a1b  jmp     loc_180006911
0x180006a20  mov     r8d, ebp
0x180006a23  lea     rdx, aFwppdeepcopyfr_117; "FwppDeepCopyFromVerIndependent_UINT32"
0x180006a2a  call    WfpReportSysErrorAsNtStatus
0x180006a2f  mov     rbx, rax
0x180006a32  test    rax, rax
0x180006a35  jz      loc_1800068E6
0x180006a3b  lea     rdx, aFwppdeepcopyfr_117; "FwppDeepCopyFromVerIndependent_UINT32"
0x180006a42  mov     rcx, rax
0x180006a45  call    WfpReportError
0x180006a4a  mov     rcx, rsi
0x180006a4d  call    FwppDeepFreeContentsOnly_FWPM_NET_EVENT_HEADER1
0x180006a52  test    rbx, rbx
0x180006a55  jz      loc_18000691D
0x180006a5b  lea     rdx, aFwppdeepcopyfr_133; "FwppDeepCopyFromVerIndependent_FWPM_NET"...
0x180006a62  mov     rcx, rbx
0x180006a65  call    WfpReportError
0x180006a6a  jmp     loc_18000691D
```
