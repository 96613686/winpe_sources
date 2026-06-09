# std::default_delete<DeviceEncryptionResourceManager>::operator()(DeviceEncryptionResourceManager *)

- ea: `0x180004ba4`
- end: `0x180004bcc`
- name: `??R?$default_delete@VDeviceEncryptionResourceManager@@@std@@QEBAXPEAVDeviceEncryptionResourceManager@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, FveEasNetworkStatus **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003a3c`
- `0x1800046d4`

## callees

- `0x180001bd4`
- `0x180004ba4`
- `0x18001443c`

## pseudocode

```c
void __fastcall std::default_delete<DeviceEncryptionResourceManager>::operator()(__int64 a1, FveEasNetworkStatus **a2)
{
  if ( a2 )
  {
    DeviceEncryptionResourceManager::~DeviceEncryptionResourceManager(a2, (unsigned int)a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180004ba4  test    rdx, rdx
0x180004ba7  jz      short locret_180004BCB
0x180004ba9  push    rbx
0x180004baa  sub     rsp, 20h
0x180004bae  mov     rcx, rdx; this
0x180004bb1  mov     rbx, rdx
0x180004bb4  call    ??1DeviceEncryptionResourceManager@@QEAA@XZ; DeviceEncryptionResourceManager::~DeviceEncryptionResourceManager(void)
0x180004bb9  mov     edx, 78h ; 'x'; unsigned __int64
0x180004bbe  mov     rcx, rbx; void *
0x180004bc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004bc6  add     rsp, 20h
0x180004bca  pop     rbx
0x180004bcb  retn
```
