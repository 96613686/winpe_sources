# PmWmiCounterIoComplete(_PERF_COUNTER_CONTEXT *,_IRP *,_LARGE_INTEGER *,ulong *)

- ea: `0x140009ed0`
- end: `0x14000a00e`
- name: `?PmWmiCounterIoComplete@@YAXPEAU_PERF_COUNTER_CONTEXT@@PEAU_IRP@@PEAT_LARGE_INTEGER@@PEAK@Z`
- size: `318`
- prototype: `void __fastcall(struct _PERF_COUNTER_CONTEXT *, struct _IRP *, union _LARGE_INTEGER *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009ca4`
- `0x140009ed0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140009ef3`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140009ef3`

## pseudocode

```c
void __fastcall PmWmiCounterIoComplete(
        union _LARGE_INTEGER *a1,
        struct _IRP *a2,
        union _LARGE_INTEGER *a3,
        unsigned int *a4)
{
  ULONG64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  UCHAR MajorFunction; // cl
  unsigned __int64 QpcTimeStamp; // [rsp+70h] [rbp+18h] BYREF

  QpcTimeStamp = 0;
  v8 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
  a3->QuadPart = v8 - a3->QuadPart;
  if ( a1 )
  {
    PmPerfCounterIdleUpdate(a1, (union _LARGE_INTEGER)v8, a4, 0, 1);
    LODWORD(v9) = HIDWORD(KeGetPcr()[1].LockArray);
    if ( (unsigned int)v9 < a1[7].HighPart )
    {
      v10 = 24 * v9;
      MajorFunction = a2->Tail.Overlay.CurrentStackLocation->MajorFunction;
      switch ( MajorFunction )
      {
        case 3u:
          a1[v10 + 16].QuadPart += a2->IoStatus.Information;
          ++a1[v10 + 22].LowPart;
          a1[v10 + 18].QuadPart += a3->QuadPart;
          break;
        case 4u:
          a1[v10 + 17].QuadPart += a2->IoStatus.Information;
          ++a1[v10 + 22].HighPart;
          a1[v10 + 19].QuadPart += a3->QuadPart;
          break;
        case 9u:
          ++a1[v10 + 23].LowPart;
          a1[v10 + 20].QuadPart += a3->QuadPart;
          break;
      }
      if ( (a2->Flags & 8) != 0 )
        ++a1[v10 + 23].HighPart;
    }
  }
}

```

## disassembly

```asm
0x140009ed0  push    rbx
0x140009ed2  push    rbp
0x140009ed3  push    rsi
0x140009ed4  push    rdi
0x140009ed5  sub     rsp, 38h
0x140009ed9  mov     rbx, rcx
0x140009edc  mov     [rsp+58h+QpcTimeStamp], 0
0x140009ee5  lea     rcx, [rsp+58h+QpcTimeStamp]; QpcTimeStamp
0x140009eea  mov     rbp, r9
0x140009eed  mov     rsi, r8
0x140009ef0  mov     rdi, rdx
0x140009ef3  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140009efa  nop     dword ptr [rax+rax+00h]
0x140009eff  mov     r10, rax
0x140009f02  sub     r10, [rsi]
0x140009f05  mov     [rsi], r10
0x140009f08  test    rbx, rbx
0x140009f0b  jz      loc_14000A004
0x140009f11  xor     r9d, r9d; unsigned __int8
0x140009f14  mov     [rsp+58h+var_38], 1; char
0x140009f19  mov     r8, rbp; unsigned int *
0x140009f1c  mov     rdx, rax; union _LARGE_INTEGER
0x140009f1f  mov     rcx, rbx; struct _PERF_COUNTER_CONTEXT *
0x140009f22  call    ?PmPerfCounterIdleUpdate@@YA_KPEAU_PERF_COUNTER_CONTEXT@@T_LARGE_INTEGER@@PEAKEE@Z; PmPerfCounterIdleUpdate(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER,ulong *,uchar,uchar)
0x140009f27  mov     edx, gs:1A4h
0x140009f2f  cmp     edx, [rbx+3Ch]
0x140009f32  jnb     loc_14000A004
0x140009f38  mov     rax, [rdi+0B8h]
0x140009f3f  lea     rdx, [rdx+rdx*2]
0x140009f43  shl     rdx, 6
0x140009f47  mov     cl, [rax]
0x140009f49  cmp     cl, 3
0x140009f4c  jnz     short loc_140009F87
0x140009f4e  mov     rcx, [rdx+rbx+80h]
0x140009f56  add     rcx, [rdi+38h]
0x140009f5a  mov     [rdx+rbx+80h], rcx
0x140009f62  mov     eax, [rdx+rbx+0B0h]
0x140009f69  inc     eax
0x140009f6b  mov     [rdx+rbx+0B0h], eax
0x140009f72  mov     rcx, [rdx+rbx+90h]
0x140009f7a  add     rcx, [rsi]
0x140009f7d  mov     [rdx+rbx+90h], rcx
0x140009f85  jmp     short loc_140009FED
0x140009f87  cmp     cl, 4
0x140009f8a  jnz     short loc_140009FC5
0x140009f8c  mov     rcx, [rdx+rbx+88h]
0x140009f94  add     rcx, [rdi+38h]
0x140009f98  mov     [rdx+rbx+88h], rcx
0x140009fa0  mov     eax, [rdx+rbx+0B4h]
0x140009fa7  inc     eax
0x140009fa9  mov     [rdx+rbx+0B4h], eax
0x140009fb0  mov     rcx, [rdx+rbx+98h]
0x140009fb8  add     rcx, [rsi]
0x140009fbb  mov     [rdx+rbx+98h], rcx
0x140009fc3  jmp     short loc_140009FED
0x140009fc5  cmp     cl, 9
0x140009fc8  jnz     short loc_140009FED
0x140009fca  mov     eax, [rdx+rbx+0B8h]
0x140009fd1  inc     eax
0x140009fd3  mov     [rdx+rbx+0B8h], eax
0x140009fda  mov     rcx, [rdx+rbx+0A0h]
0x140009fe2  add     rcx, [rsi]
0x140009fe5  mov     [rdx+rbx+0A0h], rcx
0x140009fed  mov     eax, [rdi+10h]
0x140009ff0  test    al, 8
0x140009ff2  jz      short loc_14000A004
0x140009ff4  mov     eax, [rdx+rbx+0BCh]
0x140009ffb  inc     eax
0x140009ffd  mov     [rdx+rbx+0BCh], eax
0x14000a004  add     rsp, 38h
0x14000a008  pop     rdi
0x14000a009  pop     rsi
0x14000a00a  pop     rbp
0x14000a00b  pop     rbx
0x14000a00c  retn
```
