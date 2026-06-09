# McGenControlCallbackV2

- ea: `0x1400037a0`
- end: `0x14000389e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400037a0`
- `0x1400059c0`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x1400037a0  push    rbx
0x1400037a2  sub     rsp, 20h
0x1400037a6  mov     r10, [rsp+28h+CallbackContext]
0x1400037ab  xor     ebx, ebx
0x1400037ad  test    r10, r10
0x1400037b0  jz      loc_140003897
0x1400037b6  test    edx, edx
0x1400037b8  jz      loc_14000385F
0x1400037be  cmp     edx, 1
0x1400037c1  jnz     loc_140003897
0x1400037c7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400037cc  mov     [r10+28h], r8b
0x1400037d0  mov     r8d, ebx
0x1400037d3  mov     [r10+18h], rax
0x1400037d7  mov     [r10+10h], r9
0x1400037db  mov     [r10+24h], edx
0x1400037df  cmp     bx, [r10+2Ah]
0x1400037e4  jnb     loc_140003897
0x1400037ea  mov     rax, [r10+40h]
0x1400037ee  mov     cl, [r10+28h]
0x1400037f2  mov     r9d, r8d
0x1400037f5  cmp     [r9+rax], cl
0x1400037f9  jbe     short loc_1400037FF
0x1400037fb  test    cl, cl
0x1400037fd  jnz     short loc_140003821
0x1400037ff  mov     rax, [r10+38h]
0x140003803  mov     rdx, [rax+r9*8]
0x140003807  test    rdx, rdx
0x14000380a  jz      short loc_140003826
0x14000380c  test    [r10+10h], rdx
0x140003810  jz      short loc_140003821
0x140003812  mov     rcx, [r10+18h]
0x140003816  mov     rax, rcx
0x140003819  and     rax, rdx
0x14000381c  cmp     rax, rcx
0x14000381f  jz      short loc_140003826
0x140003821  mov     r11b, bl
0x140003824  jmp     short loc_140003829
0x140003826  mov     r11b, 1
0x140003829  mov     rax, [r10+30h]
0x14000382d  mov     ecx, r8d
0x140003830  shr     r9, 5
0x140003834  mov     edx, 1
0x140003839  shl     edx, cl
0x14000383b  lea     rcx, [rax+r9*4]
0x14000383f  mov     eax, [rcx]
0x140003841  test    r11b, r11b
0x140003844  jz      short loc_14000384A
0x140003846  or      edx, eax
0x140003848  jmp     short loc_14000384E
0x14000384a  not     edx
0x14000384c  and     edx, eax
0x14000384e  mov     [rcx], edx
0x140003850  inc     r8d
0x140003853  movzx   eax, word ptr [r10+2Ah]
0x140003858  cmp     r8d, eax
0x14000385b  jb      short loc_1400037EA
0x14000385d  jmp     short loc_140003897
0x14000385f  movzx   eax, word ptr [r10+2Ah]
0x140003864  mov     [r10+24h], ebx
0x140003868  mov     [r10+28h], bl
0x14000386c  mov     [r10+10h], rbx
0x140003870  mov     [r10+18h], rbx
0x140003874  test    ax, ax
0x140003877  jz      short loc_140003897
0x140003879  dec     eax
0x14000387b  mov     ecx, 20h ; ' '
0x140003880  cdq
0x140003881  idiv    ecx
0x140003883  mov     rcx, [r10+30h]; void *
0x140003887  xor     edx, edx; Val
0x140003889  inc     eax
0x14000388b  movsxd  r8, eax
0x14000388e  shl     r8, 2; Size
0x140003892  call    memset
0x140003897  add     rsp, 20h
0x14000389b  pop     rbx
0x14000389c  retn
```
