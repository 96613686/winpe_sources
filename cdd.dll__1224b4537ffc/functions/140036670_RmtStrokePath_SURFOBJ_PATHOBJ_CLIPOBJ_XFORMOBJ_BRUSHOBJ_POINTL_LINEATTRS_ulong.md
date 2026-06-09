# RmtStrokePath(_SURFOBJ *,_PATHOBJ *,_CLIPOBJ *,_XFORMOBJ *,_BRUSHOBJ *,_POINTL *,_LINEATTRS *,ulong)

- ea: `0x140036670`
- end: `0x14003672a`
- name: `?RmtStrokePath@@YAHPEAU_SURFOBJ@@PEAU_PATHOBJ@@PEAU_CLIPOBJ@@PEAU_XFORMOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAU_LINEATTRS@@K@Z`
- size: `186`
- prototype: `__int64 __usercall@<rax>(struct _SURFOBJ *@<rcx>, struct _PATHOBJ *@<rdx>, struct _CLIPOBJ *@<r8>, struct _XFORMOBJ *@<r9>, struct _BRUSHOBJ *, struct _POINTL *, struct _LINEATTRS *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140024f20`
- `0x140025030`
- `0x14002733c`
- `0x14002793c`
- `0x140027c48`
- `0x140036670`
- `0x1400372d0`

## pseudocode

```c
__int64 __fastcall RmtStrokePath(
        struct _SURFOBJ *a1,
        struct _PATHOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XFORMOBJ *a4,
        struct _BRUSHOBJ *a5,
        struct _POINTL *a6,
        struct _LINEATTRS *a7,
        unsigned int a8)
{
  __int64 v12; // rdx
  __int64 v13; // rdx
  struct _DDI_DISPATCH_TABLE *v14; // rax
  unsigned int v15; // ebx
  _BYTE v17[72]; // [rsp+50h] [rbp-48h] BYREF

  SURFSWITCHLOCK::SURFSWITCHLOCK((SURFSWITCHLOCK *)v17, a1, 0);
  SURFACCESS::SURFACCESS((SURFACCESS *)v17, a1);
  if ( *((_QWORD *)SURFACCESS::Dispatch((SURFACCESS *)v17, v12) + 14) )
  {
    v14 = SURFACCESS::Dispatch((SURFACCESS *)v17, v13);
    v15 = (*((__int64 (__fastcall **)(struct _SURFOBJ *, struct _PATHOBJ *, struct _CLIPOBJ *, struct _XFORMOBJ *, struct _BRUSHOBJ *, struct _POINTL *, struct _LINEATTRS *, unsigned int))v14
           + 14))(
            a1,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8);
  }
  else
  {
    v15 = 0;
  }
  SURFACCESS::~SURFACCESS((SURFACCESS *)v17);
  SURFSWITCHLOCK::~SURFSWITCHLOCK((SURFSWITCHLOCK *)v17);
  return v15;
}

```

## disassembly

```asm
0x140036670  push    rbx
0x140036672  push    rbp
0x140036673  push    rsi
0x140036674  push    rdi
0x140036675  sub     rsp, 78h
0x140036679  mov     rbp, rdx
0x14003667c  mov     rsi, r8
0x14003667f  mov     rdx, rcx; struct _SURFOBJ *
0x140036682  mov     rbx, rcx
0x140036685  lea     rcx, [rsp+98h+var_48]; this
0x14003668a  xor     r8d, r8d; struct _SURFOBJ *
0x14003668d  mov     rdi, r9
0x140036690  call    ??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z; SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)
0x140036695  mov     rdx, rbx; struct _SURFOBJ *
0x140036698  lea     rcx, [rsp+98h+var_48]; this
0x14003669d  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x1400366a2  lea     rcx, [rsp+98h+var_48]; this
0x1400366a7  call    ?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ; SURFACCESS::Dispatch(void)
0x1400366ac  cmp     qword ptr [rax+70h], 0
0x1400366b1  jz      short loc_140036708
0x1400366b3  lea     rcx, [rsp+98h+var_48]; this
0x1400366b8  call    ?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ; SURFACCESS::Dispatch(void)
0x1400366bd  mov     ecx, [rsp+98h+arg_38]
0x1400366c4  mov     r9, rdi
0x1400366c7  mov     [rsp+98h+var_60], ecx
0x1400366cb  mov     r8, rsi
0x1400366ce  mov     rcx, [rsp+98h+arg_30]
0x1400366d6  mov     rdx, rbp
0x1400366d9  mov     rax, [rax+70h]
0x1400366dd  mov     [rsp+98h+var_68], rcx
0x1400366e2  mov     rcx, [rsp+98h+arg_28]
0x1400366ea  mov     [rsp+98h+var_70], rcx
0x1400366ef  mov     rcx, [rsp+98h+arg_20]
0x1400366f7  mov     [rsp+98h+var_78], rcx
0x1400366fc  mov     rcx, rbx
0x1400366ff  call    _guard_dispatch_icall
0x140036704  mov     ebx, eax
0x140036706  jmp     short loc_14003670A
0x140036708  xor     ebx, ebx
0x14003670a  lea     rcx, [rsp+98h+var_48]; this
0x14003670f  call    ??1SURFACCESS@@QEAA@XZ; SURFACCESS::~SURFACCESS(void)
0x140036714  lea     rcx, [rsp+98h+var_48]; this
0x140036719  call    ??1SURFSWITCHLOCK@@QEAA@XZ; SURFSWITCHLOCK::~SURFSWITCHLOCK(void)
0x14003671e  mov     eax, ebx
0x140036720  add     rsp, 78h
0x140036724  pop     rdi
0x140036725  pop     rsi
0x140036726  pop     rbp
0x140036727  pop     rbx
0x140036728  retn
```
