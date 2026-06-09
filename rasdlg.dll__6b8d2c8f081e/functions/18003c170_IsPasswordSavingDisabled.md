# IsPasswordSavingDisabled

- ea: `0x18003c170`
- end: `0x18003c24f`
- name: `IsPasswordSavingDisabled`
- size: `223`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000e360`

## callees

- `0x18003af74`
- `0x18003c170`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c1eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c1eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c22c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c22c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c220`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c220`

## string_xrefs

- `0x18003c1cf`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
_BOOL8 IsPasswordSavingDisabled()
{
  LSTATUS v0; // ebx
  _BOOL8 result; // rax
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids);
  }
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  result = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Rasman\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    v0 = RegQueryValueExW(hKey, L"DisableSavePassword", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( !v0 && Type == 4 && Data )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18003c170  push    rbp
0x18003c172  push    rbx
0x18003c173  mov     rbp, rsp
0x18003c176  sub     rsp, 38h
0x18003c17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c181  lea     rax, WPP_GLOBAL_Control
0x18003c188  cmp     rcx, rax
0x18003c18b  jz      short loc_18003C1AE
0x18003c18d  test    byte ptr [rcx+1Ch], 4
0x18003c191  jz      short loc_18003C1AE
0x18003c193  cmp     byte ptr [rcx+19h], 6
0x18003c197  jb      short loc_18003C1AE
0x18003c199  mov     rcx, [rcx+10h]
0x18003c19d  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18003c1a4  mov     edx, 30h ; '0'
0x18003c1a9  call    WPP_SF_
0x18003c1ae  lea     rax, [rbp+hKey]
0x18003c1b2  mov     [rbp+hKey], 0
0x18003c1ba  mov     r9d, 20019h; samDesired
0x18003c1c0  mov     [rsp+38h+phkResult], rax; phkResult
0x18003c1c5  xor     r8d, r8d; ulOptions
0x18003c1c8  mov     [rbp+Type], 0
0x18003c1cf  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Ra"...
0x18003c1d6  mov     [rbp+Data], 0
0x18003c1dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c1e4  mov     [rbp+cbData], 0
0x18003c1eb  call    cs:__imp_RegOpenKeyExW
0x18003c1f1  test    eax, eax
0x18003c1f3  jnz     short loc_18003C246
0x18003c1f5  mov     rcx, [rbp+hKey]; hKey
0x18003c1f9  lea     rax, [rbp+cbData]
0x18003c1fd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003c202  lea     r9, [rbp+Type]; lpType
0x18003c206  lea     rax, [rbp+Data]
0x18003c20a  mov     [rbp+cbData], 4
0x18003c211  xor     r8d, r8d; lpReserved
0x18003c214  mov     [rsp+38h+phkResult], rax; lpData
0x18003c219  lea     rdx, aDisablesavepas; "DisableSavePassword"
0x18003c220  call    cs:__imp_RegQueryValueExW
0x18003c226  mov     rcx, [rbp+hKey]; hKey
0x18003c22a  mov     ebx, eax
0x18003c22c  call    cs:__imp_RegCloseKey
0x18003c232  test    ebx, ebx
0x18003c234  jnz     short loc_18003C246
0x18003c236  cmp     [rbp+Type], 4
0x18003c23a  jnz     short loc_18003C246
0x18003c23c  cmp     [rbp+Data], ebx
0x18003c23f  jz      short loc_18003C246
0x18003c241  lea     eax, [rbx+1]
0x18003c244  jmp     short loc_18003C248
0x18003c246  xor     eax, eax
0x18003c248  add     rsp, 38h
0x18003c24c  pop     rbx
0x18003c24d  pop     rbp
0x18003c24e  retn
```
