# CEnrollmentLogger::GetLogger(void)

- ea: `0x18001dce8`
- end: `0x18001dd43`
- name: `?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ`
- size: `91`
- prototype: `struct CEnrollmentLogger *(void)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180012a70`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`
- `0x18001c054`
- `0x18001c61c`

## callees

- `0x180003740`
- `0x1800037a8`
- `0x18001dce8`
- `0x18001e478`

## pseudocode

```c
struct CEnrollmentLogger *CEnrollmentLogger::GetLogger(void)
{
  char *v1; // rdx
  const unsigned __int16 *v2; // rcx

  if ( dword_18002B8D4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18002B8D4);
    if ( dword_18002B8D4 == -1 )
    {
      GetCorrelationVectorForEnrollmentSession(v2, v1);
      Init_thread_footer(&dword_18002B8D4);
    }
  }
  return (struct CEnrollmentLogger *)&byte_18002B850;
}

```

## disassembly

```asm
0x18001dce8  sub     rsp, 28h
0x18001dcec  mov     ecx, cs:_tls_index
0x18001dcf2  mov     rax, gs:58h
0x18001dcfb  mov     edx, 4
0x18001dd00  mov     rax, [rax+rcx*8]
0x18001dd04  mov     eax, [rdx+rax]
0x18001dd07  cmp     cs:dword_18002B8D4, eax
0x18001dd0d  jg      short loc_18001DD1B
0x18001dd0f  lea     rax, byte_18002B850
0x18001dd16  add     rsp, 28h
0x18001dd1a  retn
0x18001dd1b  lea     rcx, dword_18002B8D4
0x18001dd22  call    _Init_thread_header
0x18001dd27  cmp     cs:dword_18002B8D4, 0FFFFFFFFh
0x18001dd2e  jnz     short loc_18001DD0F
0x18001dd30  call    ?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForEnrollmentSession(ushort const *,char *)
0x18001dd35  lea     rcx, dword_18002B8D4
0x18001dd3c  call    _Init_thread_footer
0x18001dd41  jmp     short loc_18001DD0F
```
