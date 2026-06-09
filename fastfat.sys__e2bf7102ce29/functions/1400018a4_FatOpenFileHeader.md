# FatOpenFileHeader

- ea: `0x1400018a4`
- end: `0x1400019af`
- name: `FatOpenFileHeader`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000363c`
- `0x140029774`
- `0x14003805c`

## callees

- `0x140001858`
- `0x1400018a4`
- `0x14003db44`
- `0x1400465f4`
- `0x140048e6c`

## import_xrefs

- `ntoskrnl!IoCreateStreamFileObject` at `0x1400018e6`
- `ntoskrnl!IoCreateStreamFileObject` at `0x1400018e6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001997`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cca9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001997`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cca9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ccbe`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ccbe`

## pseudocode

```c
void __fastcall FatOpenFileHeader(__int64 a1, struct _FILE_OBJECT *a2, __int64 a3)
{
  PFILE_OBJECT StreamFileObject; // rbx
  __int64 v6; // rdx
  struct _FILE_OBJECT *v7; // rcx
  __int64 v8; // rax

  FatAcquireExclusiveFcb(a1, a3);
  if ( !*(_QWORD *)(a3 + 424) )
  {
    StreamFileObject = IoCreateStreamFileObject(a2, *(PDEVICE_OBJECT *)(*(_QWORD *)(a3 + 184) + 768LL));
    FatPreallocateCloseContext();
    FatSetFileObject(StreamFileObject, v6, a3, 0);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a3 + 184) + 280LL));
    StreamFileObject->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 120) + 96LL);
    *(_WORD *)&StreamFileObject->ReadAccess = 257;
    StreamFileObject->DeleteAccess = 1;
    ++*(_DWORD *)(a3 + 232);
    *(_QWORD *)(a3 + 424) = StreamFileObject;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a3 + 456));
  v7 = *(struct _FILE_OBJECT **)(a3 + 424);
  if ( !v7->PrivateCacheMap )
  {
    v8 = *(unsigned int *)(a3 + 132);
    *(_QWORD *)(a3 + 440) = v8;
    *(_QWORD *)(a3 + 432) = v8;
    *(_QWORD *)(a3 + 448) = FatMaxLarge;
    FatInitializeCacheMap(
      v7,
      (struct _CC_FILE_SIZES *)(a3 + 432),
      1u,
      (struct _CACHE_MANAGER_CALLBACKS *)&qword_140017DB0,
      (PVOID)a3);
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a3 + 8));
}

```

## disassembly

```asm
0x1400018a4  mov     [rsp+arg_0], rbx
0x1400018a9  mov     [rsp+arg_10], r8
0x1400018ae  push    rdi
0x1400018af  sub     rsp, 40h
0x1400018b3  mov     rdi, r8
0x1400018b6  mov     rbx, rdx
0x1400018b9  mov     [rsp+48h+var_18], 0
0x1400018c2  mov     rdx, r8
0x1400018c5  call    FatAcquireExclusiveFcb
0x1400018ca  nop
0x1400018cb  cmp     qword ptr [rdi+1A8h], 0
0x1400018d3  jnz     short loc_140001944
0x1400018d5  mov     rdx, [rdi+0B8h]
0x1400018dc  mov     rdx, [rdx+300h]; DeviceObject
0x1400018e3  mov     rcx, rbx; FileObject
0x1400018e6  call    cs:__imp_IoCreateStreamFileObject
0x1400018ed  nop     dword ptr [rax+rax+00h]
0x1400018f2  mov     rbx, rax
0x1400018f5  mov     [rsp+48h+var_18], rax
0x1400018fa  call    FatPreallocateCloseContext
0x1400018ff  xor     r9d, r9d
0x140001902  mov     r8, rdi
0x140001905  mov     rcx, rbx
0x140001908  call    FatSetFileObject
0x14000190d  mov     r8, [rdi+0B8h]
0x140001914  lock inc dword ptr [r8+118h]
0x14000191c  mov     rcx, [rdi+78h]
0x140001920  add     rcx, 60h ; '`'
0x140001924  mov     [rbx+28h], rcx
0x140001928  mov     word ptr [rbx+4Ah], 101h
0x14000192e  mov     byte ptr [rbx+4Ch], 1
0x140001932  inc     dword ptr [rdi+0E8h]
0x140001938  mov     [rdi+1A8h], rbx
0x14000193f  mov     [rsp+48h+var_18], r9
0x140001944  lock inc dword ptr [rdi+1C8h]
0x14000194b  mov     rcx, [rdi+1A8h]; int
0x140001952  cmp     qword ptr [rcx+30h], 0
0x140001957  jnz     short loc_140001993
0x140001959  mov     eax, [rdi+84h]
0x14000195f  mov     [rdi+1B8h], rax
0x140001966  lea     rdx, [rdi+1B0h]; int
0x14000196d  mov     [rdx], rax
0x140001970  mov     rax, cs:FatMaxLarge
0x140001977  mov     [rdi+1C0h], rax
0x14000197e  mov     [rsp+48h+var_28], rdi; PVOID
0x140001983  lea     r9, qword_140017DB0; int
0x14000198a  mov     r8b, 1; int
0x14000198d  call    FatInitializeCacheMap
0x140001992  nop
0x140001993  mov     rcx, [rdi+8]; Resource
0x140001997  call    cs:__imp_ExReleaseResourceLite
0x14000199e  nop     dword ptr [rax+rax+00h]
0x1400019a3  mov     rbx, [rsp+48h+arg_0]
0x1400019a8  add     rsp, 40h
0x1400019ac  pop     rdi
0x1400019ad  retn
0x14000cc98  push    rbp
0x14000cc9a  sub     rsp, 30h
0x14000cc9e  mov     rbp, rdx
0x14000cca1  mov     rcx, [rbp+60h]
0x14000cca5  mov     rcx, [rcx+8]; Resource
0x14000cca9  call    cs:__imp_ExReleaseResourceLite
0x14000ccb0  nop     dword ptr [rax+rax+00h]
0x14000ccb5  mov     rcx, [rbp+30h]; Object
0x14000ccb9  test    rcx, rcx
0x14000ccbc  jz      short loc_14000CCCB
0x14000ccbe  call    cs:__imp_ObfDereferenceObject
0x14000ccc5  nop     dword ptr [rax+rax+00h]
0x14000ccca  nop
0x14000cccb  add     rsp, 30h
0x14000cccf  pop     rbp
0x14000ccd0  retn
```
