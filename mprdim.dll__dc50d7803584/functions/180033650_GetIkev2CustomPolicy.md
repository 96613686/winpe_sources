# GetIkev2CustomPolicy

- ea: `0x180033650`
- end: `0x1800336d4`
- name: `GetIkev2CustomPolicy`
- size: `132`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800165cc`
- `0x180032e84`

## callees

- `0x180032d10`
- `0x180033650`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180033697`
- `ADVAPI32!RegOpenKeyExW` at `0x180033697`
- `ADVAPI32!RegCloseKey` at `0x1800336c1`
- `ADVAPI32!RegCloseKey` at `0x1800336c1`

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
0x180033650  mov     r11, rsp
0x180033653  mov     [r11+8], rbx
0x180033657  push    rdi
0x180033658  sub     rsp, 30h
0x18003365c  mov     rax, rcx
0x18003365f  mov     rdi, r9
0x180033662  xor     ecx, ecx; hKey
0x180033664  mov     [r11+20h], rcx
0x180033668  test    r9, r9
0x18003366b  jz      short loc_1800336B7
0x18003366d  test    rdx, rdx
0x180033670  jz      short loc_1800336B7
0x180033672  test    r8, r8
0x180033675  jz      short loc_1800336B7
0x180033677  test    rax, rax
0x18003367a  jz      short loc_1800336B7
0x18003367c  lea     rcx, [r11+20h]
0x180033680  mov     r9d, 20019h; samDesired
0x180033686  mov     [r11-18h], rcx
0x18003368a  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x180033691  mov     rcx, rax; hKey
0x180033694  xor     r8d, r8d; ulOptions
0x180033697  call    cs:__imp_RegOpenKeyExW
0x18003369d  mov     rcx, [rsp+38h+arg_18]
0x1800336a2  mov     ebx, eax
0x1800336a4  test    eax, eax
0x1800336a6  jnz     short loc_1800336BC
0x1800336a8  mov     rdx, rdi
0x1800336ab  call    GetCustomPolicyRegParams
0x1800336b0  mov     rcx, [rsp+38h+arg_18]
0x1800336b5  jmp     short loc_1800336BC
0x1800336b7  mov     ebx, 57h ; 'W'
0x1800336bc  test    rcx, rcx
0x1800336bf  jz      short loc_1800336C7
0x1800336c1  call    cs:__imp_RegCloseKey
0x1800336c7  mov     eax, ebx
0x1800336c9  mov     rbx, [rsp+38h+arg_0]
0x1800336ce  add     rsp, 30h
0x1800336d2  pop     rdi
0x1800336d3  retn
```
