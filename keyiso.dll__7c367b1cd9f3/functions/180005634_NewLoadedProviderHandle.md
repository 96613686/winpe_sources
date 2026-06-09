# _NewLoadedProviderHandle

- ea: `0x180005634`
- end: `0x180005799`
- name: `_NewLoadedProviderHandle`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004b70`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180005634`
- `0x180018928`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800056c5`
- `ntdll!RtlAllocateHeap` at `0x1800056c5`

## string_xrefs

- `0x1800056ea`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180005755`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall NewLoadedProviderHandle(__int64 a1, __int64 a2, _QWORD *a3)
{
  _WORD **v3; // rax
  _WORD *v7; // r11
  __int64 v8; // r9
  unsigned int v9; // ecx
  unsigned __int64 v10; // rax
  size_t v11; // rsi
  _QWORD *Heap; // rax
  _QWORD *v13; // rbx
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx

  v3 = *(_WORD ***)(a1 + 40);
  *a3 = 0;
  v7 = *v3;
  if ( !*v3 )
  {
    LOBYTE(v9) = 87;
    goto LABEL_14;
  }
  v8 = 2048;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
  {
LABEL_14:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)a3,
        (unsigned int)"hResult",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        82);
    v14 = -1073741811;
    goto LABEL_18;
  }
  v10 = (2 * (2048 - v8)) & -(__int64)(v8 != 0);
  v11 = v10 + 2;
  if ( v10 + 2 < v10 || v11 >= 0xFFFFFFFFFFFFFFE0uLL )
  {
    v14 = -1073741675;
    v15 = 348;
    v16 = 3221225621LL;
    goto LABEL_10;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10 + 34);
  v13 = Heap;
  if ( !Heap )
  {
    v14 = -1073741801;
    v15 = 367;
    v16 = 3221225495LL;
LABEL_10:
    DebugTraceError(v16, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v15);
LABEL_18:
    v13 = 0;
    goto LABEL_19;
  }
  *Heap = Heap + 4;
  v14 = 0;
  memcpy_0(Heap + 4, **(const void ***)(a1 + 40), v11);
  v13[1] = a2;
  *((_DWORD *)v13 + 4) = 2;
  v13[3] = 0;
LABEL_19:
  *a3 = v13;
  return v14;
}

```

## disassembly

```asm
0x180005634  push    rbx
0x180005636  push    rbp
0x180005637  push    rsi
0x180005638  push    rdi
0x180005639  push    r12
0x18000563b  push    r14
0x18000563d  push    r15
0x18000563f  sub     rsp, 40h
0x180005643  mov     rax, [rcx+28h]
0x180005647  xor     r12d, r12d
0x18000564a  mov     r14, r8
0x18000564d  mov     [r8], r12
0x180005650  mov     r15, rdx
0x180005653  mov     rbp, rcx
0x180005656  mov     r11, [rax]
0x180005659  test    r11, r11
0x18000565c  jz      loc_180005737
0x180005662  mov     r10d, 800h
0x180005668  mov     r9d, r10d
0x18000566b  cmp     [r11], r12w
0x18000566f  jz      short loc_18000567B
0x180005671  add     r11, 2
0x180005675  sub     r9, 1
0x180005679  jnz     short loc_18000566B
0x18000567b  mov     rax, r9
0x18000567e  neg     rax
0x180005681  sbb     ecx, ecx
0x180005683  not     ecx
0x180005685  and     ecx, 80070057h
0x18000568b  test    r9, r9
0x18000568e  jz      loc_18000573C
0x180005694  sub     r10, r9
0x180005697  add     r10, r10
0x18000569a  neg     r9
0x18000569d  sbb     rax, rax
0x1800056a0  and     rax, r10
0x1800056a3  lea     rsi, [rax+2]
0x1800056a7  cmp     rsi, rax
0x1800056aa  jb      short loc_180005725
0x1800056ac  lea     r8, [rsi+20h]; Size
0x1800056b0  cmp     r8, 20h ; ' '
0x1800056b4  jb      short loc_180005725
0x1800056b6  mov     rcx, gs:60h
0x1800056bf  xor     edx, edx; Flags
0x1800056c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800056c5  call    cs:__imp_RtlAllocateHeap
0x1800056cb  mov     rbx, rax
0x1800056ce  test    rax, rax
0x1800056d1  jnz     short loc_1800056FB
0x1800056d3  mov     edi, 0C0000017h
0x1800056d8  mov     r9d, 16Fh
0x1800056de  mov     ecx, 0C0000017h
0x1800056e3  lea     rdx, aSresult; "sResult"
0x1800056ea  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800056f1  call    DebugTraceError
0x1800056f6  jmp     loc_180005782
0x1800056fb  lea     rcx, [rax+20h]; void *
0x1800056ff  mov     r8, rsi; Size
0x180005702  mov     [rax], rcx
0x180005705  mov     edi, r12d
0x180005708  mov     rdx, [rbp+28h]
0x18000570c  mov     rdx, [rdx]; Src
0x18000570f  call    memcpy_0
0x180005714  mov     [rbx+8], r15
0x180005718  mov     dword ptr [rbx+10h], 2
0x18000571f  mov     [rbx+18h], r12
0x180005723  jmp     short loc_180005785
0x180005725  mov     edi, 0C0000095h
0x18000572a  mov     r9d, 15Ch
0x180005730  mov     ecx, 0C0000095h
0x180005735  jmp     short loc_1800056E3
0x180005737  mov     ecx, 80070057h
0x18000573c  mov     rdx, cs:WPP_GLOBAL_Control
0x180005743  lea     rax, WPP_GLOBAL_Control
0x18000574a  cmp     rdx, rax
0x18000574d  jz      short loc_18000577D
0x18000574f  test    byte ptr [rdx+1Ch], 1
0x180005753  jz      short loc_18000577D
0x180005755  lea     rax, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000575c  mov     [rsp+78h+var_48], 152h
0x180005764  mov     [rsp+78h+var_50], rax
0x180005769  lea     r9, aHresult; "hResult"
0x180005770  mov     [rsp+78h+var_58], ecx
0x180005774  mov     rcx, [rdx+10h]
0x180005778  call    WPP_SF_sDsd
0x18000577d  mov     edi, 0C000000Dh
0x180005782  mov     rbx, r12
0x180005785  mov     [r14], rbx
0x180005788  mov     eax, edi
0x18000578a  add     rsp, 40h
0x18000578e  pop     r15
0x180005790  pop     r14
0x180005792  pop     r12
0x180005794  pop     rdi
0x180005795  pop     rsi
0x180005796  pop     rbp
0x180005797  pop     rbx
0x180005798  retn
```
