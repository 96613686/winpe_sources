# DiscpParseCacheName

- ea: `0x18000fb28`
- end: `0x18000fbd4`
- name: `DiscpParseCacheName`
- size: `172`
- prototype: `__int64 __fastcall(_WORD *, _QWORD *, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f8e8`
- `0x18000fe70`

## callees

- `0x18000fb28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fb46`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fb46`
- `ISCSIUM!DiscpXtoI` at `0x18000fbbd`
- `ISCSIUM!DiscpXtoI` at `0x18000fbbd`

## pseudocode

```c
__int64 __fastcall DiscpParseCacheName(_WORD *a1, _QWORD *a2, _DWORD *a3, _QWORD *a4)
{
  _WORD *v7; // rbx
  _WORD *v8; // rbx
  unsigned int v9; // ecx
  __int64 v10; // rdx
  _WORD *v11; // r8
  _WORD *v13; // r9
  int v14; // eax
  bool v15; // zf

  v7 = a1;
  if ( (unsigned int)_o__wcsicmp(a1, L"All") )
  {
    v9 = 0;
    v10 = -1;
    do
      ++v10;
    while ( v7[v10] );
    *a2 = v7;
    if ( (_DWORD)v10 )
    {
      while ( 1 )
      {
        ++v9;
        v11 = v7 + 1;
        if ( *v7 == 32 )
          break;
        ++v7;
        if ( v9 >= (unsigned int)v10 )
          return 4026466358LL;
      }
      *v7 = 0;
      v13 = v7 + 1;
      while ( v9 < (unsigned int)v10 )
      {
        v8 = v11 + 1;
        if ( *v11 == 32 )
        {
          *v11 = 0;
          v14 = DiscpXtoI(v13);
          v15 = *v8 == 42;
          *a3 = v14;
          if ( v15 )
            v8 = 0;
          goto LABEL_16;
        }
        ++v11;
        ++v9;
      }
    }
    return 4026466358LL;
  }
  else
  {
    *a2 = 0;
    v8 = 0;
    *a3 = -1;
LABEL_16:
    *a4 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x18000fb28  push    rbx
0x18000fb2a  push    rbp
0x18000fb2b  push    rsi
0x18000fb2c  push    rdi
0x18000fb2d  push    r14
0x18000fb2f  sub     rsp, 20h
0x18000fb33  mov     rdi, rdx
0x18000fb36  mov     r14, r9
0x18000fb39  lea     rdx, aAll; "All"
0x18000fb40  mov     rsi, r8
0x18000fb43  mov     rbx, rcx
0x18000fb46  call    cs:__imp__o__wcsicmp
0x18000fb4c  xor     ebp, ebp
0x18000fb4e  test    eax, eax
0x18000fb50  jnz     short loc_18000FB5F
0x18000fb52  mov     [rdi], rbp
0x18000fb55  mov     ebx, ebp
0x18000fb57  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000fb5d  jmp     short loc_18000FBCD
0x18000fb5f  mov     ecx, ebp
0x18000fb61  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fb65  inc     rdx
0x18000fb68  cmp     [rbx+rdx*2], bp
0x18000fb6c  jnz     short loc_18000FB65
0x18000fb6e  mov     [rdi], rbx
0x18000fb71  test    edx, edx
0x18000fb73  jz      short loc_18000FB88
0x18000fb75  inc     ecx
0x18000fb77  lea     r8, [rbx+2]
0x18000fb7b  cmp     word ptr [rbx], 20h ; ' '
0x18000fb7f  jz      short loc_18000FB98
0x18000fb81  mov     rbx, r8
0x18000fb84  cmp     ecx, edx
0x18000fb86  jb      short loc_18000FB75
0x18000fb88  mov     eax, 0EFFF0036h
0x18000fb8d  add     rsp, 20h
0x18000fb91  pop     r14
0x18000fb93  pop     rdi
0x18000fb94  pop     rsi
0x18000fb95  pop     rbp
0x18000fb96  pop     rbx
0x18000fb97  retn
0x18000fb98  mov     [rbx], bp
0x18000fb9b  mov     r9, r8
0x18000fb9e  jmp     short loc_18000FBB0
0x18000fba0  cmp     word ptr [r8], 20h ; ' '
0x18000fba5  lea     rbx, [r8+2]
0x18000fba9  jz      short loc_18000FBB6
0x18000fbab  mov     r8, rbx
0x18000fbae  inc     ecx
0x18000fbb0  cmp     ecx, edx
0x18000fbb2  jb      short loc_18000FBA0
0x18000fbb4  jmp     short loc_18000FB88
0x18000fbb6  mov     rcx, r9
0x18000fbb9  mov     [r8], bp
0x18000fbbd  call    cs:__imp_DiscpXtoI
0x18000fbc3  cmp     word ptr [rbx], 2Ah ; '*'
0x18000fbc7  mov     [rsi], eax
0x18000fbc9  cmovz   rbx, rbp
0x18000fbcd  mov     [r14], rbx
0x18000fbd0  mov     eax, ebp
0x18000fbd2  jmp     short loc_18000FB8D
```
