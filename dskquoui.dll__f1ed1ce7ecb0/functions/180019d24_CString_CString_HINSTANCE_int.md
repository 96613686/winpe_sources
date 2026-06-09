# CString::CString(HINSTANCE__ *,int,...)

- ea: `0x180019d24`
- end: `0x180019d6b`
- name: `??0CString@@QEAA@PEAUHINSTANCE__@@HZZ`
- size: `71`
- prototype: `CString *(CString *__hidden this, HINSTANCE, int, ...)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ebc`
- `0x180006a38`
- `0x180006c54`
- `0x18000729c`
- `0x1800081ec`
- `0x1800098ac`
- `0x18000b8fc`
- `0x18000c8c4`
- `0x1800101b4`
- `0x18001058c`
- `0x180012e94`
- `0x180013d44`
- `0x180014604`
- `0x180016f08`
- `0x1800177fc`
- `0x1800180a8`
- `0x1800184c0`
- `0x1800190e4`
- `0x1800196b0`
- `0x180019a54`
- `0x18001ab24`
- `0x18001abb8`

## callees

- `0x18001a30c`

## pseudocode

```c
CString *CString::CString(CString *this, HINSTANCE a2, DWORD a3, ...)
{
  va_list v5; // [rsp+20h] [rbp-18h] BYREF
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)this = &CString::`vftable';
  *((_QWORD *)this + 1) = 0;
  va_copy(v5, va);
  CString::Format(this, a2, a3, &v5);
  return this;
}

```

## disassembly

```asm
0x180019d24  mov     r11, rsp
0x180019d27  mov     [r11+18h], r8d
0x180019d2b  mov     [r11+20h], r9
0x180019d2f  push    rbx
0x180019d30  sub     rsp, 30h
0x180019d34  lea     rax, ??_7CString@@6B@; const CString::`vftable'
0x180019d3b  mov     qword ptr [r11-18h], 0
0x180019d43  mov     [rcx], rax
0x180019d46  lea     r9, [r11-18h]; char **
0x180019d4a  lea     rax, [r11+20h]
0x180019d4e  mov     qword ptr [rcx+8], 0
0x180019d56  mov     [r11-18h], rax
0x180019d5a  mov     rbx, rcx
0x180019d5d  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IPEAPEAD@Z; CString::Format(HINSTANCE__ *,uint,char * *)
0x180019d62  mov     rax, rbx
0x180019d65  add     rsp, 30h
0x180019d69  pop     rbx
0x180019d6a  retn
```
