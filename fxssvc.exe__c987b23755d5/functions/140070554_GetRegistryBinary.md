# GetRegistryBinary

- ea: `0x140070554`
- end: `0x14007067c`
- name: `GetRegistryBinary`
- size: `296`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14004e1cc`
- `0x14007aab0`
- `0x14007b2a8`

## callees

- `0x140065d14`
- `0x140065dbc`
- `0x140070554`
- `0x140071ec8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140070649`
- `ADVAPI32!RegSetValueExW` at `0x140070649`
- `ADVAPI32!RegQueryValueExW` at `0x140070598`
- `ADVAPI32!RegQueryValueExW` at `0x140070614`
- `ADVAPI32!RegQueryValueExW` at `0x140070598`
- `ADVAPI32!RegQueryValueExW` at `0x140070614`

## string_xrefs

- `0x140070656`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
void *__fastcall GetRegistryBinary(HKEY hKey, LPCWSTR lpValueName, DWORD *a3)
{
  unsigned int v6; // eax
  void *lpData; // rbx
  DWORD v9; // eax
  unsigned int v10; // eax
  DWORD Type[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  cbData = 0;
  Type[0] = 3;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, Type, 0, &cbData);
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      lpData = 0;
LABEL_4:
      fax_dprintf(L"RegQueryValueEx() failed, ec=%d", v6);
LABEL_5:
      pMemFree(lpData);
      return 0;
    }
    goto LABEL_9;
  }
  if ( Type[0] != 3 )
    return 0;
  v9 = cbData;
  if ( !cbData )
  {
LABEL_9:
    v9 = 1;
    cbData = 1;
  }
  lpData = (void *)pMemAlloc(v9 + 1);
  if ( !lpData )
    goto LABEL_5;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, Type, (LPBYTE)lpData, &cbData);
  *((_BYTE *)lpData + cbData) = 0;
  if ( v6 )
  {
    if ( v6 != 2 )
      goto LABEL_4;
    v10 = RegSetValueExW(hKey, lpValueName, 0, 3u, (const BYTE *)lpData, cbData);
    if ( v10 )
    {
      fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v10);
      goto LABEL_5;
    }
  }
  if ( a3 )
    *a3 = cbData;
  return lpData;
}

```

## disassembly

```asm
0x140070554  mov     r11, rsp
0x140070557  mov     [r11+8], rbx
0x14007055b  mov     [r11+10h], rsi
0x14007055f  push    rbp
0x140070560  push    rdi
0x140070561  push    r14
0x140070563  mov     rbp, rsp
0x140070566  sub     rsp, 40h
0x14007056a  lea     rax, [rbp+cbData]
0x14007056e  mov     [rbp+cbData], 0
0x140070575  mov     rdi, r8
0x140070578  mov     [r11-30h], rax
0x14007057c  lea     r9, [rbp+Type]; lpType
0x140070580  mov     qword ptr [r11-38h], 0
0x140070588  xor     r8d, r8d; lpReserved
0x14007058b  mov     [rbp+Type], 3
0x140070592  mov     rsi, rdx
0x140070595  mov     r14, rcx
0x140070598  call    cs:__imp_RegQueryValueExW
0x14007059e  test    eax, eax
0x1400705a0  jz      short loc_1400705D4
0x1400705a2  cmp     eax, 2
0x1400705a5  jz      short loc_1400705E1
0x1400705a7  xor     ebx, ebx
0x1400705a9  mov     edx, eax
0x1400705ab  lea     rcx, aRegqueryvaluee_1; "RegQueryValueEx() failed, ec=%d"
0x1400705b2  call    fax_dprintf
0x1400705b7  mov     rcx, rbx; lpMem
0x1400705ba  call    pMemFree
0x1400705bf  xor     eax, eax
0x1400705c1  mov     rbx, [rsp+40h+arg_0]
0x1400705c6  mov     rsi, [rsp+40h+arg_8]
0x1400705cb  add     rsp, 40h
0x1400705cf  pop     r14
0x1400705d1  pop     rdi
0x1400705d2  pop     rbp
0x1400705d3  retn
0x1400705d4  cmp     [rbp+Type], 3
0x1400705d8  jnz     short loc_1400705BF
0x1400705da  mov     eax, [rbp+cbData]
0x1400705dd  test    eax, eax
0x1400705df  jnz     short loc_1400705E9
0x1400705e1  mov     eax, 1
0x1400705e6  mov     [rbp+cbData], eax
0x1400705e9  lea     ecx, [rax+1]; dwBytes
0x1400705ec  call    pMemAlloc
0x1400705f1  mov     rbx, rax
0x1400705f4  test    rax, rax
0x1400705f7  jz      short loc_1400705B7
0x1400705f9  lea     rax, [rbp+cbData]
0x1400705fd  xor     r8d, r8d; lpReserved
0x140070600  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140070605  lea     r9, [rbp+Type]; lpType
0x140070609  mov     rdx, rsi; lpValueName
0x14007060c  mov     [rsp+40h+lpData], rbx; lpData
0x140070611  mov     rcx, r14; hKey
0x140070614  call    cs:__imp_RegQueryValueExW
0x14007061a  mov     ecx, [rbp+cbData]
0x14007061d  mov     byte ptr [rcx+rbx], 0
0x140070621  test    eax, eax
0x140070623  jz      short loc_14007066A
0x140070625  cmp     eax, 2
0x140070628  jnz     loc_1400705A9
0x14007062e  mov     eax, [rbp+cbData]
0x140070631  mov     r9d, 3; dwType
0x140070637  mov     dword ptr [rsp+40h+lpcbData], eax; cbData
0x14007063b  xor     r8d, r8d; Reserved
0x14007063e  mov     rdx, rsi; lpValueName
0x140070641  mov     [rsp+40h+lpData], rbx; lpData
0x140070646  mov     rcx, r14; hKey
0x140070649  call    cs:__imp_RegSetValueExW
0x14007064f  test    eax, eax
0x140070651  jz      short loc_14007066A
0x140070653  mov     r8d, eax
0x140070656  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x14007065d  mov     rdx, rsi
0x140070660  call    fax_dprintf
0x140070665  jmp     loc_1400705B7
0x14007066a  test    rdi, rdi
0x14007066d  jz      short loc_140070674
0x14007066f  mov     eax, [rbp+cbData]
0x140070672  mov     [rdi], eax
0x140070674  mov     rax, rbx
0x140070677  jmp     loc_1400705C1
```
