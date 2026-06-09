# CheckForServerAdminUI(void)

- ea: `0x140090720`
- end: `0x1400908ce`
- name: `?CheckForServerAdminUI@@YAXXZ`
- size: `430`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400a3f04`

## callees

- `0x140020dfc`
- `0x140090720`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x140090882`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1400908b8`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x140090882`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1400908b8`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x140090768`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x140090846`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x140090768`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x140090846`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x140090783`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x140090783`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14009079e`
- `SHELL32!__imp_SHTestTokenMembership` at `0x1400907b5`
- `SHELL32!__imp_SHTestTokenMembership` at `0x1400907cc`
- `SHELL32!__imp_SHTestTokenMembership` at `0x1400907e3`
- `SHELL32!__imp_SHTestTokenMembership` at `0x14009079e`
- `SHELL32!__imp_SHTestTokenMembership` at `0x1400907b5`
- `SHELL32!__imp_SHTestTokenMembership` at `0x1400907cc`
- `SHELL32!__imp_SHTestTokenMembership` at `0x1400907e3`

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
0x140090720  push    rbp
0x140090722  push    rdi
0x140090723  push    r15
0x140090725  mov     rbp, rsp
0x140090728  sub     rsp, 30h
0x14009072c  lea     rax, [rbp+arg_8]
0x140090730  mov     [rbp+arg_0], 0
0x140090737  mov     [rsp+30h+pcbData], rax; pcbData
0x14009073c  lea     r8, aServeradminui; "ServerAdminUI"
0x140090743  lea     rax, [rbp+arg_0]
0x140090747  mov     r15, 0FFFFFFFF80000001h
0x14009074e  mov     edi, 4
0x140090753  mov     [rsp+30h+pvData], rax; pvData
0x140090758  xor     r9d, r9d; pdwType
0x14009075b  mov     [rbp+arg_8], edi
0x14009075e  lea     rdx, aSoftwareMicros_127; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140090765  mov     rcx, r15; hkey
0x140090768  call    cs:__imp_SHGetValueW
0x14009076f  nop     dword ptr [rax+rax+00h]
0x140090774  add     eax, 0FFFFFFFEh
0x140090777  cmp     eax, 1
0x14009077a  ja      loc_1400908C4
0x140090780  lea     ecx, [rdi+19h]; dwOS
0x140090783  call    cs:__imp_IsOS
0x14009078a  nop     dword ptr [rax+rax+00h]
0x14009078f  test    eax, eax
0x140090791  jz      loc_140090890
0x140090797  mov     edx, 220h; ulRID
0x14009079c  xor     ecx, ecx; hToken
0x14009079e  call    cs:__imp_SHTestTokenMembership
0x1400907a5  nop     dword ptr [rax+rax+00h]
0x1400907aa  test    eax, eax
0x1400907ac  jnz     short loc_14009080F
0x1400907ae  mov     edx, 225h; ulRID
0x1400907b3  xor     ecx, ecx; hToken
0x1400907b5  call    cs:__imp_SHTestTokenMembership
0x1400907bc  nop     dword ptr [rax+rax+00h]
0x1400907c1  test    eax, eax
0x1400907c3  jnz     short loc_14009080F
0x1400907c5  mov     edx, 227h; ulRID
0x1400907ca  xor     ecx, ecx; hToken
0x1400907cc  call    cs:__imp_SHTestTokenMembership
0x1400907d3  nop     dword ptr [rax+rax+00h]
0x1400907d8  test    eax, eax
0x1400907da  jnz     short loc_14009080F
0x1400907dc  mov     edx, 22Ch; ulRID
0x1400907e1  xor     ecx, ecx; hToken
0x1400907e3  call    cs:__imp_SHTestTokenMembership
0x1400907ea  nop     dword ptr [rax+rax+00h]
0x1400907ef  test    eax, eax
0x1400907f1  jnz     short loc_14009080F
0x1400907f3  lea     rdx, [rbp+arg_10]
0x1400907f7  mov     [rbp+arg_0], eax
0x1400907fa  mov     [rbp+arg_10], eax
0x1400907fd  call    LUAGetUserType
0x140090802  test    eax, eax
0x140090804  jnz     short loc_140090816
0x140090806  test    [rbp+arg_10], 0FFFFFFEEh
0x14009080d  jnz     short loc_140090816
0x14009080f  mov     [rbp+arg_0], 1
0x140090816  lea     rax, [rbp+arg_8]
0x14009081a  mov     [rbp+arg_18], 0
0x140090821  mov     [rsp+30h+pcbData], rax; pcbData
0x140090826  lea     r8, aStartmenuadmin; "StartMenuAdminTools"
0x14009082d  lea     rax, [rbp+arg_18]
0x140090831  mov     [rbp+arg_8], edi
0x140090834  xor     r9d, r9d; pdwType
0x140090837  mov     [rsp+30h+pvData], rax; pvData
0x14009083c  lea     rdx, aSoftwareMicros_127; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140090843  mov     rcx, r15; hkey
0x140090846  call    cs:__imp_SHGetValueW
0x14009084d  nop     dword ptr [rax+rax+00h]
0x140090852  add     eax, 0FFFFFFFEh
0x140090855  cmp     eax, 1
0x140090858  ja      short loc_140090897
0x14009085a  lea     rax, [rbp+arg_10]
0x14009085e  mov     dword ptr [rsp+30h+pcbData], edi; cbData
0x140090862  mov     r9d, edi; dwType
0x140090865  mov     [rsp+30h+pvData], rax; pvData
0x14009086a  lea     r8, aStartmenuadmin; "StartMenuAdminTools"
0x140090871  mov     [rbp+arg_10], 1
0x140090878  lea     rdx, aSoftwareMicros_127; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14009087f  mov     rcx, r15; hkey
0x140090882  call    cs:__imp_SHSetValueW
0x140090889  nop     dword ptr [rax+rax+00h]
0x14009088e  jmp     short loc_140090897
0x140090890  mov     [rbp+arg_0], 0
0x140090897  lea     rax, [rbp+arg_0]
0x14009089b  mov     dword ptr [rsp+30h+pcbData], edi; cbData
0x14009089f  mov     r9d, edi; dwType
0x1400908a2  mov     [rsp+30h+pvData], rax; pvData
0x1400908a7  lea     r8, aServeradminui; "ServerAdminUI"
0x1400908ae  mov     rcx, r15; hkey
0x1400908b1  lea     rdx, aSoftwareMicros_127; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400908b8  call    cs:__imp_SHSetValueW
0x1400908bf  nop     dword ptr [rax+rax+00h]
0x1400908c4  add     rsp, 30h
0x1400908c8  pop     r15
0x1400908ca  pop     rdi
0x1400908cb  pop     rbp
0x1400908cc  retn
```
