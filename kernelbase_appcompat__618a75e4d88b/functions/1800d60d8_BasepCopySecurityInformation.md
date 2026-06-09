# BasepCopySecurityInformation

- ea: `0x1800d60d8`
- end: `0x1800d6783`
- name: `BasepCopySecurityInformation`
- size: `1707`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE, int, SECURITY_INFORMATION SecurityInfo, __int64, char, __int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d4240`
- `0x1800d770c`

## callees

- `0x1800391f0`
- `0x18004b9d0`
- `0x1800d60d8`
- `0x1800d678c`
- `0x1800d6840`
- `0x180138050`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800d6580`
- `ntdll!RtlSetLastWin32Error` at `0x1800d6580`
- `ntdll!RtlGetLastNtStatus` at `0x1800d6566`
- `ntdll!RtlGetLastNtStatus` at `0x1800d6566`
- `ntdll!RtlpMergeSecurityAttributeInformation` at `0x1800d65ba`
- `ntdll!RtlpMergeSecurityAttributeInformation` at `0x1800d65ba`
- `ntdll!RtlFindAceByType` at `0x1800d6294`
- `ntdll!RtlFindAceByType` at `0x1800d6294`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800d6549`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800d6549`
- `ntdll!RtlFreeHeap` at `0x1800d6436`
- `ntdll!RtlFreeHeap` at `0x1800d6436`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800d6263`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800d62e0`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800d6374`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800d6263`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800d62e0`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800d6374`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!SetSecurityInfo` at `0x1800d63db`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!SetSecurityInfo` at `0x1800d63db`

## pseudocode

