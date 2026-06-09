# FveWrqCompleteRequestByCookie

- ea: `0x140025718`
- end: `0x140025902`
- name: `FveWrqCompleteRequestByCookie`
- size: `490`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14005a27c`
- `0x140079a40`
- `0x14007db90`
- `0x140083304`
- `0x1400c27fc`

## callees

- `0x140008e80`
- `0x14000bc14`
- `0x140022cd0`
- `0x140025718`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002586f`
- `ntoskrnl!IofCompleteRequest` at `0x14002586f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400257c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400257c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025773`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002580b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002580b`

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
0x140025718  push    rbx
0x14002571a  push    rbp
0x14002571b  push    rsi
0x14002571c  push    rdi
0x14002571d  push    r14
0x14002571f  sub     rsp, 30h
0x140025723  mov     ebp, r8d
0x140025726  mov     rdi, rdx
0x140025729  mov     r14, rcx
0x14002572c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025733  lea     rax, WPP_GLOBAL_Control
0x14002573a  cmp     rcx, rax
0x14002573d  jz      short loc_140025769
0x14002573f  mov     eax, [rcx+2Ch]
0x140025742  test    al, 8
0x140025744  jz      short loc_140025769
0x140025746  cmp     byte ptr [rcx+29h], 5
0x14002574a  jb      short loc_140025769
0x14002574c  mov     rcx, [rcx+18h]
0x140025750  mov     edx, 85h
0x140025755  mov     [rsp+58h+var_38], r8d
0x14002575a  mov     r9, rdi
0x14002575d  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140025764  call    WPP_SF_qd
0x140025769  lea     rsi, [r14+320h]
0x140025770  mov     rcx, rsi; SpinLock
0x140025773  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002577a  nop     dword ptr [rax+rax+00h]
0x14002577f  lea     r8, [r14+308h]
0x140025786  mov     r9b, al
0x140025789  mov     rcx, [r8]
0x14002578c  xor     ebx, ebx
0x14002578e  cmp     rcx, r8
0x140025791  jz      short loc_1400257C2
0x140025793  mov     rbx, rcx
0x140025796  mov     rdx, [rcx]
0x140025799  cmp     [rcx+10h], rdi
0x14002579d  jz      short loc_1400257A4
0x14002579f  mov     rcx, rdx
0x1400257a2  jmp     short loc_14002578C
0x1400257a4  cmp     [rdx+8], rcx
0x1400257a8  jnz     loc_140025853
0x1400257ae  mov     rax, [rcx+8]
0x1400257b2  cmp     [rax], rcx
0x1400257b5  jnz     loc_140025853
0x1400257bb  mov     [rax], rdx
0x1400257be  mov     [rdx+8], rax
0x1400257c2  mov     dl, r9b; NewIrql
0x1400257c5  mov     rcx, rsi; SpinLock
0x1400257c8  call    cs:__imp_KeReleaseSpinLock
0x1400257cf  nop     dword ptr [rax+rax+00h]
0x1400257d4  test    rbx, rbx
0x1400257d7  jz      loc_1400258C1
0x1400257dd  mov     rax, [rbx+20h]
0x1400257e1  test    rax, rax
0x1400257e4  jz      short loc_1400257FC
0x1400257e6  cmp     qword ptr [rbx+18h], 0
0x1400257eb  jz      short loc_14002585A
0x1400257ed  mov     rdx, [rbx+28h]
0x1400257f1  mov     r8d, ebp
0x1400257f4  mov     rcx, r14
0x1400257f7  call    _guard_dispatch_icall
0x1400257fc  lea     rdi, WPP_GLOBAL_Control
0x140025803  mov     edx, 30455646h; Tag
0x140025808  mov     rcx, rbx; P
0x14002580b  call    cs:__imp_ExFreePoolWithTag
0x140025812  nop     dword ptr [rax+rax+00h]
0x140025817  mov     rcx, cs:WPP_GLOBAL_Control
0x14002581e  cmp     rcx, rdi
0x140025821  jz      loc_1400258F6
0x140025827  mov     eax, [rcx+2Ch]
0x14002582a  test    al, 8
0x14002582c  jz      loc_1400258C8
0x140025832  cmp     byte ptr [rcx+29h], 5
0x140025836  jb      loc_1400258C8
0x14002583c  mov     rcx, [rcx+18h]
0x140025840  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140025847  mov     edx, 87h
0x14002584c  call    WPP_SF_
0x140025851  jmp     short loc_1400258C8
0x140025853  mov     ecx, 3
0x140025858  int     29h; Win8: RtlFailFast(ecx)
0x14002585a  mov     qword ptr [rax+38h], 0
0x140025862  xor     edx, edx; PriorityBoost
0x140025864  mov     rax, [rbx+20h]
0x140025868  mov     [rax+30h], ebp
0x14002586b  mov     rcx, [rbx+20h]; Irp
0x14002586f  call    cs:__imp_IofCompleteRequest
0x140025876  nop     dword ptr [rax+rax+00h]
0x14002587b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025882  lea     rdi, WPP_GLOBAL_Control
0x140025889  cmp     rcx, rdi
0x14002588c  jz      loc_140025803
0x140025892  mov     eax, [rcx+2Ch]
0x140025895  test    al, 8
0x140025897  jz      loc_140025803
0x14002589d  cmp     byte ptr [rcx+29h], 5
0x1400258a1  jb      loc_140025803
0x1400258a7  mov     rcx, [rcx+18h]
0x1400258ab  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400258b2  mov     edx, 86h
0x1400258b7  call    WPP_SF_
0x1400258bc  jmp     loc_140025803
0x1400258c1  lea     rdi, WPP_GLOBAL_Control
0x1400258c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400258cf  cmp     rcx, rdi
0x1400258d2  jz      short loc_1400258F6
0x1400258d4  mov     eax, [rcx+2Ch]
0x1400258d7  test    al, 8
0x1400258d9  jz      short loc_1400258F6
0x1400258db  cmp     byte ptr [rcx+29h], 5
0x1400258df  jb      short loc_1400258F6
0x1400258e1  mov     rcx, [rcx+18h]
0x1400258e5  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400258ec  mov     edx, 88h
0x1400258f1  call    WPP_SF_
0x1400258f6  add     rsp, 30h
0x1400258fa  pop     r14
0x1400258fc  pop     rdi
0x1400258fd  pop     rsi
0x1400258fe  pop     rbp
0x1400258ff  pop     rbx
0x140025900  retn
```
