# CConfigRefreshLogger::GetLogger(void)

- ea: `0x180021ec4`
- end: `0x180021f28`
- name: `?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ`
- size: `100`
- prototype: `struct CConfigRefreshLogger *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b090`
- `0x1800118a0`

## callees

- `0x180004bfc`
- `0x180004c64`
- `0x180020c74`
- `0x180021ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CConfigRefreshLogger *CConfigRefreshLogger::GetLogger(void)
{
  const unsigned __int16 *v1; // rcx

  if ( dword_180032DA4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180032DA4);
    if ( dword_180032DA4 == -1 )
    {
      GetCorrelationVectorForDmSession(v1, qword_1800323F0);
      Init_thread_footer(&dword_180032DA4);
    }
  }
  return (struct CConfigRefreshLogger *)&qword_1800323E0;
}

```

## disassembly

```asm
0x180021ec4  sub     rsp, 28h
0x180021ec8  mov     ecx, cs:_tls_index
0x180021ece  mov     rax, gs:58h
0x180021ed7  mov     edx, 4
0x180021edc  mov     rax, [rax+rcx*8]
0x180021ee0  mov     eax, [rdx+rax]
0x180021ee3  cmp     cs:dword_180032DA4, eax
0x180021ee9  jg      short loc_180021EF8
0x180021eeb  lea     rax, qword_1800323E0
0x180021ef2  add     rsp, 28h
0x180021ef6  retn
0x180021ef8  lea     rcx, dword_180032DA4
0x180021eff  call    _Init_thread_header
0x180021f04  cmp     cs:dword_180032DA4, 0FFFFFFFFh
0x180021f0b  jnz     short loc_180021EEB
0x180021f0d  lea     rdx, qword_1800323F0; char *
0x180021f14  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x180021f19  nop
0x180021f1a  lea     rcx, dword_180032DA4
0x180021f21  call    _Init_thread_footer
0x180021f26  jmp     short loc_180021EEB
```
