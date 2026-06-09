# MidlCopyStringArray(ushort * const *,ulong,ushort * * *)

- ea: `0x140019e10`
- end: `0x140019f2f`
- name: `?MidlCopyStringArray@@YAJPEBQEAGKPEAPEAPEAG@Z`
- size: `287`
- prototype: `__int64 __fastcall(unsigned __int16 *const *, unsigned int, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140019b20`

## callees

- `0x1400020d0`
- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x140019e10`

## pseudocode

```c
__int64 __fastcall MidlCopyStringArray(unsigned __int16 *const *a1, unsigned int a2, unsigned __int16 ***a3)
{
  size_t v4; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rsi
  signed int v9; // ebx
  int v10; // edi
  unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned int v16; // edi
  void *v17; // rcx

  v4 = 8LL * a2;
  v7 = (_QWORD *)DAF_user_alloc(v4);
  v8 = v7;
  if ( v7 )
  {
    v9 = 0;
    memset_0(v7, 0, v4);
    v10 = 0;
    if ( a2 )
    {
      while ( 1 )
      {
        v11 = a1[v10];
        if ( !v11 )
          break;
        v12 = 0x3FFFFFFF;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v12;
        }
        while ( v12 );
        v9 = v12 == 0 ? 0x80070057 : 0;
        if ( !v12 )
          goto LABEL_16;
        v13 = -(__int64)(v12 != 0) & (2 * (0x3FFFFFFF - v12));
        v14 = (unsigned __int16 *)DAF_user_alloc(v13 + 2);
        v8[v10] = v14;
        if ( !v14 )
        {
          v9 = -2147024882;
          goto LABEL_16;
        }
        v9 = StringCbCopyW(v14, v13 + 2, a1[v10]);
        if ( v9 < 0 )
          goto LABEL_16;
        if ( ++v10 >= a2 )
          goto LABEL_12;
      }
      v9 = -2147024809;
LABEL_16:
      v16 = 0;
      do
      {
        v17 = (void *)v8[v16];
        if ( v17 )
        {
          MIDL_user_free(v17);
          v8[v16] = 0;
        }
        ++v16;
      }
      while ( v16 < a2 );
      MIDL_user_free(v8);
    }
    else
    {
LABEL_12:
      *a3 = (unsigned __int16 **)v8;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140019e10  push    rbx
0x140019e12  push    rbp
0x140019e13  push    rsi
0x140019e14  push    rdi
0x140019e15  push    r12
0x140019e17  push    r13
0x140019e19  push    r14
0x140019e1b  push    r15
0x140019e1d  sub     rsp, 28h
0x140019e21  mov     edi, edx
0x140019e23  mov     r12, rcx
0x140019e26  shl     rdi, 3
0x140019e2a  mov     r14, r8
0x140019e2d  mov     rcx, rdi
0x140019e30  mov     r15d, edx
0x140019e33  call    DAF_user_alloc
0x140019e38  xor     r13d, r13d
0x140019e3b  mov     rsi, rax
0x140019e3e  test    rax, rax
0x140019e41  jnz     short loc_140019E4D
0x140019e43  mov     ebx, 8007000Eh
0x140019e48  jmp     loc_140019EE5
0x140019e4d  mov     r8, rdi; Size
0x140019e50  xor     edx, edx; Val
0x140019e52  mov     rcx, rsi; void *
0x140019e55  mov     ebx, r13d
0x140019e58  call    memset_0
0x140019e5d  mov     edi, r13d
0x140019e60  test    r15d, r15d
0x140019e63  jz      short loc_140019EE2
0x140019e65  mov     ebp, edi
0x140019e67  mov     rax, [r12+rbp*8]
0x140019e6b  test    rax, rax
0x140019e6e  jz      loc_140019EFF
0x140019e74  mov     edx, 3FFFFFFFh
0x140019e79  cmp     [rax], r13w
0x140019e7d  jz      short loc_140019E89
0x140019e7f  add     rax, 2
0x140019e83  sub     rdx, 1
0x140019e87  jnz     short loc_140019E79
0x140019e89  mov     rax, rdx
0x140019e8c  neg     rax
0x140019e8f  sbb     ebx, ebx
0x140019e91  not     ebx
0x140019e93  and     ebx, 80070057h
0x140019e99  test    rdx, rdx
0x140019e9c  jz      short loc_140019F04
0x140019e9e  mov     ecx, 3FFFFFFFh
0x140019ea3  sub     rcx, rdx
0x140019ea6  neg     rdx
0x140019ea9  sbb     rax, rax
0x140019eac  lea     rbx, [rcx+rcx]
0x140019eb0  and     rbx, rax
0x140019eb3  lea     rcx, [rbx+2]
0x140019eb7  call    DAF_user_alloc
0x140019ebc  mov     [rsi+rbp*8], rax
0x140019ec0  test    rax, rax
0x140019ec3  jz      short loc_140019EF8
0x140019ec5  mov     r8, [r12+rbp*8]; unsigned __int16 *
0x140019ec9  lea     rdx, [rbx+2]; unsigned __int64
0x140019ecd  mov     rcx, rax; unsigned __int16 *
0x140019ed0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140019ed5  mov     ebx, eax
0x140019ed7  test    eax, eax
0x140019ed9  js      short loc_140019F04
0x140019edb  inc     edi
0x140019edd  cmp     edi, r15d
0x140019ee0  jb      short loc_140019E65
0x140019ee2  mov     [r14], rsi
0x140019ee5  mov     eax, ebx
0x140019ee7  add     rsp, 28h
0x140019eeb  pop     r15
0x140019eed  pop     r14
0x140019eef  pop     r13
0x140019ef1  pop     r12
0x140019ef3  pop     rdi
0x140019ef4  pop     rsi
0x140019ef5  pop     rbp
0x140019ef6  pop     rbx
0x140019ef7  retn
0x140019ef8  mov     ebx, 8007000Eh
0x140019efd  jmp     short loc_140019F04
0x140019eff  mov     ebx, 80070057h
0x140019f04  mov     r14, rsi
0x140019f07  mov     edi, r13d
0x140019f0a  mov     ebp, edi
0x140019f0c  mov     rcx, [r14+rbp*8]; void *
0x140019f10  test    rcx, rcx
0x140019f13  jz      short loc_140019F1E
0x140019f15  call    MIDL_user_free
0x140019f1a  mov     [r14+rbp*8], r13
0x140019f1e  inc     edi
0x140019f20  cmp     edi, r15d
0x140019f23  jb      short loc_140019F0A
0x140019f25  mov     rcx, rsi; void *
0x140019f28  call    MIDL_user_free
0x140019f2d  jmp     short loc_140019EE5
```
