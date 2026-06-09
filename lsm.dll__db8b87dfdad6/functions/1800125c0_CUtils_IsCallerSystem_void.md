# CUtils::IsCallerSystem(void)

- ea: `0x1800125c0`
- end: `0x180012885`
- name: `?IsCallerSystem@CUtils@@SAJXZ`
- size: `709`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800117c0`
- `0x180012a90`
- `0x1800226a0`
- `0x1800489c0`

## callees

- `0x1800074c0`
- `0x1800125c0`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001266a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001266a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001263a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001263a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012846`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012773`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012855`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012863`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012855`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012863`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180012723`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800127c2`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180012723`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800127c2`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180012674`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x180012674`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800126e9`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800126e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800126ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800126ba`

## string_xrefs

- `0x18001269c`: `IsCallerSystem: IsTokenRestricted failed %x`
- `0x18001265c`: `IsCallerSystem: Could not open thread token %x`
- `0x1800126d5`: `IsCallerSystem: Could not convert security descriptor string %x`
- `0x18001282b`: `IsCallerSystem: Token is restricted %x`
- `0x180012762`: `IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x`
- `0x18001274a`: `IsCallerSystem: Token access check probe failed %x`
- `0x1800127dd`: `IsCallerSystem: Token access check failed %x`
- `0x180012786`: `IsCallerSystem: Failed to allocate privilege set %x`
- `0x18001280c`: `IsCallerSystem: Token missing required right`
- `0x1800127fd`: `IsCallerSystem: Token access denied %x`

## pseudocode

```c
__int64 CUtils::IsCallerSystem(void)
{
  struct _PRIVILEGE_SET *v0; // rsi
  HANDLE CurrentThread; // rax
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-19h] BYREF
  DWORD PrivilegeSetLength; // [rsp+44h] [rbp-15h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-11h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-Dh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-1h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+7h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+17h] BYREF

  TokenHandle = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  v0 = 0;
  SecurityDescriptor = 0;
  GenericMapping = (struct _GENERIC_MAPPING)xmmword_1800B90C8;
  GrantedAccess = 0;
  AccessMask = 0x40000000;
  PrivilegeSetLength = 20;
  CurrentThread = GetCurrentThread();
  AccessStatus = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( AccessStatus )
  {
    SetLastError(0);
    if ( IsTokenRestricted(TokenHandle) )
    {
      v3 = -2147024891;
      _DbgPrintMessage(8, "IsCallerSystem: Token is restricted %x", 2147942405LL);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 )
      {
        _DbgPrintMessage(8, "IsCallerSystem: IsTokenRestricted failed %x", v3);
        goto LABEL_35;
      }
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYG:BAD:(A;;0x1;;;SY)", 1u, &SecurityDescriptor, 0) )
      {
        MapGenericMask(&AccessMask, &GenericMapping);
        if ( AccessCheck(
               SecurityDescriptor,
               TokenHandle,
               AccessMask,
               &GenericMapping,
               &PrivilegeSet,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus) )
        {
          goto LABEL_27;
        }
        v6 = GetLastError();
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        if ( v3 != -2147024774 )
        {
          _DbgPrintMessage(8, "IsCallerSystem: Token access check probe failed %x", v3);
          goto LABEL_35;
        }
        if ( !PrivilegeSetLength )
        {
          v3 = -2147418113;
          _DbgPrintMessage(
            8,
            "IsCallerSystem: AccessCheck probe returned privilege set size of 0 unexpectedly %x",
            2147549183LL);
          goto LABEL_35;
        }
        v0 = (struct _PRIVILEGE_SET *)LocalAlloc(0, PrivilegeSetLength);
        if ( !v0 )
        {
          v3 = -2147024882;
          _DbgPrintMessage(8, "IsCallerSystem: Failed to allocate privilege set %x", 2147942414LL);
          goto LABEL_35;
        }
        if ( AccessCheck(
               SecurityDescriptor,
               TokenHandle,
               AccessMask,
               &GenericMapping,
               v0,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus) )
        {
LABEL_27:
          if ( AccessStatus )
          {
            if ( (GrantedAccess & 1) != 0 )
            {
              v3 = 0;
            }
            else
            {
              v3 = 1;
              _DbgPrintMessage(8, "IsCallerSystem: Token missing required right");
            }
          }
          else
          {
            v8 = GetLastError();
            v3 = v8;
            if ( v8 > 0 )
              v3 = (unsigned __int16)v8 | 0x80070000;
            _DbgPrintMessage(8, "IsCallerSystem: Token access denied %x", v3);
          }
        }
        else
        {
          v7 = GetLastError();
          v3 = v7;
          if ( v7 > 0 )
            v3 = (unsigned __int16)v7 | 0x80070000;
          _DbgPrintMessage(8, "IsCallerSystem: Token access check failed %x", v3);
        }
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
        _DbgPrintMessage(8, "IsCallerSystem: Could not convert security descriptor string %x", v3);
      }
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    _DbgPrintMessage(8, "IsCallerSystem: Could not open thread token %x", v3);
  }
