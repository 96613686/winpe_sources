# CscSetting_OpenRegKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)

- ea: `0x180029ce4`
- end: `0x180029dca`
- name: `?CscSetting_OpenRegKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z`
- size: `230`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, int, HKEY *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180035368`
- `0x18005b690`
- `0x18005bd80`
- `0x18005c6c0`

## callees

- `0x180029ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029d97`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180029d28`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180029d28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029db3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029db3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029d87`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180029d87`

## pseudocode

```c
__int64 __fastcall CscSetting_OpenRegKey(HKEY a1, const unsigned __int16 *a2, REGSAM a3, int a4, PHKEY a5)
{
  HKEY *phkResult; // r14
  HKEY v9; // rdi
  LSTATUS v10; // eax
  signed int v11; // ebx
  int v12; // esi
  LSTATUS Key; // eax

  phkResult = a5;
  v9 = a1;
  *a5 = 0;
  if ( a1 == HKEY_CURRENT_USER )
  {
    a5 = 0;
    v10 = RegOpenCurrentUser(a3, (PHKEY)&a5);
    v11 = v10;
    if ( v10 )
    {
      v12 = 0;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v9 = (HKEY)a5;
      v12 = 1;
    }
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
  if ( v11 >= 0 )
  {
    if ( a4 )
      Key = RegCreateKeyExW(v9, a2, 0, (LPWSTR)&Class, 0, a3, 0, phkResult, 0);
    else
      Key = RegOpenKeyExW(v9, a2, 0, a3, phkResult);
    v11 = Key;
    if ( Key > 0 )
      v11 = (unsigned __int16)Key | 0x80070000;
    if ( v12 )
      RegCloseKey(v9);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180029ce4  mov     rax, rsp
0x180029ce7  push    rbx
0x180029ce8  push    rbp
0x180029ce9  push    rsi
0x180029cea  push    rdi
0x180029ceb  push    r12
0x180029ced  push    r14
0x180029cef  push    r15
0x180029cf1  sub     rsp, 50h
0x180029cf5  mov     r14, [rsp+88h+arg_20]
0x180029cfd  mov     r15d, r9d
0x180029d00  mov     ebp, r8d
0x180029d03  mov     r12, rdx
0x180029d06  mov     rdi, rcx
0x180029d09  mov     qword ptr [r14], 0
0x180029d10  cmp     rcx, 0FFFFFFFF80000001h
0x180029d17  jnz     short loc_180029D52
0x180029d19  lea     rdx, [rax+28h]; phkResult
0x180029d1d  mov     qword ptr [rax+28h], 0
0x180029d25  mov     ecx, r8d; samDesired
0x180029d28  call    cs:__imp_RegOpenCurrentUser
0x180029d2e  mov     ebx, eax
0x180029d30  test    eax, eax
0x180029d32  jnz     short loc_180029D41
0x180029d34  mov     rdi, [rsp+88h+arg_20]
0x180029d3c  lea     esi, [rax+1]
0x180029d3f  jmp     short loc_180029D56
0x180029d41  xor     esi, esi
0x180029d43  test    eax, eax
0x180029d45  jle     short loc_180029D56
0x180029d47  movzx   ebx, ax
0x180029d4a  or      ebx, 80070000h
0x180029d50  jmp     short loc_180029D56
0x180029d52  xor     ebx, ebx
0x180029d54  xor     esi, esi
0x180029d56  test    ebx, ebx
0x180029d58  js      short loc_180029DB9
0x180029d5a  xor     r8d, r8d; ulOptions
0x180029d5d  mov     rdx, r12; lpSubKey
0x180029d60  mov     rcx, rdi; hKey
0x180029d63  test    r15d, r15d
0x180029d66  jz      short loc_180029D8F
0x180029d68  mov     [rsp+88h+lpdwDisposition], r8; lpdwDisposition
0x180029d6d  lea     r9, Class; lpClass
0x180029d74  mov     [rsp+88h+phkResult], r14; phkResult
0x180029d79  mov     [rsp+88h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180029d7e  mov     [rsp+88h+samDesired], ebp; samDesired
0x180029d82  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x180029d87  call    cs:__imp_RegCreateKeyExW
0x180029d8d  jmp     short loc_180029D9D
0x180029d8f  mov     r9d, ebp; samDesired
0x180029d92  mov     qword ptr [rsp+88h+dwOptions], r14; phkResult
0x180029d97  call    cs:__imp_RegOpenKeyExW
0x180029d9d  mov     ebx, eax
0x180029d9f  test    eax, eax
0x180029da1  jle     short loc_180029DAC
0x180029da3  movzx   ebx, bx
0x180029da6  or      ebx, 80070000h
0x180029dac  test    esi, esi
0x180029dae  jz      short loc_180029DB9
0x180029db0  mov     rcx, rdi; hKey
0x180029db3  call    cs:__imp_RegCloseKey
0x180029db9  mov     eax, ebx
0x180029dbb  add     rsp, 50h
0x180029dbf  pop     r15
0x180029dc1  pop     r14
0x180029dc3  pop     r12
0x180029dc5  pop     rdi
0x180029dc6  pop     rsi
0x180029dc7  pop     rbp
0x180029dc8  pop     rbx
0x180029dc9  retn
```
