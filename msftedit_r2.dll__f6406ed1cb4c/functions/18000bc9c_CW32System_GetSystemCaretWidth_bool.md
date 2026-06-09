# CW32System::GetSystemCaretWidth(bool)

- ea: `0x18000bc9c`
- end: `0x18000be04`
- name: `?GetSystemCaretWidth@CW32System@@SAE_N@Z`
- size: `360`
- prototype: `unsigned __int8 __fastcall(bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b2d8`
- `0x18000b468`

## callees

- `0x18000bc9c`
- `0x18013ce80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000bcef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000bcef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000bd2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000bd6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000bd2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000bd6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bda1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bda1`
- `ext-ms-win-ntuser-caret-l1-1-0!SetCaretBlinkTime` at `0x18000bd91`
- `ext-ms-win-ntuser-caret-l1-1-0!SetCaretBlinkTime` at `0x18000bd91`

## string_xrefs

- `0x18000bd66`: `CursorBlinkRate`

## pseudocode

```c
__int64 __fastcall CW32System::GetSystemCaretWidth()
{
  unsigned int v0; // ebx
  UINT v1; // ecx
  __int64 v2; // r8
  __int64 result; // rax
  int v4; // r9d
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  v0 = 1;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\Desktop", 0, 1u, &hKey) )
    return v0;
  cbData = 4;
  if ( !RegQueryValueExA(hKey, "CaretWidth", 0, &Type, Data, &cbData) && cbData <= 4 )
    v0 = *(_DWORD *)Data;
  cbData = 8;
  if ( !RegQueryValueExA(hKey, "CursorBlinkRate", 0, &Type, Data, &cbData) && cbData <= 8 )
  {
    v1 = 0;
    v2 = 0;
    if ( !cbData )
      goto LABEL_6;
    do
    {
      v4 = Data[v2];
      if ( (unsigned int)(v4 - 48) > 9 )
        break;
      v2 = (unsigned int)(v2 + 1);
      v1 = v4 + 2 * (5 * v1 - 24);
    }
    while ( (unsigned int)v2 < cbData );
    if ( !v1 )
LABEL_6:
      v1 = -1;
    SetCaretBlinkTime(v1);
  }
  RegCloseKey(hKey);
  result = 255;
  if ( v0 < 0xFF )
    return v0;
  return result;
}

```

## disassembly

```asm
0x18000bc9c  mov     [rsp-8+arg_0], rbx
0x18000bca1  push    rbp
0x18000bca2  mov     rbp, rsp
0x18000bca5  sub     rsp, 50h
0x18000bca9  mov     rax, cs:__security_cookie
0x18000bcb0  xor     rax, rsp
0x18000bcb3  mov     [rbp+var_8], rax
0x18000bcb7  lea     rax, [rbp+hKey]
0x18000bcbb  mov     [rbp+hKey], 0
0x18000bcc3  mov     ebx, 1
0x18000bcc8  mov     [rbp+Type], 0
0x18000bccf  mov     r9d, ebx; samDesired
0x18000bcd2  mov     [rbp+cbData], 0
0x18000bcd9  xor     r8d, r8d; ulOptions
0x18000bcdc  mov     [rsp+50h+phkResult], rax; phkResult
0x18000bce1  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x18000bce8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000bcef  call    cs:__imp_RegOpenKeyExA
0x18000bcf6  nop     dword ptr [rax+rax+00h]
0x18000bcfb  test    eax, eax
0x18000bcfd  jnz     loc_18000BDB6
0x18000bd03  mov     rcx, [rbp+hKey]; hKey
0x18000bd07  lea     rax, [rbp+cbData]
0x18000bd0b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000bd10  lea     r9, [rbp+Type]; lpType
0x18000bd14  lea     rax, [rbp+Data]
0x18000bd18  mov     [rbp+cbData], 4
0x18000bd1f  xor     r8d, r8d; lpReserved
0x18000bd22  mov     [rsp+50h+phkResult], rax; lpData
0x18000bd27  lea     rdx, aCaretwidth; "CaretWidth"
0x18000bd2e  call    cs:__imp_RegQueryValueExA
0x18000bd35  nop     dword ptr [rax+rax+00h]
0x18000bd3a  test    eax, eax
0x18000bd3c  jz      loc_18000BDD0
0x18000bd42  mov     rcx, [rbp+hKey]; hKey
0x18000bd46  lea     rax, [rbp+cbData]
0x18000bd4a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000bd4f  lea     r9, [rbp+Type]; lpType
0x18000bd53  lea     rax, [rbp+Data]
0x18000bd57  mov     [rbp+cbData], 8
0x18000bd5e  xor     r8d, r8d; lpReserved
0x18000bd61  mov     [rsp+50h+phkResult], rax; lpData
0x18000bd66  lea     rdx, aCursorblinkrat; "CursorBlinkRate"
0x18000bd6d  call    cs:__imp_RegQueryValueExA
0x18000bd74  nop     dword ptr [rax+rax+00h]
0x18000bd79  test    eax, eax
0x18000bd7b  jnz     short loc_18000BD9D
0x18000bd7d  mov     edx, [rbp+cbData]
0x18000bd80  cmp     edx, 8
0x18000bd83  ja      short loc_18000BD9D
0x18000bd85  xor     ecx, ecx
0x18000bd87  xor     r8d, r8d
0x18000bd8a  test    edx, edx
0x18000bd8c  jnz     short loc_18000BDDD
0x18000bd8e  or      ecx, 0FFFFFFFFh; uMSeconds
0x18000bd91  call    cs:__imp_SetCaretBlinkTime
0x18000bd98  nop     dword ptr [rax+rax+00h]
0x18000bd9d  mov     rcx, [rbp+hKey]; hKey
0x18000bda1  call    cs:__imp_RegCloseKey
0x18000bda8  nop     dword ptr [rax+rax+00h]
0x18000bdad  mov     eax, 0FFh
0x18000bdb2  cmp     ebx, eax
0x18000bdb4  jnb     short loc_18000BDB8
0x18000bdb6  mov     eax, ebx
0x18000bdb8  mov     rcx, [rbp+var_8]
0x18000bdbc  xor     rcx, rsp; StackCookie
0x18000bdbf  call    __security_check_cookie
0x18000bdc4  mov     rbx, [rsp+50h+arg_0]
0x18000bdc9  add     rsp, 50h
0x18000bdcd  pop     rbp
0x18000bdce  retn
0x18000bdd0  cmp     [rbp+cbData], 4
0x18000bdd4  cmovbe  ebx, dword ptr [rbp+Data]
0x18000bdd8  jmp     loc_18000BD42
0x18000bddd  movzx   r9d, [rbp+r8+Data]
0x18000bde3  lea     eax, [r9-30h]
0x18000bde7  cmp     eax, 9
0x18000bdea  ja      short loc_18000BDFE
0x18000bdec  lea     ecx, [rcx+rcx*4]
0x18000bdef  inc     r8d
0x18000bdf2  lea     ecx, [rcx-18h]
0x18000bdf5  lea     ecx, [r9+rcx*2]
0x18000bdf9  cmp     r8d, edx
0x18000bdfc  jb      short loc_18000BDDD
0x18000bdfe  test    ecx, ecx
0x18000be00  jnz     short loc_18000BD91
0x18000be02  jmp     short loc_18000BD8E
```