LABEL_35:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v0 )
    LocalFree(v0);
  return v3;
}

```

## disassembly

```asm
0x1800125c0  push    rbp
0x1800125c2  push    rbx
0x1800125c3  push    rsi
0x1800125c4  push    rdi
0x1800125c5  push    r15
0x1800125c7  lea     rbp, [rsp-37h]
0x1800125cc  sub     rsp, 90h
0x1800125d3  mov     rax, cs:__security_cookie
0x1800125da  xor     rax, rsp
0x1800125dd  mov     [rbp+57h+var_28], rax
0x1800125e1  xorps   xmm0, xmm0
0x1800125e4  mov     [rbp+57h+TokenHandle], 0
0x1800125ec  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x1800125f0  xor     eax, eax
0x1800125f2  xor     esi, esi
0x1800125f4  movups  xmm0, cs:xmmword_1800B90C8
0x1800125fb  mov     [rbp+57h+var_70], 0
0x180012602  mov     [rbp+57h+SecurityDescriptor], 0
0x18001260a  movdqu  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18001260f  mov     [rbp+57h+var_64], esi
0x180012612  mov     [rbp+57h+AccessMask], 40000000h
0x180012619  mov     [rbp+57h+var_40.Privilege.Attributes], eax
0x18001261c  mov     [rbp+57h+var_6C], 14h
0x180012623  call    cs:__imp_GetCurrentThread
0x180012629  lea     r15d, [rsi+8]
0x18001262d  xor     r8d, r8d; OpenAsSelf
0x180012630  mov     rcx, rax; ThreadHandle
0x180012633  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180012637  mov     edx, r15d; DesiredAccess
0x18001263a  call    cs:__imp_OpenThreadToken
0x180012640  mov     [rbp+57h+var_70], eax
0x180012643  test    eax, eax
0x180012645  jnz     short loc_180012668
0x180012647  call    cs:__imp_GetLastError
0x18001264d  mov     ebx, eax
0x18001264f  test    eax, eax
0x180012651  jle     short loc_18001265C
0x180012653  movzx   ebx, ax
0x180012656  or      ebx, 80070000h
0x18001265c  lea     rdx, aIscallersystem_1; "IsCallerSystem: Could not open thread t"...
0x180012663  jmp     loc_180012832
0x180012668  xor     ecx, ecx; dwErrCode
0x18001266a  call    cs:__imp_SetLastError
0x180012670  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180012674  call    cs:__imp_IsTokenRestricted
0x18001267a  test    eax, eax
0x18001267c  jnz     loc_180012826
0x180012682  call    cs:__imp_GetLastError
0x180012688  mov     ebx, eax
0x18001268a  mov     edi, 80070000h
0x18001268f  test    eax, eax
0x180012691  jle     short loc_180012698
0x180012693  movzx   ebx, ax
0x180012696  or      ebx, edi
0x180012698  test    ebx, ebx
0x18001269a  jz      short loc_1800126A8
0x18001269c  lea     rdx, aIscallersystem_6; "IsCallerSystem: IsTokenRestricted faile"...
0x1800126a3  jmp     loc_180012832
0x1800126a8  xor     r9d, r9d; SecurityDescriptorSize
0x1800126ab  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800126af  lea     rcx, StringSecurityDescriptor; "O:SYG:BAD:(A;;0x1;;;SY)"
0x1800126b6  lea     edx, [r9+1]; StringSDRevision
0x1800126ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800126c0  test    eax, eax
0x1800126c2  jnz     short loc_1800126E1
0x1800126c4  call    cs:__imp_GetLastError
0x1800126ca  mov     ebx, eax
0x1800126cc  test    eax, eax
0x1800126ce  jle     short loc_1800126D5
0x1800126d0  movzx   ebx, ax
0x1800126d3  or      ebx, edi
0x1800126d5  lea     rdx, aIscallersystem_3; "IsCallerSystem: Could not convert secur"...
0x1800126dc  jmp     loc_180012832
0x1800126e1  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1800126e5  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800126e9  call    cs:__imp_MapGenericMask
0x1800126ef  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x1800126f3  lea     rax, [rbp+57h+var_70]
0x1800126f7  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800126fb  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800126ff  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180012703  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x180012708  lea     rax, [rbp+57h+var_64]
0x18001270c  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180012711  lea     rax, [rbp+57h+var_6C]
0x180012715  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001271a  lea     rax, [rbp+57h+var_40]
0x18001271e  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x180012723  call    cs:__imp_AccessCheck
0x180012729  test    eax, eax
0x18001272b  jnz     loc_1800127E6
0x180012731  call    cs:__imp_GetLastError
0x180012737  mov     ebx, eax
0x180012739  test    eax, eax
0x18001273b  jle     short loc_180012742
0x18001273d  movzx   ebx, ax
0x180012740  or      ebx, edi
0x180012742  cmp     ebx, 8007007Ah
0x180012748  jz      short loc_180012756
0x18001274a  lea     rdx, aIscallersystem_2; "IsCallerSystem: Token access check prob"...
0x180012751  jmp     loc_180012832
0x180012756  mov     eax, [rbp+57h+var_6C]
0x180012759  test    eax, eax
0x18001275b  jnz     short loc_18001276E
0x18001275d  mov     ebx, 8000FFFFh
0x180012762  lea     rdx, aIscallersystem_8; "IsCallerSystem: AccessCheck probe retur"...
0x180012769  jmp     loc_180012832
0x18001276e  mov     rdx, rax; uBytes
0x180012771  xor     ecx, ecx; uFlags
0x180012773  call    cs:__imp_LocalAlloc
0x180012779  mov     rsi, rax
0x18001277c  test    rax, rax
0x18001277f  jnz     short loc_180012792
0x180012781  mov     ebx, 8007000Eh
0x180012786  lea     rdx, aIscallersystem_7; "IsCallerSystem: Failed to allocate priv"...
0x18001278d  jmp     loc_180012832
0x180012792  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x180012796  lea     rax, [rbp+57h+var_70]
0x18001279a  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18001279e  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800127a2  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800127a6  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800127ab  lea     rax, [rbp+57h+var_64]
0x1800127af  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x1800127b4  lea     rax, [rbp+57h+var_6C]
0x1800127b8  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800127bd  mov     [rsp+0B0h+PrivilegeSet], rsi; PrivilegeSet
0x1800127c2  call    cs:__imp_AccessCheck
0x1800127c8  test    eax, eax
0x1800127ca  jnz     short loc_1800127E6
0x1800127cc  call    cs:__imp_GetLastError
0x1800127d2  mov     ebx, eax
0x1800127d4  test    eax, eax
0x1800127d6  jle     short loc_1800127DD
0x1800127d8  movzx   ebx, ax
0x1800127db  or      ebx, edi
0x1800127dd  lea     rdx, aIscallersystem_5; "IsCallerSystem: Token access check fail"...
0x1800127e4  jmp     short loc_180012832
0x1800127e6  cmp     [rbp+57h+var_70], 0
0x1800127ea  jnz     short loc_180012806
0x1800127ec  call    cs:__imp_GetLastError
0x1800127f2  mov     ebx, eax
0x1800127f4  test    eax, eax
0x1800127f6  jle     short loc_1800127FD
0x1800127f8  movzx   ebx, ax
0x1800127fb  or      ebx, edi
0x1800127fd  lea     rdx, aIscallersystem_0; "IsCallerSystem: Token access denied %x"
0x180012804  jmp     short loc_180012832
0x180012806  test    byte ptr [rbp+57h+var_64], 1
0x18001280a  jnz     short loc_180012822
0x18001280c  lea     rdx, aIscallersystem_4; "IsCallerSystem: Token missing required "...
0x180012813  mov     ecx, r15d; int
0x180012816  mov     ebx, 1
0x18001281b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012820  jmp     short loc_18001283D
0x180012822  xor     ebx, ebx
0x180012824  jmp     short loc_18001283D
0x180012826  mov     ebx, 80070005h
0x18001282b  lea     rdx, aIscallersystem; "IsCallerSystem: Token is restricted %x"
0x180012832  mov     r8d, ebx
0x180012835  mov     ecx, r15d; int
0x180012838  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001283d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180012841  test    rcx, rcx
0x180012844  jz      short loc_18001284C
0x180012846  call    cs:__imp_CloseHandle
0x18001284c  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180012850  test    rcx, rcx
0x180012853  jz      short loc_18001285B
0x180012855  call    cs:__imp_LocalFree
0x18001285b  test    rsi, rsi
0x18001285e  jz      short loc_180012869
0x180012860  mov     rcx, rsi; hMem
0x180012863  call    cs:__imp_LocalFree
0x180012869  mov     eax, ebx
0x18001286b  mov     rcx, [rbp+57h+var_28]
0x18001286f  xor     rcx, rsp; StackCookie
0x180012872  call    __security_check_cookie
0x180012877  add     rsp, 90h
0x18001287e  pop     r15
0x180012880  pop     rdi
0x180012881  pop     rsi
0x180012882  pop     rbx
0x180012883  pop     rbp
0x180012884  retn
```
