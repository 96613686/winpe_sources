# CDiskScanner::StartDiskScan(void *)

- ea: `0x18001f878`
- end: `0x18001f8d5`
- name: `?StartDiskScan@CDiskScanner@@QEAAXPEAX@Z`
- size: `93`
- prototype: `void __fastcall(CDiskScanner *this, void *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800165a0`
- `0x180016a74`

## callees

- `0x18001f878`
- `0x1800204b4`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x18001f8ce`

## pseudocode

```c
void __fastcall CDiskScanner::StartDiskScan(CDiskScanner *this, void *a2, __int64 a3)
{
  *((_QWORD *)this + 12) = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, *((unsigned int *)this + 4), *((_QWORD *)this + 31));
  }
  SubmitThreadpoolWork(*((PTP_WORK *)this + 31));
}

```

## disassembly

```asm
0x18001f878  push    rbx
0x18001f87a  sub     rsp, 30h
0x18001f87e  mov     rbx, rcx
0x18001f881  mov     [rcx+60h], rdx
0x18001f885  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f88c  lea     rax, WPP_GLOBAL_Control
0x18001f893  cmp     rcx, rax
0x18001f896  jz      short loc_18001F8C2
0x18001f898  test    byte ptr [rcx+1Ch], 1
0x18001f89c  jz      short loc_18001F8C2
0x18001f89e  cmp     byte ptr [rcx+19h], 4
0x18001f8a2  jb      short loc_18001F8C2
0x18001f8a4  mov     rax, [rbx+0F8h]
0x18001f8ab  mov     edx, 0Eh
0x18001f8b0  mov     r9d, [rbx+10h]
0x18001f8b4  mov     rcx, [rcx+10h]
0x18001f8b8  mov     [rsp+38h+var_18], rax
0x18001f8bd  call    WPP_SF_Dq
0x18001f8c2  mov     rcx, [rbx+0F8h]
0x18001f8c9  add     rsp, 30h
0x18001f8cd  pop     rbx
0x18001f8ce  jmp     cs:__imp_SubmitThreadpoolWork
```
