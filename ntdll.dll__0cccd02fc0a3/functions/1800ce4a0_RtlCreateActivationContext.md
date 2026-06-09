# RtlCreateActivationContext

- ea: `0x1800ce4a0`
- end: `0x1800ce624`
- name: `RtlCreateActivationContext`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001b984`
- `0x1800ce4a0`
- `0x1800ce62c`
- `0x1800cecbc`
- `0x18011c79c`
- `0x18016f030`

## string_xrefs

- `0x1800ce5e7`: `RtlCreateActivationContext`

## pseudocode

```c
__int64 __fastcall RtlCreateActivationContext(int a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  __int64 v6; // rdi
  int v9; // ebx
  _QWORD *Heap_0; // rax
  _QWORD *v11; // r14
  _QWORD *v12; // rdi
  _QWORD *v13; // rcx
  _QWORD *v14; // r8
  __int64 v15; // rdx
  _QWORD *v16; // rax

  v6 = a3;
  if ( (char *)a2 == "Actx " )
  {
    DbgPrintEx(51, 0, "SXS: %s() passed the empty activation context data\n", "RtlCreateActivationContext");
    return (unsigned int)-1073741811;
  }
  if ( a6 )
    *a6 = 0;
  if ( a1 || !a2 || a3 > 0x10000 || !a6 )
    return (unsigned int)-1073741811;
  v9 = RtlpValidateActivationContextData();
  if ( v9 >= 0 )
  {
    Heap_0 = (_QWORD *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6 + 528);
    v11 = Heap_0;
    if ( Heap_0 )
    {
      v12 = Heap_0 + 1;
      *Heap_0 = 1733124929;
      v13 = Heap_0 + 15;
      v14 = 0;
      v15 = *(unsigned int *)(*(unsigned int *)(a2 + 24) + a2 + 8);
      v16 = Heap_0 + 17;
      if ( (unsigned int)v15 <= 0x20 )
        v14 = v16;
      v9 = RtlpInitializeAssemblyStorageMap(v13, v15, v14);
      if ( v9 < 0 )
      {
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v11);
      }
      else
      {
        v12[5] = a5;
        *v12 = 1;
        v12[3] = a2;
        v12[4] = a4;
        *(_OWORD *)(v11 + 7) = 0;
        *(_OWORD *)(v11 + 9) = 0;
        *(_OWORD *)(v11 + 11) = 0;
        *(_OWORD *)(v11 + 13) = 0;
        memset_thunk_772440563353939046(v12 + 49, 0, 0x80u);
        *((_DWORD *)v12 + 96) = 0;
        if ( g_SxsKeepActivationContextsAlive )
          RtlpPlaceActivationContextOnLiveList(v12);
        *a6 = v12;
        return 0;
      }
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ce4a0  push    rbx
0x1800ce4a2  push    rbp
0x1800ce4a3  push    rsi
0x1800ce4a4  push    rdi
0x1800ce4a5  push    r14
0x1800ce4a7  push    r15
0x1800ce4a9  sub     rsp, 28h
0x1800ce4ad  lea     rax, RtlpTheEmptyActivationContextData; "Actx "
0x1800ce4b4  mov     edi, r8d
0x1800ce4b7  mov     r15, r9
0x1800ce4ba  mov     rbp, rdx
0x1800ce4bd  cmp     rdx, rax
0x1800ce4c0  jz      loc_1800CE5E5
0x1800ce4c6  mov     rsi, [rsp+58h+arg_28]
0x1800ce4ce  test    rsi, rsi
0x1800ce4d1  jz      short loc_1800CE4DA
0x1800ce4d3  mov     qword ptr [rsi], 0
0x1800ce4da  test    ecx, ecx
0x1800ce4dc  jnz     loc_1800CE5FD
0x1800ce4e2  test    rbp, rbp
0x1800ce4e5  jz      loc_1800CE5FD
0x1800ce4eb  cmp     edi, 10000h
0x1800ce4f1  ja      loc_1800CE5FD
0x1800ce4f7  test    rsi, rsi
0x1800ce4fa  jz      loc_1800CE5FD
0x1800ce500  call    RtlpValidateActivationContextData
0x1800ce505  mov     ebx, eax
0x1800ce507  test    eax, eax
0x1800ce509  js      loc_1800CE5D5
0x1800ce50f  mov     rcx, gs:60h
0x1800ce518  lea     r8, [rdi+210h]
0x1800ce51f  xor     edx, edx
0x1800ce521  mov     rcx, [rcx+30h]
0x1800ce525  call    RtlAllocateHeap_0
0x1800ce52a  mov     r14, rax
0x1800ce52d  test    rax, rax
0x1800ce530  jz      loc_1800CE604
0x1800ce536  lea     rdi, [rax+8]
0x1800ce53a  mov     qword ptr [rax], 674D6341h
0x1800ce541  mov     eax, [rbp+18h]
0x1800ce544  lea     rcx, [rdi+70h]
0x1800ce548  xor     r8d, r8d
0x1800ce54b  mov     edx, [rax+rbp+8]
0x1800ce54f  cmp     edx, 20h ; ' '
0x1800ce552  lea     rax, [rdi+80h]
0x1800ce559  cmovbe  r8, rax
0x1800ce55d  call    RtlpInitializeAssemblyStorageMap
0x1800ce562  mov     ebx, eax
0x1800ce564  test    eax, eax
0x1800ce566  js      loc_1800CE60B
0x1800ce56c  mov     rax, [rsp+58h+arg_20]
0x1800ce574  lea     rcx, [rdi+188h]; void *
0x1800ce57b  mov     [rdi+28h], rax
0x1800ce57f  xorps   xmm0, xmm0
0x1800ce582  mov     qword ptr [rdi], 1
0x1800ce589  xorps   xmm1, xmm1
0x1800ce58c  mov     [rdi+18h], rbp
0x1800ce590  xor     edx, edx; Val
0x1800ce592  mov     [rdi+20h], r15
0x1800ce596  mov     r8d, 80h; Size
0x1800ce59c  movups  xmmword ptr [r14+38h], xmm0
0x1800ce5a1  movups  xmmword ptr [r14+48h], xmm0
0x1800ce5a6  movups  xmmword ptr [r14+58h], xmm1
0x1800ce5ab  movups  xmmword ptr [r14+68h], xmm1
0x1800ce5b0  call    memset$thunk$772440563353939046
0x1800ce5b5  mov     dword ptr [rdi+180h], 0
0x1800ce5bf  cmp     cs:g_SxsKeepActivationContextsAlive, 0
0x1800ce5c6  jz      short loc_1800CE5D0
0x1800ce5c8  mov     rcx, rdi
0x1800ce5cb  call    RtlpPlaceActivationContextOnLiveList
0x1800ce5d0  mov     [rsi], rdi
0x1800ce5d3  xor     ebx, ebx
0x1800ce5d5  mov     eax, ebx
0x1800ce5d7  add     rsp, 28h
0x1800ce5db  pop     r15
0x1800ce5dd  pop     r14
0x1800ce5df  pop     rdi
0x1800ce5e0  pop     rsi
0x1800ce5e1  pop     rbp
0x1800ce5e2  pop     rbx
0x1800ce5e3  retn
0x1800ce5e5  xor     edx, edx
0x1800ce5e7  lea     r9, aRtlcreateactiv_0; "RtlCreateActivationContext"
0x1800ce5ee  lea     r8, aSxsSPassedTheE; "SXS: %s() passed the empty activation c"...
0x1800ce5f5  lea     ecx, [rdx+33h]
0x1800ce5f8  call    DbgPrintEx
0x1800ce5fd  mov     ebx, 0C000000Dh
0x1800ce602  jmp     short loc_1800CE5D5
0x1800ce604  mov     ebx, 0C0000017h
0x1800ce609  jmp     short loc_1800CE5D5
0x1800ce60b  mov     rcx, gs:60h
0x1800ce614  mov     r8, r14
0x1800ce617  xor     edx, edx
0x1800ce619  mov     rcx, [rcx+30h]
0x1800ce61d  call    RtlFreeHeap_0
0x1800ce622  jmp     short loc_1800CE5D5
```
