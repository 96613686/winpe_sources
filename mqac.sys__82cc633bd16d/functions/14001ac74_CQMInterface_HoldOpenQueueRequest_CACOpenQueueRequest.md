# CQMInterface::HoldOpenQueueRequest(CACOpenQueueRequest *)

- ea: `0x14001ac74`
- end: `0x14001ad25`
- name: `?HoldOpenQueueRequest@CQMInterface@@QEAAJPEAVCACOpenQueueRequest@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CQMInterface *__hidden this, struct CACOpenQueueRequest *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007460`

## callees

- `0x14001a900`
- `0x14001ac74`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001acf4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001acf4`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ac8e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ac8e`

## pseudocode

```c
__int64 __fastcall CQMInterface::HoldOpenQueueRequest(CQMInterface *this, struct CACOpenQueueRequest *a2)
{
  char *v4; // rbx
  char **v5; // rax
  __int64 v6; // rcx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  v4 = (char *)this + 72;
  *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 184LL) + 3LL) |= 1u;
  v5 = (char **)*((_QWORD *)v4 + 1);
  if ( *v5 != v4 )
    __fastfail(3u);
  *(_QWORD *)a2 = v4;
  *((_QWORD *)a2 + 1) = v5;
  *v5 = (char *)a2;
  *((_QWORD *)v4 + 1) = a2;
  v6 = *((_QWORD *)a2 + 2);
  if ( *(_BYTE *)(v6 + 68) )
  {
    *(_BYTE *)(v6 + 69) = Irql;
    CQMInterface::CancelOpenQueueRequest(0, *((struct _IRP **)a2 + 2));
  }
  else
  {
    **(_QWORD **)(*((_QWORD *)a2 + 3) + 32LL) = a2;
    _InterlockedExchange64(
      (volatile __int64 *)(*((_QWORD *)a2 + 2) + 104LL),
      (__int64)CQMInterface::CancelOpenQueueRequest);
    IoReleaseCancelSpinLock(Irql);
  }
  return 259;
}

```

## disassembly

```asm
0x14001ac74  mov     [rsp+arg_8], rbx
0x14001ac79  push    rdi
0x14001ac7a  sub     rsp, 20h
0x14001ac7e  mov     rbx, rcx
0x14001ac81  mov     [rsp+28h+Irql], 0
0x14001ac86  lea     rcx, [rsp+28h+Irql]; Irql
0x14001ac8b  mov     rdi, rdx
0x14001ac8e  call    cs:__imp_IoAcquireCancelSpinLock
0x14001ac95  nop     dword ptr [rax+rax+00h]
0x14001ac9a  mov     rax, [rdi+10h]
0x14001ac9e  add     rbx, 48h ; 'H'
0x14001aca2  mov     r8, [rax+0B8h]
0x14001aca9  or      byte ptr [r8+3], 1
0x14001acae  mov     rax, [rbx+8]
0x14001acb2  cmp     [rax], rbx
0x14001acb5  jz      short loc_14001ACBE
0x14001acb7  mov     ecx, 3
0x14001acbc  int     29h; Win8: RtlFailFast(ecx)
0x14001acbe  mov     [rdi], rbx
0x14001acc1  mov     [rdi+8], rax
0x14001acc5  mov     [rax], rdi
0x14001acc8  mov     [rbx+8], rdi
0x14001accc  mov     rcx, [rdi+10h]
0x14001acd0  cmp     byte ptr [rcx+44h], 0
0x14001acd4  jnz     short loc_14001AD02
0x14001acd6  mov     rax, [rdi+18h]
0x14001acda  mov     rcx, [rax+20h]
0x14001acde  lea     rax, ?CancelOpenQueueRequest@CQMInterface@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CQMInterface::CancelOpenQueueRequest(_DEVICE_OBJECT *,_IRP *)
0x14001ace5  mov     [rcx], rdi
0x14001ace8  mov     rcx, [rdi+10h]
0x14001acec  xchg    rax, [rcx+68h]
0x14001acf0  mov     cl, [rsp+28h+Irql]; Irql
0x14001acf4  call    cs:__imp_IoReleaseCancelSpinLock
0x14001acfb  nop     dword ptr [rax+rax+00h]
0x14001ad00  jmp     short loc_14001AD14
0x14001ad02  mov     al, [rsp+28h+Irql]
0x14001ad06  mov     [rcx+45h], al
0x14001ad09  xor     ecx, ecx; struct _DEVICE_OBJECT *
0x14001ad0b  mov     rdx, [rdi+10h]; struct _IRP *
0x14001ad0f  call    ?CancelOpenQueueRequest@CQMInterface@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CQMInterface::CancelOpenQueueRequest(_DEVICE_OBJECT *,_IRP *)
0x14001ad14  mov     rbx, [rsp+28h+arg_8]
0x14001ad19  mov     eax, 103h
0x14001ad1e  add     rsp, 20h
0x14001ad22  pop     rdi
0x14001ad23  retn
```
