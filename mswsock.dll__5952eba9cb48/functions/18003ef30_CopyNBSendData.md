# CopyNBSendData

- ea: `0x18003ef30`
- end: `0x18003f150`
- name: `CopyNBSendData`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800411a8`

## callees

- `0x180024720`
- `0x180024dd4`
- `0x18003ef30`
- `0x18003f28c`
- `0x180047b18`
- `0x18004f0d0`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003f003`
- `ntdll!RtlFreeHeap` at `0x18003f0c4`
- `ntdll!RtlFreeHeap` at `0x18003f003`
- `ntdll!RtlFreeHeap` at `0x18003f0c4`

## pseudocode

```c
__int64 __fastcall CopyNBSendData(__int64 *a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 result; // rax
  __int64 v6; // rbp
  __int64 WsaBufArray; // r14
  __int64 *v8; // rdi
  __int64 *i; // rax
  __int64 *v10; // rcx
  __int64 **v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // r8
  __int64 v14; // rax
  HANDLE v15; // rcx
  __int64 HeapRoutine; // rax
  __int64 v17; // rcx
  char *v18; // r8
  _QWORD *v19; // rcx
  char *v20; // rax
  __int64 v21; // rdx
  bool v22; // al

  v2 = *a1;
  if ( *((_DWORD *)a1 + 32) < *(_DWORD *)(*a1 + 64) )
  {
    v6 = *(int *)(a2 + 80);
    WsaBufArray = GetWsaBufArray(a1, 1);
    if ( !WsaBufArray )
      return 10055;
    if ( (unsigned int)UseRdma((unsigned int)v6) )
    {
      v8 = a1 + 112;
      for ( i = (__int64 *)a1[112]; i != v8; i = (__int64 *)*i )
      {
        v10 = (__int64 *)*i;
        if ( *((_DWORD *)i + 4) >= (int)v6 )
        {
          if ( (__int64 *)v10[1] == i )
          {
            v11 = (__int64 **)i[1];
            if ( *v11 == i )
            {
              *v11 = v10;
              v12 = (__int64)(i + 3);
              v10[1] = (__int64)v11;
              goto LABEL_20;
            }
          }
LABEL_25:
          __fastfail(3u);
        }
      }
      while ( 1 )
      {
        v13 = (_QWORD *)*v8;
        if ( (__int64 *)*v8 == v8 )
          break;
        if ( (__int64 *)v13[1] != v8 )
          goto LABEL_25;
        v14 = *v13;
        if ( *(_QWORD **)(*v13 + 8LL) != v13 )
          goto LABEL_25;
        v15 = SockPrivateHeap;
        *v8 = v14;
        *(_QWORD *)(v14 + 8) = v8;
        RtlFreeHeap(v15, 0, v13);
      }
      HeapRoutine = SockAllocateHeapRoutine(SockPrivateHeap, 0, (unsigned int)v6 + 24LL);
      v17 = HeapRoutine + 24;
      *(_DWORD *)(HeapRoutine + 16) = v6;
      *(_QWORD *)(WsaBufArray + 8) = HeapRoutine + 24;
    }
    else
    {
      v12 = SockAllocateHeapRoutine(SockPrivateHeap, 0, v6);
      v8 = a1 + 112;
LABEL_20:
      *(_QWORD *)(WsaBufArray + 8) = v12;
      v17 = v12;
    }
    *(_DWORD *)WsaBufArray = v6;
    if ( v17 )
    {
      if ( (unsigned int)CopyFromUserBuffer(v17, WsaBufArray, *(_QWORD *)(a2 + 48), *(_DWORD *)(a2 + 56), 0) )
      {
        if ( (unsigned int)UseRdma((unsigned int)v6) )
        {
          v19 = (_QWORD *)*v8;
          if ( *(__int64 **)(*v8 + 8) != v8 )
            goto LABEL_25;
          v20 = v18 - 24;
          *(_QWORD *)v20 = v19;
          *((_QWORD *)v20 + 1) = v8;
          v19[1] = v18 - 24;
          *v8 = (__int64)(v18 - 24);
        }
        else
        {
          RtlFreeHeap(SockPrivateHeap, 0, v18);
        }
        ReleaseWsaBufArray(a1, WsaBufArray);
        return 10014;
      }
      else
      {
        *((_DWORD *)a1 + 32) += v6;
        v21 = *(_QWORD *)(a2 + 48);
        if ( v21 )
          ReleaseWsaBufArray(a1, v21);
        *(_QWORD *)(a2 + 64) = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_QWORD *)(a2 + 48) = WsaBufArray;
        *(_DWORD *)(a2 + 56) = 1;
        *(_QWORD *)(a2 + 84) = 0;
        v22 = (*(_BYTE *)(v2 + 68) & 0x40) != 0;
        *(_BYTE *)(a2 + 131) = 0;
        *(_BYTE *)(a2 + 128) = v22;
        result = 0;
        *(_BYTE *)(a2 + 129) = 1;
      }
    }
    else
    {
      return 10055;
    }
  }
  else
  {
    if ( (*(_BYTE *)(v2 + 68) & 0x40) != 0 )
      NotifyAfdOfSendNotAvail();
    return 10035;
  }
  return result;
}

```

