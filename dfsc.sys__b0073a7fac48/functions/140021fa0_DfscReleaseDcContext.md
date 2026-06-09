# DfscReleaseDcContext

- ea: `0x140021fa0`
- end: `0x14002210f`
- name: `DfscReleaseDcContext`
- size: `367`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140013100`
- `0x140016c84`
- `0x1400219c0`
- `0x140021c60`
- `0x140021e28`
- `0x140022b60`
- `0x140022cd8`

## callees

- `0x1400025f4`
- `0x140021fa0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140022008`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022063`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400220ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400220f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022008`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022063`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400220ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400220f2`

## pseudocode

```c
void __fastcall DfscReleaseDcContext(PVOID P)
{
  __int64 v2; // r9
  __int64 v3; // r9
  __int64 v4; // r9

  if ( P && _InterlockedExchangeAdd((volatile signed __int32 *)P + 1, 0xFFFFFFFF) == 1 )
  {
    v2 = *((_QWORD *)P + 6);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, v2);
      }
      ExFreePoolWithTag(*((PVOID *)P + 6), 0);
      *((_QWORD *)P + 6) = 0;
      *((_QWORD *)P + 7) = 0;
      *((_QWORD *)P + 1) = 0;
    }
    v3 = *((_QWORD *)P + 3);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, v3);
      }
      ExFreePoolWithTag(*((PVOID *)P + 3), 0);
      *((_QWORD *)P + 3) = 0;
    }
    v4 = *((_QWORD *)P + 5);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, v4);
      }
      ExFreePoolWithTag(*((PVOID *)P + 5), 0);
      *((_QWORD *)P + 5) = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, P);
    }
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140021fa0  test    rcx, rcx
0x140021fa3  jz      locret_14002210D
0x140021fa9  mov     [rsp+arg_0], rbx
0x140021fae  mov     [rsp+arg_8], rbp
0x140021fb3  push    rsi
0x140021fb4  sub     rsp, 20h
0x140021fb8  mov     rbx, rcx
0x140021fbb  or      eax, 0FFFFFFFFh
0x140021fbe  lock xadd [rcx+4], eax
0x140021fc3  cmp     eax, 1
0x140021fc6  jnz     loc_1400220FE
0x140021fcc  mov     r9, [rcx+30h]
0x140021fd0  lea     rbp, WPP_GLOBAL_Control
0x140021fd7  test    r9, r9
0x140021fda  jz      short loc_14002202C
0x140021fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fe3  cmp     rcx, rbp
0x140021fe6  jz      short loc_140022002
0x140021fe8  bt      dword ptr [rcx+2Ch], 16h
0x140021fed  jnb     short loc_140022002
0x140021fef  mov     rcx, [rcx+18h]
0x140021ff3  lea     edx, [rax+15h]
0x140021ff6  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x140021ffd  call    WPP_SF_q
0x140022002  mov     rcx, [rbx+30h]; P
0x140022006  xor     edx, edx; Tag
0x140022008  call    cs:__imp_ExFreePoolWithTag
0x14002200f  nop     dword ptr [rax+rax+00h]
0x140022014  mov     qword ptr [rbx+30h], 0
0x14002201c  mov     qword ptr [rbx+38h], 0
0x140022024  mov     qword ptr [rbx+8], 0
0x14002202c  mov     r9, [rbx+18h]
0x140022030  test    r9, r9
0x140022033  jz      short loc_140022077
0x140022035  mov     rcx, cs:WPP_GLOBAL_Control
0x14002203c  cmp     rcx, rbp
0x14002203f  jz      short loc_14002205D
0x140022041  bt      dword ptr [rcx+2Ch], 16h
0x140022046  jnb     short loc_14002205D
0x140022048  mov     rcx, [rcx+18h]
0x14002204c  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x140022053  mov     edx, 17h
0x140022058  call    WPP_SF_q
0x14002205d  mov     rcx, [rbx+18h]; P
0x140022061  xor     edx, edx; Tag
0x140022063  call    cs:__imp_ExFreePoolWithTag
0x14002206a  nop     dword ptr [rax+rax+00h]
0x14002206f  mov     qword ptr [rbx+18h], 0
0x140022077  mov     r9, [rbx+28h]
0x14002207b  test    r9, r9
0x14002207e  jz      short loc_1400220C2
0x140022080  mov     rcx, cs:WPP_GLOBAL_Control
0x140022087  cmp     rcx, rbp
0x14002208a  jz      short loc_1400220A8
0x14002208c  bt      dword ptr [rcx+2Ch], 16h
0x140022091  jnb     short loc_1400220A8
0x140022093  mov     rcx, [rcx+18h]
0x140022097  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x14002209e  mov     edx, 18h
0x1400220a3  call    WPP_SF_q
0x1400220a8  mov     rcx, [rbx+28h]; P
0x1400220ac  xor     edx, edx; Tag
0x1400220ae  call    cs:__imp_ExFreePoolWithTag
0x1400220b5  nop     dword ptr [rax+rax+00h]
0x1400220ba  mov     qword ptr [rbx+28h], 0
0x1400220c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220c9  cmp     rcx, rbp
0x1400220cc  jz      short loc_1400220ED
0x1400220ce  bt      dword ptr [rcx+2Ch], 16h
0x1400220d3  jnb     short loc_1400220ED
0x1400220d5  mov     rcx, [rcx+18h]
0x1400220d9  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x1400220e0  mov     edx, 19h
0x1400220e5  mov     r9, rbx
0x1400220e8  call    WPP_SF_q
0x1400220ed  xor     edx, edx; Tag
0x1400220ef  mov     rcx, rbx; P
0x1400220f2  call    cs:__imp_ExFreePoolWithTag
0x1400220f9  nop     dword ptr [rax+rax+00h]
0x1400220fe  mov     rbx, [rsp+28h+arg_0]
0x140022103  mov     rbp, [rsp+28h+arg_8]
0x140022108  add     rsp, 20h
0x14002210c  pop     rsi
0x14002210d  retn
```
