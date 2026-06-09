# UlpQueryConfigGroupBinding

- ea: `0x14009ff60`
- end: `0x1400a00ed`
- name: `UlpQueryConfigGroupBinding`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400a44d8`

## callees

- `0x14000a350`
- `0x14009ff60`
- `0x1400a00f4`
- `0x1400d742c`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14009ffa1`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14009ffa1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14009ffe7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a00ad`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14009ffe7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a00ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009fff3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a00b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009fff3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a00b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009ff8c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009ff8c`

## pseudocode

```c
__int64 __fastcall UlpQueryConfigGroupBinding(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rax
  volatile signed __int32 *v5; // rdi
  int v6; // ecx
  unsigned int AutoConfigGroup; // esi
  int v8; // eax

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 149, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  *a2 = 0;
  a2[1] = 0;
  KeEnterCriticalRegion();
  v4 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 280), 0);
  if ( *(_BYTE *)(a1 + 144) && (v5 = *(volatile signed __int32 **)(a1 + 136)) != 0 )
  {
    v6 = _InterlockedIncrement(v5 + 1);
    if ( UxDebugCheckRefcount && v6 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v5 + 1), 0x21u, v6);
    ExReleaseCacheAwarePushLockSharedEx(v4, 0);
    KeLeaveCriticalRegion();
    AutoConfigGroup = UlGetAutoConfigGroup(v5, a2);
    v8 = _InterlockedDecrement(v5 + 1);
    if ( UxDebugCheckRefcount && v8 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v5 + 1), 0x21u, v8);
    if ( !v8 )
      UlFreeServerSession((PVOID)v5);
  }
  else
  {
    ExReleaseCacheAwarePushLockSharedEx(v4, 0);
    KeLeaveCriticalRegion();
    AutoConfigGroup = -1073741811;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 150, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, AutoConfigGroup);
  return AutoConfigGroup;
}

```

## disassembly

```asm
0x14009ff60  mov     [rsp+arg_0], rbx
0x14009ff65  mov     [rsp+arg_8], rsi
0x14009ff6a  push    rdi
0x14009ff6b  sub     rsp, 30h
0x14009ff6f  mov     rsi, rdx
0x14009ff72  mov     rbx, rcx
0x14009ff75  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14009ff7c  jnz     loc_1400A0078
0x14009ff82  xorps   xmm0, xmm0
0x14009ff85  movups  xmmword ptr [rsi], xmm0
0x14009ff88  movups  xmmword ptr [rsi+10h], xmm0
0x14009ff8c  call    cs:__imp_KeEnterCriticalRegion
0x14009ff93  nop     dword ptr [rax+rax+00h]
0x14009ff98  mov     rcx, [rbx+118h]
0x14009ff9f  xor     edx, edx
0x14009ffa1  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14009ffa8  nop     dword ptr [rax+rax+00h]
0x14009ffad  cmp     byte ptr [rbx+90h], 0
0x14009ffb4  jz      loc_1400A00A8
0x14009ffba  mov     rdi, [rbx+88h]
0x14009ffc1  test    rdi, rdi
0x14009ffc4  jz      loc_1400A00A8
0x14009ffca  lea     rbx, [rdi+4]
0x14009ffce  mov     ecx, 1
0x14009ffd3  lock xadd [rbx], ecx
0x14009ffd7  inc     ecx
0x14009ffd9  cmp     cs:UxDebugCheckRefcount, 0
0x14009ffe0  jnz     short loc_1400A0042
0x14009ffe2  xor     edx, edx
0x14009ffe4  mov     rcx, rax
0x14009ffe7  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14009ffee  nop     dword ptr [rax+rax+00h]
0x14009fff3  call    cs:__imp_KeLeaveCriticalRegion
0x14009fffa  nop     dword ptr [rax+rax+00h]
0x14009ffff  mov     rdx, rsi
0x1400a0002  mov     rcx, rdi
0x1400a0005  call    UlGetAutoConfigGroup
0x1400a000a  mov     esi, eax
0x1400a000c  or      eax, 0FFFFFFFFh
0x1400a000f  lock xadd [rbx], eax
0x1400a0013  dec     eax
0x1400a0015  cmp     cs:UxDebugCheckRefcount, 0
0x1400a001c  jnz     short loc_1400A005D
0x1400a001e  test    eax, eax
0x1400a0020  jz      short loc_1400A009B
0x1400a0022  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400a0029  jnz     loc_1400A00CF
0x1400a002f  mov     rbx, [rsp+38h+arg_0]
0x1400a0034  mov     eax, esi
0x1400a0036  mov     rsi, [rsp+38h+arg_8]
0x1400a003b  add     rsp, 30h
0x1400a003f  pop     rdi
0x1400a0040  retn
0x1400a0042  cmp     ecx, 0FFFFFFFFh
0x1400a0045  jg      short loc_14009FFE2
0x1400a0047  mov     r8d, 21h ; '!'; BugCheckParameter3
0x1400a004d  movsxd  r9, ecx; BugCheckParameter4
0x1400a0050  mov     rdx, rbx; BugCheckParameter2
0x1400a0053  lea     ecx, [r8-1Eh]; BugCheckParameter1
0x1400a0057  call    UlBugCheckEx
0x1400a005d  cmp     eax, 0FFFFFFFFh
0x1400a0060  jg      short loc_1400A001E
0x1400a0062  mov     r8d, 21h ; '!'; BugCheckParameter3
0x1400a0068  movsxd  r9, eax; BugCheckParameter4
0x1400a006b  mov     rdx, rbx; BugCheckParameter2
0x1400a006e  lea     ecx, [r8-1Eh]; BugCheckParameter1
0x1400a0072  call    UlBugCheckEx
0x1400a0078  mov     edx, 95h
0x1400a007d  mov     [rsp+38h+var_18], rsi
0x1400a0082  mov     ecx, 408h
0x1400a0087  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a008e  mov     r9, rbx
0x1400a0091  call    WPP_SF_qq
0x1400a0096  jmp     loc_14009FF82
0x1400a009b  mov     rcx, rdi; P
0x1400a009e  call    UlFreeServerSession
0x1400a00a3  jmp     loc_1400A0022
0x1400a00a8  xor     edx, edx
0x1400a00aa  mov     rcx, rax
0x1400a00ad  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400a00b4  nop     dword ptr [rax+rax+00h]
0x1400a00b9  call    cs:__imp_KeLeaveCriticalRegion
0x1400a00c0  nop     dword ptr [rax+rax+00h]
0x1400a00c5  mov     esi, 0C000000Dh
0x1400a00ca  jmp     loc_1400A0022
0x1400a00cf  mov     edx, 96h
0x1400a00d4  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a00db  mov     ecx, 408h
0x1400a00e0  mov     r9d, esi
0x1400a00e3  call    WPP_SF_d
0x1400a00e8  jmp     loc_1400A002F
```
