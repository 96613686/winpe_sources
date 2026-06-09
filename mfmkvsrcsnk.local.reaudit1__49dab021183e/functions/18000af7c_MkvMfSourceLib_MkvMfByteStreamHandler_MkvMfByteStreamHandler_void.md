# MkvMfSourceLib::MkvMfByteStreamHandler::~MkvMfByteStreamHandler(void)

- ea: `0x18000af7c`
- end: `0x18000afb3`
- name: `??1MkvMfByteStreamHandler@MkvMfSourceLib@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(MkvMfSourceLib::MkvMfByteStreamHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b010`

## callees

- `0x180005c68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af92`

## pseudocode

```c
void __fastcall MkvMfSourceLib::MkvMfByteStreamHandler::~MkvMfByteStreamHandler(
        MkvMfSourceLib::MkvMfByteStreamHandler *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *((_DWORD *)this + 13) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 40);
}

```

## disassembly

```asm
0x18000af7c  push    rbx
0x18000af7e  sub     rsp, 20h
0x18000af82  mov     rbx, rcx
0x18000af85  add     rcx, 60h ; '`'
0x18000af89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000af8e  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000af92  call    cs:__imp_DeleteCriticalSection
0x18000af99  nop     dword ptr [rax+rax+00h]
0x18000af9e  lea     rcx, [rbx+28h]
0x18000afa2  mov     dword ptr [rbx+34h], 0C0000001h
0x18000afa9  add     rsp, 20h
0x18000afad  pop     rbx
0x18000afae  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
