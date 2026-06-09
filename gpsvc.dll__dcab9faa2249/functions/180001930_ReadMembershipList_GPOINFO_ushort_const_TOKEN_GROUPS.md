# ReadMembershipList(_GPOINFO *,ushort const *,_TOKEN_GROUPS *)

- ea: `0x180001930`
- end: `0x180001f1f`
- name: `?ReadMembershipList@@YAHPEAU_GPOINFO@@PEBGPEAU_TOKEN_GROUPS@@@Z`
- size: `1519`
- prototype: `__int64 __fastcall(struct _GPOINFO *, const unsigned __int16 *, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800014e0`

## callees

- `0x180001930`
- `0x180003770`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000198e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000198e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c34`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001bc4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001bc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001b1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180001af6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180001af6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001a60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001a60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001b93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001b93`
- `ntdll!RtlEqualSid` at `0x180001bff`
- `ntdll!RtlEqualSid` at `0x180001bff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180001bd7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180001bd7`

## string_xrefs

- `0x180001d3b`: `ReadMembershipList: Failed to read old group count`
- `0x180001d6d`: `ReadMembershipList: Failed to read old group count`
- `0x180001d9f`: `ReadMembershipList: Old count %d is different from current count %d`
- `0x180001dd4`: `ReadMembershipList: Old count %d is different from current count %d`
- `0x180001df9`: `ReadMembershipList: Failed to query max size with %d.`
- `0x180001e2f`: `ReadMembershipList: Failed to query max size with %d.`
- `0x180001cf8`: `ReadMembershipList: Failed to allocate memory with %d.`
- `0x180001e62`: `ReadMembershipList: Failed to allocate memory with %d.`
- `0x180001eca`: `ReadMembershipList: Failed to read value %ws`
- `0x180001f00`: `ReadMembershipList: Failed to read value %ws`
- `0x180001c5e`: `ReadMembershipList: Group %ws not in current list of token groups`
- `0x180001e97`: `ReadMembershipList: Group %ws not in current list of token groups`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadMembershipList(struct _GPOINFO *a1, const unsigned __int16 *a2, struct _TOKEN_GROUPS *a3)
{
  unsigned int v6; // r13d
  unsigned int v7; // edi
  DWORD LastError; // ebx
  DWORD i; // ecx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  WCHAR *v14; // r9
  int v15; // r10d
  unsigned __int16 v16; // ax
  __int64 v17; // rcx
  DWORD v18; // edi
  unsigned int v19; // eax
  DWORD v20; // ecx
  BYTE *v21; // r12
  unsigned int j; // r15d
  int v23; // eax
  int v24; // r14d
  BOOLEAN v25; // al
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE Data[4]; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  DWORD v33; // [rsp+80h] [rbp-80h]
  WCHAR ValueName[36]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SubKey[256]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  v6 = 1;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  cbMaxValueLen = 0;
  v7 = 0;
  LastError = GetLastError();
  v33 = LastError;
  for ( i = 0; i < a3->GroupCount; ++i )
  {
    v10 = v7 + 1;
    if ( (a3->Groups[i].Attributes & 0xC0000000) != 0 )
      v10 = v7;
    v7 = v10;
  }
  v11 = 250;
  if ( a2 )
  {
    v15 = StringCchPrintfW(
            SubKey,
            0xFAu,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws\\GroupMembership",
            a2);
  }
  else
  {
    v12 = 2147483646;
    v13 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\GroupMembership";
    v14 = SubKey;
    v15 = 0;
    while ( v12 )
    {
      v16 = *v13;
      if ( !*v13 )
        break;
      ++v13;
      *v14++ = v16;
      --v12;
      if ( !--v11 )
      {
        --v14;
        v15 = -2147024774;
        break;
      }
    }
    *v14 = 0;
  }
  if ( v15 < 0 )
  {
    LastError = (unsigned __int16)v15;
LABEL_39:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_41;
  }
  v17 = -2147483646;
  if ( !a2 )
    v17 = *((_QWORD *)a1 + 5);
  if ( !RegOpenKeyExW((HKEY)v17, SubKey, 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Count", 0, &Type, Data, &cbData) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"ReadMembershipList: Failed to read old group count");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"ReadMembershipList: Failed to read old group count");
        }
      }
    }
    else if ( *(_DWORD *)Data == v7 )
    {
      v18 = 0;
      v19 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
      if ( v19 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"ReadMembershipList: Failed to query max size with %d.", v19);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"ReadMembershipList: Failed to query max size with %d.", v19);
          }
        }
      }
      else
      {
        v20 = cbMaxValueLen + 2;
        if ( cbMaxValueLen + 2 < cbMaxValueLen )
        {
          cbMaxValueLen = -1;
          LastError = 534;
        }
        else
        {
          cbMaxValueLen += 2;
          v21 = (BYTE *)LocalAlloc(0x40u, v20);
          if ( v21 )
          {
            for ( j = 0; ; ++j )
            {
              if ( j >= *(_DWORD *)Data )
              {
                v6 = 0;
                goto LABEL_44;
              }
              v23 = StringCchPrintfW(ValueName, 0x1Eu, L"Group%d", j);
              if ( v23 < 0 )
              {
                LastError = (unsigned __int16)v23;
                goto LABEL_44;
              }
              cbData = cbMaxValueLen;
              if ( RegQueryValueExW(hKey, ValueName, 0, &Type, v21, &cbData) )
                break;
              Sid = 0;
              if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)v21, -1, L"s-1-1-0", -1) != 2 )
              {
                if ( !ConvertStringSidToSidW((LPCWSTR)v21, &Sid) && GetLastError() )
                  goto LABEL_35;
                v24 = 0;
                if ( a3->GroupCount )
                {
                  do
                  {
                    v25 = RtlEqualSid(Sid, a3->Groups[v18].Sid);
                    v24 = v25;
                    if ( v25 )
                      break;
                    ++v18;
                  }
                  while ( v18 < a3->GroupCount );
                }
                LocalFree(Sid);
                if ( !v24 )
                {
LABEL_35:
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(2u, L"ReadMembershipList: Group %ws not in current list of token groups", v21);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(2u, L"ReadMembershipList: Group %ws not in current list of token groups", v21);
                    }
                  }
                  goto LABEL_44;
                }
                v18 = 0;
              }
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"ReadMembershipList: Failed to read value %ws", ValueName);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"ReadMembershipList: Failed to read value %ws", ValueName);
              }
            }
