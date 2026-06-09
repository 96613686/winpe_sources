# StLoadProfileList(_GUID *,_ST_PROFILE_LIST * *)

- ea: `0x18001cce8`
- end: `0x18001cfd0`
- name: `?StLoadProfileList@@YAKPEAU_GUID@@PEAPEAU_ST_PROFILE_LIST@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(GUID *rguid, struct _ST_PROFILE_LIST **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000df4c`

## callees

- `0x1800025f0`
- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001cce8`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cdab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cdab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cdeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ce58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cdeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ce58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cf5d`
- `RPCRT4!UuidFromStringW` at `0x18001cf0a`
- `RPCRT4!UuidFromStringW` at `0x18001cf0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceab`

## pseudocode

```c
__int64 __fastcall StLoadProfileList(GUID *rguid, struct _ST_PROFILE_LIST **a2)
{
  struct _ST_PROFILE_LIST *v3; // r14
  unsigned int RegKeyPath; // ebx
  BYTE *v6; // rsi
  unsigned __int128 v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdi
  unsigned int v11; // r15d
  BYTE *i; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 29, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, 0, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    v6 = 0;
    LODWORD(v7) = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    RegKeyPath = v7;
    if ( (_DWORD)v7 )
    {
      if ( (_DWORD)v7 != 2 )
        goto LABEL_34;
      LODWORD(v9) = 0;
    }
    else
    {
      LODWORD(v7) = RegQueryValueExW(hKey, L"ProfileList", 0, &Type, 0, &cbData);
      RegKeyPath = v7;
      if ( (v7 & 0xFFFFFFFD) != 0 )
        goto LABEL_34;
      LODWORD(v9) = 0;
      if ( !(_DWORD)v7 && Type == 7 )
      {
        v6 = (BYTE *)Dot3Alloc(cbData + 4LL, *((__int64 *)&v7 + 1), v8);
        if ( !v6 )
        {
          RegKeyPath = GetLastError();
          if ( RegKeyPath )
            goto LABEL_34;
        }
        RegKeyPath = RegQueryValueExW(hKey, L"ProfileList", 0, &Type, v6, &cbData);
        if ( RegKeyPath )
          goto LABEL_32;
        v10 = ((unsigned __int64)cbData >> 1) + 1;
        v7 = v10 * (unsigned __int128)0xA41A41A41A41A41BuLL;
        v9 = v10 / 0x27;
      }
    }
    LODWORD(v7) = 16 * v9;
    if ( !(_DWORD)v9 )
      LODWORD(v7) = 16;
    v3 = (struct _ST_PROFILE_LIST *)Dot3Alloc((unsigned int)(v7 + 4), *((__int64 *)&v7 + 1), v8);
    if ( v3 || (RegKeyPath = GetLastError()) == 0 )
    {
      v11 = 0;
      RegKeyPath = 0;
      if ( (_DWORD)v9 )
      {
        for ( i = v6; *(_WORD *)i; i += 2 * v14 + 2 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&i[2 * v13] );
          if ( v13 == 38 && *(_WORD *)i == 123 && *((_WORD *)i + 37) == 125 )
          {
            *((_WORD *)i + 37) = 0;
            UuidFromStringW((RPC_WSTR)i + 1, (UUID *)((char *)v3 + 16 * v11 + 4));
            *((_WORD *)i + 37) = 125;
            ++v11;
          }
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)&i[2 * v14] );
        }
      }
      *(_DWORD *)v3 = v11;
      *a2 = v3;
    }
LABEL_32:
    if ( v6 )
      Dot3Free(v6);
  }
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( RegKeyPath && v3 )
    Dot3Free(v3);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 30, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001cce8  mov     [rsp-8+arg_10], rbx
0x18001cced  push    rbp
0x18001ccee  push    rsi
0x18001ccef  push    rdi
0x18001ccf0  push    r12
0x18001ccf2  push    r13
0x18001ccf4  push    r14
0x18001ccf6  push    r15
0x18001ccf8  lea     rbp, [rsp-170h]
0x18001cd00  sub     rsp, 270h
0x18001cd07  mov     rax, cs:__security_cookie
0x18001cd0e  xor     rax, rsp
0x18001cd11  mov     [rbp+1A0h+var_40], rax
0x18001cd18  xor     r13d, r13d
0x18001cd1b  mov     r12, rdx
0x18001cd1e  mov     r14d, r13d
0x18001cd21  mov     [rsp+2A0h+hKey], r13
0x18001cd26  mov     [rsp+2A0h+Type], r13d
0x18001cd2b  mov     rbx, rcx
0x18001cd2e  mov     [rsp+2A0h+cbData], r13d
0x18001cd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd3a  lea     rdi, WPP_GLOBAL_Control
0x18001cd41  cmp     rcx, rdi
0x18001cd44  jz      short loc_18001CD66
0x18001cd46  cmp     byte ptr [rcx+19h], 4
0x18001cd4a  jb      short loc_18001CD66
0x18001cd4c  test    byte ptr [rcx+1Ch], 1
0x18001cd50  jz      short loc_18001CD66
0x18001cd52  mov     rcx, [rcx+10h]
0x18001cd56  lea     edx, [r13+1Dh]
0x18001cd5a  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001cd61  call    WPP_SF_
0x18001cd66  lea     r9, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18001cd6b  mov     [rsp+2A0h+phkResult], 104h; unsigned __int64
0x18001cd74  xor     r8d, r8d; int
0x18001cd77  xor     edx, edx; GUID *
0x18001cd79  mov     rcx, rbx; rguid
0x18001cd7c  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001cd81  mov     ebx, eax
0x18001cd83  test    eax, eax
0x18001cd85  jnz     loc_18001CF53
0x18001cd8b  lea     rax, [rsp+2A0h+hKey]
0x18001cd90  xor     r8d, r8d; ulOptions
0x18001cd93  lea     r9d, [rbx+1]; samDesired
0x18001cd97  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001cd9c  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18001cda1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cda8  mov     rsi, r13
0x18001cdab  call    cs:__imp_RegOpenKeyExW
0x18001cdb1  mov     ebx, eax
0x18001cdb3  test    eax, eax
0x18001cdb5  jz      short loc_18001CDC8
0x18001cdb7  cmp     eax, 2
0x18001cdba  jnz     loc_18001CF53
0x18001cdc0  mov     edi, r13d
0x18001cdc3  jmp     loc_18001CE8C
0x18001cdc8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001cdcd  lea     rax, [rsp+2A0h+cbData]
0x18001cdd2  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18001cdd7  lea     r9, [rsp+2A0h+Type]; lpType
0x18001cddc  xor     r8d, r8d; lpReserved
0x18001cddf  mov     [rsp+2A0h+phkResult], r13; lpData
0x18001cde4  lea     rdx, aProfilelist; "ProfileList"
0x18001cdeb  call    cs:__imp_RegQueryValueExW
0x18001cdf1  mov     ebx, eax
0x18001cdf3  test    eax, 0FFFFFFFDh
0x18001cdf8  jnz     loc_18001CF53
0x18001cdfe  mov     edi, r13d
0x18001ce01  test    eax, eax
0x18001ce03  jnz     loc_18001CE8C
0x18001ce09  cmp     [rsp+2A0h+Type], 7
0x18001ce0e  jnz     short loc_18001CE8C
0x18001ce10  mov     ecx, [rsp+2A0h+cbData]
0x18001ce14  add     rcx, 4; dwBytes
0x18001ce18  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001ce1d  mov     rsi, rax
0x18001ce20  test    rax, rax
0x18001ce23  jnz     short loc_18001CE35
0x18001ce25  call    cs:__imp_GetLastError
0x18001ce2b  mov     ebx, eax
0x18001ce2d  test    eax, eax
0x18001ce2f  jnz     loc_18001CF4C
0x18001ce35  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001ce3a  lea     rax, [rsp+2A0h+cbData]
0x18001ce3f  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18001ce44  lea     r9, [rsp+2A0h+Type]; lpType
0x18001ce49  xor     r8d, r8d; lpReserved
0x18001ce4c  mov     [rsp+2A0h+phkResult], rsi; lpData
0x18001ce51  lea     rdx, aProfilelist; "ProfileList"
0x18001ce58  call    cs:__imp_RegQueryValueExW
0x18001ce5e  mov     ebx, eax
0x18001ce60  test    eax, eax
0x18001ce62  jnz     loc_18001CF3F
0x18001ce68  mov     edi, [rsp+2A0h+cbData]
0x18001ce6c  mov     rax, 0A41A41A41A41A41Bh
0x18001ce76  shr     rdi, 1
0x18001ce79  inc     rdi
0x18001ce7c  mul     rdi
0x18001ce7f  sub     rdi, rdx
0x18001ce82  shr     rdi, 1
0x18001ce85  add     rdi, rdx
0x18001ce88  shr     rdi, 5
0x18001ce8c  mov     eax, edi
0x18001ce8e  mov     ecx, 10h
0x18001ce93  shl     eax, 4
0x18001ce96  test    edi, edi
0x18001ce98  cmovz   eax, ecx
0x18001ce9b  lea     ecx, [rax+4]; dwBytes
0x18001ce9e  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001cea3  mov     r14, rax
0x18001cea6  test    rax, rax
0x18001cea9  jnz     short loc_18001CEBB
0x18001ceab  call    cs:__imp_GetLastError
0x18001ceb1  mov     ebx, eax
0x18001ceb3  test    eax, eax
0x18001ceb5  jnz     loc_18001CF3F
0x18001cebb  mov     r15d, r13d
0x18001cebe  mov     ebx, r13d
0x18001cec1  test    edi, edi
0x18001cec3  jz      short loc_18001CF38
0x18001cec5  mov     rdi, rsi
0x18001cec8  cmp     [rsi], r13w
0x18001cecc  jz      short loc_18001CF38
0x18001cece  mov     ecx, 7Dh ; '}'
0x18001ced3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ced7  inc     rax
0x18001ceda  cmp     [rdi+rax*2], r13w
0x18001cedf  jnz     short loc_18001CED7
0x18001cee1  cmp     rax, 26h ; '&'
0x18001cee5  jnz     short loc_18001CF1C
0x18001cee7  cmp     word ptr [rdi], 7Bh ; '{'
0x18001ceeb  jnz     short loc_18001CF1C
0x18001ceed  cmp     [rdi+4Ah], cx
0x18001cef1  jnz     short loc_18001CF1C
0x18001cef3  mov     edx, r15d
0x18001cef6  lea     rcx, [rdi+2]; StringUuid
0x18001cefa  shl     rdx, 4
0x18001cefe  add     rdx, 4
0x18001cf02  mov     [rdi+4Ah], r13w
0x18001cf07  add     rdx, r14; Uuid
0x18001cf0a  call    cs:__imp_UuidFromStringW
0x18001cf10  mov     ecx, 7Dh ; '}'
0x18001cf15  mov     [rdi+4Ah], cx
0x18001cf19  inc     r15d
0x18001cf1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cf20  inc     rax
0x18001cf23  cmp     [rdi+rax*2], r13w
0x18001cf28  jnz     short loc_18001CF20
0x18001cf2a  lea     rdi, [rdi+rax*2]
0x18001cf2e  add     rdi, 2
0x18001cf32  cmp     [rdi], r13w
0x18001cf36  jnz     short loc_18001CED3
0x18001cf38  mov     [r14], r15d
0x18001cf3b  mov     [r12], r14
0x18001cf3f  test    rsi, rsi
0x18001cf42  jz      short loc_18001CF4C
0x18001cf44  mov     rcx, rsi; lpMem
0x18001cf47  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001cf4c  lea     rdi, WPP_GLOBAL_Control
0x18001cf53  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001cf58  test    rcx, rcx
0x18001cf5b  jz      short loc_18001CF63
0x18001cf5d  call    cs:__imp_RegCloseKey
0x18001cf63  test    ebx, ebx
0x18001cf65  jz      short loc_18001CF74
0x18001cf67  test    r14, r14
0x18001cf6a  jz      short loc_18001CF74
0x18001cf6c  mov     rcx, r14; lpMem
0x18001cf6f  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001cf74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf7b  cmp     rcx, rdi
0x18001cf7e  jz      short loc_18001CFA4
0x18001cf80  cmp     byte ptr [rcx+19h], 4
0x18001cf84  jb      short loc_18001CFA4
0x18001cf86  test    byte ptr [rcx+1Ch], 1
0x18001cf8a  jz      short loc_18001CFA4
0x18001cf8c  mov     rcx, [rcx+10h]
0x18001cf90  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001cf97  mov     edx, 1Eh
0x18001cf9c  mov     r9d, ebx
0x18001cf9f  call    WPP_SF_d
0x18001cfa4  mov     eax, ebx
0x18001cfa6  mov     rcx, [rbp+1A0h+var_40]
0x18001cfad  xor     rcx, rsp; StackCookie
0x18001cfb0  call    __security_check_cookie
0x18001cfb5  mov     rbx, [rsp+2A0h+arg_10]
0x18001cfbd  add     rsp, 270h
0x18001cfc4  pop     r15
0x18001cfc6  pop     r14
0x18001cfc8  pop     r13
0x18001cfca  pop     r12
0x18001cfcc  pop     rdi
0x18001cfcd  pop     rsi
0x18001cfce  pop     rbp
0x18001cfcf  retn
```
