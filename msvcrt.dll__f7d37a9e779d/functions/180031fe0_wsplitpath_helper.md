# _wsplitpath_helper

- ea: `0x180031fe0`
- end: `0x18003229a`
- name: `_wsplitpath_helper`
- size: `698`
- prototype: `__int64 __usercall@<rax>(wchar_t *Source@<rcx>, wchar_t *Destination@<rdx>, __int64, wchar_t *, __int64, wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180031f50`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x180031fe0`
- `0x180061e50`

## pseudocode

```c
__int64 __fastcall wsplitpath_helper(
        wchar_t *Source,
        wchar_t *Destination,
        unsigned __int64 a3,
        wchar_t *a4,
        unsigned __int64 a5,
        wchar_t *Destinationa,
        unsigned __int64 a7,
        wchar_t *a8,
        unsigned __int64 a9)
{
  unsigned __int64 v11; // r9
  const wchar_t *v12; // rdi
  int v13; // ecx
  __int64 v14; // rax
  const wchar_t *v15; // rbx
  wchar_t v16; // ax
  const wchar_t *v17; // rsi
  const wchar_t *v18; // rbx
  const wchar_t *v19; // rbp
  rsize_t v20; // r9
  rsize_t v21; // r9
  rsize_t v22; // rbx
  rsize_t v23; // rbx

  v11 = a3;
  v12 = Source;
  if ( !Source )
    goto LABEL_4;
  if ( Destination )
  {
    if ( !a3 )
      goto LABEL_4;
  }
  else if ( a3 )
  {
LABEL_4:
    v13 = 1;
    goto LABEL_59;
  }
  if ( a4 )
  {
    if ( !a5 )
      goto LABEL_4;
  }
  else if ( a5 )
  {
    goto LABEL_4;
  }
  if ( Destinationa )
  {
    if ( !a7 )
      goto LABEL_4;
  }
  else if ( a7 )
  {
    goto LABEL_4;
  }
  if ( a8 )
  {
    if ( !a9 )
      goto LABEL_4;
  }
  else if ( a9 )
  {
    goto LABEL_4;
  }
  v13 = 0;
  v14 = 1;
  v15 = v12;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( *v15 == 58 )
  {
    if ( Destination )
    {
      if ( a3 < 3 )
        goto LABEL_60;
      wcsncpy_s(Destination, 0xFFFFFFFFFFFFFFFFuLL, v12, 2u);
      v13 = 0;
    }
    v12 = v15 + 1;
  }
  else if ( Destination )
  {
    *Destination = 0;
  }
  v16 = *v12;
  v17 = 0;
  v18 = v12;
  if ( !*v12 )
    goto LABEL_41;
  v19 = 0;
  do
  {
    if ( v16 == 47 || v16 == 92 )
    {
      v19 = v18 + 1;
    }
    else if ( v16 == 46 )
    {
      v17 = v18;
    }
    v16 = *++v18;
  }
  while ( *v18 );
  if ( !v19 )
  {
LABEL_41:
    if ( a4 )
      *a4 = 0;
LABEL_43:
    if ( v17 && v17 >= v12 )
    {
      if ( !Destinationa )
      {
LABEL_48:
        if ( !a8 )
          return 0;
        v22 = v18 - v17;
        if ( a9 > v22 )
        {
          wcsncpy_s(a8, 0xFFFFFFFFFFFFFFFFuLL, v17, v22);
          return 0;
        }
        goto LABEL_57;
      }
      v21 = v17 - v12;
      if ( a7 > v21 )
      {
        wcsncpy_s(Destinationa, 0xFFFFFFFFFFFFFFFFuLL, v12, v21);
        goto LABEL_48;
      }
LABEL_57:
      v13 = 0;
      goto LABEL_58;
    }
    if ( Destinationa )
    {
      v23 = v18 - v12;
      if ( a7 <= v23 )
        goto LABEL_57;
      wcsncpy_s(Destinationa, 0xFFFFFFFFFFFFFFFFuLL, v12, v23);
    }
    if ( a8 )
      *a8 = 0;
    return 0;
  }
  if ( !a4 )
  {
LABEL_40:
    v12 = v19;
    goto LABEL_43;
  }
  v20 = v19 - v12;
  if ( a5 > v20 )
  {
    wcsncpy_s(a4, 0xFFFFFFFFFFFFFFFFuLL, v12, v20);
    goto LABEL_40;
  }
LABEL_58:
  v11 = a3;
LABEL_59:
  if ( Destination )
  {
LABEL_60:
    if ( v11 )
      *Destination = 0;
  }
  if ( a4 && a5 )
    *a4 = 0;
  if ( Destinationa && a7 )
    *Destinationa = 0;
  if ( a8 && a9 )
    *a8 = 0;
  if ( !v12 || v13 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  *errno() = 34;
  return 34;
}

```

## disassembly

```asm
0x180031fe0  mov     [rsp+arg_8], rbx
0x180031fe5  mov     [rsp+arg_10], r8
0x180031fea  push    rbp
0x180031feb  push    rsi
0x180031fec  push    rdi
0x180031fed  push    r12
0x180031fef  push    r13
0x180031ff1  push    r14
0x180031ff3  push    r15
0x180031ff5  sub     rsp, 30h
0x180031ff9  mov     r14, [rsp+68h+arg_38]
0x180032001  mov     r12, rdx
0x180032004  mov     r15, [rsp+68h+Destination]
0x18003200c  xor     edx, edx
0x18003200e  mov     r13, r9
0x180032011  mov     r9, r8
0x180032014  mov     rdi, rcx
0x180032017  test    rcx, rcx
0x18003201a  jz      short loc_180032026
0x18003201c  test    r12, r12
0x18003201f  jnz     short loc_180032030
0x180032021  test    r8, r8
0x180032024  jz      short loc_180032035
0x180032026  mov     ecx, 1
0x18003202b  jmp     loc_1800321FD
0x180032030  test    r8, r8
0x180032033  jz      short loc_180032026
0x180032035  test    r13, r13
0x180032038  jnz     short loc_180032046
0x18003203a  cmp     [rsp+68h+arg_20], rdx
0x180032042  jnz     short loc_180032026
0x180032044  jmp     short loc_180032050
0x180032046  cmp     [rsp+68h+arg_20], rdx
0x18003204e  jz      short loc_180032026
0x180032050  test    r15, r15
0x180032053  jnz     short loc_180032061
0x180032055  cmp     [rsp+68h+arg_30], rdx
0x18003205d  jnz     short loc_180032026
0x18003205f  jmp     short loc_18003206B
0x180032061  cmp     [rsp+68h+arg_30], rdx
0x180032069  jz      short loc_180032026
0x18003206b  test    r14, r14
0x18003206e  jnz     short loc_18003207C
0x180032070  cmp     [rsp+68h+arg_40], rdx
0x180032078  jnz     short loc_180032026
0x18003207a  jmp     short loc_180032086
0x18003207c  cmp     [rsp+68h+arg_40], rdx
0x180032084  jz      short loc_180032026
0x180032086  mov     ecx, edx
0x180032088  mov     [rsp+68h+arg_0], edx
0x18003208c  mov     eax, 1
0x180032091  mov     rbx, rdi
0x180032094  cmp     [rbx], dx
0x180032097  jz      short loc_1800320A3
0x180032099  add     rbx, 2
0x18003209d  sub     rax, 1
0x1800320a1  jnz     short loc_180032094
0x1800320a3  cmp     word ptr [rbx], 3Ah ; ':'
0x1800320a7  jnz     short loc_1800320D9
0x1800320a9  test    r12, r12
0x1800320ac  jz      short loc_1800320D3
0x1800320ae  cmp     r8, 3
0x1800320b2  jb      loc_180032202
0x1800320b8  mov     r9d, 2; MaxCount
0x1800320be  mov     r8, rdi; Source
0x1800320c1  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInWords
0x1800320c5  mov     rcx, r12; Destination
0x1800320c8  call    wcsncpy_s
0x1800320cd  mov     ecx, [rsp+68h+arg_0]
0x1800320d1  xor     edx, edx
0x1800320d3  lea     rdi, [rbx+2]
0x1800320d7  jmp     short loc_1800320E3
0x1800320d9  test    r12, r12
0x1800320dc  jz      short loc_1800320E3
0x1800320de  mov     [r12], dx
0x1800320e3  movzx   eax, word ptr [rdi]
0x1800320e6  mov     rsi, rdx
0x1800320e9  mov     rbx, rdi
0x1800320ec  test    ax, ax
0x1800320ef  jz      short loc_180032152
0x1800320f1  mov     rbp, rdx
0x1800320f4  cmp     ax, 2Fh ; '/'
0x1800320f8  jz      short loc_18003210B
0x1800320fa  cmp     ax, 5Ch ; '\'
0x1800320fe  jz      short loc_18003210B
0x180032100  cmp     ax, 2Eh ; '.'
0x180032104  jnz     short loc_18003210F
0x180032106  mov     rsi, rbx
0x180032109  jmp     short loc_18003210F
0x18003210b  lea     rbp, [rbx+2]
0x18003210f  add     rbx, 2
0x180032113  movzx   eax, word ptr [rbx]
0x180032116  test    ax, ax
0x180032119  jnz     short loc_1800320F4
0x18003211b  test    rbp, rbp
0x18003211e  jz      short loc_180032152
0x180032120  test    r13, r13
0x180032123  jz      short loc_18003214D
0x180032125  mov     r9, rbp
0x180032128  sub     r9, rdi
0x18003212b  sar     r9, 1; MaxCount
0x18003212e  cmp     [rsp+68h+arg_20], r9
0x180032136  jbe     loc_1800321F5
0x18003213c  mov     r8, rdi; Source
0x18003213f  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInWords
0x180032143  mov     rcx, r13; Destination
0x180032146  call    wcsncpy_s
0x18003214b  xor     edx, edx
0x18003214d  mov     rdi, rbp
0x180032150  jmp     short loc_18003215C
0x180032152  test    r13, r13
0x180032155  jz      short loc_18003215C
0x180032157  mov     [r13+0], dx
0x18003215c  test    rsi, rsi
0x18003215f  jz      short loc_1800321B8
0x180032161  cmp     rsi, rdi
0x180032164  jb      short loc_1800321B8
0x180032166  test    r15, r15
0x180032169  jz      short loc_18003218F
0x18003216b  mov     r9, rsi
0x18003216e  sub     r9, rdi
0x180032171  sar     r9, 1; MaxCount
0x180032174  cmp     [rsp+68h+arg_30], r9
0x18003217c  jbe     short loc_1800321F1
0x18003217e  mov     r8, rdi; Source
0x180032181  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInWords
0x180032185  mov     rcx, r15; Destination
0x180032188  call    wcsncpy_s
0x18003218d  xor     edx, edx
0x18003218f  test    r14, r14
0x180032192  jz      short loc_1800321EA
0x180032194  sub     rbx, rsi
0x180032197  sar     rbx, 1
0x18003219a  cmp     [rsp+68h+arg_40], rbx
0x1800321a2  jbe     short loc_1800321F1
0x1800321a4  mov     r9, rbx; MaxCount
0x1800321a7  mov     r8, rsi; Source
0x1800321aa  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInWords
0x1800321ae  mov     rcx, r14; Destination
0x1800321b1  call    wcsncpy_s
0x1800321b6  jmp     short loc_1800321EA
0x1800321b8  test    r15, r15
0x1800321bb  jz      short loc_1800321E1
0x1800321bd  sub     rbx, rdi
0x1800321c0  sar     rbx, 1
0x1800321c3  cmp     [rsp+68h+arg_30], rbx
0x1800321cb  jbe     short loc_1800321F1
0x1800321cd  mov     r9, rbx; MaxCount
0x1800321d0  mov     r8, rdi; Source
0x1800321d3  or      rdx, 0FFFFFFFFFFFFFFFFh; SizeInWords
0x1800321d7  mov     rcx, r15; Destination
0x1800321da  call    wcsncpy_s
0x1800321df  xor     edx, edx
0x1800321e1  test    r14, r14
0x1800321e4  jz      short loc_1800321EA
0x1800321e6  mov     [r14], dx
0x1800321ea  xor     eax, eax
0x1800321ec  jmp     loc_180032285
0x1800321f1  mov     ecx, [rsp+68h+arg_0]
0x1800321f5  mov     r9, [rsp+68h+arg_10]
0x1800321fd  test    r12, r12
0x180032200  jz      short loc_18003220C
0x180032202  test    r9, r9
0x180032205  jz      short loc_18003220C
0x180032207  mov     [r12], dx
0x18003220c  test    r13, r13
0x18003220f  jz      short loc_180032220
0x180032211  cmp     [rsp+68h+arg_20], rdx
0x180032219  jbe     short loc_180032220
0x18003221b  mov     [r13+0], dx
0x180032220  test    r15, r15
0x180032223  jz      short loc_180032233
0x180032225  cmp     [rsp+68h+arg_30], rdx
0x18003222d  jbe     short loc_180032233
0x18003222f  mov     [r15], dx
0x180032233  test    r14, r14
0x180032236  jz      short loc_180032246
0x180032238  cmp     [rsp+68h+arg_40], rdx
0x180032240  jbe     short loc_180032246
0x180032242  mov     [r14], dx
0x180032246  test    rdi, rdi
0x180032249  jnz     short loc_180032273
0x18003224b  call    _errno
0x180032250  mov     ebx, 16h
0x180032255  mov     [rsp+68h+Reserved], 0; Reserved
0x18003225e  xor     r9d, r9d; LineNo
0x180032261  xor     r8d, r8d; FileName
0x180032264  xor     edx, edx; FunctionName
0x180032266  xor     ecx, ecx; Expression
0x180032268  mov     [rax], ebx
0x18003226a  call    _invalid_parameter
0x18003226f  mov     eax, ebx
0x180032271  jmp     short loc_180032285
0x180032273  test    ecx, ecx
0x180032275  jnz     short loc_18003224B
0x180032277  call    _errno
0x18003227c  mov     ecx, 22h ; '"'
0x180032281  mov     [rax], ecx
0x180032283  mov     eax, ecx
0x180032285  mov     rbx, [rsp+68h+arg_8]
0x18003228a  add     rsp, 30h
0x18003228e  pop     r15
0x180032290  pop     r14
0x180032292  pop     r13
0x180032294  pop     r12
0x180032296  pop     rdi
0x180032297  pop     rsi
0x180032298  pop     rbp
0x180032299  retn
```
