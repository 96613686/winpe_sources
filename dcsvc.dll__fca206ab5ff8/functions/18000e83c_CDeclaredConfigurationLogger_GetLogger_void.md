# CDeclaredConfigurationLogger::GetLogger(void)

- ea: `0x18000e83c`
- end: `0x18000e89f`
- name: `?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ`
- size: `99`
- prototype: `struct CDeclaredConfigurationLogger *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800060b0`
- `0x18000993c`

## callees

- `0x1800028dc`
- `0x180002944`
- `0x18000e83c`
- `0x18000ed9c`

## pseudocode

```c
struct CDeclaredConfigurationLogger *CDeclaredConfigurationLogger::GetLogger(void)
{
  const unsigned __int16 *v1; // rcx

  if ( dword_18001BA10 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18001BA10);
    if ( dword_18001BA10 == -1 )
    {
      GetCorrelationVectorForDmSession(v1, qword_18001B2F0);
      Init_thread_footer(&dword_18001BA10);
    }
  }
  return (struct CDeclaredConfigurationLogger *)&qword_18001B2E0;
}

```

## disassembly

```asm
0x18000e83c  sub     rsp, 28h
0x18000e840  mov     ecx, cs:_tls_index
0x18000e846  mov     rax, gs:58h
0x18000e84f  mov     edx, 4
0x18000e854  mov     rax, [rax+rcx*8]
0x18000e858  mov     eax, [rdx+rax]
0x18000e85b  cmp     cs:dword_18001BA10, eax
0x18000e861  jg      short loc_18000E86F
0x18000e863  lea     rax, qword_18001B2E0
0x18000e86a  add     rsp, 28h
0x18000e86e  retn
0x18000e86f  lea     rcx, dword_18001BA10
0x18000e876  call    _Init_thread_header
0x18000e87b  cmp     cs:dword_18001BA10, 0FFFFFFFFh
0x18000e882  jnz     short loc_18000E863
0x18000e884  lea     rdx, qword_18001B2F0; char *
0x18000e88b  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x18000e890  nop
0x18000e891  lea     rcx, dword_18001BA10
0x18000e898  call    _Init_thread_footer
0x18000e89d  jmp     short loc_18000E863
```
