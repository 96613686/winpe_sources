# RtlCreateActivationContext

- ea: `0x1800cfbd0`
- end: `0x1800cfd54`
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
- `0x1800cfbd0`
- `0x1800cfd5c`
- `0x1800d03ec`
- `0x18011d28c`
- `0x18016f030`

## string_xrefs

- `0x1800cfd17`: `RtlCreateActivationContext`

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
0x1800cfbd0  push    rbx
0x1800cfbd2  push    rbp
0x1800cfbd3  push    rsi
0x1800cfbd4  push    rdi
0x1800cfbd5  push    r14
0x1800cfbd7  push    r15
0x1800cfbd9  sub     rsp, 28h
0x1800cfbdd  lea     rax, RtlpTheEmptyActivationContextData; "Actx "
0x1800cfbe4  mov     edi, r8d
0x1800cfbe7  mov     r15, r9
0x1800cfbea  mov     rbp, rdx
0x1800cfbed  cmp     rdx, rax
0x1800cfbf0  jz      loc_1800CFD15
0x1800cfbf6  mov     rsi, [rsp+58h+arg_28]
0x1800cfbfe  test    rsi, rsi
0x1800cfc01  jz      short loc_1800CFC0A
0x1800cfc03  mov     qword ptr [rsi], 0
0x1800cfc0a  test    ecx, ecx
0x1800cfc0c  jnz     loc_1800CFD2D
0x1800cfc12  test    rbp, rbp
0x1800cfc15  jz      loc_1800CFD2D
0x1800cfc1b  cmp     edi, 10000h
0x1800cfc21  ja      loc_1800CFD2D
0x1800cfc27  test    rsi, rsi
0x1800cfc2a  jz      loc_1800CFD2D
0x1800cfc30  call    RtlpValidateActivationContextData
0x1800cfc35  mov     ebx, eax
0x1800cfc37  test    eax, eax
0x1800cfc39  js      loc_1800CFD05
0x1800cfc3f  mov     rcx, gs:60h
0x1800cfc48  lea     r8, [rdi+210h]
0x1800cfc4f  xor     edx, edx
0x1800cfc51  mov     rcx, [rcx+30h]
0x1800cfc55  call    RtlAllocateHeap_0
0x1800cfc5a  mov     r14, rax
0x1800cfc5d  test    rax, rax
0x1800cfc60  jz      loc_1800CFD34
0x1800cfc66  lea     rdi, [rax+8]
0x1800cfc6a  mov     qword ptr [rax], 674D6341h
0x1800cfc71  mov     eax, [rbp+18h]
0x1800cfc74  lea     rcx, [rdi+70h]
0x1800cfc78  xor     r8d, r8d
0x1800cfc7b  mov     edx, [rax+rbp+8]
0x1800cfc7f  cmp     edx, 20h ; ' '
0x1800cfc82  lea     rax, [rdi+80h]
0x1800cfc89  cmovbe  r8, rax
0x1800cfc8d  call    RtlpInitializeAssemblyStorageMap
0x1800cfc92  mov     ebx, eax
0x1800cfc94  test    eax, eax
0x1800cfc96  js      loc_1800CFD3B
0x1800cfc9c  mov     rax, [rsp+58h+arg_20]
0x1800cfca4  lea     rcx, [rdi+188h]; void *
0x1800cfcab  mov     [rdi+28h], rax
0x1800cfcaf  xorps   xmm0, xmm0
0x1800cfcb2  mov     qword ptr [rdi], 1
0x1800cfcb9  xorps   xmm1, xmm1
0x1800cfcbc  mov     [rdi+18h], rbp
0x1800cfcc0  xor     edx, edx; Val
0x1800cfcc2  mov     [rdi+20h], r15
0x1800cfcc6  mov     r8d, 80h; Size
0x1800cfccc  movups  xmmword ptr [r14+38h], xmm0
0x1800cfcd1  movups  xmmword ptr [r14+48h], xmm0
0x1800cfcd6  movups  xmmword ptr [r14+58h], xmm1
0x1800cfcdb  movups  xmmword ptr [r14+68h], xmm1
0x1800cfce0  call    memset$thunk$772440563353939046
0x1800cfce5  mov     dword ptr [rdi+180h], 0
0x1800cfcef  cmp     cs:g_SxsKeepActivationContextsAlive, 0
0x1800cfcf6  jz      short loc_1800CFD00
0x1800cfcf8  mov     rcx, rdi
0x1800cfcfb  call    RtlpPlaceActivationContextOnLiveList
0x1800cfd00  mov     [rsi], rdi
0x1800cfd03  xor     ebx, ebx
0x1800cfd05  mov     eax, ebx
0x1800cfd07  add     rsp, 28h
0x1800cfd0b  pop     r15
0x1800cfd0d  pop     r14
0x1800cfd0f  pop     rdi
0x1800cfd10  pop     rsi
0x1800cfd11  pop     rbp
0x1800cfd12  pop     rbx
0x1800cfd13  retn
0x1800cfd15  xor     edx, edx
0x1800cfd17  lea     r9, aRtlcreateactiv_0; "RtlCreateActivationContext"
0x1800cfd1e  lea     r8, aSxsSPassedTheE; "SXS: %s() passed the empty activation c"...
0x1800cfd25  lea     ecx, [rdx+33h]
0x1800cfd28  call    DbgPrintEx
0x1800cfd2d  mov     ebx, 0C000000Dh
0x1800cfd32  jmp     short loc_1800CFD05
0x1800cfd34  mov     ebx, 0C0000017h
0x1800cfd39  jmp     short loc_1800CFD05
0x1800cfd3b  mov     rcx, gs:60h
0x1800cfd44  mov     r8, r14
0x1800cfd47  xor     edx, edx
0x1800cfd49  mov     rcx, [rcx+30h]
0x1800cfd4d  call    RtlFreeHeap_0
0x1800cfd52  jmp     short loc_1800CFD05
```
