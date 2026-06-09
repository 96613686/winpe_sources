# CheckUserAllowedInRole(ushort *,ushort *,int *)

- ea: `0x18001e864`
- end: `0x18001e9f8`
- name: `?CheckUserAllowedInRole@@YAXPEAG0PEAH@Z`
- size: `404`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800090a0`

## callees

- `0x180018a8c`
- `0x180018d48`
- `0x18001e864`
- `0x18002bac4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e971`
- `msvcrt!_wcsicmp` at `0x18001e971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e9be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e9be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e99a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e99a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e8be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e8be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e900`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e900`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e928`

## string_xrefs

- `0x18001e8b0`: `SOFTWARE\Microsoft\COM3`

## pseudocode

```c
void __fastcall CheckUserAllowedInRole(unsigned __int16 *a1, unsigned __int16 *a2, int *a3)
{
  bool v4; // zf
  const wchar_t *RoleName; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+48h] BYREF

  v4 = dword_180072494 == 0;
  *a3 = 0;
  if ( v4 )
    goto LABEL_10;
  dword_180072494 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3", 0, 0x20019u, &hKey) )
  {
    if ( !hKey )
      goto LABEL_10;
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CheckUserAllowedInRole", 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
      dword_180072490 = *(_DWORD *)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_10:
  if ( !dword_180072490 )
    goto LABEL_24;
  RoleName = CPartitionRoleCheck::GetRoleName(1);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( RoleName[v9] );
  do
    ++v8;
  while ( a1[v8] );
  if ( !(_DWORD)v9 || (unsigned int)v8 < (unsigned int)v9 || _wcsicmp(RoleName, &a1[(unsigned int)(v8 - v9)]) )
    goto LABEL_24;
  if ( a2 )
  {
    Type = 0;
    if ( !CCheckGroupMembership::sm_fFirstTime )
      goto LABEL_23;
    v10 = 0;
    EnterCriticalSection(&CCheckGroupMembership::sm_cs);
    if ( CCheckGroupMembership::sm_fFirstTime )
    {
      v10 = CCheckGroupMembership::Initialize();
      CCheckGroupMembership::sm_fFirstTime = 0;
    }
    LeaveCriticalSection(&CCheckGroupMembership::sm_cs);
    if ( !v10 )
    {
LABEL_23:
      if ( !(unsigned int)CCheckGroupMembership::InternalIsInAllowedGroups(a2, (int *)&Type) && Type )
LABEL_24:
        *a3 = 1;
    }
  }
}

