# details::ResolvePhysicalInterfaceWorkItem::ResolvePhysicalInterfaceWorkItem(void)

- ea: `0x18005e08c`
- end: `0x18005e11c`
- name: `??0ResolvePhysicalInterfaceWorkItem@details@@QEAA@XZ`
- size: `144`
- prototype: `details::ResolvePhysicalInterfaceWorkItem *__fastcall(details::ResolvePhysicalInterfaceWorkItem *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005e2e4`

## callees

- `0x180047f78`
- `0x180047fa8`
- `0x18005e08c`
- `0x18005e124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e0d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e0d4`

## string_xrefs

- `0x18005e0f0`: `Unable to create DoneEvent for ResolvePhysicalInterfaceWorkItem`

## pseudocode

```c
details::ResolvePhysicalInterfaceWorkItem *__fastcall details::ResolvePhysicalInterfaceWorkItem::ResolvePhysicalInterfaceWorkItem(
        details::ResolvePhysicalInterfaceWorkItem *this)
{
  HANDLE EventW; // rax
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  memset_0(this, 0, 0x80u);
  *((_QWORD *)this + 16) = 0;
  *(GUID *)((char *)this + 136) = GUID_NULL;
  *((_DWORD *)this + 38) = 2;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 20) = EventW;
  *((_DWORD *)this + 42) = 258;
  if ( !EventW )
  {
    std::exception::exception(
      (std::exception *)pExceptionObject,
      "Unable to create DoneEvent for ResolvePhysicalInterfaceWorkItem");
    throw (std::exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18005e08c  push    rbx
0x18005e08e  sub     rsp, 40h
0x18005e092  mov     rbx, rcx
0x18005e095  mov     [rsp+48h+var_28], rcx
0x18005e09a  xor     edx, edx; Val
0x18005e09c  mov     r8d, 80h; Size
0x18005e0a2  call    memset_0
0x18005e0a7  xor     eax, eax
0x18005e0a9  mov     [rbx+80h], rax
0x18005e0b0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18005e0b7  movdqu  xmmword ptr [rbx+88h], xmm0
0x18005e0bf  mov     dword ptr [rbx+98h], 2
0x18005e0c9  xor     r9d, r9d; lpName
0x18005e0cc  xor     r8d, r8d; bInitialState
0x18005e0cf  lea     edx, [rax+1]; bManualReset
0x18005e0d2  xor     ecx, ecx; lpEventAttributes
0x18005e0d4  call    cs:__imp_CreateEventW
0x18005e0da  mov     [rbx+0A0h], rax
0x18005e0e1  mov     dword ptr [rbx+0A8h], 102h
0x18005e0eb  test    rax, rax
0x18005e0ee  jnz     short loc_18005E113
0x18005e0f0  lea     rdx, aUnableToCreate; "Unable to create DoneEvent for ResolveP"...
0x18005e0f7  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18005e0fc  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18005e101  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x18005e108  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18005e10d  call    _CxxThrowException_0
0x18005e113  mov     rax, rbx
0x18005e116  add     rsp, 40h
0x18005e11a  pop     rbx
0x18005e11b  retn
```
