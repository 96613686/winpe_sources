# NpFsdClose

- ea: `0x14000e640`
- end: `0x14000e76d`
- name: `NpFsdClose`
- size: `301`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000e640`
- `0x14000e774`
- `0x14000e830`
- `0x14000e8bc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e650`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e650`
- `ntoskrnl!IofCompleteRequest` at `0x14000e6c3`
- `ntoskrnl!IofCompleteRequest` at `0x14000e6c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e6cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e6cf`

## pseudocode

```c
__int64 __fastcall NpFsdClose(__int64 a1, IRP *a2)
{
  __int64 v4; // rcx
  PFILE_OBJECT FileObject; // rdi
  volatile signed __int32 *FsContext; // r8
  int v7; // edx
  unsigned __int64 FsContext2; // rdi
  _QWORD *v9; // rdi
  void *v10; // rcx
  int v12; // edx
  int v13; // edx
  unsigned __int64 v14; // rdi
  volatile signed __int32 *v15; // rax
  _QWORD v16[3]; // [rsp+20h] [rbp-18h] BYREF

  KeEnterCriticalRegion();
  v4 = *(_QWORD *)(a1 + 64);
  v16[1] = v16;
  v16[0] = v16;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  FsContext = (volatile signed __int32 *)FileObject->FsContext;
  v7 = *(unsigned __int16 *)FsContext;
  if ( v7 == 518 )
  {
    FsContext2 = (unsigned __int64)FileObject->FsContext2;
    _InterlockedDecrement((volatile signed __int32 *)(v4 + 120));
    v9 = (_QWORD *)(FsContext2 & 0xFFFFFFFFFFFFFFFEuLL);
    if ( v9 )
    {
      v10 = (void *)v9[2];
      if ( v10 )
        ExFreePoolWithTag(v10, 0);
      ExFreePoolWithTag(v9, 0);
    }
  }
  else
  {
    v12 = v7 - 513;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 == 1 && _InterlockedExchangeAdd(FsContext + 31, 0xFFFFFFFF) == 1 )
          NpFreeProtectedPrefix((PVOID)FsContext);
      }
      else
      {
        v14 = (unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 4), 0xFFFFFFFF) == 1 )
        {
          v15 = *(volatile signed __int32 **)(v14 + 40);
          if ( _InterlockedExchangeAdd(v15 + 31, 0xFFFFFFFF) == 1 )
            NpFreeFcb((PVOID)v15);
          NpFreeCcb((PVOID)v14);
        }
      }
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 120));
    }
  }
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 2);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x14000e640  mov     [rsp+arg_0], rbx
0x14000e645  push    rdi
0x14000e646  sub     rsp, 30h
0x14000e64a  mov     rbx, rdx
0x14000e64d  mov     rdi, rcx
0x14000e650  call    cs:__imp_KeEnterCriticalRegion
0x14000e657  nop     dword ptr [rax+rax+00h]
0x14000e65c  mov     rcx, [rdi+40h]
0x14000e660  lea     rax, [rsp+38h+var_18]
0x14000e665  mov     [rsp+38h+var_10], rax
0x14000e66a  lea     rax, [rsp+38h+var_18]
0x14000e66f  mov     [rsp+38h+var_18], rax
0x14000e674  mov     rax, [rbx+0B8h]
0x14000e67b  mov     rdi, [rax+30h]
0x14000e67f  mov     r8, [rdi+18h]
0x14000e683  movzx   edx, word ptr [r8]
0x14000e687  cmp     edx, 206h
0x14000e68d  jnz     short loc_14000E6F9
0x14000e68f  mov     rdi, [rdi+20h]
0x14000e693  lock dec dword ptr [rcx+78h]
0x14000e697  and     rdi, 0FFFFFFFFFFFFFFFEh
0x14000e69b  jz      short loc_14000E6B7
0x14000e69d  mov     rcx, [rdi+10h]; P
0x14000e6a1  test    rcx, rcx
0x14000e6a4  jnz     short loc_14000E6E9
0x14000e6a6  xor     edx, edx; Tag
0x14000e6a8  mov     rcx, rdi; P
0x14000e6ab  call    cs:__imp_ExFreePoolWithTag
0x14000e6b2  nop     dword ptr [rax+rax+00h]
0x14000e6b7  mov     dl, 2; PriorityBoost
0x14000e6b9  mov     dword ptr [rbx+30h], 0
0x14000e6c0  mov     rcx, rbx; Irp
0x14000e6c3  call    cs:__imp_IofCompleteRequest
0x14000e6ca  nop     dword ptr [rax+rax+00h]
0x14000e6cf  call    cs:__imp_KeLeaveCriticalRegion
0x14000e6d6  nop     dword ptr [rax+rax+00h]
0x14000e6db  mov     rbx, [rsp+38h+arg_0]
0x14000e6e0  xor     eax, eax
0x14000e6e2  add     rsp, 30h
0x14000e6e6  pop     rdi
0x14000e6e7  retn
0x14000e6e9  xor     edx, edx; Tag
0x14000e6eb  call    cs:__imp_ExFreePoolWithTag
0x14000e6f2  nop     dword ptr [rax+rax+00h]
0x14000e6f7  jmp     short loc_14000E6A6
0x14000e6f9  sub     edx, 201h
0x14000e6ff  jz      short loc_14000E764
0x14000e701  sub     edx, 1
0x14000e704  jz      short loc_14000E724
0x14000e706  cmp     edx, 1
0x14000e709  jnz     short loc_14000E6B7
0x14000e70b  mov     ecx, 0FFFFFFFFh
0x14000e710  lock xadd [r8+7Ch], ecx
0x14000e716  cmp     ecx, edx
0x14000e718  jnz     short loc_14000E6B7
0x14000e71a  mov     rcx, r8; P
0x14000e71d  call    NpFreeProtectedPrefix
0x14000e722  jmp     short loc_14000E6B7
0x14000e724  mov     rdi, [rdi+20h]
0x14000e728  mov     ecx, 0FFFFFFFFh
0x14000e72d  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14000e731  mov     eax, ecx
0x14000e733  lock xadd [rdi+4], eax
0x14000e738  cmp     eax, 1
0x14000e73b  jnz     loc_14000E6B7
0x14000e741  mov     rax, [rdi+28h]
0x14000e745  lock xadd [rax+7Ch], ecx
0x14000e74a  cmp     ecx, 1
0x14000e74d  jnz     short loc_14000E757
0x14000e74f  mov     rcx, rax; P
0x14000e752  call    NpFreeFcb
0x14000e757  mov     rcx, rdi; P
0x14000e75a  call    NpFreeCcb
0x14000e75f  jmp     loc_14000E6B7
0x14000e764  lock dec dword ptr [rcx+78h]
0x14000e768  jmp     loc_14000E6B7
```
