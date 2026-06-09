# CTransaction::CompletePendingReaders(void)

- ea: `0x14001faa4`
- end: `0x14001fb17`
- name: `?CompletePendingReaders@CTransaction@@AEAAXXZ`
- size: `115`
- prototype: `void __fastcall(CTransaction *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001f1c4`
- `0x14001f3dc`
- `0x14001f4e0`
- `0x14001f56c`
- `0x14001f714`
- `0x14001f8d4`
- `0x14001fcc8`
- `0x14001fe88`

## callees

- `0x140003a48`
- `0x14001faa4`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001faff`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001faff`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001fac4`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001fac4`

## pseudocode

```c
void __fastcall CTransaction::CompletePendingReaders(CTransaction *this)
{
  _QWORD *v1; // rbx
  __int64 v3; // r8
  __int64 v4; // rdx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 96);
  if ( (_QWORD *)*v1 != v1 )
  {
    Irql = 0;
    while ( 1 )
    {
      IoAcquireCancelSpinLock(&Irql);
      v4 = 0;
      if ( (_QWORD *)*v1 != v1 )
        v4 = *v1 - 120LL;
      if ( !v4 )
        break;
      LOBYTE(v3) = Irql;
      ACCancelIrp(*((_QWORD *)this + 8), v4, v3, 3222143057LL);
    }
    IoReleaseCancelSpinLock(Irql);
  }
}

```

## disassembly

```asm
0x14001faa4  mov     [rsp+arg_8], rbx
0x14001faa9  push    rdi
0x14001faaa  sub     rsp, 20h
0x14001faae  lea     rbx, [rcx+60h]
0x14001fab2  mov     rdi, rcx
0x14001fab5  cmp     [rbx], rbx
0x14001fab8  jz      short loc_14001FB0B
0x14001faba  mov     [rsp+28h+Irql], 0
0x14001fabf  lea     rcx, [rsp+28h+Irql]; Irql
0x14001fac4  call    cs:__imp_IoAcquireCancelSpinLock
0x14001facb  nop     dword ptr [rax+rax+00h]
0x14001fad0  mov     rcx, [rbx]
0x14001fad3  xor     edx, edx
0x14001fad5  cmp     rcx, rbx
0x14001fad8  lea     rax, [rcx-78h]
0x14001fadc  cmovnz  rdx, rax
0x14001fae0  test    rdx, rdx
0x14001fae3  jz      short loc_14001FAFB
0x14001fae5  mov     r8b, [rsp+28h+Irql]
0x14001faea  mov     r9d, 0C00E0051h
0x14001faf0  mov     rcx, [rdi+40h]
0x14001faf4  call    ACCancelIrp
0x14001faf9  jmp     short loc_14001FABF
0x14001fafb  mov     cl, [rsp+28h+Irql]; Irql
0x14001faff  call    cs:__imp_IoReleaseCancelSpinLock
0x14001fb06  nop     dword ptr [rax+rax+00h]
0x14001fb0b  mov     rbx, [rsp+28h+arg_8]
0x14001fb10  add     rsp, 20h
0x14001fb14  pop     rdi
0x14001fb15  retn
```
