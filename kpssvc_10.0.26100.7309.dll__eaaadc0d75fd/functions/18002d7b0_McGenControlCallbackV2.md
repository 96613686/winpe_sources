# McGenControlCallbackV2

- ea: `0x18002d7b0`
- end: `0x18002d8bc`
- name: `McGenControlCallbackV2`
- size: `268`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002d7b0`
- `0x18003100e`

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
  unsigned __int8 v8; // r9
  __int64 v9; // rdx
  bool v10; // r9
  int v11; // edx
  int *v12; // r11
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
          v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
          v10 = (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
             && (!v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3));
          v11 = 1 << (v7 & 0x1F);
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
0x18002d7b0  push    rbx
0x18002d7b2  sub     rsp, 20h
0x18002d7b6  mov     r10, [rsp+28h+CallbackContext]
0x18002d7bb  xor     ebx, ebx
0x18002d7bd  test    r10, r10
0x18002d7c0  jz      loc_18002D8B5
0x18002d7c6  test    edx, edx
0x18002d7c8  jz      loc_18002D87A
0x18002d7ce  cmp     edx, 1
0x18002d7d1  jnz     loc_18002D8B5
0x18002d7d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x18002d7dc  mov     [r10+28h], r8b
0x18002d7e0  mov     r8d, ebx
0x18002d7e3  mov     [r10+18h], rax
0x18002d7e7  mov     [r10+10h], r9
0x18002d7eb  mov     [r10+24h], edx
0x18002d7ef  cmp     bx, [r10+2Ah]
0x18002d7f4  jnb     loc_18002D8B5
0x18002d7fa  mov     rax, [r10+38h]
0x18002d7fe  mov     r9b, [r10+28h]
0x18002d802  mov     ecx, r8d
0x18002d805  mov     rdx, [rax+rcx*8]
0x18002d809  mov     rax, [r10+40h]
0x18002d80d  cmp     [rcx+rax], r9b
0x18002d811  jbe     short loc_18002D818
0x18002d813  test    r9b, r9b
0x18002d816  jnz     short loc_18002D830
0x18002d818  test    rdx, rdx
0x18002d81b  jz      short loc_18002D835
0x18002d81d  test    [r10+10h], rdx
0x18002d821  jz      short loc_18002D830
0x18002d823  mov     rax, [r10+18h]
0x18002d827  and     rax, rdx
0x18002d82a  cmp     rax, [r10+18h]
0x18002d82e  jz      short loc_18002D835
0x18002d830  mov     r9b, bl
0x18002d833  jmp     short loc_18002D838
0x18002d835  mov     r9b, 1
0x18002d838  mov     rax, [r10+30h]
0x18002d83c  mov     ecx, r8d
0x18002d83f  and     ecx, 1Fh
0x18002d842  mov     edx, 1
0x18002d847  shl     edx, cl
0x18002d849  mov     ecx, r8d
0x18002d84c  shr     rcx, 5
0x18002d850  lea     r11, [rax+rcx*4]
0x18002d854  test    r9b, r9b
0x18002d857  jz      short loc_18002D85E
0x18002d859  or      edx, [r11]
0x18002d85c  jmp     short loc_18002D863
0x18002d85e  not     edx
0x18002d860  and     edx, [r11]
0x18002d863  mov     [r11], edx
0x18002d866  inc     r8d
0x18002d869  movzx   eax, word ptr [r10+2Ah]
0x18002d86e  cmp     r8d, eax
0x18002d871  jb      short loc_18002D7FA
0x18002d873  add     rsp, 20h
0x18002d877  pop     rbx
0x18002d878  retn
0x18002d87a  mov     [r10+24h], ebx
0x18002d87e  mov     [r10+28h], bl
0x18002d882  mov     [r10+10h], rbx
0x18002d886  mov     [r10+18h], rbx
0x18002d88a  cmp     [r10+2Ah], bx
0x18002d88f  jbe     short loc_18002D8B5
0x18002d891  movzx   eax, word ptr [r10+2Ah]
0x18002d896  mov     rcx, [r10+30h]; void *
0x18002d89a  dec     eax
0x18002d89c  cdq
0x18002d89d  and     edx, 1Fh
0x18002d8a0  add     eax, edx
0x18002d8a2  xor     edx, edx; Val
0x18002d8a4  sar     eax, 5
0x18002d8a7  inc     eax
0x18002d8a9  movsxd  r8, eax
0x18002d8ac  shl     r8, 2; Size
0x18002d8b0  call    memset_0
0x18002d8b5  add     rsp, 20h
0x18002d8b9  pop     rbx
0x18002d8ba  retn
```
