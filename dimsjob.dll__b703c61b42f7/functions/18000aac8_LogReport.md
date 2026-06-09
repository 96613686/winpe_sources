# _LogReport

- ea: `0x18000aac8`
- end: `0x18000aaef`
- name: `_LogReport`
- size: `39`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001410`
- `0x180001c10`
- `0x1800022f0`
- `0x180002f70`
- `0x1800078e0`
- `0x18000b4dc`

## callees

- `0x18000aac8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000aae4`
- `ntdll!EtwEventWrite` at `0x18000aae4`

## pseudocode

```c
__int64 __fastcall LogReport(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 result; // rax

  result = a1;
  if ( qword_180011978 )
    return EtwEventWrite(qword_180011978, a1, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000aac8  sub     rsp, 28h
0x18000aacc  mov     rax, rcx
0x18000aacf  mov     rcx, cs:qword_180011978
0x18000aad6  test    rcx, rcx
0x18000aad9  jz      short loc_18000AAEA
0x18000aadb  mov     r9, r8
0x18000aade  mov     r8d, edx
0x18000aae1  mov     rdx, rax
0x18000aae4  call    cs:__imp_EtwEventWrite
0x18000aaea  add     rsp, 28h
0x18000aaee  retn
```
