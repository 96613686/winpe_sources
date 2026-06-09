# HsmpCreateProcessInfo

- ea: `0x140076810`
- end: `0x140076e73`
- name: `HsmpCreateProcessInfo`
- size: `1635`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400520d0`
- `0x14005c8c0`
- `0x140076734`
- `0x1400843f8`

## callees

- `0x140001510`
- `0x140001578`
- `0x140008c44`
- `0x140008d4c`
- `0x140008e90`
- `0x14000a910`
- `0x14000b668`
- `0x14001309c`
- `0x14001e140`
- `0x14001e280`
- `0x140076810`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x14007691a`
- `ntoskrnl!RtlInitAnsiString` at `0x14007691a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140076e27`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140076e27`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140076932`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140076932`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076e0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076e40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076e0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076e40`
- `ntoskrnl!ExAllocatePool2` at `0x14007697d`
- `ntoskrnl!ExAllocatePool2` at `0x140076a83`
- `ntoskrnl!ExAllocatePool2` at `0x14007697d`
- `ntoskrnl!ExAllocatePool2` at `0x140076a83`

## pseudocode

```c
__int64 __fastcall HsmpCreateProcessInfo(__int64 a1)
{
  PVOID v2; // rcx
  USHORT Length; // r12
  PWSTR Buffer; // r15
  __int64 v5; // rdi
  void *v6; // r13
  unsigned __int16 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // r10
  unsigned int ProcessId; // esi
  const char *ProcessImageFileName; // rax
  int ProcessCommandLineByAttributionInfo; // eax
  _QWORD *Pool2; // rax
  unsigned __int16 v14; // di
  unsigned __int16 v15; // cx
  unsigned int v16; // r13d
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // ecx
  unsigned int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rsi
  int v23; // eax
  void *v24; // rsi
  unsigned __int16 v25; // r9
  unsigned __int64 v26; // rbx
  __int64 v27; // rcx
  void *v28; // rdx
  unsigned int v29; // eax
  void *v30; // rcx
  __int64 v31; // rcx
  USHORT v32; // r10
  size_t v33; // r8
  void *v34; // rax
  __int64 v35; // rcx
  void *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // ecx
  void *v40; // rsi
  unsigned int v41; // edx
  __int64 v42; // r8
  __int64 v43; // rsi
  int v44; // eax
  __int128 *v45; // r8
  __int64 v46; // rcx
  __int128 v47; // xmm0
  __int64 v48; // rax
  unsigned __int16 v50; // [rsp+30h] [rbp-D0h]
  ULONG v51; // [rsp+34h] [rbp-CCh] BYREF
  int ProcessSessionId; // [rsp+38h] [rbp-C8h]
  int v53; // [rsp+3Ch] [rbp-C4h]
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  ULONGLONG v55; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v56; // [rsp+50h] [rbp-B0h]
  struct _STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  ULONGLONG v58; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h]
  void *v60; // [rsp+78h] [rbp-88h]
  void *v61; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-78h] BYREF
  __int64 VmGuid; // [rsp+98h] [rbp-68h]
  _BYTE v64[144]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v65[256]; // [rsp+140h] [rbp+40h] BYREF

  v55 = 256;
  v58 = 132;
  v56 = 0;
  HIDWORD(VmGuid) = 0;
  v2 = 0;
  P = 0;
  v51 = 0;
  Length = 14;
  Buffer = L"UNKNOWN";
  v5 = 0;
  v6 = 0;
  UnicodeString = 0;
  if ( a1 )
  {
    Src = L"UNKNOWN";
    v7 = 14;
    v60 = L"UNKNOWN";
    v61 = L"UNKNOWN";
    if ( HsmOsGetEcpFromAttributionInfo(a1) )
    {
      ProcessId = (unsigned int)HsmOsGetProcessId(v8);
      ProcessSessionId = HsmOsGetProcessSessionId(a1);
      VmGuid = HsmOsGetVmGuid(a1);
    }
    else
    {
      VmGuid = v9;
      ProcessId = (unsigned int)HsmOsGetProcessId(v8);
      ProcessSessionId = HsmOsGetProcessSessionId(a1);
    }
    if ( (int)HsmOsLocateProcessImageName(a1, &P) >= 0 )
    {
      if ( *((_QWORD *)P + 1) )
      {
        Length = *(_WORD *)P;
        Buffer = (PWSTR)*((_QWORD *)P + 1);
      }
      else
      {
        DestinationString = 0;
        ProcessImageFileName = (const char *)HsmOsGetProcessImageFileName(a1);
        RtlInitAnsiString(&DestinationString, ProcessImageFileName);
        if ( RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u) >= 0 )
        {
          Length = UnicodeString.Length;
          Buffer = UnicodeString.Buffer;
        }
      }
    }
    ProcessCommandLineByAttributionInfo = HsmOsGetProcessCommandLineByAttributionInfo(a1, 0, 0, &v51);
    if ( ProcessCommandLineByAttributionInfo == -1073741820 )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(256, v51, 1934979912);
      v56 = Pool2;
      v6 = Pool2;
      if ( !Pool2 )
        goto LABEL_15;
      ProcessCommandLineByAttributionInfo = HsmOsGetProcessCommandLineByAttributionInfo(a1, Pool2, v51, &v51);
    }
    if ( ProcessCommandLineByAttributionInfo >= 0 )
    {
      v14 = *(_WORD *)v6;
      v50 = *(_WORD *)v6;
      v61 = (void *)*((_QWORD *)v6 + 1);
      goto LABEL_16;
    }
LABEL_15:
    v50 = 14;
    v14 = 14;
LABEL_16:
    if ( (int)HsmOsQueryPackageIdentity(a1, v65, &v55, v64, &v58) < 0 )
    {
      v15 = 14;
    }
    else
    {
      if ( v55 <= 0xFFFF )
      {
        v7 = v55;
        Src = v65;
      }
      v15 = v58;
      *(_QWORD *)&DestinationString.Length = v58;
      if ( v58 <= 0xFFFF )
      {
        v60 = v64;
        goto LABEL_24;
      }
      v15 = 14;
    }
    *(_QWORD *)&DestinationString.Length = 14;
LABEL_24:
    v53 = v14;
    v16 = ((((v15 + 7 + ((v7 + 3 + ((Length + 81) & 0xFFFFFFFC)) & 0xFFFFFFFC)) & 0xFFFFFFFC) + v14 + 5) & 0xFFFFFFFC)
        + 16;
    v17 = ExAllocatePool2(256, v16, 1766880072);
    v5 = v17;
    if ( !v17 )
    {
LABEL_76:
      v6 = v56;
      v2 = P;
      goto LABEL_77;
    }
    *(_QWORD *)v17 = 1768975427;
    *(_DWORD *)(v17 + 8) = 72;
    *(_DWORD *)(v17 + 12) = 458752;
    *(_OWORD *)(v17 + 16) = 0;
    *(_OWORD *)(v17 + 32) = 0;
    *(_OWORD *)(v17 + 48) = 0;
    *(_QWORD *)(v17 + 64) = 0;
    if ( v16 < 0x18 )
      goto LABEL_45;
    if ( *(_WORD *)(v17 + 14) )
    {
      v18 = *(unsigned int *)(v17 + 8);
      if ( ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v16 )
      {
        v19 = (v18 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(v17 + 8) = v19;
        *(_DWORD *)(v17 + 16) = 262154;
        *(_DWORD *)(v17 + 20) = v19;
        *(_DWORD *)(v19 + v17) = ProcessId;
        *(_DWORD *)(v17 + 8) += 4;
      }
    }
    v20 = Length + 2;
    if ( *(_WORD *)(v17 + 14) <= 1u
      || v16 < 0x20
      || v20 > 0x10000
      || (v21 = *(unsigned int *)(v17 + 8), v20 + ((v21 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v16) )
    {
LABEL_45:
      v24 = 0;
    }
    else
    {
      v22 = ((_DWORD)v21 + 3) & 0xFFFFFFFC;
      *(_WORD *)(v17 + 26) = v20;
      v23 = v22 + (unsigned __int16)v20;
      *(_DWORD *)(v5 + 28) = v22;
      *(_WORD *)(v5 + 24) = 17;
      v24 = (void *)(v5 + v22);
      *(_DWORD *)(v5 + 8) = v23;
    }
    memmove(v24, Buffer, Length);
    *((_WORD *)v24 + ((unsigned __int64)Length >> 1)) = 0;
    if ( v16 < 0x18 )
      goto LABEL_60;
    v25 = *(_WORD *)(v5 + 14);
    v26 = v16;
    if ( v25 > 2u && v16 >= 0x28 )
    {
      v27 = *(unsigned int *)(v5 + 8);
      if ( v7 + ((v27 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v16 )
      {
        if ( *(_WORD *)(v5 + 32) )
          *(_WORD *)(v5 + 12) |= 1u;
        v28 = Src;
        v29 = (v27 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(v5 + 8) = v29;
        *(_WORD *)(v5 + 32) = 17;
        *(_WORD *)(v5 + 34) = v7;
        *(_DWORD *)(v5 + 36) = v29;
        if ( v28 )
        {
          v30 = (void *)(v5 + v29);
          if ( v30 != v28 )
          {
            memmove(v30, v28, v7);
            v25 = *(_WORD *)(v5 + 14);
          }
        }
        *(_DWORD *)(v5 + 8) += *(unsigned __int16 *)(v5 + 34);
      }
    }
    if ( v25 > 3u && v16 >= 0x30 )
    {
      v31 = *(unsigned int *)(v5 + 8);
      v32 = DestinationString.Length;
      v33 = DestinationString.Length;
      if ( DestinationString.Length + ((v31 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v16 )
      {
        if ( *(_WORD *)(v5 + 40) )
          *(_WORD *)(v5 + 12) |= 1u;
        v34 = v60;
        v35 = ((_DWORD)v31 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(v5 + 8) = v35;
        *(_DWORD *)(v5 + 44) = v35;
        v36 = (void *)(v5 + v35);
        *(_WORD *)(v5 + 40) = 17;
        *(_WORD *)(v5 + 42) = v32;
        if ( v36 != v34 )
        {
          memmove(v36, v34, v33);
          v25 = *(_WORD *)(v5 + 14);
        }
        *(_DWORD *)(v5 + 8) += *(unsigned __int16 *)(v5 + 42);
      }
    }
    if ( v25 <= 4u || v16 < 0x38 || (v37 = *(unsigned int *)(v5 + 8), ((v37 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v16) )
    {
LABEL_60:
      if ( v16 < 0x18 )
        goto LABEL_61;
      v26 = v16;
    }
    else
    {
      v38 = ((_DWORD)v37 + 3) & 0xFFFFFFFC;
      *(_DWORD *)(v5 + 8) = v38;
      if ( *(_WORD *)(v5 + 48) )
        *(_WORD *)(v5 + 12) |= 1u;
      v39 = ProcessSessionId;
      *(_DWORD *)(v5 + 48) = 262154;
      *(_DWORD *)(v5 + 52) = v38;
      *(_DWORD *)(v38 + v5) = v39;
      *(_DWORD *)(v5 + 8) += 4;
    }
    v41 = v53 + 2;
    if ( *(_WORD *)(v5 + 14) > 5u && v16 >= 0x40 && v41 <= 0x10000 )
    {
      v42 = *(unsigned int *)(v5 + 8);
      if ( v41 + ((v42 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v26 )
      {
        v43 = ((_DWORD)v42 + 3) & 0xFFFFFFFC;
        *(_WORD *)(v5 + 58) = v41;
        v44 = v43 + (unsigned __int16)v41;
        *(_DWORD *)(v5 + 60) = v43;
        *(_WORD *)(v5 + 56) = 17;
        v40 = (void *)(v5 + v43);
        *(_DWORD *)(v5 + 8) = v44;
        goto LABEL_68;
      }
    }
LABEL_61:
    v40 = 0;
LABEL_68:
    memmove(v40, v61, v50);
    v45 = (__int128 *)VmGuid;
    *((_WORD *)v40 + ((unsigned __int64)v50 >> 1)) = 0;
    if ( v45 )
    {
      if ( v16 >= 0x18 && *(_WORD *)(v5 + 14) > 6u && v16 >= 0x48 )
      {
        v46 = *(unsigned int *)(v5 + 8);
        if ( ((v46 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 16 <= v16 )
        {
          v47 = *v45;
          v48 = ((_DWORD)v46 + 3) & 0xFFFFFFFC;
          *(_DWORD *)(v5 + 8) = v48;
          if ( *(_WORD *)(v5 + 64) )
            *(_WORD *)(v5 + 12) |= 1u;
          *(_DWORD *)(v5 + 64) = 1048592;
          *(_DWORD *)(v5 + 68) = v48;
          *(_OWORD *)(v48 + v5) = v47;
          *(_DWORD *)(v5 + 8) += 16;
        }
      }
    }
    goto LABEL_76;
  }
LABEL_77:
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x73557348u);
  return v5;
}

```

