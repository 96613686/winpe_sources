# CIISModuleFactory::Terminate(void)

- ea: `0x180007ef0`
- end: `0x180007f60`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `112`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800054a0`
- `0x180007ef0`
- `0x180008904`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180007f24`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180007f24`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  void *v2; // rdi

  if ( g_fHttpCompressionInited )
  {
    HTTP_COMPRESSION::Terminate();
    g_fHttpCompressionInited = 0;
  }
  v2 = g_pCompressionLock;
  if ( g_pCompressionLock )
  {
    CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)g_pCompressionLock);
    operator delete(v2);
  }
  g_pCompressionLock = 0;
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180007ef0  mov     [rsp+arg_0], rbx
0x180007ef5  push    rdi
0x180007ef6  sub     rsp, 20h
0x180007efa  cmp     cs:?g_fHttpCompressionInited@@3HA, 0; int g_fHttpCompressionInited
0x180007f01  mov     rbx, rcx
0x180007f04  jz      short loc_180007F15
0x180007f06  call    ?Terminate@HTTP_COMPRESSION@@SAXXZ; HTTP_COMPRESSION::Terminate(void)
0x180007f0b  mov     cs:?g_fHttpCompressionInited@@3HA, 0; int g_fHttpCompressionInited
0x180007f15  mov     rdi, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x180007f1c  test    rdi, rdi
0x180007f1f  jz      short loc_180007F32
0x180007f21  mov     rcx, rdi
0x180007f24  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180007f2a  mov     rcx, rdi; Block
0x180007f2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f32  mov     cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA, 0; CReaderWriterLock3 * g_pCompressionLock
0x180007f3d  test    rbx, rbx
0x180007f40  jz      short loc_180007F55
0x180007f42  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180007f49  mov     rcx, rbx; Block
0x180007f4c  mov     [rbx+8], rax
0x180007f50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f55  mov     rbx, [rsp+28h+arg_0]
0x180007f5a  add     rsp, 20h
0x180007f5e  pop     rdi
0x180007f5f  retn
```
