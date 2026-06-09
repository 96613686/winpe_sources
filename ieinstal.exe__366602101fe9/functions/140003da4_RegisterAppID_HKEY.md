# RegisterAppID(HKEY__ *)

- ea: `0x140003da4`
- end: `0x140003e9c`
- name: `?RegisterAppID@@YAKPEAUHKEY__@@@Z`
- size: `248`
- prototype: `unsigned int __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000c498`

## callees

- `0x140001af3`
- `0x140003da4`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140003de9`
- `ADVAPI32!RegDeleteValueW` at `0x140003de9`
- `ADVAPI32!RegSetValueExW` at `0x140003e60`
- `ADVAPI32!RegSetValueExW` at `0x140003e60`
- `KERNEL32!GetModuleHandleW` at `0x140003df7`
- `KERNEL32!GetModuleHandleW` at `0x140003df7`
- `KERNEL32!GetLastError` at `0x140003e6e`
- `KERNEL32!GetLastError` at `0x140003e6e`
- `USER32!LoadStringW` at `0x140003e16`
- `USER32!LoadStringW` at `0x140003e16`

## pseudocode

```c
LSTATUS __fastcall RegisterAppID(HKEY hKey)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rax
  WCHAR Buffer; // [rsp+30h] [rbp-218h] BYREF
  _BYTE v6[510]; // [rsp+32h] [rbp-216h] BYREF

  Buffer = 0;
  memset_0(v6, 0, sizeof(v6));
  RegDeleteValueW(hKey, L"RunAs");
  ModuleHandleW = GetModuleHandleW(0);
  if ( LoadStringW(ModuleHandleW, 0x3E9u, &Buffer, 256) <= 0 )
    return GetLastError();
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&v6[2 * v3 - 2] );
  return RegSetValueExW(hKey, &Data, 0, 1u, (const BYTE *)&Buffer, 2 * v3 + 2);
}

```

## disassembly

```asm
0x140003da4  mov     [rsp+arg_8], rbx
0x140003da9  push    rdi
0x140003daa  sub     rsp, 240h
0x140003db1  mov     rax, cs:__security_cookie
0x140003db8  xor     rax, rsp
0x140003dbb  mov     [rsp+248h+var_18], rax
0x140003dc3  mov     rbx, rcx
0x140003dc6  xor     edi, edi
0x140003dc8  lea     rcx, [rsp+248h+var_216]; void *
0x140003dcd  mov     [rsp+248h+Buffer], di
0x140003dd2  xor     edx, edx; Val
0x140003dd4  mov     r8d, 1FEh; Size
0x140003dda  call    memset_0
0x140003ddf  lea     rdx, ValueName; "RunAs"
0x140003de6  mov     rcx, rbx; hKey
0x140003de9  call    cs:__imp_RegDeleteValueW
0x140003df0  nop     dword ptr [rax+rax+00h]
0x140003df5  xor     ecx, ecx; lpModuleName
0x140003df7  call    cs:__imp_GetModuleHandleW
0x140003dfe  nop     dword ptr [rax+rax+00h]
0x140003e03  mov     r9d, 100h; cchBufferMax
0x140003e09  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x140003e0e  mov     rcx, rax; hInstance
0x140003e11  mov     edx, 3E9h; uID
0x140003e16  call    cs:__imp_LoadStringW
0x140003e1d  nop     dword ptr [rax+rax+00h]
0x140003e22  test    eax, eax
0x140003e24  jle     short loc_140003E6E
0x140003e26  lea     rcx, [rsp+248h+Buffer]
0x140003e2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003e2f  inc     rax
0x140003e32  cmp     [rcx+rax*2], di
0x140003e36  jnz     short loc_140003E2F
0x140003e38  lea     eax, ds:2[rax*2]
0x140003e3f  mov     r9d, 1; dwType
0x140003e45  mov     [rsp+248h+cbData], eax; cbData
0x140003e49  lea     rdx, Data; lpValueName
0x140003e50  lea     rax, [rsp+248h+Buffer]
0x140003e55  xor     r8d, r8d; Reserved
0x140003e58  mov     rcx, rbx; hKey
0x140003e5b  mov     [rsp+248h+lpData], rax; lpData
0x140003e60  call    cs:__imp_RegSetValueExW
0x140003e67  nop     dword ptr [rax+rax+00h]
0x140003e6c  jmp     short loc_140003E7A
0x140003e6e  call    cs:__imp_GetLastError
0x140003e75  nop     dword ptr [rax+rax+00h]
0x140003e7a  mov     rcx, [rsp+248h+var_18]
0x140003e82  xor     rcx, rsp; StackCookie
0x140003e85  call    __security_check_cookie
0x140003e8a  mov     rbx, [rsp+248h+arg_8]
0x140003e92  add     rsp, 240h
0x140003e99  pop     rdi
0x140003e9a  retn
```
