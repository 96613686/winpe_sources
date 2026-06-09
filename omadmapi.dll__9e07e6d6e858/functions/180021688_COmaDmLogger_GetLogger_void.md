# COmaDmLogger::GetLogger(void)

- ea: `0x180021688`
- end: `0x1800216ec`
- name: `?GetLogger@COmaDmLogger@@SAPEAV1@XZ`
- size: `100`
- prototype: `struct COmaDmLogger *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019684`
- `0x18001fa38`

## callees

- `0x180004bfc`
- `0x180004c64`
- `0x180020c74`
- `0x180021688`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct COmaDmLogger *COmaDmLogger::GetLogger(void)
{
  const unsigned __int16 *v1; // rcx

  if ( dword_180032DA0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180032DA0);
    if ( dword_180032DA0 == -1 )
    {
      GetCorrelationVectorForDmSession(v1, qword_180032350);
      Init_thread_footer(&dword_180032DA0);
    }
  }
  return (struct COmaDmLogger *)&qword_180032340;
}

```

## disassembly

```asm
0x180021688  sub     rsp, 28h
0x18002168c  mov     ecx, cs:_tls_index
0x180021692  mov     rax, gs:58h
0x18002169b  mov     edx, 4
0x1800216a0  mov     rax, [rax+rcx*8]
0x1800216a4  mov     eax, [rdx+rax]
0x1800216a7  cmp     cs:dword_180032DA0, eax
0x1800216ad  jg      short loc_1800216BC
0x1800216af  lea     rax, qword_180032340
0x1800216b6  add     rsp, 28h
0x1800216ba  retn
0x1800216bc  lea     rcx, dword_180032DA0
0x1800216c3  call    _Init_thread_header
0x1800216c8  cmp     cs:dword_180032DA0, 0FFFFFFFFh
0x1800216cf  jnz     short loc_1800216AF
0x1800216d1  lea     rdx, qword_180032350; char *
0x1800216d8  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x1800216dd  nop
0x1800216de  lea     rcx, dword_180032DA0
0x1800216e5  call    _Init_thread_footer
0x1800216ea  jmp     short loc_1800216AF
```
