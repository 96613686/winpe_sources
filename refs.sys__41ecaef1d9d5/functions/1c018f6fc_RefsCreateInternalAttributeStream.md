# RefsCreateInternalAttributeStream

- ea: `0x1c018f6fc`
- end: `0x1c018fa29`
- name: `RefsCreateInternalAttributeStream`
- size: `813`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1c014eb7c`
- `0x1c014f108`
- `0x1c01639a0`
- `0x1c018d3ec`
- `0x1c018e078`
- `0x1c01960f8`
- `0x1c019d414`
- `0x1c01af5ac`
- `0x1c01d1838`
- `0x1c01d345c`

## callees

- `0x1c0002bac`
- `0x1c0061878`
- `0x1c0067040`
- `0x1c009294c`
- `0x1c015331c`
- `0x1c015ac58`
- `0x1c018f6fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1c018f794`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c018f794`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c018f757`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c018f757`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c018f89b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c018f89b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c018f8d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c018f8d4`
- `ntoskrnl!ObfDereferenceObject` at `0x1c018f9d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1c018f9d9`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x1c018f7ca`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x1c018f7ca`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1c018f93a`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1c018f93a`
- `ntoskrnl!KeReleaseMutant` at `0x1c018f97a`
- `ntoskrnl!KeReleaseMutant` at `0x1c018fa14`
- `ntoskrnl!KeReleaseMutant` at `0x1c018f97a`
- `ntoskrnl!KeReleaseMutant` at `0x1c018fa14`

## pseudocode

```c
void __fastcall RefsCreateInternalAttributeStream(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  char v8; // di
  char v9; // r14
  PFILE_OBJECT StreamFileObjectLite; // rax
  PFILE_OBJECT v11; // r11
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r11
  __int64 v15; // rdx
  __int64 v16; // r8
  char v17; // dl
  __int64 v18; // r8
  int v19; // eax
  char v20; // [rsp+30h] [rbp-38h]
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp-30h]

  v8 = 0;
  v9 = 0;
  if ( !*(_QWORD *)(a2 + 224) )
  {
    if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a2 + 120) + 96LL) + 64LL))
      || *(_QWORD *)(a2 + 16)
      && !(unsigned __int8)MsIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)(a2 + 120) + 104LL)) )
    {
      KeWaitForSingleObject(&StreamFileCreationMutex, Executive, 0, 0, 0);
      v9 = 1;
    }
    if ( !*(_QWORD *)(a2 + 224) )
    {
      StreamFileObjectLite = IoCreateStreamFileObjectLite(
                               0,
                               *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(a2 + 128) + 208LL) + 16LL));
      v11 = StreamFileObjectLite;
      FileObject = StreamFileObjectLite;
      if ( a4 )
      {
        StreamFileObjectLite->FileName.MaximumLength = *(_WORD *)(a4 + 2);
        StreamFileObjectLite->FileName.Length = *(_WORD *)a4;
        StreamFileObjectLite->FileName.Buffer = *(PWSTR *)(a4 + 8);
      }
      if ( (*(_DWORD *)(a2 + 304) & 0x20) == 0 )
      {
        v12 = *(_QWORD *)(a1 + 72);
        if ( v12 )
        {
          v13 = *(_QWORD *)(*(_QWORD *)(v12 + 184) + 48LL);
          if ( v13 )
            v11->Flags |= *(_DWORD *)(v13 + 80) & 0x8020;
        }
      }
      RefsSetFileObject(v11, 5, a2, 0);
      *(_WORD *)(v14 + 74) = 257;
      *(_WORD *)(v14 + 77) = 257;
      *(_BYTE *)(v14 + 79) = 1;
      LOBYTE(v15) = 1;
      RefsIncrementCloseCounts(a2, v15, 0);
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 144));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 120) + 24LL));
      v20 = v17;
      if ( a3 && (*(_DWORD *)(a2 + 136) & 0x20) == 0 )
        RefsUpdateScbFromAttribute(a1, a2, v16);
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a2 + 48));
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 156));
      *(_BYTE *)(a2 + 6) &= ~1u;
      if ( (*(_BYTE *)(a2 + 304) & 0x20) == 0 )
        *(_BYTE *)(a2 + 6) |= 1u;
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 156));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(a2 + 48));
      if ( !FileObject->PrivateCacheMap )
      {
        LOBYTE(v18) = 0;
        v19 = *(_DWORD *)(a2 + 200);
        if ( v19 != 128 && v19 != 176
          || (*(_DWORD *)(*(_QWORD *)(a2 + 120) + 4LL) & 0x80104) != 0
          || (*(_DWORD *)(*(_QWORD *)(a2 + 128) + 4LL) & 0x10) != 0 )
        {
          LOBYTE(v18) = 1;
        }
        RefsInitializeCacheMap(a1, FileObject, v18, a2);
        CcSetParallelFlushFile(FileObject, 1u);
      }
      *(_QWORD *)(a2 + 224) = FileObject;
      v8 = v20;
    }
    if ( v8 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(a2 + 144));
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 120) + 24LL));
    }
    if ( v9 )
      KeReleaseMutant(&StreamFileCreationMutex, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x1c018f6fc  mov     rax, rsp
0x1c018f6ff  mov     [rax+8], rbx
0x1c018f703  mov     [rax+18h], rsi
0x1c018f707  mov     [rax+20h], rdi
0x1c018f70b  mov     [rax+10h], rdx
0x1c018f70f  push    r12
0x1c018f711  push    r14
0x1c018f713  push    r15
0x1c018f715  sub     rsp, 50h
0x1c018f719  mov     rsi, r9
0x1c018f71c  mov     r12b, r8b
0x1c018f71f  mov     rbx, rdx
0x1c018f722  mov     r15, rcx
0x1c018f725  and     qword ptr [rax-30h], 0
0x1c018f72a  mov     byte ptr [rax-37h], 0
0x1c018f72e  xor     dil, dil
0x1c018f731  mov     [rax-38h], dil
0x1c018f735  xor     r14b, r14b
0x1c018f738  mov     [rsp+68h+var_36], r14b
0x1c018f73d  cmp     qword ptr [rdx+0E0h], 0
0x1c018f745  jnz     loc_1C018F986
0x1c018f74b  mov     rax, [rdx+78h]
0x1c018f74f  mov     rcx, [rax+60h]
0x1c018f753  add     rcx, 40h ; '@'; Resource
0x1c018f757  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1c018f75e  nop     dword ptr [rax+rax+00h]
0x1c018f763  test    al, al
0x1c018f765  jz      short loc_1C018F77F
0x1c018f767  cmp     qword ptr [rbx+10h], 0
0x1c018f76c  jz      short loc_1C018F7A8
0x1c018f76e  mov     rcx, [rbx+78h]
0x1c018f772  mov     rcx, [rcx+68h]
0x1c018f776  call    MsIsFastResourceHeldExclusive
0x1c018f77b  test    al, al
0x1c018f77d  jnz     short loc_1C018F7A8
0x1c018f77f  and     [rsp+68h+var_48], 0
0x1c018f785  xor     r9d, r9d; Alertable
0x1c018f788  xor     r8d, r8d; WaitMode
0x1c018f78b  xor     edx, edx; WaitReason
0x1c018f78d  lea     rcx, StreamFileCreationMutex; Object
0x1c018f794  call    cs:__imp_KeWaitForSingleObject
0x1c018f79b  nop     dword ptr [rax+rax+00h]
0x1c018f7a0  mov     r14b, 1
0x1c018f7a3  mov     [rsp+68h+var_36], r14b
0x1c018f7a8  cmp     qword ptr [rbx+0E0h], 0
0x1c018f7b0  jnz     loc_1C018F952
0x1c018f7b6  mov     rax, [rbx+80h]
0x1c018f7bd  mov     rdx, [rax+0D0h]
0x1c018f7c4  mov     rdx, [rdx+10h]; DeviceObject
0x1c018f7c8  xor     ecx, ecx; FileObject
0x1c018f7ca  call    cs:__imp_IoCreateStreamFileObjectLite
0x1c018f7d1  nop     dword ptr [rax+rax+00h]
0x1c018f7d6  mov     r11, rax
0x1c018f7d9  mov     [rsp+68h+FileObject], rax
0x1c018f7de  test    rsi, rsi
0x1c018f7e1  jz      short loc_1C018F7FA
0x1c018f7e3  movzx   ecx, word ptr [rsi+2]
0x1c018f7e7  mov     [rax+5Ah], cx
0x1c018f7eb  movzx   ecx, word ptr [rsi]
0x1c018f7ee  mov     [rax+58h], cx
0x1c018f7f2  mov     rcx, [rsi+8]
0x1c018f7f6  mov     [rax+60h], rcx
0x1c018f7fa  mov     ecx, [rbx+130h]
0x1c018f800  mov     dil, 20h ; ' '
0x1c018f803  test    dil, cl
0x1c018f806  jnz     short loc_1C018F837
0x1c018f808  mov     rax, [r15+48h]
0x1c018f80c  test    rax, rax
0x1c018f80f  jz      short loc_1C018F837
0x1c018f811  mov     rax, [rax+0B8h]
0x1c018f818  mov     [rsp+68h+var_28], rax
0x1c018f81d  mov     rcx, [rax+30h]
0x1c018f821  mov     [rsp+68h+var_20], rcx
0x1c018f826  test    rcx, rcx
0x1c018f829  jz      short loc_1C018F837
0x1c018f82b  mov     eax, [rcx+50h]
0x1c018f82e  and     eax, 8020h
0x1c018f833  or      [r11+50h], eax
0x1c018f837  xor     r9d, r9d
0x1c018f83a  mov     r8, rbx
0x1c018f83d  lea     edx, [r9+5]
0x1c018f841  mov     rcx, r11
0x1c018f844  call    RefsSetFileObject
0x1c018f849  mov     word ptr [r11+4Ah], 101h
0x1c018f850  mov     word ptr [r11+4Dh], 101h
0x1c018f857  mov     byte ptr [r11+4Fh], 1
0x1c018f85c  xor     r8d, r8d
0x1c018f85f  mov     dl, 1
0x1c018f861  mov     rcx, rbx
0x1c018f864  call    RefsIncrementCloseCounts
0x1c018f869  lock inc dword ptr [rbx+90h]
0x1c018f870  mov     rax, [rbx+78h]
0x1c018f874  lock inc dword ptr [rax+18h]
0x1c018f878  mov     [rsp+68h+var_38], dl
0x1c018f87c  test    r12b, r12b
0x1c018f87f  jz      short loc_1C018F897
0x1c018f881  mov     eax, [rbx+88h]
0x1c018f887  test    dil, al
0x1c018f88a  jnz     short loc_1C018F897
0x1c018f88c  mov     rdx, rbx
0x1c018f88f  mov     rcx, r15
0x1c018f892  call    RefsUpdateScbFromAttribute
0x1c018f897  mov     rcx, [rbx+30h]; FastMutex
0x1c018f89b  call    cs:__imp_ExAcquireFastMutex
0x1c018f8a2  nop     dword ptr [rax+rax+00h]
0x1c018f8a7  lock inc dword ptr [rbx+9Ch]
0x1c018f8ae  and     byte ptr [rbx+6], 0FEh
0x1c018f8b2  mov     cl, [rbx+6]
0x1c018f8b5  test    [rbx+130h], dil
0x1c018f8bc  setz    al
0x1c018f8bf  test    al, 1
0x1c018f8c1  jz      short loc_1C018F8C9
0x1c018f8c3  or      cl, 1
0x1c018f8c6  mov     [rbx+6], cl
0x1c018f8c9  lock inc dword ptr [rbx+9Ch]
0x1c018f8d0  mov     rcx, [rbx+30h]; FastMutex
0x1c018f8d4  call    cs:__imp_ExReleaseFastMutex
0x1c018f8db  nop     dword ptr [rax+rax+00h]
0x1c018f8e0  mov     rdi, [rsp+68h+FileObject]
0x1c018f8e5  cmp     qword ptr [rdi+30h], 0
0x1c018f8ea  jnz     short loc_1C018F946
0x1c018f8ec  xor     r8b, r8b
0x1c018f8ef  mov     eax, [rbx+0C8h]
0x1c018f8f5  cmp     eax, 80h
0x1c018f8fa  jz      short loc_1C018F903
0x1c018f8fc  cmp     eax, 0B0h
0x1c018f901  jnz     short loc_1C018F91F
0x1c018f903  mov     rax, [rbx+78h]
0x1c018f907  test    dword ptr [rax+4], 80104h
0x1c018f90e  jnz     short loc_1C018F91F
0x1c018f910  mov     rax, [rbx+80h]
0x1c018f917  mov     ecx, [rax+4]
0x1c018f91a  test    cl, 10h
0x1c018f91d  jz      short loc_1C018F922
0x1c018f91f  mov     r8b, 1
0x1c018f922  mov     r9, rbx
0x1c018f925  mov     rdx, rdi
0x1c018f928  mov     rcx, r15
0x1c018f92b  call    RefsInitializeCacheMap
0x1c018f930  mov     [rsp+68h+var_37], 1
0x1c018f935  mov     dl, 1; EnableParallelFlush
0x1c018f937  mov     rcx, rdi; FileObject
0x1c018f93a  call    cs:__imp_CcSetParallelFlushFile
0x1c018f941  nop     dword ptr [rax+rax+00h]
0x1c018f946  mov     [rbx+0E0h], rdi
0x1c018f94d  mov     dil, [rsp+68h+var_38]
0x1c018f952  test    dil, dil
0x1c018f955  jz      short loc_1C018F966
0x1c018f957  lock dec dword ptr [rbx+90h]
0x1c018f95e  mov     rax, [rbx+78h]
0x1c018f962  lock dec dword ptr [rax+18h]
0x1c018f966  test    r14b, r14b
0x1c018f969  jz      short loc_1C018F986
0x1c018f96b  xor     r9d, r9d; Wait
0x1c018f96e  xor     r8d, r8d; Abandoned
0x1c018f971  xor     edx, edx; Increment
0x1c018f973  lea     rcx, StreamFileCreationMutex; Mutant
0x1c018f97a  call    cs:__imp_KeReleaseMutant
0x1c018f981  nop     dword ptr [rax+rax+00h]
0x1c018f986  lea     r11, [rsp+68h+var_18]
0x1c018f98b  mov     rbx, [r11+20h]
0x1c018f98f  mov     rsi, [r11+30h]
0x1c018f993  mov     rdi, [r11+38h]
0x1c018f997  mov     rsp, r11
0x1c018f99a  pop     r15
0x1c018f99c  pop     r14
0x1c018f99e  pop     r12
0x1c018f9a0  retn
0x1c018f9a2  push    rbx
0x1c018f9a4  push    rbp
0x1c018f9a5  sub     rsp, 38h
0x1c018f9a9  mov     rbp, rdx
0x1c018f9ac  mov     [rbp+33h], cl
0x1c018f9af  test    cl, cl
0x1c018f9b1  jz      short loc_1C018F9E6
0x1c018f9b3  mov     rbx, [rbp+38h]
0x1c018f9b7  cmp     byte ptr [rbp+31h], 0
0x1c018f9bb  jz      short loc_1C018F9C8
0x1c018f9bd  xor     edx, edx
0x1c018f9bf  mov     rcx, rbx
0x1c018f9c2  call    RefsUninitializeCacheMap
0x1c018f9c7  nop
0x1c018f9c8  test    rbx, rbx
0x1c018f9cb  jz      short loc_1C018F9E6
0x1c018f9cd  xor     eax, eax
0x1c018f9cf  mov     [rbx+58h], eax
0x1c018f9d2  and     [rbx+60h], rax
0x1c018f9d6  mov     rcx, rbx; Object
0x1c018f9d9  call    cs:__imp_ObfDereferenceObject
0x1c018f9e0  nop     dword ptr [rax+rax+00h]
0x1c018f9e5  nop
0x1c018f9e6  cmp     byte ptr [rbp+30h], 0
0x1c018f9ea  jz      short loc_1C018F9FF
0x1c018f9ec  mov     rax, [rbp+78h]
0x1c018f9f0  lock dec dword ptr [rax+90h]
0x1c018f9f7  mov     rcx, [rax+78h]
0x1c018f9fb  lock dec dword ptr [rcx+18h]
0x1c018f9ff  cmp     byte ptr [rbp+32h], 0
0x1c018fa03  jz      short loc_1C018FA21
0x1c018fa05  xor     r9d, r9d; Wait
0x1c018fa08  xor     r8d, r8d; Abandoned
0x1c018fa0b  xor     edx, edx; Increment
0x1c018fa0d  lea     rcx, StreamFileCreationMutex; Mutant
0x1c018fa14  call    cs:__imp_KeReleaseMutant
0x1c018fa1b  nop     dword ptr [rax+rax+00h]
0x1c018fa20  nop
0x1c018fa21  add     rsp, 38h
0x1c018fa25  pop     rbp
0x1c018fa26  pop     rbx
0x1c018fa27  retn
```
