# McGenControlCallbackV2

- ea: `0x180008400`
- end: `0x1800084ff`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024f0`
- `0x180008400`

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
0x180008400  push    rbx
0x180008402  sub     rsp, 20h
0x180008406  mov     r10, [rsp+28h+CallbackContext]
0x18000840b  xor     ebx, ebx
0x18000840d  test    r10, r10
0x180008410  jz      loc_1800084F9
0x180008416  test    edx, edx
0x180008418  jz      loc_1800084BF
0x18000841e  cmp     edx, 1
0x180008421  jnz     loc_1800084F9
0x180008427  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000842c  mov     [r10+28h], r8b
0x180008430  mov     r8d, ebx
0x180008433  mov     [r10+18h], rax
0x180008437  mov     [r10+10h], r9
0x18000843b  mov     [r10+24h], edx
0x18000843f  cmp     bx, [r10+2Ah]
0x180008444  jnb     loc_1800084F9
0x18000844a  mov     rax, [r10+40h]
0x18000844e  mov     cl, [r10+28h]
0x180008452  mov     r9d, r8d
0x180008455  cmp     [r9+rax], cl
0x180008459  jbe     short loc_18000845F
0x18000845b  test    cl, cl
0x18000845d  jnz     short loc_18000847F
0x18000845f  mov     rax, [r10+38h]
0x180008463  mov     rcx, [rax+r9*8]
0x180008467  test    rcx, rcx
0x18000846a  jz      short loc_180008484
0x18000846c  test    [r10+10h], rcx
0x180008470  jz      short loc_18000847F
0x180008472  mov     rax, [r10+18h]
0x180008476  and     rax, rcx
0x180008479  cmp     rax, [r10+18h]
0x18000847d  jz      short loc_180008484
0x18000847f  mov     r11b, bl
0x180008482  jmp     short loc_180008487
0x180008484  mov     r11b, 1
0x180008487  mov     rax, [r10+30h]
0x18000848b  mov     ecx, r8d
0x18000848e  shr     r9, 5
0x180008492  mov     edx, 1
0x180008497  shl     edx, cl
0x180008499  lea     rcx, [rax+r9*4]
0x18000849d  test    r11b, r11b
0x1800084a0  jz      short loc_1800084A6
0x1800084a2  or      edx, [rcx]
0x1800084a4  jmp     short loc_1800084AA
0x1800084a6  not     edx
0x1800084a8  and     edx, [rcx]
0x1800084aa  mov     [rcx], edx
0x1800084ac  inc     r8d
0x1800084af  movzx   eax, word ptr [r10+2Ah]
0x1800084b4  cmp     r8d, eax
0x1800084b7  jb      short loc_18000844A
0x1800084b9  add     rsp, 20h
0x1800084bd  pop     rbx
0x1800084be  retn
0x1800084bf  mov     [r10+24h], ebx
0x1800084c3  mov     [r10+28h], bl
0x1800084c7  mov     [r10+10h], rbx
0x1800084cb  mov     [r10+18h], rbx
0x1800084cf  cmp     [r10+2Ah], bx
0x1800084d4  jbe     short loc_1800084F9
0x1800084d6  movzx   eax, word ptr [r10+2Ah]
0x1800084db  mov     ecx, 20h ; ' '
0x1800084e0  dec     eax
0x1800084e2  cdq
0x1800084e3  idiv    ecx
0x1800084e5  mov     rcx, [r10+30h]; void *
0x1800084e9  xor     edx, edx; Val
0x1800084eb  inc     eax
0x1800084ed  movsxd  r8, eax
0x1800084f0  shl     r8, 2; Size
0x1800084f4  call    memset_0
0x1800084f9  add     rsp, 20h
0x1800084fd  pop     rbx
0x1800084fe  retn
```