```

## disassembly

```asm
0x18001e864  mov     [rsp-28h+arg_0], rbx
0x18001e869  push    rbp
0x18001e86a  push    rsi
0x18001e86b  push    rdi
0x18001e86c  push    r14
0x18001e86e  push    r15
0x18001e870  mov     rbp, rsp
0x18001e873  sub     rsp, 40h
0x18001e877  xor     r15d, r15d
0x18001e87a  mov     rsi, r8
0x18001e87d  cmp     cs:dword_180072494, r15d
0x18001e884  mov     r14, rdx
0x18001e887  mov     rbx, rcx
0x18001e88a  mov     [r8], r15d
0x18001e88d  jz      loc_18001E92E
0x18001e893  lea     rax, [rbp+hKey]
0x18001e897  mov     cs:dword_180072494, r15d
0x18001e89e  mov     r9d, 20019h; samDesired
0x18001e8a4  mov     [rsp+40h+phkResult], rax; phkResult
0x18001e8a9  xor     r8d, r8d; ulOptions
0x18001e8ac  mov     [rbp+hKey], r15
0x18001e8b0  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\COM3"
0x18001e8b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e8be  call    cs:__imp_RegOpenKeyExW
0x18001e8c4  test    eax, eax
0x18001e8c6  jnz     short loc_18001E91F
0x18001e8c8  mov     rcx, [rbp+hKey]; hKey
0x18001e8cc  test    rcx, rcx
0x18001e8cf  jz      short loc_18001E92E
0x18001e8d1  lea     rax, [rbp+cbData]
0x18001e8d5  mov     [rbp+Type], r15d
0x18001e8d9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001e8de  lea     r9, [rbp+Type]; lpType
0x18001e8e2  lea     rax, [rbp+Data]
0x18001e8e6  mov     dword ptr [rbp+Data], r15d
0x18001e8ea  xor     r8d, r8d; lpReserved
0x18001e8ed  mov     [rsp+40h+phkResult], rax; lpData
0x18001e8f2  lea     rdx, aCheckuserallow; "CheckUserAllowedInRole"
0x18001e8f9  mov     [rbp+cbData], 4
0x18001e900  call    cs:__imp_RegQueryValueExW
0x18001e906  test    eax, eax
0x18001e908  jnz     short loc_18001E91F
0x18001e90a  cmp     [rbp+Type], 4
0x18001e90e  jnz     short loc_18001E91F
0x18001e910  cmp     [rbp+cbData], 4
0x18001e914  jnz     short loc_18001E91F
0x18001e916  mov     eax, dword ptr [rbp+Data]
0x18001e919  mov     cs:dword_180072490, eax
0x18001e91f  mov     rcx, [rbp+hKey]; hKey
0x18001e923  test    rcx, rcx
0x18001e926  jz      short loc_18001E92E
0x18001e928  call    cs:__imp_RegCloseKey
0x18001e92e  cmp     cs:dword_180072490, r15d
0x18001e935  jz      loc_18001E9E1
0x18001e93b  mov     ecx, 1; int
0x18001e940  call    ?GetRoleName@CPartitionRoleCheck@@SAPEBGJ@Z; CPartitionRoleCheck::GetRoleName(long)
0x18001e945  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e949  mov     rdx, rcx
0x18001e94c  inc     rdx
0x18001e94f  cmp     [rax+rdx*2], r15w
0x18001e954  jnz     short loc_18001E94C
0x18001e956  inc     rcx
0x18001e959  cmp     [rbx+rcx*2], r15w
0x18001e95e  jnz     short loc_18001E956
0x18001e960  test    edx, edx
0x18001e962  jz      short loc_18001E9E1
0x18001e964  cmp     ecx, edx
0x18001e966  jb      short loc_18001E9E1
0x18001e968  sub     ecx, edx
0x18001e96a  lea     rdx, [rbx+rcx*2]; String2
0x18001e96e  mov     rcx, rax; String1
0x18001e971  call    cs:__imp__wcsicmp
0x18001e977  test    eax, eax
0x18001e979  jnz     short loc_18001E9E1
0x18001e97b  test    r14, r14
0x18001e97e  jz      short loc_18001E9E7
0x18001e980  cmp     cs:?sm_fFirstTime@CCheckGroupMembership@@0HA, r15d; int CCheckGroupMembership::sm_fFirstTime
0x18001e987  mov     edi, r15d
0x18001e98a  mov     [rbp+Type], r15d
0x18001e98e  jz      short loc_18001E9C8
0x18001e990  lea     rcx, ?sm_cs@CCheckGroupMembership@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e997  mov     ebx, r15d
0x18001e99a  call    cs:__imp_EnterCriticalSection
0x18001e9a0  cmp     cs:?sm_fFirstTime@CCheckGroupMembership@@0HA, r15d; int CCheckGroupMembership::sm_fFirstTime
0x18001e9a7  jz      short loc_18001E9B7
0x18001e9a9  call    ?Initialize@CCheckGroupMembership@@CAJXZ; CCheckGroupMembership::Initialize(void)
0x18001e9ae  mov     ebx, eax
0x18001e9b0  mov     cs:?sm_fFirstTime@CCheckGroupMembership@@0HA, r15d; int CCheckGroupMembership::sm_fFirstTime
0x18001e9b7  lea     rcx, ?sm_cs@CCheckGroupMembership@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e9be  call    cs:__imp_LeaveCriticalSection
0x18001e9c4  test    ebx, ebx
0x18001e9c6  jnz     short loc_18001E9E7
0x18001e9c8  lea     rdx, [rbp+Type]; int *
0x18001e9cc  mov     rcx, r14; lpAccountName
0x18001e9cf  call    ?InternalIsInAllowedGroups@CCheckGroupMembership@@CAJPEAGPEAH@Z; CCheckGroupMembership::InternalIsInAllowedGroups(ushort *,int *)
0x18001e9d4  mov     edi, [rbp+Type]
0x18001e9d7  mov     ebx, eax
0x18001e9d9  test    eax, eax
0x18001e9db  jnz     short loc_18001E9E7
0x18001e9dd  test    edi, edi
0x18001e9df  jz      short loc_18001E9E7
0x18001e9e1  mov     dword ptr [rsi], 1
0x18001e9e7  mov     rbx, [rsp+40h+arg_0]
0x18001e9ec  add     rsp, 40h
0x18001e9f0  pop     r15
0x18001e9f2  pop     r14
0x18001e9f4  pop     rdi
0x18001e9f5  pop     rsi
0x18001e9f6  pop     rbp
0x18001e9f7  retn
```