## disassembly

```asm
0x140076810  push    rbp
0x140076812  push    rbx
0x140076813  push    rsi
0x140076814  push    rdi
0x140076815  push    r12
0x140076817  push    r13
0x140076819  push    r14
0x14007681b  push    r15
0x14007681d  lea     rbp, [rsp-158h]
0x140076825  sub     rsp, 258h
0x14007682c  mov     rax, cs:__security_cookie
0x140076833  xor     rax, rsp
0x140076836  mov     [rbp+190h+var_50], rax
0x14007683d  xor     r10d, r10d
0x140076840  mov     [rsp+290h+var_248], 100h
0x140076849  mov     rbx, rcx
0x14007684c  mov     [rsp+290h+var_228], 84h
0x140076855  xor     eax, eax
0x140076857  mov     [rsp+290h+var_240], r10
0x14007685c  mov     [rbp+190h+var_1F4], eax
0x14007685f  mov     ecx, r10d
0x140076862  mov     [rsp+290h+P], rcx
0x140076867  xorps   xmm0, xmm0
0x14007686a  mov     [rsp+290h+var_25C], r10d
0x14007686f  lea     r12d, [r10+0Eh]
0x140076873  lea     r15, aUnknown_0; "UNKNOWN"
0x14007687a  mov     edi, r10d
0x14007687d  mov     r13d, r10d
0x140076880  movups  xmmword ptr [rbp+190h+UnicodeString.Length], xmm0
0x140076884  test    rbx, rbx
0x140076887  jz      loc_140076E07
0x14007688d  mov     rcx, rbx
0x140076890  mov     [rsp+290h+Src], r15
0x140076895  movzx   r14d, r12w
0x140076899  mov     [rsp+290h+var_218], r15
0x14007689e  mov     [rbp+190h+var_210], r15
0x1400768a2  call    HsmOsGetEcpFromAttributionInfo
0x1400768a7  test    rax, rax
0x1400768aa  jz      short loc_1400768CE
0x1400768ac  call    HsmOsGetProcessId
0x1400768b1  mov     rcx, rbx
0x1400768b4  mov     rsi, rax
0x1400768b7  call    HsmOsGetProcessSessionId
0x1400768bc  mov     rcx, rbx
0x1400768bf  mov     [rsp+290h+var_258], eax
0x1400768c3  call    HsmOsGetVmGuid
0x1400768c8  mov     [rbp-68h], rax
0x1400768cc  jmp     short loc_1400768E6
0x1400768ce  mov     [rbp-68h], r10
0x1400768d2  call    HsmOsGetProcessId
0x1400768d7  mov     rcx, rbx
0x1400768da  mov     rsi, rax
0x1400768dd  call    HsmOsGetProcessSessionId
0x1400768e2  mov     [rsp+290h+var_258], eax
0x1400768e6  lea     rdx, [rsp+290h+P]
0x1400768eb  mov     rcx, rbx
0x1400768ee  call    HsmOsLocateProcessImageName
0x1400768f3  test    eax, eax
0x1400768f5  js      short loc_140076955
0x1400768f7  mov     rax, [rsp+290h+P]
0x1400768fc  cmp     [rax+8], rdi
0x140076900  jnz     short loc_14007694D
0x140076902  xorps   xmm0, xmm0
0x140076905  mov     rcx, rbx
0x140076908  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x14007690d  call    HsmOsGetProcessImageFileName
0x140076912  mov     rdx, rax; SourceString
0x140076915  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x14007691a  call    cs:__imp_RtlInitAnsiString
0x140076921  nop     dword ptr [rax+rax+00h]
0x140076926  mov     r8b, 1; AllocateDestinationString
0x140076929  lea     rdx, [rsp+290h+DestinationString]; SourceString
0x14007692e  lea     rcx, [rbp+190h+UnicodeString]; DestinationString
0x140076932  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140076939  nop     dword ptr [rax+rax+00h]
0x14007693e  test    eax, eax
0x140076940  js      short loc_140076955
0x140076942  movzx   r12d, [rbp+190h+UnicodeString.Length]
0x140076947  mov     r15, [rbp+190h+UnicodeString.Buffer]
0x14007694b  jmp     short loc_140076955
0x14007694d  movzx   r12d, word ptr [rax]
0x140076951  mov     r15, [rax+8]
0x140076955  lea     r9, [rsp+290h+var_25C]
0x14007695a  xor     r8d, r8d
0x14007695d  xor     edx, edx
0x14007695f  mov     rcx, rbx
0x140076962  call    HsmOsGetProcessCommandLineByAttributionInfo
0x140076967  cmp     eax, 0C0000004h
0x14007696c  jnz     short loc_1400769AB
0x14007696e  mov     edx, [rsp+290h+var_25C]
0x140076972  mov     ecx, 100h
0x140076977  mov     r8d, 73557348h
0x14007697d  call    cs:__imp_ExAllocatePool2
0x140076984  nop     dword ptr [rax+rax+00h]
0x140076989  mov     [rsp+290h+var_240], rax
0x14007698e  mov     r13, rax
0x140076991  test    rax, rax
0x140076994  jz      short loc_1400769C3
0x140076996  mov     r8d, [rsp+290h+var_25C]
0x14007699b  lea     r9, [rsp+290h+var_25C]
0x1400769a0  mov     rdx, rax
0x1400769a3  mov     rcx, rbx
0x1400769a6  call    HsmOsGetProcessCommandLineByAttributionInfo
0x1400769ab  test    eax, eax
0x1400769ad  js      short loc_1400769C3
0x1400769af  movzx   edi, word ptr [r13+0]
0x1400769b4  mov     rax, [r13+8]
0x1400769b8  mov     [rsp+290h+var_260], di
0x1400769bd  mov     [rbp+190h+var_210], rax
0x1400769c1  jmp     short loc_1400769CD
0x1400769c3  mov     [rsp+290h+var_260], r14w
0x1400769c9  movzx   edi, r14w
0x1400769cd  lea     rax, [rsp+290h+var_228]
0x1400769d2  mov     rcx, rbx
0x1400769d5  lea     r9, [rbp+190h+var_1E0]
0x1400769d9  mov     [rsp+290h+var_270], rax
0x1400769de  lea     r8, [rsp+290h+var_248]
0x1400769e3  lea     rdx, [rbp+190h+var_150]
0x1400769e7  call    HsmOsQueryPackageIdentity
0x1400769ec  test    eax, eax
0x1400769ee  js      short loc_140076A2E
0x1400769f0  mov     edx, 0FFFFh
0x1400769f5  movzx   eax, r14w
0x1400769f9  cmp     [rsp+290h+var_248], rdx
0x1400769fe  ja      short loc_140076A0F
0x140076a00  movzx   r14d, word ptr [rsp+290h+var_248]
0x140076a06  lea     rcx, [rbp+190h+var_150]
0x140076a0a  mov     [rsp+290h+Src], rcx
0x140076a0f  mov     rcx, [rsp+290h+var_228]
0x140076a14  mov     qword ptr [rsp+290h+DestinationString.Length], rcx
0x140076a19  cmp     rcx, rdx
0x140076a1c  ja      short loc_140076A29
0x140076a1e  lea     rax, [rbp+190h+var_1E0]
0x140076a22  mov     [rsp+290h+var_218], rax
0x140076a27  jmp     short loc_140076A37
0x140076a29  movzx   ecx, ax
0x140076a2c  jmp     short loc_140076A32
0x140076a2e  movzx   ecx, r14w
0x140076a32  mov     qword ptr [rsp+290h+DestinationString.Length], rcx
0x140076a37  mov     r9d, 0FFFFFFFCh
0x140076a3d  movzx   r8d, di
0x140076a41  movzx   eax, r14w
0x140076a45  add     eax, 3
0x140076a48  mov     [rsp+290h+var_254], r8d
0x140076a4d  movzx   ebx, r12w
0x140076a51  lea     r13d, [r8+5]
0x140076a55  mov     r8d, 69507348h
0x140076a5b  lea     edx, [rbx+51h]
0x140076a5e  and     edx, r9d
0x140076a61  add     edx, eax
0x140076a63  movzx   eax, cx
0x140076a66  and     edx, r9d
0x140076a69  add     eax, 7
0x140076a6c  add     edx, eax
0x140076a6e  mov     ecx, 100h
0x140076a73  and     edx, r9d
0x140076a76  add     r13d, edx
0x140076a79  and     r13d, r9d
0x140076a7c  add     r13d, 10h
0x140076a80  mov     edx, r13d
0x140076a83  call    cs:__imp_ExAllocatePool2
0x140076a8a  nop     dword ptr [rax+rax+00h]
0x140076a8f  xor     r10d, r10d
0x140076a92  mov     rdi, rax
0x140076a95  test    rax, rax
0x140076a98  jz      loc_140076DFD
0x140076a9e  mov     qword ptr [rax], 69706C43h
0x140076aa5  xorps   xmm0, xmm0
0x140076aa8  mov     dword ptr [rax+8], 48h ; 'H'
0x140076aaf  mov     dword ptr [rax+0Ch], 70000h
0x140076ab6  xor     eax, eax
0x140076ab8  mov     r9d, r13d
0x140076abb  movups  xmmword ptr [rdi+10h], xmm0
0x140076abf  lea     edx, [rax+4]
0x140076ac2  movups  xmmword ptr [rdi+20h], xmm0
0x140076ac6  movups  xmmword ptr [rdi+30h], xmm0
0x140076aca  mov     [rdi+40h], rax
0x140076ace  cmp     r13d, 18h
0x140076ad2  jb      loc_140076C2F
0x140076ad8  cmp     r10w, [rdi+0Eh]
0x140076add  jnb     loc_140076C25
0x140076ae3  mov     ecx, [rdi+8]
0x140076ae6  lea     rax, [rcx+3]
0x140076aea  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076aee  add     rax, rdx
0x140076af1  cmp     rax, r9
0x140076af4  ja      loc_140076C25
0x140076afa  lea     eax, [rcx+3]
0x140076afd  and     eax, 0FFFFFFFCh
0x140076b00  mov     ecx, eax
0x140076b02  mov     [rdi+8], ecx
0x140076b05  mov     dword ptr [rdi+10h], 4000Ah
0x140076b0c  mov     [rdi+14h], ecx
0x140076b0f  mov     [rax+rdi], esi
0x140076b12  add     [rdi+8], edx
0x140076b15  mov     eax, 1
0x140076b1a  lea     edx, [rbx+2]
0x140076b1d  cmp     ax, [rdi+0Eh]
0x140076b21  jnb     loc_140076C2F
0x140076b27  cmp     r13d, 20h ; ' '
0x140076b2b  jb      loc_140076C2F
0x140076b31  cmp     edx, 10000h
0x140076b37  ja      loc_140076C2F
0x140076b3d  mov     r8d, [rdi+8]
0x140076b41  mov     eax, edx
0x140076b43  lea     rcx, [r8+3]
0x140076b47  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140076b4b  add     rcx, rax
0x140076b4e  cmp     rcx, r9
0x140076b51  ja      loc_140076C2F
0x140076b57  lea     esi, [r8+3]
0x140076b5b  movzx   eax, dx
0x140076b5e  and     esi, 0FFFFFFFCh
0x140076b61  mov     [rdi+1Ah], ax
0x140076b65  add     eax, esi
0x140076b67  mov     [rdi+1Ch], esi
0x140076b6a  mov     word ptr [rdi+18h], 11h
0x140076b70  add     rsi, rdi
0x140076b73  mov     [rdi+8], eax
0x140076b76  movzx   ebx, r12w
0x140076b7a  mov     rdx, r15; Src
0x140076b7d  mov     r8d, ebx; Size
0x140076b80  mov     rcx, rsi; void *
0x140076b83  call    memmove
0x140076b88  shr     rbx, 1
0x140076b8b  xor     r11d, r11d
0x140076b8e  mov     [rsi+rbx*2], r11w
0x140076b93  cmp     r13d, 18h
0x140076b97  jb      loc_140076D07
0x140076b9d  movzx   r9d, word ptr [rdi+0Eh]
0x140076ba2  lea     eax, [r11+2]
0x140076ba6  mov     ebx, r13d
0x140076ba9  cmp     ax, r9w
0x140076bad  jnb     loc_140076C37
0x140076bb3  cmp     r13d, 28h ; '('
0x140076bb7  jb      short loc_140076C37
0x140076bb9  mov     ecx, [rdi+8]
0x140076bbc  movzx   r8d, r14w; Size
0x140076bc0  lea     rax, [rcx+3]
0x140076bc4  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076bc8  add     rax, r8
0x140076bcb  cmp     rax, rbx
0x140076bce  ja      short loc_140076C37
0x140076bd0  cmp     [rdi+20h], r11w
0x140076bd5  jz      short loc_140076BDF
0x140076bd7  lea     eax, [r11+1]
0x140076bdb  or      [rdi+0Ch], ax
0x140076bdf  mov     rdx, [rsp+290h+Src]; Src
0x140076be4  lea     eax, [rcx+3]
0x140076be7  and     eax, 0FFFFFFFCh
0x140076bea  mov     r12d, 11h
0x140076bf0  mov     [rdi+8], eax
0x140076bf3  mov     [rdi+20h], r12w
0x140076bf8  mov     [rdi+22h], r14w
0x140076bfd  mov     [rdi+24h], eax
0x140076c00  test    rdx, rdx
0x140076c03  jz      short loc_140076C1C
0x140076c05  mov     ecx, eax
0x140076c07  add     rcx, rdi; void *
0x140076c0a  cmp     rcx, rdx
0x140076c0d  jz      short loc_140076C1C
0x140076c0f  call    memmove
0x140076c14  movzx   r9d, word ptr [rdi+0Eh]
0x140076c19  xor     r11d, r11d
0x140076c1c  movzx   eax, word ptr [rdi+22h]
0x140076c20  add     [rdi+8], eax
0x140076c23  jmp     short loc_140076C3D
0x140076c25  cmp     r13d, 18h
0x140076c29  jnb     loc_140076B15
0x140076c2f  mov     rsi, r10
0x140076c32  jmp     loc_140076B76
0x140076c37  mov     r12d, 11h
0x140076c3d  mov     r14d, 3
0x140076c43  cmp     r14w, r9w
0x140076c47  jnb     short loc_140076CB4
0x140076c49  cmp     r13d, 30h ; '0'
0x140076c4d  jb      short loc_140076CB4
0x140076c4f  mov     ecx, [rdi+8]
0x140076c52  mov     r10, qword ptr [rsp+290h+DestinationString.Length]
0x140076c57  movzx   r8d, r10w; Size
0x140076c5b  lea     rax, [r14+rcx]
0x140076c5f  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076c63  add     rax, r8
0x140076c66  cmp     rax, rbx
0x140076c69  ja      short loc_140076CB4
0x140076c6b  cmp     [rdi+28h], r11w
0x140076c70  jz      short loc_140076C7A
0x140076c72  lea     eax, [r14-2]
0x140076c76  or      [rdi+0Ch], ax
0x140076c7a  mov     rax, [rsp+290h+var_218]
0x140076c7f  add     ecx, r14d
0x140076c82  and     ecx, 0FFFFFFFCh
0x140076c85  mov     [rdi+8], ecx
0x140076c88  mov     [rdi+2Ch], ecx
0x140076c8b  add     rcx, rdi; void *
0x140076c8e  mov     [rdi+28h], r12w
0x140076c93  mov     [rdi+2Ah], r10w
0x140076c98  cmp     rcx, rax
0x140076c9b  jz      short loc_140076CAD
0x140076c9d  mov     rdx, rax; Src
  ... truncated ...
```
