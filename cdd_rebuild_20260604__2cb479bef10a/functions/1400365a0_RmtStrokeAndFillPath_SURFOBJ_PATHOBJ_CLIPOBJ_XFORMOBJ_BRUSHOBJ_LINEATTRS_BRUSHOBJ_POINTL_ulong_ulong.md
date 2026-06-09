# RmtStrokeAndFillPath(_SURFOBJ *,_PATHOBJ *,_CLIPOBJ *,_XFORMOBJ *,_BRUSHOBJ *,_LINEATTRS *,_BRUSHOBJ *,_POINTL *,ulong,ulong)

- ea: `0x1400365a0`
- end: `0x140036669`
- name: `?RmtStrokeAndFillPath@@YAHPEAU_SURFOBJ@@PEAU_PATHOBJ@@PEAU_CLIPOBJ@@PEAU_XFORMOBJ@@PEAU_BRUSHOBJ@@PEAU_LINEATTRS@@4PEAU_POINTL@@KK@Z`
- size: `201`
- prototype: `__int64 __usercall@<rax>(struct _SURFOBJ *@<rcx>, struct _PATHOBJ *@<rdx>, struct _CLIPOBJ *@<r8>, struct _XFORMOBJ *@<r9>, struct _BRUSHOBJ *, struct _LINEATTRS *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140024f20`
- `0x140025030`
- `0x14002733c`
- `0x14002793c`
- `0x140027c48`
- `0x1400372d0`

## pseudocode

```c
__int64 __fastcall RmtStrokeAndFillPath(
        struct _SURFOBJ *a1,
        struct _PATHOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XFORMOBJ *a4,
        struct _BRUSHOBJ *a5,
        struct _LINEATTRS *a6,
        struct _BRUSHOBJ *a7,
        struct _POINTL *a8,
        unsigned int a9,
        unsigned int a10)
{
  __int64 v14; // rdx
  struct _DDI_DISPATCH_TABLE *v15; // rax
  _BYTE v17[72]; // [rsp+60h] [rbp-48h] BYREF

  SURFSWITCHLOCK::SURFSWITCHLOCK((SURFSWITCHLOCK *)v17, a1, 0);
  SURFACCESS::SURFACCESS((SURFACCESS *)v17, a1);
  v15 = SURFACCESS::Dispatch((SURFACCESS *)v17, v14);
  LODWORD(a4) = (*((__int64 (__fastcall **)(struct _SURFOBJ *, struct _PATHOBJ *, struct _CLIPOBJ *, struct _XFORMOBJ *, struct _BRUSHOBJ *, struct _LINEATTRS *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int, unsigned int))v15
                 + 16))(
                  a1,
                  a2,
                  a3,
                  a4,
                  a5,
                  a6,
                  a7,
                  a8,
                  a9,
                  a10);
  SURFACCESS::~SURFACCESS((SURFACCESS *)v17);
  SURFSWITCHLOCK::~SURFSWITCHLOCK((SURFSWITCHLOCK *)v17);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x1400365a0  push    rbx
0x1400365a2  push    rbp
0x1400365a3  push    rsi
0x1400365a4  push    rdi
0x1400365a5  sub     rsp, 88h
0x1400365ac  mov     rsi, rdx
0x1400365af  mov     rdi, r8
0x1400365b2  mov     rdx, rcx; struct _SURFOBJ *
0x1400365b5  mov     rbp, rcx
0x1400365b8  lea     rcx, [rsp+0A8h+var_48]; this
0x1400365bd  xor     r8d, r8d; struct _SURFOBJ *
0x1400365c0  mov     rbx, r9
0x1400365c3  call    ??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z; SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)
0x1400365c8  mov     rdx, rbp; struct _SURFOBJ *
0x1400365cb  lea     rcx, [rsp+0A8h+var_48]; this
0x1400365d0  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x1400365d5  lea     rcx, [rsp+0A8h+var_48]; this
0x1400365da  call    ?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ; SURFACCESS::Dispatch(void)
0x1400365df  mov     ecx, [rsp+0A8h+arg_40]
0x1400365e6  mov     r9, rbx
0x1400365e9  mov     r8, rdi
0x1400365ec  mov     rdx, rsi
0x1400365ef  mov     r10, [rax+80h]
0x1400365f6  mov     eax, [rsp+0A8h+arg_48]
0x1400365fd  mov     [rsp+0A8h+var_60], eax
0x140036601  mov     rax, r10
0x140036604  mov     [rsp+0A8h+var_68], ecx
0x140036608  mov     rcx, [rsp+0A8h+arg_38]
0x140036610  mov     [rsp+0A8h+var_70], rcx
0x140036615  mov     rcx, [rsp+0A8h+arg_30]
0x14003661d  mov     [rsp+0A8h+var_78], rcx
0x140036622  mov     rcx, [rsp+0A8h+arg_28]
0x14003662a  mov     [rsp+0A8h+var_80], rcx
0x14003662f  mov     rcx, [rsp+0A8h+arg_20]
0x140036637  mov     [rsp+0A8h+var_88], rcx
0x14003663c  mov     rcx, rbp
0x14003663f  call    _guard_dispatch_icall
0x140036644  lea     rcx, [rsp+0A8h+var_48]; this
0x140036649  mov     ebx, eax
0x14003664b  call    ??1SURFACCESS@@QEAA@XZ; SURFACCESS::~SURFACCESS(void)
0x140036650  lea     rcx, [rsp+0A8h+var_48]; this
0x140036655  call    ??1SURFSWITCHLOCK@@QEAA@XZ; SURFSWITCHLOCK::~SURFSWITCHLOCK(void)
0x14003665a  mov     eax, ebx
0x14003665c  add     rsp, 88h
0x140036663  pop     rdi
0x140036664  pop     rsi
0x140036665  pop     rbp
0x140036666  pop     rbx
0x140036667  retn
```
