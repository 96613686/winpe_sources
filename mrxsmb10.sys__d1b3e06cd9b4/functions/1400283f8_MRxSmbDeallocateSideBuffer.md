# MRxSmbDeallocateSideBuffer

- ea: `0x1400283f8`
- end: `0x140028517`
- name: `MRxSmbDeallocateSideBuffer`
- size: `287`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002a430`
- `0x1400367d0`
- `0x1400508a0`
- `0x140052fa0`

## callees

- `0x14000edac`
- `0x1400283f8`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400284a2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400284a2`
- `ntoskrnl!ExAcquireFastMutex` at `0x140028467`
- `ntoskrnl!ExAcquireFastMutex` at `0x140028467`
- `ntoskrnl!DbgPrint` at `0x140028454`
- `ntoskrnl!DbgPrint` at `0x140028454`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400284f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400284f2`

## string_xrefs

- `0x14002843a`: `D--------- side buffer %p %08lx %p %p %p <%wZ> %s\n`

## pseudocode

```c
void __fastcall MRxSmbDeallocateSideBuffer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  __int64 v6; // rbp
  __int64 v7; // rsi
  __int64 v8; // r8
  _QWORD *v9; // rdx

  v4 = *(_QWORD *)(a2 + 16);
  if ( v4 )
  {
    v5 = (_QWORD *)(v4 - 48);
    v6 = *(_QWORD *)(a1 + 56);
    v7 = *(_QWORD *)(a1 + 64);
    if ( MRxSmbLoudSideBuffers )
      DbgPrint(
        "D--------- side buffer %p %08lx %p %p %p <%wZ> %s\n",
        v4,
        (unsigned int)MRxSmbSideBuffersCount,
        a2,
        v7,
        *(_QWORD *)(v7 + 32),
        v6 + 360,
        a3);
    ExAcquireFastMutex(&MRxSmbSerializationMutex);
    _InterlockedDecrement(&MRxSmbSideBuffersCount);
    v8 = v5[1];
    if ( *(_QWORD **)(v8 + 8) != v5 + 1 || (v9 = (_QWORD *)v5[2], (_QWORD *)*v9 != v5 + 1) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    ExReleaseFastMutex(&MRxSmbSerializationMutex);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        *(_QWORD *)(a2 + 16),
        v7,
        v6);
    ExFreePoolWithTag(v5, 0);
    *(_QWORD *)(a2 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1400283f8  mov     r11, rsp
0x1400283fb  push    rbx
0x1400283fc  push    rbp
0x1400283fd  push    rsi
0x1400283fe  push    rdi
0x1400283ff  sub     rsp, 48h
0x140028403  mov     rbx, rdx
0x140028406  mov     rdx, [rdx+10h]
0x14002840a  test    rdx, rdx
0x14002840d  jz      loc_140028506
0x140028413  cmp     cs:MRxSmbLoudSideBuffers, 0
0x14002841a  lea     rdi, [rdx-30h]
0x14002841e  mov     rbp, [rcx+38h]
0x140028422  mov     rsi, [rcx+40h]
0x140028426  jz      short loc_140028460
0x140028428  mov     [r11-30h], r8
0x14002842c  lea     rax, [rbp+168h]
0x140028433  mov     r8d, cs:MRxSmbSideBuffersCount
0x14002843a  lea     rcx, aDSideBufferP08; "D--------- side buffer %p %08lx %p %p %"...
0x140028441  mov     [r11-38h], rax
0x140028445  mov     r9, rbx
0x140028448  mov     rax, [rsi+20h]
0x14002844c  mov     [r11-40h], rax
0x140028450  mov     [r11-48h], rsi
0x140028454  call    cs:__imp_DbgPrint
0x14002845b  nop     dword ptr [rax+rax+00h]
0x140028460  lea     rcx, MRxSmbSerializationMutex; FastMutex
0x140028467  call    cs:__imp_ExAcquireFastMutex
0x14002846e  nop     dword ptr [rax+rax+00h]
0x140028473  lock dec cs:MRxSmbSideBuffersCount
0x14002847a  lea     rax, [rdi+8]
0x14002847e  mov     r8, [rax]
0x140028481  cmp     [r8+8], rax
0x140028485  jnz     loc_140028510
0x14002848b  mov     rdx, [rax+8]
0x14002848f  cmp     [rdx], rax
0x140028492  jnz     short loc_140028510
0x140028494  mov     [rdx], r8
0x140028497  lea     rcx, MRxSmbSerializationMutex; FastMutex
0x14002849e  mov     [r8+8], rdx
0x1400284a2  call    cs:__imp_ExReleaseFastMutex
0x1400284a9  nop     dword ptr [rax+rax+00h]
0x1400284ae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400284b5  lea     rax, WPP_GLOBAL_Control
0x1400284bc  cmp     rcx, rax
0x1400284bf  jz      short loc_1400284ED
0x1400284c1  test    dword ptr [rcx+2Ch], 200h
0x1400284c8  jz      short loc_1400284ED
0x1400284ca  mov     r9, [rbx+10h]
0x1400284ce  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x1400284d5  mov     rcx, [rcx+18h]
0x1400284d9  mov     edx, 0Bh
0x1400284de  mov     [rsp+68h+var_40], rbp
0x1400284e3  mov     [rsp+68h+var_48], rsi
0x1400284e8  call    WPP_SF_qqq
0x1400284ed  xor     edx, edx; Tag
0x1400284ef  mov     rcx, rdi; P
0x1400284f2  call    cs:__imp_ExFreePoolWithTag
0x1400284f9  nop     dword ptr [rax+rax+00h]
0x1400284fe  mov     qword ptr [rbx+10h], 0
0x140028506  add     rsp, 48h
0x14002850a  pop     rdi
0x14002850b  pop     rsi
0x14002850c  pop     rbp
0x14002850d  pop     rbx
0x14002850e  retn
0x140028510  mov     ecx, 3
0x140028515  int     29h; Win8: RtlFailFast(ecx)
```
