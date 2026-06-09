# SetSecurityDescriptorOnNamedPipe(ushort *)

- ea: `0x18003827c`
- end: `0x1800385d0`
- name: `?SetSecurityDescriptorOnNamedPipe@@YAJPEAG@Z`
- size: `852`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180036f60`

## callees

- `0x18000d060`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x180036b78`
- `0x18003827c`
- `0x1800a0fb0`

## import_xrefs

- `ADVAPI32!SetKernelObjectSecurity` at `0x180038515`
- `ADVAPI32!SetKernelObjectSecurity` at `0x180038515`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180038431`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180038431`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800384fa`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800384fa`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800384dc`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800384dc`
- `ntdll!RtlAddMandatoryAce` at `0x1800384c7`
- `ntdll!RtlAddMandatoryAce` at `0x1800384c7`
- `ntdll!RtlCreateAcl` at `0x1800384a0`
- `ntdll!RtlCreateAcl` at `0x1800384a0`
- `KERNEL32!CreateFileW` at `0x1800383cf`
- `KERNEL32!CreateFileW` at `0x1800383cf`
- `KERNEL32!GetLastError` at `0x18003832e`
- `KERNEL32!GetLastError` at `0x1800383f6`
- `KERNEL32!GetLastError` at `0x180038453`
- `KERNEL32!GetLastError` at `0x180038548`
- `KERNEL32!GetLastError` at `0x18003832e`
- `KERNEL32!GetLastError` at `0x1800383f6`
- `KERNEL32!GetLastError` at `0x180038453`
- `KERNEL32!GetLastError` at `0x180038548`
- `KERNEL32!CloseHandle` at `0x18003847d`
- `KERNEL32!CloseHandle` at `0x180038526`
- `KERNEL32!CloseHandle` at `0x18003847d`
- `KERNEL32!CloseHandle` at `0x180038526`

## string_xrefs

- `0x1800382dc`: `SetSecurityDescriptorOnNamedPipe`
- `0x18003858d`: `SetSecurityDescriptorOnNamedPipe`

## pseudocode

```c
__int64 __fastcall SetSecurityDescriptorOnNamedPipe(unsigned __int16 *a1)
{
  PVOID *v1; // rcx
  DWORD v2; // eax
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  DWORD v6; // eax
  unsigned int v7; // esi
  BOOL v8; // ebx
  DWORD v9; // eax
  PSID LabelSid; // [rsp+30h] [rbp-D8h]
  PSID Sid; // [rsp+48h] [rbp-C0h] BYREF
  _ACL Acl; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR FileName[512]; // [rsp+258h] [rbp+150h] BYREF
  _BYTE SecurityDescriptor[2048]; // [rsp+658h] [rbp+550h] BYREF

  Sid = 0;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
        L"SetSecurityDescriptorOnNamedPipe");
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x20) != 0 )
      WPP_SF_(v1[2], 23, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids);
  }
  if ( (unsigned int)EnableSinglePrivilege((int)v1) )
  {
    StringCchPrintfW(FileName, 0x200u, L"\\\\.%s", L"\\pipe\\HydraLsPipe");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, FileName);
    FileW = CreateFileW(FileName, 0xA0000u, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, LastError);
      }
      return 4294967293LL;
    }
    else if ( ConvertStringSidToSidW(L"S-1-16-0", &Sid) )
    {
      RtlCreateAcl(&Acl, 0x200u, 2u);
      LODWORD(LabelSid) = 1;
      RtlAddMandatoryAce(&Acl, 2u, 0, (ULONG)Sid, 0x11u, LabelSid);
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      v7 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
      v8 = SetKernelObjectSecurity(FileW, 0x10u, SecurityDescriptor);
      CloseHandle(FileW);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids,
            L"SetSecurityDescriptorOnNamedPipe");
        return v7;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          v9 = GetLastError();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, v9);
        }
        return 1;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v6 = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, v6);
      }
      CloseHandle(FileW);
      return 0xFFFFFFFFLL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v2 = GetLastError();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids, v2);
    }
    return 4294967294LL;
  }
}

```

## disassembly

