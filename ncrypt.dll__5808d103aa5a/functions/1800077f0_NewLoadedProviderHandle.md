# _NewLoadedProviderHandle

- ea: `0x1800077f0`
- end: `0x180007952`
- name: `_NewLoadedProviderHandle`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007df4`

## callees

- `0x1800077f0`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800078d8`
- `ntdll!RtlAllocateHeap` at `0x1800078d8`

## string_xrefs

- `0x180007881`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180007925`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
  unsigned int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *Heap; // rax

  v3 = *(_WORD ***)(a1 + 40);
  *a3 = 0;
  v7 = *v3;
  if ( !*v3 )
  {
    LOBYTE(v9) = 87;
    goto LABEL_11;
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
LABEL_11:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)a3,
        (unsigned int)"hResult",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        82);
    v12 = -1073741811;
    goto LABEL_15;
  }
  v10 = (2 * (2048 - v8)) & -(__int64)(v8 != 0);
  v11 = v10 + 2;
  if ( v10 + 2 >= v10 && v11 < 0xFFFFFFFFFFFFFFE0uLL )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10 + 34);
    v15 = Heap;
    if ( Heap )
    {
      *Heap = Heap + 4;
      v12 = 0;
      memcpy_0(Heap + 4, **(const void ***)(a1 + 40), v11);
      v15[1] = a2;
      *((_DWORD *)v15 + 4) = 2;
      v15[3] = 0;
      goto LABEL_16;
    }
    v12 = -1073741801;
    v13 = 367;
    v14 = 3221225495LL;
  }
  else
  {
    v12 = -1073741675;
    v13 = 348;
    v14 = 3221225621LL;
  }
  DebugTraceError(v14, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v13);
LABEL_15:
  v15 = 0;
LABEL_16:
  *a3 = v15;
  return v12;
}

```

## disassembly

```asm
0x1800077f0  push    rbx
0x1800077f2  push    rbp
0x1800077f3  push    rsi
0x1800077f4  push    rdi
0x1800077f5  push    r12
0x1800077f7  push    r14
0x1800077f9  push    r15
0x1800077fb  sub     rsp, 40h
0x1800077ff  mov     rax, [rcx+28h]
0x180007803  xor     r12d, r12d
0x180007806  mov     r14, r8
0x180007809  mov     [r8], r12
0x18000780c  mov     r15, rdx
0x18000780f  mov     rbp, rcx
0x180007812  mov     r11, [rax]
0x180007815  test    r11, r11
0x180007818  jz      short loc_18000788F
0x18000781a  mov     r10d, 800h
0x180007820  mov     r9d, r10d
0x180007823  cmp     [r11], r12w
0x180007827  jz      short loc_180007833
0x180007829  add     r11, 2
0x18000782d  sub     r9, 1
0x180007831  jnz     short loc_180007823
0x180007833  mov     rax, r9
0x180007836  neg     rax
0x180007839  sbb     ecx, ecx
0x18000783b  not     ecx
0x18000783d  and     ecx, 80070057h
0x180007843  test    r9, r9
0x180007846  jz      short loc_180007894
0x180007848  sub     r10, r9
0x18000784b  add     r10, r10
0x18000784e  neg     r9
0x180007851  sbb     rax, rax
0x180007854  and     rax, r10
0x180007857  lea     rsi, [rax+2]
0x18000785b  cmp     rsi, rax
0x18000785e  jb      short loc_18000786A
0x180007860  lea     r8, [rsi+20h]; Size
0x180007864  cmp     r8, 20h ; ' '
0x180007868  jnb     short loc_1800078C9
0x18000786a  mov     edi, 0C0000095h
0x18000786f  mov     r9d, 15Ch
0x180007875  mov     ecx, 0C0000095h
0x18000787a  lea     rdx, aSresult; "sResult"
0x180007881  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007888  call    DebugTraceError
0x18000788d  jmp     short loc_1800078B2
0x18000788f  mov     ecx, 80070057h
0x180007894  mov     rdx, cs:WPP_GLOBAL_Control
0x18000789b  lea     rax, WPP_GLOBAL_Control
0x1800078a2  cmp     rdx, rax
0x1800078a5  jz      short loc_1800078AD
0x1800078a7  test    byte ptr [rdx+1Ch], 1
0x1800078ab  jnz     short loc_180007925
0x1800078ad  mov     edi, 0C000000Dh
0x1800078b2  mov     rbx, r12
0x1800078b5  mov     [r14], rbx
0x1800078b8  mov     eax, edi
0x1800078ba  add     rsp, 40h
0x1800078be  pop     r15
0x1800078c0  pop     r14
0x1800078c2  pop     r12
0x1800078c4  pop     rdi
0x1800078c5  pop     rsi
0x1800078c6  pop     rbp
0x1800078c7  pop     rbx
0x1800078c8  retn
0x1800078c9  mov     rcx, gs:60h
0x1800078d2  xor     edx, edx; Flags
0x1800078d4  mov     rcx, [rcx+30h]; HeapHandle
0x1800078d8  call    cs:__imp_RtlAllocateHeap
0x1800078de  mov     rbx, rax
0x1800078e1  test    rax, rax
0x1800078e4  jz      short loc_180007910
0x1800078e6  lea     rcx, [rax+20h]; void *
0x1800078ea  mov     r8, rsi; Size
0x1800078ed  mov     [rax], rcx
0x1800078f0  mov     edi, r12d
0x1800078f3  mov     rdx, [rbp+28h]
0x1800078f7  mov     rdx, [rdx]; Src
0x1800078fa  call    memcpy_0
0x1800078ff  mov     [rbx+8], r15
0x180007903  mov     dword ptr [rbx+10h], 2
0x18000790a  mov     [rbx+18h], r12
0x18000790e  jmp     short loc_1800078B5
0x180007910  mov     edi, 0C0000017h
0x180007915  mov     r9d, 16Fh
0x18000791b  mov     ecx, 0C0000017h
0x180007920  jmp     loc_18000787A
0x180007925  lea     rax, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000792c  mov     [rsp+78h+var_48], 152h
0x180007934  mov     [rsp+78h+var_50], rax
0x180007939  lea     r9, aHresult; "hResult"
0x180007940  mov     [rsp+78h+var_58], ecx
0x180007944  mov     rcx, [rdx+10h]
0x180007948  call    WPP_SF_sDsd
0x18000794d  jmp     loc_1800078AD
```
