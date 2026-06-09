# ACProbeArrayElementsForRead(void *,ulong,ulong)

- ea: `0x140007684`
- end: `0x140007704`
- name: `?ACProbeArrayElementsForRead@@YAXPEAXKK@Z`
- size: `128`
- prototype: `void __fastcall(void *, unsigned int, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011ac`
- `0x140004d64`
- `0x14000533c`
- `0x1400058fc`
- `0x14000e488`
- `0x14002186c`
- `0x140022b28`
- `0x1400242b4`

## callees

- `0x140007684`
- `0x14000b570`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400076a8`
- `ntoskrnl!ProbeForRead` at `0x1400076a8`
- `ntoskrnl!ExRaiseStatus` at `0x1400076f7`
- `ntoskrnl!ExRaiseStatus` at `0x1400076f7`

## pseudocode

```c
void __fastcall ACProbeArrayElementsForRead(void *a1, unsigned int a2, __int64 a3)
{
  unsigned __int64 v3; // r9

  v3 = (unsigned int)a3 * (unsigned __int64)a2;
  if ( v3 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Ddd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 230, a3, 3221225621LL, a2, a3);
    }
    ExRaiseStatus(-1073741675);
  }
  ProbeForRead(a1, (unsigned int)v3, 1u);
}

```

## disassembly

```asm
0x140007684  sub     rsp, 38h
0x140007688  mov     eax, r8d
0x14000768b  mov     r9d, edx
0x14000768e  imul    r9, rax
0x140007692  mov     eax, 0FFFFFFFFh
0x140007697  mov     r10d, edx
0x14000769a  cmp     r9, rax
0x14000769d  ja      short loc_1400076BA
0x14000769f  mov     edx, r9d; Length
0x1400076a2  mov     r8d, 1; Alignment
0x1400076a8  call    cs:__imp_ProbeForRead
0x1400076af  nop     dword ptr [rax+rax+00h]
0x1400076b4  add     rsp, 38h
0x1400076b8  retn
0x1400076ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076c1  lea     rax, WPP_GLOBAL_Control
0x1400076c8  cmp     rcx, rax
0x1400076cb  jz      short loc_1400076F2
0x1400076cd  mov     eax, [rcx+6Ch]
0x1400076d0  test    al, 1
0x1400076d2  jz      short loc_1400076F2
0x1400076d4  mov     rcx, [rcx+58h]
0x1400076d8  mov     edx, 0E6h
0x1400076dd  mov     [rsp+38h+var_10], r8d
0x1400076e2  mov     r9d, 0C0000095h
0x1400076e8  mov     [rsp+38h+var_18], r10d
0x1400076ed  call    WPP_SF_Ddd
0x1400076f2  mov     ecx, 0C0000095h; Status
0x1400076f7  call    cs:__imp_ExRaiseStatus
```
