# NlpEliminateCacheEntry(ulong)

- ea: `0x180041ec8`
- end: `0x180041f5b`
- name: `?NlpEliminateCacheEntry@@YAJK@Z`
- size: `147`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180040fec`

## callees

- `0x18002fb50`
- `0x180041ec8`
- `0x180042740`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180041f3d`
- `ntdll!NtDeleteValueKey` at `0x180041f3d`
- `LSASRV!LsarDeleteObject` at `0x180041f2b`
- `LSASRV!LsarDeleteObject` at `0x180041f2b`
- `LSASRV!LsarOpenSecret` at `0x180041f1c`
- `LSASRV!LsarOpenSecret` at `0x180041f1c`

## pseudocode

```c
NTSTATUS __fastcall NlpEliminateCacheEntry(unsigned int a1)
{
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-78h] BYREF
  _QWORD v3[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v4; // [rsp+40h] [rbp-58h] BYREF

  *(_QWORD *)&ValueName.Length = 0x200000;
  ValueName.Buffer = (PWSTR)&v4;
  v3[0] = 0;
  NlpMakeCacheEntryName(a1, &ValueName);
  if ( (int)LsarOpenSecret(NtLmGlobalPolicyHandle, &ValueName, 0x10000, v3) >= 0 )
    LsarDeleteObject(v3);
  return NtDeleteValueKey(NlpCacheHandle, &ValueName);
}

```

## disassembly

```asm
0x180041ec8  mov     r11, rsp
0x180041ecb  sub     rsp, 98h
0x180041ed2  mov     rax, cs:__security_cookie
0x180041ed9  xor     rax, rsp
0x180041edc  mov     [rsp+98h+var_18], rax
0x180041ee4  lea     rax, [r11-58h]
0x180041ee8  mov     qword ptr [r11-78h], 200000h
0x180041ef0  lea     rdx, [r11-78h]; struct _UNICODE_STRING *
0x180041ef4  mov     [r11-70h], rax
0x180041ef8  mov     qword ptr [r11-68h], 0
0x180041f00  call    ?NlpMakeCacheEntryName@@YAXKPEAU_UNICODE_STRING@@@Z; NlpMakeCacheEntryName(ulong,_UNICODE_STRING *)
0x180041f05  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180041f0c  lea     r9, [rsp+98h+var_68]
0x180041f11  mov     r8d, 10000h
0x180041f17  lea     rdx, [rsp+98h+ValueName]
0x180041f1c  call    cs:__imp_LsarOpenSecret
0x180041f22  test    eax, eax
0x180041f24  js      short loc_180041F31
0x180041f26  lea     rcx, [rsp+98h+var_68]
0x180041f2b  call    cs:__imp_LsarDeleteObject
0x180041f31  mov     rcx, cs:?NlpCacheHandle@@3PEAXEA; KeyHandle
0x180041f38  lea     rdx, [rsp+98h+ValueName]; ValueName
0x180041f3d  call    cs:__imp_NtDeleteValueKey
0x180041f43  mov     rcx, [rsp+98h+var_18]
0x180041f4b  xor     rcx, rsp; StackCookie
0x180041f4e  call    __security_check_cookie
0x180041f53  add     rsp, 98h
0x180041f5a  retn
```
