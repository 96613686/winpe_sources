# std::unique_ptr<Microsoft::HostGuardian::Client::CertificateCache,std::default_delete<Microsoft::HostGuardian::Client::CertificateCache>>::~unique_ptr<Microsoft::HostGuardian::Client::CertificateCache,std::default_delete<Microsoft::HostGuardian::Client::CertificateCache>>(void)

- ea: `0x18000c404`
- end: `0x18000c42d`
- name: `??1?$unique_ptr@VCertificateCache@Client@HostGuardian@Microsoft@@U?$default_delete@VCertificateCache@Client@HostGuardian@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::CertificateCache **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015d93`
- `0x180015e84`

## callees

- `0x180001bb4`
- `0x18000c404`
- `0x18000ee6c`

## pseudocode

```c
void __fastcall std::unique_ptr<Microsoft::HostGuardian::Client::CertificateCache>::~unique_ptr<Microsoft::HostGuardian::Client::CertificateCache>(
        Microsoft::HostGuardian::Client::CertificateCache **a1)
{
  Microsoft::HostGuardian::Client::CertificateCache *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000c404  push    rbx
0x18000c406  sub     rsp, 20h
0x18000c40a  mov     rbx, [rcx]
0x18000c40d  test    rbx, rbx
0x18000c410  jz      short loc_18000C427
0x18000c412  mov     rcx, rbx; this
0x18000c415  call    ??1CertificateCache@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::CertificateCache::~CertificateCache(void)
0x18000c41a  mov     edx, 30h ; '0'
0x18000c41f  mov     rcx, rbx; Block
0x18000c422  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c427  add     rsp, 20h
0x18000c42b  pop     rbx
0x18000c42c  retn
```
