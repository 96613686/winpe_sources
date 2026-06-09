# RmtFillPath(_SURFOBJ *,_PATHOBJ *,_CLIPOBJ *,_BRUSHOBJ *,_POINTL *,ulong,ulong)

- ea: `0x140035630`
- end: `0x1400356c6`
- name: `?RmtFillPath@@YAHPEAU_SURFOBJ@@PEAU_PATHOBJ@@PEAU_CLIPOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@KK@Z`
- size: `150`
- prototype: `__int64 __usercall@<rax>(struct _SURFOBJ *@<rcx>, struct _PATHOBJ *@<rdx>, struct _CLIPOBJ *@<r8>, struct _BRUSHOBJ *@<r9>, struct _POINTL *, unsigned int, unsigned int)`
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
__int64 __fastcall RmtFillPath(
        struct _SURFOBJ *a1,
        struct _PATHOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _BRUSHOBJ *a4,
        struct _POINTL *a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v11; // rdx
  struct _DDI_DISPATCH_TABLE *v12; // rax
  _BYTE v14[72]; // [rsp+40h] [rbp-48h] BYREF

  SURFSWITCHLOCK::SURFSWITCHLOCK((SURFSWITCHLOCK *)v14, a1, 0);
  SURFACCESS::SURFACCESS((SURFACCESS *)v14, a1);
  v12 = SURFACCESS::Dispatch((SURFACCESS *)v14, v11);
  LODWORD(a4) = (*((__int64 (__fastcall **)(struct _SURFOBJ *, struct _PATHOBJ *, struct _CLIPOBJ *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int, unsigned int))v12
                 + 15))(
                  a1,
                  a2,
                  a3,
                  a4,
                  a5,
                  a6,
                  a7);
  SURFACCESS::~SURFACCESS((SURFACCESS *)v14);
  SURFSWITCHLOCK::~SURFSWITCHLOCK((SURFSWITCHLOCK *)v14);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x140035630  push    rbx
0x140035632  push    rbp
0x140035633  push    rsi
0x140035634  push    rdi
0x140035635  sub     rsp, 68h
0x140035639  mov     rsi, rdx
0x14003563c  mov     rdi, r8
0x14003563f  mov     rdx, rcx; struct _SURFOBJ *
0x140035642  mov     rbp, rcx
0x140035645  lea     rcx, [rsp+88h+var_48]; this
0x14003564a  xor     r8d, r8d; struct _SURFOBJ *
0x14003564d  mov     rbx, r9
0x140035650  call    ??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z; SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)
0x140035655  mov     rdx, rbp; struct _SURFOBJ *
0x140035658  lea     rcx, [rsp+88h+var_48]; this
0x14003565d  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x140035662  lea     rcx, [rsp+88h+var_48]; this
0x140035667  call    ?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ; SURFACCESS::Dispatch(void)
0x14003566c  mov     edx, [rsp+88h+arg_30]
0x140035673  mov     r9, rbx
0x140035676  mov     ecx, [rsp+88h+arg_28]
0x14003567d  mov     r8, rdi
0x140035680  mov     [rsp+88h+var_58], edx
0x140035684  mov     rdx, rsi
0x140035687  mov     rax, [rax+78h]
0x14003568b  mov     [rsp+88h+var_60], ecx
0x14003568f  mov     rcx, [rsp+88h+arg_20]
0x140035697  mov     [rsp+88h+var_68], rcx
0x14003569c  mov     rcx, rbp
0x14003569f  call    _guard_dispatch_icall
0x1400356a4  lea     rcx, [rsp+88h+var_48]; this
0x1400356a9  mov     ebx, eax
0x1400356ab  call    ??1SURFACCESS@@QEAA@XZ; SURFACCESS::~SURFACCESS(void)
0x1400356b0  lea     rcx, [rsp+88h+var_48]; this
0x1400356b5  call    ??1SURFSWITCHLOCK@@QEAA@XZ; SURFSWITCHLOCK::~SURFSWITCHLOCK(void)
0x1400356ba  mov     eax, ebx
0x1400356bc  add     rsp, 68h
0x1400356c0  pop     rdi
0x1400356c1  pop     rsi
0x1400356c2  pop     rbp
0x1400356c3  pop     rbx
0x1400356c4  retn
```
