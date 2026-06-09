# RmtMovePointer(_SURFOBJ *,long,long,_RECTL *)

- ea: `0x1400359f0`
- end: `0x140035a82`
- name: `?RmtMovePointer@@YAXPEAU_SURFOBJ@@JJPEAU_RECTL@@@Z`
- size: `146`
- prototype: `void __fastcall(struct _SURFOBJ *, int, int, struct _RECTL *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x14001d1b0`
- `0x140024f20`
- `0x140025030`
- `0x14002733c`
- `0x14002793c`
- `0x140027c48`
- `0x1400359f0`
- `0x1400372d0`

## pseudocode

```c
void __fastcall RmtMovePointer(struct _SURFOBJ *a1, unsigned int a2, unsigned int a3, struct _RECTL *a4)
{
  __int64 v8; // rdx
  struct _DDI_DISPATCH_TABLE *v9; // rax
  __int64 v10; // rcx
  _BYTE v11[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h]

  SURFSWITCHLOCK::SURFSWITCHLOCK((SURFSWITCHLOCK *)v11, a1, 0);
  SURFACCESS::SURFACCESS((SURFACCESS *)v11, a1);
  v9 = SURFACCESS::Dispatch((SURFACCESS *)v11, v8);
  (*((void (__fastcall **)(struct _SURFOBJ *, _QWORD, _QWORD, struct _RECTL *))v9 + 30))(a1, a2, a3, a4);
  v10 = *(_QWORD *)(v12 + 8);
  if ( v10 )
    MovePointerInternal((struct _POINTER_INFO *)(v10 + 1120), a2, a3, 0);
  SURFACCESS::~SURFACCESS((SURFACCESS *)v11);
  SURFSWITCHLOCK::~SURFSWITCHLOCK((SURFSWITCHLOCK *)v11);
}

```

## disassembly

```asm
0x1400359f0  push    rbx
0x1400359f2  push    rbp
0x1400359f3  push    rsi
0x1400359f4  push    rdi
0x1400359f5  sub     rsp, 58h
0x1400359f9  mov     ebp, edx
0x1400359fb  mov     esi, r8d
0x1400359fe  mov     rdx, rcx; struct _SURFOBJ *
0x140035a01  mov     rdi, rcx
0x140035a04  lea     rcx, [rsp+78h+var_48]; this
0x140035a09  xor     r8d, r8d; struct _SURFOBJ *
0x140035a0c  mov     rbx, r9
0x140035a0f  call    ??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z; SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)
0x140035a14  mov     rdx, rdi; struct _SURFOBJ *
0x140035a17  lea     rcx, [rsp+78h+var_48]; this
0x140035a1c  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x140035a21  lea     rcx, [rsp+78h+var_48]; this
0x140035a26  call    ?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ; SURFACCESS::Dispatch(void)
0x140035a2b  mov     r9, rbx
0x140035a2e  mov     r8d, esi
0x140035a31  mov     edx, ebp
0x140035a33  mov     rcx, rdi
0x140035a36  mov     rax, [rax+0F0h]
0x140035a3d  call    _guard_dispatch_icall
0x140035a42  mov     rax, [rsp+78h+var_40]
0x140035a47  mov     rcx, [rax+8]
0x140035a4b  test    rcx, rcx
0x140035a4e  jz      short loc_140035A64
0x140035a50  add     rcx, 460h; struct _POINTER_INFO *
0x140035a57  xor     r9d, r9d; unsigned int
0x140035a5a  mov     r8d, esi; int
0x140035a5d  mov     edx, ebp; int
0x140035a5f  call    ?MovePointerInternal@@YAXPEAU_POINTER_INFO@@JJK@Z; MovePointerInternal(_POINTER_INFO *,long,long,ulong)
0x140035a64  lea     rcx, [rsp+78h+var_48]; this
0x140035a69  call    ??1SURFACCESS@@QEAA@XZ; SURFACCESS::~SURFACCESS(void)
0x140035a6e  lea     rcx, [rsp+78h+var_48]; this
0x140035a73  call    ??1SURFSWITCHLOCK@@QEAA@XZ; SURFSWITCHLOCK::~SURFSWITCHLOCK(void)
0x140035a78  add     rsp, 58h
0x140035a7c  pop     rdi
0x140035a7d  pop     rsi
0x140035a7e  pop     rbp
0x140035a7f  pop     rbx
0x140035a80  retn
```
