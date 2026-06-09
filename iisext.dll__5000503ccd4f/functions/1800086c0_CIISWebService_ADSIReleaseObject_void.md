# CIISWebService::ADSIReleaseObject(void)

- ea: `0x1800086c0`
- end: `0x1800086e7`
- name: `?ADSIReleaseObject@CIISWebService@@UEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180001048`
- `0x1800085f0`
- `0x1800086c0`

## pseudocode

```c
__int64 __fastcall CIISWebService::ADSIReleaseObject(CIISWebService *this)
{
  char *v1; // rbx

  v1 = (char *)this - 8;
  if ( this != (CIISWebService *)8 )
  {
    CIISWebService::~CIISWebService((CIISWebService *)((char *)this - 8));
    operator delete(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800086c0  push    rbx
0x1800086c2  sub     rsp, 20h
0x1800086c6  lea     rbx, [rcx-8]
0x1800086ca  test    rbx, rbx
0x1800086cd  jz      short loc_1800086DF
0x1800086cf  mov     rcx, rbx; this
0x1800086d2  call    ??1CIISWebService@@QEAA@XZ; CIISWebService::~CIISWebService(void)
0x1800086d7  mov     rcx, rbx; Block
0x1800086da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800086df  xor     eax, eax
0x1800086e1  add     rsp, 20h
0x1800086e5  pop     rbx
0x1800086e6  retn
```
