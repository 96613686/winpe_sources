# UpdateRunLogonScriptSyncCache(void *)

- ea: `0x180004d94`
- end: `0x180004fec`
- name: `?UpdateRunLogonScriptSyncCache@@YAXPEAX@Z`
- size: `600`
- prototype: `void __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800179fc`

## callees

- `0x180004170`
- `0x180004d94`
- `0x180004ff4`
- `0x180005024`
- `0x180006580`
- `0x18000f1b0`
- `0x180036a6c`
- `0x18003e8fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004dc5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004dc5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004db4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004db4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f00`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004e43`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004e43`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004e0c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004e0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004df5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004f91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004df5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004f91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004e8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004e8c`

## pseudocode

```c
void __fastcall UpdateRunLogonScriptSyncCache(HANDLE TokenHandle)
{
  HANDLE ProcessHeap; // rax
  LPWSTR v3; // rdi
  void *v4; // r14
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v7; // rax
  void *v8; // rax
  void *v9; // rsi
  HANDLE v10; // rax
  WCHAR *v11; // rdi
  int v12; // ebx
  HANDLE v13; // rax
  BOOL IsRunLogonScriptSync; // esi
  int ProfileListKeyNameFromSid; // eax
  HKEY v16; // rcx
  void *v17; // rbx
  HANDLE v18; // rax
  int v19; // eax
  BOOL TokenInformation; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+30h] BYREF

  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v3 = StringSid;
  if ( !StringSid )
  {
    v12 = -2147024882;
    v11 = 0;
LABEL_20:
    if ( v12 >= 0 )
    {
      lpMem = 0;
      IsRunLogonScriptSync = _IsRunLogonScriptSync(v11);
      ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(v11, (unsigned __int16 **)&lpMem, 0);
      v17 = lpMem;
      if ( ProfileListKeyNameFromSid >= 0 )
        SHRegSetBOOL(v16, (const unsigned __int16 *)lpMem, L"RunLogonScriptSync", IsRunLogonScriptSync);
      if ( v17 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v17);
      }
    }
    goto LABEL_25;
  }
  v4 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v19 = ResultFromHeapReAlloc(v3, TokenInformationLength, (void **)&StringSid);
      v3 = StringSid;
      Error = v19;
      if ( v19 < 0 )
        goto LABEL_9;
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           StringSid,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v3);
    TokenInformationLength = LengthSid;
    v7 = GetProcessHeap();
    v8 = HeapAlloc(v7, 8u, LengthSid);
    v9 = v8;
    if ( v8 )
    {
      if ( CopySid(TokenInformationLength, v8, *(PSID *)v3) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          ResultFromHeapFree(v9);
          goto LABEL_9;
        }
      }
      v4 = v9;
    }
    else
    {
      Error = -2147024882;
    }
  }
LABEL_9:
  if ( v3 )
  {
    v10 = GetProcessHeap();
    if ( !HeapFree(v10, 0, v3) )
      ResultFromKnownLastError();
  }
  v11 = 0;
  if ( Error >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(v4, &StringSid) )
    {
      v12 = 0;
    }
    else
    {
      v12 = ResultFromKnownLastError();
      if ( v12 < 0 )
      {
LABEL_17:
        if ( v4 )
        {
          v13 = GetProcessHeap();
          if ( !HeapFree(v13, 0, v4) )
            ResultFromKnownLastError();
        }
        goto LABEL_20;
      }
    }
    v11 = StringSid;
    goto LABEL_17;
  }
LABEL_25:
  if ( v11 )
    LocalFree(v11);
}

