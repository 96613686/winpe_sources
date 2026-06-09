# UtilIsCurrentProcessInteractive(void)

- ea: `0x180026ed4`
- end: `0x1800270bc`
- name: `?UtilIsCurrentProcessInteractive@@YAHXZ`
- size: `488`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180011a38`
- `0x18002c8c8`
- `0x18002f798`
- `0x180034498`
- `0x180035fe4`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180026ed4`
- `0x1800270c4`
- `0x18003b790`
- `0x18003b8c8`
- `0x18003ba00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180026fda`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180026fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026fed`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026f38`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026f38`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026f7a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026f7a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180027093`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180027093`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027054`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027025`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 UtilIsCurrentProcessInteractive(void)
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  HANDLE v2; // rax
  LSTATUS v3; // ebx
  HKEY v4; // rcx
  unsigned int v5; // ebx
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  HKEY hKey; // [rsp+78h] [rbp+27h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+2Fh] BYREF
  HKEY *p_hKey; // [rsp+88h] [rbp+37h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp+47h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = 16;
LABEL_5:
      WPP_SF_(v0[2], v1, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = 17;
      goto LABEL_5;
    }
LABEL_12:
    if ( IsMember )
      goto LABEL_25;
    goto LABEL_13;
  }
  if ( IsMember )
  {
    IsMember = UtilIsInteractiveDesktop();
    goto LABEL_12;
  }
LABEL_13:
  if ( UtilIsSystem()
    && (unsigned int)UtilIsInteractiveDesktop()
    && (v2 = OpenMutexW(0x1F0001u, 0, L"Global\\Microsoft.Windows.Setup"), (unsigned __int64)v2 + 1 > 1) )
  {
    CloseHandle(v2);
  }
  else
  {
    phkResult = 0;
    p_hKey = &hKey;
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &phkResult);
    if ( phkResult )
    {
      v4 = *p_hKey;
      *p_hKey = phkResult;
      if ( v4 )
        RegCloseKey(v4);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v3 || !(unsigned int)UtilIsInteractiveDesktop() )
      goto LABEL_28;
  }
  IsMember = 1;
LABEL_25:
  if ( (unsigned int)UtilIsWindowManagerToken(v0) && !UtilIsVirtualServer() )
  {
    v5 = IsMember;
    goto LABEL_29;
  }
LABEL_28:
  v5 = 0;
  IsMember = 0;
LABEL_29:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v5;
}

```

## disassembly

