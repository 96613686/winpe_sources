# DecodeRle

- ea: `0x18000211c`
- end: `0x180002247`
- name: `DecodeRle`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x180001c9e`
- `0x18000211c`

## pseudocode

```c
void __fastcall DecodeRle(__int64 a1, _BYTE *a2, char *a3, unsigned int a4)
{
  int v4; // edi
  _BYTE *v7; // r15
  unsigned int v8; // r12d
  unsigned int v9; // edi
  unsigned int v10; // r14d
  size_t v11; // rbp
  unsigned __int8 *v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  char v15; // al
  unsigned int v16; // ecx
  __int64 v17; // rax

  v4 = *(_DWORD *)(a1 + 8);
  v7 = a2;
  if ( v4 > 0 )
  {
    v8 = (*(_DWORD *)(a1 + 4) + 3) & 0xFFFFFFFC;
    v9 = v8 * v4;
LABEL_3:
    v10 = 0;
    while ( a4 >= 2 )
    {
      v11 = (unsigned __int8)*a3;
      v12 = (unsigned __int8 *)(a3 + 1);
      v13 = (unsigned __int8)a3[1];
      a4 -= 2;
      a3 += 2;
      if ( (_DWORD)v11 )
      {
        if ( v9 < (unsigned int)v11 )
          return;
        v10 += v11;
        v9 -= v11;
        LOBYTE(a2) = v13;
        memset_0(v7, (int)a2, v11);
        do
        {
          ++v7;
          LODWORD(v11) = v11 - 1;
        }
        while ( (_DWORD)v11 );
      }
      else
      {
        v14 = v13;
        LODWORD(a2) = v13;
        if ( !(_BYTE)v13 )
        {
          if ( v10 <= v8 )
          {
            v17 = v8 - v10;
            if ( v9 >= (unsigned int)v17 )
            {
              v9 += v10 - v8;
              v7 += v17;
              goto LABEL_3;
            }
          }
          return;
        }
        LODWORD(a2) = v13 - 1;
        if ( v13 == 1 )
          return;
        if ( v13 == 2 )
        {
          if ( a4 < 2 )
            return;
          LODWORD(a2) = (unsigned __int8)*a3;
          v16 = (_DWORD)a2 + v8 * v12[2];
          if ( v9 < v16 )
            return;
          a3 = (char *)(v12 + 3);
          v7 += v16;
          a4 -= 2;
          v9 -= v16;
          v10 += (unsigned int)a2;
        }
        else
        {
          if ( v9 < v13 || a4 < v13 )
            return;
          v9 -= v13;
          a4 -= v13;
          v10 += v13;
          do
          {
            v15 = *a3++;
            *v7++ = v15;
            --v14;
          }
          while ( v14 );
          if ( (v13 & 1) != 0 )
          {
            if ( !a4 )
              return;
            --a4;
            ++a3;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000211c  push    rbx
0x18000211e  push    rbp
0x18000211f  push    rsi
0x180002120  push    rdi
0x180002121  push    r12
0x180002123  push    r14
0x180002125  push    r15
0x180002127  sub     rsp, 20h
0x18000212b  mov     edi, [rcx+8]
0x18000212e  mov     ebx, r9d
0x180002131  mov     rsi, r8
0x180002134  mov     r15, rdx
0x180002137  test    edi, edi
0x180002139  jle     loc_180002238
0x18000213f  mov     r12d, [rcx+4]
0x180002143  add     r12d, 3
0x180002147  and     r12d, 0FFFFFFFCh
0x18000214b  imul    edi, r12d
0x18000214f  xor     r14d, r14d
0x180002152  jmp     loc_18000222F
0x180002157  movzx   ebp, byte ptr [rsi]
0x18000215a  lea     r8, [rsi+1]
0x18000215e  movzx   r9d, byte ptr [rsi+1]
0x180002163  add     ebx, 0FFFFFFFEh
0x180002166  add     rsi, 2
0x18000216a  test    ebp, ebp
0x18000216c  jnz     loc_180002210
0x180002172  mov     ecx, r9d
0x180002175  mov     edx, r9d
0x180002178  test    r9b, r9b
0x18000217b  jz      short loc_1800021F3
0x18000217d  sub     edx, 1
0x180002180  jz      loc_180002238
0x180002186  cmp     edx, 1
0x180002189  jz      short loc_1800021C9
0x18000218b  cmp     edi, ecx
0x18000218d  jb      loc_180002238
0x180002193  cmp     ebx, ecx
0x180002195  jb      loc_180002238
0x18000219b  sub     edi, ecx
0x18000219d  sub     ebx, ecx
0x18000219f  add     r14d, ecx
0x1800021a2  test    r9b, r9b
0x1800021a5  jz      short loc_1800021B7
0x1800021a7  mov     al, [rsi]
0x1800021a9  inc     rsi
0x1800021ac  mov     [r15], al
0x1800021af  inc     r15
0x1800021b2  add     ecx, 0FFFFFFFFh
0x1800021b5  jnz     short loc_1800021A7
0x1800021b7  test    r9b, 1
0x1800021bb  jz      short loc_18000222F
0x1800021bd  cmp     ebx, 1
0x1800021c0  jb      short loc_180002238
0x1800021c2  dec     ebx
0x1800021c4  inc     rsi
0x1800021c7  jmp     short loc_18000222F
0x1800021c9  cmp     ebx, 2
0x1800021cc  jb      short loc_180002238
0x1800021ce  movzx   ecx, byte ptr [r8+2]
0x1800021d3  movzx   edx, byte ptr [rsi]
0x1800021d6  imul    ecx, r12d
0x1800021da  add     ecx, edx
0x1800021dc  cmp     edi, ecx
0x1800021de  jb      short loc_180002238
0x1800021e0  mov     eax, ecx
0x1800021e2  lea     rsi, [r8+3]
0x1800021e6  add     r15, rax
0x1800021e9  add     ebx, 0FFFFFFFEh
0x1800021ec  sub     edi, ecx
0x1800021ee  add     r14d, edx
0x1800021f1  jmp     short loc_18000222F
0x1800021f3  cmp     r14d, r12d
0x1800021f6  ja      short loc_180002238
0x1800021f8  mov     eax, r12d
0x1800021fb  sub     eax, r14d
0x1800021fe  cmp     edi, eax
0x180002200  jb      short loc_180002238
0x180002202  sub     r14d, r12d
0x180002205  add     edi, r14d
0x180002208  add     r15, rax
0x18000220b  jmp     loc_18000214F
0x180002210  cmp     edi, ebp
0x180002212  jb      short loc_180002238
0x180002214  add     r14d, ebp
0x180002217  sub     edi, ebp
0x180002219  mov     r8, rbp; Size
0x18000221c  mov     dl, r9b; Val
0x18000221f  mov     rcx, r15; void *
0x180002222  call    memset_0
0x180002227  inc     r15
0x18000222a  add     ebp, 0FFFFFFFFh
0x18000222d  jnz     short loc_180002227
0x18000222f  cmp     ebx, 2
0x180002232  jnb     loc_180002157
0x180002238  add     rsp, 20h
0x18000223c  pop     r15
0x18000223e  pop     r14
0x180002240  pop     r12
0x180002242  pop     rdi
0x180002243  pop     rsi
0x180002244  pop     rbp
0x180002245  pop     rbx
0x180002246  retn
```
