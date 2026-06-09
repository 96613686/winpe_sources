# g_make_token_header(gss_OID_desc_struct *,int,uchar * *,int)

- ea: `0x1400084c4`
- end: `0x14000857e`
- name: `?g_make_token_header@@YAXPEAUgss_OID_desc_struct@@HPEAPEAEH@Z`
- size: `186`
- prototype: `void __fastcall(struct gss_OID_desc_struct *, int, unsigned __int8 **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140027324`

## callees

- `0x140008404`
- `0x1400084c4`
- `0x1400102c0`

## pseudocode

```c
void __fastcall g_make_token_header(const void **a1, int a2, unsigned __int8 **a3, __int16 a4)
{
  _BYTE *v4; // r10
  _BYTE *v8; // rbx
  int v9; // ecx
  _BYTE *v10; // rdx
  __int64 v11; // r10
  __int64 v12; // rcx

  v4 = *a3;
  *v4 = 96;
  v8 = v4 + 1;
  v9 = a2 + *(_DWORD *)a1 + 4;
  if ( v9 >= 128 )
  {
    *v8 = der_length_size(v9) + 127;
    if ( v9 < 0x1000000 )
    {
      if ( v9 < 0x10000 )
      {
        if ( v9 < 256 )
        {
          v8 = v10;
          goto LABEL_9;
        }
        goto LABEL_7;
      }
    }
    else
    {
      *v10 = HIBYTE(v9);
      v10 = (_BYTE *)(v11 + 3);
    }
    *v10++ = BYTE2(v9);
LABEL_7:
    v8 = v10 + 1;
    *v10 = BYTE1(v9);
  }
LABEL_9:
  *v8 = v9;
  v8[1] = 6;
  v8[2] = *(_BYTE *)a1;
  memmove(v8 + 3, a1[1], *(int *)a1);
  v12 = *(int *)a1;
  v8[v12 + 3] = HIBYTE(a4);
  v8[v12 + 4] = a4;
  *a3 = &v8[v12 + 5];
}

```

## disassembly

```asm
0x1400084c4  push    rbx
0x1400084c6  push    rbp
0x1400084c7  push    rsi
0x1400084c8  push    rdi
0x1400084c9  sub     rsp, 28h
0x1400084cd  mov     r10, [r8]
0x1400084d0  mov     rdi, rcx
0x1400084d3  mov     ebp, r9d
0x1400084d6  mov     rsi, r8
0x1400084d9  mov     byte ptr [r10], 60h ; '`'
0x1400084dd  lea     rbx, [r10+1]
0x1400084e1  mov     ecx, [rcx]
0x1400084e3  add     ecx, 4
0x1400084e6  add     ecx, edx; int
0x1400084e8  cmp     ecx, 80h
0x1400084ee  jl      short loc_14000853E
0x1400084f0  lea     rdx, [r10+2]
0x1400084f4  call    ?der_length_size@@YAHH@Z; der_length_size(int)
0x1400084f9  add     al, 7Fh
0x1400084fb  mov     [rbx], al
0x1400084fd  cmp     ecx, 1000000h
0x140008503  jl      short loc_140008512
0x140008505  mov     eax, ecx
0x140008507  sar     eax, 18h
0x14000850a  mov     [rdx], al
0x14000850c  lea     rdx, [r10+3]
0x140008510  jmp     short loc_14000851A
0x140008512  cmp     ecx, 10000h
0x140008518  jl      short loc_140008526
0x14000851a  mov     eax, ecx
0x14000851c  sar     eax, 10h
0x14000851f  mov     [rdx], al
0x140008521  inc     rdx
0x140008524  jmp     short loc_14000852E
0x140008526  cmp     ecx, 100h
0x14000852c  jl      short loc_14000853B
0x14000852e  mov     eax, ecx
0x140008530  lea     rbx, [rdx+1]
0x140008534  sar     eax, 8
0x140008537  mov     [rdx], al
0x140008539  jmp     short loc_14000853E
0x14000853b  mov     rbx, rdx
0x14000853e  mov     [rbx], cl
0x140008540  lea     rcx, [rbx+3]; void *
0x140008544  mov     byte ptr [rbx+1], 6
0x140008548  mov     al, [rdi]
0x14000854a  mov     [rbx+2], al
0x14000854d  movsxd  r8, dword ptr [rdi]; Size
0x140008550  mov     rdx, [rdi+8]; Src
0x140008554  call    memmove
0x140008559  movsxd  rcx, dword ptr [rdi]
0x14000855c  mov     eax, ebp
0x14000855e  sar     eax, 8
0x140008561  mov     [rcx+rbx+3], al
0x140008565  lea     rax, [rcx+5]
0x140008569  add     rax, rbx
0x14000856c  mov     [rcx+rbx+4], bpl
0x140008571  mov     [rsi], rax
0x140008574  add     rsp, 28h
0x140008578  pop     rdi
0x140008579  pop     rsi
0x14000857a  pop     rbp
0x14000857b  pop     rbx
0x14000857c  retn
```
