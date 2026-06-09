# CClfsDriver::Finalize(void)

- ea: `0x140035590`
- end: `0x140035653`
- name: `?Finalize@CClfsDriver@@QEAAJXZ`
- size: `195`
- prototype: `__int64 __fastcall(CClfsDriver *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x14003599c`
- `0x140035cc4`

## callees

- `0x140035590`
- `0x140035660`
- `0x14005293c`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140035625`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140035625`
- `ntoskrnl!IoUnregisterFileSystem` at `0x1400355f3`
- `ntoskrnl!IoUnregisterFileSystem` at `0x1400355f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035614`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035614`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400355ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400355ce`

## pseudocode

```c
__int64 __fastcall CClfsDriver::Finalize(CClfsDriver *this)
{
  PVOID v1; // rdi
  struct _DEVICE_OBJECT *v3; // rsi
  unsigned int v4; // eax
  __int64 result; // rax
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  v1 = ClfsMgmtCollectionGlobalInstance;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v3 = *(struct _DEVICE_OBJECT **)(*((_QWORD *)this + 1) + 8LL);
  if ( ClfsMgmtCollectionGlobalInstance )
  {
    CClfsManagedLogCollection::~CClfsManagedLogCollection((CClfsManagedLogCollection *)ClfsMgmtCollectionGlobalInstance);
    ExFreePoolWithTag(v1, 0);
    ClfsMgmtCollectionGlobalInstance = 0;
  }
  ClfsFinalize();
  v4 = *(_DWORD *)this;
  if ( (*(_DWORD *)this & 2) != 0 )
  {
    IoUnregisterFileSystem(v3);
    *(_DWORD *)this &= ~2u;
    v4 = *(_DWORD *)this;
  }
  if ( (v4 & 8) != 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\??\\LOG:");
    IoDeleteSymbolicLink(&DestinationString);
    v4 = *(_DWORD *)this & 0xFFFFFFF7;
  }
  *(_DWORD *)this = v4;
  result = 0;
  *((_QWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x140035590  mov     r11, rsp
0x140035593  mov     [r11+8], rbx
0x140035597  mov     [r11+10h], rsi
0x14003559b  push    rdi
0x14003559c  sub     rsp, 30h
0x1400355a0  mov     rdi, cs:?ClfsMgmtCollectionGlobalInstance@@3PEAVCClfsManagedLogCollection@@EA; CClfsManagedLogCollection * ClfsMgmtCollectionGlobalInstance
0x1400355a7  xor     eax, eax
0x1400355a9  mov     [r11-18h], rax
0x1400355ad  mov     rbx, rcx
0x1400355b0  mov     [r11-10h], rax
0x1400355b4  mov     rax, [rcx+8]
0x1400355b8  mov     rsi, [rax+8]
0x1400355bc  test    rdi, rdi
0x1400355bf  jz      short loc_1400355E5
0x1400355c1  mov     rcx, rdi; this
0x1400355c4  call    ??1CClfsManagedLogCollection@@AEAA@XZ; CClfsManagedLogCollection::~CClfsManagedLogCollection(void)
0x1400355c9  xor     edx, edx; Tag
0x1400355cb  mov     rcx, rdi; P
0x1400355ce  call    cs:__imp_ExFreePoolWithTag
0x1400355d5  nop     dword ptr [rax+rax+00h]
0x1400355da  mov     cs:?ClfsMgmtCollectionGlobalInstance@@3PEAVCClfsManagedLogCollection@@EA, 0; CClfsManagedLogCollection * ClfsMgmtCollectionGlobalInstance
0x1400355e5  call    ClfsFinalize
0x1400355ea  mov     eax, [rbx]
0x1400355ec  test    al, 2
0x1400355ee  jz      short loc_140035604
0x1400355f0  mov     rcx, rsi; DeviceObject
0x1400355f3  call    cs:__imp_IoUnregisterFileSystem
0x1400355fa  nop     dword ptr [rax+rax+00h]
0x1400355ff  and     dword ptr [rbx], 0FFFFFFFDh
0x140035602  mov     eax, [rbx]
0x140035604  test    al, 8
0x140035606  jz      short loc_140035636
0x140035608  lea     rdx, aLog; "\\??\\LOG:"
0x14003560f  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140035614  call    cs:__imp_RtlInitUnicodeString
0x14003561b  nop     dword ptr [rax+rax+00h]
0x140035620  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x140035625  call    cs:__imp_IoDeleteSymbolicLink
0x14003562c  nop     dword ptr [rax+rax+00h]
0x140035631  mov     eax, [rbx]
0x140035633  and     eax, 0FFFFFFF7h
0x140035636  mov     rsi, [rsp+38h+arg_8]
0x14003563b  mov     [rbx], eax
0x14003563d  xor     eax, eax
0x14003563f  mov     qword ptr [rbx+8], 0
0x140035647  mov     rbx, [rsp+38h+arg_0]
0x14003564c  add     rsp, 30h
0x140035650  pop     rdi
0x140035651  retn
```
