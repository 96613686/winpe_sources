# IsInboundAppActivationAllowed(int *)

- ea: `0x18004d2c8`
- end: `0x18004d3ae`
- name: `?IsInboundAppActivationAllowed@@YAJPEAH@Z`
- size: `230`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d820`

## callees

- `0x18003d3fc`
- `0x18004d2c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d39e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d39e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d32a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d32a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004d369`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004d369`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x18004d2f1`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x18004d2f1`

## pseudocode

```c
__int64 __fastcall IsInboundAppActivationAllowed(int *a1)
{
  signed int v1; // ebx
  LSTATUS ValueW; // eax
  bool v4; // cc
  HKEY hkey; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF
  DWORD pdwType; // [rsp+80h] [rbp+30h] BYREF
  int pvData; // [rsp+88h] [rbp+38h] BYREF

  v1 = 0;
  hkey = 0;
  pcbData = 0;
  pdwType = 0;
  pvData = 0;
  if ( (unsigned __int8)IsIsEmbeddedModeAllowedPresent() )
  {
    v1 = IsEmbeddedModeAllowed(a1);
    if ( v1 < 0 || *a1 )
      goto LABEL_12;
  }
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Device Association Framework", 0, 0x20019u, &hkey);
  v4 = ValueW <= 0;
  if ( ValueW
    || (pcbData = 4,
        ValueW = RegGetValueW(hkey, 0, L"Inbound", 0x18u, &pdwType, &pvData, &pcbData),
        v4 = ValueW <= 0,
        ValueW) )
  {
    if ( !v4 )
    {
      v1 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_12;
    }
LABEL_10:
    v1 = ValueW;
    goto LABEL_12;
  }
  if ( pdwType != 4 )
    goto LABEL_10;
  if ( pvData )
    *a1 = 1;
LABEL_12:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18004d2c8  push    rbp
0x18004d2ca  push    rbx
0x18004d2cb  push    rdi
0x18004d2cc  mov     rbp, rsp
0x18004d2cf  sub     rsp, 50h
0x18004d2d3  xor     ebx, ebx
0x18004d2d5  mov     rdi, rcx
0x18004d2d8  mov     [rbp+hkey], rbx
0x18004d2dc  mov     [rbp+arg_8], ebx
0x18004d2df  mov     [rbp+pdwType], ebx
0x18004d2e2  mov     [rbp+arg_18], ebx
0x18004d2e5  call    IsIsEmbeddedModeAllowedPresent
0x18004d2ea  test    al, al
0x18004d2ec  jz      short loc_18004D30A
0x18004d2ee  mov     rcx, rdi
0x18004d2f1  call    cs:__imp_IsEmbeddedModeAllowed
0x18004d2f7  mov     ebx, eax
0x18004d2f9  test    eax, eax
0x18004d2fb  js      loc_18004D395
0x18004d301  cmp     dword ptr [rdi], 0
0x18004d304  jnz     loc_18004D395
0x18004d30a  lea     rax, [rbp+hkey]
0x18004d30e  mov     r9d, 20019h; samDesired
0x18004d314  xor     r8d, r8d; ulOptions
0x18004d317  mov     [rsp+50h+phkResult], rax; phkResult
0x18004d31c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Device Association"...
0x18004d323  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d32a  call    cs:__imp_RegOpenKeyExW
0x18004d330  test    eax, eax
0x18004d332  jnz     short loc_18004D386
0x18004d334  mov     rcx, [rbp+hkey]; hkey
0x18004d338  lea     rax, [rbp+arg_8]
0x18004d33c  mov     [rsp+50h+pcbData], rax; pcbData
0x18004d341  lea     r8, aInbound; "Inbound"
0x18004d348  lea     rax, [rbp+arg_18]
0x18004d34c  mov     [rbp+arg_8], 4
0x18004d353  mov     [rsp+50h+pvData], rax; pvData
0x18004d358  mov     r9d, 18h; dwFlags
0x18004d35e  lea     rax, [rbp+pdwType]
0x18004d362  xor     edx, edx; lpSubKey
0x18004d364  mov     [rsp+50h+phkResult], rax; pdwType
0x18004d369  call    cs:__imp_RegGetValueW
0x18004d36f  test    eax, eax
0x18004d371  jnz     short loc_18004D386
0x18004d373  cmp     [rbp+pdwType], 4
0x18004d377  jnz     short loc_18004D388
0x18004d379  cmp     [rbp+arg_18], eax
0x18004d37c  jz      short loc_18004D395
0x18004d37e  mov     dword ptr [rdi], 1
0x18004d384  jmp     short loc_18004D395
0x18004d386  jg      short loc_18004D38C
0x18004d388  mov     ebx, eax
0x18004d38a  jmp     short loc_18004D395
0x18004d38c  movzx   ebx, ax
0x18004d38f  or      ebx, 80070000h
0x18004d395  mov     rcx, [rbp+hkey]; hKey
0x18004d399  test    rcx, rcx
0x18004d39c  jz      short loc_18004D3A4
0x18004d39e  call    cs:__imp_RegCloseKey
0x18004d3a4  mov     eax, ebx
0x18004d3a6  add     rsp, 50h
0x18004d3aa  pop     rdi
0x18004d3ab  pop     rbx
0x18004d3ac  pop     rbp
0x18004d3ad  retn
```