LABEL_44:
            LocalFree(v21);
          }
          else if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"ReadMembershipList: Failed to allocate memory with %d.", 0);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"ReadMembershipList: Failed to allocate memory with %d.", 0);
            }
          }
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          4u,
          L"ReadMembershipList: Old count %d is different from current count %d",
          *(unsigned int *)Data,
          v7);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"ReadMembershipList: Old count %d is different from current count %d",
          *(unsigned int *)Data,
          v7);
      }
    }
    goto LABEL_39;
  }
LABEL_41:
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x180001930  mov     [rsp-8+arg_18], rbx
0x180001935  push    rbp
0x180001936  push    rsi
0x180001937  push    rdi
0x180001938  push    r12
0x18000193a  push    r13
0x18000193c  push    r14
0x18000193e  push    r15
0x180001940  lea     rbp, [rsp-1E0h]
0x180001948  sub     rsp, 2E0h
0x18000194f  mov     rax, cs:__security_cookie
0x180001956  xor     rax, rsp
0x180001959  mov     [rbp+210h+var_40], rax
0x180001960  mov     rsi, r8
0x180001963  mov     r14, rdx
0x180001966  mov     r15, rcx
0x180001969  xor     r12d, r12d
0x18000196c  mov     [rsp+310h+hKey], r12
0x180001971  mov     r13d, 1
0x180001977  mov     dword ptr [rsp+310h+Data], r12d
0x18000197c  mov     [rsp+310h+cbData], r12d
0x180001981  mov     [rsp+310h+Type], r12d
0x180001986  mov     [rsp+310h+cbMaxValueLen], r12d
0x18000198b  mov     edi, r12d
0x18000198e  call    cs:__imp_GetLastError
0x180001994  mov     ebx, eax
0x180001996  mov     [rbp+210h+var_290], eax
0x180001999  mov     edx, [rsi]
0x18000199b  mov     ecx, r12d
0x18000199e  test    edx, edx
0x1800019a0  jz      short loc_1800019BF
0x1800019a2  mov     eax, ecx
0x1800019a4  inc     rax
0x1800019a7  add     rax, rax
0x1800019aa  test    dword ptr [rsi+rax*8], 0C0000000h
0x1800019b1  lea     eax, [rdi+1]
0x1800019b4  cmovnz  eax, edi
0x1800019b7  mov     edi, eax
0x1800019b9  inc     ecx
0x1800019bb  cmp     ecx, edx
0x1800019bd  jb      short loc_1800019A2
0x1800019bf  mov     edx, 0FAh; unsigned __int64
0x1800019c4  test    r14, r14
0x1800019c7  jnz     short loc_180001A0F
0x1800019c9  mov     ecx, 7FFFFFFEh
0x1800019ce  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800019d5  lea     r9, [rbp+210h+SubKey]
0x1800019d9  mov     r10d, r12d
0x1800019dc  nop     dword ptr [rax+00h]
0x1800019e0  test    rcx, rcx
0x1800019e3  jz      short loc_180001A2C
0x1800019e5  movzx   eax, word ptr [r8]
0x1800019e9  test    ax, ax
0x1800019ec  jz      short loc_180001A27
0x1800019ee  add     r8, 2
0x1800019f2  mov     [r9], ax
0x1800019f6  add     r9, 2
0x1800019fa  dec     rcx
0x1800019fd  sub     rdx, 1
0x180001a01  jnz     short loc_1800019E0
0x180001a03  sub     r9, 2
0x180001a07  mov     r10d, 8007007Ah
0x180001a0d  jmp     short loc_180001A2C
0x180001a0f  mov     r9, r14
0x180001a12  lea     r8, aSoftwareMicros_33; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001a19  lea     rcx, [rbp+210h+SubKey]; unsigned __int16 *
0x180001a1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001a22  mov     r10d, eax
0x180001a25  jmp     short loc_180001A30
0x180001a27  test    rdx, rdx
0x180001a2a  jz      short loc_180001A03
0x180001a2c  mov     [r9], r12w
0x180001a30  test    r10d, r10d
0x180001a33  js      loc_180001D19
0x180001a39  test    r14, r14
0x180001a3c  mov     rcx, 0FFFFFFFF80000002h
0x180001a43  jnz     short loc_180001A49
0x180001a45  mov     rcx, [r15+28h]; hKey
0x180001a49  lea     rax, [rsp+310h+hKey]
0x180001a4e  mov     [rsp+310h+phkResult], rax; phkResult
0x180001a53  mov     r9d, 20019h; samDesired
0x180001a59  xor     r8d, r8d; ulOptions
0x180001a5c  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x180001a60  call    cs:__imp_RegOpenKeyExW
0x180001a66  test    eax, eax
0x180001a68  jnz     loc_180001C8B
0x180001a6e  mov     [rsp+310h+cbData], 4
0x180001a76  lea     rax, [rsp+310h+cbData]
0x180001a7b  mov     [rsp+310h+lpcbData], rax; lpcbData
0x180001a80  lea     rax, [rsp+310h+Data]
0x180001a85  mov     [rsp+310h+phkResult], rax; lpData
0x180001a8a  lea     r9, [rsp+310h+Type]; lpType
0x180001a8f  xor     r8d, r8d; lpReserved
0x180001a92  lea     rdx, ValueName; "Count"
0x180001a99  mov     rcx, [rsp+310h+hKey]; hKey
0x180001a9e  call    cs:__imp_RegQueryValueExW
0x180001aa4  test    eax, eax
0x180001aa6  jnz     loc_180001D22
0x180001aac  mov     r8d, dword ptr [rsp+310h+Data]
0x180001ab1  cmp     r8d, edi
0x180001ab4  jnz     loc_180001D83
0x180001aba  xor     edi, edi
0x180001abc  mov     [rsp+310h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180001ac1  mov     [rsp+310h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180001ac6  lea     rax, [rsp+310h+cbMaxValueLen]
0x180001acb  mov     [rsp+310h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180001ad0  mov     [rsp+310h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180001ad5  mov     [rsp+310h+lpcValues], rdi; lpcValues
0x180001ada  mov     [rsp+310h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180001adf  mov     [rsp+310h+lpcbData], rdi; lpcbMaxSubKeyLen
0x180001ae4  mov     [rsp+310h+phkResult], rdi; lpcSubKeys
0x180001ae9  xor     r9d, r9d; lpReserved
0x180001aec  xor     r8d, r8d; lpcchClass
0x180001aef  xor     edx, edx; lpClass
0x180001af1  mov     rcx, [rsp+310h+hKey]; hKey
0x180001af6  call    cs:__imp_RegQueryInfoKeyW
0x180001afc  test    eax, eax
0x180001afe  jnz     loc_180001C71
0x180001b04  mov     eax, [rsp+310h+cbMaxValueLen]
0x180001b08  lea     ecx, [rax+2]
0x180001b0b  cmp     ecx, eax
0x180001b0d  jb      loc_180001CC0
0x180001b13  mov     [rsp+310h+cbMaxValueLen], ecx
0x180001b17  mov     edx, ecx; uBytes
0x180001b19  mov     ecx, 40h ; '@'; uFlags
0x180001b1e  call    cs:__imp_LocalAlloc
0x180001b24  mov     r12, rax
0x180001b27  test    rax, rax
0x180001b2a  jz      loc_180001CDD
0x180001b30  mov     r15d, edi
0x180001b33  lea     r14, String2; "s-1-1-0"
0x180001b3a  nop     word ptr [rax+rax+00h]
0x180001b40  cmp     r15d, dword ptr [rsp+310h+Data]
0x180001b45  jnb     loc_180001CCF
0x180001b4b  mov     r9d, r15d
0x180001b4e  lea     r8, aGroupD; "Group%d"
0x180001b55  mov     edx, 1Eh; unsigned __int64
0x180001b5a  lea     rcx, [rbp+210h+ValueName]; unsigned __int16 *
0x180001b5e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001b63  test    eax, eax
0x180001b65  js      loc_180001F16
0x180001b6b  mov     eax, [rsp+310h+cbMaxValueLen]
0x180001b6f  mov     [rsp+310h+cbData], eax
0x180001b73  lea     rax, [rsp+310h+cbData]
0x180001b78  mov     [rsp+310h+lpcbData], rax; lpcbData
0x180001b7d  mov     [rsp+310h+phkResult], r12; lpData
0x180001b82  lea     r9, [rsp+310h+Type]; lpType
0x180001b87  xor     r8d, r8d; lpReserved
0x180001b8a  lea     rdx, [rbp+210h+ValueName]; lpValueName
0x180001b8e  mov     rcx, [rsp+310h+hKey]; hKey
0x180001b93  call    cs:__imp_RegQueryValueExW
0x180001b99  test    eax, eax
0x180001b9b  jnz     loc_180001EAD
0x180001ba1  mov     [rsp+310h+Sid], rdi
0x180001ba6  mov     dword ptr [rsp+310h+lpcbData], 0FFFFFFFFh; cchCount2
0x180001bae  mov     [rsp+310h+phkResult], r14; lpString2
0x180001bb3  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001bb9  mov     r8, r12; lpString1
0x180001bbc  mov     edx, r13d; dwCmpFlags
0x180001bbf  mov     ecx, 7Fh; Locale
0x180001bc4  call    cs:__imp_CompareStringW
0x180001bca  cmp     eax, 2
0x180001bcd  jz      short loc_180001C2C
0x180001bcf  lea     rdx, [rsp+310h+Sid]; Sid
0x180001bd4  mov     rcx, r12; StringSid
0x180001bd7  call    cs:__imp_ConvertStringSidToSidW
0x180001bdd  test    eax, eax
0x180001bdf  jz      short loc_180001C34
0x180001be1  mov     r14d, edi
0x180001be4  cmp     dword ptr [rsi], 0
0x180001be7  jbe     short loc_180001C13
0x180001be9  nop     dword ptr [rax+00000000h]
0x180001bf0  mov     edx, edi
0x180001bf2  add     rdx, rdx
0x180001bf5  mov     rdx, [rsi+rdx*8+8]; Sid2
0x180001bfa  mov     rcx, [rsp+310h+Sid]; Sid1
0x180001bff  call    cs:__imp_RtlEqualSid
0x180001c05  movzx   r14d, al
0x180001c09  test    al, al
0x180001c0b  jnz     short loc_180001C13
0x180001c0d  inc     edi
0x180001c0f  cmp     edi, [rsi]
0x180001c11  jb      short loc_180001BF0
0x180001c13  mov     rcx, [rsp+310h+Sid]; hMem
0x180001c18  call    cs:__imp_LocalFree
0x180001c1e  test    r14d, r14d
0x180001c21  jz      short loc_180001C3E
0x180001c23  xor     edi, edi
0x180001c25  lea     r14, String2; "s-1-1-0"
0x180001c2c  inc     r15d
0x180001c2f  jmp     loc_180001B40
0x180001c34  call    cs:__imp_GetLastError
0x180001c3a  test    eax, eax
0x180001c3c  jz      short loc_180001BE1
0x180001c3e  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180001c45  jz      loc_180001CD2
0x180001c4b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180001c52  test    rax, rax
0x180001c55  jz      loc_180001E78
0x180001c5b  mov     r8, r12
0x180001c5e  lea     rdx, aReadmembership; "ReadMembershipList: Group %ws not in cu"...
0x180001c65  mov     ecx, 2
0x180001c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6f  jmp     short loc_180001CD2
0x180001c71  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x180001c77  jnz     loc_180001DEA
0x180001c7d  mov     rcx, [rsp+310h+hKey]; hKey
0x180001c82  test    rcx, rcx
0x180001c85  jnz     loc_180001D0E
0x180001c8b  mov     ecx, ebx; dwErrCode
0x180001c8d  call    cs:__imp_SetLastError
0x180001c93  mov     eax, r13d
0x180001c96  mov     rcx, [rbp+210h+var_40]
0x180001c9d  xor     rcx, rsp; StackCookie
0x180001ca0  call    __security_check_cookie
0x180001ca5  mov     rbx, [rsp+310h+arg_18]
0x180001cad  add     rsp, 2E0h
0x180001cb4  pop     r15
0x180001cb6  pop     r14
0x180001cb8  pop     r13
0x180001cba  pop     r12
0x180001cbc  pop     rdi
0x180001cbd  pop     rsi
0x180001cbe  pop     rbp
0x180001cbf  retn
0x180001cc0  mov     [rsp+310h+cbMaxValueLen], 0FFFFFFFFh
0x180001cc8  mov     ebx, 216h
0x180001ccd  jmp     short loc_180001C7D
0x180001ccf  mov     r13d, edi
0x180001cd2  mov     rcx, r12; hMem
0x180001cd5  call    cs:__imp_LocalFree
0x180001cdb  jmp     short loc_180001C7D
0x180001cdd  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x180001ce3  jz      short loc_180001C7D
0x180001ce5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180001cec  test    rax, rax
0x180001cef  jz      loc_180001E45
0x180001cf5  xor     r8d, r8d
0x180001cf8  lea     rdx, aReadmembership_3; "ReadMembershipList: Failed to allocate "...
0x180001cff  mov     ecx, 2
0x180001d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d09  jmp     loc_180001C7D
0x180001d0e  call    cs:__imp_RegCloseKey
0x180001d14  jmp     loc_180001C8B
0x180001d19  movzx   ebx, r10w
0x180001d1d  jmp     loc_180001C7D
0x180001d22  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180001d29  jz      loc_180001C7D
0x180001d2f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180001d36  test    rax, rax
0x180001d39  jz      short loc_180001D51
0x180001d3b  lea     rdx, aReadmembership_1; "ReadMembershipList: Failed to read old "...
0x180001d42  mov     ecx, 4
0x180001d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d4c  jmp     loc_180001C7D
0x180001d51  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180001d59  jz      loc_180001C7D
0x180001d5f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180001d67  jz      loc_180001C7D
0x180001d6d  lea     rdx, aReadmembership_1; "ReadMembershipList: Failed to read old "...
0x180001d74  mov     ecx, 4; unsigned int
0x180001d79  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180001d7e  jmp     loc_180001C7D
0x180001d83  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180001d8a  jz      loc_180001C7D
0x180001d90  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180001d97  test    rax, rax
0x180001d9a  jz      short loc_180001DB5
0x180001d9c  mov     r9d, edi
0x180001d9f  lea     rdx, aReadmembership_4; "ReadMembershipList: Old count %d is dif"...
0x180001da6  mov     ecx, 4
0x180001dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001db0  jmp     loc_180001C7D
0x180001db5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180001dbd  jz      loc_180001C7D
0x180001dc3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180001dcb  jz      loc_180001C7D
0x180001dd1  mov     r9d, edi
0x180001dd4  lea     rdx, aReadmembership_4; "ReadMembershipList: Old count %d is dif"...
0x180001ddb  mov     ecx, 4; unsigned int
0x180001de0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180001de5  jmp     loc_180001C7D
0x180001dea  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180001df1  test    r9, r9
0x180001df4  jz      short loc_180001E12
0x180001df6  mov     r8d, eax
0x180001df9  lea     rdx, aReadmembership_0; "ReadMembershipList: Failed to query max"...
0x180001e00  mov     ecx, 2
0x180001e05  mov     rax, r9
0x180001e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e0d  jmp     loc_180001C7D
0x180001e12  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdi; void * g_lpDebugMsgContextInstance
0x180001e19  jz      loc_180001C7D
0x180001e1f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180001e26  jz      loc_180001C7D
0x180001e2c  mov     r8d, eax
0x180001e2f  lea     rdx, aReadmembership_0; "ReadMembershipList: Failed to query max"...
0x180001e36  mov     ecx, 2; unsigned int
0x180001e3b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180001e40  jmp     loc_180001C7D
  ... truncated ...
```
