# MatchPathInUrl(ushort const *,ulong,ushort const *)

- ea: `0x18000dae0`
- end: `0x18000dd70`
- name: `?MatchPathInUrl@@YAPEBGPEBGK0@Z`
- size: `656`
- prototype: `const unsigned __int16 *__fastcall(wchar_t *String1, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d8a0`
- `0x1800227e0`

## callees

- `0x18000dae0`
- `0x1800343ca`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000db48`
- `msvcrt!wcsrchr` at `0x18000db5d`
- `msvcrt!wcsrchr` at `0x18000db48`
- `msvcrt!wcsrchr` at `0x18000db5d`

## pseudocode

```c
wchar_t *__fastcall MatchPathInUrl(wchar_t *String1, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned __int16 v3; // r12
  __int64 v4; // r13
  const unsigned __int16 *v5; // r15
  unsigned __int16 v7; // ax
  __int64 v8; // rax
  bool v9; // zf
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // rbx
  wchar_t *v15; // rsi
  const unsigned __int16 *i; // rdi
  wchar_t v17; // cx
  wchar_t v18; // ax
  const wchar_t *v19; // r14
  wchar_t k; // ax
  wchar_t v21; // ax
  wchar_t *v22; // rdx
  wchar_t j; // ax
  __int64 v24; // rbp
  wchar_t m; // ax

  v3 = *a3;
  v4 = a2;
  v5 = a3;
  if ( *a3 != 42 )
  {
    if ( v3 == 47 )
      v5 = a3 + 1;
LABEL_17:
    v14 = String1 + 1;
    if ( *String1 != 47 )
      v14 = String1;
    v15 = v14;
    while ( 2 )
    {
      i = v5;
      while ( 1 )
      {
        v17 = *i;
        if ( *i == 63 )
        {
          while ( *v14 )
          {
            if ( *v14 == 47 )
              goto LABEL_56;
            v17 = i[1];
            ++i;
            ++v14;
            if ( v17 != 63 )
              goto LABEL_25;
          }
          return 0;
        }
LABEL_25:
        if ( v17 == 42 )
          v18 = i[1];
        else
          v18 = v17;
        v19 = i + 1;
        if ( v17 != 42 )
          v19 = i;
        if ( !v18 )
          break;
        v21 = *v19;
        for ( i = v19; v21 != 42; ++i )
        {
          if ( v21 == 63 )
            break;
          if ( !v21 )
            break;
          v21 = i[1];
        }
        if ( v17 == 42 )
        {
          if ( !*i )
          {
            v22 = &v14[i - v19];
            if ( v22 > &v15[v4] )
              return 0;
            for ( j = *v22; j != 47; ++v14 )
            {
              if ( !j )
                break;
              if ( *v14 == 47 )
                break;
              if ( !*v14 )
                break;
              j = v22[1];
              ++v22;
            }
          }
          v24 = i - v19;
          if ( wcsncmp_0(v14, v19, (unsigned int)v24) )
          {
            while ( *v14 )
            {
              if ( *v14 == 47 )
                goto LABEL_56;
              if ( !wcsncmp_0(++v14, v19, (unsigned int)v24) )
                goto LABEL_54;
            }
            return 0;
          }
        }
        else
        {
          v24 = i - v19;
          if ( wcsncmp_0(v14, v19, (unsigned int)v24) )
            goto LABEL_56;
        }
LABEL_54:
        v14 += v24;
      }
      if ( v17 == 42 )
      {
        for ( k = *v14; k != 47; ++v14 )
        {
          if ( !k )
            break;
          k = v14[1];
        }
      }
      if ( *v14 == 47 || !*v14 )
        return v14;
LABEL_56:
      if ( v3 != 47 )
      {
        for ( m = *v15; m != 47; ++v15 )
        {
          if ( !m )
            break;
          m = v15[1];
        }
        if ( *v15 )
        {
          v14 = ++v15;
          continue;
        }
      }
      return 0;
    }
  }
  v7 = a3[1];
  if ( !v7 )
  {
    v8 = -1;
    do
      v9 = String1[++v8] == 0;
    while ( !v9 );
    return &String1[v8];
  }
  if ( v7 != 46 || a3[2] )
    goto LABEL_17;
  v11 = wcsrchr(String1, 0x2Fu);
  if ( !v11 )
    v11 = String1;
  v12 = wcsrchr(v11, 0x2Eu);
  if ( v12 && v12[1] )
    return 0;
  v13 = -1;
  do
    v9 = String1[++v13] == 0;
  while ( !v9 );
  return &String1[v13];
}

