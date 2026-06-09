# DeviceSeek(_MCIGRAPHIC *,long,ulong,unsigned __int64)

- ea: `0x180003074`
- end: `0x180003104`
- name: `?DeviceSeek@@YAKPEAU_MCIGRAPHIC@@JK_K@Z`
- size: `144`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, int, unsigned int, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000485c`
- `0x180006088`

## callees

- `0x180003408`
- `0x18000415c`
- `0x180004f9c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall DeviceSeek(struct _MCIGRAPHIC *a1, unsigned int a2, int a3)
{
  __int64 v4; // rcx
  int v5; // edx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF
  int v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = a3;
  v7 = a2;
  *((_DWORD *)a1 + 72) = 528;
  GraphicDelayedNotify((__int64)a1, 4u);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 72LL))(*((_QWORD *)a1 + 19));
  PutSelection(a1, &v7, &v7);
  v4 = *((_QWORD *)a1 + 19);
  v8 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
  (*(void (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)a1 + 19) + 80LL))(
    *((_QWORD *)a1 + 19),
    0xFFFFFFFFLL,
    &v8);
  DeviceStop(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x180003074  mov     [rsp+arg_10], r8d
0x180003079  mov     [rsp+arg_8], edx
0x18000307d  push    rbx
0x18000307e  sub     rsp, 20h
0x180003082  mov     edx, 4
0x180003087  mov     dword ptr [rcx+120h], 210h
0x180003091  mov     rbx, rcx
0x180003094  call    GraphicDelayedNotify
0x180003099  mov     rcx, [rbx+98h]
0x1800030a0  mov     rax, [rcx]
0x1800030a3  mov     rax, [rax+48h]
0x1800030a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ac  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x1800030b1  mov     rcx, rbx; struct _MCIGRAPHIC *
0x1800030b4  lea     rdx, [rsp+28h+arg_8]; unsigned int *
0x1800030b9  call    ?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z; PutSelection(_MCIGRAPHIC *,ulong *,ulong *)
0x1800030be  mov     rcx, [rbx+98h]
0x1800030c5  mov     [rsp+28h+arg_10], 0
0x1800030cd  mov     rax, [rcx]
0x1800030d0  mov     rax, [rax+40h]
0x1800030d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d9  mov     rcx, [rbx+98h]
0x1800030e0  lea     r8, [rsp+28h+arg_10]
0x1800030e5  or      edx, 0FFFFFFFFh
0x1800030e8  mov     rax, [rcx]
0x1800030eb  mov     rax, [rax+50h]
0x1800030ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f4  mov     rcx, rbx; struct _MCIGRAPHIC *
0x1800030f7  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x1800030fc  xor     eax, eax
0x1800030fe  add     rsp, 20h
0x180003102  pop     rbx
0x180003103  retn
```
