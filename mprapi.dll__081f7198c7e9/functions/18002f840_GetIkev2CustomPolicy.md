# GetIkev2CustomPolicy

- ea: `0x18002f840`
- end: `0x18002f8c4`
- name: `GetIkev2CustomPolicy`
- size: `132`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021e38`
- `0x18002efac`

## callees

- `0x18002ee38`
- `0x18002f840`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f8b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f8b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f887`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f887`

## pseudocode

```c
__int64 __fastcall GetIkev2CustomPolicy(HKEY hKey, __int64 a2, __int64 a3, __int64 a4)
{
  HKEY v6; // rcx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  HKEY v10; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
  v10 = 0;
  if ( a4 && a2 && a3 && hKey )
  {
    v7 = RegOpenKeyExW(hKey, L"IKEv2CustomPolicy", 0, 0x20019u, &v10);
    v6 = v10;
    v8 = v7;
    if ( !v7 )
    {
      GetCustomPolicyRegParams(v10, a4);
      v6 = v10;
    }
  }
  else
  {
    v8 = 87;
  }
  if ( v6 )
    RegCloseKey(v6);
  return v8;
}

```

## disassembly

```asm
0x18002f840  mov     r11, rsp
0x18002f843  mov     [r11+8], rbx
0x18002f847  push    rdi
0x18002f848  sub     rsp, 30h
0x18002f84c  mov     rax, rcx
0x18002f84f  mov     rdi, r9
0x18002f852  xor     ecx, ecx; hKey
0x18002f854  mov     [r11+20h], rcx
0x18002f858  test    r9, r9
0x18002f85b  jz      short loc_18002F8A7
0x18002f85d  test    rdx, rdx
0x18002f860  jz      short loc_18002F8A7
0x18002f862  test    r8, r8
0x18002f865  jz      short loc_18002F8A7
0x18002f867  test    rax, rax
0x18002f86a  jz      short loc_18002F8A7
0x18002f86c  lea     rcx, [r11+20h]
0x18002f870  mov     r9d, 20019h; samDesired
0x18002f876  mov     [r11-18h], rcx
0x18002f87a  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x18002f881  mov     rcx, rax; hKey
0x18002f884  xor     r8d, r8d; ulOptions
0x18002f887  call    cs:__imp_RegOpenKeyExW
0x18002f88d  mov     rcx, [rsp+38h+arg_18]
0x18002f892  mov     ebx, eax
0x18002f894  test    eax, eax
0x18002f896  jnz     short loc_18002F8AC
0x18002f898  mov     rdx, rdi
0x18002f89b  call    GetCustomPolicyRegParams
0x18002f8a0  mov     rcx, [rsp+38h+arg_18]
0x18002f8a5  jmp     short loc_18002F8AC
0x18002f8a7  mov     ebx, 57h ; 'W'
0x18002f8ac  test    rcx, rcx
0x18002f8af  jz      short loc_18002F8B7
0x18002f8b1  call    cs:__imp_RegCloseKey
0x18002f8b7  mov     eax, ebx
0x18002f8b9  mov     rbx, [rsp+38h+arg_0]
0x18002f8be  add     rsp, 30h
0x18002f8c2  pop     rdi
0x18002f8c3  retn
```
