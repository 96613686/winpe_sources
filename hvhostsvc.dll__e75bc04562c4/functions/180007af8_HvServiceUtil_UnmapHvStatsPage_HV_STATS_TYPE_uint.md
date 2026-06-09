# HvServiceUtil::UnmapHvStatsPage(_HV_STATS_TYPE,uint)

- ea: `0x180007af8`
- end: `0x180007b74`
- name: `?UnmapHvStatsPage@HvServiceUtil@@QEBAXW4_HV_STATS_TYPE@@I@Z`
- size: `124`
- prototype: `void __fastcall(HANDLE *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007110`

## callees

- `0x180007594`
- `0x180007ac0`
- `0x180007af8`

## string_xrefs

- `0x180007b4c`: `onecore\hv\common\inc\HvServiceUtil.h`

## pseudocode

```c
void __fastcall HvServiceUtil::UnmapHvStatsPage(HANDLE *a1, int a2, int a3)
{
  const char *v3; // [rsp+28h] [rbp-20h]
  int v4; // [rsp+30h] [rbp-18h]
  int v5; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v7; // [rsp+68h] [rbp+20h] BYREF
  int v8; // [rsp+6Ch] [rbp+24h]

  if ( (unsigned int)(a2 - 1) > 9 )
  {
    v5 = 10;
    v4 = 1;
    LODWORD(v3) = a2;
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\hv\\common\\inc\\HvServiceUtil.h",
      (const char *)0x57,
      (unsigned int)"Invalid stats type %d. (expected between %d and %d)",
      v3,
      v4,
      v5);
  }
  v7 = a2;
  v8 = a3;
  HvServiceUtil::Ioctl(a1, 0x223FF8u, &v7, 8u, 0, 0);
}

```

## disassembly

```asm
0x180007af8  sub     rsp, 48h
0x180007afc  lea     eax, [rdx-1]
0x180007aff  cmp     eax, 9
0x180007b02  ja      short loc_180007B38
0x180007b04  mov     [rsp+48h+arg_18], edx
0x180007b08  mov     r9d, 8; unsigned int
0x180007b0e  mov     [rsp+48h+arg_1C], r8d
0x180007b13  mov     edx, 223FF8h; unsigned int
0x180007b18  lea     r8, [rsp+48h+arg_18]; void *
0x180007b1d  mov     dword ptr [rsp+48h+var_20], 0; DWORD
0x180007b25  mov     [rsp+48h+var_28], 0; void *
0x180007b2e  call    ?Ioctl@HvServiceUtil@@AEBAXKPEBXKPEAXK@Z; HvServiceUtil::Ioctl(ulong,void const *,ulong,void *,ulong)
0x180007b33  add     rsp, 48h
0x180007b37  retn
0x180007b38  mov     rcx, [rsp+48h]; this
0x180007b3d  lea     rax, aInvalidStatsTy; "Invalid stats type %d. (expected betwee"...
0x180007b44  mov     [rsp+48h+var_10], 0Ah
0x180007b4c  lea     r8, aOnecoreHvCommo; "onecore\\hv\\common\\inc\\HvServiceUtil"...
0x180007b53  mov     r9d, 57h ; 'W'; char *
0x180007b59  mov     [rsp+48h+var_18], 1
0x180007b61  mov     dword ptr [rsp+48h+var_20], edx; char *
0x180007b65  mov     [rsp+48h+var_28], rax; unsigned int
0x180007b6a  lea     edx, [r9+7]; void *
0x180007b6e  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
