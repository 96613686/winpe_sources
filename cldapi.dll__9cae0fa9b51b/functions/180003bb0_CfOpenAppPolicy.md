# CfOpenAppPolicy

- ea: `0x180003bb0`
- end: `0x180003c47`
- name: `CfOpenAppPolicy`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003bb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c2d`

## pseudocode

```c
__int64 __fastcall CfOpenAppPolicy(int a1, HKEY *a2)
{
  signed int v2; // ebx
  LSTATUS v4; // eax
  HKEY v5; // rcx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  hKey = 0;
  *a2 = 0;
  if ( a1 == 1 )
  {
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Policies\\Microsoft\\CloudFiles\\BlockedApps", 0, 8u, &hKey);
    v2 = v4;
    if ( v4 == 2 )
    {
      v2 = 0;
    }
    else if ( v4 > 0 )
    {
      v2 = (unsigned __int16)v4 | 0x80070000;
    }
    if ( v2 < 0 )
    {
      v5 = hKey;
    }
    else
    {
      v5 = 0;
      *a2 = hKey;
      hKey = 0;
    }
    if ( v5 )
      RegCloseKey(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003bb0  mov     r11, rsp
0x180003bb3  mov     [r11+8], rbx
0x180003bb7  push    rdi
0x180003bb8  sub     rsp, 30h
0x180003bbc  xor     ebx, ebx
0x180003bbe  mov     rdi, rdx
0x180003bc1  mov     [r11+10h], rbx
0x180003bc5  mov     [rdx], rbx
0x180003bc8  cmp     ecx, 1
0x180003bcb  jnz     short loc_180003C39
0x180003bcd  lea     rax, [r11+10h]
0x180003bd1  xor     r8d, r8d; ulOptions
0x180003bd4  lea     r9d, [rbx+8]; samDesired
0x180003bd8  mov     [r11-18h], rax
0x180003bdc  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\CloudFil"...
0x180003be3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180003bea  call    cs:__imp_RegOpenKeyExW
0x180003bf1  nop     dword ptr [rax+rax+00h]
0x180003bf6  mov     ebx, eax
0x180003bf8  cmp     eax, 2
0x180003bfb  jnz     short loc_180003C01
0x180003bfd  xor     ebx, ebx
0x180003bff  jmp     short loc_180003C0E
0x180003c01  test    eax, eax
0x180003c03  jle     short loc_180003C0E
0x180003c05  movzx   ebx, ax
0x180003c08  or      ebx, 80070000h
0x180003c0e  test    ebx, ebx
0x180003c10  js      short loc_180003C23
0x180003c12  mov     rax, [rsp+38h+hKey]
0x180003c17  xor     ecx, ecx
0x180003c19  mov     [rdi], rax
0x180003c1c  mov     [rsp+38h+hKey], rcx
0x180003c21  jmp     short loc_180003C28
0x180003c23  mov     rcx, [rsp+38h+hKey]; hKey
0x180003c28  test    rcx, rcx
0x180003c2b  jz      short loc_180003C39
0x180003c2d  call    cs:__imp_RegCloseKey
0x180003c34  nop     dword ptr [rax+rax+00h]
0x180003c39  mov     eax, ebx
0x180003c3b  mov     rbx, [rsp+38h+arg_0]
0x180003c40  add     rsp, 30h
0x180003c44  pop     rdi
0x180003c45  retn
```
