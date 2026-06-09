# StLoadIntfParameters(_GUID *,ushort const *,ulong,void *)

- ea: `0x18001c900`
- end: `0x18001ca75`
- name: `?StLoadIntfParameters@@YAKPEAU_GUID@@PEBGKPEAX@Z`
- size: `373`
- prototype: `__int64 __fastcall(GUID *rguid, const unsigned __int16 *, __int64, BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a930`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001c900`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c9f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c9f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca1a`

## pseudocode

```c
__int64 __fastcall StLoadIntfParameters(GUID *rguid, const unsigned __int16 *a2, __int64 a3, BYTE *a4)
{
  unsigned int RegKeyPath; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 37, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, 0, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    RegKeyPath = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    if ( !RegKeyPath )
    {
      cbData = 4;
      RegKeyPath = RegQueryValueExW(hKey, L"Parameters", 0, &Type, a4, &cbData);
      if ( !RegKeyPath && (Type != 3 || cbData != 4) )
        RegKeyPath = 2;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 38, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001c900  mov     [rsp-8+arg_8], rbx
0x18001c905  push    rbp
0x18001c906  push    rdi
0x18001c907  push    r15
0x18001c909  lea     rbp, [rsp-160h]
0x18001c911  sub     rsp, 260h
0x18001c918  mov     rax, cs:__security_cookie
0x18001c91f  xor     rax, rsp
0x18001c922  mov     [rbp+170h+var_20], rax
0x18001c929  mov     rdi, r9
0x18001c92c  mov     [rsp+270h+hKey], 0
0x18001c935  mov     rbx, rcx
0x18001c938  mov     [rsp+270h+Type], 0
0x18001c940  mov     [rsp+270h+cbData], 0
0x18001c948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c94f  lea     r15, WPP_GLOBAL_Control
0x18001c956  cmp     rcx, r15
0x18001c959  jz      short loc_18001C97C
0x18001c95b  cmp     byte ptr [rcx+19h], 4
0x18001c95f  jb      short loc_18001C97C
0x18001c961  test    byte ptr [rcx+1Ch], 1
0x18001c965  jz      short loc_18001C97C
0x18001c967  mov     rcx, [rcx+10h]
0x18001c96b  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c972  mov     edx, 25h ; '%'
0x18001c977  call    WPP_SF_
0x18001c97c  lea     r9, [rsp+270h+SubKey]; unsigned __int16 *
0x18001c981  mov     [rsp+270h+phkResult], 104h; unsigned __int64
0x18001c98a  xor     r8d, r8d; int
0x18001c98d  xor     edx, edx; GUID *
0x18001c98f  mov     rcx, rbx; rguid
0x18001c992  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001c997  mov     ebx, eax
0x18001c999  test    eax, eax
0x18001c99b  jnz     short loc_18001CA10
0x18001c99d  lea     rax, [rsp+270h+hKey]
0x18001c9a2  xor     r8d, r8d; ulOptions
0x18001c9a5  lea     r9d, [rbx+1]; samDesired
0x18001c9a9  mov     [rsp+270h+phkResult], rax; phkResult
0x18001c9ae  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18001c9b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c9ba  call    cs:__imp_RegOpenKeyExW
0x18001c9c0  mov     ebx, eax
0x18001c9c2  test    eax, eax
0x18001c9c4  jnz     short loc_18001CA10
0x18001c9c6  mov     rcx, [rsp+270h+hKey]; hKey
0x18001c9cb  lea     rax, [rsp+270h+cbData]
0x18001c9d0  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18001c9d5  lea     r9, [rsp+270h+Type]; lpType
0x18001c9da  xor     r8d, r8d; lpReserved
0x18001c9dd  mov     [rsp+270h+phkResult], rdi; lpData
0x18001c9e2  lea     rdx, aParameters; "Parameters"
0x18001c9e9  mov     [rsp+270h+cbData], 4
0x18001c9f1  call    cs:__imp_RegQueryValueExW
0x18001c9f7  mov     ebx, eax
0x18001c9f9  test    eax, eax
0x18001c9fb  jnz     short loc_18001CA10
0x18001c9fd  cmp     [rsp+270h+Type], 3
0x18001ca02  jnz     short loc_18001CA0B
0x18001ca04  cmp     [rsp+270h+cbData], 4
0x18001ca09  jz      short loc_18001CA10
0x18001ca0b  mov     ebx, 2
0x18001ca10  mov     rcx, [rsp+270h+hKey]; hKey
0x18001ca15  test    rcx, rcx
0x18001ca18  jz      short loc_18001CA20
0x18001ca1a  call    cs:__imp_RegCloseKey
0x18001ca20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca27  cmp     rcx, r15
0x18001ca2a  jz      short loc_18001CA50
0x18001ca2c  cmp     byte ptr [rcx+19h], 4
0x18001ca30  jb      short loc_18001CA50
0x18001ca32  test    byte ptr [rcx+1Ch], 1
0x18001ca36  jz      short loc_18001CA50
0x18001ca38  mov     rcx, [rcx+10h]
0x18001ca3c  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001ca43  mov     edx, 26h ; '&'
0x18001ca48  mov     r9d, ebx
0x18001ca4b  call    WPP_SF_d
0x18001ca50  mov     eax, ebx
0x18001ca52  mov     rcx, [rbp+170h+var_20]
0x18001ca59  xor     rcx, rsp; StackCookie
0x18001ca5c  call    __security_check_cookie
0x18001ca61  mov     rbx, [rsp+270h+arg_8]
0x18001ca69  add     rsp, 260h
0x18001ca70  pop     r15
0x18001ca72  pop     rdi
0x18001ca73  pop     rbp
0x18001ca74  retn
```