```asm
0x180026ed4  mov     r11, rsp
0x180026ed7  mov     [r11+8], rbx
0x180026edb  mov     [r11+10h], rdi
0x180026edf  push    rbp
0x180026ee0  lea     rbp, [r11-5Fh]
0x180026ee4  sub     rsp, 0A0h
0x180026eeb  mov     rax, cs:__security_cookie
0x180026ef2  xor     rax, rsp
0x180026ef5  mov     [rbp+57h+var_8], rax
0x180026ef9  xor     edi, edi
0x180026efb  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180026efe  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180026f04  mov     [rbp+57h+IsMember], edi
0x180026f07  mov     [rbp+57h+SidToCheck], rdi
0x180026f0b  lea     rax, [rbp+57h+SidToCheck]
0x180026f0f  mov     [r11-58h], rax
0x180026f13  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x180026f17  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x180026f1b  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x180026f1f  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x180026f23  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x180026f27  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x180026f2b  xor     r9d, r9d; nSubAuthority1
0x180026f2e  lea     r8d, [rdi+4]; nSubAuthority0
0x180026f32  mov     dl, 1; nSubAuthorityCount
0x180026f34  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180026f38  call    cs:__imp_AllocateAndInitializeSid
0x180026f3e  test    eax, eax
0x180026f40  jnz     short loc_180026F70
0x180026f42  lea     rax, WPP_GLOBAL_Control
0x180026f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f50  cmp     rcx, rax
0x180026f53  jz      short loc_180026FB1
0x180026f55  test    byte ptr [rcx+1Ch], 1
0x180026f59  jz      short loc_180026FB1
0x180026f5b  lea     edx, [rdi+10h]
0x180026f5e  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x180026f65  mov     rcx, [rcx+10h]
0x180026f69  call    WPP_SF_
0x180026f6e  jmp     short loc_180026FB1
0x180026f70  lea     r8, [rbp+57h+IsMember]; IsMember
0x180026f74  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180026f78  xor     ecx, ecx; TokenHandle
0x180026f7a  call    cs:__imp_CheckTokenMembership
0x180026f80  test    eax, eax
0x180026f82  jnz     short loc_180026FA4
0x180026f84  lea     rax, WPP_GLOBAL_Control
0x180026f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f92  cmp     rcx, rax
0x180026f95  jz      short loc_180026FB1
0x180026f97  test    byte ptr [rcx+1Ch], 1
0x180026f9b  jz      short loc_180026FB1
0x180026f9d  mov     edx, 11h
0x180026fa2  jmp     short loc_180026F5E
0x180026fa4  cmp     [rbp+57h+IsMember], edi
0x180026fa7  jz      short loc_180026FBA
0x180026fa9  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x180026fae  mov     [rbp+57h+IsMember], eax
0x180026fb1  cmp     [rbp+57h+IsMember], edi
0x180026fb4  jnz     loc_18002706E
0x180026fba  call    ?UtilIsSystem@@YA_NXZ; UtilIsSystem(void)
0x180026fbf  test    al, al
0x180026fc1  jz      short loc_180026FF5
0x180026fc3  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x180026fc8  test    eax, eax
0x180026fca  jz      short loc_180026FF5
0x180026fcc  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.Setup"
0x180026fd3  xor     edx, edx; bInheritHandle
0x180026fd5  mov     ecx, 1F0001h; dwDesiredAccess
0x180026fda  call    cs:__imp_OpenMutexW
0x180026fe0  lea     rcx, [rax+1]
0x180026fe4  cmp     rcx, 1
0x180026fe8  jbe     short loc_180026FF5
0x180026fea  mov     rcx, rax; hObject
0x180026fed  call    cs:__imp_CloseHandle
0x180026ff3  jmp     short loc_180027067
0x180026ff5  mov     [rbp+57h+phkResult], rdi
0x180026ff9  lea     rax, [rbp+57h+hKey]
0x180026ffd  mov     [rbp+57h+var_20], rax
0x180027001  mov     [rbp+57h+hKey], rdi
0x180027005  lea     rax, [rbp+57h+phkResult]
0x180027009  mov     qword ptr [rsp+0A0h+nSubAuthority2], rax; phkResult
0x18002700e  mov     r9d, 20019h; samDesired
0x180027014  xor     r8d, r8d; ulOptions
0x180027017  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x18002701e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027025  call    cs:__imp_RegOpenKeyExW
0x18002702b  mov     ebx, eax
0x18002702d  mov     r8, [rbp+57h+phkResult]
0x180027031  test    r8, r8
0x180027034  jz      short loc_18002704B
0x180027036  mov     rdx, [rbp+57h+var_20]
0x18002703a  mov     rcx, [rdx]; hKey
0x18002703d  mov     [rdx], r8
0x180027040  test    rcx, rcx
0x180027043  jz      short loc_18002704B
0x180027045  call    cs:__imp_RegCloseKey
0x18002704b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002704f  test    rcx, rcx
0x180027052  jz      short loc_18002705A
0x180027054  call    cs:__imp_RegCloseKey
0x18002705a  test    ebx, ebx
0x18002705c  jnz     short loc_180027085
0x18002705e  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x180027063  test    eax, eax
0x180027065  jz      short loc_180027085
0x180027067  mov     [rbp+57h+IsMember], 1
0x18002706e  call    ?UtilIsWindowManagerToken@@YAJPEAX@Z; UtilIsWindowManagerToken(void *)
0x180027073  test    eax, eax
0x180027075  jz      short loc_180027085
0x180027077  call    ?UtilIsVirtualServer@@YA_NXZ; UtilIsVirtualServer(void)
0x18002707c  test    al, al
0x18002707e  jnz     short loc_180027085
0x180027080  mov     ebx, [rbp+57h+IsMember]
0x180027083  jmp     short loc_18002708A
0x180027085  mov     ebx, edi
0x180027087  mov     [rbp+57h+IsMember], ebx
0x18002708a  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18002708e  test    rcx, rcx
0x180027091  jz      short loc_180027099
0x180027093  call    cs:__imp_FreeSid
0x180027099  mov     eax, ebx
0x18002709b  mov     rcx, [rbp+57h+var_8]
0x18002709f  xor     rcx, rsp; StackCookie
0x1800270a2  call    __security_check_cookie
0x1800270a7  lea     r11, [rsp+0A0h+var_s0]
0x1800270af  mov     rbx, [r11+10h]
0x1800270b3  mov     rdi, [r11+18h]
0x1800270b7  mov     rsp, r11
0x1800270ba  pop     rbp
0x1800270bb  retn
```
