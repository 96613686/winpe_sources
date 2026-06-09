# UlpQueryConfigGroupBinding

- ea: `0x14009ff40`
- end: `0x1400a00cd`
- name: `UlpQueryConfigGroupBinding`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400a44b8`

## callees

- `0x14000a350`
- `0x14009ff40`
- `0x1400a00d4`
- `0x1400d737c`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14009ff81`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x14009ff81`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14009ffc7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a008d`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x14009ffc7`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a008d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009ffd3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a0099`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009ffd3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a0099`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009ff6c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009ff6c`

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
0x14009ff40  mov     [rsp+arg_0], rbx
0x14009ff45  mov     [rsp+arg_8], rsi
0x14009ff4a  push    rdi
0x14009ff4b  sub     rsp, 30h
0x14009ff4f  mov     rsi, rdx
0x14009ff52  mov     rbx, rcx
0x14009ff55  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14009ff5c  jnz     loc_1400A0058
0x14009ff62  xorps   xmm0, xmm0
0x14009ff65  movups  xmmword ptr [rsi], xmm0
0x14009ff68  movups  xmmword ptr [rsi+10h], xmm0
0x14009ff6c  call    cs:__imp_KeEnterCriticalRegion
0x14009ff73  nop     dword ptr [rax+rax+00h]
0x14009ff78  mov     rcx, [rbx+118h]
0x14009ff7f  xor     edx, edx
0x14009ff81  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x14009ff88  nop     dword ptr [rax+rax+00h]
0x14009ff8d  cmp     byte ptr [rbx+90h], 0
0x14009ff94  jz      loc_1400A0088
0x14009ff9a  mov     rdi, [rbx+88h]
0x14009ffa1  test    rdi, rdi
0x14009ffa4  jz      loc_1400A0088
0x14009ffaa  lea     rbx, [rdi+4]
0x14009ffae  mov     ecx, 1
0x14009ffb3  lock xadd [rbx], ecx
0x14009ffb7  inc     ecx
0x14009ffb9  cmp     cs:UxDebugCheckRefcount, 0
0x14009ffc0  jnz     short loc_1400A0022
0x14009ffc2  xor     edx, edx
0x14009ffc4  mov     rcx, rax
0x14009ffc7  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x14009ffce  nop     dword ptr [rax+rax+00h]
0x14009ffd3  call    cs:__imp_KeLeaveCriticalRegion
0x14009ffda  nop     dword ptr [rax+rax+00h]
0x14009ffdf  mov     rdx, rsi
0x14009ffe2  mov     rcx, rdi
0x14009ffe5  call    UlGetAutoConfigGroup
0x14009ffea  mov     esi, eax
0x14009ffec  or      eax, 0FFFFFFFFh
0x14009ffef  lock xadd [rbx], eax
0x14009fff3  dec     eax
0x14009fff5  cmp     cs:UxDebugCheckRefcount, 0
0x14009fffc  jnz     short loc_1400A003D
0x14009fffe  test    eax, eax
0x1400a0000  jz      short loc_1400A007B
0x1400a0002  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400a0009  jnz     loc_1400A00AF
0x1400a000f  mov     rbx, [rsp+38h+arg_0]
0x1400a0014  mov     eax, esi
0x1400a0016  mov     rsi, [rsp+38h+arg_8]
0x1400a001b  add     rsp, 30h
0x1400a001f  pop     rdi
0x1400a0020  retn
0x1400a0022  cmp     ecx, 0FFFFFFFFh
0x1400a0025  jg      short loc_14009FFC2
0x1400a0027  mov     r8d, 21h ; '!'; BugCheckParameter3
0x1400a002d  movsxd  r9, ecx; BugCheckParameter4
0x1400a0030  mov     rdx, rbx; BugCheckParameter2
0x1400a0033  lea     ecx, [r8-1Eh]; BugCheckParameter1
0x1400a0037  call    UlBugCheckEx
0x1400a003d  cmp     eax, 0FFFFFFFFh
0x1400a0040  jg      short loc_14009FFFE
0x1400a0042  mov     r8d, 21h ; '!'; BugCheckParameter3
0x1400a0048  movsxd  r9, eax; BugCheckParameter4
0x1400a004b  mov     rdx, rbx; BugCheckParameter2
0x1400a004e  lea     ecx, [r8-1Eh]; BugCheckParameter1
0x1400a0052  call    UlBugCheckEx
0x1400a0058  mov     edx, 95h
0x1400a005d  mov     [rsp+38h+var_18], rsi
0x1400a0062  mov     ecx, 408h
0x1400a0067  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a006e  mov     r9, rbx
0x1400a0071  call    WPP_SF_qq
0x1400a0076  jmp     loc_14009FF62
0x1400a007b  mov     rcx, rdi; P
0x1400a007e  call    UlFreeServerSession
0x1400a0083  jmp     loc_1400A0002
0x1400a0088  xor     edx, edx
0x1400a008a  mov     rcx, rax
0x1400a008d  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400a0094  nop     dword ptr [rax+rax+00h]
0x1400a0099  call    cs:__imp_KeLeaveCriticalRegion
0x1400a00a0  nop     dword ptr [rax+rax+00h]
0x1400a00a5  mov     esi, 0C000000Dh
0x1400a00aa  jmp     loc_1400A0002
0x1400a00af  mov     edx, 96h
0x1400a00b4  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400a00bb  mov     ecx, 408h
0x1400a00c0  mov     r9d, esi
0x1400a00c3  call    WPP_SF_d
0x1400a00c8  jmp     loc_1400A000F
```
