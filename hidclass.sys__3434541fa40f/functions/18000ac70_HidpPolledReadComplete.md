# HidpPolledReadComplete

- ea: `0x18000ac70`
- end: `0x18000adb7`
- name: `HidpPolledReadComplete`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009b70`

## callees

- `0x180003030`
- `0x18000ac70`
- `0x18000adc0`
- `0x18000b040`
- `0x18000c250`
- `0x18000cc90`
- `0x180027d00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x18000ad96`
- `ntoskrnl!IoFreeIrp` at `0x18000ad96`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ad87`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ad87`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000ad5c`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000ad5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000ad28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000ad28`

## pseudocode

```c
__int64 __fastcall HidpPolledReadComplete(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // r14
  __int64 ReportIdentifier; // rax
  unsigned int v6; // r12d
  __int64 HidclassCollection; // rbp
  __int64 v8; // r8
  __int64 CollectionDesc; // rax
  __int64 v10; // rcx
  size_t v11; // r15
  KIRQL v12; // bl

  v4 = (_QWORD *)(*(_QWORD *)(a3 + 64) + 32LL);
  if ( !**(_BYTE **)(*(_QWORD *)(a3 + 64) + 208LL) )
  {
    *(_BYTE *)--*(_QWORD *)(a2 + 112) = 0;
    if ( *(int *)(a2 + 48) >= 0 )
      ++*(_QWORD *)(a2 + 56);
  }
  ReportIdentifier = GetReportIdentifier(v4, **(unsigned __int8 **)(a2 + 112));
  if ( ReportIdentifier )
  {
    v6 = *(unsigned __int8 *)(ReportIdentifier + 1);
    HidclassCollection = GetHidclassCollection(v4, *(unsigned __int8 *)(ReportIdentifier + 1));
    CollectionDesc = GetCollectionDesc(v4, v6, v8);
    if ( HidclassCollection )
    {
      if ( CollectionDesc )
      {
        v11 = *(unsigned int *)(a2 + 56);
        if ( *(int *)(a2 + 48) >= 0 )
        {
          CheckReportPowerEvent(v10, HidclassCollection, *(CHAR **)(a2 + 112), v11);
          if ( *(_DWORD *)(HidclassCollection + 336) )
          {
            *(_BYTE *)(HidclassCollection + 252) = 1;
          }
          else
          {
            v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(HidclassCollection + 232));
            memmove(*(void **)(HidclassCollection + 240), *(const void **)(a2 + 112), v11);
            *(_DWORD *)(HidclassCollection + 248) = v11;
            *(_BYTE *)(HidclassCollection + 252) = 0;
            KeReleaseSpinLock((PKSPIN_LOCK)(HidclassCollection + 232), v12);
          }
        }
        CompleteQueuedIrpsForPolled(v4, v6, *(const void **)(a2 + 112), v11, *(_DWORD *)(a2 + 48));
      }
    }
  }
  ExFreePoolWithTag(*(PVOID *)(a2 + 112), 0);
  IoFreeIrp((PIRP)a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x18000ac70  push    rbx
0x18000ac72  push    rbp
0x18000ac73  push    rsi
0x18000ac74  push    rdi
0x18000ac75  push    r12
0x18000ac77  push    r14
0x18000ac79  push    r15
0x18000ac7b  sub     rsp, 30h
0x18000ac7f  mov     r14, [r8+40h]
0x18000ac83  mov     rsi, rdx
0x18000ac86  add     r14, 20h ; ' '
0x18000ac8a  mov     rax, [r14+0B0h]
0x18000ac91  cmp     byte ptr [rax], 0
0x18000ac94  jnz     short loc_18000ACAB
0x18000ac96  dec     qword ptr [rdx+70h]
0x18000ac9a  mov     rax, [rdx+70h]
0x18000ac9e  mov     byte ptr [rax], 0
0x18000aca1  cmp     dword ptr [rdx+30h], 0
0x18000aca5  jl      short loc_18000ACAB
0x18000aca7  inc     qword ptr [rdx+38h]
0x18000acab  mov     rax, [rdx+70h]
0x18000acaf  mov     rcx, r14
0x18000acb2  movzx   edx, byte ptr [rax]
0x18000acb5  call    GetReportIdentifier
0x18000acba  test    rax, rax
0x18000acbd  jz      loc_18000AD81
0x18000acc3  movzx   r12d, byte ptr [rax+1]
0x18000acc8  mov     rcx, r14
0x18000accb  mov     edx, r12d
0x18000acce  call    GetHidclassCollection
0x18000acd3  mov     edx, r12d
0x18000acd6  mov     rcx, r14
0x18000acd9  mov     rbp, rax
0x18000acdc  call    GetCollectionDesc
0x18000ace1  test    rbp, rbp
0x18000ace4  jz      loc_18000AD81
0x18000acea  test    rax, rax
0x18000aced  jz      loc_18000AD81
0x18000acf3  cmp     dword ptr [rsi+30h], 0
0x18000acf7  mov     r15d, [rsi+38h]
0x18000acfb  jl      short loc_18000AD68
0x18000acfd  mov     r8, [rsi+70h]
0x18000ad01  mov     r9d, r15d
0x18000ad04  mov     rdx, rbp
0x18000ad07  call    CheckReportPowerEvent
0x18000ad0c  cmp     dword ptr [rbp+150h], 0
0x18000ad13  jz      short loc_18000AD1E
0x18000ad15  mov     byte ptr [rbp+0FCh], 1
0x18000ad1c  jmp     short loc_18000AD68
0x18000ad1e  lea     rdi, [rbp+0E8h]
0x18000ad25  mov     rcx, rdi; SpinLock
0x18000ad28  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000ad2f  nop     dword ptr [rax+rax+00h]
0x18000ad34  mov     rdx, [rsi+70h]; Src
0x18000ad38  mov     r8, r15; Size
0x18000ad3b  mov     rcx, [rbp+0F0h]; void *
0x18000ad42  mov     bl, al
0x18000ad44  call    memmove
0x18000ad49  mov     dl, bl; NewIrql
0x18000ad4b  mov     [rbp+0F8h], r15d
0x18000ad52  mov     rcx, rdi; SpinLock
0x18000ad55  mov     byte ptr [rbp+0FCh], 0
0x18000ad5c  call    cs:__imp_KeReleaseSpinLock
0x18000ad63  nop     dword ptr [rax+rax+00h]
0x18000ad68  mov     eax, [rsi+30h]
0x18000ad6b  mov     r9d, r15d
0x18000ad6e  mov     r8, [rsi+70h]
0x18000ad72  mov     edx, r12d
0x18000ad75  mov     rcx, r14
0x18000ad78  mov     [rsp+68h+var_48], eax
0x18000ad7c  call    CompleteQueuedIrpsForPolled
0x18000ad81  mov     rcx, [rsi+70h]; P
0x18000ad85  xor     edx, edx; Tag
0x18000ad87  call    cs:__imp_ExFreePoolWithTag
0x18000ad8e  nop     dword ptr [rax+rax+00h]
0x18000ad93  mov     rcx, rsi; Irp
0x18000ad96  call    cs:__imp_IoFreeIrp
0x18000ad9d  nop     dword ptr [rax+rax+00h]
0x18000ada2  mov     eax, 0C0000016h
0x18000ada7  add     rsp, 30h
0x18000adab  pop     r15
0x18000adad  pop     r14
0x18000adaf  pop     r12
0x18000adb1  pop     rdi
0x18000adb2  pop     rsi
0x18000adb3  pop     rbp
0x18000adb4  pop     rbx
0x18000adb5  retn
```
