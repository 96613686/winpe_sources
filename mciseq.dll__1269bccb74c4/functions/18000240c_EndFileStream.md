# EndFileStream

- ea: `0x18000240c`
- end: `0x1800024c7`
- name: `EndFileStream`
- size: `187`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800025fc`
- `0x180002eac`

## callees

- `0x18000137c`
- `0x1800013fc`
- `0x18000240c`
- `0x1800024d0`
- `0x180005270`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000247b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000247b`

## pseudocode

```c
__int64 __fastcall EndFileStream(__int64 a1)
{
  DWORD_PTR v2; // rcx
  __int64 v3; // rax
  __int64 i; // rdi
  __int64 v5; // rsi
  void *v6; // rcx
  __int64 v7; // rdi

  if ( a1 )
  {
    EndStreamCycle(a1);
    v2 = *(_QWORD *)(a1 + 256);
    if ( v2 )
      midiSeqMessage(v2, 2u, 0, 0);
    v3 = *(unsigned int *)(a1 + 296);
    if ( (_DWORD)v3 != -1 )
    {
      for ( i = (qword_18000A628[2 * v3] + 16) & -(__int64)(qword_18000A628[2 * v3] != 0); i; i = v7 + 16 )
      {
        v5 = 0;
        do
        {
          v6 = *(void **)(i + 8 * v5 + 16);
          if ( !v6 )
            break;
          GlobalFree(v6);
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (int)v5 < 2 );
        v7 = *(_QWORD *)(i - 16);
        if ( !v7 )
          break;
      }
      List_Destroy(*(unsigned int *)(a1 + 296));
    }
    List_Deallocate((unsigned int)SeqStreamListHandle, a1);
  }
  return 0;
}

```

## disassembly

```asm
0x18000240c  mov     [rsp+arg_0], rbx
0x180002411  mov     [rsp+arg_8], rsi
0x180002416  push    rdi
0x180002417  sub     rsp, 20h
0x18000241b  mov     rbx, rcx
0x18000241e  test    rcx, rcx
0x180002421  jz      loc_1800024B5
0x180002427  call    EndStreamCycle
0x18000242c  mov     rcx, [rbx+100h]; dwUser
0x180002433  test    rcx, rcx
0x180002436  jz      short loc_180002447
0x180002438  xor     r9d, r9d
0x18000243b  xor     r8d, r8d
0x18000243e  lea     edx, [r9+2]
0x180002442  call    midiSeqMessage
0x180002447  mov     eax, [rbx+128h]
0x18000244d  cmp     eax, 0FFFFFFFFh
0x180002450  jz      short loc_1800024A7
0x180002452  add     rax, rax
0x180002455  lea     rcx, qword_18000A628
0x18000245c  mov     rcx, [rcx+rax*8]
0x180002460  lea     rax, [rcx+10h]
0x180002464  neg     rcx
0x180002467  sbb     rdi, rdi
0x18000246a  and     rdi, rax
0x18000246d  jz      short loc_18000249C
0x18000246f  xor     esi, esi
0x180002471  mov     rcx, [rdi+rsi*8+10h]; hMem
0x180002476  test    rcx, rcx
0x180002479  jz      short loc_180002488
0x18000247b  call    cs:__imp_GlobalFree
0x180002481  inc     esi
0x180002483  cmp     esi, 2
0x180002486  jl      short loc_180002471
0x180002488  test    rdi, rdi
0x18000248b  jz      short loc_18000249C
0x18000248d  mov     rdi, [rdi-10h]
0x180002491  test    rdi, rdi
0x180002494  jz      short loc_18000249C
0x180002496  add     rdi, 10h
0x18000249a  jnz     short loc_18000246F
0x18000249c  mov     ecx, [rbx+128h]
0x1800024a2  call    List_Destroy
0x1800024a7  mov     ecx, cs:SeqStreamListHandle
0x1800024ad  mov     rdx, rbx
0x1800024b0  call    List_Deallocate
0x1800024b5  mov     rbx, [rsp+28h+arg_0]
0x1800024ba  xor     eax, eax
0x1800024bc  mov     rsi, [rsp+28h+arg_8]
0x1800024c1  add     rsp, 20h
0x1800024c5  pop     rdi
0x1800024c6  retn
```
