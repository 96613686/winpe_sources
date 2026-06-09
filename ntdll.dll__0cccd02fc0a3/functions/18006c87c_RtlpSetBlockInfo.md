# RtlpSetBlockInfo

- ea: `0x18006c87c`
- end: `0x18006c9d5`
- name: `RtlpSetBlockInfo`
- size: `345`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006c130`
- `0x18006c2bc`
- `0x18006c87c`

## callees

- `0x180007060`
- `0x18001b984`
- `0x18006c87c`
- `0x18006ca40`

## string_xrefs

- `0x18006c951`: `Not enough memory to complete\n`

## pseudocode

```c
unsigned __int64 __fastcall RtlpSetBlockInfo(_QWORD *a1, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v6; // rcx
  unsigned __int64 result; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r14
  __int64 Heap_0; // rax

  v6 = a1[1];
  result = a2 + a3 - 1;
  if ( result >= v6 && a2 <= a1[2] )
  {
    if ( a2 <= v6 )
      v10 = 0;
    else
      v10 = (a2 - v6) / *a1;
    v11 = a2 + a3 - v6;
    v12 = (v11 - 1) % *a1;
    v13 = (v11 - 1) / *a1;
    result = 255;
    if ( v13 > 0xFF )
      v13 = 255;
    while ( v10 <= v13 )
    {
      if ( *a1 == 4096 )
      {
        if ( a4 )
        {
          result = a1[v10 + 7];
          if ( result )
          {
            if ( result != a4 )
              result = DbgPrint("Error\n", v12);
          }
          a1[v10 + 7] = a4;
        }
        else
        {
          v12 = v10 >> 3;
          result = v10 & 7;
          *((_BYTE *)a1 + (v10 >> 3) + 24) |= 1 << result;
        }
      }
      else
      {
        if ( !a1[v10 + 7] )
        {
          Heap_0 = RtlAllocateHeap_0(RtlpLeakHeap, 0, 2112);
          a1[v10 + 7] = Heap_0;
          if ( !Heap_0 )
            return DbgPrint("Not enough memory to complete\n");
          RtlpInitializeMap(Heap_0, a1);
          *(_QWORD *)(a1[v10 + 7] + 8LL) = a1[1] + *a1 * v10;
          *(_QWORD *)(a1[v10 + 7] + 16LL) = a1[1] - 1LL + *a1 * (v10 + 1);
        }
        result = RtlpSetBlockInfo(a1[v10 + 7], a2, a3, a4);
      }
      ++v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006c87c  push    rbx
0x18006c87e  push    rbp
0x18006c87f  push    rsi
0x18006c880  push    rdi
0x18006c881  push    r14
0x18006c883  push    r15
0x18006c885  sub     rsp, 28h
0x18006c889  mov     rbp, r9
0x18006c88c  mov     rbx, rcx
0x18006c88f  mov     rcx, [rcx+8]
0x18006c893  lea     r9, [rdx+r8]
0x18006c897  lea     rax, [r9-1]
0x18006c89b  mov     r15, r8
0x18006c89e  mov     rsi, rdx
0x18006c8a1  cmp     rax, rcx
0x18006c8a4  jb      loc_18006C95D
0x18006c8aa  cmp     rdx, [rbx+10h]
0x18006c8ae  ja      loc_18006C95D
0x18006c8b4  cmp     rdx, rcx
0x18006c8b7  jbe     loc_18006C97C
0x18006c8bd  mov     rax, rdx
0x18006c8c0  xor     edx, edx
0x18006c8c2  sub     rax, rcx
0x18006c8c5  div     qword ptr [rbx]
0x18006c8c8  mov     rdi, rax
0x18006c8cb  sub     r9, rcx
0x18006c8ce  xor     edx, edx
0x18006c8d0  lea     rax, [r9-1]
0x18006c8d4  div     qword ptr [rbx]
0x18006c8d7  mov     r14, rax
0x18006c8da  mov     eax, 0FFh
0x18006c8df  cmp     r14, rax
0x18006c8e2  cmova   r14, rax
0x18006c8e6  cmp     rdi, r14
0x18006c8e9  ja      short loc_18006C95D
0x18006c8eb  cmp     qword ptr [rbx], 1000h
0x18006c8f2  jnz     short loc_18006C913
0x18006c8f4  test    rbp, rbp
0x18006c8f7  jnz     short loc_18006C96B
0x18006c8f9  mov     rdx, rdi
0x18006c8fc  mov     eax, edi
0x18006c8fe  shr     rdx, 3
0x18006c902  and     eax, 7
0x18006c905  movsx   ecx, byte ptr [rdx+rbx+18h]
0x18006c90a  bts     ecx, eax
0x18006c90d  mov     [rdx+rbx+18h], cl
0x18006c911  jmp     short loc_18006C92E
0x18006c913  cmp     qword ptr [rbx+rdi*8+38h], 0
0x18006c919  jz      short loc_18006C933
0x18006c91b  mov     rcx, [rbx+rdi*8+38h]
0x18006c920  mov     r9, rbp
0x18006c923  mov     r8, r15
0x18006c926  mov     rdx, rsi
0x18006c929  call    RtlpSetBlockInfo
0x18006c92e  inc     rdi
0x18006c931  jmp     short loc_18006C8E6
0x18006c933  mov     rcx, cs:RtlpLeakHeap
0x18006c93a  xor     edx, edx
0x18006c93c  mov     r8d, 840h
0x18006c942  call    RtlAllocateHeap_0
0x18006c947  mov     [rbx+rdi*8+38h], rax
0x18006c94c  test    rax, rax
0x18006c94f  jnz     short loc_18006C983
0x18006c951  lea     rcx, aNotEnoughMemor; "Not enough memory to complete\n"
0x18006c958  call    DbgPrint
0x18006c95d  add     rsp, 28h
0x18006c961  pop     r15
0x18006c963  pop     r14
0x18006c965  pop     rdi
0x18006c966  pop     rsi
0x18006c967  pop     rbp
0x18006c968  pop     rbx
0x18006c969  retn
0x18006c96b  mov     rax, [rbx+rdi*8+38h]
0x18006c970  test    rax, rax
0x18006c973  jnz     short loc_18006C9C2
0x18006c975  mov     [rbx+rdi*8+38h], rbp
0x18006c97a  jmp     short loc_18006C92E
0x18006c97c  xor     edi, edi
0x18006c97e  jmp     loc_18006C8CB
0x18006c983  mov     rdx, rbx
0x18006c986  mov     rcx, rax
0x18006c989  call    RtlpInitializeMap
0x18006c98e  mov     rax, [rbx+rdi*8+38h]
0x18006c993  mov     rcx, rdi
0x18006c996  imul    rcx, [rbx]
0x18006c99a  add     rcx, [rbx+8]
0x18006c99e  mov     [rax+8], rcx
0x18006c9a2  lea     rcx, [rdi+1]
0x18006c9a6  imul    rcx, [rbx]
0x18006c9aa  mov     rax, [rbx+8]
0x18006c9ae  dec     rax
0x18006c9b1  add     rcx, rax
0x18006c9b4  mov     rax, [rbx+rdi*8+38h]
0x18006c9b9  mov     [rax+10h], rcx
0x18006c9bd  jmp     loc_18006C91B
0x18006c9c2  cmp     rax, rbp
0x18006c9c5  jz      short loc_18006C975
0x18006c9c7  lea     rcx, aError; "Error\n"
0x18006c9ce  call    DbgPrint
0x18006c9d3  jmp     short loc_18006C975
```
