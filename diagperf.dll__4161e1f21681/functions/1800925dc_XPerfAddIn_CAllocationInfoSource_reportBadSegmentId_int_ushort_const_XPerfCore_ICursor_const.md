# XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(int,ushort const *,XPerfCore::ICursor const *)

- ea: `0x1800925dc`
- end: `0x180092671`
- name: `?reportBadSegmentId@CAllocationInfoSource@XPerfAddIn@@QEAAXHPEBGPEBUICursor@XPerfCore@@@Z`
- size: `149`
- prototype: `void __fastcall(XPerfAddIn::CAllocationInfoSource *__hidden this, int, const unsigned __int16 *, const struct XPerfCore::ICursor *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004b898`
- `0x18004c978`

## callees

- `0x180057df8`
- `0x1800925dc`
- `0x1800d6010`

## import_xrefs

- `msvcrt!fwprintf` at `0x18009265b`
- `msvcrt!fwprintf` at `0x18009265b`

## string_xrefs

- `0x180092654`: `DX::is_alloc: ERROR bad segment identifier %d during %ws at time %lld (should be between 1 and %d)\n`

## pseudocode

```c
void __fastcall XPerfAddIn::CAllocationInfoSource::reportBadSegmentId(
        XPerfAddIn::CAllocationInfoSource *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const struct XPerfCore::ICursor *a4)
{
  __int64 v6; // rbx
  FILE *v7; // rax
  XPerfAddIn::CAllocationInfoSource *v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = this;
  if ( a4 )
    v6 = *(_QWORD *)(*(__int64 (__fastcall **)(const struct XPerfCore::ICursor *, XPerfAddIn::CAllocationInfoSource **))(*(_QWORD *)a4 + 72LL))(
                      a4,
                      &v8)
       / 1000LL;
  else
    v6 = -1;
  v7 = _acrt_iob_func(2u);
  fwprintf(
    v7,
    L"DX::is_alloc: ERROR bad segment identifier %d during %ws at time %lld (should be between 1 and %d)\n",
    a2,
    a3,
    v6,
    32);
}

```

## disassembly

```asm
0x1800925dc  mov     r11, rsp
0x1800925df  mov     [r11+10h], rbx
0x1800925e3  mov     [r11+18h], rsi
0x1800925e7  mov     [r11+8], rcx
0x1800925eb  push    rdi
0x1800925ec  sub     rsp, 30h
0x1800925f0  mov     rdi, r8
0x1800925f3  mov     esi, edx
0x1800925f5  test    r9, r9
0x1800925f8  jz      short loc_180092630
0x1800925fa  mov     rax, [r9]
0x1800925fd  lea     rdx, [r11+8]
0x180092601  mov     rcx, r9
0x180092604  mov     rax, [rax+48h]
0x180092608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009260d  mov     rcx, [rax]
0x180092610  mov     rax, 20C49BA5E353F7CFh
0x18009261a  imul    rcx
0x18009261d  mov     rbx, rdx
0x180092620  sar     rbx, 7
0x180092624  mov     rax, rbx
0x180092627  shr     rax, 3Fh
0x18009262b  add     rbx, rax
0x18009262e  jmp     short loc_180092634
0x180092630  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180092634  mov     ecx, 2; Ix
0x180092639  call    __acrt_iob_func
0x18009263e  mov     rcx, rax; Stream
0x180092641  mov     [rsp+38h+var_10], 20h ; ' '
0x180092649  mov     r9, rdi
0x18009264c  mov     [rsp+38h+var_18], rbx
0x180092651  mov     r8d, esi
0x180092654  lea     rdx, aDxIsAllocError; "DX::is_alloc: ERROR bad segment identif"...
0x18009265b  call    cs:__imp_fwprintf
0x180092661  mov     rbx, [rsp+38h+arg_8]
0x180092666  mov     rsi, [rsp+38h+arg_10]
0x18009266b  add     rsp, 30h
0x18009266f  pop     rdi
0x180092670  retn
```
