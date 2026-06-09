# NlpMakeNewCacheEntry

- ea: `0x180044e50`
- end: `0x180044f3f`
- name: `NlpMakeNewCacheEntry`
- size: `239`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18003db30`
- `0x180040fec`
- `0x180042168`

## callees

- `0x18002fb50`
- `0x180030844`
- `0x180042740`
- `0x180044e50`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x180044f1c`
- `ntdll!NtSetValueKey` at `0x180044f1c`
- `LSASRV!LsarDeleteObject` at `0x180044ed1`
- `LSASRV!LsarDeleteObject` at `0x180044ed1`
- `LSASRV!LsarOpenSecret` at `0x180044ec2`
- `LSASRV!LsarOpenSecret` at `0x180044ec2`

## pseudocode

```c
NTSTATUS __fastcall NlpMakeNewCacheEntry(unsigned int a1)
{
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v4[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Data[40]; // [rsp+50h] [rbp-B0h] BYREF
  int v6; // [rsp+78h] [rbp-88h]
  char v7; // [rsp+80h] [rbp-80h]
  char v8; // [rsp+100h] [rbp+0h] BYREF

  memset_0(Data, 0, 0xA8u);
  *(_QWORD *)&ValueName.Length = 0x200000;
  ValueName.Buffer = (PWSTR)&v8;
  v4[0] = 0;
  NlpMakeCacheEntryName(a1, &ValueName);
  if ( (int)LsarOpenSecret(NtLmGlobalPolicyHandle, &ValueName, 0x10000, v4) >= 0 )
    LsarDeleteObject(v4);
  memset_0(Data, 0, 0xA8u);
  v6 = 65540;
  v7 = 0;
  return NtSetValueKey(NlpCacheHandle, &ValueName, 0, 3u, Data, 0xA8u);
}

```

## disassembly

```asm
0x180044e50  mov     [rsp-8+arg_8], rbx
0x180044e55  push    rbp
0x180044e56  lea     rbp, [rsp-50h]
0x180044e5b  sub     rsp, 150h
0x180044e62  mov     rax, cs:__security_cookie
0x180044e69  xor     rax, rsp
0x180044e6c  mov     [rbp+50h+var_10], rax
0x180044e70  mov     ebx, ecx
0x180044e72  xor     edx, edx; Val
0x180044e74  lea     rcx, [rsp+150h+var_100]; void *
0x180044e79  mov     r8d, 0A8h; Size
0x180044e7f  call    memset_0
0x180044e84  lea     rax, [rbp+50h+var_50]
0x180044e88  mov     qword ptr [rsp+150h+ValueName.Length], 200000h
0x180044e91  lea     rdx, [rsp+150h+ValueName]; struct _UNICODE_STRING *
0x180044e96  mov     [rsp+150h+ValueName.Buffer], rax
0x180044e9b  mov     ecx, ebx; unsigned int
0x180044e9d  mov     [rsp+150h+var_110], 0
0x180044ea6  call    ?NlpMakeCacheEntryName@@YAXKPEAU_UNICODE_STRING@@@Z; NlpMakeCacheEntryName(ulong,_UNICODE_STRING *)
0x180044eab  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180044eb2  lea     r9, [rsp+150h+var_110]
0x180044eb7  mov     r8d, 10000h
0x180044ebd  lea     rdx, [rsp+150h+ValueName]
0x180044ec2  call    cs:__imp_LsarOpenSecret
0x180044ec8  test    eax, eax
0x180044eca  js      short loc_180044ED7
0x180044ecc  lea     rcx, [rsp+150h+var_110]
0x180044ed1  call    cs:__imp_LsarDeleteObject
0x180044ed7  xor     edx, edx; Val
0x180044ed9  lea     rcx, [rsp+150h+var_100]; void *
0x180044ede  mov     r8d, 0A8h; Size
0x180044ee4  call    memset_0
0x180044ee9  mov     rcx, cs:?NlpCacheHandle@@3PEAXEA; KeyHandle
0x180044ef0  lea     rax, [rsp+150h+var_100]
0x180044ef5  mov     [rsp+150h+DataSize], 0A8h; DataSize
0x180044efd  lea     rdx, [rsp+150h+ValueName]; ValueName
0x180044f02  mov     r9d, 3; Type
0x180044f08  mov     [rsp+150h+Data], rax; Data
0x180044f0d  xor     r8d, r8d; TitleIndex
0x180044f10  mov     [rsp+150h+var_D8], 10004h
0x180044f18  mov     [rbp+50h+var_D0], 0
0x180044f1c  call    cs:__imp_NtSetValueKey
0x180044f22  mov     rcx, [rbp+50h+var_10]
0x180044f26  xor     rcx, rsp; StackCookie
0x180044f29  call    __security_check_cookie
0x180044f2e  mov     rbx, [rsp+150h+arg_8]
0x180044f36  add     rsp, 150h
0x180044f3d  pop     rbp
0x180044f3e  retn
```
