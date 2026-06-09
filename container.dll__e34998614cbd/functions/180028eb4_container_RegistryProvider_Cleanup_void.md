# container::RegistryProvider::Cleanup(void *)

- ea: `0x180028eb4`
- end: `0x180028f4e`
- name: `?Cleanup@RegistryProvider@container@@YAXPEAX@Z`
- size: `154`
- prototype: `void __fastcall(container::RegistryProvider *__hidden this, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800052b8`
- `0x18000d134`
- `0x18000d8f0`
- `0x180028b68`

## callees

- `0x18000bdec`
- `0x180028eb4`
- `0x18002993c`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180028f02`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180028f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f24`

## string_xrefs

- `0x180028f3d`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall container::RegistryProvider::Cleanup(container::RegistryProvider *this, void *a2)
{
  char *v3; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // [rsp+0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF
  container::RegistryProvider *InBuffer; // [rsp+60h] [rbp+18h] BYREF
  char *v10; // [rsp+68h] [rbp+20h]

  try
  {
    v3 = (char *)container::RegistryProvider::OpenRegistryDriver(this);
    v10 = v3;
    InBuffer = this;
    BytesReturned = 0;
    if ( !DeviceIoControl(v3, 0x220018u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        v5);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, &v6, v4, v5);
  }
}

```

## disassembly

```asm
0x180028eb4  mov     [rsp+arg_0], rbx
0x180028eb9  push    rdi
0x180028eba  sub     rsp, 40h
0x180028ebe  mov     rdi, rcx
0x180028ec1  call    ?OpenRegistryDriver@RegistryProvider@container@@YAPEAXXZ; container::RegistryProvider::OpenRegistryDriver(void)
0x180028ec6  mov     rbx, rax
0x180028ec9  mov     [rsp+48h+arg_18], rax
0x180028ece  mov     [rsp+48h+InBuffer], rdi
0x180028ed3  xor     edi, edi
0x180028ed5  mov     [rsp+48h+BytesReturned], edi
0x180028ed9  mov     [rsp+48h+lpOverlapped], rdi; lpOverlapped
0x180028ede  lea     rax, [rsp+48h+BytesReturned]
0x180028ee3  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180028ee8  mov     [rsp+48h+nOutBufferSize], edi; nOutBufferSize
0x180028eec  mov     [rsp+48h+lpOutBuffer], rdi; lpOutBuffer
0x180028ef1  lea     r9d, [rdi+8]; nInBufferSize
0x180028ef5  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x180028efa  mov     edx, 220018h; dwIoControlCode
0x180028eff  mov     rcx, rbx; hDevice
0x180028f02  call    cs:__imp_DeviceIoControl
0x180028f09  nop     dword ptr [rax+rax+00h]
0x180028f0e  mov     rcx, [rsp+48h]; this
0x180028f13  test    eax, eax
0x180028f15  jz      short loc_180028F3D
0x180028f17  lea     rax, [rbx-1]
0x180028f1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028f1f  ja      short loc_180028F31
0x180028f21  mov     rcx, rbx; hObject
0x180028f24  call    cs:__imp_CloseHandle
0x180028f2b  nop     dword ptr [rax+rax+00h]
0x180028f30  nop
0x180028f31  mov     rbx, [rsp+48h+arg_0]
0x180028f36  add     rsp, 40h
0x180028f3a  pop     rdi
0x180028f3b  retn
0x180028f3d  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180028f44  lea     edx, [rdi+3Fh]; void *
0x180028f47  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
