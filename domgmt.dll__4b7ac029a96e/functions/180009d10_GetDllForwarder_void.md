# GetDllForwarder(void)

- ea: `0x180009d10`
- end: `0x180009d78`
- name: `?GetDllForwarder@@YAAEAUDllForwarder@@XZ`
- size: `104`
- prototype: `struct DllForwarder *(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ad80`
- `0x18000ae80`

## callees

- `0x180001f50`
- `0x18000214c`
- `0x1800021b4`
- `0x180008334`
- `0x180009d10`

## pseudocode

```c
struct DllForwarder *GetDllForwarder(void)
{
  const unsigned __int16 *v1; // rdx
  DllForwarder *v2; // rcx
  const unsigned __int16 *v3; // r8
  const unsigned __int16 *v4; // r9

  if ( dword_1800188D8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800188D8);
    if ( dword_1800188D8 == -1 )
    {
      DllForwarder::DllForwarder(v2, v1, v3, v4);
      atexit(GetDllForwarder_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_1800188D8);
    }
  }
  return (struct DllForwarder *)&qword_1800188E0;
}

```

## disassembly

```asm
0x180009d10  sub     rsp, 28h
0x180009d14  mov     ecx, cs:_tls_index
0x180009d1a  mov     rax, gs:58h
0x180009d23  mov     edx, 4
0x180009d28  mov     rax, [rax+rcx*8]
0x180009d2c  mov     eax, [rdx+rax]
0x180009d2f  cmp     cs:dword_1800188D8, eax
0x180009d35  jg      short loc_180009D43
0x180009d37  lea     rax, qword_1800188E0
0x180009d3e  add     rsp, 28h
0x180009d42  retn
0x180009d43  lea     rcx, dword_1800188D8
0x180009d4a  call    _Init_thread_header
0x180009d4f  cmp     cs:dword_1800188D8, 0FFFFFFFFh
0x180009d56  jnz     short loc_180009D37
0x180009d58  call    ??0DllForwarder@@QEAA@PEBG00@Z; DllForwarder::DllForwarder(ushort const *,ushort const *,ushort const *)
0x180009d5d  lea     rcx, _GetDllForwarder____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x180009d64  call    atexit
0x180009d69  nop
0x180009d6a  lea     rcx, dword_1800188D8
0x180009d71  call    _Init_thread_footer
0x180009d76  jmp     short loc_180009D37
```
