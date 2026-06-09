# CKernelFilterDevice::FileObjectToFilterFile(_IRP *)

- ea: `0x1400017bc`
- end: `0x140001835`
- name: `?FileObjectToFilterFile@CKernelFilterDevice@@QEAAPEAVCKernelFilterFile@@PEAU_IRP@@@Z`
- size: `121`
- prototype: `struct CKernelFilterFile *__fastcall(KSPIN_LOCK *this, struct _IRP *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001370`
- `0x1400013d0`
- `0x140001700`
- `0x140001760`
- `0x1400021e0`

## callees

- `0x1400017bc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000181c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000181c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400017dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400017dc`

## pseudocode

```c
struct CKernelFilterFile *__fastcall CKernelFilterDevice::FileObjectToFilterFile(KSPIN_LOCK *this, struct _IRP *a2)
{
  KSPIN_LOCK *v2; // rsi
  PFILE_OBJECT FileObject; // rbp
  _QWORD **v4; // rbx
  KIRQL v5; // dl
  _QWORD *v6; // rax
  _QWORD *v7; // rdi

  v2 = this + 1;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v4 = (_QWORD **)(this + 2);
  v5 = KeAcquireSpinLockRaiseToDpc(this + 1);
  v6 = *v4;
  if ( *v4 )
  {
    while ( v6 != v4 )
    {
      v7 = v6 - 1;
      if ( (PFILE_OBJECT)v6[2] != FileObject )
      {
        v6 = (_QWORD *)*v6;
        if ( v6 )
          continue;
      }
      if ( v6 && v6 != v4 )
        goto LABEL_8;
      break;
    }
  }
  v7 = 0;
LABEL_8:
  KeReleaseSpinLock(v2, v5);
  return (struct CKernelFilterFile *)v7;
}

```

## disassembly

```asm
0x1400017bc  push    rbx
0x1400017be  push    rbp
0x1400017bf  push    rsi
0x1400017c0  push    rdi
0x1400017c1  sub     rsp, 28h
0x1400017c5  mov     rax, [rdx+0B8h]
0x1400017cc  lea     rsi, [rcx+8]
0x1400017d0  mov     rbx, rcx
0x1400017d3  xor     edi, edi
0x1400017d5  mov     rcx, rsi; SpinLock
0x1400017d8  mov     rbp, [rax+30h]
0x1400017dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400017e3  nop     dword ptr [rax+rax+00h]
0x1400017e8  add     rbx, 10h
0x1400017ec  mov     dl, al; NewIrql
0x1400017ee  mov     rax, [rbx]
0x1400017f1  test    rax, rax
0x1400017f4  jz      short loc_140001817
0x1400017f6  cmp     rax, rbx
0x1400017f9  jz      short loc_140001817
0x1400017fb  lea     rdi, [rax-8]
0x1400017ff  cmp     [rdi+18h], rbp
0x140001803  jz      short loc_14000180D
0x140001805  mov     rax, [rax]
0x140001808  test    rax, rax
0x14000180b  jnz     short loc_1400017F6
0x14000180d  test    rax, rax
0x140001810  jz      short loc_140001817
0x140001812  cmp     rax, rbx
0x140001815  jnz     short loc_140001819
0x140001817  xor     edi, edi
0x140001819  mov     rcx, rsi; SpinLock
0x14000181c  call    cs:__imp_KeReleaseSpinLock
0x140001823  nop     dword ptr [rax+rax+00h]
0x140001828  mov     rax, rdi
0x14000182b  add     rsp, 28h
0x14000182f  pop     rdi
0x140001830  pop     rsi
0x140001831  pop     rbp
0x140001832  pop     rbx
0x140001833  retn
```
