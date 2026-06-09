# MkvMfSourceLib::MkvMfByteStreamHandler::~MkvMfByteStreamHandler(void)

- ea: `0x18000aba0`
- end: `0x18000abd1`
- name: `??1MkvMfByteStreamHandler@MkvMfSourceLib@@UEAA@XZ`
- size: `49`
- prototype: `void __fastcall(MkvMfSourceLib::MkvMfByteStreamHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac30`

## callees

- `0x180005ab8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000abb6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000abb6`

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
0x18000aba0  push    rbx
0x18000aba2  sub     rsp, 20h
0x18000aba6  mov     rbx, rcx
0x18000aba9  add     rcx, 60h ; '`'
0x18000abad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000abb2  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000abb6  call    cs:__imp_DeleteCriticalSection
0x18000abbc  lea     rcx, [rbx+28h]
0x18000abc0  mov     dword ptr [rbx+34h], 0C0000001h
0x18000abc7  add     rsp, 20h
0x18000abcb  pop     rbx
0x18000abcc  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