```

## disassembly

```asm
0x18000dae0  push    rbx
0x18000dae2  push    rbp
0x18000dae3  push    rsi
0x18000dae4  push    rdi
0x18000dae5  push    r12
0x18000dae7  push    r13
0x18000dae9  push    r14
0x18000daeb  push    r15
0x18000daed  sub     rsp, 28h
0x18000daf1  movzx   r12d, word ptr [r8]
0x18000daf5  lea     rax, [r8+2]
0x18000daf9  mov     r13d, edx
0x18000dafc  mov     r15, r8
0x18000daff  mov     rsi, rcx
0x18000db02  cmp     r12w, 2Ah ; '*'
0x18000db07  jnz     loc_18000DB95
0x18000db0d  movzx   eax, word ptr [rax]
0x18000db10  test    ax, ax
0x18000db13  jnz     short loc_18000DB35
0x18000db15  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000db1c  nop     dword ptr [rax+00h]
0x18000db20  cmp     word ptr [rcx+rax*2+2], 0
0x18000db26  lea     rax, [rax+1]
0x18000db2a  jnz     short loc_18000DB20
0x18000db2c  lea     rax, [rcx+rax*2]
0x18000db30  jmp     loc_18000DD5F
0x18000db35  cmp     ax, 2Eh ; '.'
0x18000db39  jnz     short loc_18000DB9E
0x18000db3b  cmp     word ptr [r8+4], 0
0x18000db41  jnz     short loc_18000DB9E
0x18000db43  mov     edx, 2Fh ; '/'; Ch
0x18000db48  call    cs:__imp_wcsrchr
0x18000db4e  test    rax, rax
0x18000db51  mov     edx, 2Eh ; '.'; Ch
0x18000db56  cmovz   rax, rsi
0x18000db5a  mov     rcx, rax; Str
0x18000db5d  call    cs:__imp_wcsrchr
0x18000db63  test    rax, rax
0x18000db66  jz      short loc_18000DB73
0x18000db68  cmp     word ptr [rax+2], 0
0x18000db6d  jnz     loc_18000DD5D
0x18000db73  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000db7a  nop     word ptr [rax+rax+00h]
0x18000db80  cmp     word ptr [rsi+rax*2+2], 0
0x18000db86  lea     rax, [rax+1]
0x18000db8a  jnz     short loc_18000DB80
0x18000db8c  lea     rax, [rsi+rax*2]
0x18000db90  jmp     loc_18000DD5F
0x18000db95  cmp     r12w, 2Fh ; '/'
0x18000db9a  cmovz   r15, rax
0x18000db9e  cmp     word ptr [rcx], 2Fh ; '/'
0x18000dba2  lea     rbx, [rcx+2]
0x18000dba6  cmovnz  rbx, rsi
0x18000dbaa  mov     rsi, rbx
0x18000dbad  mov     rdi, r15
0x18000dbb0  movzx   ecx, word ptr [rdi]
0x18000dbb3  cmp     cx, 3Fh ; '?'
0x18000dbb7  jnz     short loc_18000DBE8
0x18000dbb9  nop     dword ptr [rax+00000000h]
0x18000dbc0  movzx   eax, word ptr [rbx]
0x18000dbc3  test    ax, ax
0x18000dbc6  jz      loc_18000DD5D
0x18000dbcc  cmp     ax, 2Fh ; '/'
0x18000dbd0  jz      loc_18000DD28
0x18000dbd6  movzx   ecx, word ptr [rdi+2]
0x18000dbda  add     rdi, 2
0x18000dbde  add     rbx, 2
0x18000dbe2  cmp     cx, 3Fh ; '?'
0x18000dbe6  jz      short loc_18000DBC0
0x18000dbe8  cmp     cx, 2Ah ; '*'
0x18000dbec  jnz     short loc_18000DBF4
0x18000dbee  movzx   eax, word ptr [rdi+2]
0x18000dbf2  jmp     short loc_18000DBF7
0x18000dbf4  movzx   eax, cx
0x18000dbf7  lea     r14, [rdi+2]
0x18000dbfb  cmovnz  r14, rdi
0x18000dbff  test    ax, ax
0x18000dc02  jnz     short loc_18000DC40
0x18000dc04  cmp     cx, 2Ah ; '*'
0x18000dc08  jnz     short loc_18000DC26
0x18000dc0a  movzx   eax, word ptr [rbx]
0x18000dc0d  cmp     ax, 2Fh ; '/'
0x18000dc11  jz      short loc_18000DC26
0x18000dc13  test    ax, ax
0x18000dc16  jz      short loc_18000DC26
0x18000dc18  movzx   eax, word ptr [rbx+2]
0x18000dc1c  add     rbx, 2
0x18000dc20  cmp     ax, 2Fh ; '/'
0x18000dc24  jnz     short loc_18000DC13
0x18000dc26  movzx   eax, word ptr [rbx]
0x18000dc29  cmp     ax, 2Fh ; '/'
0x18000dc2d  jz      short loc_18000DC38
0x18000dc2f  test    ax, ax
0x18000dc32  jnz     loc_18000DD28
0x18000dc38  mov     rax, rbx
0x18000dc3b  jmp     loc_18000DD5F
0x18000dc40  movzx   eax, word ptr [r14]
0x18000dc44  mov     rdi, r14
0x18000dc47  cmp     ax, 2Ah ; '*'
0x18000dc4b  jz      short loc_18000DC69
0x18000dc4d  nop     dword ptr [rax]
0x18000dc50  cmp     ax, 3Fh ; '?'
0x18000dc54  jz      short loc_18000DC69
0x18000dc56  test    ax, ax
0x18000dc59  jz      short loc_18000DC69
0x18000dc5b  movzx   eax, word ptr [rdi+2]
0x18000dc5f  add     rdi, 2
0x18000dc63  cmp     ax, 2Ah ; '*'
0x18000dc67  jnz     short loc_18000DC50
0x18000dc69  cmp     cx, 2Ah ; '*'
0x18000dc6d  jnz     loc_18000DD0D
0x18000dc73  cmp     word ptr [rdi], 0
0x18000dc77  jnz     short loc_18000DCC5
0x18000dc79  mov     rax, rdi
0x18000dc7c  lea     rcx, [rsi+r13*2]
0x18000dc80  sub     rax, r14
0x18000dc83  sar     rax, 1
0x18000dc86  lea     rdx, [rbx+rax*2]
0x18000dc8a  cmp     rdx, rcx
0x18000dc8d  ja      loc_18000DD5D
0x18000dc93  movzx   eax, word ptr [rdx]
0x18000dc96  cmp     ax, 2Fh ; '/'
0x18000dc9a  jz      short loc_18000DCC5
0x18000dc9c  nop     dword ptr [rax+00h]
0x18000dca0  test    ax, ax
0x18000dca3  jz      short loc_18000DCC5
0x18000dca5  movzx   eax, word ptr [rbx]
0x18000dca8  cmp     ax, 2Fh ; '/'
0x18000dcac  jz      short loc_18000DCC5
0x18000dcae  test    ax, ax
0x18000dcb1  jz      short loc_18000DCC5
0x18000dcb3  movzx   eax, word ptr [rdx+2]
0x18000dcb7  add     rdx, 2
0x18000dcbb  add     rbx, 2
0x18000dcbf  cmp     ax, 2Fh ; '/'
0x18000dcc3  jnz     short loc_18000DCA0
0x18000dcc5  mov     rbp, rdi
0x18000dcc8  mov     rdx, r14; String2
0x18000dccb  sub     rbp, r14
0x18000dcce  mov     rcx, rbx; String1
0x18000dcd1  sar     rbp, 1
0x18000dcd4  mov     r8d, ebp; MaxCount
0x18000dcd7  call    wcsncmp_0
0x18000dcdc  test    eax, eax
0x18000dcde  jz      short loc_18000DD04
0x18000dce0  movzx   eax, word ptr [rbx]
0x18000dce3  test    ax, ax
0x18000dce6  jz      short loc_18000DD5D
0x18000dce8  cmp     ax, 2Fh ; '/'
0x18000dcec  jz      short loc_18000DD28
0x18000dcee  add     rbx, 2
0x18000dcf2  mov     r8d, ebp; MaxCount
0x18000dcf5  mov     rcx, rbx; String1
0x18000dcf8  mov     rdx, r14; String2
0x18000dcfb  call    wcsncmp_0
0x18000dd00  test    eax, eax
0x18000dd02  jnz     short loc_18000DCE0
0x18000dd04  lea     rbx, [rbx+rbp*2]
0x18000dd08  jmp     loc_18000DBB0
0x18000dd0d  mov     rbp, rdi
0x18000dd10  mov     rdx, r14; String2
0x18000dd13  sub     rbp, r14
0x18000dd16  mov     rcx, rbx; String1
0x18000dd19  sar     rbp, 1
0x18000dd1c  mov     r8d, ebp; MaxCount
0x18000dd1f  call    wcsncmp_0
0x18000dd24  test    eax, eax
0x18000dd26  jz      short loc_18000DD04
0x18000dd28  cmp     r12w, 2Fh ; '/'
0x18000dd2d  jz      short loc_18000DD5D
0x18000dd2f  movzx   eax, word ptr [rsi]
0x18000dd32  cmp     ax, 2Fh ; '/'
0x18000dd36  jz      short loc_18000DD4B
0x18000dd38  test    ax, ax
0x18000dd3b  jz      short loc_18000DD4B
0x18000dd3d  movzx   eax, word ptr [rsi+2]
0x18000dd41  add     rsi, 2
0x18000dd45  cmp     ax, 2Fh ; '/'
0x18000dd49  jnz     short loc_18000DD38
0x18000dd4b  cmp     word ptr [rsi], 0
0x18000dd4f  jz      short loc_18000DD5D
0x18000dd51  add     rsi, 2
0x18000dd55  mov     rbx, rsi
0x18000dd58  jmp     loc_18000DBAD
0x18000dd5d  xor     eax, eax
0x18000dd5f  add     rsp, 28h
0x18000dd63  pop     r15
0x18000dd65  pop     r14
0x18000dd67  pop     r13
0x18000dd69  pop     r12
0x18000dd6b  pop     rdi
0x18000dd6c  pop     rsi
0x18000dd6d  pop     rbp
0x18000dd6e  pop     rbx
0x18000dd6f  retn
```
