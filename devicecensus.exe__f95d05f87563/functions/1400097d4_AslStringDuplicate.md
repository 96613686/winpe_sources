# AslStringDuplicate

- ea: `0x1400097d4`
- end: `0x140009a07`
- name: `AslStringDuplicate`
- size: `563`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140007448`
- `0x14000ba04`
- `0x14000fee8`

## callees

- `0x140007074`
- `0x14000800c`
- `0x1400097d4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400099ea`
- `ntdll!RtlFreeHeap` at `0x1400099ea`
- `ntdll!RtlAllocateHeap` at `0x14000992a`
- `ntdll!RtlAllocateHeap` at `0x14000992a`

## string_xrefs

- `0x140009980`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicate(_QWORD *a1, _WORD *a2)
{
  void *v4; // rsi
  int v5; // ebx
  __int64 v6; // rax
  _WORD *i; // rcx
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  SIZE_T v12; // rax
  PVOID Heap; // rax
  int v14; // eax
  unsigned __int64 v16; // [rsp+90h] [rbp+18h]

  v4 = 0;
  *a1 = 0;
  v5 = 0;
  if ( a2 )
  {
    v6 = 0x7FFFFFFF;
    for ( i = a2; v6 && *i; ++i )
      --v6;
    if ( !v6 )
      v5 = -1073741811;
    if ( v5 < 0 )
      v16 = 0;
    else
      v16 = 0x7FFFFFFF - v6;
    if ( v5 < 0 )
    {
      v8 = "RtlStringCchLengthW failed [%x]";
      v9 = 590;
LABEL_13:
      AslLogCallPrintf(1, "AslStringDuplicate", v9, v8, v5);
      goto LABEL_29;
    }
    v10 = v16 + 1;
    if ( v16 + 1 < v16 )
    {
      v10 = -1;
      v5 = -1073741675;
      v11 = -1;
    }
    else
    {
      v5 = 0;
      v11 = v16 + 1;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 602;
      goto LABEL_13;
    }
    v12 = 2 * v11;
    if ( is_mul_ok(v11, 2u) )
    {
      v5 = 0;
    }
    else
    {
      v12 = -1;
      v5 = -1073741675;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 608;
      goto LABEL_13;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
    v4 = Heap;
    if ( Heap )
    {
      v14 = RtlStringCchCopyW(Heap, v10, a2);
      v5 = v14;
      if ( v14 >= 0 )
      {
        *a1 = v4;
        v4 = 0;
        v5 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "AslStringDuplicate", 632, "RtlStringCchCopyW failed [%x]", v14);
      }
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslStringDuplicate", 615, "Out of memory");
    }
  }
LABEL_29:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400097d4  mov     rax, rsp
0x1400097d7  mov     [rax+8], rbx
0x1400097db  push    rsi
0x1400097dc  push    rdi
0x1400097dd  push    r12
0x1400097df  push    r14
0x1400097e1  push    r15
0x1400097e3  sub     rsp, 50h
0x1400097e7  mov     r15, rdx
0x1400097ea  mov     r12, rcx
0x1400097ed  xor     edi, edi
0x1400097ef  mov     [rax+18h], rdi
0x1400097f3  mov     esi, edi
0x1400097f5  mov     [rax-40h], rdi
0x1400097f9  mov     [rcx], rdi
0x1400097fc  mov     ebx, edi
0x1400097fe  test    rdx, rdx
0x140009801  jz      loc_1400099A0
0x140009807  lea     r8, [rax+18h]
0x14000980b  mov     edx, 7FFFFFFFh
0x140009810  mov     eax, edx
0x140009812  mov     [rsp+78h+var_30], rdx
0x140009817  mov     rcx, r15
0x14000981a  mov     [rsp+78h+var_38], rcx
0x14000981f  test    rax, rax
0x140009822  jz      short loc_14000983C
0x140009824  cmp     [rcx], di
0x140009827  jz      short loc_14000983C
0x140009829  add     rcx, 2
0x14000982d  mov     [rsp+78h+var_38], rcx
0x140009832  dec     rax
0x140009835  mov     [rsp+78h+var_30], rax
0x14000983a  jmp     short loc_14000981F
0x14000983c  mov     ecx, 0C000000Dh
0x140009841  test    rax, rax
0x140009844  cmovz   ebx, ecx
0x140009847  test    ebx, ebx
0x140009849  js      short loc_140009853
0x14000984b  sub     rdx, rax
0x14000984e  mov     [r8], rdx
0x140009851  jmp     short loc_140009856
0x140009853  mov     [r8], rdi
0x140009856  test    ebx, ebx
0x140009858  jns     short loc_14000985D
0x14000985a  mov     [r8], rdi
0x14000985d  mov     [rsp+78h+var_48], ebx
0x140009861  test    ebx, ebx
0x140009863  jns     short loc_14000988C
0x140009865  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x14000986c  mov     r8d, 24Eh
0x140009872  mov     [rsp+78h+var_58], ebx
0x140009876  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x14000987d  mov     ecx, 1
0x140009882  call    AslLogCallPrintf
0x140009887  jmp     loc_1400099A4
0x14000988c  mov     rax, [rsp+78h+arg_10]
0x140009894  lea     r14, [rax+1]
0x140009898  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000989c  cmp     r14, rax
0x14000989f  jb      short loc_1400098B0
0x1400098a1  mov     [rsp+78h+arg_10], r14
0x1400098a9  mov     ebx, edi
0x1400098ab  mov     rdx, r14
0x1400098ae  jmp     short loc_1400098C3
0x1400098b0  mov     r14, rcx
0x1400098b3  mov     [rsp+78h+arg_10], rcx
0x1400098bb  mov     ebx, 0C0000095h
0x1400098c0  mov     rdx, rcx
0x1400098c3  mov     [rsp+78h+var_48], ebx
0x1400098c7  test    ebx, ebx
0x1400098c9  jns     short loc_1400098DA
0x1400098cb  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x1400098d2  mov     r8d, 25Ah
0x1400098d8  jmp     short loc_140009872
0x1400098da  mov     [rsp+78h+arg_18], rdi
0x1400098e2  mov     eax, 2
0x1400098e7  mul     rdx
0x1400098ea  test    rdx, rdx
0x1400098ed  jnz     short loc_1400098F3
0x1400098ef  mov     ebx, edi
0x1400098f1  jmp     short loc_1400098FB
0x1400098f3  mov     rax, rcx
0x1400098f6  mov     ebx, 0C0000095h
0x1400098fb  mov     [rsp+78h+var_48], ebx
0x1400098ff  test    ebx, ebx
0x140009901  jns     short loc_140009915
0x140009903  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x14000990a  mov     r8d, 260h
0x140009910  jmp     loc_140009872
0x140009915  mov     rcx, gs:60h
0x14000991e  mov     r8, rax; Size
0x140009921  mov     edx, 8; Flags
0x140009926  mov     rcx, [rcx+30h]; HeapHandle
0x14000992a  call    cs:__imp_RtlAllocateHeap
0x140009930  mov     rsi, rax
0x140009933  mov     [rsp+78h+var_40], rax
0x140009938  test    rax, rax
0x14000993b  jnz     short loc_140009964
0x14000993d  mov     ebx, 0C0000017h
0x140009942  mov     [rsp+78h+var_48], ebx
0x140009946  lea     r9, aOutOfMemory; "Out of memory"
0x14000994d  mov     r8d, 267h
0x140009953  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x14000995a  lea     ecx, [rax+1]
0x14000995d  call    AslLogCallPrintf
0x140009962  jmp     short loc_1400099A4
0x140009964  mov     r8, r15
0x140009967  mov     rdx, r14
0x14000996a  mov     rcx, rsi
0x14000996d  call    RtlStringCchCopyW
0x140009972  mov     ebx, eax
0x140009974  mov     [rsp+78h+var_48], eax
0x140009978  test    eax, eax
0x14000997a  jns     short loc_140009992
0x14000997c  mov     [rsp+78h+var_58], eax
0x140009980  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x140009987  mov     r8d, 278h
0x14000998d  jmp     loc_140009876
0x140009992  mov     [r12], rsi
0x140009996  mov     rsi, rdi
0x140009999  mov     [rsp+78h+var_40], rdi
0x14000999e  mov     ebx, edi
0x1400099a0  mov     [rsp+78h+var_48], ebx
0x1400099a4  jmp     short loc_1400099D3
0x1400099a6  mov     ebx, eax
0x1400099a8  mov     [rsp+78h+var_48], eax
0x1400099ac  mov     [rsp+78h+var_58], eax
0x1400099b0  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x1400099b7  mov     r8d, 289h
0x1400099bd  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x1400099c4  mov     ecx, 1
0x1400099c9  call    AslLogCallPrintf
0x1400099ce  mov     rsi, [rsp+78h+var_40]
0x1400099d3  test    rsi, rsi
0x1400099d6  jz      short loc_1400099F0
0x1400099d8  mov     rcx, gs:60h
0x1400099e1  mov     r8, rsi; P
0x1400099e4  xor     edx, edx; Flags
0x1400099e6  mov     rcx, [rcx+30h]; HeapHandle
0x1400099ea  call    cs:__imp_RtlFreeHeap
0x1400099f0  mov     eax, ebx
0x1400099f2  mov     rbx, [rsp+78h+arg_0]
0x1400099fa  add     rsp, 50h
0x1400099fe  pop     r15
0x140009a00  pop     r14
0x140009a02  pop     r12
0x140009a04  pop     rdi
0x140009a05  pop     rsi
0x140009a06  retn
0x140011836  push    rbp
0x140011838  sub     rsp, 30h
0x14001183c  mov     rbp, rdx
0x14001183f  mov     rax, [rcx]
0x140011842  xor     ecx, ecx
0x140011844  cmp     dword ptr [rax], 0C00000FDh
0x14001184a  setnz   cl
0x14001184d  mov     [rbp+34h], ecx
0x140011850  mov     eax, [rbp+34h]
0x140011853  add     rsp, 30h
0x140011857  pop     rbp
0x140011858  retn
```
