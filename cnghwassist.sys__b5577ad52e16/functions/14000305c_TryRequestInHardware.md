# TryRequestInHardware

- ea: `0x14000305c`
- end: `0x1400031cc`
- name: `TryRequestInHardware`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140003268`
- `0x1400037ec`

## callees

- `0x14000305c`
- `0x1400031d4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400031a7`
- `ntoskrnl!KeSetEvent` at `0x1400031a7`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400030dc`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000318f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400030dc`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000318f`
- `ntoskrnl!KeBugCheck` at `0x1400031bf`
- `ntoskrnl!KeBugCheck` at `0x1400031bf`

## pseudocode

```c
char __fastcall TryRequestInHardware(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int *v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // r8d
  unsigned int v9; // edx
  unsigned int v10; // eax
  bool v12; // zf
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx

  v4 = *(unsigned int **)a1;
  v5 = g_mHwThreadsIdle & v4[12];
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, *(unsigned int *)(a1 + 156), *(_DWORD *)(a1 + 32));
    v12 = !_BitScanForward((unsigned int *)&v13, v5);
    *(_DWORD *)(a1 + 152) = 5;
    if ( v12 || (v14 = 7 * v13, g_hwEngineState[7 * v13]) )
      KeBugCheck(0x6C746166u);
    g_hwEngineState[v14] = a1;
    g_mHwThreadsIdle &= ~LODWORD(g_hwEngineState[v14 + 1]);
    if ( dword_1400077F4[0] )
    {
      v15 = g_maxPrioritySoftware;
      if ( *(_DWORD *)(a1 + 128) > (unsigned int)g_maxPrioritySoftware )
        v15 = *(_DWORD *)(a1 + 128);
      v16 = v15 + 1;
      if ( v15 >= 0xE )
        v16 = v15;
      if ( LODWORD(g_hwEngineState[v14 + 3]) != (_DWORD)v16 )
      {
        v17 = g_hwEngineState[v14 + 2];
        LODWORD(g_hwEngineState[v14 + 3]) = v16;
        KeSetActualBasePriorityThread(v17, v16);
      }
    }
    KeSetEvent((PRKEVENT)&qword_140007680[v14], 0, 0);
    return 1;
  }
  else
  {
    if ( dword_1400077F4[0] )
    {
      v6 = *(_DWORD *)(a1 + 128);
      v7 = *v4;
      v8 = v6 + 1;
      if ( v6 >= 0xE )
        v8 = *(_DWORD *)(a1 + 128);
      if ( v7 )
      {
        v9 = 0;
        v10 = 0;
        while ( LODWORD(g_hwEngineState[7 * v9 + 3]) >= v8 )
        {
          v10 = ++v9;
          if ( v9 >= v7 )
            return 0;
        }
        LODWORD(g_hwEngineState[7 * v10 + 3]) = v8;
        KeSetActualBasePriorityThread(g_hwEngineState[7 * v10 + 2], v8);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14000305c  mov     [rsp+arg_8], rbx
0x140003061  mov     [rsp+arg_10], rsi
0x140003066  push    rdi
0x140003067  sub     rsp, 30h
0x14000306b  mov     rdi, rcx
0x14000306e  mov     [rsp+38h+arg_0], 0
0x140003076  mov     rcx, [rcx]
0x140003079  mov     ebx, [rcx+30h]
0x14000307c  and     ebx, cs:g_mHwThreadsIdle
0x140003082  jnz     short loc_1400030FB
0x140003084  cmp     cs:dword_1400077F4, ebx
0x14000308a  jz      short loc_1400030E8
0x14000308c  mov     eax, [rdi+80h]
0x140003092  cmp     eax, 0Eh
0x140003095  mov     r9d, [rcx]
0x140003098  lea     r8d, [rax+1]
0x14000309c  cmovnb  r8d, eax
0x1400030a0  test    r9d, r9d
0x1400030a3  jz      short loc_1400030E8
0x1400030a5  xor     edx, edx
0x1400030a7  lea     rbx, g_hwEngineState
0x1400030ae  xor     eax, eax
0x1400030b0  mov     r10d, eax
0x1400030b3  mov     eax, edx
0x1400030b5  imul    rcx, rax, 38h ; '8'
0x1400030b9  cmp     [rcx+rbx+18h], r8d
0x1400030be  jb      short loc_1400030CB
0x1400030c0  inc     edx
0x1400030c2  mov     eax, edx
0x1400030c4  cmp     edx, r9d
0x1400030c7  jb      short loc_1400030B0
0x1400030c9  jmp     short loc_1400030E8
0x1400030cb  imul    rcx, r10, 38h ; '8'
0x1400030cf  mov     edx, r8d
0x1400030d2  mov     [rcx+rbx+18h], r8d
0x1400030d7  mov     rcx, [rcx+rbx+10h]
0x1400030dc  call    cs:__imp_KeSetActualBasePriorityThread
0x1400030e3  nop     dword ptr [rax+rax+00h]
0x1400030e8  xor     al, al
0x1400030ea  mov     rbx, [rsp+38h+arg_8]
0x1400030ef  mov     rsi, [rsp+38h+arg_10]
0x1400030f4  add     rsp, 30h
0x1400030f8  pop     rdi
0x1400030f9  retn
0x1400030fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003102  lea     rax, WPP_GLOBAL_Control
0x140003109  cmp     rcx, rax
0x14000310c  jz      short loc_14000312C
0x14000310e  mov     eax, [rcx+2Ch]
0x140003111  test    al, 8
0x140003113  jz      short loc_14000312C
0x140003115  mov     eax, [rdi+20h]
0x140003118  mov     r9d, [rdi+9Ch]
0x14000311f  mov     rcx, [rcx+18h]
0x140003123  mov     [rsp+38h+var_18], eax
0x140003127  call    WPP_SF_Dd
0x14000312c  bsf     eax, ebx
0x14000312f  mov     dword ptr [rdi+98h], 5
0x140003139  jz      short loc_1400031BA
0x14000313b  imul    rsi, rax, 38h ; '8'
0x14000313f  lea     rbx, g_hwEngineState
0x140003146  cmp     qword ptr [rsi+rbx], 0
0x14000314b  jnz     short loc_1400031BA
0x14000314d  mov     [rsi+rbx], rdi
0x140003151  mov     eax, [rsi+rbx+8]
0x140003155  not     eax
0x140003157  and     cs:g_mHwThreadsIdle, eax
0x14000315d  cmp     cs:dword_1400077F4, 0
0x140003164  jz      short loc_14000319B
0x140003166  mov     eax, [rdi+80h]
0x14000316c  mov     ecx, cs:g_maxPrioritySoftware
0x140003172  cmp     eax, ecx
0x140003174  cmova   ecx, eax
0x140003177  cmp     ecx, 0Eh
0x14000317a  lea     edx, [rcx+1]
0x14000317d  cmovnb  edx, ecx
0x140003180  cmp     [rsi+rbx+18h], edx
0x140003184  jz      short loc_14000319B
0x140003186  mov     rcx, [rsi+rbx+10h]
0x14000318b  mov     [rsi+rbx+18h], edx
0x14000318f  call    cs:__imp_KeSetActualBasePriorityThread
0x140003196  nop     dword ptr [rax+rax+00h]
0x14000319b  lea     rcx, [rbx+20h]
0x14000319f  xor     r8d, r8d; Wait
0x1400031a2  add     rcx, rsi; Event
0x1400031a5  xor     edx, edx; Increment
0x1400031a7  call    cs:__imp_KeSetEvent
0x1400031ae  nop     dword ptr [rax+rax+00h]
0x1400031b3  mov     al, 1
0x1400031b5  jmp     loc_1400030EA
0x1400031ba  mov     ecx, 6C746166h; BugCheckCode
0x1400031bf  call    cs:__imp_KeBugCheck
```
