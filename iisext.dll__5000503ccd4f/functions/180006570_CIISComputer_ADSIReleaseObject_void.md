# CIISComputer::ADSIReleaseObject(void)

- ea: `0x180006570`
- end: `0x180006597`
- name: `?ADSIReleaseObject@CIISComputer@@UEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x1800064a0`
- `0x180006570`

## pseudocode

```c
__int64 __fastcall CIISComputer::ADSIReleaseObject(CIISComputer *this)
{
  char *v1; // rbx

  v1 = (char *)this - 8;
  if ( this != (CIISComputer *)8 )
  {
    CIISComputer::~CIISComputer((CIISComputer *)((char *)this - 8));
    operator delete(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180006570  push    rbx
0x180006572  sub     rsp, 20h
0x180006576  lea     rbx, [rcx-8]
0x18000657a  test    rbx, rbx
0x18000657d  jz      short loc_18000658F
0x18000657f  mov     rcx, rbx; this
0x180006582  call    ??1CIISComputer@@QEAA@XZ; CIISComputer::~CIISComputer(void)
0x180006587  mov     rcx, rbx; Block
0x18000658a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000658f  xor     eax, eax
0x180006591  add     rsp, 20h
0x180006595  pop     rbx
0x180006596  retn
```
