# EnumComplete

- ea: `0x1400157f4`
- end: `0x140015873`
- name: `EnumComplete`
- size: `127`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011838`
- `0x140011d04`
- `0x1400122b0`
- `0x1400133d0`
- `0x140013954`

## callees

- `0x1400157f4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015854`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015854`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015812`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015812`

## pseudocode

```c
void __fastcall EnumComplete(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rcx

  if ( *a1 )
  {
    if ( a2 )
      *(_BYTE *)(a2 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a2);
    v4 = *a1;
    if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v5 = (_QWORD *)a1[1], (_QWORD *)*v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    a1[1] = 0;
    *a1 = 0;
    if ( a2 )
      KeReleaseSpinLock((PKSPIN_LOCK)a2, *(_BYTE *)(a2 + 8));
  }
}

```

## disassembly

```asm
0x1400157f4  mov     [rsp+arg_0], rbx
0x1400157f9  push    rdi
0x1400157fa  sub     rsp, 20h
0x1400157fe  cmp     qword ptr [rcx], 0
0x140015802  mov     rbx, rdx
0x140015805  mov     rdi, rcx
0x140015808  jz      short loc_140015860
0x14001580a  test    rdx, rdx
0x14001580d  jz      short loc_140015821
0x14001580f  mov     rcx, rdx; SpinLock
0x140015812  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015819  nop     dword ptr [rax+rax+00h]
0x14001581e  mov     [rbx+8], al
0x140015821  mov     rax, [rdi]
0x140015824  cmp     [rax+8], rdi
0x140015828  jnz     short loc_14001586C
0x14001582a  mov     rcx, [rdi+8]
0x14001582e  cmp     [rcx], rdi
0x140015831  jnz     short loc_14001586C
0x140015833  mov     [rcx], rax
0x140015836  mov     [rax+8], rcx
0x14001583a  mov     qword ptr [rdi+8], 0
0x140015842  mov     qword ptr [rdi], 0
0x140015849  test    rbx, rbx
0x14001584c  jz      short loc_140015860
0x14001584e  mov     dl, [rbx+8]; NewIrql
0x140015851  mov     rcx, rbx; SpinLock
0x140015854  call    cs:__imp_KeReleaseSpinLock
0x14001585b  nop     dword ptr [rax+rax+00h]
0x140015860  mov     rbx, [rsp+28h+arg_0]
0x140015865  add     rsp, 20h
0x140015869  pop     rdi
0x14001586a  retn
0x14001586c  mov     ecx, 3
0x140015871  int     29h; Win8: RtlFailFast(ecx)
```
