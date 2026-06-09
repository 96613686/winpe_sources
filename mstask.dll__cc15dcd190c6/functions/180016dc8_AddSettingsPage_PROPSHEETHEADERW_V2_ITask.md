# AddSettingsPage(_PROPSHEETHEADERW_V2 &,ITask *)

- ea: `0x180016dc8`
- end: `0x180016e0e`
- name: `?AddSettingsPage@@YAJAEAU_PROPSHEETHEADERW_V2@@PEAUITask@@@Z`
- size: `70`
- prototype: `int(struct _PROPSHEETHEADERW_V2 *, struct ITask *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000ff30`

## callees

- `0x180016dc8`
- `0x180016e14`

## pseudocode

```c
__int64 __fastcall AddSettingsPage(struct _PROPSHEETHEADERW_V2 *a1, struct ITask *a2)
{
  __int64 result; // rax
  struct _PSP *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = GetSettingsPage(a2, 0, 1, &v4);
  if ( (int)result >= 0 )
    *((_QWORD *)&a1->ppsp->dwSize + a1->nPages++) = v4;
  return result;
}

```

## disassembly

```asm
0x180016dc8  push    rbx
0x180016dca  sub     rsp, 20h
0x180016dce  mov     rax, rdx
0x180016dd1  mov     [rsp+28h+arg_10], 0
0x180016dda  xor     edx, edx; unsigned __int16 *
0x180016ddc  lea     r9, [rsp+28h+arg_10]; struct _PSP **
0x180016de1  mov     rbx, rcx
0x180016de4  mov     rcx, rax; struct ITask *
0x180016de7  lea     r8d, [rdx+1]; int
0x180016deb  call    ?GetSettingsPage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z; GetSettingsPage(ITask *,ushort *,int,_PSP * *)
0x180016df0  test    eax, eax
0x180016df2  js      short loc_180016E08
0x180016df4  mov     r8d, [rbx+28h]
0x180016df8  mov     rdx, [rbx+38h]
0x180016dfc  mov     rcx, [rsp+28h+arg_10]
0x180016e01  mov     [rdx+r8*8], rcx
0x180016e05  inc     dword ptr [rbx+28h]
0x180016e08  add     rsp, 20h
0x180016e0c  pop     rbx
0x180016e0d  retn
```
