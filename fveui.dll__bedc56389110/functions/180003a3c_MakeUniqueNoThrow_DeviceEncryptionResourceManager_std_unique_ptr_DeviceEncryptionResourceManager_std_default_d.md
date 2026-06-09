# MakeUniqueNoThrow<DeviceEncryptionResourceManager>(std::unique_ptr<DeviceEncryptionResourceManager,std::default_delete<DeviceEncryptionResourceManager>> &)

- ea: `0x180003a3c`
- end: `0x180003a85`
- name: `??$MakeUniqueNoThrow@VDeviceEncryptionResourceManager@@@@YAJAEAV?$unique_ptr@VDeviceEncryptionResourceManager@@U?$default_delete@VDeviceEncryptionResourceManager@@@std@@@std@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(DeviceEncryptionResourceManager **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c1a0`

## callees

- `0x180001c00`
- `0x180003a3c`
- `0x180004ba4`
- `0x1800141ec`

## pseudocode

```c
__int64 __fastcall MakeUniqueNoThrow<DeviceEncryptionResourceManager>(DeviceEncryptionResourceManager **a1)
{
  unsigned int v2; // ebx
  DeviceEncryptionResourceManager *v3; // rcx
  DeviceEncryptionResourceManager *v4; // rax
  DeviceEncryptionResourceManager *v5; // rdx

  try
  {
    v2 = 0;
    v3 = (DeviceEncryptionResourceManager *)operator new(0x78u);
    v4 = DeviceEncryptionResourceManager::DeviceEncryptionResourceManager(v3);
    v5 = *a1;
    *a1 = v4;
    if ( v5 )
      std::default_delete<DeviceEncryptionResourceManager>::operator()();
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  v2 = 0;
}

```

## disassembly

```asm
0x180003a3c  mov     [rsp+arg_0], rbx
0x180003a41  push    rdi
0x180003a42  sub     rsp, 20h
0x180003a46  mov     rdi, rcx
0x180003a49  xor     ebx, ebx
0x180003a4b  lea     ecx, [rbx+78h]; Size
0x180003a4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a53  mov     [rsp+28h+arg_8], rax
0x180003a58  mov     rcx, rax; this
0x180003a5b  call    ??0DeviceEncryptionResourceManager@@QEAA@XZ; DeviceEncryptionResourceManager::DeviceEncryptionResourceManager(void)
0x180003a60  nop
0x180003a61  mov     rdx, [rdi]
0x180003a64  mov     [rdi], rax
0x180003a67  test    rdx, rdx
0x180003a6a  jz      short loc_180003A72
0x180003a6c  call    ??R?$default_delete@VDeviceEncryptionResourceManager@@@std@@QEBAXPEAVDeviceEncryptionResourceManager@@@Z; std::default_delete<DeviceEncryptionResourceManager>::operator()(DeviceEncryptionResourceManager *)
0x180003a71  nop
0x180003a72  jmp     short loc_180003A78
0x180003a74  mov     ebx, dword ptr [rsp+28h+arg_8]
0x180003a78  mov     eax, ebx
0x180003a7a  mov     rbx, [rsp+28h+arg_0]
0x180003a7f  add     rsp, 20h
0x180003a83  pop     rdi
0x180003a84  retn
```
