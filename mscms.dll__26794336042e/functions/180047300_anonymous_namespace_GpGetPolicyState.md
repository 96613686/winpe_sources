# _anonymous_namespace_::GpGetPolicyState

- ea: `0x180047300`
- end: `0x180047425`
- name: `_anonymous_namespace_::GpGetPolicyState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180047430`

## callees

- `0x180047300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800473ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800473ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004737a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004737a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047402`

## string_xrefs

- `0x1800473a9`: `ProhibitInstallUninstall`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GpGetPolicyState(__int64 a1, __int64 a2, LSTATUS *a3)
{
  unsigned int v3; // ebx
  unsigned int i; // edi
  LSTATUS Value; // eax
  bool v7; // cc
  LSTATUS v8; // eax
  __int64 cbData; // [rsp+60h] [rbp+30h] BYREF
  __int64 Type; // [rsp+68h] [rbp+38h] BYREF
  int Data; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  Type = a2;
  cbData = a1;
  v3 = 0;
  *a3 = 2;
  hKey = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( hKey )
    {
      Value = RegCloseKey(hKey);
      v7 = Value <= 0;
      if ( Value )
        goto LABEL_15;
      hKey = 0;
    }
    Value = RegOpenKeyExW(
              (HKEY)qword_18008C400[i],
              L"Software\\Policies\\Microsoft\\Windows\\WindowsColorSystem",
              0,
              0x20019u,
              &hKey);
    if ( Value != 2 )
    {
      v7 = Value <= 0;
      if ( Value )
        goto LABEL_15;
      LODWORD(Type) = 0;
      Data = 0;
      LODWORD(cbData) = 4;
      Value = RegQueryValueExW(hKey, L"ProhibitInstallUninstall", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData);
      if ( Value != 2 )
      {
        v7 = Value <= 0;
        if ( Value )
        {
LABEL_15:
          if ( v7 )
            v3 = Value;
          else
            v3 = (unsigned __int16)Value | 0x80070000;
          break;
        }
        if ( (_DWORD)Type == 4 && (_DWORD)cbData == 4 )
        {
          LOBYTE(Value) = Data == 0;
          *a3 = Value;
        }
        else
        {
          v3 = -2147467259;
        }
        break;
      }
    }
  }
  if ( hKey )
  {
    v8 = RegCloseKey(hKey);
    if ( v8 )
    {
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
      else
        return (unsigned int)v8;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180047300  mov     [rsp-28h+Type], rdx
0x180047305  mov     [rsp-28h+cbData], rcx
0x18004730a  push    rbp
0x18004730b  push    rbx
0x18004730c  push    rsi
0x18004730d  push    rdi
0x18004730e  push    r15
0x180047310  mov     rbp, rsp
0x180047313  sub     rsp, 30h
0x180047317  xor     ebx, ebx
0x180047319  mov     dword ptr [r8], 2
0x180047320  mov     [rbp+hKey], rbx
0x180047324  xor     edi, edi
0x180047326  mov     rsi, r8
0x180047329  mov     r15d, 80070000h
0x18004732f  cmp     edi, 2
0x180047332  jnb     loc_1800473F9
0x180047338  mov     rcx, [rbp+hKey]; hKey
0x18004733c  test    rcx, rcx
0x18004733f  jz      short loc_180047353
0x180047341  call    cs:__imp_RegCloseKey
0x180047347  test    eax, eax
0x180047349  jnz     loc_1800473ED
0x18004734f  mov     [rbp+hKey], rbx
0x180047353  lea     r10, qword_18008C400
0x18004735a  movsxd  rcx, edi
0x18004735d  lea     rax, [rbp+hKey]
0x180047361  mov     r9d, 20019h; samDesired
0x180047367  xor     r8d, r8d; ulOptions
0x18004736a  mov     [rsp+30h+phkResult], rax; phkResult
0x18004736f  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180047376  mov     rcx, [r10+rcx*8]; hKey
0x18004737a  call    cs:__imp_RegOpenKeyExW
0x180047380  cmp     eax, 2
0x180047383  jz      short loc_1800473C5
0x180047385  test    eax, eax
0x180047387  jnz     short loc_1800473ED
0x180047389  mov     rcx, [rbp+hKey]; hKey
0x18004738d  lea     rax, [rbp+cbData]
0x180047391  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180047396  lea     r9, [rbp+Type]; lpType
0x18004739a  lea     rax, [rbp+Data]
0x18004739e  mov     dword ptr [rbp+Type], ebx
0x1800473a1  xor     r8d, r8d; lpReserved
0x1800473a4  mov     [rsp+30h+phkResult], rax; lpData
0x1800473a9  lea     rdx, aProhibitinstal; "ProhibitInstallUninstall"
0x1800473b0  mov     [rbp+Data], ebx
0x1800473b3  mov     dword ptr [rbp+cbData], 4
0x1800473ba  call    cs:__imp_RegQueryValueExW
0x1800473c0  cmp     eax, 2
0x1800473c3  jnz     short loc_1800473CC
0x1800473c5  inc     edi
0x1800473c7  jmp     loc_180047329
0x1800473cc  test    eax, eax
0x1800473ce  jnz     short loc_1800473ED
0x1800473d0  cmp     dword ptr [rbp+Type], 4
0x1800473d4  jnz     short loc_1800473E6
0x1800473d6  cmp     dword ptr [rbp+cbData], 4
0x1800473da  jnz     short loc_1800473E6
0x1800473dc  cmp     [rbp+Data], eax
0x1800473df  setz    al
0x1800473e2  mov     [rsi], eax
0x1800473e4  jmp     short loc_1800473F9
0x1800473e6  mov     ebx, 80004005h
0x1800473eb  jmp     short loc_1800473F9
0x1800473ed  jg      short loc_1800473F3
0x1800473ef  mov     ebx, eax
0x1800473f1  jmp     short loc_1800473F9
0x1800473f3  movzx   ebx, ax
0x1800473f6  or      ebx, r15d
0x1800473f9  mov     rcx, [rbp+hKey]; hKey
0x1800473fd  test    rcx, rcx
0x180047400  jz      short loc_180047418
0x180047402  call    cs:__imp_RegCloseKey
0x180047408  test    eax, eax
0x18004740a  jz      short loc_180047418
0x18004740c  jg      short loc_180047412
0x18004740e  mov     ebx, eax
0x180047410  jmp     short loc_180047418
0x180047412  movzx   ebx, ax
0x180047415  or      ebx, r15d
0x180047418  mov     eax, ebx
0x18004741a  add     rsp, 30h
0x18004741e  pop     r15
0x180047420  pop     rdi
0x180047421  pop     rsi
0x180047422  pop     rbx
0x180047423  pop     rbp
0x180047424  retn
```