```c
__int64 __fastcall BasepCopySecurityInformation(
        __int64 a1,
        void *a2,
        int a3,
        __int64 a4,
        HANDLE a5,
        int a6,
        SECURITY_INFORMATION SecurityInfo,
        __int64 a8,
        char a9,
        _DWORD *a10,
        int a11)
{
  HANDLE v12; // r14
  BOOL v13; // esi
  SECURITY_INFORMATION v14; // edi
  SECURITY_INFORMATION v15; // r15d
  __int64 v16; // rbx
  int v17; // r13d
  unsigned int v18; // r14d
  HANDLE v19; // r13
  __int64 v20; // r9
  ULONG v21; // r14d
  bool v22; // r14
  __int64 AceByType; // rax
  HANDLE v24; // r15
  PSID v25; // r8
  DWORD v26; // eax
  NTSTATUS ControlSecurityDescriptor; // eax
  PACL v29; // rdx
  PACL v30; // rcx
  __int64 v31; // rdx
  PACL pSacl; // [rsp+48h] [rbp-59h] BYREF
  PVOID P; // [rsp+50h] [rbp-51h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-49h] BYREF
  ULONG Revision; // [rsp+60h] [rbp-41h] BYREF
  PSID v36; // [rsp+68h] [rbp-39h] BYREF
  PACL ppSacl; // [rsp+70h] [rbp-31h] BYREF
  PSID ppsidOwner; // [rsp+78h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+80h] [rbp-21h] BYREF
  PSID psidGroup; // [rsp+88h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+90h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR v42; // [rsp+98h] [rbp-9h] BYREF
  WORD Control; // [rsp+E8h] [rbp+47h] BYREF
  HANDLE handle; // [rsp+F0h] [rbp+4Fh]
  int v45; // [rsp+F8h] [rbp+57h]

  v45 = a3;
  handle = a2;
  v12 = a2;
  pDacl = 0;
  pSacl = 0;
  *a10 = 0;
  ppSacl = 0;
  P = 0;
  ppsidOwner = 0;
  psidGroup = 0;
  v36 = 0;
  ppSecurityDescriptor = 0;
  v42 = 0;
  hMem = 0;
  Control = 0;
  Revision = 0;
  if ( !a1 || !a4 || !(unsigned __int8)IsSetSecurityInfoPresent() )
  {
    v18 = 1;
    goto LABEL_40;
  }
  v13 = 1;
  if ( (a9 & 8) == 0 )
  {
    if ( (SecurityInfo & 0xFFFFFFDF) != 0 )
    {
      v31 = a8;
      if ( a8 )
      {
        *(_QWORD *)(a8 + 40) = a5;
        *(_DWORD *)(v31 + 20) = 1;
        *(_DWORD *)(v31 + 24) = 50;
        *(_QWORD *)(v31 + 64) = 0;
        *(_QWORD *)(v31 + 32) = v12;
      }
      v13 = BasepCopyFileCallback(20) != 0;
    }
    goto LABEL_39;
  }
  v14 = SecurityInfo;
  v15 = SecurityInfo;
  v16 = a8;
  v17 = a6;
  if ( (SecurityInfo & 4) != 0 && ((a3 & 0x80020000) == 0 || (a6 & 0x40000) == 0) )
  {
    v14 = SecurityInfo & 0xFFFFFFFB;
    if ( a8 )
    {
      *(_QWORD *)(a8 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 5;
      *(_QWORD *)(v16 + 64) = 0;
      *(_QWORD *)(v16 + 32) = v12;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(16) )
      goto LABEL_40;
    v12 = handle;
  }
  if ( (v15 & 3) != 0 && ((a3 & 0x80020000) == 0 || (v17 & 0x80000) == 0) )
  {
    v14 &= 0xFFFFFFFC;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 5;
      *(_QWORD *)(v16 + 64) = 0;
      *(_QWORD *)(v16 + 32) = v12;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(17) )
      goto LABEL_40;
  }
  if ( (v15 & 8) != 0 && (v17 & a3 & 0x1000000) == 0 )
  {
    v14 &= ~8u;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 32) = handle;
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 1314;
      *(_QWORD *)(v16 + 64) = 0;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(19) )
      goto LABEL_40;
  }
  if ( (v15 & 0x20) != 0 && ((v45 & 0x80020000) == 0 || v17 >= 0 || (v17 & 0x40000) == 0) )
    v14 &= ~0x20u;
  if ( (v15 & 0x10) != 0 && ((v45 & 0x80020000) == 0 || (v17 & 0x80000) == 0) )
  {
    v14 &= ~0x10u;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 32) = handle;
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 5;
      *(_QWORD *)(v16 + 64) = 0;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(19) )
      goto LABEL_40;
  }
  if ( !v14 )
    goto LABEL_39;
  if ( a11 )
    v15 = v14 | 1;
  v19 = handle;
  v21 = GetSecurityInfo(handle, SE_FILE_OBJECT, v15, &ppsidOwner, &psidGroup, &pDacl, &pSacl, &ppSecurityDescriptor);
  if ( !v21 )
  {
    v22 = 0;
    if ( (v14 & 0x20) != 0 && ((AceByType = RtlFindAceByType(pSacl, 18, 0), v22 = AceByType != 0, a11) || AceByType) )
    {
      v24 = a5;
      if ( GetSecurityInfo(a5, SE_FILE_OBJECT, 0x20u, 0, 0, 0, &ppSacl, &v42) )
        v14 &= ~0x20u;
    }
    else
    {
      v24 = a5;
    }
    if ( !pDacl )
      v14 &= ~4u;
    if ( !pSacl )
      v14 &= 0xFFFFFFC7;
    if ( (v14 & 0xC) != 0 )
    {
      ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(ppSecurityDescriptor, &Control, &Revision);
      if ( ControlSecurityDescriptor < 0 )
      {
        BaseSetLastNTError((unsigned int)ControlSecurityDescriptor);
        goto LABEL_70;
      }
    }
    if ( (v14 & 4) != 0 )
    {
      v14 |= (Control & 0x1000) != 0 ? 0x80000000 : 0x20000000;
      if ( a11 )
      {
        if ( GetSecurityInfo(v24, SE_FILE_OBJECT, 1u, &v36, 0, 0, 0, &hMem) )
        {
          v25 = 0;
          v36 = 0;
        }
        else
        {
          v25 = v36;
        }
        BasepCopyCreatorOwnerACE(pDacl, ppsidOwner, v25);
      }
    }
    if ( (v14 & 8) != 0 )
    {
      if ( (Control & 0x2000) != 0 )
        v14 |= 0x40000000u;
      else
        v14 |= 0x10000000u;
    }
    if ( (v14 & 0x20) == 0 )
    {
LABEL_37:
      while ( v14 )
      {
        v26 = SetSecurityInfo(v24, SE_FILE_OBJECT, v14, ppsidOwner, psidGroup, pDacl, pSacl);
        if ( !v26 )
          break;
        if ( (v14 & 3) != 0 )
        {
          if ( v16 )
          {
            *(_DWORD *)(v16 + 20) = 1;
            *(_DWORD *)(v16 + 24) = v26;
            *(_QWORD *)(v16 + 64) = 0;
            *(_QWORD *)(v16 + 32) = v19;
            *(_QWORD *)(v16 + 40) = v24;
          }
          if ( !(unsigned int)BasepCopyFileCallback(18) )
            goto LABEL_71;
          v14 &= 0xFFFFFFFC;
        }
        else
        {
          if ( v16 )
          {
            *(_DWORD *)(v16 + 20) = 1;
            *(_DWORD *)(v16 + 24) = v26;
            *(_QWORD *)(v16 + 64) = 0;
            *(_QWORD *)(v16 + 32) = v19;
            *(_QWORD *)(v16 + 40) = v24;
          }
          if ( !(unsigned int)BasepCopyFileCallback(16) )
            goto LABEL_71;
          v14 = 0;
        }
      }
      goto LABEL_39;
    }
    if ( a11 )
    {
      v29 = pSacl;
      LOBYTE(v20) = 1;
      v30 = ppSacl;
    }
    else
    {
      if ( !v22 )
      {
LABEL_76:
        if ( P )
          pSacl = (PACL)P;
        goto LABEL_37;
      }
      v29 = ppSacl;
      v20 = 0;
      v30 = pSacl;
    }
    if ( (int)RtlpMergeSecurityAttributeInformation(v30, v29, &P, v20) < 0 )
      goto LABEL_37;
    goto LABEL_76;
  }
  if ( RtlGetLastNtStatus() == -1073741637 )
  {
    if ( v16 )
    {
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 50;
      *(_QWORD *)(v16 + 64) = 0;
      *(_QWORD *)(v16 + 32) = v19;
    }
    if ( (unsigned int)BasepCopyFileCallback(20) )
    {
LABEL_39:
      v18 = v13;
      goto LABEL_40;
    }
  }
  RtlSetLastWin32Error(v21);
LABEL_70:
  *a10 = 1;
LABEL_71:
  v18 = 0;
LABEL_40:
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  if ( v42 )
    LocalFree(v42);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return v18;
}

```

