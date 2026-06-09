# OSKDuiFrame::HandleMoveDuringPressAndHold(tagPOINT *)

- ea: `0x14000eeb4`
- end: `0x14000efe9`
- name: `?HandleMoveDuringPressAndHold@OSKDuiFrame@@AEAAXPEAUtagPOINT@@@Z`
- size: `309`
- prototype: `void __fastcall(OSKDuiFrame *__hidden this, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000f620`

## callees

- `0x14000edf0`
- `0x14000eeb4`
- `0x14000f398`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `USER32!GetCursorPos` at `0x14000efb1`
- `USER32!GetCursorPos` at `0x14000efb1`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x14000ef41`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x14000ef41`

## pseudocode

```c
void __fastcall OSKDuiFrame::HandleMoveDuringPressAndHold(OSKDuiFrame *this, struct tagPOINT *a2)
{
  DirectUI::Element *v3; // rdi
  DirectUI::Element *v4; // rax
  struct DirectUI::Element *Parent; // rax
  __int64 v6; // rcx
  struct DirectUI::Element *v7; // [rsp+20h] [rbp-50h] BYREF
  struct DirectUI::Element *v8; // [rsp+28h] [rbp-48h] BYREF
  DirectUI::Element *v9; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+38h] [rbp-38h]
  __int64 v11; // [rsp+3Ch] [rbp-34h]
  __int64 v12; // [rsp+44h] [rbp-2Ch]
  int v13; // [rsp+4Ch] [rbp-24h]
  struct tagPOINT Point[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]

  if ( *((_BYTE *)this + 296) )
  {
    v3 = (DirectUI::Element *)*((_QWORD *)this + 38);
    v7 = OSKDuiFrame::ElementFromClientPointWorldwide(this, a2);
    (*(void (__fastcall **)(_QWORD, struct DirectUI::Element **))(**(_QWORD **)(*((_QWORD *)this + 34) + 24LL) + 336LL))(
      *(_QWORD *)(*((_QWORD *)this + 34) + 24LL),
      &v7);
    v4 = v7;
    *((_QWORD *)this + 38) = v7;
    if ( v3 != v4 )
    {
      *((_BYTE *)this + 296) = 0;
      OSKDuiFrame::KillPressAndHoldTimers(this);
      if ( v3 )
      {
        Parent = DirectUI::Element::GetParent(v3);
        v6 = *((_QWORD *)this + 34);
        v8 = Parent;
        if ( (*(int (__fastcall **)(_QWORD, struct DirectUI::Element *, struct DirectUI::Element **))(**(_QWORD **)(v6 + 24) + 352LL))(
               *(_QWORD *)(v6 + 24),
               Parent,
               &v8) >= 0 )
        {
          v10 = 0;
          v13 = 0;
          v11 = 1;
          *(_OWORD *)&Point[0].x = 0;
          LOBYTE(Point[1].x) = 1;
          v15 = 1;
          v9 = v3;
          v12 = 2;
          Point[1].y = 0;
          GetCursorPos(Point);
          (*(void (__fastcall **)(struct DirectUI::Element *, DirectUI::Element **))(*(_QWORD *)v8 + 72LL))(v8, &v9);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000eeb4  mov     [rsp-8+arg_10], rbx
0x14000eeb9  mov     [rsp-8+arg_18], rdi
0x14000eebe  push    rbp
0x14000eebf  mov     rbp, rsp
0x14000eec2  sub     rsp, 70h
0x14000eec6  mov     rax, cs:__security_cookie
0x14000eecd  xor     rax, rsp
0x14000eed0  mov     [rbp+var_8], rax
0x14000eed4  cmp     byte ptr [rcx+128h], 0
0x14000eedb  mov     rbx, rcx
0x14000eede  jz      loc_14000EFCB
0x14000eee4  mov     rdi, [rcx+130h]
0x14000eeeb  call    ?ElementFromClientPointWorldwide@OSKDuiFrame@@AEAAPEAVElement@DirectUI@@PEAUtagPOINT@@@Z; OSKDuiFrame::ElementFromClientPointWorldwide(tagPOINT *)
0x14000eef0  mov     [rbp+var_50], rax
0x14000eef4  lea     rdx, [rbp+var_50]
0x14000eef8  mov     rax, [rbx+110h]
0x14000eeff  mov     rcx, [rax+18h]
0x14000ef03  mov     rax, [rcx]
0x14000ef06  mov     rax, [rax+150h]
0x14000ef0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef12  mov     rax, [rbp+var_50]
0x14000ef16  mov     [rbx+130h], rax
0x14000ef1d  cmp     rdi, rax
0x14000ef20  jz      loc_14000EFCB
0x14000ef26  mov     rcx, rbx; this
0x14000ef29  mov     byte ptr [rbx+128h], 0
0x14000ef30  call    ?KillPressAndHoldTimers@OSKDuiFrame@@AEAAXXZ; OSKDuiFrame::KillPressAndHoldTimers(void)
0x14000ef35  test    rdi, rdi
0x14000ef38  jz      loc_14000EFCB
0x14000ef3e  mov     rcx, rdi
0x14000ef41  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x14000ef47  mov     rcx, [rbx+110h]
0x14000ef4e  lea     r8, [rbp+var_48]
0x14000ef52  mov     [rbp+var_48], rax
0x14000ef56  mov     r9, rax
0x14000ef59  mov     rcx, [rcx+18h]
0x14000ef5d  mov     rdx, [rcx]
0x14000ef60  mov     rax, [rdx+160h]
0x14000ef67  mov     rdx, r9
0x14000ef6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef6f  test    eax, eax
0x14000ef71  js      short loc_14000EFCB
0x14000ef73  xor     eax, eax
0x14000ef75  lea     rcx, [rbp+Point]; lpPoint
0x14000ef79  xorps   xmm0, xmm0
0x14000ef7c  mov     [rbp+var_10], rax
0x14000ef80  movups  [rbp+var_40], xmm0
0x14000ef84  mov     byte ptr [rbp+var_40+8], al
0x14000ef87  mov     eax, 1
0x14000ef8c  movups  [rbp+var_30], xmm0
0x14000ef90  mov     qword ptr [rbp+var_40+0Ch], rax
0x14000ef94  movups  xmmword ptr [rbp+Point.x], xmm0
0x14000ef98  mov     byte ptr [rbp+Point.x+8], al
0x14000ef9b  mov     dword ptr [rbp+var_10], eax
0x14000ef9e  mov     qword ptr [rbp+var_40], rdi
0x14000efa2  mov     qword ptr [rbp+var_30+4], 2
0x14000efaa  mov     [rbp+Point.y+8], 0
0x14000efb1  call    cs:__imp_GetCursorPos
0x14000efb7  mov     rcx, [rbp+var_48]
0x14000efbb  lea     rdx, [rbp+var_40]
0x14000efbf  mov     rax, [rcx]
0x14000efc2  mov     rax, [rax+48h]
0x14000efc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efcb  mov     rcx, [rbp+var_8]
0x14000efcf  xor     rcx, rsp; StackCookie
0x14000efd2  call    __security_check_cookie
0x14000efd7  lea     r11, [rsp+70h+var_s0]
0x14000efdc  mov     rbx, [r11+20h]
0x14000efe0  mov     rdi, [r11+28h]
0x14000efe4  mov     rsp, r11
0x14000efe7  pop     rbp
0x14000efe8  retn
```