## disassembly

```asm
0x18003ef30  push    rbx
0x18003ef32  push    rbp
0x18003ef33  push    rsi
0x18003ef34  push    rdi
0x18003ef35  push    r14
0x18003ef37  push    r15
0x18003ef39  sub     rsp, 38h
0x18003ef3d  mov     r15, [rcx]
0x18003ef40  mov     rbx, rdx
0x18003ef43  mov     rsi, rcx
0x18003ef46  mov     eax, [r15+40h]
0x18003ef4a  cmp     [rcx+80h], eax
0x18003ef50  jb      short loc_18003EF68
0x18003ef52  test    byte ptr [r15+44h], 40h
0x18003ef57  jz      short loc_18003EF5E
0x18003ef59  call    NotifyAfdOfSendNotAvail
0x18003ef5e  mov     eax, 2733h
0x18003ef63  jmp     loc_18003F142
0x18003ef68  movsxd  rbp, dword ptr [rdx+50h]
0x18003ef6c  mov     edx, 1
0x18003ef71  call    GetWsaBufArray
0x18003ef76  mov     r14, rax
0x18003ef79  test    rax, rax
0x18003ef7c  jz      loc_18003F13D
0x18003ef82  mov     ecx, ebp
0x18003ef84  call    UseRdma
0x18003ef89  test    eax, eax
0x18003ef8b  jz      loc_18003F03A
0x18003ef91  lea     rdi, [rsi+380h]
0x18003ef98  mov     rax, [rdi]
0x18003ef9b  cmp     rax, rdi
0x18003ef9e  jz      short loc_18003EFD4
0x18003efa0  mov     rcx, [rax]
0x18003efa3  cmp     [rax+10h], ebp
0x18003efa6  jge     short loc_18003EFAD
0x18003efa8  mov     rax, rcx
0x18003efab  jmp     short loc_18003EF9B
0x18003efad  cmp     [rcx+8], rax
0x18003efb1  jnz     loc_18003F0A0
0x18003efb7  mov     rdx, [rax+8]
0x18003efbb  cmp     [rdx], rax
0x18003efbe  jnz     loc_18003F0A0
0x18003efc4  mov     [rdx], rcx
0x18003efc7  add     rax, 18h
0x18003efcb  mov     [rcx+8], rdx
0x18003efcf  jmp     loc_18003F059
0x18003efd4  mov     r8, [rdi]; P
0x18003efd7  cmp     r8, rdi
0x18003efda  jz      short loc_18003F011
0x18003efdc  cmp     [r8+8], rdi
0x18003efe0  jnz     loc_18003F0A0
0x18003efe6  mov     rax, [r8]
0x18003efe9  cmp     [rax+8], r8
0x18003efed  jnz     loc_18003F0A0
0x18003eff3  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003effa  xor     edx, edx; Flags
0x18003effc  mov     [rdi], rax
0x18003efff  mov     [rax+8], rdi
0x18003f003  call    cs:__imp_RtlFreeHeap
0x18003f00a  nop     dword ptr [rax+rax+00h]
0x18003f00f  jmp     short loc_18003EFD4
0x18003f011  mov     rcx, cs:SockPrivateHeap
0x18003f018  xor     edx, edx
0x18003f01a  mov     rax, cs:SockAllocateHeapRoutine
0x18003f021  mov     r8d, ebp
0x18003f024  add     r8, 18h
0x18003f028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f02d  lea     rcx, [rax+18h]
0x18003f031  mov     [rax+10h], ebp
0x18003f034  mov     [r14+8], rcx
0x18003f038  jmp     short loc_18003F060
0x18003f03a  mov     rcx, cs:SockPrivateHeap
0x18003f041  mov     r8, rbp
0x18003f044  mov     rax, cs:SockAllocateHeapRoutine
0x18003f04b  xor     edx, edx
0x18003f04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f052  lea     rdi, [rsi+380h]
0x18003f059  mov     [r14+8], rax
0x18003f05d  mov     rcx, rax
0x18003f060  mov     [r14], ebp
0x18003f063  test    rcx, rcx
0x18003f066  jz      loc_18003F13D
0x18003f06c  mov     r9d, [rbx+38h]
0x18003f070  mov     rdx, r14
0x18003f073  mov     r8, [rbx+30h]
0x18003f077  mov     [rsp+68h+var_48], 0
0x18003f07f  call    CopyFromUserBuffer
0x18003f084  test    eax, eax
0x18003f086  jz      short loc_18003F0E2
0x18003f088  mov     r8, [r14+8]
0x18003f08c  mov     ecx, ebp
0x18003f08e  call    UseRdma
0x18003f093  test    eax, eax
0x18003f095  jz      short loc_18003F0BB
0x18003f097  mov     rcx, [rdi]
0x18003f09a  cmp     [rcx+8], rdi
0x18003f09e  jz      short loc_18003F0A7
0x18003f0a0  mov     ecx, 3
0x18003f0a5  int     29h; Win8: RtlFailFast(ecx)
0x18003f0a7  lea     rax, [r8-18h]
0x18003f0ab  mov     [rax], rcx
0x18003f0ae  mov     [rax+8], rdi
0x18003f0b2  mov     [rcx+8], rax
0x18003f0b6  mov     [rdi], rax
0x18003f0b9  jmp     short loc_18003F0D0
0x18003f0bb  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003f0c2  xor     edx, edx; Flags
0x18003f0c4  call    cs:__imp_RtlFreeHeap
0x18003f0cb  nop     dword ptr [rax+rax+00h]
0x18003f0d0  mov     rdx, r14
0x18003f0d3  mov     rcx, rsi
0x18003f0d6  call    ReleaseWsaBufArray
0x18003f0db  mov     eax, 271Eh
0x18003f0e0  jmp     short loc_18003F142
0x18003f0e2  add     [rsi+80h], ebp
0x18003f0e8  mov     rdx, [rbx+30h]
0x18003f0ec  test    rdx, rdx
0x18003f0ef  jz      short loc_18003F0F9
0x18003f0f1  mov     rcx, rsi
0x18003f0f4  call    ReleaseWsaBufArray
0x18003f0f9  mov     qword ptr [rbx+40h], 0
0x18003f101  mov     qword ptr [rbx+8], 0
0x18003f109  mov     [rbx+30h], r14
0x18003f10d  mov     dword ptr [rbx+38h], 1
0x18003f114  mov     qword ptr [rbx+54h], 0
0x18003f11c  mov     al, [r15+44h]
0x18003f120  shr     al, 6
0x18003f123  and     al, 1
0x18003f125  mov     byte ptr [rbx+83h], 0
0x18003f12c  mov     [rbx+80h], al
0x18003f132  xor     eax, eax
0x18003f134  mov     byte ptr [rbx+81h], 1
0x18003f13b  jmp     short loc_18003F142
0x18003f13d  mov     eax, 2747h
0x18003f142  add     rsp, 38h
0x18003f146  pop     r15
0x18003f148  pop     r14
0x18003f14a  pop     rdi
0x18003f14b  pop     rsi
0x18003f14c  pop     rbp
0x18003f14d  pop     rbx
0x18003f14e  retn
```
