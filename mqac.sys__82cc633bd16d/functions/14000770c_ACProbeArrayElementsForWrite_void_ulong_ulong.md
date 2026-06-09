# ACProbeArrayElementsForWrite(void *,ulong,ulong)

- ea: `0x14000770c`
- end: `0x140007787`
- name: `?ACProbeArrayElementsForWrite@@YAXPEAXKK@Z`
- size: `123`
- prototype: `void __fastcall(void *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006d50`
- `0x14000e834`
- `0x140021b5c`
- `0x140023b00`

## callees

- `0x14000770c`
- `0x14000b570`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140007728`
- `ntoskrnl!ProbeForWrite` at `0x140007728`
- `ntoskrnl!ExRaiseStatus` at `0x14000777a`
- `ntoskrnl!ExRaiseStatus` at `0x14000777a`

## pseudocode

```c
void __fastcall ACProbeArrayElementsForWrite(void *a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rax

  v3 = 2LL * (unsigned int)a3;
  if ( v3 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Ddd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 231, a3, 3221225621LL, 2, a3);
    }
    ExRaiseStatus(-1073741675);
  }
  ProbeForWrite(a1, (unsigned int)v3, 1u);
}

```

## disassembly

```asm
0x14000770c  sub     rsp, 38h
0x140007710  mov     eax, r8d
0x140007713  mov     edx, 0FFFFFFFFh
0x140007718  add     rax, rax
0x14000771b  cmp     rax, rdx
0x14000771e  ja      short loc_14000773A
0x140007720  mov     edx, eax; Length
0x140007722  mov     r8d, 1; Alignment
0x140007728  call    cs:__imp_ProbeForWrite
0x14000772f  nop     dword ptr [rax+rax+00h]
0x140007734  add     rsp, 38h
0x140007738  retn
0x14000773a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007741  lea     rax, WPP_GLOBAL_Control
0x140007748  cmp     rcx, rax
0x14000774b  jz      short loc_140007775
0x14000774d  mov     eax, [rcx+6Ch]
0x140007750  test    al, 1
0x140007752  jz      short loc_140007775
0x140007754  mov     rcx, [rcx+58h]
0x140007758  mov     edx, 0E7h
0x14000775d  mov     [rsp+38h+var_10], r8d
0x140007762  mov     r9d, 0C0000095h
0x140007768  mov     [rsp+38h+var_18], 2
0x140007770  call    WPP_SF_Ddd
0x140007775  mov     ecx, 0C0000095h; Status
0x14000777a  call    cs:__imp_ExRaiseStatus
```
