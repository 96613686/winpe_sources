# StSaveUserData(void *,_GUID const *,_GUID const *,ushort const *,ulong,uchar *)

- ea: `0x18001dd30`
- end: `0x18001dfe9`
- name: `?StSaveUserData@@YAKPEAXPEBU_GUID@@1PEBGKPEAE@Z`
- size: `697`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, GUID *rguid, struct _GUID *, const unsigned __int16 *, DWORD, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000ce28`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001dd30`
- `0x18001e34c`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001de8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001de8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001de6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001de6a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dedd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001dedd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df60`
- `CRYPT32!CryptProtectData` at `0x18001df15`
- `CRYPT32!CryptProtectData` at `0x18001df15`

## pseudocode

```c
__int64 __fastcall StSaveUserData(
        HANDLE TokenHandle,
        GUID *rguid,
        struct _GUID *a3,
        const unsigned __int16 *a4,
        DWORD a5,
        unsigned __int8 *a6)
{
  HKEY v9; // rdi
  unsigned int RegKeyPath; // ebx
  unsigned int HKeyFromToken; // eax
  __int64 v12; // rcx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rcx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v18; // [rsp+58h] [rbp-A8h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-A0h] BYREF
  GUID *v20; // [rsp+70h] [rbp-90h]
  DATA_BLOB pDataIn; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  *(&pDataIn.cbData + 1) = 0;
  v20 = a3;
  v18 = 0;
  v9 = 0;
  hKey = 0;
  pDataIn.cbData = a5;
  pDataIn.pbData = a6;
  *(_QWORD *)&pDataOut.cbData = 0;
  pDataOut.pbData = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 31, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  if ( !a4 )
    goto LABEL_6;
  if ( a5 )
  {
    if ( a6 )
      goto LABEL_11;
LABEL_6:
    RegKeyPath = 87;
    goto LABEL_29;
  }
  if ( a6 )
    goto LABEL_6;
LABEL_11:
  if ( !TokenHandle
    || (HKeyFromToken = StpGetHKeyFromToken(TokenHandle, &v18), v9 = v18, (RegKeyPath = HKeyFromToken) == 0) )
  {
    RegKeyPath = StpGetRegKeyPath(rguid, v20, 1, SubKey, 0x104u);
    if ( !RegKeyPath )
    {
      if ( a5 || a6 )
      {
        v15 = -2147483646;
        if ( TokenHandle )
          v15 = (__int64)v9;
        RegKeyPath = RegCreateKeyExW((HKEY)v15, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
        if ( !RegKeyPath
          && (CryptProtectData(&pDataIn, 0, &blobSalt, 0, 0, 1u, &pDataOut) || (RegKeyPath = GetLastError()) == 0) )
        {
          v14 = RegSetValueExW(hKey, a4, 0, 3u, pDataOut.pbData, pDataOut.cbData);
          goto LABEL_28;
        }
      }
      else
      {
        v12 = -2147483646;
        if ( TokenHandle )
          v12 = (__int64)v9;
        v13 = RegOpenKeyExW((HKEY)v12, SubKey, 0, 2u, &hKey);
        RegKeyPath = v13;
        if ( v13 == 2 )
        {
          RegKeyPath = 0;
          goto LABEL_29;
        }
        if ( !v13 )
        {
          v14 = RegDeleteValueW(hKey, a4);
LABEL_28:
          RegKeyPath = v14;
        }
      }
    }
  }
LABEL_29:
  if ( pDataOut.pbData )
  {
    LocalFree(pDataOut.pbData);
    pDataOut.pbData = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    RegCloseKey(v9);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 32, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001dd30  push    rbp
0x18001dd32  push    rbx
0x18001dd33  push    rsi
0x18001dd34  push    rdi
0x18001dd35  push    r12
0x18001dd37  push    r13
0x18001dd39  push    r14
0x18001dd3b  push    r15
0x18001dd3d  lea     rbp, [rsp-1B8h]
0x18001dd45  sub     rsp, 2B8h
0x18001dd4c  mov     rax, cs:__security_cookie
0x18001dd53  xor     rax, rsp
0x18001dd56  mov     [rbp+1F0h+var_50], rax
0x18001dd5d  mov     rsi, [rbp+1F0h+arg_28]
0x18001dd64  xor     ebx, ebx
0x18001dd66  mov     r15d, [rbp+1F0h+arg_20]
0x18001dd6d  xor     eax, eax
0x18001dd6f  mov     dword ptr [rsp+2F0h+pDataIn+4], eax
0x18001dd73  mov     r12, r9
0x18001dd76  mov     [rsp+2F0h+var_280], r8
0x18001dd7b  mov     r13, rdx
0x18001dd7e  mov     r14, rcx
0x18001dd81  mov     [rsp+2F0h+var_298], rbx
0x18001dd86  mov     edi, ebx
0x18001dd88  mov     [rsp+2F0h+hKey], rbx
0x18001dd8d  mov     [rsp+2F0h+pDataIn.cbData], r15d
0x18001dd92  mov     [rbp+1F0h+pDataIn.pbData], rsi
0x18001dd96  mov     qword ptr [rsp+2F0h+pDataOut.cbData], rbx
0x18001dd9b  mov     [rsp+2F0h+pDataOut.pbData], rbx
0x18001dda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dda7  lea     rax, WPP_GLOBAL_Control
0x18001ddae  cmp     rcx, rax
0x18001ddb1  jz      short loc_18001DDD2
0x18001ddb3  cmp     byte ptr [rcx+19h], 4
0x18001ddb7  jb      short loc_18001DDD2
0x18001ddb9  test    byte ptr [rcx+1Ch], 1
0x18001ddbd  jz      short loc_18001DDD2
0x18001ddbf  mov     rcx, [rcx+10h]
0x18001ddc3  lea     edx, [rbx+1Fh]
0x18001ddc6  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001ddcd  call    WPP_SF_
0x18001ddd2  test    r12, r12
0x18001ddd5  jnz     short loc_18001DDE1
0x18001ddd7  mov     ebx, 57h ; 'W'
0x18001dddc  jmp     loc_18001DF56
0x18001dde1  test    r15d, r15d
0x18001dde4  jnz     short loc_18001DDED
0x18001dde6  test    rsi, rsi
0x18001dde9  jnz     short loc_18001DDD7
0x18001ddeb  jmp     short loc_18001DDF2
0x18001dded  test    rsi, rsi
0x18001ddf0  jz      short loc_18001DDD7
0x18001ddf2  test    r14, r14
0x18001ddf5  jz      short loc_18001DE13
0x18001ddf7  lea     rdx, [rsp+2F0h+var_298]; HKEY *
0x18001ddfc  mov     rcx, r14; TokenHandle
0x18001ddff  call    ?StpGetHKeyFromToken@@YAKPEAXPEAPEAUHKEY__@@@Z; StpGetHKeyFromToken(void *,HKEY__ * *)
0x18001de04  mov     rdi, [rsp+2F0h+var_298]
0x18001de09  mov     ebx, eax
0x18001de0b  test    eax, eax
0x18001de0d  jnz     loc_18001DF56
0x18001de13  mov     rdx, [rsp+2F0h+var_280]; GUID *
0x18001de18  lea     r9, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18001de1c  mov     r8d, 1; int
0x18001de22  mov     [rsp+2F0h+phkResult], 104h; unsigned __int64
0x18001de2b  mov     rcx, r13; rguid
0x18001de2e  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001de33  mov     ebx, eax
0x18001de35  test    eax, eax
0x18001de37  jnz     loc_18001DF56
0x18001de3d  test    r15d, r15d
0x18001de40  jnz     short loc_18001DE99
0x18001de42  test    rsi, rsi
0x18001de45  jnz     short loc_18001DE99
0x18001de47  lea     rax, [rsp+2F0h+hKey]
0x18001de4c  test    r14, r14
0x18001de4f  mov     rcx, 0FFFFFFFF80000002h
0x18001de56  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18001de5b  cmovnz  rcx, rdi; hKey
0x18001de5f  lea     r9d, [rbx+2]; samDesired
0x18001de63  xor     r8d, r8d; ulOptions
0x18001de66  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18001de6a  call    cs:__imp_RegOpenKeyExW
0x18001de70  mov     ebx, eax
0x18001de72  cmp     eax, 2
0x18001de75  jnz     short loc_18001DE7E
0x18001de77  xor     ebx, ebx
0x18001de79  jmp     loc_18001DF56
0x18001de7e  test    eax, eax
0x18001de80  jnz     loc_18001DF56
0x18001de86  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001de8b  mov     rdx, r12; lpValueName
0x18001de8e  call    cs:__imp_RegDeleteValueW
0x18001de94  jmp     loc_18001DF54
0x18001de99  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18001dea2  lea     rax, [rsp+2F0h+hKey]
0x18001dea7  mov     [rsp+2F0h+var_2B8], rax; phkResult
0x18001deac  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18001deb0  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001deb9  test    r14, r14
0x18001debc  mov     rcx, 0FFFFFFFF80000002h
0x18001dec3  mov     [rsp+2F0h+samDesired], 20006h; samDesired
0x18001decb  cmovnz  rcx, rdi; hKey
0x18001decf  mov     dword ptr [rsp+2F0h+phkResult], 0; dwOptions
0x18001ded7  xor     r9d, r9d; lpClass
0x18001deda  xor     r8d, r8d; Reserved
0x18001dedd  call    cs:__imp_RegCreateKeyExW
0x18001dee3  mov     ebx, eax
0x18001dee5  test    eax, eax
0x18001dee7  jnz     short loc_18001DF56
0x18001dee9  lea     rax, [rsp+2F0h+pDataOut]
0x18001deee  xor     r9d, r9d; pvReserved
0x18001def1  mov     [rsp+2F0h+lpSecurityAttributes], rax; pDataOut
0x18001def6  lea     r8, ?blobSalt@@3U_CRYPTOAPI_BLOB@@A; pOptionalEntropy
0x18001defd  mov     [rsp+2F0h+samDesired], 1; dwFlags
0x18001df05  lea     rcx, [rsp+2F0h+pDataIn]; pDataIn
0x18001df0a  xor     edx, edx; szDataDescr
0x18001df0c  mov     [rsp+2F0h+phkResult], 0; pPromptStruct
0x18001df15  call    cs:__imp_CryptProtectData
0x18001df1b  test    eax, eax
0x18001df1d  jnz     short loc_18001DF2B
0x18001df1f  call    cs:__imp_GetLastError
0x18001df25  mov     ebx, eax
0x18001df27  test    eax, eax
0x18001df29  jnz     short loc_18001DF56
0x18001df2b  mov     eax, [rsp+2F0h+pDataOut.cbData]
0x18001df2f  mov     r9d, 3; dwType
0x18001df35  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001df3a  xor     r8d, r8d; Reserved
0x18001df3d  mov     [rsp+2F0h+samDesired], eax; cbData
0x18001df41  mov     rdx, r12; lpValueName
0x18001df44  mov     rax, [rsp+2F0h+pDataOut.pbData]
0x18001df49  mov     [rsp+2F0h+phkResult], rax; lpData
0x18001df4e  call    cs:__imp_RegSetValueExW
0x18001df54  mov     ebx, eax
0x18001df56  mov     rcx, [rsp+2F0h+pDataOut.pbData]; hMem
0x18001df5b  test    rcx, rcx
0x18001df5e  jz      short loc_18001DF6F
0x18001df60  call    cs:__imp_LocalFree
0x18001df66  mov     [rsp+2F0h+pDataOut.pbData], 0
0x18001df6f  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001df74  test    rcx, rcx
0x18001df77  jz      short loc_18001DF7F
0x18001df79  call    cs:__imp_RegCloseKey
0x18001df7f  test    rdi, rdi
0x18001df82  jz      short loc_18001DF8D
0x18001df84  mov     rcx, rdi; hKey
0x18001df87  call    cs:__imp_RegCloseKey
0x18001df8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df94  lea     rax, WPP_GLOBAL_Control
0x18001df9b  cmp     rcx, rax
0x18001df9e  jz      short loc_18001DFC4
0x18001dfa0  cmp     byte ptr [rcx+19h], 4
0x18001dfa4  jb      short loc_18001DFC4
0x18001dfa6  test    byte ptr [rcx+1Ch], 1
0x18001dfaa  jz      short loc_18001DFC4
0x18001dfac  mov     rcx, [rcx+10h]
0x18001dfb0  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001dfb7  mov     edx, 20h ; ' '
0x18001dfbc  mov     r9d, ebx
0x18001dfbf  call    WPP_SF_d
0x18001dfc4  mov     eax, ebx
0x18001dfc6  mov     rcx, [rbp+1F0h+var_50]
0x18001dfcd  xor     rcx, rsp; StackCookie
0x18001dfd0  call    __security_check_cookie
0x18001dfd5  add     rsp, 2B8h
0x18001dfdc  pop     r15
0x18001dfde  pop     r14
0x18001dfe0  pop     r13
0x18001dfe2  pop     r12
0x18001dfe4  pop     rdi
0x18001dfe5  pop     rsi
0x18001dfe6  pop     rbx
0x18001dfe7  pop     rbp
0x18001dfe8  retn
```
