# container::RegistryProvider::GetVirtualRootHandle(void *,_VR_ROOT_KEY)

- ea: `0x1800296a8`
- end: `0x180029777`
- name: `?GetVirtualRootHandle@RegistryProvider@container@@YAPEAXPEAXW4_VR_ROOT_KEY@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(container::RegistryProvider *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000dd70`
- `0x18000e5a0`
- `0x180012280`

## callees

- `0x18000bdec`
- `0x1800296a8`
- `0x18002993c`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029726`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029726`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002974d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002974d`

## string_xrefs

- `0x180029765`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall container::RegistryProvider::GetVirtualRootHandle(container::RegistryProvider *a1, int a2)
{
  char *v4; // rsi
  const char *v5; // r9
  __int64 v6; // rbx
  __int128 InBuffer; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 OutBuffer; // [rsp+70h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF
  char *v12; // [rsp+80h] [rbp+18h]

  BytesReturned = 0;
  v12 = 0;
  InBuffer = 0;
  OutBuffer = 0;
  v4 = (char *)container::RegistryProvider::OpenRegistryDriver(a1);
  v12 = v4;
  *(_QWORD *)&InBuffer = a1;
  DWORD2(InBuffer) = a2;
  if ( !DeviceIoControl(v4, 0x22001Cu, &InBuffer, 0x10u, &OutBuffer, 8u, &BytesReturned, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v5);
  v6 = OutBuffer;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return v6;
}

```

## disassembly

```asm
0x1800296a8  mov     rax, rsp
0x1800296ab  push    rbx
0x1800296ac  push    rsi
0x1800296ad  push    rdi
0x1800296ae  sub     rsp, 50h
0x1800296b2  mov     edi, edx
0x1800296b4  mov     rbx, rcx
0x1800296b7  mov     dword ptr [rax+10h], 0
0x1800296be  mov     qword ptr [rax+18h], 0
0x1800296c6  xorps   xmm0, xmm0
0x1800296c9  movups  xmmword ptr [rax-28h], xmm0
0x1800296cd  mov     qword ptr [rax+8], 0
0x1800296d5  call    ?OpenRegistryDriver@RegistryProvider@container@@YAPEAXXZ; container::RegistryProvider::OpenRegistryDriver(void)
0x1800296da  mov     rsi, rax
0x1800296dd  mov     [rsp+68h+arg_10], rax
0x1800296e5  mov     [rsp+68h+InBuffer], rbx
0x1800296ea  mov     [rsp+68h+var_20], edi
0x1800296ee  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800296f7  lea     rax, [rsp+68h+BytesReturned]
0x1800296fc  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180029701  mov     [rsp+68h+nOutBufferSize], 8; nOutBufferSize
0x180029709  lea     rax, [rsp+68h+OutBuffer]
0x18002970e  mov     [rsp+68h+lpOutBuffer], rax; lpOutBuffer
0x180029713  mov     r9d, 10h; nInBufferSize
0x180029719  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x18002971e  mov     edx, 22001Ch; dwIoControlCode
0x180029723  mov     rcx, rsi; hDevice
0x180029726  call    cs:__imp_DeviceIoControl
0x18002972d  nop     dword ptr [rax+rax+00h]
0x180029732  mov     rcx, [rsp+68h]; this
0x180029737  test    eax, eax
0x180029739  jz      short loc_180029765
0x18002973b  mov     rbx, [rsp+68h+OutBuffer]
0x180029740  lea     rcx, [rsi-1]
0x180029744  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180029748  ja      short loc_180029759
0x18002974a  mov     rcx, rsi; hObject
0x18002974d  call    cs:__imp_CloseHandle
0x180029754  nop     dword ptr [rax+rax+00h]
0x180029759  mov     rax, rbx
0x18002975c  add     rsp, 50h
0x180029760  pop     rdi
0x180029761  pop     rsi
0x180029762  pop     rbx
0x180029763  retn
0x180029765  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002976c  mov     edx, 13Ah; void *
0x180029771  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
