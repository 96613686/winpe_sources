# AddGeneralPage(_PROPSHEETHEADERW_V2 &,ITask *)

- ea: `0x180010478`
- end: `0x1800104be`
- name: `?AddGeneralPage@@YAJAEAU_PROPSHEETHEADERW_V2@@PEAUITask@@@Z`
- size: `70`
- prototype: `int(struct _PROPSHEETHEADERW_V2 *, struct ITask *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000ff30`

## callees

- `0x180010478`
- `0x1800105a8`

## pseudocode

```c
__int64 __fastcall AddGeneralPage(struct _PROPSHEETHEADERW_V2 *a1, struct ITask *a2)
{
  __int64 result; // rax
  struct _PSP *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = GetGeneralPage(a2, 0, 1, &v4);
  if ( (int)result >= 0 )
    *((_QWORD *)&a1->ppsp->dwSize + a1->nPages++) = v4;
  return result;
}

```

## disassembly

```asm
0x180010478  push    rbx
0x18001047a  sub     rsp, 20h
0x18001047e  mov     rax, rdx
0x180010481  mov     [rsp+28h+arg_10], 0
0x18001048a  xor     edx, edx; unsigned __int16 *
0x18001048c  lea     r9, [rsp+28h+arg_10]; struct _PSP **
0x180010491  mov     rbx, rcx
0x180010494  mov     rcx, rax; struct ITask *
0x180010497  lea     r8d, [rdx+1]; int
0x18001049b  call    ?GetGeneralPage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z; GetGeneralPage(ITask *,ushort *,int,_PSP * *)
0x1800104a0  test    eax, eax
0x1800104a2  js      short loc_1800104B8
0x1800104a4  mov     r8d, [rbx+28h]
0x1800104a8  mov     rdx, [rbx+38h]
0x1800104ac  mov     rcx, [rsp+28h+arg_10]
0x1800104b1  mov     [rdx+r8*8], rcx
0x1800104b5  inc     dword ptr [rbx+28h]
0x1800104b8  add     rsp, 20h
0x1800104bc  pop     rbx
0x1800104bd  retn
```
