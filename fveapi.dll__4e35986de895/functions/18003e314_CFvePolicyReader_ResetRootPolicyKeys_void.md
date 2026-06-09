# CFvePolicyReader::ResetRootPolicyKeys(void)

- ea: `0x18003e314`
- end: `0x18003e410`
- name: `?ResetRootPolicyKeys@CFvePolicyReader@@AEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180057790`

## callees

- `0x18003e314`
- `0x18003e418`
- `0x18003e470`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e3f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e3f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e361`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e3a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e361`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e3a1`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::ResetRootPolicyKeys(CFvePolicyReader *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  phkResult = 0;
  hKey = 0;
  CFvePolicyReader::CloseRootPolicyKeys(this);
  CFvePolicyReader::UnloadVolumePolicy(this);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &phkResult);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_9;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System", 0, 0x20019u, &hKey);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 < 0 )
  {
LABEL_9:
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    *((_QWORD *)this + 2) = phkResult;
    *((_QWORD *)this + 3) = hKey;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003e314  mov     [rsp+arg_0], rbx
0x18003e319  push    rdi
0x18003e31a  sub     rsp, 30h
0x18003e31e  mov     rdi, rcx
0x18003e321  mov     [rsp+38h+arg_8], 0
0x18003e32a  mov     [rsp+38h+hKey], 0
0x18003e333  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x18003e338  mov     rcx, rdi; this
0x18003e33b  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x18003e340  lea     rax, [rsp+38h+arg_8]
0x18003e345  mov     r9d, 20019h; samDesired
0x18003e34b  xor     r8d, r8d; ulOptions
0x18003e34e  mov     [rsp+38h+phkResult], rax; phkResult
0x18003e353  lea     rdx, aSoftware; "Software"
0x18003e35a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e361  call    cs:__imp_RegOpenKeyExW
0x18003e368  nop     dword ptr [rax+rax+00h]
0x18003e36d  mov     ebx, eax
0x18003e36f  test    eax, eax
0x18003e371  jle     short loc_18003E37C
0x18003e373  movzx   ebx, ax
0x18003e376  or      ebx, 80070000h
0x18003e37c  test    ebx, ebx
0x18003e37e  js      short loc_18003E3E0
0x18003e380  lea     rax, [rsp+38h+hKey]
0x18003e385  mov     r9d, 20019h; samDesired
0x18003e38b  xor     r8d, r8d; ulOptions
0x18003e38e  mov     [rsp+38h+phkResult], rax; phkResult
0x18003e393  lea     rdx, aSystem_1; "System"
0x18003e39a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e3a1  call    cs:__imp_RegOpenKeyExW
0x18003e3a8  nop     dword ptr [rax+rax+00h]
0x18003e3ad  mov     ebx, eax
0x18003e3af  test    eax, eax
0x18003e3b1  jle     short loc_18003E3BC
0x18003e3b3  movzx   ebx, ax
0x18003e3b6  or      ebx, 80070000h
0x18003e3bc  test    ebx, ebx
0x18003e3be  js      short loc_18003E3E0
0x18003e3c0  mov     rax, [rsp+38h+arg_8]
0x18003e3c5  mov     [rdi+10h], rax
0x18003e3c9  mov     rax, [rsp+38h+hKey]
0x18003e3ce  mov     [rdi+18h], rax
0x18003e3d2  mov     eax, ebx
0x18003e3d4  mov     rbx, [rsp+38h+arg_0]
0x18003e3d9  add     rsp, 30h
0x18003e3dd  pop     rdi
0x18003e3de  retn
0x18003e3e0  mov     rcx, [rsp+38h+arg_8]; hKey
0x18003e3e5  test    rcx, rcx
0x18003e3e8  jnz     short loc_18003E402
0x18003e3ea  mov     rcx, [rsp+38h+hKey]; hKey
0x18003e3ef  test    rcx, rcx
0x18003e3f2  jz      short loc_18003E3D2
0x18003e3f4  call    cs:__imp_RegCloseKey
0x18003e3fb  nop     dword ptr [rax+rax+00h]
0x18003e400  jmp     short loc_18003E3D2
0x18003e402  call    cs:__imp_RegCloseKey
0x18003e409  nop     dword ptr [rax+rax+00h]
0x18003e40e  jmp     short loc_18003E3EA
```
