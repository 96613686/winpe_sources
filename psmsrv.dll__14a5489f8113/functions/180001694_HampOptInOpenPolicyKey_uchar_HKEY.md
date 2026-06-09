# HampOptInOpenPolicyKey(uchar,HKEY__ * *)

- ea: `0x180001694`
- end: `0x180001716`
- name: `?HampOptInOpenPolicyKey@@YAKEPEAPEAUHKEY__@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(__int64, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001580`

## callees

- `0x180001694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000170e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000170e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800016da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800016da`

## pseudocode

```c
__int64 __fastcall HampOptInOpenPolicyKey(__int64 a1, HKEY *a2)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  __int128 v6; // [rsp+38h] [rbp-40h]
  __int128 v7; // [rsp+48h] [rbp-30h]
  __int128 v8; // [rsp+58h] [rbp-20h]

  hKey = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\HostActivityManager",
         0,
         0x20019u,
         &hKey);
  if ( v3 )
  {
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    *a2 = hKey;
    hKey = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180001694  mov     rax, rsp
0x180001697  mov     [rax+8], rbx
0x18000169b  push    rdi
0x18000169c  sub     rsp, 70h
0x1800016a0  xorps   xmm0, xmm0
0x1800016a3  mov     qword ptr [rax-48h], 0
0x1800016ab  movups  xmmword ptr [rax-40h], xmm0
0x1800016af  mov     rdi, rdx
0x1800016b2  mov     r9d, 20019h; samDesired
0x1800016b8  movups  xmmword ptr [rax-30h], xmm0
0x1800016bc  xor     r8d, r8d; ulOptions
0x1800016bf  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800016c6  movups  xmmword ptr [rax-20h], xmm0
0x1800016ca  lea     rax, [rax-48h]
0x1800016ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800016d5  mov     [rsp+78h+phkResult], rax; phkResult
0x1800016da  call    cs:__imp_RegOpenKeyExW
0x1800016e0  mov     rcx, [rsp+78h+hKey]; hKey
0x1800016e5  mov     ebx, eax
0x1800016e7  test    eax, eax
0x1800016e9  jz      short loc_180001700
0x1800016eb  test    rcx, rcx
0x1800016ee  jnz     short loc_18000170E
0x1800016f0  mov     eax, ebx
0x1800016f2  mov     rbx, [rsp+78h+arg_0]
0x1800016fa  add     rsp, 70h
0x1800016fe  pop     rdi
0x1800016ff  retn
0x180001700  mov     [rdi], rcx
0x180001703  mov     [rsp+78h+hKey], 0
0x18000170c  jmp     short loc_1800016F0
0x18000170e  call    cs:__imp_RegCloseKey
0x180001714  jmp     short loc_1800016F0
```
