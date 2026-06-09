# DllCanUnloadNow

- ea: `0x18008fd70`
- end: `0x18008fdec`
- name: `DllCanUnloadNow`
- size: `124`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18008fd70`
- `0x180095e54`
- `0x18018c010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18008fde0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( byte_1801FACC2 )
    return 0;
  if ( !sub_18018C010() )
    return 1;
  if ( dword_1801FACC4 > 0 )
    return 1;
  if ( dword_1801FADB4 > 0 )
    return 1;
  if ( dword_1801FADB8 )
    return 1;
  sub_180095E54();
  if ( (unsigned int)sub_18018C010() )
    return 1;
  return NdrDllCanUnloadNow(&pPSFactoryBuffer);
}

```

## disassembly

```asm
0x18008fd70  sub     rsp, 28h
0x18008fd74  cmp     cs:byte_1801FACC2, 0
0x18008fd7b  jnz     short loc_18008FD99
0x18008fd7d  mov     rax, cs:qword_1801F76F0
0x18008fd84  call    sub_18018C010
0x18008fd89  test    rax, rax
0x18008fd8c  jnz     short loc_18008FD9D
0x18008fd8e  mov     eax, 1
0x18008fd93  add     rsp, 28h
0x18008fd97  retn
0x18008fd99  xor     eax, eax
0x18008fd9b  jmp     short loc_18008FD93
0x18008fd9d  cmp     cs:dword_1801FACC4, 0
0x18008fda4  jg      short loc_18008FD8E
0x18008fda6  mov     eax, cs:dword_1801FADB4
0x18008fdac  test    eax, eax
0x18008fdae  jg      short loc_18008FD8E
0x18008fdb0  mov     eax, cs:dword_1801FADB8
0x18008fdb6  test    eax, eax
0x18008fdb8  jnz     short loc_18008FD8E
0x18008fdba  call    sub_180095E54
0x18008fdbf  mov     rdx, rax
0x18008fdc2  mov     rcx, [rax]
0x18008fdc5  mov     rax, [rcx+18h]
0x18008fdc9  mov     rcx, rdx
0x18008fdcc  call    sub_18018C010
0x18008fdd1  test    eax, eax
0x18008fdd3  jnz     short loc_18008FD8E
0x18008fdd5  lea     rcx, pPSFactoryBuffer
0x18008fddc  add     rsp, 28h
0x18008fde0  jmp     cs:NdrDllCanUnloadNow
```
