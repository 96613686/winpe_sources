# DsRolepSetLogonDomain

- ea: `0x180015008`
- end: `0x1800150a1`
- name: `DsRolepSetLogonDomain`
- size: `153`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180015008`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015040`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015040`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015089`

## pseudocode

```c
__int64 __fastcall DsRolepSetLogonDomain(__int64 a1)
{
  unsigned int v2; // ebx
  int v3; // r8d
  __int64 v4; // rax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\",
         0,
         0x2001Fu,
         &hKey);
  if ( !v2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a1 + 2 * v4) );
    v2 = DsRolepRegSetValueEx((int)hKey, (int)L"DefaultDomainName", v3, 1, a1, 2 * v4 + 2);
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180015008  mov     r11, rsp
0x18001500b  mov     [r11+8], rbx
0x18001500f  mov     [r11+10h], rsi
0x180015013  push    rdi
0x180015014  sub     rsp, 30h
0x180015018  mov     rdi, rcx
0x18001501b  lea     rax, [r11+18h]
0x18001501f  xor     esi, esi
0x180015021  mov     [r11-18h], rax
0x180015025  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001502c  mov     [r11+18h], rsi
0x180015030  mov     r9d, 2001Fh; samDesired
0x180015036  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001503d  xor     r8d, r8d; ulOptions
0x180015040  call    cs:__imp_RegOpenKeyExW
0x180015046  mov     ebx, eax
0x180015048  test    eax, eax
0x18001504a  jnz     short loc_18001508F
0x18001504c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015050  inc     rax
0x180015053  cmp     [rdi+rax*2], si
0x180015057  jnz     short loc_180015050
0x180015059  mov     rcx, [rsp+38h+hKey]; int
0x18001505e  lea     rax, ds:2[rax*2]
0x180015066  mov     [rsp+38h+ullOperand], rax; ullOperand
0x18001506b  lea     rdx, aDefaultdomainn; "DefaultDomainName"
0x180015072  mov     r9d, 1; int
0x180015078  mov     qword ptr [rsp+38h+var_18], rdi; int
0x18001507d  call    DsRolepRegSetValueEx
0x180015082  mov     rcx, [rsp+38h+hKey]; hKey
0x180015087  mov     ebx, eax
0x180015089  call    cs:__imp_RegCloseKey
0x18001508f  mov     rsi, [rsp+38h+arg_8]
0x180015094  mov     eax, ebx
0x180015096  mov     rbx, [rsp+38h+arg_0]
0x18001509b  add     rsp, 30h
0x18001509f  pop     rdi
0x1800150a0  retn
```
