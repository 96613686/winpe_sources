# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)

- ea: `0x180009c1c`
- end: `0x180009c45`
- name: `?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180009b24`

## callees

- `0x180009c1c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(
        _QWORD *a1)
{
  __int64 result; // rax

  result = -1;
  if ( a1[1] == -1 )
  {
    if ( *a1 )
    {
      do
        ++result;
      while ( *(_WORD *)(*a1 + 2 * result) );
    }
    else
    {
      result = 0;
    }
    a1[1] = result;
  }
  return result;
}

```

## disassembly

```asm
0x180009c1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009c20  cmp     [rcx+8], rax
0x180009c24  jnz     short locret_180009C44
0x180009c26  mov     rdx, [rcx]
0x180009c29  xor     r8d, r8d
0x180009c2c  test    rdx, rdx
0x180009c2f  jz      short loc_180009C3D
0x180009c31  inc     rax
0x180009c34  cmp     [rdx+rax*2], r8w
0x180009c39  jnz     short loc_180009C31
0x180009c3b  jmp     short loc_180009C40
0x180009c3d  mov     rax, r8
0x180009c40  mov     [rcx+8], rax
0x180009c44  retn
```
