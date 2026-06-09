# SetL2tpConfigParams

- ea: `0x180077c70`
- end: `0x180077e26`
- name: `SetL2tpConfigParams`
- size: `438`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005bc0`

## callees

- `0x180077c70`
- `0x180077e2c`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180077d41`
- `ADVAPI32!RegSetValueExW` at `0x180077d87`
- `ADVAPI32!RegSetValueExW` at `0x180077ded`
- `ADVAPI32!RegSetValueExW` at `0x180077d41`
- `ADVAPI32!RegSetValueExW` at `0x180077d87`
- `ADVAPI32!RegSetValueExW` at `0x180077ded`
- `ADVAPI32!RegDeleteKeyExW` at `0x180077dc7`
- `ADVAPI32!RegDeleteKeyExW` at `0x180077dc7`

## pseudocode

```c
__int64 __fastcall SetL2tpConfigParams(HKEY hKey, char a2, __int64 a3)
{
  __int64 v5; // r9
  const BYTE *lpData; // r14
  int v8; // ebp
  LPCWSTR *i; // rsi
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  _QWORD v15[6]; // [rsp+30h] [rbp-68h] BYREF

  v15[0] = L"idleTimeout";
  v15[1] = a3;
  v15[2] = L"saLifeTime";
  LODWORD(v5) = 0;
  v15[3] = a3 + 8;
  v15[4] = L"saDataSize";
  v15[5] = a3 + 12;
  if ( a2 != 1 && a2 != 2 )
  {
    if ( a2 == 3 || (unsigned int)(a2 - 4) < 2 )
    {
      lpData = (const BYTE *)(a3 + 4);
      if ( *(_DWORD *)(a3 + 4) <= 3u )
      {
        v8 = 0;
        for ( i = (LPCWSTR *)v15; ; i += 2 )
        {
          v10 = RegSetValueExW(hKey, *i, 0, 4u, (const BYTE *)i[1], 4u);
          v5 = v10;
          if ( v10 )
            break;
          if ( (unsigned int)++v8 >= 3 )
          {
            if ( a2 < 5
              || (v12 = RegSetValueExW(hKey, L"mmSaLifeTime", 0, 4u, (const BYTE *)(a3 + 24), 4u), (v5 = v12) == 0) )
            {
              if ( a2 >= 3 )
              {
                v13 = *(_QWORD *)(a3 + 16);
                if ( v13 )
                {
                  LODWORD(v5) = SetL2tpCustomPolicy(hKey, v13, v11, v5);
                  if ( (_DWORD)v5 )
                    return (unsigned int)v5;
                }
                else
                {
                  RegDeleteKeyExW(hKey, L"L2TPCustomPolicy", 0, 0);
                }
                LODWORD(v5) = RegSetValueExW(hKey, L"EncryptionType", 0, 4u, lpData, 4u);
              }
            }
            return (unsigned int)v5;
          }
        }
      }
      else
      {
        LODWORD(v5) = 87;
      }
    }
    else
    {
      LODWORD(v5) = 50;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180077c70  mov     r11, rsp
0x180077c73  mov     [r11+10h], rbx
0x180077c77  mov     [r11+20h], rbp
0x180077c7b  push    rsi
0x180077c7c  push    rdi
0x180077c7d  push    r12
0x180077c7f  push    r14
0x180077c81  push    r15
0x180077c83  sub     rsp, 70h
0x180077c87  mov     rax, cs:__security_cookie
0x180077c8e  xor     rax, rsp
0x180077c91  mov     [rsp+98h+var_38], rax
0x180077c96  lea     rax, aIdletimeout; "idleTimeout"
0x180077c9d  movsx   r15d, dl
0x180077ca1  mov     [r11-68h], rax
0x180077ca5  mov     rbx, rcx
0x180077ca8  lea     rax, aSalifetime; "saLifeTime"
0x180077caf  mov     [r11-60h], r8
0x180077cb3  mov     [r11-58h], rax
0x180077cb7  xor     r9d, r9d
0x180077cba  lea     rax, [r8+8]
0x180077cbe  mov     ecx, r15d
0x180077cc1  mov     [r11-50h], rax
0x180077cc5  lea     rax, aSadatasize; "saDataSize"
0x180077ccc  mov     [r11-48h], rax
0x180077cd0  lea     rax, [r8+0Ch]
0x180077cd4  mov     [r11-40h], rax
0x180077cd8  mov     rdi, r8
0x180077cdb  sub     ecx, 1
0x180077cde  jz      loc_180077DFC
0x180077ce4  sub     ecx, 1
0x180077ce7  jz      loc_180077DFC
0x180077ced  sub     ecx, 1
0x180077cf0  jz      short loc_180077D07
0x180077cf2  sub     ecx, 1
0x180077cf5  jz      short loc_180077D07
0x180077cf7  cmp     ecx, 1
0x180077cfa  jz      short loc_180077D07
0x180077cfc  mov     r9d, 32h ; '2'
0x180077d02  jmp     loc_180077DFC
0x180077d07  lea     r14, [r8+4]
0x180077d0b  cmp     dword ptr [r14], 3
0x180077d0f  jbe     short loc_180077D1C
0x180077d11  mov     r9d, 57h ; 'W'
0x180077d17  jmp     loc_180077DFC
0x180077d1c  xor     ebp, ebp
0x180077d1e  lea     rsi, [rsp+98h+var_68]
0x180077d23  lea     r12d, [rbp+4]
0x180077d27  mov     rax, [rsi+8]
0x180077d2b  mov     r9d, r12d; dwType
0x180077d2e  mov     rdx, [rsi]; lpValueName
0x180077d31  xor     r8d, r8d; Reserved
0x180077d34  mov     [rsp+98h+cbData], r12d; cbData
0x180077d39  mov     rcx, rbx; hKey
0x180077d3c  mov     [rsp+98h+lpData], rax; lpData
0x180077d41  call    cs:__imp_RegSetValueExW
0x180077d48  nop     dword ptr [rax+rax+00h]
0x180077d4d  mov     r9d, eax
0x180077d50  test    eax, eax
0x180077d52  jnz     loc_180077DFC
0x180077d58  inc     ebp
0x180077d5a  add     rsi, 10h
0x180077d5e  cmp     ebp, 3
0x180077d61  jb      short loc_180077D27
0x180077d63  cmp     r15b, 5
0x180077d67  jl      short loc_180077D9A
0x180077d69  lea     rax, [rdi+18h]
0x180077d6d  mov     [rsp+98h+cbData], r12d; cbData
0x180077d72  mov     r9d, r12d; dwType
0x180077d75  mov     [rsp+98h+lpData], rax; lpData
0x180077d7a  xor     r8d, r8d; Reserved
0x180077d7d  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180077d84  mov     rcx, rbx; hKey
0x180077d87  call    cs:__imp_RegSetValueExW
0x180077d8e  nop     dword ptr [rax+rax+00h]
0x180077d93  mov     r9d, eax
0x180077d96  test    eax, eax
0x180077d98  jnz     short loc_180077DFC
0x180077d9a  cmp     r15b, 3
0x180077d9e  jl      short loc_180077DFC
0x180077da0  mov     rdx, [rdi+10h]
0x180077da4  mov     rcx, rbx; hKey
0x180077da7  test    rdx, rdx
0x180077daa  jz      short loc_180077DBA
0x180077dac  call    SetL2tpCustomPolicy
0x180077db1  mov     r9d, eax
0x180077db4  test    eax, eax
0x180077db6  jnz     short loc_180077DFC
0x180077db8  jmp     short loc_180077DD3
0x180077dba  xor     r9d, r9d; Reserved
0x180077dbd  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180077dc4  xor     r8d, r8d; samDesired
0x180077dc7  call    cs:__imp_RegDeleteKeyExW
0x180077dce  nop     dword ptr [rax+rax+00h]
0x180077dd3  mov     [rsp+98h+cbData], r12d; cbData
0x180077dd8  lea     rdx, aEncryptiontype; "EncryptionType"
0x180077ddf  mov     r9d, r12d; dwType
0x180077de2  mov     [rsp+98h+lpData], r14; lpData
0x180077de7  xor     r8d, r8d; Reserved
0x180077dea  mov     rcx, rbx; hKey
0x180077ded  call    cs:__imp_RegSetValueExW
0x180077df4  nop     dword ptr [rax+rax+00h]
0x180077df9  mov     r9d, eax
0x180077dfc  mov     eax, r9d
0x180077dff  mov     rcx, [rsp+98h+var_38]
0x180077e04  xor     rcx, rsp; StackCookie
0x180077e07  call    __security_check_cookie
0x180077e0c  lea     r11, [rsp+98h+var_28]
0x180077e11  mov     rbx, [r11+38h]
0x180077e15  mov     rbp, [r11+48h]
0x180077e19  mov     rsp, r11
0x180077e1c  pop     r15
0x180077e1e  pop     r14
0x180077e20  pop     r12
0x180077e22  pop     rdi
0x180077e23  pop     rsi
0x180077e24  retn
```
