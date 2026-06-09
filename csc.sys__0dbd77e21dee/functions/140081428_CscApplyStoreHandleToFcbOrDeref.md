# CscApplyStoreHandleToFcbOrDeref

- ea: `0x140081428`
- end: `0x1400817e5`
- name: `CscApplyStoreHandleToFcbOrDeref`
- size: `957`
- prototype: `__int64 __fastcall(PMRX_FCB Fcb, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140062b70`
- `0x14008caec`

## callees

- `0x14000a634`
- `0x140016a04`
- `0x140018930`
- `0x1400190ec`
- `0x14001b5bc`
- `0x14001b710`
- `0x140081428`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400814b3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400814b3`
- `rdbss!RxIterateOnFcbOpens` at `0x140081514`
- `rdbss!RxIterateOnFcbOpens` at `0x140081679`
- `rdbss!RxIterateOnFcbOpens` at `0x140081514`
- `rdbss!RxIterateOnFcbOpens` at `0x140081679`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140081585`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140081585`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x1400816fd`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x1400816fd`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x1400817d4`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x1400817d4`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x1400814d6`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x1400814d6`

## pseudocode

```c
__int64 __fastcall CscApplyStoreHandleToFcbOrDeref(PMRX_FCB Fcb, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v5; // rbx
  char v6; // r13
  unsigned int v7; // esi
  __int64 v8; // r8
  char v9; // r12
  int v10; // r15d
  struct _LIST_ENTRY *v11; // rcx
  PDEVICE_OBJECT v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // [rsp+28h] [rbp-40h]
  struct _LIST_ENTRY *v17; // [rsp+70h] [rbp+8h] BYREF
  struct _LIST_ENTRY *v18; // [rsp+78h] [rbp+10h] BYREF
  __int64 v19; // [rsp+80h] [rbp+18h] BYREF

  v18 = a2;
  Flink = Fcb->Header.FilterContexts.Flink;
  v5 = Flink[9].Flink;
  if ( v5 && LOWORD(v5->Flink) != 0xEAA1 )
    v5 = 0;
  v17 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 185, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, Flink);
  if ( !v5 || !a2 )
  {
    v7 = -1073741811;
    v10 = 10304;
    goto LABEL_24;
  }
  v6 = 0;
  v7 = 0;
  v9 = 1;
  if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)Flink->Blink) )
  {
    v7 = RxAcquireExclusiveFcbResourceInMRx(Fcb);
    if ( v7 )
    {
      v9 = 0;
      v10 = 10320;
      goto LABEL_38;
    }
    v6 = 1;
  }
  LOBYTE(v8) = 1;
  v10 = 0;
  RxAcquireExclusiveFcbPagingInMRx(Fcb, Flink, v8);
  if ( !v5[3].Blink )
  {
    v17 = a2;
    v7 = RxIterateOnFcbOpens(Fcb, Flink, CscSrvOpenObtainStoreHandleCallBack, CscFobxAllocateContextCallback, &v17, 0);
    if ( !v7 )
    {
      v11 = Flink[9].Flink;
      if ( v11 && LOWORD(v11->Flink) != 0xEAA1 )
        v11 = 0;
      v11[3].Blink = a2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          Flink,
          a2,
          0);
      v7 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          188,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          a2,
          Flink,
          Fcb->Header.PushLock);
      goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v7);
    v10 = 10351;
    LOBYTE(v16) = 0;
    BYTE4(v19) = 0;
    v14 = RxIterateOnFcbOpens(Fcb, Flink, CscSrvOpenCloseStoreStateCallBack, 0, &v19, v16);
    if ( v14
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 189, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v14);
    }
LABEL_38:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v15 = 191;
LABEL_47:
      WPP_SF_qqq(
        v13->AttachedDevice,
        v15,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        a2,
        Flink,
        Fcb->Header.PushLock);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v15 = 190;
    goto LABEL_47;
  }
LABEL_31:
  CscStoreDereferenceEntry(&v18);
  if ( v9 )
LABEL_21:
    RxReleaseFcbPagingInMRx(Fcb, Flink);
  if ( v6 )
    RxReleaseFcbResourceInMRx(Fcb);
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 192, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v7, v10);
  return v7;
}

