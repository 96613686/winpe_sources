# FillInIsdnParams

- ea: `0x180010ff4`
- end: `0x18001117b`
- name: `FillInIsdnParams`
- size: `391`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014f2c`

## callees

- `0x180010ff4`

## import_xrefs

- `msvcrt!_stricmp` at `0x18001102d`
- `msvcrt!_stricmp` at `0x18001104b`
- `msvcrt!_stricmp` at `0x180011066`
- `msvcrt!_stricmp` at `0x180011081`
- `msvcrt!_stricmp` at `0x18001109c`
- `msvcrt!_stricmp` at `0x1800110b7`
- `msvcrt!_stricmp` at `0x18001102d`
- `msvcrt!_stricmp` at `0x18001104b`
- `msvcrt!_stricmp` at `0x180011066`
- `msvcrt!_stricmp` at `0x180011081`
- `msvcrt!_stricmp` at `0x18001109c`
- `msvcrt!_stricmp` at `0x1800110b7`

## string_xrefs

- `0x18001105c`: `EnableCompression`

## pseudocode

```c
__int64 __fastcall FillInIsdnParams(__int64 a1, _DWORD *a2)
{
  unsigned __int16 v2; // bp
  const char *v3; // rbx
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // rax
  _BYTE *v9; // rcx
  unsigned __int64 v10; // rax
  _BYTE *v11; // r8
  __int64 v12; // rdx
  _BYTE *v13; // rax
  const char *v14; // rax
  _BYTE *v15; // rcx
  _BYTE *v16; // rax

  v2 = 0;
  v3 = (const char *)(a2 + 2);
  v6 = 2147483646;
  v7 = 100;
  if ( *a2 )
  {
    while ( 1 )
    {
      if ( !_stricmp(v3, "LineType") )
      {
        v8 = 460;
      }
      else if ( !_stricmp(v3, "Fallback") )
      {
        v8 = 560;
      }
      else if ( !_stricmp(v3, "EnableCompression") )
      {
        v8 = 660;
      }
      else if ( !_stricmp(v3, "ChannelAggregation") )
      {
        v8 = 760;
      }
      else if ( !_stricmp(v3, "PhoneNumber") )
      {
        v8 = 260;
      }
      else
      {
        if ( _stricmp(v3, "ConnectBps") )
          return 604;
        v8 = 360;
      }
      if ( *((_DWORD *)v3 + 8) != 1 )
        return 604;
      v9 = (_BYTE *)(v8 + a1);
      v10 = *((unsigned int *)v3 + 10);
      if ( v10 <= 0x7FFFFFFE )
      {
        v11 = (_BYTE *)*((_QWORD *)v3 + 6);
        v12 = 100;
        do
        {
          if ( !v10 )
            break;
          if ( !*v11 )
            break;
          *v9++ = *v11++;
          --v10;
          --v12;
        }
        while ( v12 );
        v13 = v9 - 1;
        if ( v12 )
          v13 = v9;
        *v13 = 0;
      }
      else
      {
        *v9 = 0;
      }
      ++v2;
      v3 += 56;
      if ( (unsigned int)v2 >= *a2 )
        goto LABEL_25;
    }
  }
  else
  {
LABEL_25:
    v14 = "64000";
    v15 = (_BYTE *)(a1 + 360);
    do
    {
      if ( !v6 )
        break;
      if ( !*v14 )
        break;
      *v15++ = *v14++;
      --v6;
      --v7;
    }
    while ( v7 );
    v16 = v15 - 1;
    if ( v7 )
      v16 = v15;
    *v16 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180010ff4  push    rbx
0x180010ff6  push    rbp
0x180010ff7  push    rsi
0x180010ff8  push    rdi
0x180010ff9  push    r13
0x180010ffb  push    r14
0x180010ffd  push    r15
0x180010fff  sub     rsp, 20h
0x180011003  xor     ebp, ebp
0x180011005  lea     rbx, [rdx+8]
0x180011009  mov     r14, rdx
0x18001100c  mov     r15, rcx
0x18001100f  mov     esi, 7FFFFFFEh
0x180011014  lea     edi, [rbp+64h]
0x180011017  lea     r13d, [rbp+1]
0x18001101b  cmp     [rdx], ebp
0x18001101d  jbe     loc_18001112C
0x180011023  lea     rdx, aLinetype; "LineType"
0x18001102a  mov     rcx, rbx; String1
0x18001102d  call    cs:__imp__stricmp
0x180011033  test    eax, eax
0x180011035  jnz     short loc_180011041
0x180011037  mov     eax, 1CCh
0x18001103c  jmp     loc_1800110CA
0x180011041  lea     rdx, aFallback; "Fallback"
0x180011048  mov     rcx, rbx; String1
0x18001104b  call    cs:__imp__stricmp
0x180011051  test    eax, eax
0x180011053  jnz     short loc_18001105C
0x180011055  mov     eax, 230h
0x18001105a  jmp     short loc_1800110CA
0x18001105c  lea     rdx, aEnablecompress; "EnableCompression"
0x180011063  mov     rcx, rbx; String1
0x180011066  call    cs:__imp__stricmp
0x18001106c  test    eax, eax
0x18001106e  jnz     short loc_180011077
0x180011070  mov     eax, 294h
0x180011075  jmp     short loc_1800110CA
0x180011077  lea     rdx, aChannelaggrega; "ChannelAggregation"
0x18001107e  mov     rcx, rbx; String1
0x180011081  call    cs:__imp__stricmp
0x180011087  test    eax, eax
0x180011089  jnz     short loc_180011092
0x18001108b  mov     eax, 2F8h
0x180011090  jmp     short loc_1800110CA
0x180011092  lea     rdx, aPhonenumber; "PhoneNumber"
0x180011099  mov     rcx, rbx; String1
0x18001109c  call    cs:__imp__stricmp
0x1800110a2  test    eax, eax
0x1800110a4  jnz     short loc_1800110AD
0x1800110a6  mov     eax, 104h
0x1800110ab  jmp     short loc_1800110CA
0x1800110ad  lea     rdx, aConnectbps; "ConnectBps"
0x1800110b4  mov     rcx, rbx; String1
0x1800110b7  call    cs:__imp__stricmp
0x1800110bd  test    eax, eax
0x1800110bf  jnz     loc_180011174
0x1800110c5  mov     eax, 168h
0x1800110ca  cmp     [rbx+20h], r13d
0x1800110ce  jnz     loc_180011174
0x1800110d4  lea     rcx, [rax+r15]
0x1800110d8  mov     eax, [rbx+28h]
0x1800110db  cmp     rax, rsi
0x1800110de  jbe     short loc_1800110E5
0x1800110e0  mov     byte ptr [rcx], 0
0x1800110e3  jmp     short loc_180011118
0x1800110e5  mov     r8, [rbx+30h]
0x1800110e9  mov     rdx, rdi
0x1800110ec  test    rax, rax
0x1800110ef  jz      short loc_18001110A
0x1800110f1  mov     r9b, [r8]
0x1800110f4  test    r9b, r9b
0x1800110f7  jz      short loc_18001110A
0x1800110f9  mov     [rcx], r9b
0x1800110fc  add     r8, r13
0x1800110ff  add     rcx, r13
0x180011102  sub     rax, r13
0x180011105  sub     rdx, r13
0x180011108  jnz     short loc_1800110EC
0x18001110a  test    rdx, rdx
0x18001110d  lea     rax, [rcx-1]
0x180011111  cmovnz  rax, rcx
0x180011115  mov     byte ptr [rax], 0
0x180011118  add     bp, r13w
0x18001111c  add     rbx, 38h ; '8'
0x180011120  movzx   eax, bp
0x180011123  cmp     eax, [r14]
0x180011126  jb      loc_180011023
0x18001112c  lea     rax, a64000; "64000"
0x180011133  lea     rcx, [r15+168h]
0x18001113a  test    rsi, rsi
0x18001113d  jz      short loc_180011155
0x18001113f  mov     dl, [rax]
0x180011141  test    dl, dl
0x180011143  jz      short loc_180011155
0x180011145  mov     [rcx], dl
0x180011147  add     rax, r13
0x18001114a  add     rcx, r13
0x18001114d  sub     rsi, r13
0x180011150  sub     rdi, r13
0x180011153  jnz     short loc_18001113A
0x180011155  test    rdi, rdi
0x180011158  lea     rax, [rcx-1]
0x18001115c  cmovnz  rax, rcx
0x180011160  mov     byte ptr [rax], 0
0x180011163  xor     eax, eax
0x180011165  add     rsp, 20h
0x180011169  pop     r15
0x18001116b  pop     r14
0x18001116d  pop     r13
0x18001116f  pop     rdi
0x180011170  pop     rsi
0x180011171  pop     rbp
0x180011172  pop     rbx
0x180011173  retn
0x180011174  mov     eax, 25Ch
0x180011179  jmp     short loc_180011165
```
