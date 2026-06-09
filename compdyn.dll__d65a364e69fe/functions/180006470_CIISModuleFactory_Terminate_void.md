# CIISModuleFactory::Terminate(void)

- ea: `0x180006470`
- end: `0x1800064e0`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `112`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004250`
- `0x180006470`
- `0x180006e14`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800064a4`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800064a4`

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
0x180006470  mov     [rsp+arg_0], rbx
0x180006475  push    rdi
0x180006476  sub     rsp, 20h
0x18000647a  cmp     cs:?g_fHttpCompressionInited@@3HA, 0; int g_fHttpCompressionInited
0x180006481  mov     rbx, rcx
0x180006484  jz      short loc_180006495
0x180006486  call    ?Terminate@HTTP_COMPRESSION@@SAXXZ; HTTP_COMPRESSION::Terminate(void)
0x18000648b  mov     cs:?g_fHttpCompressionInited@@3HA, 0; int g_fHttpCompressionInited
0x180006495  mov     rdi, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x18000649c  test    rdi, rdi
0x18000649f  jz      short loc_1800064B2
0x1800064a1  mov     rcx, rdi
0x1800064a4  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800064aa  mov     rcx, rdi; Block
0x1800064ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800064b2  mov     cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA, 0; CReaderWriterLock3 * g_pCompressionLock
0x1800064bd  test    rbx, rbx
0x1800064c0  jz      short loc_1800064D5
0x1800064c2  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x1800064c9  mov     rcx, rbx; Block
0x1800064cc  mov     [rbx+8], rax
0x1800064d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800064d5  mov     rbx, [rsp+28h+arg_0]
0x1800064da  add     rsp, 20h
0x1800064de  pop     rdi
0x1800064df  retn
```
