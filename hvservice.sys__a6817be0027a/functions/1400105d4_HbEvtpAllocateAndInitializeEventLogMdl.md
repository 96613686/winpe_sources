# HbEvtpAllocateAndInitializeEventLogMdl

- ea: `0x1400105d4`
- end: `0x1400106f0`
- name: `HbEvtpAllocateAndInitializeEventLogMdl`
- size: `284`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010700`
- `0x140012abc`

## callees

- `0x140001600`
- `0x1400105d4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001060e`
- `ntoskrnl!ExAllocatePool2` at `0x14001060e`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400106a7`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400106a7`

## pseudocode

```c
__int64 __fastcall HbEvtpAllocateAndInitializeEventLogMdl(int a1, __int64 a2)
{
  __int64 Pool2; // rax
  unsigned int v6; // ebx
  PMDL PagesForMdl; // rax

  if ( (unsigned int)(a1 - 1) > 0x1FF )
    return 3221225485LL;
  if ( byte_140009048 )
  {
    Pool2 = ExAllocatePool2(64, 4144, 1967284808);
    *(_QWORD *)a2 = Pool2;
    if ( !Pool2 )
    {
      HbpTraceEvent(
        0,
        "HbEvtpAllocateAndInitializeEventLogMdl",
        2379,
        "Out of memory. Can't allocate MDL for %d pages",
        a1);
      return 3221225626LL;
    }
    *(_QWORD *)Pool2 = 0;
    v6 = a1 << 12;
    *(_DWORD *)(Pool2 + 40) = v6;
    *(_WORD *)(Pool2 + 8) = 8 * ((v6 >> 12) + 6);
    *(_WORD *)(Pool2 + 10) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)(Pool2 + 44) = 0;
    *(_WORD *)(*(_QWORD *)a2 + 10LL) |= 0x2002u;
  }
  else
  {
    PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, (unsigned int)(a1 << 12), MmCached, 4u);
    *(_QWORD *)a2 = PagesForMdl;
    if ( !PagesForMdl )
    {
      HbpTraceEvent(
        0,
        "HbEvtpAllocateAndInitializeEventLogMdl",
        2406,
        "Out of memory. Can't allocate %d pages of physical memory",
        a1);
      return 3221225626LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400105d4  mov     [rsp+arg_0], rbx
0x1400105d9  push    rdi
0x1400105da  sub     rsp, 30h
0x1400105de  lea     eax, [rcx-1]
0x1400105e1  mov     rdi, rdx
0x1400105e4  mov     ebx, ecx
0x1400105e6  cmp     eax, 1FFh
0x1400105eb  ja      loc_1400106DF
0x1400105f1  cmp     cs:byte_140009048, 0
0x1400105f8  jz      loc_140010687
0x1400105fe  mov     edx, 1030h
0x140010603  mov     ecx, 40h ; '@'
0x140010608  mov     r8d, 75426248h
0x14001060e  call    cs:__imp_ExAllocatePool2
0x140010615  nop     dword ptr [rax+rax+00h]
0x14001061a  mov     [rdi], rax
0x14001061d  mov     rcx, rax
0x140010620  test    rax, rax
0x140010623  jnz     short loc_14001064C
0x140010625  lea     r9, aOutOfMemoryCan; "Out of memory. Can't allocate MDL for %"...
0x14001062c  mov     [rsp+38h+CacheType], ebx
0x140010630  mov     r8d, 94Bh
0x140010636  lea     rdx, aHbevtpallocate_0; "HbEvtpAllocateAndInitializeEventLogMdl"
0x14001063d  call    HbpTraceEvent
0x140010642  mov     eax, 0C000009Ah
0x140010647  jmp     loc_1400106E4
0x14001064c  mov     qword ptr [rax], 0
0x140010653  shl     ebx, 0Ch
0x140010656  mov     eax, ebx
0x140010658  mov     [rcx+28h], ebx
0x14001065b  shr     eax, 0Ch
0x14001065e  add     ax, 6
0x140010662  shl     ax, 3
0x140010666  mov     [rcx+8], ax
0x14001066a  xor     eax, eax
0x14001066c  mov     [rcx+0Ah], ax
0x140010670  mov     [rcx+20h], rax
0x140010674  mov     [rcx+2Ch], eax
0x140010677  mov     ecx, 2002h
0x14001067c  mov     rax, [rdi]
0x14001067f  or      [rax+0Ah], cx
0x140010683  xor     eax, eax
0x140010685  jmp     short loc_1400106E4
0x140010687  mov     r9d, ebx
0x14001068a  mov     [rsp+38h+Flags], 4; Flags
0x140010692  shl     r9d, 0Ch; TotalBytes
0x140010696  xor     r8d, r8d; SkipBytes
0x140010699  xor     ecx, ecx; LowAddress
0x14001069b  mov     [rsp+38h+CacheType], 1; CacheType
0x1400106a3  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x1400106a7  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400106ae  nop     dword ptr [rax+rax+00h]
0x1400106b3  mov     [rdi], rax
0x1400106b6  test    rax, rax
0x1400106b9  jnz     short loc_140010683
0x1400106bb  lea     r9, aOutOfMemoryCan_1; "Out of memory. Can't allocate %d pages "...
0x1400106c2  mov     [rsp+38h+CacheType], ebx
0x1400106c6  mov     r8d, 966h
0x1400106cc  lea     rdx, aHbevtpallocate_0; "HbEvtpAllocateAndInitializeEventLogMdl"
0x1400106d3  xor     ecx, ecx
0x1400106d5  call    HbpTraceEvent
0x1400106da  jmp     loc_140010642
0x1400106df  mov     eax, 0C000000Dh
0x1400106e4  mov     rbx, [rsp+38h+arg_0]
0x1400106e9  add     rsp, 30h
0x1400106ed  pop     rdi
0x1400106ee  retn
```
