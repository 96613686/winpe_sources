# CheckForServerAdminUI(void)

- ea: `0x14008b158`
- end: `0x14008b2cf`
- name: `?CheckForServerAdminUI@@YAXXZ`
- size: `375`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14009ae00`

## callees

- `0x140012bf8`
- `0x14008b158`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x14008b290`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x14008b2c0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x14008b290`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x14008b2c0`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x14008b1a0`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x14008b25a`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x14008b1a0`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x14008b25a`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14008b1b5`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14008b1b5`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1ca`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1db`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1ec`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1fd`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1ca`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1db`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1ec`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14008b1fd`

## pseudocode

```c
void CheckForServerAdminUI(void)
{
  __int64 v0; // rcx
  int pvData; // [rsp+50h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+28h] BYREF
  int v3; // [rsp+60h] [rbp+30h] BYREF
  int v4; // [rsp+68h] [rbp+38h] BYREF

  pvData = 0;
  pcbData = 4;
  if ( (unsigned int)(SHGetValueW(
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
                        L"ServerAdminUI",
                        0,
                        &pvData,
                        &pcbData)
                    - 2) <= 1 )
  {
    if ( IsOS(0x1Du) )
    {
      if ( SHTestTokenMembership(0, 0x220u)
        || SHTestTokenMembership(0, 0x225u)
        || SHTestTokenMembership(0, 0x227u)
        || SHTestTokenMembership(0, 0x22Cu)
        || (pvData = 0, v3 = 0, !(unsigned int)LUAGetUserType(v0, &v3)) && (v3 & 0xFFFFFFEE) == 0 )
      {
        pvData = 1;
      }
      v4 = 0;
      pcbData = 4;
      if ( (unsigned int)(SHGetValueW(
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
                            L"StartMenuAdminTools",
                            0,
                            &v4,
                            &pcbData)
                        - 2) <= 1 )
      {
        v3 = 1;
        SHSetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
          L"StartMenuAdminTools",
          4u,
          &v3,
          4u);
      }
    }
    else
    {
      pvData = 0;
    }
    SHSetValueW(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
      L"ServerAdminUI",
      4u,
      &pvData,
      4u);
  }
}

```

## disassembly

```asm
0x14008b158  push    rbp
0x14008b15a  push    rdi
0x14008b15b  push    r15
0x14008b15d  mov     rbp, rsp
0x14008b160  sub     rsp, 30h
0x14008b164  lea     rax, [rbp+arg_8]
0x14008b168  mov     [rbp+arg_0], 0
0x14008b16f  mov     [rsp+30h+pcbData], rax; pcbData
0x14008b174  lea     r8, aServeradminui; "ServerAdminUI"
0x14008b17b  lea     rax, [rbp+arg_0]
0x14008b17f  mov     r15, 0FFFFFFFF80000001h
0x14008b186  mov     edi, 4
0x14008b18b  mov     [rsp+30h+pvData], rax; pvData
0x14008b190  xor     r9d, r9d; pdwType
0x14008b193  mov     [rbp+arg_8], edi
0x14008b196  lea     rdx, aSoftwareMicros_126; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14008b19d  mov     rcx, r15; hkey
0x14008b1a0  call    cs:__imp_SHGetValueW
0x14008b1a6  add     eax, 0FFFFFFFEh
0x14008b1a9  cmp     eax, 1
0x14008b1ac  ja      loc_14008B2C6
0x14008b1b2  lea     ecx, [rdi+19h]; dwOS
0x14008b1b5  call    cs:__imp_IsOS
0x14008b1bb  test    eax, eax
0x14008b1bd  jz      loc_14008B298
0x14008b1c3  mov     edx, 220h; ulRID
0x14008b1c8  xor     ecx, ecx; hToken
0x14008b1ca  call    cs:__imp_SHTestTokenMembership
0x14008b1d0  test    eax, eax
0x14008b1d2  jnz     short loc_14008B223
0x14008b1d4  mov     edx, 225h; ulRID
0x14008b1d9  xor     ecx, ecx; hToken
0x14008b1db  call    cs:__imp_SHTestTokenMembership
0x14008b1e1  test    eax, eax
0x14008b1e3  jnz     short loc_14008B223
0x14008b1e5  mov     edx, 227h; ulRID
0x14008b1ea  xor     ecx, ecx; hToken
0x14008b1ec  call    cs:__imp_SHTestTokenMembership
0x14008b1f2  test    eax, eax
0x14008b1f4  jnz     short loc_14008B223
0x14008b1f6  mov     edx, 22Ch; ulRID
0x14008b1fb  xor     ecx, ecx; hToken
0x14008b1fd  call    cs:__imp_SHTestTokenMembership
0x14008b203  test    eax, eax
0x14008b205  jnz     short loc_14008B223
0x14008b207  lea     rdx, [rbp+arg_10]
0x14008b20b  mov     [rbp+arg_0], eax
0x14008b20e  mov     [rbp+arg_10], eax
0x14008b211  call    LUAGetUserType
0x14008b216  test    eax, eax
0x14008b218  jnz     short loc_14008B22A
0x14008b21a  test    [rbp+arg_10], 0FFFFFFEEh
0x14008b221  jnz     short loc_14008B22A
0x14008b223  mov     [rbp+arg_0], 1
0x14008b22a  lea     rax, [rbp+arg_8]
0x14008b22e  mov     [rbp+arg_18], 0
0x14008b235  mov     [rsp+30h+pcbData], rax; pcbData
0x14008b23a  lea     r8, aStartmenuadmin; "StartMenuAdminTools"
0x14008b241  lea     rax, [rbp+arg_18]
0x14008b245  mov     [rbp+arg_8], edi
0x14008b248  xor     r9d, r9d; pdwType
0x14008b24b  mov     [rsp+30h+pvData], rax; pvData
0x14008b250  lea     rdx, aSoftwareMicros_126; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14008b257  mov     rcx, r15; hkey
0x14008b25a  call    cs:__imp_SHGetValueW
0x14008b260  add     eax, 0FFFFFFFEh
0x14008b263  cmp     eax, 1
0x14008b266  ja      short loc_14008B29F
0x14008b268  lea     rax, [rbp+arg_10]
0x14008b26c  mov     dword ptr [rsp+30h+pcbData], edi; cbData
0x14008b270  mov     r9d, edi; dwType
0x14008b273  mov     [rsp+30h+pvData], rax; pvData
0x14008b278  lea     r8, aStartmenuadmin; "StartMenuAdminTools"
0x14008b27f  mov     [rbp+arg_10], 1
0x14008b286  lea     rdx, aSoftwareMicros_126; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14008b28d  mov     rcx, r15; hkey
0x14008b290  call    cs:__imp_SHSetValueW
0x14008b296  jmp     short loc_14008B29F
0x14008b298  mov     [rbp+arg_0], 0
0x14008b29f  lea     rax, [rbp+arg_0]
0x14008b2a3  mov     dword ptr [rsp+30h+pcbData], edi; cbData
0x14008b2a7  mov     r9d, edi; dwType
0x14008b2aa  mov     [rsp+30h+pvData], rax; pvData
0x14008b2af  lea     r8, aServeradminui; "ServerAdminUI"
0x14008b2b6  mov     rcx, r15; hkey
0x14008b2b9  lea     rdx, aSoftwareMicros_126; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14008b2c0  call    cs:__imp_SHSetValueW
0x14008b2c6  add     rsp, 30h
0x14008b2ca  pop     r15
0x14008b2cc  pop     rdi
0x14008b2cd  pop     rbp
0x14008b2ce  retn
```
