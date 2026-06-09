# resetAccumulator

- ea: `0x140044fe4`
- end: `0x1400450f2`
- name: `resetAccumulator`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14006cd0c`

## callees

- `0x140044fe4`
- `0x1400560c4`
- `0x140061d5c`
- `0x1400738a0`
- `0x140073ca8`
- `0x14007aa84`

## string_xrefs

- `0x1400450a2`: `USE TEMP B-TREE FOR %s(DISTINCT)`

## pseudocode

```c
void __fastcall resetAccumulator(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // r12
  __int64 v6; // rsi
  int i; // r15d
  _DWORD *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // r9

  v4 = *(_DWORD *)(a2 + 48) + *(_DWORD *)(a2 + 32);
  if ( v4 )
  {
    if ( !*(_DWORD *)(a1 + 48) )
    {
      v5 = *(_QWORD *)(a1 + 16);
      sqlite3VdbeAddOp3(v5, 75, 0, *(_DWORD *)(a2 + 12), v4 + *(_DWORD *)(a2 + 12) - 1);
      v6 = *(_QWORD *)(a2 + 40);
      for ( i = 0; i < *(_DWORD *)(a2 + 48); v6 += 24 )
      {
        if ( *(int *)(v6 + 16) >= 0 )
        {
          v8 = *(_DWORD **)(*(_QWORD *)v6 + 32LL);
          if ( v8 && *v8 == 1 )
          {
            v9 = sqlite3KeyInfoFromExprList(a1, v8, 0, 0);
            v10 = (unsigned int)sqlite3VdbeAddOp3(v5, 118, *(_DWORD *)(v6 + 16), 0, 0);
            sqlite3VdbeChangeP4(v5, v10, v9, 4294967288LL);
            v11 = *(_QWORD *)(v6 + 8);
            *(_DWORD *)(v6 + 20) = v10;
            sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s(DISTINCT)", *(const char **)(v11 + 56));
          }
          else
          {
            sqlite3ErrorMsg(a1, "DISTINCT aggregates must have exactly one argument");
            *(_DWORD *)(v6 + 16) = -1;
          }
        }
        ++i;
      }
    }
  }
}

```

## disassembly

```asm
0x140044fe4  push    rbx
0x140044fe6  push    rbp
0x140044fe7  push    rsi
0x140044fe8  push    rdi
0x140044fe9  push    r12
0x140044feb  push    r14
0x140044fed  push    r15
0x140044fef  sub     rsp, 30h
0x140044ff3  mov     r14, rcx
0x140044ff6  mov     rbp, rdx
0x140044ff9  mov     ecx, [rdx+20h]
0x140044ffc  add     ecx, [rdx+30h]
0x140044fff  jz      loc_1400450E3
0x140045005  cmp     dword ptr [r14+30h], 0
0x14004500a  jnz     loc_1400450E3
0x140045010  mov     r9d, [rdx+0Ch]
0x140045014  xor     r8d, r8d
0x140045017  mov     r12, [r14+10h]
0x14004501b  lea     eax, [r9-1]
0x14004501f  add     eax, ecx
0x140045021  lea     edx, [r8+4Bh]
0x140045025  mov     rcx, r12
0x140045028  mov     [rsp+68h+var_48], eax
0x14004502c  call    sqlite3VdbeAddOp3
0x140045031  mov     rsi, [rbp+28h]
0x140045035  xor     r15d, r15d
0x140045038  cmp     [rbp+30h], r15d
0x14004503c  jle     loc_1400450E3
0x140045042  cmp     dword ptr [rsi+10h], 0
0x140045046  jl      loc_1400450D2
0x14004504c  mov     rax, [rsi]
0x14004504f  mov     rdx, [rax+20h]
0x140045053  test    rdx, rdx
0x140045056  jz      short loc_1400450BC
0x140045058  cmp     dword ptr [rdx], 1
0x14004505b  jnz     short loc_1400450BC
0x14004505d  xor     r9d, r9d
0x140045060  xor     r8d, r8d
0x140045063  mov     rcx, r14
0x140045066  call    sqlite3KeyInfoFromExprList
0x14004506b  mov     r8d, [rsi+10h]
0x14004506f  xor     r9d, r9d
0x140045072  mov     rcx, r12
0x140045075  mov     [rsp+68h+var_48], 0
0x14004507d  mov     rdi, rax
0x140045080  lea     edx, [r9+76h]
0x140045084  call    sqlite3VdbeAddOp3
0x140045089  mov     r9d, 0FFFFFFF8h
0x14004508f  mov     r8, rdi
0x140045092  mov     edx, eax
0x140045094  mov     rcx, r12
0x140045097  mov     ebx, eax
0x140045099  call    sqlite3VdbeChangeP4
0x14004509e  mov     r9, [rsi+8]
0x1400450a2  lea     r8, aUseTempBTreeFo; "USE TEMP B-TREE FOR %s(DISTINCT)"
0x1400450a9  mov     [rsi+14h], ebx
0x1400450ac  xor     edx, edx
0x1400450ae  mov     rcx, r14
0x1400450b1  mov     r9, [r9+38h]
0x1400450b5  call    sqlite3VdbeExplain
0x1400450ba  jmp     short loc_1400450D2
0x1400450bc  lea     rdx, aDistinctAggreg; "DISTINCT aggregates must have exactly o"...
0x1400450c3  mov     rcx, r14
0x1400450c6  call    sqlite3ErrorMsg
0x1400450cb  mov     dword ptr [rsi+10h], 0FFFFFFFFh
0x1400450d2  inc     r15d
0x1400450d5  add     rsi, 18h
0x1400450d9  cmp     r15d, [rbp+30h]
0x1400450dd  jl      loc_140045042
0x1400450e3  add     rsp, 30h
0x1400450e7  pop     r15
0x1400450e9  pop     r14
0x1400450eb  pop     r12
0x1400450ed  pop     rdi
0x1400450ee  pop     rsi
0x1400450ef  pop     rbp
0x1400450f0  pop     rbx
0x1400450f1  retn
```