```

## disassembly

```asm
0x140081428  mov     [rsp+arg_18], rbx
0x14008142d  mov     [rsp+arg_8], rdx
0x140081432  push    rbp
0x140081433  push    rsi
0x140081434  push    rdi
0x140081435  push    r12
0x140081437  push    r13
0x140081439  push    r14
0x14008143b  push    r15
0x14008143d  sub     rsp, 30h
0x140081441  mov     rdi, [rcx+38h]
0x140081445  mov     rbp, rcx
0x140081448  mov     r14, rdx
0x14008144b  mov     ecx, 0EAA1h
0x140081450  mov     rbx, [rdi+90h]
0x140081457  test    rbx, rbx
0x14008145a  jz      short loc_140081465
0x14008145c  xor     eax, eax
0x14008145e  cmp     cx, [rbx]
0x140081461  cmovnz  rbx, rax
0x140081465  mov     [rsp+68h+arg_0], 0
0x14008146e  mov     [rsp+68h+arg_10], 0
0x14008147a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081481  lea     rax, WPP_GLOBAL_Control
0x140081488  cmp     rcx, rax
0x14008148b  jz      short loc_140081498
0x14008148d  mov     eax, [rcx+2Ch]
0x140081490  test    al, 40h
0x140081492  jnz     loc_1400816DA
0x140081498  test    rbx, rbx
0x14008149b  jz      loc_1400815E8
0x1400814a1  test    r14, r14
0x1400814a4  jz      loc_1400815E8
0x1400814aa  mov     rcx, [rdi+8]; Resource
0x1400814ae  xor     r13b, r13b
0x1400814b1  xor     esi, esi
0x1400814b3  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400814ba  nop     dword ptr [rax+rax+00h]
0x1400814bf  mov     r12b, 1
0x1400814c2  test    al, al
0x1400814c4  jz      loc_1400816F7
0x1400814ca  mov     r8b, r12b
0x1400814cd  mov     rdx, rdi
0x1400814d0  mov     rcx, rbp
0x1400814d3  xor     r15d, r15d
0x1400814d6  call    cs:__imp_RxAcquireExclusiveFcbPagingInMRx
0x1400814dd  nop     dword ptr [rax+rax+00h]
0x1400814e2  cmp     [rbx+38h], r15
0x1400814e6  jnz     loc_1400815FC
0x1400814ec  lea     rax, [rsp+68h+arg_0]
0x1400814f1  mov     byte ptr [rsp+68h+var_40], r15b
0x1400814f6  lea     r9, CscFobxAllocateContextCallback
0x1400814fd  mov     [rsp+68h+var_48], rax
0x140081502  lea     r8, CscSrvOpenObtainStoreHandleCallBack
0x140081509  mov     [rsp+68h+arg_0], r14
0x14008150e  mov     rdx, rdi
0x140081511  mov     rcx, rbp
0x140081514  call    cs:__imp_RxIterateOnFcbOpens
0x14008151b  nop     dword ptr [rax+rax+00h]
0x140081520  mov     esi, eax
0x140081522  test    eax, eax
0x140081524  jnz     loc_140081632
0x14008152a  mov     rcx, [rdi+90h]
0x140081531  test    rcx, rcx
0x140081534  jz      short loc_140081544
0x140081536  xor     eax, eax
0x140081538  mov     edx, 0EAA1h
0x14008153d  cmp     dx, [rcx]
0x140081540  cmovnz  rcx, rax
0x140081544  mov     [rcx+38h], r14
0x140081548  mov     rcx, cs:WPP_GLOBAL_Control
0x14008154f  lea     rbx, WPP_GLOBAL_Control
0x140081556  cmp     rcx, rbx
0x140081559  jz      short loc_140081566
0x14008155b  mov     eax, [rcx+2Ch]
0x14008155e  test    al, 40h
0x140081560  jnz     loc_140081751
0x140081566  xor     esi, esi
0x140081568  mov     rcx, cs:WPP_GLOBAL_Control
0x14008156f  cmp     rcx, rbx
0x140081572  jz      short loc_14008157F
0x140081574  mov     eax, [rcx+2Ch]
0x140081577  test    al, 40h
0x140081579  jnz     loc_140081778
0x14008157f  mov     rdx, rdi
0x140081582  mov     rcx, rbp
0x140081585  call    cs:__imp_RxReleaseFcbPagingInMRx
0x14008158c  nop     dword ptr [rax+rax+00h]
0x140081591  test    r13b, r13b
0x140081594  jnz     loc_1400817CE
0x14008159a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400815a1  cmp     rcx, rbx
0x1400815a4  jnz     short loc_1400815C1
0x1400815a6  mov     rbx, [rsp+68h+arg_18]
0x1400815ae  mov     eax, esi
0x1400815b0  add     rsp, 30h
0x1400815b4  pop     r15
0x1400815b6  pop     r14
0x1400815b8  pop     r13
0x1400815ba  pop     r12
0x1400815bc  pop     rdi
0x1400815bd  pop     rsi
0x1400815be  pop     rbp
0x1400815bf  retn
0x1400815c1  mov     edx, [rcx+2Ch]
0x1400815c4  test    dl, 20h
0x1400815c7  jz      short loc_1400815A6
0x1400815c9  mov     rcx, [rcx+18h]
0x1400815cd  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400815d4  mov     edx, 0C0h
0x1400815d9  mov     dword ptr [rsp+68h+var_48], r15d
0x1400815de  mov     r9d, esi
0x1400815e1  call    WPP_SF_Dd
0x1400815e6  jmp     short loc_1400815A6
0x1400815e8  mov     esi, 0C000000Dh
0x1400815ed  lea     rbx, WPP_GLOBAL_Control
0x1400815f4  mov     r15d, 2840h
0x1400815fa  jmp     short loc_14008159A
0x1400815fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140081603  lea     rbx, WPP_GLOBAL_Control
0x14008160a  cmp     rcx, rbx
0x14008160d  jz      short loc_14008161A
0x14008160f  mov     eax, [rcx+2Ch]
0x140081612  test    al, 40h
0x140081614  jnz     loc_1400817A3
0x14008161a  lea     rcx, [rsp+68h+arg_8]
0x14008161f  call    CscStoreDereferenceEntry
0x140081624  test    r12b, r12b
0x140081627  jnz     loc_14008157F
0x14008162d  jmp     loc_140081591
0x140081632  mov     rcx, cs:WPP_GLOBAL_Control
0x140081639  lea     rbx, WPP_GLOBAL_Control
0x140081640  cmp     rcx, rbx
0x140081643  jnz     loc_140081729
0x140081649  mov     r15d, 286Fh
0x14008164f  lea     rax, [rsp+68h+arg_10]
0x140081657  mov     byte ptr [rsp+68h+var_40], 0
0x14008165c  xor     r9d, r9d
0x14008165f  mov     [rsp+68h+var_48], rax
0x140081664  lea     r8, CscSrvOpenCloseStoreStateCallBack
0x14008166b  mov     byte ptr [rsp+68h+arg_10+4], 0
0x140081673  mov     rdx, rdi
0x140081676  mov     rcx, rbp
0x140081679  call    cs:__imp_RxIterateOnFcbOpens
0x140081680  nop     dword ptr [rax+rax+00h]
0x140081685  test    eax, eax
0x140081687  jz      short loc_1400816B5
0x140081689  mov     rcx, cs:WPP_GLOBAL_Control
0x140081690  cmp     rcx, rbx
0x140081693  jz      short loc_1400816B5
0x140081695  mov     edx, [rcx+2Ch]
0x140081698  test    dl, 20h
0x14008169b  jz      short loc_1400816B5
0x14008169d  mov     rcx, [rcx+18h]
0x1400816a1  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400816a8  mov     edx, 0BDh
0x1400816ad  mov     r9d, eax
0x1400816b0  call    WPP_SF_d
0x1400816b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400816bc  cmp     rcx, rbx
0x1400816bf  jz      loc_14008161A
0x1400816c5  mov     eax, [rcx+2Ch]
0x1400816c8  test    al, 40h
0x1400816ca  jz      loc_14008161A
0x1400816d0  mov     edx, 0BFh
0x1400816d5  jmp     loc_1400817A8
0x1400816da  mov     rcx, [rcx+18h]
0x1400816de  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400816e5  mov     edx, 0B9h
0x1400816ea  mov     r9, rdi
0x1400816ed  call    WPP_SF_q
0x1400816f2  jmp     loc_140081498
0x1400816f7  mov     rdx, rdi
0x1400816fa  mov     rcx, rbp; Fcb
0x1400816fd  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x140081704  nop     dword ptr [rax+rax+00h]
0x140081709  mov     esi, eax
0x14008170b  test    eax, eax
0x14008170d  jz      short loc_140081721
0x14008170f  xor     r12b, r12b
0x140081712  lea     rbx, WPP_GLOBAL_Control
0x140081719  mov     r15d, 2850h
0x14008171f  jmp     short loc_1400816B5
0x140081721  mov     r13b, r12b
0x140081724  jmp     loc_1400814CA
0x140081729  mov     eax, [rcx+2Ch]
0x14008172c  test    al, 40h
0x14008172e  jz      loc_140081649
0x140081734  mov     rcx, [rcx+18h]
0x140081738  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14008173f  mov     edx, 0BAh
0x140081744  mov     r9d, esi
0x140081747  call    WPP_SF_d
0x14008174c  jmp     loc_140081649
0x140081751  mov     rcx, [rcx+18h]
0x140081755  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14008175c  mov     edx, 0Fh
0x140081761  mov     [rsp+68h+var_40], r15d
0x140081766  mov     r9, rdi
0x140081769  mov     [rsp+68h+var_48], r14
0x14008176e  call    WPP_SF_qqD
0x140081773  jmp     loc_140081566
0x140081778  mov     rax, [rbp+48h]
0x14008177c  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140081783  mov     rcx, [rcx+18h]
0x140081787  mov     edx, 0BCh
0x14008178c  mov     qword ptr [rsp+68h+var_40], rax
0x140081791  mov     r9, r14
0x140081794  mov     [rsp+68h+var_48], rdi
0x140081799  call    WPP_SF_qqq
0x14008179e  jmp     loc_14008157F
0x1400817a3  mov     edx, 0BEh
0x1400817a8  mov     rax, [rbp+48h]
0x1400817ac  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400817b3  mov     rcx, [rcx+18h]
0x1400817b7  mov     r9, r14
0x1400817ba  mov     qword ptr [rsp+68h+var_40], rax
0x1400817bf  mov     [rsp+68h+var_48], rdi
0x1400817c4  call    WPP_SF_qqq
0x1400817c9  jmp     loc_14008161A
0x1400817ce  mov     rdx, rdi
0x1400817d1  mov     rcx, rbp; Fcb
0x1400817d4  call    cs:__imp_RxReleaseFcbResourceInMRx
0x1400817db  nop     dword ptr [rax+rax+00h]
0x1400817e0  jmp     loc_14008159A
```
