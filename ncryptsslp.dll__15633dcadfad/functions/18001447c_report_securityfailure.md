# __report_securityfailure

- ea: `0x18001447c`
- end: `0x180014502`
- name: `__report_securityfailure`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014460`

## callees

- `0x1800142b8`
- `0x18001afff`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  RtlCaptureContext_0(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_18003D950 = retaddr;
  dword_18003D940 = -1073740791;
  dword_18003D944 = 1;
  dword_18003D958 = 1;
  qword_18003D960[0] = v2;
  _raise_securityfailure(&ExceptionInfo);
}

```

## disassembly

```asm
0x18001447c  mov     [rsp+arg_0], ecx
0x180014480  sub     rsp, 28h
0x180014484  lea     rcx, ContextRecord; ContextRecord
0x18001448b  call    RtlCaptureContext_0
0x180014490  mov     rax, [rsp+28h]
0x180014495  mov     cs:ContextRecord.Rip, rax
0x18001449c  lea     rax, [rsp+28h]
0x1800144a1  add     rax, 8
0x1800144a5  mov     cs:ContextRecord.Rsp, rax
0x1800144ac  mov     rax, cs:ContextRecord.Rip
0x1800144b3  mov     cs:qword_18003D950, rax
0x1800144ba  mov     cs:dword_18003D940, 0C0000409h
0x1800144c4  mov     cs:dword_18003D944, 1
0x1800144ce  mov     cs:dword_18003D958, 1
0x1800144d8  mov     eax, 8
0x1800144dd  imul    rax, 0
0x1800144e1  lea     rcx, qword_18003D960
0x1800144e8  mov     edx, [rsp+28h+arg_0]
0x1800144ec  mov     [rcx+rax], rdx
0x1800144f0  lea     rcx, ExceptionInfo
0x1800144f7  call    __raise_securityfailure
0x1800144fc  nop
0x1800144fd  add     rsp, 28h
0x180014501  retn
```
