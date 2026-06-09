# CODBCLOG::GetConfig(ulong,uchar *)

- ea: `0x18000a8f0`
- end: `0x18000a972`
- name: `?GetConfig@CODBCLOG@@UEAAJKPEAE@Z`
- size: `130`
- prototype: `__int64 __fastcall(CODBCLOG *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000a914`
- `msvcrt!strcpy_s` at `0x18000a92d`
- `msvcrt!strcpy_s` at `0x18000a946`
- `msvcrt!strcpy_s` at `0x18000a95f`
- `msvcrt!strcpy_s` at `0x18000a914`
- `msvcrt!strcpy_s` at `0x18000a92d`
- `msvcrt!strcpy_s` at `0x18000a946`
- `msvcrt!strcpy_s` at `0x18000a95f`

## pseudocode

```c
__int64 __fastcall CODBCLOG::GetConfig(CODBCLOG *this, __int64 a2, char *a3)
{
  *(_DWORD *)a3 = 2;
  strcpy_s(a3 + 4, 0x104u, (const char *)this + 96);
  strcpy_s(a3 + 264, 0x1Eu, (const char *)this + 356);
  strcpy_s(a3 + 294, 0x101u, (const char *)this + 386);
  strcpy_s(a3 + 551, 0x101u, (const char *)this + 643);
  return 0;
}

```

## disassembly

```asm
0x18000a8f0  mov     [rsp+arg_0], rbx
0x18000a8f5  push    rdi
0x18000a8f6  sub     rsp, 20h
0x18000a8fa  mov     rdi, r8
0x18000a8fd  mov     dword ptr [r8], 2
0x18000a904  mov     rbx, rcx
0x18000a907  lea     r8, [rcx+60h]; Source
0x18000a90b  mov     edx, 104h; SizeInBytes
0x18000a910  lea     rcx, [rdi+4]; Destination
0x18000a914  call    cs:__imp_strcpy_s
0x18000a91a  lea     r8, [rbx+164h]; Source
0x18000a921  mov     edx, 1Eh; SizeInBytes
0x18000a926  lea     rcx, [rdi+108h]; Destination
0x18000a92d  call    cs:__imp_strcpy_s
0x18000a933  lea     r8, [rbx+182h]; Source
0x18000a93a  mov     edx, 101h; SizeInBytes
0x18000a93f  lea     rcx, [rdi+126h]; Destination
0x18000a946  call    cs:__imp_strcpy_s
0x18000a94c  lea     r8, [rbx+283h]; Source
0x18000a953  mov     edx, 101h; SizeInBytes
0x18000a958  lea     rcx, [rdi+227h]; Destination
0x18000a95f  call    cs:__imp_strcpy_s
0x18000a965  mov     rbx, [rsp+28h+arg_0]
0x18000a96a  xor     eax, eax
0x18000a96c  add     rsp, 20h
0x18000a970  pop     rdi
0x18000a971  retn
```
