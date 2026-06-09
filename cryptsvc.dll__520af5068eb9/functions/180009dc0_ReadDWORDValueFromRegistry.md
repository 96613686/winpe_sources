# _ReadDWORDValueFromRegistry

- ea: `0x180009dc0`
- end: `0x180009e3e`
- name: `_ReadDWORDValueFromRegistry`
- size: `126`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005bd0`

## callees

- `0x180009dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009e07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009e07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009dfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009dfb`

## pseudocode

```c
__int64 __fastcall ReadDWORDValueFromRegistry(HKEY a1, const WCHAR *a2, _DWORD *a3)
{
  LSTATUS v4; // eax
  DWORD v5; // ecx
  __int64 result; // rax
  BYTE Data[24]; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  cbData = 4;
  Type = 0;
  *(_DWORD *)Data = 0;
  v4 = RegQueryValueExW(a1, a2, 0, &Type, Data, &cbData);
  if ( v4 )
  {
    v5 = v4;
LABEL_3:
    SetLastError(v5);
    result = 0;
    *a3 = 0;
    return result;
  }
  if ( Type != 4 || cbData != 4 )
  {
    v5 = 13;
    goto LABEL_3;
  }
  result = 1;
  *a3 = *(_DWORD *)Data;
  return result;
}

```

## disassembly

```asm
0x180009dc0  mov     [rsp+arg_0], rbx
0x180009dc5  push    rdi
0x180009dc6  sub     rsp, 40h
0x180009dca  lea     rax, [rsp+48h+cbData]
0x180009dcf  mov     [rsp+48h+cbData], 4
0x180009dd7  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180009ddc  lea     r9, [rsp+48h+Type]; lpType
0x180009de1  lea     rax, [rsp+48h+Data]
0x180009de6  mov     rbx, r8
0x180009de9  xor     edi, edi
0x180009deb  mov     [rsp+48h+lpData], rax; lpData
0x180009df0  xor     r8d, r8d; lpReserved
0x180009df3  mov     [rsp+48h+Type], edi
0x180009df7  mov     dword ptr [rsp+48h+Data], edi
0x180009dfb  call    cs:__imp_RegQueryValueExW
0x180009e01  test    eax, eax
0x180009e03  jz      short loc_180009E1C
0x180009e05  mov     ecx, eax; dwErrCode
0x180009e07  call    cs:__imp_SetLastError
0x180009e0d  mov     eax, edi
0x180009e0f  mov     [rbx], edi
0x180009e11  mov     rbx, [rsp+48h+arg_0]
0x180009e16  add     rsp, 40h
0x180009e1a  pop     rdi
0x180009e1b  retn
0x180009e1c  cmp     [rsp+48h+Type], 4
0x180009e21  jnz     short loc_180009E37
0x180009e23  cmp     [rsp+48h+cbData], 4
0x180009e28  jnz     short loc_180009E37
0x180009e2a  mov     ecx, dword ptr [rsp+48h+Data]
0x180009e2e  mov     eax, 1
0x180009e33  mov     [rbx], ecx
0x180009e35  jmp     short loc_180009E11
0x180009e37  mov     ecx, 0Dh
0x180009e3c  jmp     short loc_180009E07
```
