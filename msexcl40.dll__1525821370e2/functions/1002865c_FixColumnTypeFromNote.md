# FixColumnTypeFromNote

- ea: `0x1002865c`
- end: `0x100286fb`
- name: `FixColumnTypeFromNote`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10028701`

## callees

- `0x10026b91`
- `0x1002865c`
- `0x10035510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100286b1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100286d7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100286b1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100286d7`

## string_xrefs

- `0x10028687`: `[Microsoft JET Created Table]`

## pseudocode

```c
int __fastcall FixColumnTypeFromNote(int a1, int *a2, int a3)
{
  int v5; // ecx
  int v6; // ebx
  int v7; // eax
  int v8; // edx
  int v9; // eax
  int v11; // [esp+Ch] [ebp-Ch] BYREF
  __int16 v12; // [esp+10h] [ebp-8h]
  __int16 v13; // [esp+12h] [ebp-6h]

  *a2 = 10;
  v5 = *(_DWORD *)(a1 + 92);
  if ( v5 )
  {
    if ( !strcmp2(v5, L"[Microsoft JET Created Table]") )
    {
      v6 = *(_DWORD *)(a1 + 92);
      v11 = *(_DWORD *)(v6 + 58);
      v12 = *(_WORD *)(v6 + 62);
      v13 = 0;
      v7 = __o__wtoi(&v11);
      v8 = HIWORD(a3) - *(unsigned __int16 *)(a1 + 98);
      if ( v8 < v7 )
      {
        v11 = *(_DWORD *)(v6 + 4 * v8 + 64);
        v12 = 0;
        v9 = __o__wtoi(&v11);
        if ( (unsigned int)(v9 - 1) <= 0x10 )
          *a2 = v9;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1002865c  mov     edi, edi
0x1002865e  push    ebp
0x1002865f  mov     ebp, esp
0x10028661  sub     esp, 10h
0x10028664  mov     eax, ___security_cookie
0x10028669  xor     eax, ebp
0x1002866b  mov     [ebp+var_4], eax
0x1002866e  mov     eax, [ebp+arg_0]
0x10028671  push    esi
0x10028672  push    edi
0x10028673  mov     esi, edx
0x10028675  mov     [ebp+var_10], eax
0x10028678  mov     edi, ecx
0x1002867a  mov     dword ptr [esi], 0Ah
0x10028680  mov     ecx, [edi+5Ch]
0x10028683  test    ecx, ecx
0x10028685  jz      short loc_100286E9
0x10028687  mov     edx, offset aMicrosoftJetCr; "[Microsoft JET Created Table]"
0x1002868c  call    strcmp2
0x10028691  test    eax, eax
0x10028693  jnz     short loc_100286E9
0x10028695  push    ebx
0x10028696  mov     ebx, [edi+5Ch]
0x10028699  mov     eax, [ebx+3Ah]
0x1002869c  mov     [ebp+var_C], eax
0x1002869f  mov     ax, [ebx+3Eh]
0x100286a3  mov     [ebp+var_8], ax
0x100286a7  xor     eax, eax
0x100286a9  mov     [ebp+var_6], ax
0x100286ad  lea     eax, [ebp+var_C]
0x100286b0  push    eax
0x100286b1  call    ds:__imp___o__wtoi
0x100286b7  movzx   edx, word ptr [ebp+var_10+2]
0x100286bb  pop     ecx
0x100286bc  movzx   ecx, word ptr [edi+62h]
0x100286c0  sub     edx, ecx
0x100286c2  cmp     edx, eax
0x100286c4  jge     short loc_100286E8
0x100286c6  mov     eax, [ebx+edx*4+40h]
0x100286ca  mov     [ebp+var_C], eax
0x100286cd  xor     eax, eax
0x100286cf  mov     [ebp+var_8], ax
0x100286d3  lea     eax, [ebp+var_C]
0x100286d6  push    eax
0x100286d7  call    ds:__imp___o__wtoi
0x100286dd  pop     ecx
0x100286de  lea     ecx, [eax-1]
0x100286e1  cmp     ecx, 10h
0x100286e4  ja      short loc_100286E8
0x100286e6  mov     [esi], eax
0x100286e8  pop     ebx
0x100286e9  mov     ecx, [ebp+var_4]
0x100286ec  xor     eax, eax
0x100286ee  pop     edi
0x100286ef  xor     ecx, ebp; StackCookie
0x100286f1  pop     esi
0x100286f2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100286f7  leave
0x100286f8  retn    4
```
