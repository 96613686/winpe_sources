# PROTOCOL::SplitMessages(FCGI_BUFFER *,ulong,_LIST_ENTRY *)

- ea: `0x180003c08`
- end: `0x180003e13`
- name: `?SplitMessages@PROTOCOL@@AEAAJPEAVFCGI_BUFFER@@KPEAU_LIST_ENTRY@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(PROTOCOL *this, struct FCGI_BUFFER *, int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800036b8`

## callees

- `0x180003c08`
- `0x180008f90`
- `0x180009128`
- `0x18000edc6`

## pseudocode

```c
__int64 __fastcall PROTOCOL::SplitMessages(PROTOCOL *this, struct FCGI_BUFFER *a2, int a3, struct _LIST_ENTRY *a4)
{
  _BYTE *v6; // rbp
  int v7; // r12d
  unsigned int v8; // r12d
  int v9; // r8d
  unsigned int v10; // r14d
  int v11; // ecx
  unsigned __int16 v12; // ax
  bool v13; // zf
  int v14; // r15d
  struct FCGI_BUFFER *v15; // rdi
  __int64 v16; // r13
  void **v17; // rax
  __int64 v18; // rcx
  struct _LIST_ENTRY *Blink; // rcx
  unsigned int v20; // edi
  void **v22; // rax
  void **v23; // r14
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v25; // rax
  FCGI_BUFFER *v26; // rcx
  struct FCGI_BUFFER *v27; // [rsp+68h] [rbp+10h]
  int v28; // [rsp+70h] [rbp+18h]

  v27 = a2;
  v6 = *(_BYTE **)a2;
  v7 = *((_DWORD *)this + 32) - **((_DWORD **)this + 15);
  v13 = a3 + v7 == 0;
  v8 = a3 + v7;
  v9 = 1;
  v28 = 1;
  if ( v13 )
  {
    return 0;
  }
  else
  {
    while ( 1 )
    {
      v10 = 8;
      if ( v8 < 8 )
        break;
      if ( v6[1] > 0xAu
        || (v11 = 1224, !_bittest(&v11, (unsigned __int8)v6[1]))
        || v6[2]
        || ((v12 = (unsigned __int8)v6[3], (_BYTE)v12) ? (v13 = *((_WORD *)this + 20) == v12) : (v13 = v6[1] == 10), !v13) )
      {
        v20 = -2147024883;
        goto LABEL_27;
      }
      v14 = (unsigned __int8)v6[5] + ((unsigned __int8)v6[4] << 8);
      v10 = (unsigned __int8)v6[6] + v14 + 8;
      if ( v8 < v10 )
        break;
      if ( v9 )
      {
        ++*((_DWORD *)this + 40);
        v9 = 0;
        v28 = 0;
        v15 = a2;
        *((_QWORD *)this + 15) = 0;
        if ( v14 )
        {
          *((_DWORD *)a2 + 6) = v14;
          *((_QWORD *)a2 + 2) = v6 + 8;
        }
        v16 = v10;
      }
      else
      {
        v17 = (void **)FCGI_BUFFER::Alloc(v10);
        v15 = (struct FCGI_BUFFER *)v17;
        if ( !v17 )
          goto LABEL_26;
        v16 = v10;
        memcpy_0(*v17, v6, v10);
        ++*((_DWORD *)this + 41);
        a2 = v27;
        v9 = v28;
        if ( v14 )
        {
          v18 = *(_QWORD *)v15 + 8LL;
          *((_DWORD *)v15 + 6) = v14;
          *((_QWORD *)v15 + 2) = v18;
        }
      }
      Blink = a4->Blink;
      if ( Blink->Flink != a4 )
LABEL_31:
        __fastfail(3u);
      *((_QWORD *)v15 + 4) = a4;
      *((_QWORD *)v15 + 5) = Blink;
      Blink->Flink = (struct _LIST_ENTRY *)((char *)v15 + 32);
      a4->Blink = (struct _LIST_ENTRY *)((char *)v15 + 32);
      if ( !v14 )
      {
        *((_QWORD *)v15 + 2) = *(_QWORD *)v15;
        *((_DWORD *)v15 + 6) = 0;
      }
      v6 += v16;
      v8 -= v10;
      if ( !v8 )
        return 0;
    }
    v20 = 0;
    v22 = (void **)FCGI_BUFFER::Alloc(v10);
    v23 = v22;
    if ( v22 )
    {
      memcpy_0(*v22, v6, v8);
      ++*((_DWORD *)this + 41);
      *((_QWORD *)this + 16) = (char *)*v23 + v8;
      v26 = (FCGI_BUFFER *)*((_QWORD *)this + 15);
      if ( v26 )
        FCGI_BUFFER::Free(v26);
      *((_QWORD *)this + 15) = v23;
      return v20;
    }
LABEL_26:
    v20 = -2147024882;
LABEL_27:
    while ( 1 )
    {
      Flink = a4->Flink;
      if ( a4->Flink == a4 )
        break;
      if ( Flink->Blink != a4 )
        goto LABEL_31;
      v25 = Flink->Flink;
      if ( Flink->Flink->Blink != Flink )
        goto LABEL_31;
      a4->Flink = v25;
      v25->Blink = a4;
      FCGI_BUFFER::Free((FCGI_BUFFER *)&Flink[-2]);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x180003c08  mov     [rsp+arg_0], rbx
0x180003c0d  mov     [rsp+arg_8], rdx
0x180003c12  push    rbp
0x180003c13  push    rsi
0x180003c14  push    rdi
0x180003c15  push    r12
0x180003c17  push    r13
0x180003c19  push    r14
0x180003c1b  push    r15
0x180003c1d  sub     rsp, 20h
0x180003c21  mov     rax, [rcx+78h]
0x180003c25  mov     rbx, r9
0x180003c28  mov     r12d, [rcx+80h]
0x180003c2f  mov     rsi, rcx
0x180003c32  mov     rbp, [rdx]
0x180003c35  sub     r12d, [rax]
0x180003c38  add     r12d, r8d
0x180003c3b  mov     r8d, 1
0x180003c41  mov     [rsp+58h+arg_10], r8d
0x180003c46  jz      loc_180003D71
0x180003c4c  mov     r14d, 8
0x180003c52  cmp     r12d, r14d
0x180003c55  jb      loc_180003D91
0x180003c5b  cmp     byte ptr [rbp+1], 0Ah
0x180003c5f  ja      loc_180003D8A
0x180003c65  movzx   eax, byte ptr [rbp+1]
0x180003c69  mov     ecx, 4C8h
0x180003c6e  bt      ecx, eax
0x180003c71  jnb     loc_180003D8A
0x180003c77  cmp     byte ptr [rbp+2], 0
0x180003c7b  jnz     loc_180003D8A
0x180003c81  movzx   eax, byte ptr [rbp+3]
0x180003c85  test    al, al
0x180003c87  jnz     short loc_180003C8F
0x180003c89  cmp     byte ptr [rbp+1], 0Ah
0x180003c8d  jmp     short loc_180003C93
0x180003c8f  cmp     [rsi+28h], ax
0x180003c93  jnz     loc_180003D8A
0x180003c99  movzx   eax, byte ptr [rbp+5]
0x180003c9d  movzx   r15d, byte ptr [rbp+4]
0x180003ca2  shl     r15d, 8
0x180003ca6  add     r15d, eax
0x180003ca9  movzx   eax, byte ptr [rbp+6]
0x180003cad  lea     r14d, [r15+8]
0x180003cb1  add     r14d, eax
0x180003cb4  cmp     r12d, r14d
0x180003cb7  jb      loc_180003D91
0x180003cbd  test    r8d, r8d
0x180003cc0  jz      short loc_180003CED
0x180003cc2  inc     dword ptr [rsi+0A0h]
0x180003cc8  xor     r8d, r8d
0x180003ccb  mov     [rsp+58h+arg_10], r8d
0x180003cd0  mov     rdi, rdx
0x180003cd3  mov     [rsi+78h], r8
0x180003cd7  test    r15d, r15d
0x180003cda  jz      short loc_180003CE8
0x180003cdc  lea     rax, [rbp+8]
0x180003ce0  mov     [rdx+18h], r15d
0x180003ce4  mov     [rdx+10h], rax
0x180003ce8  mov     r13d, r14d
0x180003ceb  jmp     short loc_180003D36
0x180003ced  mov     ecx, r14d; unsigned int
0x180003cf0  call    ?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z; FCGI_BUFFER::Alloc(ulong)
0x180003cf5  mov     rdi, rax
0x180003cf8  test    rax, rax
0x180003cfb  jz      loc_180003DA3
0x180003d01  mov     rcx, [rax]; void *
0x180003d04  mov     rdx, rbp; Src
0x180003d07  mov     r8d, r14d; Size
0x180003d0a  mov     r13d, r14d
0x180003d0d  call    memcpy_0
0x180003d12  inc     dword ptr [rsi+0A4h]
0x180003d18  mov     rdx, [rsp+58h+arg_8]
0x180003d1d  mov     r8d, [rsp+58h+arg_10]
0x180003d22  test    r15d, r15d
0x180003d25  jz      short loc_180003D36
0x180003d27  mov     rcx, [rdi]
0x180003d2a  add     rcx, 8
0x180003d2e  mov     [rdi+18h], r15d
0x180003d32  mov     [rdi+10h], rcx
0x180003d36  mov     rcx, [rbx+8]
0x180003d3a  cmp     [rcx], rbx
0x180003d3d  jnz     loc_180003DD1
0x180003d43  lea     rax, [rdi+20h]
0x180003d47  mov     [rax], rbx
0x180003d4a  mov     [rax+8], rcx
0x180003d4e  mov     [rcx], rax
0x180003d51  mov     [rbx+8], rax
0x180003d55  test    r15d, r15d
0x180003d58  jnz     short loc_180003D65
0x180003d5a  mov     rax, [rdi]
0x180003d5d  mov     [rdi+10h], rax
0x180003d61  mov     [rdi+18h], r15d
0x180003d65  add     rbp, r13
0x180003d68  sub     r12d, r14d
0x180003d6b  jnz     loc_180003C4C
0x180003d71  xor     edi, edi
0x180003d73  mov     rbx, [rsp+58h+arg_0]
0x180003d78  mov     eax, edi
0x180003d7a  add     rsp, 20h
0x180003d7e  pop     r15
0x180003d80  pop     r14
0x180003d82  pop     r13
0x180003d84  pop     r12
0x180003d86  pop     rdi
0x180003d87  pop     rsi
0x180003d88  pop     rbp
0x180003d89  retn
0x180003d8a  mov     edi, 8007000Dh
0x180003d8f  jmp     short loc_180003DA8
0x180003d91  mov     ecx, r14d; unsigned int
0x180003d94  xor     edi, edi
0x180003d96  call    ?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z; FCGI_BUFFER::Alloc(ulong)
0x180003d9b  mov     r14, rax
0x180003d9e  test    rax, rax
0x180003da1  jnz     short loc_180003DD8
0x180003da3  mov     edi, 8007000Eh
0x180003da8  mov     rcx, [rbx]
0x180003dab  cmp     rcx, rbx
0x180003dae  jz      short loc_180003D73
0x180003db0  cmp     [rcx+8], rbx
0x180003db4  jnz     short loc_180003DD1
0x180003db6  mov     rax, [rcx]
0x180003db9  cmp     [rax+8], rcx
0x180003dbd  jnz     short loc_180003DD1
0x180003dbf  mov     [rbx], rax
0x180003dc2  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x180003dc6  mov     [rax+8], rbx
0x180003dca  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180003dcf  jmp     short loc_180003DA8
0x180003dd1  mov     ecx, 3
0x180003dd6  int     29h; Win8: RtlFailFast(ecx)
0x180003dd8  mov     rcx, [rax]; void *
0x180003ddb  mov     rdx, rbp; Src
0x180003dde  mov     r8d, r12d; Size
0x180003de1  mov     ebx, r12d
0x180003de4  call    memcpy_0
0x180003de9  inc     dword ptr [rsi+0A4h]
0x180003def  mov     rcx, [r14]
0x180003df2  add     rcx, rbx
0x180003df5  mov     [rsi+80h], rcx
0x180003dfc  mov     rcx, [rsi+78h]; this
0x180003e00  test    rcx, rcx
0x180003e03  jz      short loc_180003E0A
0x180003e05  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180003e0a  mov     [rsi+78h], r14
0x180003e0e  jmp     loc_180003D73
```
