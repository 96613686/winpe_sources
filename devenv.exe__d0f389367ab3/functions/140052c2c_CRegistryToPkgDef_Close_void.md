# CRegistryToPkgDef::Close(void)

- ea: `0x140052c2c`
- end: `0x140052c8a`
- name: `?Close@CRegistryToPkgDef@@QEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(CRegistryToPkgDef *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x14004c05c`
- `0x140052aa4`

## callees

- `0x140052c2c`
- `0x140061178`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140052c70`
- `KERNEL32!DeleteFileW` at `0x140052c70`
- `KERNEL32!CopyFileW` at `0x140052c66`
- `KERNEL32!CopyFileW` at `0x140052c66`

## pseudocode

```c
__int64 __fastcall CRegistryToPkgDef::Close(CRegistryToPkgDef *this)
{
  __int64 result; // rax
  unsigned int v3; // edi

  if ( !*((_BYTE *)this + 160) )
    return 1;
  result = PkgDefIO::CPkgDefFileWriter::Close((CRegistryToPkgDef *)((char *)this + 24));
  v3 = result;
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    CopyFileW(*((LPCWSTR *)this + 2), *((LPCWSTR *)this + 1), 0);
    DeleteFileW(*((LPCWSTR *)this + 2));
    result = v3;
    *((_BYTE *)this + 160) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140052c2c  mov     [rsp+arg_0], rbx
0x140052c31  push    rdi
0x140052c32  sub     rsp, 20h
0x140052c36  cmp     byte ptr [rcx+0A0h], 0
0x140052c3d  mov     rbx, rcx
0x140052c40  jnz     short loc_140052C49
0x140052c42  mov     eax, 1
0x140052c47  jmp     short loc_140052C7F
0x140052c49  add     rcx, 18h; this
0x140052c4d  call    ?Close@CPkgDefFileWriter@PkgDefIO@@QEAAJXZ; PkgDefIO::CPkgDefFileWriter::Close(void)
0x140052c52  mov     edi, eax
0x140052c54  lfence
0x140052c57  test    eax, eax
0x140052c59  js      short loc_140052C7F
0x140052c5b  mov     rdx, [rbx+8]; lpNewFileName
0x140052c5f  xor     r8d, r8d; bFailIfExists
0x140052c62  mov     rcx, [rbx+10h]; lpExistingFileName
0x140052c66  call    cs:__imp_CopyFileW
0x140052c6c  mov     rcx, [rbx+10h]; lpFileName
0x140052c70  call    cs:__imp_DeleteFileW
0x140052c76  mov     eax, edi
0x140052c78  mov     byte ptr [rbx+0A0h], 0
0x140052c7f  mov     rbx, [rsp+28h+arg_0]
0x140052c84  add     rsp, 20h
0x140052c88  pop     rdi
0x140052c89  retn
```
