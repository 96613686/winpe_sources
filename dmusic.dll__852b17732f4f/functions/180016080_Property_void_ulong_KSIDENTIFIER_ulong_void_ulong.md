# Property(void *,ulong,KSIDENTIFIER *,ulong,void *,ulong *)

- ea: `0x180016080`
- end: `0x1800160cd`
- name: `?Property@@YAHPEAXKPEAUKSIDENTIFIER@@K0PEAK@Z`
- size: `77`
- prototype: `__int64 __fastcall(void *, unsigned int, struct KSIDENTIFIER *, unsigned int, void *, unsigned int *)`
- caller_count: `10`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180015ec0`
- `0x180015f2c`
- `0x18001e528`
- `0x18001ef80`
- `0x18001f170`
- `0x18001f238`
- `0x18001f310`
- `0x18001f51c`
- `0x180020b40`
- `0x180020be0`

## callees

- `0x1800212e4`

## pseudocode

```c
_BOOL8 __fastcall Property(void *a1, unsigned int a2, struct KSIDENTIFIER *a3, DWORD a4, void *a5, unsigned int *a6)
{
  DWORD *v6; // r10
  int v8; // [rsp+40h] [rbp-18h] BYREF

  v6 = (DWORD *)&v8;
  v8 = 0;
  if ( a6 )
    v6 = a6;
  return (int)SyncIoctl(a1, 0x2F0003u, a3, a2, a5, a4, v6) >= 0;
}

```

## disassembly

```asm
0x180016080  mov     r11, rsp
0x180016083  sub     rsp, 58h
0x180016087  mov     rax, [rsp+58h+arg_28]
0x18001608f  lea     r10, [r11-18h]
0x180016093  test    rax, rax
0x180016096  mov     [rsp+58h+var_18], 0
0x18001609e  cmovnz  r10, rax
0x1800160a2  mov     rax, [rsp+58h+arg_20]
0x1800160aa  mov     [r11-28h], r10
0x1800160ae  mov     [r11-30h], r9d
0x1800160b2  mov     r9d, edx; unsigned int
0x1800160b5  mov     edx, 2F0003h; unsigned int
0x1800160ba  mov     [r11-38h], rax
0x1800160be  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x1800160c3  not     eax
0x1800160c5  shr     eax, 1Fh
0x1800160c8  add     rsp, 58h
0x1800160cc  retn
```
