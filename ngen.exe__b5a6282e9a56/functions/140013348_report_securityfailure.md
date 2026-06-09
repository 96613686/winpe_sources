# __report_securityfailure

- ea: `0x140013348`
- end: `0x1400133e4`
- name: `__report_securityfailure`
- size: `156`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013334`

## callees

- `0x140013220`
- `0x140013348`
- `0x1400133e4`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x140013355`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140013355`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v2);
  capture_current_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_1400272D0 = retaddr;
  dword_1400272C0 = -1073740791;
  dword_1400272C4 = 1;
  dword_1400272D8 = 1;
  qword_1400272E0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140013348  mov     [rsp+arg_0], ecx
0x14001334c  sub     rsp, 28h
0x140013350  mov     ecx, 17h; ProcessorFeature
0x140013355  call    cs:__imp_IsProcessorFeaturePresent
0x14001335b  test    eax, eax
0x14001335d  jz      short loc_140013367
0x14001335f  mov     eax, [rsp+28h+arg_0]
0x140013363  mov     ecx, eax
0x140013365  int     29h; Win8: RtlFailFast(ecx)
0x140013367  lea     rcx, ContextRecord; ContextRecord
0x14001336e  call    capture_current_context
0x140013373  mov     rax, [rsp+28h]
0x140013378  mov     cs:ContextRecord.Rip, rax
0x14001337f  lea     rax, [rsp+28h]
0x140013384  add     rax, 8
0x140013388  mov     cs:ContextRecord.Rsp, rax
0x14001338f  mov     rax, cs:ContextRecord.Rip
0x140013396  mov     cs:qword_1400272D0, rax
0x14001339d  mov     cs:dword_1400272C0, 0C0000409h
0x1400133a7  mov     cs:dword_1400272C4, 1
0x1400133b1  mov     cs:dword_1400272D8, 1
0x1400133bb  mov     eax, 8
0x1400133c0  imul    rax, 0
0x1400133c4  lea     rcx, qword_1400272E0
0x1400133cb  mov     edx, [rsp+28h+arg_0]
0x1400133cf  mov     [rcx+rax], rdx
0x1400133d3  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400133da  call    __raise_securityfailure
0x1400133df  add     rsp, 28h
0x1400133e3  retn
```
