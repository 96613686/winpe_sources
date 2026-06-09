# AddSchedulePage(_PROPSHEETHEADERW_V2 &,ITask *)

- ea: `0x180012f9c`
- end: `0x180012fe2`
- name: `?AddSchedulePage@@YAJAEAU_PROPSHEETHEADERW_V2@@PEAUITask@@@Z`
- size: `70`
- prototype: `int(struct _PROPSHEETHEADERW_V2 *, struct ITask *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000ff30`

## callees

- `0x180012f9c`
- `0x180012fe8`

## pseudocode

```c
__int64 __fastcall AddSchedulePage(struct _PROPSHEETHEADERW_V2 *a1, struct ITask *a2)
{
  __int64 result; // rax
  struct _PSP *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = GetSchedulePage(a2, 0, 1, &v4);
  if ( (int)result >= 0 )
    *((_QWORD *)&a1->ppsp->dwSize + a1->nPages++) = v4;
  return result;
}

```

## disassembly

```asm
0x180012f9c  push    rbx
0x180012f9e  sub     rsp, 20h
0x180012fa2  mov     rax, rdx
0x180012fa5  mov     [rsp+28h+arg_10], 0
0x180012fae  xor     edx, edx; Src
0x180012fb0  lea     r9, [rsp+28h+arg_10]; struct _PSP **
0x180012fb5  mov     rbx, rcx
0x180012fb8  mov     rcx, rax; struct ITask *
0x180012fbb  lea     r8d, [rdx+1]; int
0x180012fbf  call    ?GetSchedulePage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z; GetSchedulePage(ITask *,ushort *,int,_PSP * *)
0x180012fc4  test    eax, eax
0x180012fc6  js      short loc_180012FDC
0x180012fc8  mov     r8d, [rbx+28h]
0x180012fcc  mov     rdx, [rbx+38h]
0x180012fd0  mov     rcx, [rsp+28h+arg_10]
0x180012fd5  mov     [rdx+r8*8], rcx
0x180012fd9  inc     dword ptr [rbx+28h]
0x180012fdc  add     rsp, 20h
0x180012fe0  pop     rbx
0x180012fe1  retn
```
