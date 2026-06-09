# COmaDmPrcLogger::GetLogger(void)

- ea: `0x14000b708`
- end: `0x14000b76c`
- name: `?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ`
- size: `100`
- prototype: `struct COmaDmPrcLogger *(void)`
- caller_count: `18`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000abe0`
- `0x14000edf4`
- `0x14000eee0`
- `0x14000ef80`
- `0x14000efe4`
- `0x14000f13c`
- `0x14000f580`
- `0x14000fff0`
- `0x1400107ec`
- `0x140010bb8`
- `0x1400112f4`
- `0x140011ac8`
- `0x140012060`
- `0x140012288`
- `0x1400128d4`
- `0x140013350`
- `0x140013ae0`
- `0x14001401c`

## callees

- `0x1400029ac`
- `0x140002a1c`
- `0x14000b708`
- `0x14000dc4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct COmaDmPrcLogger *COmaDmPrcLogger::GetLogger(void)
{
  if ( dword_1400242F0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1400242F0);
    if ( dword_1400242F0 == -1 )
    {
      GetCorrelationVectorForDmSession(L"OmaDmPrc", qword_1400232B0);
      Init_thread_footer(&dword_1400242F0);
    }
  }
  return (struct COmaDmPrcLogger *)&qword_1400232A0;
}

```

## disassembly

```asm
0x14000b708  sub     rsp, 28h
0x14000b70c  mov     ecx, 4
0x14000b711  mov     rax, gs:58h
0x14000b71a  mov     rax, [rax]
0x14000b71d  mov     eax, [rcx+rax]
0x14000b720  cmp     cs:dword_1400242F0, eax
0x14000b726  jg      short loc_14000B735
0x14000b728  lea     rax, qword_1400232A0
0x14000b72f  add     rsp, 28h
0x14000b733  retn
0x14000b735  lea     rcx, dword_1400242F0
0x14000b73c  call    _Init_thread_header
0x14000b741  cmp     cs:dword_1400242F0, 0FFFFFFFFh
0x14000b748  jnz     short loc_14000B728
0x14000b74a  lea     rdx, qword_1400232B0; char *
0x14000b751  lea     rcx, c_szCvValueNameOmaDmPrc; "OmaDmPrc"
0x14000b758  call    ?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z; GetCorrelationVectorForDmSession(ushort const *,char *)
0x14000b75d  nop
0x14000b75e  lea     rcx, dword_1400242F0
0x14000b765  call    _Init_thread_footer
0x14000b76a  jmp     short loc_14000B728
```
