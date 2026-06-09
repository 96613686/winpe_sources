# WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)

- ea: `0x18005cb48`
- end: `0x18005ccb1`
- name: `?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z`
- size: `361`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, REGSAM samDesired@<r8d>, int@<r9d>, HKEY *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005c2ac`
- `0x18005cd90`
- `0x1800c4440`
- `0x1800c49ec`
- `0x1800c51f4`
- `0x1800c59e4`

## callees

- `0x18005cb48`
- `0x18008b5f0`
- `0x1800dc9e0`
- `0x1800e23dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cc81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cc81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cc18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005cc18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005cbcb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005cbcb`

## pseudocode

```c
__int64 __fastcall WxOpenRegistryKey(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, int a4, HKEY *a5)
{
  LSTATUS v9; // eax
  int v10; // ebx
  bool v11; // sf
  HKEY v12; // rcx
  HKEY hKeya; // [rsp+58h] [rbp-40h] BYREF

  hKeya = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_qSDlq(
      (_DWORD)hKey,
      (_DWORD)lpSubKey,
      samDesired,
      (_DWORD)hKey,
      (__int64)lpSubKey,
      samDesired,
      a4,
      (__int64)a5);
  *a5 = 0;
  v9 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, &hKeya);
  v10 = v9;
  if ( a4 && v9 == 2 )
    v10 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &hKeya, 0);
  v11 = v10 < 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v11 = v10 < 0;
  }
  if ( v11 )
  {
    v12 = hKeya;
  }
  else
  {
    v12 = 0;
    *a5 = hKeya;
    hKeya = 0;
  }
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
  {
    WPP_SF_d(1053, 11, WPP_b64a873b5a0a3123360afb44b8058dda_Traceguids, (unsigned int)v10);
    v12 = hKeya;
  }
  if ( v12 )
    RegCloseKey(v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005cb48  mov     r11, rsp
0x18005cb4b  mov     [r11+20h], rbx
0x18005cb4f  push    rbp
0x18005cb50  push    rsi
0x18005cb51  push    rdi
0x18005cb52  push    r14
0x18005cb54  push    r15
0x18005cb56  sub     rsp, 70h
0x18005cb5a  mov     rax, cs:__security_cookie
0x18005cb61  xor     rax, rsp
0x18005cb64  mov     [rsp+98h+var_38], rax
0x18005cb69  mov     rdi, [rsp+98h+arg_20]
0x18005cb71  mov     r15d, r9d
0x18005cb74  mov     r14d, r8d
0x18005cb77  mov     [rsp+98h+var_44], 0
0x18005cb7f  mov     rbp, rdx
0x18005cb82  mov     qword ptr [r11-40h], 0
0x18005cb8a  mov     rsi, rcx
0x18005cb8d  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18005cb94  jz      short loc_18005CBAE
0x18005cb96  mov     [r11-60h], rdi
0x18005cb9a  mov     [r11-68h], r9d
0x18005cb9e  mov     r9, rcx
0x18005cba1  mov     [r11-70h], r8d
0x18005cba5  mov     [r11-78h], rdx
0x18005cba9  call    WPP_SF_qSDlq
0x18005cbae  lea     rax, [rsp+98h+hKey]
0x18005cbb3  mov     qword ptr [rdi], 0
0x18005cbba  mov     r9d, r14d; samDesired
0x18005cbbd  mov     [rsp+98h+phkResult], rax; phkResult
0x18005cbc2  xor     r8d, r8d; ulOptions
0x18005cbc5  mov     rdx, rbp; lpSubKey
0x18005cbc8  mov     rcx, rsi; hKey
0x18005cbcb  call    cs:__imp_RegOpenKeyExW
0x18005cbd2  nop     dword ptr [rax+rax+00h]
0x18005cbd7  mov     ebx, eax
0x18005cbd9  test    r15d, r15d
0x18005cbdc  jz      short loc_18005CC26
0x18005cbde  cmp     eax, 2
0x18005cbe1  jnz     short loc_18005CC26
0x18005cbe3  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x18005cbec  lea     rax, [rsp+98h+hKey]
0x18005cbf1  mov     [rsp+98h+var_60], rax; phkResult
0x18005cbf6  xor     r9d, r9d; lpClass
0x18005cbf9  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005cc02  xor     r8d, r8d; Reserved
0x18005cc05  mov     [rsp+98h+samDesired], r14d; samDesired
0x18005cc0a  mov     rdx, rbp; lpSubKey
0x18005cc0d  mov     rcx, rsi; hKey
0x18005cc10  mov     dword ptr [rsp+98h+phkResult], 0; dwOptions
0x18005cc18  call    cs:__imp_RegCreateKeyExW
0x18005cc1f  nop     dword ptr [rax+rax+00h]
0x18005cc24  mov     ebx, eax
0x18005cc26  test    ebx, ebx
0x18005cc28  jle     short loc_18005CC35
0x18005cc2a  movzx   ebx, bx
0x18005cc2d  or      ebx, 80070000h
0x18005cc33  test    ebx, ebx
0x18005cc35  jns     short loc_18005CC46
0x18005cc37  mov     rcx, [rsp+98h+hKey]
0x18005cc3c  mov     [rsp+98h+var_44], 2A8h
0x18005cc44  jmp     short loc_18005CC55
0x18005cc46  mov     rax, [rsp+98h+hKey]
0x18005cc4b  xor     ecx, ecx
0x18005cc4d  mov     [rdi], rax
0x18005cc50  mov     [rsp+98h+hKey], rcx
0x18005cc55  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18005cc5c  jz      short loc_18005CC7C
0x18005cc5e  mov     edx, 0Bh
0x18005cc63  lea     r8, WPP_b64a873b5a0a3123360afb44b8058dda_Traceguids
0x18005cc6a  mov     ecx, 41Dh
0x18005cc6f  mov     r9d, ebx
0x18005cc72  call    WPP_SF_d
0x18005cc77  mov     rcx, [rsp+98h+hKey]; hKey
0x18005cc7c  test    rcx, rcx
0x18005cc7f  jz      short loc_18005CC8D
0x18005cc81  call    cs:__imp_RegCloseKey
0x18005cc88  nop     dword ptr [rax+rax+00h]
0x18005cc8d  mov     eax, ebx
0x18005cc8f  mov     rcx, [rsp+98h+var_38]
0x18005cc94  xor     rcx, rsp; StackCookie
0x18005cc97  call    __security_check_cookie
0x18005cc9c  mov     rbx, [rsp+98h+arg_18]
0x18005cca4  add     rsp, 70h
0x18005cca8  pop     r15
0x18005ccaa  pop     r14
0x18005ccac  pop     rdi
0x18005ccad  pop     rsi
0x18005ccae  pop     rbp
0x18005ccaf  retn
```
