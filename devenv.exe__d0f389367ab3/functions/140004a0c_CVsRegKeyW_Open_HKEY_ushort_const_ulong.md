# CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x140004a0c`
- end: `0x140004a98`
- name: `?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `140`
- prototype: `int(CVsRegKeyW *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004ce8`
- `0x14000905c`
- `0x14000b208`
- `0x140012440`
- `0x140012e50`
- `0x140013100`
- `0x140027cbc`
- `0x140028640`
- `0x14002fbd8`
- `0x140032588`
- `0x1400376ac`
- `0x140037ce8`
- `0x140039248`
- `0x14003a748`
- `0x14003f8f0`

## callees

- `0x140001020`
- `0x140004a0c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140004a62`
- `ADVAPI32!RegCloseKey` at `0x140004a62`
- `ADVAPI32!RegOpenKeyExW` at `0x140004a4e`
- `ADVAPI32!RegOpenKeyExW` at `0x140004a4e`

## pseudocode

```c
__int64 __fastcall CVsRegKeyW::Open(HKEY *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  LSTATUS v5; // ebx
  __int64 result; // rax
  HKEY phkResult; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  phkResult = 0;
  v5 = RegOpenKeyExW(a2, a3, 0, a4, &phkResult);
  if ( !v5 )
  {
    if ( *this )
      RegCloseKey(*this);
    *this = phkResult;
  }
  result = (unsigned __int16)v5 | 0x80070000;
  if ( v5 <= 0 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x140004a0c  push    rbx
0x140004a0e  push    rdi
0x140004a0f  sub     rsp, 48h
0x140004a13  mov     rax, cs:__security_cookie
0x140004a1a  xor     rax, rsp
0x140004a1d  mov     [rsp+58h+var_20], rax
0x140004a22  mov     rax, r8
0x140004a25  mov     r10, rdx
0x140004a28  mov     rdi, rcx
0x140004a2b  test    rdx, rdx
0x140004a2e  jz      short loc_140004A7F
0x140004a30  test    rax, rax
0x140004a33  jz      short loc_140004A7F
0x140004a35  and     [rsp+58h+var_28], 0
0x140004a3b  lea     rcx, [rsp+58h+var_28]
0x140004a40  mov     [rsp+58h+phkResult], rcx; phkResult
0x140004a45  xor     r8d, r8d; ulOptions
0x140004a48  mov     rcx, r10; hKey
0x140004a4b  mov     rdx, rax; lpSubKey
0x140004a4e  call    cs:__imp_RegOpenKeyExW
0x140004a54  mov     ebx, eax
0x140004a56  test    eax, eax
0x140004a58  jnz     short loc_140004A70
0x140004a5a  mov     rcx, [rdi]; hKey
0x140004a5d  test    rcx, rcx
0x140004a60  jz      short loc_140004A68
0x140004a62  call    cs:__imp_RegCloseKey
0x140004a68  mov     rcx, [rsp+58h+var_28]
0x140004a6d  mov     [rdi], rcx
0x140004a70  movzx   eax, bx
0x140004a73  or      eax, 80070000h
0x140004a78  test    ebx, ebx
0x140004a7a  cmovle  eax, ebx
0x140004a7d  jmp     short loc_140004A84
0x140004a7f  mov     eax, 80004003h
0x140004a84  mov     rcx, [rsp+58h+var_20]
0x140004a89  xor     rcx, rsp; StackCookie
0x140004a8c  call    __security_check_cookie
0x140004a91  add     rsp, 48h
0x140004a95  pop     rdi
0x140004a96  pop     rbx
0x140004a97  retn
```
