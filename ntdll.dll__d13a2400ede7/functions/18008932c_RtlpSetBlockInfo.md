# RtlpSetBlockInfo

- ea: `0x18008932c`
- end: `0x180089485`
- name: `RtlpSetBlockInfo`
- size: `345`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180088be0`
- `0x180088d6c`
- `0x18008932c`

## callees

- `0x180007060`
- `0x18001b984`
- `0x18008932c`
- `0x1800894f0`

## string_xrefs

- `0x180089401`: `Not enough memory to complete\n`

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
0x18008932c  push    rbx
0x18008932e  push    rbp
0x18008932f  push    rsi
0x180089330  push    rdi
0x180089331  push    r14
0x180089333  push    r15
0x180089335  sub     rsp, 28h
0x180089339  mov     rbp, r9
0x18008933c  mov     rbx, rcx
0x18008933f  mov     rcx, [rcx+8]
0x180089343  lea     r9, [rdx+r8]
0x180089347  lea     rax, [r9-1]
0x18008934b  mov     r15, r8
0x18008934e  mov     rsi, rdx
0x180089351  cmp     rax, rcx
0x180089354  jb      loc_18008940D
0x18008935a  cmp     rdx, [rbx+10h]
0x18008935e  ja      loc_18008940D
0x180089364  cmp     rdx, rcx
0x180089367  jbe     loc_18008942C
0x18008936d  mov     rax, rdx
0x180089370  xor     edx, edx
0x180089372  sub     rax, rcx
0x180089375  div     qword ptr [rbx]
0x180089378  mov     rdi, rax
0x18008937b  sub     r9, rcx
0x18008937e  xor     edx, edx
0x180089380  lea     rax, [r9-1]
0x180089384  div     qword ptr [rbx]
0x180089387  mov     r14, rax
0x18008938a  mov     eax, 0FFh
0x18008938f  cmp     r14, rax
0x180089392  cmova   r14, rax
0x180089396  cmp     rdi, r14
0x180089399  ja      short loc_18008940D
0x18008939b  cmp     qword ptr [rbx], 1000h
0x1800893a2  jnz     short loc_1800893C3
0x1800893a4  test    rbp, rbp
0x1800893a7  jnz     short loc_18008941B
0x1800893a9  mov     rdx, rdi
0x1800893ac  mov     eax, edi
0x1800893ae  shr     rdx, 3
0x1800893b2  and     eax, 7
0x1800893b5  movsx   ecx, byte ptr [rdx+rbx+18h]
0x1800893ba  bts     ecx, eax
0x1800893bd  mov     [rdx+rbx+18h], cl
0x1800893c1  jmp     short loc_1800893DE
0x1800893c3  cmp     qword ptr [rbx+rdi*8+38h], 0
0x1800893c9  jz      short loc_1800893E3
0x1800893cb  mov     rcx, [rbx+rdi*8+38h]
0x1800893d0  mov     r9, rbp
0x1800893d3  mov     r8, r15
0x1800893d6  mov     rdx, rsi
0x1800893d9  call    RtlpSetBlockInfo
0x1800893de  inc     rdi
0x1800893e1  jmp     short loc_180089396
0x1800893e3  mov     rcx, cs:RtlpLeakHeap
0x1800893ea  xor     edx, edx
0x1800893ec  mov     r8d, 840h
0x1800893f2  call    RtlAllocateHeap_0
0x1800893f7  mov     [rbx+rdi*8+38h], rax
0x1800893fc  test    rax, rax
0x1800893ff  jnz     short loc_180089433
0x180089401  lea     rcx, aNotEnoughMemor; "Not enough memory to complete\n"
0x180089408  call    DbgPrint
0x18008940d  add     rsp, 28h
0x180089411  pop     r15
0x180089413  pop     r14
0x180089415  pop     rdi
0x180089416  pop     rsi
0x180089417  pop     rbp
0x180089418  pop     rbx
0x180089419  retn
0x18008941b  mov     rax, [rbx+rdi*8+38h]
0x180089420  test    rax, rax
0x180089423  jnz     short loc_180089472
0x180089425  mov     [rbx+rdi*8+38h], rbp
0x18008942a  jmp     short loc_1800893DE
0x18008942c  xor     edi, edi
0x18008942e  jmp     loc_18008937B
0x180089433  mov     rdx, rbx
0x180089436  mov     rcx, rax
0x180089439  call    RtlpInitializeMap
0x18008943e  mov     rax, [rbx+rdi*8+38h]
0x180089443  mov     rcx, rdi
0x180089446  imul    rcx, [rbx]
0x18008944a  add     rcx, [rbx+8]
0x18008944e  mov     [rax+8], rcx
0x180089452  lea     rcx, [rdi+1]
0x180089456  imul    rcx, [rbx]
0x18008945a  mov     rax, [rbx+8]
0x18008945e  dec     rax
0x180089461  add     rcx, rax
0x180089464  mov     rax, [rbx+rdi*8+38h]
0x180089469  mov     [rax+10h], rcx
0x18008946d  jmp     loc_1800893CB
0x180089472  cmp     rax, rbp
0x180089475  jz      short loc_180089425
0x180089477  lea     rcx, aError; "Error\n"
0x18008947e  call    DbgPrint
0x180089483  jmp     short loc_180089425
```