```

## disassembly

```asm
0x180004d94  mov     [rsp-18h+arg_0], rbx
0x180004d99  mov     [rsp-18h+arg_18], rsi
0x180004d9e  push    rbp
0x180004d9f  push    rdi
0x180004da0  push    r14
0x180004da2  mov     rbp, rsp
0x180004da5  sub     rsp, 50h
0x180004da9  mov     ebx, 0C8h
0x180004dae  mov     rsi, rcx
0x180004db1  mov     [rbp+TokenInformationLength], ebx
0x180004db4  call    cs:__imp_GetProcessHeap
0x180004dba  mov     r8d, ebx; dwBytes
0x180004dbd  mov     edx, 8; dwFlags
0x180004dc2  mov     rcx, rax; hHeap
0x180004dc5  call    cs:__imp_HeapAlloc
0x180004dcb  mov     [rbp+StringSid], rax
0x180004dcf  mov     rdi, rax
0x180004dd2  test    rax, rax
0x180004dd5  jz      loc_180004F37
0x180004ddb  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180004ddf  lea     rax, [rbp+TokenInformationLength]
0x180004de3  xor     r14d, r14d
0x180004de6  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180004deb  mov     r8, rdi; TokenInformation
0x180004dee  mov     rcx, rsi; TokenHandle
0x180004df1  lea     edx, [r14+1]; TokenInformationClass
0x180004df5  call    cs:__imp_GetTokenInformation
0x180004dfb  test    eax, eax
0x180004dfd  jz      loc_180004F4A
0x180004e03  xor     ebx, ebx
0x180004e05  test    ebx, ebx
0x180004e07  js      short loc_180004E56
0x180004e09  mov     rcx, [rdi]; pSid
0x180004e0c  call    cs:__imp_GetLengthSid
0x180004e12  mov     ebx, eax
0x180004e14  mov     [rbp+TokenInformationLength], ebx
0x180004e17  call    cs:__imp_GetProcessHeap
0x180004e1d  mov     r8d, ebx; dwBytes
0x180004e20  mov     edx, 8; dwFlags
0x180004e25  mov     rcx, rax; hHeap
0x180004e28  call    cs:__imp_HeapAlloc
0x180004e2e  mov     rsi, rax
0x180004e31  test    rax, rax
0x180004e34  jz      loc_180004F40
0x180004e3a  mov     r8, [rdi]; pSourceSid
0x180004e3d  mov     rdx, rax; pDestinationSid
0x180004e40  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180004e43  call    cs:__imp_CopySid
0x180004e49  test    eax, eax
0x180004e4b  jz      loc_180004FA5
0x180004e51  xor     ebx, ebx
0x180004e53  mov     r14, rsi
0x180004e56  test    rdi, rdi
0x180004e59  jz      short loc_180004E77
0x180004e5b  call    cs:__imp_GetProcessHeap
0x180004e61  mov     r8, rdi; lpMem
0x180004e64  xor     edx, edx; dwFlags
0x180004e66  mov     rcx, rax; hHeap
0x180004e69  call    cs:__imp_HeapFree
0x180004e6f  test    eax, eax
0x180004e71  jz      loc_180004FC1
0x180004e77  xor     edi, edi
0x180004e79  test    ebx, ebx
0x180004e7b  js      loc_180004F14
0x180004e81  lea     rdx, [rbp+StringSid]; StringSid
0x180004e85  mov     [rbp+StringSid], rdi
0x180004e89  mov     rcx, r14; Sid
0x180004e8c  call    cs:__imp_ConvertSidToStringSidW
0x180004e92  test    eax, eax
0x180004e94  jz      short loc_180004E9A
0x180004e96  xor     ebx, ebx
0x180004e98  jmp     short loc_180004EA5
0x180004e9a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004e9f  mov     ebx, eax
0x180004ea1  test    eax, eax
0x180004ea3  js      short loc_180004EA9
0x180004ea5  mov     rdi, [rbp+StringSid]
0x180004ea9  test    r14, r14
0x180004eac  jz      short loc_180004ECA
0x180004eae  call    cs:__imp_GetProcessHeap
0x180004eb4  mov     r8, r14; lpMem
0x180004eb7  xor     edx, edx; dwFlags
0x180004eb9  mov     rcx, rax; hHeap
0x180004ebc  call    cs:__imp_HeapFree
0x180004ec2  test    eax, eax
0x180004ec4  jz      loc_180004FCB
0x180004eca  test    ebx, ebx
0x180004ecc  js      short loc_180004F14
0x180004ece  mov     rcx, rdi; lpSubKey
0x180004ed1  call    ?_IsRunLogonScriptSync@@YAHPEBG@Z; _IsRunLogonScriptSync(ushort const *)
0x180004ed6  xor     r8d, r8d; int *
0x180004ed9  mov     [rbp+lpMem], 0
0x180004ee1  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x180004ee5  mov     rcx, rdi; lpString1
0x180004ee8  mov     esi, eax
0x180004eea  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180004eef  mov     rbx, [rbp+lpMem]
0x180004ef3  test    eax, eax
0x180004ef5  jns     loc_180004FD5
0x180004efb  test    rbx, rbx
0x180004efe  jz      short loc_180004F14
0x180004f00  call    cs:__imp_GetProcessHeap
0x180004f06  mov     r8, rbx; lpMem
0x180004f09  xor     edx, edx; dwFlags
0x180004f0b  mov     rcx, rax; hHeap
0x180004f0e  call    cs:__imp_HeapFree
0x180004f14  test    rdi, rdi
0x180004f17  jz      short loc_180004F22
0x180004f19  mov     rcx, rdi; hMem
0x180004f1c  call    cs:__imp_LocalFree
0x180004f22  lea     r11, [rsp+50h+var_s0]
0x180004f27  mov     rbx, [r11+20h]
0x180004f2b  mov     rsi, [r11+38h]
0x180004f2f  mov     rsp, r11
0x180004f32  pop     r14
0x180004f34  pop     rdi
0x180004f35  pop     rbp
0x180004f36  retn
0x180004f37  mov     ebx, 8007000Eh
0x180004f3c  xor     edi, edi
0x180004f3e  jmp     short loc_180004ECA
0x180004f40  mov     ebx, 8007000Eh
0x180004f45  jmp     loc_180004E56
0x180004f4a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004f4f  mov     ebx, eax
0x180004f51  cmp     eax, 8007007Ah
0x180004f56  jnz     loc_180004E05
0x180004f5c  mov     edx, [rbp+TokenInformationLength]; dwBytes
0x180004f5f  lea     r8, [rbp+StringSid]; void **
0x180004f63  mov     rcx, rdi; lpMem
0x180004f66  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180004f6b  mov     rdi, [rbp+StringSid]
0x180004f6f  mov     ebx, eax
0x180004f71  test    eax, eax
0x180004f73  js      loc_180004E56
0x180004f79  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180004f7d  lea     rax, [rbp+TokenInformationLength]
0x180004f81  mov     r8, rdi; TokenInformation
0x180004f84  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180004f89  mov     edx, 1; TokenInformationClass
0x180004f8e  mov     rcx, rsi; TokenHandle
0x180004f91  call    cs:__imp_GetTokenInformation
0x180004f97  mov     ecx, eax; int
0x180004f99  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004f9e  mov     ebx, eax
0x180004fa0  jmp     loc_180004E05
0x180004fa5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004faa  mov     ebx, eax
0x180004fac  test    eax, eax
0x180004fae  jns     loc_180004E53
0x180004fb4  mov     rcx, rsi; lpMem
0x180004fb7  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004fbc  jmp     loc_180004E56
0x180004fc1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004fc6  jmp     loc_180004E77
0x180004fcb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004fd0  jmp     loc_180004ECA
0x180004fd5  mov     r9d, esi; int
0x180004fd8  lea     r8, Value; "RunLogonScriptSync"
0x180004fdf  mov     rdx, rbx; unsigned __int16 *
0x180004fe2  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x180004fe7  jmp     loc_180004EFB
```
