# tcompFromSession

- ea: `0x1400084d8`
- end: `0x140008617`
- name: `tcompFromSession`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000488c`
- `0x140007e18`

## callees

- `0x140001b04`
- `0x140001b84`
- `0x140001c80`
- `0x1400084d8`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!atoi` at `0x140008510`
- `msvcrt!atoi` at `0x140008510`

## string_xrefs

- `0x1400084f4`: `Compress`
- `0x140008522`: `CompressionType`
- `0x14000859d`: `CompressionLevel`
- `0x14000856a`: `CompressionMemory`
- `0x1400085c8`: `CompressionMemory`

## pseudocode

```c
__int64 __fastcall tcompFromSession(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  const char *v5; // rcx
  __int64 v6; // rax
  char *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v11; // rax
  const char *v12; // rcx
  __int64 v13; // rax
  const char *v14; // rcx
  int v15; // esi
  __int64 v16; // rax
  const char *v17; // rcx

  v4 = VarFind(*(_QWORD *)(a1 + 16), "Compress", a2);
  v5 = "On";
  if ( v4 )
    v5 = *(const char **)(v4 + 8);
  if ( !atoi(v5) )
    return 0;
  v6 = VarFind(*(_QWORD *)(a1 + 16), "CompressionType", a2);
  v7 = "MSZIP";
  if ( v6 )
    v7 = *(char **)(v6 + 8);
  v8 = CompTypeFromPSZ(v7) - 1;
  if ( !v8 )
    return 1;
  v9 = v8 - 1;
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      v11 = VarFind(*(_QWORD *)(a1 + 16), "CompressionMemory", a2);
      v12 = "18";
      if ( v11 )
        v12 = *(const char **)(v11 + 8);
      return ((unsigned int)CompMemoryFromPSZ(v12, a2) << 8) | 3;
    }
    else
    {
      return 15;
    }
  }
  else
  {
    v13 = VarFind(*(_QWORD *)(a1 + 16), "CompressionLevel", a2);
    v14 = "2";
    if ( v13 )
      v14 = *(const char **)(v13 + 8);
    v15 = CompLevelFromPSZ(v14, a2);
    v16 = VarFind(*(_QWORD *)(a1 + 16), "CompressionMemory", a2);
    v17 = "18";
    if ( v16 )
      v17 = *(const char **)(v16 + 8);
    return (16 * (v15 | (16 * (unsigned int)CompMemoryFromPSZ(v17, a2)))) | 2;
  }
}

```

## disassembly

```asm
0x1400084d8  mov     [rsp+arg_0], rbx
0x1400084dd  mov     [rsp+arg_8], rsi
0x1400084e2  push    rdi
0x1400084e3  sub     rsp, 20h
0x1400084e7  mov     rbx, rdx
0x1400084ea  mov     rdi, rcx
0x1400084ed  mov     rcx, [rcx+10h]
0x1400084f1  mov     r8, rdx
0x1400084f4  lea     rdx, aCompress; "Compress"
0x1400084fb  call    VarFind
0x140008500  lea     rcx, aOn; "On"
0x140008507  test    rax, rax
0x14000850a  jz      short loc_140008510
0x14000850c  mov     rcx, [rax+8]; String
0x140008510  call    cs:__imp_atoi
0x140008516  test    eax, eax
0x140008518  jz      loc_140008605
0x14000851e  mov     rcx, [rdi+10h]
0x140008522  lea     rdx, aCompressiontyp; "CompressionType"
0x140008529  mov     r8, rbx
0x14000852c  call    VarFind
0x140008531  lea     rcx, aMszip; "MSZIP"
0x140008538  test    rax, rax
0x14000853b  jz      short loc_140008541
0x14000853d  mov     rcx, [rax+8]; String1
0x140008541  mov     rdx, rbx
0x140008544  call    CompTypeFromPSZ
0x140008549  sub     eax, 1
0x14000854c  jz      loc_1400085FE
0x140008552  sub     eax, 1
0x140008555  jz      short loc_140008599
0x140008557  cmp     eax, 1
0x14000855a  jz      short loc_140008566
0x14000855c  mov     eax, 0Fh
0x140008561  jmp     loc_140008607
0x140008566  mov     rcx, [rdi+10h]
0x14000856a  lea     rdx, aCompressionmem; "CompressionMemory"
0x140008571  mov     r8, rbx
0x140008574  call    VarFind
0x140008579  lea     rcx, a18; "18"
0x140008580  test    rax, rax
0x140008583  jz      short loc_140008589
0x140008585  mov     rcx, [rax+8]
0x140008589  mov     rdx, rbx
0x14000858c  call    CompMemoryFromPSZ
0x140008591  shl     eax, 8
0x140008594  or      eax, 3
0x140008597  jmp     short loc_140008607
0x140008599  mov     rcx, [rdi+10h]
0x14000859d  lea     rdx, aCompressionlev; "CompressionLevel"
0x1400085a4  mov     r8, rbx
0x1400085a7  call    VarFind
0x1400085ac  lea     rcx, a2; "2"
0x1400085b3  test    rax, rax
0x1400085b6  jz      short loc_1400085BC
0x1400085b8  mov     rcx, [rax+8]
0x1400085bc  mov     rdx, rbx
0x1400085bf  call    CompLevelFromPSZ
0x1400085c4  mov     rcx, [rdi+10h]
0x1400085c8  lea     rdx, aCompressionmem; "CompressionMemory"
0x1400085cf  mov     r8, rbx
0x1400085d2  mov     esi, eax
0x1400085d4  call    VarFind
0x1400085d9  lea     rcx, a18; "18"
0x1400085e0  test    rax, rax
0x1400085e3  jz      short loc_1400085E9
0x1400085e5  mov     rcx, [rax+8]
0x1400085e9  mov     rdx, rbx
0x1400085ec  call    CompMemoryFromPSZ
0x1400085f1  shl     eax, 4
0x1400085f4  or      eax, esi
0x1400085f6  shl     eax, 4
0x1400085f9  or      eax, 2
0x1400085fc  jmp     short loc_140008607
0x1400085fe  mov     eax, 1
0x140008603  jmp     short loc_140008607
0x140008605  xor     eax, eax
0x140008607  mov     rbx, [rsp+28h+arg_0]
0x14000860c  mov     rsi, [rsp+28h+arg_8]
0x140008611  add     rsp, 20h
0x140008615  pop     rdi
0x140008616  retn
```
