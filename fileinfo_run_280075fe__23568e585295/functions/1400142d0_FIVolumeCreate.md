# FIVolumeCreate

- ea: `0x1400142d0`
- end: `0x140014511`
- name: `FIVolumeCreate`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013bc0`

## callees

- `0x140002538`
- `0x140003d80`
- `0x1400142d0`

## import_xrefs

- `ntoskrnl!PfFileInfoNotify` at `0x1400144c4`
- `ntoskrnl!PfFileInfoNotify` at `0x1400144c4`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140014369`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140014369`
- `ntoskrnl!rand` at `0x1400142f5`
- `ntoskrnl!rand` at `0x1400142f5`
- `FLTMGR!FltAllocateContext` at `0x140014334`
- `FLTMGR!FltAllocateContext` at `0x140014334`

## pseudocode

```c
NTSTATUS __fastcall FIVolumeCreate(PFLT_CONTEXT *a1)
{
  int v1; // edi
  __int32 v3; // ebx
  NTSTATUS result; // eax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _DWORD v12[3]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+3Ch] [rbp-1Ch]
  int v14; // [rsp+44h] [rbp-14h]
  PFLT_CONTEXT ReturnedContext; // [rsp+88h] [rbp+30h] BYREF

  v1 = dword_1400099D8;
  ReturnedContext = 0;
  v3 = _InterlockedExchange(&dword_1400099E0, 0);
  if ( rand() % (unsigned int)dword_1400099DC < v1 + v3 )
    return -1073741546;
  result = FltAllocateContext((PFLT_FILTER)FIGlobals, 2u, 0x200u, (POOL_TYPE)512, &ReturnedContext);
  if ( result >= 0 )
  {
    memset(ReturnedContext, 0, 0x200u);
    v5 = ReturnedContext;
    *((_QWORD *)ReturnedContext + 1) = ReturnedContext;
    *v5 = v5;
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)ReturnedContext + 2);
    FILockInitialize((char *)ReturnedContext + 24);
    v6 = (char *)ReturnedContext + 32;
    *((_QWORD *)ReturnedContext + 5) = (char *)ReturnedContext + 32;
    *v6 = v6;
    FILockInitialize((char *)ReturnedContext + 136);
    v7 = (char *)ReturnedContext + 144;
    *((_QWORD *)ReturnedContext + 19) = (char *)ReturnedContext + 144;
    *v7 = v7;
    v8 = (char *)ReturnedContext + 160;
    *((_QWORD *)ReturnedContext + 21) = (char *)ReturnedContext + 160;
    *v8 = v8;
    v9 = (char *)ReturnedContext + 192;
    *((_QWORD *)ReturnedContext + 25) = (char *)ReturnedContext + 192;
    *v9 = v9;
    v10 = (char *)ReturnedContext + 176;
    *((_QWORD *)ReturnedContext + 23) = (char *)ReturnedContext + 176;
    *v10 = v10;
    v11 = ReturnedContext;
    *((_QWORD *)ReturnedContext + 28) = 0;
    v11[29] = 0;
    v11[32] = 0;
    v11[33] = 0;
    v11 += 30;
    v11[1] = v11;
    *v11 = v11;
    *((_DWORD *)ReturnedContext + 33) |= 1u;
    *((_QWORD *)ReturnedContext + 12) = FIUnknown;
    *((_WORD *)ReturnedContext + 46) = 11;
    *((_QWORD *)ReturnedContext + 13) = FIUnknown;
    *((_WORD *)ReturnedContext + 47) = 11;
    v13 = 0;
    v14 = 0;
    *((_DWORD *)ReturnedContext + 29) = dword_1400093D0
                                      + ((((MEMORY[0xFFFFF78000000004] * HIDWORD(MEMORY[0xFFFFF78000000320])) << 8)
                                        + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24)) >> 10);
    v12[0] = 15;
    v12[1] = 7;
    v12[2] = 8;
    PfFileInfoNotify(v12);
    *((_DWORD *)ReturnedContext + 30) = HIDWORD(v13);
    _InterlockedIncrement(&dword_1400093A4);
    if ( dword_1400093A8 < (unsigned int)dword_1400093A4 )
      dword_1400093A8 = dword_1400093A4;
    *a1 = ReturnedContext;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400142d0  push    rbp
