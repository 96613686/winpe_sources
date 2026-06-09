# Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)

- ea: `0x18000ba64`
- end: `0x18000ba82`
- name: `?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800081c4`
- `0x180009fb0`
- `0x18000a9cc`
- `0x18000aefc`
- `0x18000b3e8`
- `0x18000ba9c`
- `0x18000bb44`
- `0x180011290`

## callees

- `0x180007dd0`
- `0x18000ba64`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(
        volatile int **a1)
{
  volatile int *v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  result = 0;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(
             (__int64)v1,
             v1);
  }
  return result;
}

```

## disassembly

```asm
0x18000ba64  sub     rsp, 28h
0x18000ba68  mov     rdx, [rcx]
0x18000ba6b  xor     eax, eax
0x18000ba6d  test    rdx, rdx
0x18000ba70  jz      short loc_18000BA7D
0x18000ba72  mov     [rcx], rax
0x18000ba75  mov     rcx, rdx
0x18000ba78  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x18000ba7d  add     rsp, 28h
0x18000ba81  retn
```
