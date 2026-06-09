# FatOpenEaFile

- ea: `0x140023f58`
- end: `0x140024017`
- name: `FatOpenEaFile`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140035e50`

## callees

- `0x140001858`
- `0x140023f58`
- `0x14003db44`
- `0x140048e6c`

## import_xrefs

- `ntoskrnl!IoCreateStreamFileObject` at `0x140023f7a`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140023f7a`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140023ffb`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x140023ffb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b6f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b6f8`

## pseudocode

```c
PFILE_OBJECT __fastcall FatOpenEaFile(__int64 a1, struct _CC_FILE_SIZES *a2)
{
  __int64 v3; // rdx
  PFILE_OBJECT StreamFileObject; // [rsp+40h] [rbp+8h]

  StreamFileObject = IoCreateStreamFileObject(0, *(PDEVICE_OBJECT *)(a2[7].ValidDataLength.QuadPart + 768));
  FatPreallocateCloseContext();
  FatSetFileObject(StreamFileObject, v3, a2, 0);
  _InterlockedIncrement((volatile signed __int32 *)(a2[7].ValidDataLength.QuadPart + 280));
  _InterlockedIncrement((volatile signed __int32 *)(a2[7].ValidDataLength.QuadPart + 284));
  StreamFileObject->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)a2[5].AllocationSize.QuadPart;
  *(_WORD *)&StreamFileObject->ReadAccess = 257;
  a2[1].ValidDataLength.QuadPart = FatMaxLarge;
  FatInitializeCacheMap(StreamFileObject, a2 + 1, 1u, (struct _CACHE_MANAGER_CALLBACKS *)&qword_140017D90, a2);
  CcSetAdditionalCacheAttributes(StreamFileObject, 1u, 1u);
  return StreamFileObject;
}

```

## disassembly

```asm
0x140023f58  mov     [rsp+arg_8], rbx
0x140023f5d  mov     [rsp+arg_0], rcx
0x140023f62  push    rdi
0x140023f63  sub     rsp, 30h
0x140023f67  mov     rdi, rdx
0x140023f6a  mov     rdx, [rdx+0B8h]
0x140023f71  mov     rdx, [rdx+300h]; DeviceObject
0x140023f78  xor     ecx, ecx; FileObject
0x140023f7a  call    cs:__imp_IoCreateStreamFileObject
0x140023f81  nop     dword ptr [rax+rax+00h]
0x140023f86  mov     rbx, rax
0x140023f89  mov     [rsp+38h+arg_0], rax
0x140023f8e  call    FatPreallocateCloseContext
0x140023f93  xor     r9d, r9d
0x140023f96  mov     r8, rdi
0x140023f99  mov     rcx, rbx
0x140023f9c  call    FatSetFileObject
0x140023fa1  mov     r8, [rdi+0B8h]
0x140023fa8  lock inc dword ptr [r8+118h]
0x140023fb0  mov     rax, [rdi+0B8h]
0x140023fb7  lock inc dword ptr [rax+11Ch]
0x140023fbe  mov     rax, [rdi+78h]
0x140023fc2  mov     [rbx+28h], rax
0x140023fc6  mov     word ptr [rbx+4Ah], 101h
0x140023fcc  mov     rax, cs:FatMaxLarge
0x140023fd3  mov     [rdi+28h], rax
0x140023fd7  lea     rdx, [rdi+18h]; int
0x140023fdb  mov     [rsp+38h+var_18], rdi; PVOID
0x140023fe0  lea     r9, qword_140017D90; int
0x140023fe7  mov     r8b, 1; int
0x140023fea  mov     rcx, rbx; int
0x140023fed  call    FatInitializeCacheMap
0x140023ff2  mov     r8b, 1; DisableWriteBehind
0x140023ff5  mov     dl, r8b; DisableReadAhead
0x140023ff8  mov     rcx, rbx; FileObject
0x140023ffb  call    cs:__imp_CcSetAdditionalCacheAttributes
0x140024002  nop     dword ptr [rax+rax+00h]
0x140024007  nop
0x140024008  mov     rax, rbx
0x14002400b  mov     rbx, [rsp+38h+arg_8]
0x140024010  add     rsp, 30h
0x140024014  pop     rdi
0x140024015  retn
0x14005b6e4  push    rbp
0x14005b6e6  sub     rsp, 30h
0x14005b6ea  mov     rbp, rdx
0x14005b6ed  movzx   eax, cl
0x14005b6f0  test    cl, cl
0x14005b6f2  jz      short loc_14005B705
0x14005b6f4  mov     rcx, [rbp+40h]; Object
0x14005b6f8  call    cs:__imp_ObfDereferenceObject
0x14005b6ff  nop     dword ptr [rax+rax+00h]
0x14005b704  nop
0x14005b705  add     rsp, 30h
0x14005b709  pop     rbp
0x14005b70a  retn
```
