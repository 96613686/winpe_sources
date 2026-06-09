# FatOpenDirectoryFile

- ea: `0x140023df4`
- end: `0x140023f4f`
- name: `FatOpenDirectoryFile`
- size: `347`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140024228`
- `0x140024584`
- `0x1400412a8`

## callees

- `0x140001858`
- `0x1400226b8`
- `0x140023df4`
- `0x14003db44`
- `0x14004707c`
- `0x140048e6c`

## import_xrefs

- `ntoskrnl!IoCreateStreamFileObject` at `0x140023e77`
- `ntoskrnl!IoCreateStreamFileObject` at `0x140023e77`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023ef8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b6b5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140023ef8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b6b5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023e4c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023e4c`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b6ca`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b6ca`

## pseudocode

```c
void __fastcall FatOpenDirectoryFile(__int64 a1, char *a2)
{
  struct _CC_FILE_SIZES *v3; // rsi
  PFILE_OBJECT StreamFileObject; // rdi
  __int64 v5; // rdx
  struct _FILE_OBJECT *v6; // rcx

  v3 = (struct _CC_FILE_SIZES *)(a2 + 24);
  if ( *((_QWORD *)a2 + 3) == -1 )
  {
    FatLookupFileAllocationSize(a1, a2);
    *((_DWORD *)a2 + 8) = v3->AllocationSize.LowPart;
  }
  FatCheckFreeDirentBitmap(a1, a2);
  if ( !*((_QWORD *)a2 + 43) )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)a2 + 23) + 824LL));
    if ( !*((_QWORD *)a2 + 43) )
    {
      StreamFileObject = IoCreateStreamFileObject(0, *(PDEVICE_OBJECT *)(*((_QWORD *)a2 + 23) + 768LL));
      FatPreallocateCloseContext();
      FatSetFileObject(StreamFileObject, v5, a2, 0);
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a2 + 23) + 280LL));
      if ( *(_WORD *)a2 == 1284 )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a2 + 23) + 284LL));
      StreamFileObject->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)*((_QWORD *)a2 + 15);
      *(_WORD *)&StreamFileObject->ReadAccess = 257;
      StreamFileObject->DeleteAccess = 1;
      _InterlockedIncrement((volatile signed __int32 *)a2 + 84);
      *((_QWORD *)a2 + 43) = StreamFileObject;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)a2 + 23) + 824LL));
  }
  v6 = (struct _FILE_OBJECT *)*((_QWORD *)a2 + 43);
  if ( !v6->PrivateCacheMap )
  {
    *((_QWORD *)a2 + 5) = FatMaxLarge;
    *((_DWORD *)a2 + 70) = -1;
    FatInitializeCacheMap(v6, v3, 1u, (struct _CACHE_MANAGER_CALLBACKS *)&qword_140017DB0, a2);
  }
}

```

## disassembly

```asm
0x140023df4  mov     [rsp+arg_0], rbx
0x140023df9  mov     [rsp+arg_10], rsi
0x140023dfe  mov     [rsp+arg_8], rdx
0x140023e03  push    rdi
0x140023e04  sub     rsp, 40h
0x140023e08  mov     rbx, rdx
0x140023e0b  lea     rsi, [rdx+18h]
0x140023e0f  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x140023e13  jnz     short loc_140023E1F
0x140023e15  call    FatLookupFileAllocationSize
0x140023e1a  mov     eax, [rsi]
0x140023e1c  mov     [rbx+20h], eax
0x140023e1f  mov     rdx, rbx
0x140023e22  call    FatCheckFreeDirentBitmap
0x140023e27  cmp     qword ptr [rbx+158h], 0
0x140023e2f  jnz     loc_140023F04
0x140023e35  mov     [rsp+48h+var_18], 0
0x140023e3e  mov     rcx, [rbx+0B8h]
0x140023e45  add     rcx, 338h; FastMutex
0x140023e4c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023e53  nop     dword ptr [rax+rax+00h]
0x140023e58  nop
0x140023e59  cmp     qword ptr [rbx+158h], 0
0x140023e61  jnz     loc_140023EEA
0x140023e67  mov     rdx, [rbx+0B8h]
0x140023e6e  mov     rdx, [rdx+300h]; DeviceObject
0x140023e75  xor     ecx, ecx; FileObject
0x140023e77  call    cs:__imp_IoCreateStreamFileObject
0x140023e7e  nop     dword ptr [rax+rax+00h]
0x140023e83  mov     rdi, rax
0x140023e86  mov     [rsp+48h+var_18], rax
0x140023e8b  call    FatPreallocateCloseContext
0x140023e90  xor     r9d, r9d
0x140023e93  mov     r8, rbx
0x140023e96  mov     rcx, rdi
0x140023e99  call    FatSetFileObject
0x140023e9e  mov     r8, [rbx+0B8h]
0x140023ea5  lock inc dword ptr [r8+118h]
0x140023ead  mov     eax, 504h
0x140023eb2  cmp     [rbx], ax
0x140023eb5  jnz     short loc_140023EC5
0x140023eb7  mov     rax, [rbx+0B8h]
0x140023ebe  lock inc dword ptr [rax+11Ch]
0x140023ec5  mov     rax, [rbx+78h]
0x140023ec9  mov     [rdi+28h], rax
0x140023ecd  mov     word ptr [rdi+4Ah], 101h
0x140023ed3  mov     byte ptr [rdi+4Ch], 1
0x140023ed7  lock inc dword ptr [rbx+150h]
0x140023ede  mov     [rbx+158h], rdi
0x140023ee5  mov     [rsp+48h+var_18], r9
0x140023eea  mov     rcx, [rbx+0B8h]
0x140023ef1  add     rcx, 338h; FastMutex
0x140023ef8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140023eff  nop     dword ptr [rax+rax+00h]
0x140023f04  mov     rcx, [rbx+158h]; int
0x140023f0b  cmp     qword ptr [rcx+30h], 0
0x140023f10  jnz     short loc_140023F3E
0x140023f12  mov     rax, cs:FatMaxLarge
0x140023f19  mov     [rbx+28h], rax
0x140023f1d  mov     dword ptr [rbx+118h], 0FFFFFFFFh
0x140023f27  mov     [rsp+48h+var_28], rbx; PVOID
0x140023f2c  lea     r9, qword_140017DB0; int
0x140023f33  mov     r8b, 1; int
0x140023f36  mov     rdx, rsi; int
0x140023f39  call    FatInitializeCacheMap
0x140023f3e  mov     rbx, [rsp+48h+arg_0]
0x140023f43  mov     rsi, [rsp+48h+arg_10]
0x140023f48  add     rsp, 40h
0x140023f4c  pop     rdi
0x140023f4d  retn
0x14005b69a  push    rbp
0x14005b69c  sub     rsp, 30h
0x14005b6a0  mov     rbp, rdx
0x14005b6a3  mov     rax, [rbp+58h]
0x14005b6a7  mov     rcx, [rax+0B8h]
0x14005b6ae  add     rcx, 338h; FastMutex
0x14005b6b5  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005b6bc  nop     dword ptr [rax+rax+00h]
0x14005b6c1  mov     rcx, [rbp+30h]; Object
0x14005b6c5  test    rcx, rcx
0x14005b6c8  jz      short loc_14005B6D7
0x14005b6ca  call    cs:__imp_ObfDereferenceObject
0x14005b6d1  nop     dword ptr [rax+rax+00h]
0x14005b6d6  nop
0x14005b6d7  add     rsp, 30h
0x14005b6db  pop     rbp
0x14005b6dc  retn
```
