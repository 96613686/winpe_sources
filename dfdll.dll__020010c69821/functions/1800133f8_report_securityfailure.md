# __report_securityfailure

- ea: `0x1800133f8`
- end: `0x180013494`
- name: `__report_securityfailure`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800133e4`

## callees

- `0x1800132d8`
- `0x1800133f8`
- `0x180013494`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180013405`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180013405`

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
  qword_18002DAB0 = retaddr;
  dword_18002DAA0 = -1073740791;
  dword_18002DAA4 = 1;
  dword_18002DAB8 = 1;
  qword_18002DAC0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800133f8  mov     [rsp+arg_0], ecx
0x1800133fc  sub     rsp, 28h
0x180013400  mov     ecx, 17h; ProcessorFeature
0x180013405  call    cs:__imp_IsProcessorFeaturePresent
0x18001340b  test    eax, eax
0x18001340d  jz      short loc_180013417
0x18001340f  mov     eax, [rsp+28h+arg_0]
0x180013413  mov     ecx, eax
0x180013415  int     29h; Win8: RtlFailFast(ecx)
0x180013417  lea     rcx, ContextRecord; ContextRecord
0x18001341e  call    capture_current_context
0x180013423  mov     rax, [rsp+28h]
0x180013428  mov     cs:ContextRecord.Rip, rax
0x18001342f  lea     rax, [rsp+28h]
0x180013434  add     rax, 8
0x180013438  mov     cs:ContextRecord.Rsp, rax
0x18001343f  mov     rax, cs:ContextRecord.Rip
0x180013446  mov     cs:qword_18002DAB0, rax
0x18001344d  mov     cs:dword_18002DAA0, 0C0000409h
0x180013457  mov     cs:dword_18002DAA4, 1
0x180013461  mov     cs:dword_18002DAB8, 1
0x18001346b  mov     eax, 8
0x180013470  imul    rax, 0
0x180013474  lea     rcx, qword_18002DAC0
0x18001347b  mov     edx, [rsp+28h+arg_0]
0x18001347f  mov     [rcx+rax], rdx
0x180013483  lea     rcx, ExceptionInfo; ExceptionInfo
0x18001348a  call    __raise_securityfailure
0x18001348f  add     rsp, 28h
0x180013493  retn
```