## disassembly

```asm
0x1800d60d8  mov     rax, rsp
0x1800d60db  mov     [rax+20h], rbx
0x1800d60df  mov     [rax+18h], r8d
0x1800d60e3  mov     [rax+10h], rdx
0x1800d60e7  push    rbp
0x1800d60e8  push    rsi
0x1800d60e9  push    rdi
0x1800d60ea  push    r12
0x1800d60ec  push    r13
0x1800d60ee  push    r14
0x1800d60f0  push    r15
0x1800d60f2  lea     rbp, [rax-3Fh]
0x1800d60f6  sub     rsp, 0A0h
0x1800d60fd  mov     rax, [rbp+37h+arg_48]
0x1800d6104  mov     r12d, r8d
0x1800d6107  xor     r8d, r8d
0x1800d610a  mov     r14, rdx
0x1800d610d  mov     [rbp+37h+pDacl], r8
0x1800d6111  mov     [rbp+37h+pSacl], r8
0x1800d6115  mov     [rax], r8d
0x1800d6118  mov     [rbp+37h+var_68], r8
0x1800d611c  mov     [rbp+37h+P], r8
0x1800d6120  mov     [rbp+37h+ppsidOwner], r8
0x1800d6124  mov     [rbp+37h+psidGroup], r8
0x1800d6128  mov     [rbp+37h+var_70], r8
0x1800d612c  mov     [rbp+37h+ppSecurityDescriptor], r8
0x1800d6130  mov     [rbp+37h+var_40], r8
0x1800d6134  mov     [rbp+37h+hMem], r8
0x1800d6138  mov     [rbp+37h+Control], r8w
0x1800d613d  mov     [rbp+37h+Revision], r8d
0x1800d6141  test    rcx, rcx
0x1800d6144  jz      loc_1800D61CB
0x1800d614a  test    r9, r9
0x1800d614d  jz      short loc_1800D61CB
0x1800d614f  call    IsSetSecurityInfoPresent
0x1800d6154  xor     r8d, r8d
0x1800d6157  test    al, al
0x1800d6159  jz      short loc_1800D61CB
0x1800d615b  test    [rbp+37h+arg_40], 8
0x1800d6162  lea     esi, [r8+1]
0x1800d6166  jz      loc_1800D662D
0x1800d616c  mov     edi, [rbp+37h+SecurityInfo]
0x1800d616f  mov     r15d, edi
0x1800d6172  mov     rbx, [rbp+37h+arg_38]
0x1800d6176  mov     r13d, [rbp+37h+arg_28]
0x1800d617a  test    dil, 4
0x1800d617e  jnz     loc_1800D64F3
0x1800d6184  test    r15b, 3
0x1800d6188  jz      short loc_1800D61D6
0x1800d618a  test    r12d, 80020000h
0x1800d6191  setnz   cl
0x1800d6194  bt      r13d, 13h
0x1800d6199  setb    al
0x1800d619c  test    al, cl
0x1800d619e  jnz     short loc_1800D61D6
0x1800d61a0  and     edi, 0FFFFFFFCh
0x1800d61a3  test    rbx, rbx
0x1800d61a6  jz      loc_1801A0C37
0x1800d61ac  mov     rax, [rbp+37h+arg_20]
0x1800d61b0  mov     [rbx+28h], rax
0x1800d61b4  mov     [rbx+14h], esi
0x1800d61b7  mov     dword ptr [rbx+18h], 5
0x1800d61be  mov     [rbx+40h], r8
0x1800d61c2  mov     [rbx+20h], r14
0x1800d61c6  jmp     loc_1801A0C37
0x1800d61cb  mov     r14d, 1
0x1800d61d1  jmp     loc_1800D63F2
0x1800d61d6  test    r15b, 8
0x1800d61da  jnz     loc_1800D64A5
0x1800d61e0  mov     eax, [rbp+37h+arg_10]
0x1800d61e3  mov     r12d, 0FFFFFFDFh
0x1800d61e9  test    r15b, 20h
0x1800d61ed  jz      short loc_1800D620E
0x1800d61ef  test    eax, 80020000h
0x1800d61f4  jz      loc_1800D661C
0x1800d61fa  test    r13d, r13d
0x1800d61fd  jns     loc_1800D661C
0x1800d6203  bt      r13d, 12h
0x1800d6208  jnb     loc_1800D661C
0x1800d620e  test    r15b, 10h
0x1800d6212  jnz     loc_1800D6461
0x1800d6218  test    edi, edi
0x1800d621a  jz      loc_1800D63EF
0x1800d6220  cmp     [rbp+37h+arg_50], r8d
0x1800d6227  jz      short loc_1800D622F
0x1800d6229  mov     r15d, edi
0x1800d622c  or      r15d, esi
0x1800d622f  mov     r13, [rbp+37h+handle]
0x1800d6233  lea     rax, [rbp+37h+ppSecurityDescriptor]
0x1800d6237  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800d623c  lea     r9, [rbp+37h+ppsidOwner]; ppsidOwner
0x1800d6240  lea     rax, [rbp+37h+pSacl]
0x1800d6244  mov     r8d, r15d; SecurityInfo
0x1800d6247  mov     [rsp+0D0h+ppSacl], rax; ppSacl
0x1800d624c  mov     edx, esi; ObjectType
0x1800d624e  lea     rax, [rbp+37h+pDacl]
0x1800d6252  mov     rcx, r13; handle
0x1800d6255  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x1800d625a  lea     rax, [rbp+37h+psidGroup]
0x1800d625e  mov     [rsp+0D0h+ppsidGroup], rax; ppsidGroup
0x1800d6263  call    cs:__imp_GetSecurityInfo
0x1800d626a  nop     dword ptr [rax+rax+00h]
0x1800d626f  xor     r15d, r15d
0x1800d6272  mov     r14d, eax
0x1800d6275  test    eax, eax
0x1800d6277  jnz     loc_1800D6566
0x1800d627d  mov     r14b, r15b
0x1800d6280  test    dil, 20h
0x1800d6284  jz      loc_1800D64EA
0x1800d628a  mov     rcx, [rbp+37h+pSacl]
0x1800d628e  lea     edx, [rax+12h]
0x1800d6291  xor     r8d, r8d
0x1800d6294  call    cs:__imp_RtlFindAceByType
0x1800d629b  nop     dword ptr [rax+rax+00h]
0x1800d62a0  test    rax, rax
0x1800d62a3  setnz   r14b
0x1800d62a7  cmp     [rbp+37h+arg_50], r15d
0x1800d62ae  jz      loc_1800D64E1
0x1800d62b4  lea     rax, [rbp+37h+var_40]
0x1800d62b8  xor     r9d, r9d; ppsidOwner
0x1800d62bb  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800d62c0  mov     edx, esi; ObjectType
0x1800d62c2  lea     rax, [rbp+37h+var_68]
0x1800d62c6  mov     [rsp+0D0h+ppSacl], rax; ppSacl
0x1800d62cb  mov     [rsp+0D0h+ppDacl], r15; ppDacl
0x1800d62d0  lea     r8d, [r9+20h]; SecurityInfo
0x1800d62d4  mov     [rsp+0D0h+ppsidGroup], r15; ppsidGroup
0x1800d62d9  mov     r15, [rbp+37h+arg_20]
0x1800d62dd  mov     rcx, r15; handle
0x1800d62e0  call    cs:__imp_GetSecurityInfo
0x1800d62e7  nop     dword ptr [rax+rax+00h]
0x1800d62ec  test    eax, eax
0x1800d62ee  jnz     loc_1800D672D
0x1800d62f4  cmp     [rbp+37h+pDacl], 0
0x1800d62f9  jnz     short loc_1800D62FE
0x1800d62fb  and     edi, 0FFFFFFFBh
0x1800d62fe  cmp     [rbp+37h+pSacl], 0
0x1800d6303  jnz     short loc_1800D6308
0x1800d6305  and     edi, 0FFFFFFC7h
0x1800d6308  test    dil, 0Ch
0x1800d630c  jnz     loc_1800D653D
0x1800d6312  test    dil, 4
0x1800d6316  jz      loc_1800D639C
0x1800d631c  movzx   eax, [rbp+37h+Control]
0x1800d6320  mov     ecx, 1000h
0x1800d6325  and     ax, cx
0x1800d6328  neg     ax
0x1800d632b  sbb     ecx, ecx
0x1800d632d  and     ecx, 60000000h
0x1800d6333  add     ecx, 20000000h
0x1800d6339  or      edi, ecx
0x1800d633b  cmp     [rbp+37h+arg_50], 0
0x1800d6342  jz      short loc_1800D639C
0x1800d6344  lea     rax, [rbp+37h+hMem]
0x1800d6348  mov     r8d, esi; SecurityInfo
0x1800d634b  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800d6350  lea     r9, [rbp+37h+var_70]; ppsidOwner
0x1800d6354  mov     [rsp+0D0h+ppSacl], 0; ppSacl
0x1800d635d  mov     edx, esi; ObjectType
0x1800d635f  mov     [rsp+0D0h+ppDacl], 0; ppDacl
0x1800d6368  mov     rcx, r15; handle
0x1800d636b  mov     [rsp+0D0h+ppsidGroup], 0; ppsidGroup
0x1800d6374  call    cs:__imp_GetSecurityInfo
0x1800d637b  nop     dword ptr [rax+rax+00h]
0x1800d6380  test    eax, eax
0x1800d6382  jz      loc_1800D6624
0x1800d6388  xor     r8d, r8d; PSID
0x1800d638b  mov     [rbp+37h+var_70], r8
0x1800d638f  mov     rdx, [rbp+37h+ppsidOwner]; Sid1
0x1800d6393  mov     rcx, [rbp+37h+pDacl]; Acl
0x1800d6397  call    BasepCopyCreatorOwnerACE
0x1800d639c  test    dil, 8
0x1800d63a0  jnz     loc_1800D6735
0x1800d63a6  test    dil, 20h
0x1800d63aa  jnz     loc_1800D659D
0x1800d63b0  test    edi, edi
0x1800d63b2  jz      short loc_1800D63EF
0x1800d63b4  mov     rax, [rbp+37h+pSacl]
0x1800d63b8  mov     r8d, edi; SecurityInfo
0x1800d63bb  mov     r9, [rbp+37h+ppsidOwner]; psidOwner
0x1800d63bf  mov     edx, esi; ObjectType
0x1800d63c1  mov     [rsp+0D0h+ppSacl], rax; pSacl
0x1800d63c6  mov     rcx, r15; handle
0x1800d63c9  mov     rax, [rbp+37h+pDacl]
0x1800d63cd  mov     [rsp+0D0h+ppDacl], rax; pDacl
0x1800d63d2  mov     rax, [rbp+37h+psidGroup]
0x1800d63d6  mov     [rsp+0D0h+ppsidGroup], rax; psidGroup
0x1800d63db  call    cs:__imp_SetSecurityInfo
0x1800d63e2  nop     dword ptr [rax+rax+00h]
0x1800d63e7  test    eax, eax
0x1800d63e9  jnz     loc_1800D65F1
0x1800d63ef  mov     r14d, esi
0x1800d63f2  mov     rcx, [rbp+37h+ppSecurityDescriptor]; hMem
0x1800d63f6  test    rcx, rcx
0x1800d63f9  jz      short loc_1800D6400
0x1800d63fb  call    LocalFree
0x1800d6400  mov     rcx, [rbp+37h+hMem]; hMem
0x1800d6404  test    rcx, rcx
0x1800d6407  jz      short loc_1800D640E
0x1800d6409  call    LocalFree
0x1800d640e  mov     rcx, [rbp+37h+var_40]; hMem
0x1800d6412  test    rcx, rcx
0x1800d6415  jz      short loc_1800D641C
0x1800d6417  call    LocalFree
0x1800d641c  cmp     [rbp+37h+P], 0
0x1800d6421  jz      short loc_1800D6442
0x1800d6423  mov     rcx, gs:60h
0x1800d642c  xor     edx, edx; Flags
0x1800d642e  mov     r8, [rbp+37h+P]; P
0x1800d6432  mov     rcx, [rcx+30h]; HeapHandle
0x1800d6436  call    cs:__imp_RtlFreeHeap
0x1800d643d  nop     dword ptr [rax+rax+00h]
0x1800d6442  mov     rbx, [rsp+0D0h+arg_18]
0x1800d644a  mov     eax, r14d
0x1800d644d  add     rsp, 0A0h
0x1800d6454  pop     r15
0x1800d6456  pop     r14
0x1800d6458  pop     r13
0x1800d645a  pop     r12
0x1800d645c  pop     rdi
0x1800d645d  pop     rsi
0x1800d645e  pop     rbp
0x1800d645f  retn
0x1800d6461  test    eax, 80020000h
0x1800d6466  setnz   cl
0x1800d6469  bt      r13d, 13h
0x1800d646e  setb    al
0x1800d6471  test    al, cl
0x1800d6473  jnz     loc_1800D6218
0x1800d6479  and     edi, 0FFFFFFEFh
0x1800d647c  test    rbx, rbx
0x1800d647f  jnz     loc_1800D670A
0x1800d6485  mov     rdx, rbx
0x1800d6488  mov     ecx, 13h
0x1800d648d  mov     r14d, r8d
0x1800d6490  call    BasepCopyFileCallback
0x1800d6495  xor     r8d, r8d
0x1800d6498  test    eax, eax
0x1800d649a  jz      loc_1800D63F2
0x1800d64a0  jmp     loc_1800D6218
0x1800d64a5  mov     eax, r12d
0x1800d64a8  and     eax, r13d
0x1800d64ab  bt      eax, 18h
0x1800d64af  jb      loc_1800D61E0
0x1800d64b5  and     edi, 0FFFFFFF7h
0x1800d64b8  test    rbx, rbx
0x1800d64bb  jnz     loc_1800D66E7
0x1800d64c1  mov     rdx, rbx
0x1800d64c4  mov     ecx, 13h
0x1800d64c9  mov     r14d, r8d
0x1800d64cc  call    BasepCopyFileCallback
0x1800d64d1  xor     r8d, r8d
0x1800d64d4  test    eax, eax
0x1800d64d6  jnz     loc_1800D61E0
0x1800d64dc  jmp     loc_1800D63F2
0x1800d64e1  test    rax, rax
0x1800d64e4  jnz     loc_1800D62B4
0x1800d64ea  mov     r15, [rbp+37h+arg_20]
0x1800d64ee  jmp     loc_1800D62F4
0x1800d64f3  test    r12d, 80020000h
0x1800d64fa  setnz   cl
0x1800d64fd  bt      r13d, 12h
0x1800d6502  setb    al
0x1800d6505  test    al, cl
0x1800d6507  jnz     loc_1800D6184
0x1800d650d  and     edi, 0FFFFFFFBh
0x1800d6510  test    rbx, rbx
0x1800d6513  jnz     loc_1800D66C8
0x1800d6519  mov     rdx, rbx
0x1800d651c  mov     ecx, 10h
0x1800d6521  mov     r14d, r8d
0x1800d6524  call    BasepCopyFileCallback
0x1800d6529  xor     r8d, r8d
0x1800d652c  test    eax, eax
0x1800d652e  jz      loc_1800D63F2
0x1800d6534  mov     r14, [rbp+37h+handle]
0x1800d6538  jmp     loc_1800D6184
0x1800d653d  mov     rcx, [rbp+37h+ppSecurityDescriptor]; SecurityDescriptor
0x1800d6541  lea     r8, [rbp+37h+Revision]; Revision
0x1800d6545  lea     rdx, [rbp+37h+Control]; Control
0x1800d6549  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800d6550  nop     dword ptr [rax+rax+00h]
0x1800d6555  test    eax, eax
0x1800d6557  jns     loc_1800D6312
0x1800d655d  mov     ecx, eax
0x1800d655f  call    BaseSetLastNTError
0x1800d6564  jmp     short loc_1800D658C
0x1800d6566  call    cs:__imp_RtlGetLastNtStatus
0x1800d656d  nop     dword ptr [rax+rax+00h]
0x1800d6572  cmp     eax, 0C00000BBh
0x1800d6577  jz      loc_1800D6669
0x1800d657d  mov     ecx, r14d; LastError
0x1800d6580  call    cs:__imp_RtlSetLastWin32Error
0x1800d6587  nop     dword ptr [rax+rax+00h]
0x1800d658c  mov     rax, [rbp+37h+arg_48]
0x1800d6593  mov     [rax], esi
0x1800d6595  xor     r14d, r14d
0x1800d6598  jmp     loc_1800D63F2
0x1800d659d  cmp     [rbp+37h+arg_50], 0
0x1800d65a4  jnz     short loc_1800D65E4
  ... truncated ...
```