0x1400142d2  push    rbx
0x1400142d3  push    rsi
0x1400142d4  push    rdi
0x1400142d5  mov     rbp, rsp
0x1400142d8  sub     rsp, 58h
0x1400142dc  mov     edi, cs:dword_1400099D8
0x1400142e2  xor     ebx, ebx
0x1400142e4  mov     [rbp+arg_8], 0
0x1400142ec  mov     rsi, rcx
0x1400142ef  xchg    ebx, cs:dword_1400099E0
0x1400142f5  call    cs:__imp_rand
0x1400142fc  nop     dword ptr [rax+rax+00h]
0x140014301  xor     edx, edx
0x140014303  div     cs:dword_1400099DC
0x140014309  lea     eax, [rdi+rbx]
0x14001430c  cmp     edx, eax
0x14001430e  jb      loc_140014502
0x140014314  mov     rcx, cs:FIGlobals; Filter
0x14001431b  lea     rax, [rbp+arg_8]
0x14001431f  mov     ebx, 200h
0x140014324  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x140014329  mov     r9d, ebx; PoolType
0x14001432c  mov     r8d, ebx; ContextSize
0x14001432f  mov     edx, 2; ContextType
0x140014334  call    cs:__imp_FltAllocateContext
0x14001433b  nop     dword ptr [rax+rax+00h]
0x140014340  test    eax, eax
0x140014342  js      loc_1400144F8
0x140014348  mov     rcx, [rbp+arg_8]; void *
0x14001434c  mov     r8d, ebx; Size
0x14001434f  xor     edx, edx; Val
0x140014351  call    memset
0x140014356  mov     rax, [rbp+arg_8]
0x14001435a  mov     [rax+8], rax
0x14001435e  mov     [rax], rax
0x140014361  mov     rcx, [rbp+arg_8]
0x140014365  add     rcx, 10h; RunRef
0x140014369  call    cs:__imp_ExInitializeRundownProtection
0x140014370  nop     dword ptr [rax+rax+00h]
0x140014375  mov     rcx, [rbp+arg_8]
0x140014379  add     rcx, 18h
0x14001437d  call    FILockInitialize
0x140014382  mov     rax, [rbp+arg_8]
0x140014386  add     rax, 20h ; ' '
0x14001438a  mov     [rax+8], rax
0x14001438e  mov     [rax], rax
0x140014391  mov     rcx, [rbp+arg_8]
0x140014395  add     rcx, 88h
0x14001439c  call    FILockInitialize
0x1400143a1  mov     rax, [rbp+arg_8]
0x1400143a5  lea     rdx, FIUnknown; "\\FI_UNKNOWN"
0x1400143ac  add     rax, 90h
0x1400143b2  mov     ecx, 0Bh
0x1400143b7  mov     [rax+8], rax
0x1400143bb  mov     [rax], rax
0x1400143be  mov     rax, [rbp+arg_8]
0x1400143c2  add     rax, 0A0h
0x1400143c8  mov     [rax+8], rax
0x1400143cc  mov     [rax], rax
0x1400143cf  mov     rax, [rbp+arg_8]
0x1400143d3  add     rax, 0C0h
0x1400143d9  mov     [rax+8], rax
0x1400143dd  mov     [rax], rax
0x1400143e0  mov     rax, [rbp+arg_8]
0x1400143e4  add     rax, 0B0h
0x1400143ea  mov     [rax+8], rax
0x1400143ee  mov     [rax], rax
0x1400143f1  mov     rax, [rbp+arg_8]
0x1400143f5  mov     qword ptr [rax+0E0h], 0
0x140014400  mov     qword ptr [rax+0E8h], 0
0x14001440b  mov     qword ptr [rax+100h], 0
0x140014416  mov     qword ptr [rax+108h], 0
0x140014421  add     rax, 0F0h
0x140014427  mov     [rax+8], rax
0x14001442b  mov     [rax], rax
0x14001442e  mov     rax, [rbp+arg_8]
0x140014432  or      dword ptr [rax+84h], 1
0x140014439  mov     rax, [rbp+arg_8]
0x14001443d  mov     [rax+60h], rdx
0x140014441  mov     rax, [rbp+arg_8]
0x140014445  mov     [rax+5Ch], cx
0x140014449  mov     rax, [rbp+arg_8]
0x14001444d  mov     [rax+68h], rdx
0x140014451  mov     rax, [rbp+arg_8]
0x140014455  mov     [rax+5Eh], cx
0x140014459  mov     rax, 0FFFFF78000000320h
0x140014463  mov     rcx, 0FFFFF78000000004h
0x14001446d  mov     rax, [rax]
0x140014470  mov     ecx, [rcx]
0x140014472  mov     edx, eax
0x140014474  imul    rdx, rcx
0x140014478  shr     rax, 20h
0x14001447c  imul    rax, rcx
0x140014480  shr     rdx, 18h
0x140014484  lea     rcx, [rbp+var_28]
0x140014488  shl     rax, 8
0x14001448c  add     rdx, rax
0x14001448f  mov     [rbp+var_1C], 0
0x140014497  mov     rax, [rbp+arg_8]
0x14001449b  shr     rdx, 0Ah
0x14001449f  add     edx, cs:dword_1400093D0
0x1400144a5  mov     [rbp+var_14], 0
0x1400144ac  mov     [rax+74h], edx
0x1400144af  mov     [rbp+var_28], 0Fh
0x1400144b6  mov     [rbp+var_24], 7
0x1400144bd  mov     [rbp+var_20], 8
0x1400144c4  call    cs:__imp_PfFileInfoNotify
0x1400144cb  nop     dword ptr [rax+rax+00h]
0x1400144d0  mov     rcx, [rbp+arg_8]
0x1400144d4  mov     eax, dword ptr [rbp+var_1C+4]
0x1400144d7  mov     [rcx+78h], eax
0x1400144da  lock inc cs:dword_1400093A4
0x1400144e1  mov     eax, cs:dword_1400093A4
0x1400144e7  cmp     cs:dword_1400093A8, eax
0x1400144ed  jb      short loc_140014509
0x1400144ef  mov     rax, [rbp+arg_8]
0x1400144f3  mov     [rsi], rax
0x1400144f6  xor     eax, eax
0x1400144f8  add     rsp, 58h
0x1400144fc  pop     rdi
0x1400144fd  pop     rsi
0x1400144fe  pop     rbx
0x1400144ff  pop     rbp
0x140014500  retn
0x140014502  mov     eax, 0C0000116h
0x140014507  jmp     short loc_1400144F8
0x140014509  mov     cs:dword_1400093A8, eax
0x14001450f  jmp     short loc_1400144EF
```
