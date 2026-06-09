# PsmSrvTimerStart

- ea: `0x180006460`
- end: `0x18000659a`
- name: `PsmSrvTimerStart`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180006460`
- `0x180006b40`
- `0x180007214`
- `0x18001622c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000647d`
- `ntdll!RtlLengthSid` at `0x18000647d`
- `ntdll!RtlAllocateHeap` at `0x1800064c2`
- `ntdll!RtlAllocateHeap` at `0x1800064c2`
- `ntdll!RtlValidSid` at `0x18000648e`
- `ntdll!RtlValidSid` at `0x18000648e`

## pseudocode

```c
__int64 __fastcall PsmSrvTimerStart(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        char *a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        __int128 *a9,
        __int64 a10,
        _QWORD *a11)
{
  char *Heap; // rax
  char *v14; // rsi
  int v15; // ecx
  _QWORD *v17; // rcx
  __int64 v18; // rdx

  if ( a2 < 2 || RtlLengthSid(a3) != a2 || !RtlValidSid(a3) )
  {
    v17 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return (unsigned int)-1073741811;
    v18 = 51;
    goto LABEL_13;
  }
  if ( !a11 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return (unsigned int)-1073741811;
    v18 = 52;
LABEL_13:
    WPP_SF_(v17[2], v18, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return (unsigned int)-1073741811;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x150u);
  v14 = Heap;
  if ( Heap )
  {
    PsmpResourceAwareTimerInitialize(Heap);
    v15 = PsmpResourceAwareTimerStart(v14, a3, a4, a5, a6, a7, a8, a9, a10, a11);
    if ( v15 >= 0 )
      return 0;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180006460  push    rbx
0x180006462  push    rbp
0x180006463  push    rsi
0x180006464  push    rdi
0x180006465  sub     rsp, 58h
0x180006469  mov     ebp, r9d
0x18000646c  mov     rbx, r8
0x18000646f  mov     edi, edx
0x180006471  cmp     edx, 2
0x180006474  jb      loc_180006548
0x18000647a  mov     rcx, rbx; Sid
0x18000647d  call    cs:__imp_RtlLengthSid
0x180006483  cmp     eax, edi
0x180006485  jnz     loc_180006548
0x18000648b  mov     rcx, rbx; Sid
0x18000648e  call    cs:__imp_RtlValidSid
0x180006494  test    al, al
0x180006496  jz      loc_180006548
0x18000649c  mov     rdi, [rsp+78h+arg_50]
0x1800064a4  test    rdi, rdi
0x1800064a7  jz      loc_180006579
0x1800064ad  mov     rcx, gs:60h
0x1800064b6  xor     edx, edx; Flags
0x1800064b8  mov     r8d, 150h; Size
0x1800064be  mov     rcx, [rcx+30h]; HeapHandle
0x1800064c2  call    cs:__imp_RtlAllocateHeap
0x1800064c8  mov     rsi, rax
0x1800064cb  test    rax, rax
0x1800064ce  jz      loc_180006593
0x1800064d4  mov     rcx, rax
0x1800064d7  call    PsmpResourceAwareTimerInitialize
0x1800064dc  mov     rax, [rsp+78h+arg_48]
0x1800064e4  mov     r8d, ebp
0x1800064e7  mov     r9, [rsp+78h+arg_20]
0x1800064ef  mov     rdx, rbx; Sid2
0x1800064f2  mov     [rsp+78h+var_30], rdi; __int64
0x1800064f7  mov     rcx, rsi; P
0x1800064fa  mov     [rsp+78h+var_38], rax; __int64
0x1800064ff  mov     rax, [rsp+78h+arg_40]
0x180006507  mov     [rsp+78h+var_40], rax; __int64
0x18000650c  mov     eax, [rsp+78h+arg_38]
0x180006513  mov     [rsp+78h+var_48], eax; int
0x180006517  mov     rax, [rsp+78h+arg_30]
0x18000651f  mov     [rsp+78h+var_50], rax; __int64
0x180006524  mov     eax, [rsp+78h+arg_28]
0x18000652b  mov     [rsp+78h+var_58], eax; int
0x18000652f  call    PsmpResourceAwareTimerStart
0x180006534  mov     ecx, eax
0x180006536  xor     eax, eax
0x180006538  test    ecx, ecx
0x18000653a  cmovns  ecx, eax
0x18000653d  mov     eax, ecx
0x18000653f  add     rsp, 58h
0x180006543  pop     rdi
0x180006544  pop     rsi
0x180006545  pop     rbp
0x180006546  pop     rbx
0x180006547  retn
0x180006548  mov     rcx, cs:WPP_GLOBAL_Control
0x18000654f  test    byte ptr [rcx+1Ch], 2
0x180006553  jnz     short loc_18000655C
0x180006555  mov     ecx, 0C000000Dh
0x18000655a  jmp     short loc_18000653D
0x18000655c  cmp     byte ptr [rcx+19h], 2
0x180006560  jb      short loc_180006555
0x180006562  mov     edx, 33h ; '3'
0x180006567  mov     rcx, [rcx+10h]
0x18000656b  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x180006572  call    WPP_SF_
0x180006577  jmp     short loc_180006555
0x180006579  mov     rcx, cs:WPP_GLOBAL_Control
0x180006580  test    byte ptr [rcx+1Ch], 2
0x180006584  jz      short loc_180006555
0x180006586  cmp     byte ptr [rcx+19h], 2
0x18000658a  jb      short loc_180006555
0x18000658c  mov     edx, 34h ; '4'
0x180006591  jmp     short loc_180006567
0x180006593  mov     ecx, 0C000009Ah
0x180006598  jmp     short loc_18000653D
```
