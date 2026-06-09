# container::RegistryProvider::ModifyFlags(void *,ulong,ulong)

- ea: `0x1800297b4`
- end: `0x180029882`
- name: `?ModifyFlags@RegistryProvider@container@@YAXPEAXKK@Z`
- size: `206`
- prototype: `void __fastcall(container::RegistryProvider *this, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f560`

## callees

- `0x18000bdec`
- `0x1800297b4`
- `0x18002993c`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029831`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029853`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029853`

## string_xrefs

- `0x180029870`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
void __fastcall container::RegistryProvider::ModifyFlags(container::RegistryProvider *this, void *a2, int a3)
{
  int v4; // edi
  char *v6; // rbp
  const char *v7; // r9
  container::RegistryProvider *InBuffer; // [rsp+40h] [rbp-28h] BYREF
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF

  v4 = (int)a2;
  BytesReturned = 0;
  v6 = (char *)container::RegistryProvider::OpenRegistryDriver(this);
  InBuffer = this;
  v9 = v4;
  v10 = a3;
  if ( !DeviceIoControl(v6, 0x220010u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v7);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x1800297b4  mov     rax, rsp
0x1800297b7  mov     [rax+18h], rbx
0x1800297bb  push    rbp
0x1800297bc  push    rsi
0x1800297bd  push    rdi
0x1800297be  sub     rsp, 50h
0x1800297c2  mov     esi, r8d
0x1800297c5  mov     edi, edx
0x1800297c7  mov     rbx, rcx
0x1800297ca  mov     dword ptr [rax+10h], 0
0x1800297d1  mov     qword ptr [rax+8], 0
0x1800297d9  xorps   xmm0, xmm0
0x1800297dc  movups  xmmword ptr [rax-28h], xmm0
0x1800297e0  call    ?OpenRegistryDriver@RegistryProvider@container@@YAPEAXXZ; container::RegistryProvider::OpenRegistryDriver(void)
0x1800297e5  mov     rbp, rax
0x1800297e8  mov     [rsp+68h+arg_0], rax
0x1800297ed  mov     [rsp+68h+InBuffer], rbx
0x1800297f2  mov     [rsp+68h+var_20], edi
0x1800297f6  mov     [rsp+68h+var_1C], esi
0x1800297fa  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180029803  lea     rax, [rsp+68h+BytesReturned]
0x180029808  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18002980d  mov     [rsp+68h+nOutBufferSize], 0; nOutBufferSize
0x180029815  mov     [rsp+68h+lpOutBuffer], 0; lpOutBuffer
0x18002981e  mov     r9d, 10h; nInBufferSize
0x180029824  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x180029829  mov     edx, 220010h; dwIoControlCode
0x18002982e  mov     rcx, rbp; hDevice
0x180029831  call    cs:__imp_DeviceIoControl
0x180029838  nop     dword ptr [rax+rax+00h]
0x18002983d  mov     rcx, [rsp+68h]; this
0x180029842  test    eax, eax
0x180029844  jz      short loc_180029870
0x180029846  lea     rax, [rbp-1]
0x18002984a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002984e  ja      short loc_18002985F
0x180029850  mov     rcx, rbp; hObject
0x180029853  call    cs:__imp_CloseHandle
0x18002985a  nop     dword ptr [rax+rax+00h]
0x18002985f  mov     rbx, [rsp+68h+arg_10]
0x180029867  add     rsp, 50h
0x18002986b  pop     rdi
0x18002986c  pop     rsi
0x18002986d  pop     rbp
0x18002986e  retn
0x180029870  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029877  mov     edx, 16Fh; void *
0x18002987c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