```asm
0x18003827c  mov     rax, rsp
0x18003827f  mov     [rax+8], rbx
0x180038283  mov     [rax+10h], rsi
0x180038287  mov     [rax+18h], rdi
0x18003828b  push    rbp
0x18003828c  push    r14
0x18003828e  push    r15
0x180038290  lea     rbp, [rax-0D78h]
0x180038297  sub     rsp, 0E60h
0x18003829e  mov     rax, cs:__security_cookie
0x1800382a5  xor     rax, rsp
0x1800382a8  mov     [rbp+0D70h+var_20], rax
0x1800382af  and     [rsp+0E70h+Sid], 0
0x1800382b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382bc  lea     r14, WPP_GLOBAL_Control
0x1800382c3  lea     r15, WPP_15e20df975a33ff5e9de8750bd5480b2_Traceguids
0x1800382ca  cmp     rcx, r14
0x1800382cd  jz      short loc_180038313
0x1800382cf  test    dword ptr [rcx+1Ch], 1000h
0x1800382d6  jz      short loc_1800382F7
0x1800382d8  mov     rcx, [rcx+10h]
0x1800382dc  lea     r9, aSetsecuritydes; "SetSecurityDescriptorOnNamedPipe"
0x1800382e3  mov     edx, 16h
0x1800382e8  mov     r8, r15
0x1800382eb  call    WPP_SF_S
0x1800382f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382f7  cmp     rcx, r14
0x1800382fa  jz      short loc_180038313
0x1800382fc  test    byte ptr [rcx+1Ch], 20h
0x180038300  jz      short loc_180038313
0x180038302  mov     rcx, [rcx+10h]
0x180038306  mov     edx, 17h
0x18003830b  mov     r8, r15
0x18003830e  call    WPP_SF_
0x180038313  call    ?EnableSinglePrivilege@@YAHJ@Z; EnableSinglePrivilege(long)
0x180038318  test    eax, eax
0x18003831a  jnz     short loc_18003835F
0x18003831c  mov     rax, cs:WPP_GLOBAL_Control
0x180038323  cmp     rax, r14
0x180038326  jz      short loc_180038355
0x180038328  test    byte ptr [rax+1Ch], 20h
0x18003832c  jz      short loc_180038355
0x18003832e  call    cs:__imp_GetLastError
0x180038335  nop     dword ptr [rax+rax+00h]
0x18003833a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038341  mov     edx, 18h
0x180038346  mov     r9d, eax
0x180038349  mov     r8, r15
0x18003834c  mov     rcx, [rcx+10h]
0x180038350  call    WPP_SF_D
0x180038355  mov     eax, 0FFFFFFFEh
0x18003835a  jmp     loc_1800385A3
0x18003835f  mov     esi, 200h
0x180038364  lea     r9, Endpoint; "\\pipe\\HydraLsPipe"
0x18003836b  mov     edx, esi; unsigned __int64
0x18003836d  lea     r8, aS_0; "\\\\.%s"
0x180038374  lea     rcx, [rbp+0D70h+FileName]; unsigned __int16 *
0x18003837b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038380  mov     rcx, cs:WPP_GLOBAL_Control
0x180038387  cmp     rcx, r14
0x18003838a  jz      short loc_1800383AA
0x18003838c  test    byte ptr [rcx+1Ch], 20h
0x180038390  jz      short loc_1800383AA
0x180038392  mov     rcx, [rcx+10h]
0x180038396  lea     r9, [rbp+0D70h+FileName]
0x18003839d  mov     edx, 19h
0x1800383a2  mov     r8, r15
0x1800383a5  call    WPP_SF_S
0x1800383aa  and     [rsp+0E70h+var_E40], 0
0x1800383b0  lea     rcx, [rbp+0D70h+FileName]; lpFileName
0x1800383b7  and     dword ptr [rsp+0E70h+LabelSid], 0
0x1800383bc  xor     r9d, r9d; lpSecurityAttributes
0x1800383bf  xor     r8d, r8d; dwShareMode
0x1800383c2  mov     [rsp+0E70h+dwCreationDisposition], 3; dwCreationDisposition
0x1800383ca  mov     edx, 0A0000h; dwDesiredAccess
0x1800383cf  call    cs:__imp_CreateFileW
0x1800383d6  nop     dword ptr [rax+rax+00h]
0x1800383db  mov     rdi, rax
0x1800383de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800383e2  jnz     short loc_180038425
0x1800383e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800383eb  cmp     rax, r14
0x1800383ee  jz      short loc_18003841B
0x1800383f0  test    byte ptr [rax+1Ch], 20h
0x1800383f4  jz      short loc_18003841B
0x1800383f6  call    cs:__imp_GetLastError
0x1800383fd  nop     dword ptr [rax+rax+00h]
0x180038402  mov     rcx, cs:WPP_GLOBAL_Control
0x180038409  lea     edx, [rdi+1Bh]
0x18003840c  mov     r9d, eax
0x18003840f  mov     r8, r15
0x180038412  mov     rcx, [rcx+10h]
0x180038416  call    WPP_SF_D
0x18003841b  mov     eax, 0FFFFFFFDh
0x180038420  jmp     loc_1800385A3
0x180038425  lea     rdx, [rsp+0E70h+Sid]; Sid
0x18003842a  lea     rcx, aS1160; "S-1-16-0"
0x180038431  call    cs:__imp_ConvertStringSidToSidW
0x180038438  nop     dword ptr [rax+rax+00h]
0x18003843d  test    eax, eax
0x18003843f  jnz     short loc_180038491
0x180038441  mov     rax, cs:WPP_GLOBAL_Control
0x180038448  cmp     rax, r14
0x18003844b  jz      short loc_18003847A
0x18003844d  test    byte ptr [rax+1Ch], 20h
0x180038451  jz      short loc_18003847A
0x180038453  call    cs:__imp_GetLastError
0x18003845a  nop     dword ptr [rax+rax+00h]
0x18003845f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038466  mov     edx, 1Bh
0x18003846b  mov     r9d, eax
0x18003846e  mov     r8, r15
0x180038471  mov     rcx, [rcx+10h]
0x180038475  call    WPP_SF_D
0x18003847a  mov     rcx, rdi; hObject
0x18003847d  call    cs:__imp_CloseHandle
0x180038484  nop     dword ptr [rax+rax+00h]
0x180038489  or      eax, 0FFFFFFFFh
0x18003848c  jmp     loc_1800385A3
0x180038491  mov     ebx, 2
0x180038496  lea     rcx, [rsp+0E70h+Acl]; Acl
0x18003849b  mov     r8d, ebx; AclRevision
0x18003849e  mov     edx, esi; AclSize
0x1800384a0  call    cs:__imp_RtlCreateAcl
0x1800384a7  nop     dword ptr [rax+rax+00h]
0x1800384ac  mov     r9, [rsp+0E70h+Sid]; MandatoryFlags
0x1800384b1  lea     esi, [rbx-1]
0x1800384b4  mov     dword ptr [rsp+0E70h+LabelSid], esi; LabelSid
0x1800384b8  lea     rcx, [rsp+0E70h+Acl]; Acl
0x1800384bd  xor     r8d, r8d; Flags
0x1800384c0  mov     byte ptr [rsp+0E70h+dwCreationDisposition], 11h; AceType
0x1800384c5  mov     edx, ebx; Revision
0x1800384c7  call    cs:__imp_RtlAddMandatoryAce
0x1800384ce  nop     dword ptr [rax+rax+00h]
0x1800384d3  mov     edx, esi; Revision
0x1800384d5  lea     rcx, [rbp+0D70h+SecurityDescriptor]; SecurityDescriptor
0x1800384dc  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800384e3  nop     dword ptr [rax+rax+00h]
0x1800384e8  xor     r9d, r9d; SaclDefaulted
0x1800384eb  lea     r8, [rsp+0E70h+Acl]; Sacl
0x1800384f0  mov     dl, sil; SaclPresent
0x1800384f3  lea     rcx, [rbp+0D70h+SecurityDescriptor]; SecurityDescriptor
0x1800384fa  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180038501  nop     dword ptr [rax+rax+00h]
0x180038506  lea     r8, [rbp+0D70h+SecurityDescriptor]; SecurityDescriptor
0x18003850d  mov     rcx, rdi; Handle
0x180038510  lea     edx, [rbx+0Eh]; SecurityInformation
0x180038513  mov     esi, eax
0x180038515  call    cs:__imp_SetKernelObjectSecurity
0x18003851c  nop     dword ptr [rax+rax+00h]
0x180038521  mov     rcx, rdi; hObject
0x180038524  mov     ebx, eax
0x180038526  call    cs:__imp_CloseHandle
0x18003852d  nop     dword ptr [rax+rax+00h]
0x180038532  test    ebx, ebx
0x180038534  jnz     short loc_180038574
0x180038536  mov     rcx, cs:WPP_GLOBAL_Control
0x18003853d  cmp     rcx, r14
0x180038540  jz      short loc_18003856D
0x180038542  test    byte ptr [rcx+1Ch], 20h
0x180038546  jz      short loc_18003856D
0x180038548  call    cs:__imp_GetLastError
0x18003854f  nop     dword ptr [rax+rax+00h]
0x180038554  mov     rcx, cs:WPP_GLOBAL_Control
0x18003855b  lea     edx, [rbx+1Ch]
0x18003855e  mov     r9d, eax
0x180038561  mov     r8, r15
0x180038564  mov     rcx, [rcx+10h]
0x180038568  call    WPP_SF_D
0x18003856d  mov     eax, 1
0x180038572  jmp     short loc_1800385A3
0x180038574  mov     rcx, cs:WPP_GLOBAL_Control
0x18003857b  cmp     rcx, r14
0x18003857e  jz      short loc_1800385A1
0x180038580  test    dword ptr [rcx+1Ch], 1000h
0x180038587  jz      short loc_1800385A1
0x180038589  mov     rcx, [rcx+10h]
0x18003858d  lea     r9, aSetsecuritydes; "SetSecurityDescriptorOnNamedPipe"
0x180038594  mov     edx, 1Dh
0x180038599  mov     r8, r15
0x18003859c  call    WPP_SF_S
0x1800385a1  mov     eax, esi
0x1800385a3  mov     rcx, [rbp+0D70h+var_20]
0x1800385aa  xor     rcx, rsp; StackCookie
0x1800385ad  call    __security_check_cookie
0x1800385b2  lea     r11, [rsp+0E70h+var_10]
0x1800385ba  mov     rbx, [r11+20h]
0x1800385be  mov     rsi, [r11+28h]
0x1800385c2  mov     rdi, [r11+30h]
0x1800385c6  mov     rsp, r11
0x1800385c9  pop     r15
0x1800385cb  pop     r14
0x1800385cd  pop     rbp
0x1800385ce  retn
```
