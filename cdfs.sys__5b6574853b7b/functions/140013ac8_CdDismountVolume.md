# CdDismountVolume

- ea: `0x140013ac8`
- end: `0x140013c04`
- name: `CdDismountVolume`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140014e4c`

## callees

- `0x140001160`
- `0x140013ac8`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140013b74`
- `ntoskrnl!ExAcquireFastMutex` at `0x140013b74`
- `ntoskrnl!ExReleaseFastMutex` at `0x140013ba0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140013ba0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013bb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013bc8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013bb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013bc8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140013b35`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140013b35`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140013b1c`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140013b1c`
- `ntoskrnl!FsRtlDismountComplete` at `0x140013bda`
- `ntoskrnl!FsRtlDismountComplete` at `0x140013bda`

## pseudocode

```c
__int64 __fastcall CdDismountVolume(_DWORD *a1, IRP *a2)
{
  struct _FILE_OBJECT *FileObject; // rcx
  unsigned __int64 FsContext2; // rdi
  __int64 v7; // rbx
  unsigned int v8; // edi
  unsigned __int64 v9; // rdi

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( ((__int64)FileObject->FsContext2 & 7) == 2 )
  {
    FsContext2 = (unsigned __int64)FileObject->FsContext2;
    v7 = *((_QWORD *)FileObject->FsContext + 15);
    FsRtlNotifyVolumeEvent(FileObject, 1u);
    a1[8] |= 4u;
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    CdAcquireResource(a1, v7 + 128, 0, 0);
    if ( *(_DWORD *)(v7 + 52) == 2 )
    {
      v9 = FsContext2 & 0xFFFFFFFFFFFFFFF8uLL;
      ExAcquireFastMutex((PFAST_MUTEX)(v7 + 336));
      if ( *(_DWORD *)(v7 + 52) != 4 )
        *(_DWORD *)(v7 + 52) = 3;
      *(_DWORD *)(v7 + 48) |= 0x800u;
      *(_QWORD *)(v7 + 392) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(v7 + 336));
      *(_DWORD *)(v9 + 4) |= 0x10u;
      v8 = 0;
    }
    else
    {
      v8 = -1073741202;
    }
    ExReleaseResourceLite((PERESOURCE)(v7 + 128));
    ExReleaseResourceLite(&Resource);
    FsRtlDismountComplete(*(_QWORD *)(v7 + 16), v8);
    CdCompleteRequest(a1, a2, v8);
    return v8;
  }
  else
  {
    CdCompleteRequest(a1, a2, -1073741811);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140013ac8  push    rbx
0x140013aca  push    rbp
0x140013acb  push    rsi
0x140013acc  push    rdi
0x140013acd  push    r14
0x140013acf  push    r15
0x140013ad1  sub     rsp, 28h
0x140013ad5  mov     rax, [rdx+0B8h]
0x140013adc  mov     rbp, rcx
0x140013adf  mov     rsi, rdx
0x140013ae2  mov     rcx, [rax+30h]; FileObject
0x140013ae6  mov     r8d, [rcx+20h]
0x140013aea  and     r8d, 7
0x140013aee  cmp     r8d, 2
0x140013af2  jz      short loc_140013B0B
0x140013af4  mov     ebx, 0C000000Dh
0x140013af9  mov     rcx, rbp
0x140013afc  mov     r8d, ebx
0x140013aff  call    CdCompleteRequest
0x140013b04  mov     eax, ebx
0x140013b06  jmp     loc_140013BF6
0x140013b0b  mov     rax, [rcx+18h]
0x140013b0f  mov     edx, 1; EventCode
0x140013b14  mov     rdi, [rcx+20h]
0x140013b18  mov     rbx, [rax+78h]
0x140013b1c  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140013b23  nop     dword ptr [rax+rax+00h]
0x140013b28  or      dword ptr [rbp+20h], 4
0x140013b2c  lea     rcx, Resource; Resource
0x140013b33  mov     dl, 1; Wait
0x140013b35  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140013b3c  nop     dword ptr [rax+rax+00h]
0x140013b41  lea     r15, [rbx+80h]
0x140013b48  xor     r9d, r9d
0x140013b4b  mov     rdx, r15
0x140013b4e  xor     r8d, r8d
0x140013b51  mov     rcx, rbp
0x140013b54  call    CdAcquireResource
0x140013b59  cmp     dword ptr [rbx+34h], 2
0x140013b5d  jz      short loc_140013B66
0x140013b5f  mov     edi, 0C000026Eh
0x140013b64  jmp     short loc_140013BB2
0x140013b66  lea     r14, [rbx+150h]
0x140013b6d  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140013b71  mov     rcx, r14; FastMutex
0x140013b74  call    cs:__imp_ExAcquireFastMutex
0x140013b7b  nop     dword ptr [rax+rax+00h]
0x140013b80  cmp     dword ptr [rbx+34h], 4
0x140013b84  jz      short loc_140013B8D
0x140013b86  mov     dword ptr [rbx+34h], 3
0x140013b8d  bts     dword ptr [rbx+30h], 0Bh
0x140013b92  mov     rcx, r14; FastMutex
0x140013b95  mov     qword ptr [rbx+188h], 0
0x140013ba0  call    cs:__imp_ExReleaseFastMutex
0x140013ba7  nop     dword ptr [rax+rax+00h]
0x140013bac  or      dword ptr [rdi+4], 10h
0x140013bb0  xor     edi, edi
0x140013bb2  mov     rcx, r15; Resource
0x140013bb5  call    cs:__imp_ExReleaseResourceLite
0x140013bbc  nop     dword ptr [rax+rax+00h]
0x140013bc1  lea     rcx, Resource; Resource
0x140013bc8  call    cs:__imp_ExReleaseResourceLite
0x140013bcf  nop     dword ptr [rax+rax+00h]
0x140013bd4  mov     rcx, [rbx+10h]
0x140013bd8  mov     edx, edi
0x140013bda  call    cs:__imp_FsRtlDismountComplete
0x140013be1  nop     dword ptr [rax+rax+00h]
0x140013be6  mov     r8d, edi
0x140013be9  mov     rdx, rsi
0x140013bec  mov     rcx, rbp
0x140013bef  call    CdCompleteRequest
0x140013bf4  mov     eax, edi
0x140013bf6  add     rsp, 28h
0x140013bfa  pop     r15
0x140013bfc  pop     r14
0x140013bfe  pop     rdi
0x140013bff  pop     rsi
0x140013c00  pop     rbp
0x140013c01  pop     rbx
0x140013c02  retn
```
