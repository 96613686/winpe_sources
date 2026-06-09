# HsmpCreateProcessInfo

- ea: `0x140076948`
- end: `0x140076fab`
- name: `HsmpCreateProcessInfo`
- size: `1635`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400521f0`
- `0x14005c9e0`
- `0x14007686c`
- `0x1400845b0`

## callees

- `0x140001510`
- `0x140001578`
- `0x140008c44`
- `0x140008d4c`
- `0x140008e90`
- `0x14000a910`
- `0x14000b668`
- `0x14001311c`
- `0x14001e1c0`
- `0x14001e300`
- `0x140076948`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x140076a52`
- `ntoskrnl!RtlInitAnsiString` at `0x140076a52`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140076f5f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140076f5f`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140076a6a`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140076a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076f46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076f78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076f46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076f78`
- `ntoskrnl!ExAllocatePool2` at `0x140076ab5`
- `ntoskrnl!ExAllocatePool2` at `0x140076bbb`
- `ntoskrnl!ExAllocatePool2` at `0x140076ab5`
- `ntoskrnl!ExAllocatePool2` at `0x140076bbb`

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
0x140076948  push    rbp
0x14007694a  push    rbx
0x14007694b  push    rsi
0x14007694c  push    rdi
0x14007694d  push    r12
0x14007694f  push    r13
0x140076951  push    r14
0x140076953  push    r15
0x140076955  lea     rbp, [rsp-158h]
0x14007695d  sub     rsp, 258h
0x140076964  mov     rax, cs:__security_cookie
0x14007696b  xor     rax, rsp
0x14007696e  mov     [rbp+190h+var_50], rax
0x140076975  xor     r10d, r10d
0x140076978  mov     [rsp+290h+var_248], 100h
0x140076981  mov     rbx, rcx
0x140076984  mov     [rsp+290h+var_228], 84h
0x14007698d  xor     eax, eax
0x14007698f  mov     [rsp+290h+var_240], r10
0x140076994  mov     [rbp+190h+var_1F4], eax
0x140076997  mov     ecx, r10d
0x14007699a  mov     [rsp+290h+P], rcx
0x14007699f  xorps   xmm0, xmm0
0x1400769a2  mov     [rsp+290h+var_25C], r10d
0x1400769a7  lea     r12d, [r10+0Eh]
0x1400769ab  lea     r15, aUnknown_0; "UNKNOWN"
0x1400769b2  mov     edi, r10d
0x1400769b5  mov     r13d, r10d
0x1400769b8  movups  xmmword ptr [rbp+190h+UnicodeString.Length], xmm0
0x1400769bc  test    rbx, rbx
0x1400769bf  jz      loc_140076F3F
0x1400769c5  mov     rcx, rbx
0x1400769c8  mov     [rsp+290h+Src], r15
0x1400769cd  movzx   r14d, r12w
0x1400769d1  mov     [rsp+290h+var_218], r15
0x1400769d6  mov     [rbp+190h+var_210], r15
0x1400769da  call    HsmOsGetEcpFromAttributionInfo
0x1400769df  test    rax, rax
0x1400769e2  jz      short loc_140076A06
0x1400769e4  call    HsmOsGetProcessId
0x1400769e9  mov     rcx, rbx
0x1400769ec  mov     rsi, rax
0x1400769ef  call    HsmOsGetProcessSessionId
0x1400769f4  mov     rcx, rbx
0x1400769f7  mov     [rsp+290h+var_258], eax
0x1400769fb  call    HsmOsGetVmGuid
0x140076a00  mov     [rbp-68h], rax
0x140076a04  jmp     short loc_140076A1E
0x140076a06  mov     [rbp-68h], r10
0x140076a0a  call    HsmOsGetProcessId
0x140076a0f  mov     rcx, rbx
0x140076a12  mov     rsi, rax
0x140076a15  call    HsmOsGetProcessSessionId
0x140076a1a  mov     [rsp+290h+var_258], eax
0x140076a1e  lea     rdx, [rsp+290h+P]
0x140076a23  mov     rcx, rbx
0x140076a26  call    HsmOsLocateProcessImageName
0x140076a2b  test    eax, eax
0x140076a2d  js      short loc_140076A8D
0x140076a2f  mov     rax, [rsp+290h+P]
0x140076a34  cmp     [rax+8], rdi
0x140076a38  jnz     short loc_140076A85
0x140076a3a  xorps   xmm0, xmm0
0x140076a3d  mov     rcx, rbx
0x140076a40  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x140076a45  call    HsmOsGetProcessImageFileName
0x140076a4a  mov     rdx, rax; SourceString
0x140076a4d  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x140076a52  call    cs:__imp_RtlInitAnsiString
0x140076a59  nop     dword ptr [rax+rax+00h]
0x140076a5e  mov     r8b, 1; AllocateDestinationString
0x140076a61  lea     rdx, [rsp+290h+DestinationString]; SourceString
0x140076a66  lea     rcx, [rbp+190h+UnicodeString]; DestinationString
0x140076a6a  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140076a71  nop     dword ptr [rax+rax+00h]
0x140076a76  test    eax, eax
0x140076a78  js      short loc_140076A8D
0x140076a7a  movzx   r12d, [rbp+190h+UnicodeString.Length]
0x140076a7f  mov     r15, [rbp+190h+UnicodeString.Buffer]
0x140076a83  jmp     short loc_140076A8D
0x140076a85  movzx   r12d, word ptr [rax]
0x140076a89  mov     r15, [rax+8]
0x140076a8d  lea     r9, [rsp+290h+var_25C]
0x140076a92  xor     r8d, r8d
0x140076a95  xor     edx, edx
0x140076a97  mov     rcx, rbx
0x140076a9a  call    HsmOsGetProcessCommandLineByAttributionInfo
0x140076a9f  cmp     eax, 0C0000004h
0x140076aa4  jnz     short loc_140076AE3
0x140076aa6  mov     edx, [rsp+290h+var_25C]
0x140076aaa  mov     ecx, 100h
0x140076aaf  mov     r8d, 73557348h
0x140076ab5  call    cs:__imp_ExAllocatePool2
0x140076abc  nop     dword ptr [rax+rax+00h]
0x140076ac1  mov     [rsp+290h+var_240], rax
0x140076ac6  mov     r13, rax
0x140076ac9  test    rax, rax
0x140076acc  jz      short loc_140076AFB
0x140076ace  mov     r8d, [rsp+290h+var_25C]
0x140076ad3  lea     r9, [rsp+290h+var_25C]
0x140076ad8  mov     rdx, rax
0x140076adb  mov     rcx, rbx
0x140076ade  call    HsmOsGetProcessCommandLineByAttributionInfo
0x140076ae3  test    eax, eax
0x140076ae5  js      short loc_140076AFB
0x140076ae7  movzx   edi, word ptr [r13+0]
0x140076aec  mov     rax, [r13+8]
0x140076af0  mov     [rsp+290h+var_260], di
0x140076af5  mov     [rbp+190h+var_210], rax
0x140076af9  jmp     short loc_140076B05
0x140076afb  mov     [rsp+290h+var_260], r14w
0x140076b01  movzx   edi, r14w
0x140076b05  lea     rax, [rsp+290h+var_228]
0x140076b0a  mov     rcx, rbx
0x140076b0d  lea     r9, [rbp+190h+var_1E0]
0x140076b11  mov     [rsp+290h+var_270], rax
0x140076b16  lea     r8, [rsp+290h+var_248]
0x140076b1b  lea     rdx, [rbp+190h+var_150]
0x140076b1f  call    HsmOsQueryPackageIdentity
0x140076b24  test    eax, eax
0x140076b26  js      short loc_140076B66
0x140076b28  mov     edx, 0FFFFh
0x140076b2d  movzx   eax, r14w
0x140076b31  cmp     [rsp+290h+var_248], rdx
0x140076b36  ja      short loc_140076B47
0x140076b38  movzx   r14d, word ptr [rsp+290h+var_248]
0x140076b3e  lea     rcx, [rbp+190h+var_150]
0x140076b42  mov     [rsp+290h+Src], rcx
0x140076b47  mov     rcx, [rsp+290h+var_228]
0x140076b4c  mov     qword ptr [rsp+290h+DestinationString.Length], rcx
0x140076b51  cmp     rcx, rdx
0x140076b54  ja      short loc_140076B61
0x140076b56  lea     rax, [rbp+190h+var_1E0]
0x140076b5a  mov     [rsp+290h+var_218], rax
0x140076b5f  jmp     short loc_140076B6F
0x140076b61  movzx   ecx, ax
0x140076b64  jmp     short loc_140076B6A
0x140076b66  movzx   ecx, r14w
0x140076b6a  mov     qword ptr [rsp+290h+DestinationString.Length], rcx
0x140076b6f  mov     r9d, 0FFFFFFFCh
0x140076b75  movzx   r8d, di
0x140076b79  movzx   eax, r14w
0x140076b7d  add     eax, 3
0x140076b80  mov     [rsp+290h+var_254], r8d
0x140076b85  movzx   ebx, r12w
0x140076b89  lea     r13d, [r8+5]
0x140076b8d  mov     r8d, 69507348h
0x140076b93  lea     edx, [rbx+51h]
0x140076b96  and     edx, r9d
0x140076b99  add     edx, eax
0x140076b9b  movzx   eax, cx
0x140076b9e  and     edx, r9d
0x140076ba1  add     eax, 7
0x140076ba4  add     edx, eax
0x140076ba6  mov     ecx, 100h
0x140076bab  and     edx, r9d
0x140076bae  add     r13d, edx
0x140076bb1  and     r13d, r9d
0x140076bb4  add     r13d, 10h
0x140076bb8  mov     edx, r13d
0x140076bbb  call    cs:__imp_ExAllocatePool2
0x140076bc2  nop     dword ptr [rax+rax+00h]
0x140076bc7  xor     r10d, r10d
0x140076bca  mov     rdi, rax
0x140076bcd  test    rax, rax
0x140076bd0  jz      loc_140076F35
0x140076bd6  mov     qword ptr [rax], 69706C43h
0x140076bdd  xorps   xmm0, xmm0
0x140076be0  mov     dword ptr [rax+8], 48h ; 'H'
0x140076be7  mov     dword ptr [rax+0Ch], 70000h
0x140076bee  xor     eax, eax
0x140076bf0  mov     r9d, r13d
0x140076bf3  movups  xmmword ptr [rdi+10h], xmm0
0x140076bf7  lea     edx, [rax+4]
0x140076bfa  movups  xmmword ptr [rdi+20h], xmm0
0x140076bfe  movups  xmmword ptr [rdi+30h], xmm0
0x140076c02  mov     [rdi+40h], rax
0x140076c06  cmp     r13d, 18h
0x140076c0a  jb      loc_140076D67
0x140076c10  cmp     r10w, [rdi+0Eh]
0x140076c15  jnb     loc_140076D5D
0x140076c1b  mov     ecx, [rdi+8]
0x140076c1e  lea     rax, [rcx+3]
0x140076c22  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076c26  add     rax, rdx
0x140076c29  cmp     rax, r9
0x140076c2c  ja      loc_140076D5D
0x140076c32  lea     eax, [rcx+3]
0x140076c35  and     eax, 0FFFFFFFCh
0x140076c38  mov     ecx, eax
0x140076c3a  mov     [rdi+8], ecx
0x140076c3d  mov     dword ptr [rdi+10h], 4000Ah
0x140076c44  mov     [rdi+14h], ecx
0x140076c47  mov     [rax+rdi], esi
0x140076c4a  add     [rdi+8], edx
0x140076c4d  mov     eax, 1
0x140076c52  lea     edx, [rbx+2]
0x140076c55  cmp     ax, [rdi+0Eh]
0x140076c59  jnb     loc_140076D67
0x140076c5f  cmp     r13d, 20h ; ' '
0x140076c63  jb      loc_140076D67
0x140076c69  cmp     edx, 10000h
0x140076c6f  ja      loc_140076D67
0x140076c75  mov     r8d, [rdi+8]
0x140076c79  mov     eax, edx
0x140076c7b  lea     rcx, [r8+3]
0x140076c7f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140076c83  add     rcx, rax
0x140076c86  cmp     rcx, r9
0x140076c89  ja      loc_140076D67
0x140076c8f  lea     esi, [r8+3]
0x140076c93  movzx   eax, dx
0x140076c96  and     esi, 0FFFFFFFCh
0x140076c99  mov     [rdi+1Ah], ax
0x140076c9d  add     eax, esi
0x140076c9f  mov     [rdi+1Ch], esi
0x140076ca2  mov     word ptr [rdi+18h], 11h
0x140076ca8  add     rsi, rdi
0x140076cab  mov     [rdi+8], eax
0x140076cae  movzx   ebx, r12w
0x140076cb2  mov     rdx, r15; Src
0x140076cb5  mov     r8d, ebx; Size
0x140076cb8  mov     rcx, rsi; void *
0x140076cbb  call    memmove
0x140076cc0  shr     rbx, 1
0x140076cc3  xor     r11d, r11d
0x140076cc6  mov     [rsi+rbx*2], r11w
0x140076ccb  cmp     r13d, 18h
0x140076ccf  jb      loc_140076E3F
0x140076cd5  movzx   r9d, word ptr [rdi+0Eh]
0x140076cda  lea     eax, [r11+2]
0x140076cde  mov     ebx, r13d
0x140076ce1  cmp     ax, r9w
0x140076ce5  jnb     loc_140076D6F
0x140076ceb  cmp     r13d, 28h ; '('
0x140076cef  jb      short loc_140076D6F
0x140076cf1  mov     ecx, [rdi+8]
0x140076cf4  movzx   r8d, r14w; Size
0x140076cf8  lea     rax, [rcx+3]
0x140076cfc  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076d00  add     rax, r8
0x140076d03  cmp     rax, rbx
0x140076d06  ja      short loc_140076D6F
0x140076d08  cmp     [rdi+20h], r11w
0x140076d0d  jz      short loc_140076D17
0x140076d0f  lea     eax, [r11+1]
0x140076d13  or      [rdi+0Ch], ax
0x140076d17  mov     rdx, [rsp+290h+Src]; Src
0x140076d1c  lea     eax, [rcx+3]
0x140076d1f  and     eax, 0FFFFFFFCh
0x140076d22  mov     r12d, 11h
0x140076d28  mov     [rdi+8], eax
0x140076d2b  mov     [rdi+20h], r12w
0x140076d30  mov     [rdi+22h], r14w
0x140076d35  mov     [rdi+24h], eax
0x140076d38  test    rdx, rdx
0x140076d3b  jz      short loc_140076D54
0x140076d3d  mov     ecx, eax
0x140076d3f  add     rcx, rdi; void *
0x140076d42  cmp     rcx, rdx
0x140076d45  jz      short loc_140076D54
0x140076d47  call    memmove
0x140076d4c  movzx   r9d, word ptr [rdi+0Eh]
0x140076d51  xor     r11d, r11d
0x140076d54  movzx   eax, word ptr [rdi+22h]
0x140076d58  add     [rdi+8], eax
0x140076d5b  jmp     short loc_140076D75
0x140076d5d  cmp     r13d, 18h
0x140076d61  jnb     loc_140076C4D
0x140076d67  mov     rsi, r10
0x140076d6a  jmp     loc_140076CAE
0x140076d6f  mov     r12d, 11h
0x140076d75  mov     r14d, 3
0x140076d7b  cmp     r14w, r9w
0x140076d7f  jnb     short loc_140076DEC
0x140076d81  cmp     r13d, 30h ; '0'
0x140076d85  jb      short loc_140076DEC
0x140076d87  mov     ecx, [rdi+8]
0x140076d8a  mov     r10, qword ptr [rsp+290h+DestinationString.Length]
0x140076d8f  movzx   r8d, r10w; Size
0x140076d93  lea     rax, [r14+rcx]
0x140076d97  and     rax, 0FFFFFFFFFFFFFFFCh
0x140076d9b  add     rax, r8
0x140076d9e  cmp     rax, rbx
0x140076da1  ja      short loc_140076DEC
0x140076da3  cmp     [rdi+28h], r11w
0x140076da8  jz      short loc_140076DB2
0x140076daa  lea     eax, [r14-2]
0x140076dae  or      [rdi+0Ch], ax
0x140076db2  mov     rax, [rsp+290h+var_218]
0x140076db7  add     ecx, r14d
0x140076dba  and     ecx, 0FFFFFFFCh
0x140076dbd  mov     [rdi+8], ecx
0x140076dc0  mov     [rdi+2Ch], ecx
0x140076dc3  add     rcx, rdi; void *
0x140076dc6  mov     [rdi+28h], r12w
0x140076dcb  mov     [rdi+2Ah], r10w
0x140076dd0  cmp     rcx, rax
0x140076dd3  jz      short loc_140076DE5
0x140076dd5  mov     rdx, rax; Src
  ... truncated ...
```
