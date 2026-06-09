# FveWrqCompleteRequestByCookie

- ea: `0x140024718`
- end: `0x140024902`
- name: `FveWrqCompleteRequestByCookie`
- size: `490`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14005822c`
- `0x140077a10`
- `0x14007baf0`
- `0x140081264`
- `0x1400bed8c`

## callees

- `0x140008dc0`
- `0x14000ba88`
- `0x1400219a0`
- `0x140024718`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002486f`
- `ntoskrnl!IofCompleteRequest` at `0x14002486f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400247c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400247c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024773`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002480b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002480b`

## pseudocode

```c
void __fastcall FveWrqCompleteRequestByCookie(__int64 a1, __int64 a2, unsigned int a3)
{
  KIRQL v6; // r9
  _QWORD *i; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, a2, a3);
  }
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 800));
  for ( i = *(_QWORD **)(a1 + 776); ; i = (_QWORD *)*i )
  {
    v8 = 0;
    if ( i == (_QWORD *)(a1 + 776) )
      break;
    v8 = i;
    v9 = (_QWORD *)*i;
    if ( i[2] == a2 )
    {
      if ( (_QWORD *)v9[1] != i || (v10 = (_QWORD *)i[1], (_QWORD *)*v10 != i) )
        __fastfail(3u);
      *v10 = v9;
      v9[1] = v10;
      break;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 800), v6);
  if ( !v8 )
    goto LABEL_25;
  v11 = v8[4];
  if ( v11 )
  {
    if ( v8[3] )
    {
      ((void (__fastcall *)(__int64, _QWORD, _QWORD))v11)(a1, v8[5], a3);
    }
    else
    {
      *(_QWORD *)(v11 + 56) = 0;
      *(_DWORD *)(v8[4] + 48LL) = a3;
      IofCompleteRequest((PIRP)v8[4], 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
      }
    }
  }
  ExFreePoolWithTag(v8, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
LABEL_25:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x140024718  push    rbx
0x14002471a  push    rbp
0x14002471b  push    rsi
0x14002471c  push    rdi
0x14002471d  push    r14
0x14002471f  sub     rsp, 30h
0x140024723  mov     ebp, r8d
0x140024726  mov     rdi, rdx
0x140024729  mov     r14, rcx
0x14002472c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024733  lea     rax, WPP_GLOBAL_Control
0x14002473a  cmp     rcx, rax
0x14002473d  jz      short loc_140024769
0x14002473f  mov     eax, [rcx+2Ch]
0x140024742  test    al, 8
0x140024744  jz      short loc_140024769
0x140024746  cmp     byte ptr [rcx+29h], 5
0x14002474a  jb      short loc_140024769
0x14002474c  mov     rcx, [rcx+18h]
0x140024750  mov     edx, 85h
0x140024755  mov     [rsp+58h+var_38], r8d
0x14002475a  mov     r9, rdi
0x14002475d  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140024764  call    WPP_SF_qd
0x140024769  lea     rsi, [r14+320h]
0x140024770  mov     rcx, rsi; SpinLock
0x140024773  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002477a  nop     dword ptr [rax+rax+00h]
0x14002477f  lea     r8, [r14+308h]
0x140024786  mov     r9b, al
0x140024789  mov     rcx, [r8]
0x14002478c  xor     ebx, ebx
0x14002478e  cmp     rcx, r8
0x140024791  jz      short loc_1400247C2
0x140024793  mov     rbx, rcx
0x140024796  mov     rdx, [rcx]
0x140024799  cmp     [rcx+10h], rdi
0x14002479d  jz      short loc_1400247A4
0x14002479f  mov     rcx, rdx
0x1400247a2  jmp     short loc_14002478C
0x1400247a4  cmp     [rdx+8], rcx
0x1400247a8  jnz     loc_140024853
0x1400247ae  mov     rax, [rcx+8]
0x1400247b2  cmp     [rax], rcx
0x1400247b5  jnz     loc_140024853
0x1400247bb  mov     [rax], rdx
0x1400247be  mov     [rdx+8], rax
0x1400247c2  mov     dl, r9b; NewIrql
0x1400247c5  mov     rcx, rsi; SpinLock
0x1400247c8  call    cs:__imp_KeReleaseSpinLock
0x1400247cf  nop     dword ptr [rax+rax+00h]
0x1400247d4  test    rbx, rbx
0x1400247d7  jz      loc_1400248C1
0x1400247dd  mov     rax, [rbx+20h]
0x1400247e1  test    rax, rax
0x1400247e4  jz      short loc_1400247FC
0x1400247e6  cmp     qword ptr [rbx+18h], 0
0x1400247eb  jz      short loc_14002485A
0x1400247ed  mov     rdx, [rbx+28h]
0x1400247f1  mov     r8d, ebp
0x1400247f4  mov     rcx, r14
0x1400247f7  call    _guard_dispatch_icall
0x1400247fc  lea     rdi, WPP_GLOBAL_Control
0x140024803  mov     edx, 30455646h; Tag
0x140024808  mov     rcx, rbx; P
0x14002480b  call    cs:__imp_ExFreePoolWithTag
0x140024812  nop     dword ptr [rax+rax+00h]
0x140024817  mov     rcx, cs:WPP_GLOBAL_Control
0x14002481e  cmp     rcx, rdi
0x140024821  jz      loc_1400248F6
0x140024827  mov     eax, [rcx+2Ch]
0x14002482a  test    al, 8
0x14002482c  jz      loc_1400248C8
0x140024832  cmp     byte ptr [rcx+29h], 5
0x140024836  jb      loc_1400248C8
0x14002483c  mov     rcx, [rcx+18h]
0x140024840  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140024847  mov     edx, 87h
0x14002484c  call    WPP_SF_
0x140024851  jmp     short loc_1400248C8
0x140024853  mov     ecx, 3
0x140024858  int     29h; Win8: RtlFailFast(ecx)
0x14002485a  mov     qword ptr [rax+38h], 0
0x140024862  xor     edx, edx; PriorityBoost
0x140024864  mov     rax, [rbx+20h]
0x140024868  mov     [rax+30h], ebp
0x14002486b  mov     rcx, [rbx+20h]; Irp
0x14002486f  call    cs:__imp_IofCompleteRequest
0x140024876  nop     dword ptr [rax+rax+00h]
0x14002487b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024882  lea     rdi, WPP_GLOBAL_Control
0x140024889  cmp     rcx, rdi
0x14002488c  jz      loc_140024803
0x140024892  mov     eax, [rcx+2Ch]
0x140024895  test    al, 8
0x140024897  jz      loc_140024803
0x14002489d  cmp     byte ptr [rcx+29h], 5
0x1400248a1  jb      loc_140024803
0x1400248a7  mov     rcx, [rcx+18h]
0x1400248ab  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400248b2  mov     edx, 86h
0x1400248b7  call    WPP_SF_
0x1400248bc  jmp     loc_140024803
0x1400248c1  lea     rdi, WPP_GLOBAL_Control
0x1400248c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248cf  cmp     rcx, rdi
0x1400248d2  jz      short loc_1400248F6
0x1400248d4  mov     eax, [rcx+2Ch]
0x1400248d7  test    al, 8
0x1400248d9  jz      short loc_1400248F6
0x1400248db  cmp     byte ptr [rcx+29h], 5
0x1400248df  jb      short loc_1400248F6
0x1400248e1  mov     rcx, [rcx+18h]
0x1400248e5  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400248ec  mov     edx, 88h
0x1400248f1  call    WPP_SF_
0x1400248f6  add     rsp, 30h
0x1400248fa  pop     r14
0x1400248fc  pop     rdi
0x1400248fd  pop     rsi
0x1400248fe  pop     rbp
0x1400248ff  pop     rbx
0x140024900  retn
```
