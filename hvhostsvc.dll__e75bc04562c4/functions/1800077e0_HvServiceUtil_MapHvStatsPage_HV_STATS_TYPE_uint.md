# HvServiceUtil::MapHvStatsPage(_HV_STATS_TYPE,uint)

- ea: `0x1800077e0`
- end: `0x180007865`
- name: `?MapHvStatsPage@HvServiceUtil@@QEBAPEAU_HV_STATS_PAGE@@W4_HV_STATS_TYPE@@I@Z`
- size: `133`
- prototype: `__int64 __fastcall(HANDLE *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800075ec`

## callees

- `0x180007594`
- `0x1800077e0`
- `0x180007ac0`

## string_xrefs

- `0x18000783d`: `onecore\hv\common\inc\HvServiceUtil.h`

## pseudocode

```c
__int64 __fastcall HvServiceUtil::MapHvStatsPage(HANDLE *a1, int a2, int a3)
{
  char *v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+30h] [rbp-28h]
  int v6; // [rsp+38h] [rbp-20h]
  _QWORD v7[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v9; // [rsp+78h] [rbp+20h] BYREF
  int v10; // [rsp+7Ch] [rbp+24h]

  if ( (unsigned int)(a2 - 1) > 9 )
  {
    v6 = 10;
    v5 = 1;
    LODWORD(v4) = a2;
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\hv\\common\\inc\\HvServiceUtil.h",
      (const char *)0x57,
      (unsigned int)"Invalid stats type %d. (expected between %d and %d)",
      v4,
      v5,
      v6);
  }
  v9 = a2;
  v10 = a3;
  v7[0] = 0;
  HvServiceUtil::Ioctl(a1, 0x223FFCu, &v9, 8u, v7, 8u);
  return v7[0];
}

```

## disassembly

```asm
0x1800077e0  mov     r11, rsp
0x1800077e3  sub     rsp, 58h
0x1800077e7  lea     eax, [rdx-1]
0x1800077ea  cmp     eax, 9
0x1800077ed  ja      short loc_180007829
0x1800077ef  mov     [rsp+58h+arg_18], edx
0x1800077f3  lea     rax, [r11-18h]
0x1800077f7  mov     r9d, 8; unsigned int
0x1800077fd  mov     [r11+24h], r8d
0x180007801  mov     [r11-30h], r9d
0x180007805  lea     r8, [r11+20h]; void *
0x180007809  mov     edx, 223FFCh; unsigned int
0x18000780e  mov     [r11-38h], rax
0x180007812  mov     qword ptr [r11-18h], 0
0x18000781a  call    ?Ioctl@HvServiceUtil@@AEBAXKPEBXKPEAXK@Z; HvServiceUtil::Ioctl(ulong,void const *,ulong,void *,ulong)
0x18000781f  mov     rax, [rsp+58h+var_18]
0x180007824  add     rsp, 58h
0x180007828  retn
0x180007829  mov     rcx, [rsp+58h]; this
0x18000782e  lea     rax, aInvalidStatsTy; "Invalid stats type %d. (expected betwee"...
0x180007835  mov     [rsp+58h+var_20], 0Ah
0x18000783d  lea     r8, aOnecoreHvCommo; "onecore\\hv\\common\\inc\\HvServiceUtil"...
0x180007844  mov     r9d, 57h ; 'W'; char *
0x18000784a  mov     [rsp+58h+var_28], 1
0x180007852  mov     dword ptr [rsp+58h+var_30], edx; char *
0x180007856  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18000785b  lea     edx, [r9-8]; void *
0x18000785f  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
