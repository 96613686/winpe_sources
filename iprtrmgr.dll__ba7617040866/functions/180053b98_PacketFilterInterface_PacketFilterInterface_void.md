# PacketFilterInterface::~PacketFilterInterface(void)

- ea: `0x180053b98`
- end: `0x180053c07`
- name: `??1PacketFilterInterface@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(PacketFilterInterface *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180053c10`

## callees

- `0x180053b98`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180053bf2`
- `ntdll!NtDeviceIoControlFile` at `0x180053bf2`
- `KERNEL32!DeleteCriticalSection` at `0x180053c00`

## pseudocode

```c
void __fastcall PacketFilterInterface::~PacketFilterInterface(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  struct _IO_STATUS_BLOCK v3; // [rsp+50h] [rbp-18h] BYREF
  __int64 v4; // [rsp+70h] [rbp+8h] BYREF

  if ( !HIDWORD(this[1].OwningThread) )
  {
    v4 = *(_QWORD *)&this[1].LockCount;
    DebugInfo = this[1].DebugInfo;
    v3 = 0;
    NtDeviceIoControlFile(DebugInfo, 0, 0, 0, &v3, 0x12802Cu, &v4, 8u, &v4, 8u);
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180053b98  mov     r11, rsp
0x180053b9b  push    rbx
0x180053b9c  sub     rsp, 60h
0x180053ba0  cmp     dword ptr [rcx+3Ch], 0
0x180053ba4  mov     rbx, rcx
0x180053ba7  jnz     short loc_180053BF8
0x180053ba9  mov     rax, [rcx+30h]
0x180053bad  xorps   xmm0, xmm0
0x180053bb0  mov     [r11+8], rax
0x180053bb4  mov     ecx, 8
0x180053bb9  mov     [rsp+68h+OutputBufferLength], ecx; OutputBufferLength
0x180053bbd  lea     rax, [r11+8]
0x180053bc1  mov     [r11-28h], rax
0x180053bc5  xor     r9d, r9d; ApcContext
0x180053bc8  mov     [rsp+68h+InputBufferLength], ecx; InputBufferLength
0x180053bcc  lea     rax, [r11+8]
0x180053bd0  mov     rcx, [rbx+28h]; FileHandle
0x180053bd4  xor     r8d, r8d; ApcRoutine
0x180053bd7  mov     [r11-38h], rax
0x180053bdb  xor     edx, edx; Event
0x180053bdd  lea     rax, [r11-18h]
0x180053be1  mov     [rsp+68h+IoControlCode], 12802Ch; IoControlCode
0x180053be9  mov     [r11-48h], rax
0x180053bed  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180053bf2  call    cs:__imp_NtDeviceIoControlFile
0x180053bf8  mov     rcx, rbx
0x180053bfb  add     rsp, 60h
0x180053bff  pop     rbx
0x180053c00  jmp     cs:__imp_DeleteCriticalSection
```
