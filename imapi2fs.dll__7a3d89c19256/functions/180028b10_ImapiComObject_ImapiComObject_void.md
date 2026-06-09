# ImapiComObject::~ImapiComObject(void)

- ea: `0x180028b10`
- end: `0x180028b46`
- name: `??1ImapiComObject@@UEAA@XZ`
- size: `54`
- prototype: `void __fastcall(ImapiComObject *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028a94`
- `0x180028b4c`
- `0x180028ee0`
- `0x18002b638`
- `0x18008450c`
- `0x1800846ed`

## callees

- `0x18000c8d0`
- `0x180028b10`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180028b32`
- `KERNEL32!DeleteCriticalSection` at `0x180028b32`

## pseudocode

```c
void __fastcall ImapiComObject::~ImapiComObject(ImapiComObject *this)
{
  char v2; // al

  *(_QWORD *)this = &ImapiComObject::`vftable';
  v2 = *((_BYTE *)this + 16);
  *((_BYTE *)this + 16) = 0;
  if ( v2 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>((char *)this + 8);
}

```

## disassembly

```asm
0x180028b10  push    rbx
0x180028b12  sub     rsp, 20h
0x180028b16  lea     rax, ??_7ImapiComObject@@6B@; const ImapiComObject::`vftable'
0x180028b1d  mov     rbx, rcx
0x180028b20  mov     [rcx], rax
0x180028b23  mov     al, [rcx+10h]
0x180028b26  mov     byte ptr [rcx+10h], 0
0x180028b2a  test    al, al
0x180028b2c  jz      short loc_180028B38
0x180028b2e  add     rcx, 18h; lpCriticalSection
0x180028b32  call    cs:__imp_DeleteCriticalSection
0x180028b38  lea     rcx, [rbx+8]; void *
0x180028b3c  add     rsp, 20h
0x180028b40  pop     rbx
0x180028b41  jmp     ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
```
