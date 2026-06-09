# McGenControlCallbackV2

- ea: `0x14000d5b0`
- end: `0x14000d6b0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002c2c`
- `0x14000d5b0`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rcx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // edx

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          if ( v10 )
            v13 = *v12 | v11;
          else
            v13 = *v12 & ~v11;
          *v12 = v13;
        }
      }
    }
    else
    {
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( CallbackContext[21] )
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x14000d5b0  push    rbx
0x14000d5b2  sub     rsp, 20h
0x14000d5b6  mov     r10, [rsp+28h+CallbackContext]
0x14000d5bb  xor     ebx, ebx
0x14000d5bd  test    r10, r10
0x14000d5c0  jz      loc_14000D6AA
0x14000d5c6  test    edx, edx
0x14000d5c8  jz      loc_14000D66F
0x14000d5ce  cmp     edx, 1
0x14000d5d1  jnz     loc_14000D6AA
0x14000d5d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000d5dc  mov     [r10+28h], r8b
0x14000d5e0  mov     r8d, ebx
0x14000d5e3  mov     [r10+18h], rax
0x14000d5e7  mov     [r10+10h], r9
0x14000d5eb  mov     [r10+24h], edx
0x14000d5ef  cmp     bx, [r10+2Ah]
0x14000d5f4  jnb     loc_14000D6AA
0x14000d5fa  mov     rax, [r10+40h]
0x14000d5fe  mov     cl, [r10+28h]
0x14000d602  mov     r9d, r8d
0x14000d605  cmp     [r9+rax], cl
0x14000d609  jbe     short loc_14000D60F
0x14000d60b  test    cl, cl
0x14000d60d  jnz     short loc_14000D62F
0x14000d60f  mov     rax, [r10+38h]
0x14000d613  mov     rcx, [rax+r9*8]
0x14000d617  test    rcx, rcx
0x14000d61a  jz      short loc_14000D634
0x14000d61c  test    [r10+10h], rcx
0x14000d620  jz      short loc_14000D62F
0x14000d622  mov     rax, [r10+18h]
0x14000d626  and     rax, rcx
0x14000d629  cmp     rax, [r10+18h]
0x14000d62d  jz      short loc_14000D634
0x14000d62f  mov     r11b, bl
0x14000d632  jmp     short loc_14000D637
0x14000d634  mov     r11b, 1
0x14000d637  mov     rax, [r10+30h]
0x14000d63b  mov     ecx, r8d
0x14000d63e  shr     r9, 5
0x14000d642  mov     edx, 1
0x14000d647  shl     edx, cl
0x14000d649  lea     rcx, [rax+r9*4]
0x14000d64d  test    r11b, r11b
0x14000d650  jz      short loc_14000D656
0x14000d652  or      edx, [rcx]
0x14000d654  jmp     short loc_14000D65A
0x14000d656  not     edx
0x14000d658  and     edx, [rcx]
0x14000d65a  mov     [rcx], edx
0x14000d65c  inc     r8d
0x14000d65f  movzx   eax, word ptr [r10+2Ah]
0x14000d664  cmp     r8d, eax
0x14000d667  jb      short loc_14000D5FA
0x14000d669  add     rsp, 20h
0x14000d66d  pop     rbx
0x14000d66e  retn
0x14000d66f  mov     [r10+24h], ebx
0x14000d673  mov     [r10+28h], bl
0x14000d677  mov     [r10+10h], rbx
0x14000d67b  mov     [r10+18h], rbx
0x14000d67f  cmp     [r10+2Ah], bx
0x14000d684  jbe     short loc_14000D6AA
0x14000d686  movzx   eax, word ptr [r10+2Ah]
0x14000d68b  mov     rcx, [r10+30h]; void *
0x14000d68f  dec     eax
0x14000d691  cdq
0x14000d692  and     edx, 1Fh
0x14000d695  add     eax, edx
0x14000d697  xor     edx, edx; Val
0x14000d699  sar     eax, 5
0x14000d69c  inc     eax
0x14000d69e  movsxd  r8, eax
0x14000d6a1  shl     r8, 2; Size
0x14000d6a5  call    memset_0
0x14000d6aa  add     rsp, 20h
0x14000d6ae  pop     rbx
0x14000d6af  retn
```
