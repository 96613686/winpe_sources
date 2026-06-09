# MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)

- ea: `0x140019c5c`
- end: `0x140019da8`
- name: `?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z`
- size: `332`
- prototype: `__int64 __fastcall(struct _DEVPROPERTY *, unsigned int, struct _DEVPROPERTY **)`
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b5d4`
- `0x14000b7c4`
- `0x14000c350`
- `0x14000ceec`
- `0x14000deb0`
- `0x14000ef44`
- `0x14000f074`
- `0x14000faa8`

## callees

- `0x1400020d0`
- `0x140009060`
- `0x140019ac8`
- `0x140019c5c`
- `0x14001a068`

## pseudocode

```c
__int64 __fastcall MidlCopyDevProperties(struct _DEVPROPERTY *a1, unsigned int a2, struct _DEVPROPERTY **a3)
{
  size_t v6; // rbp
  struct _DEVPROPERTY *v7; // rax
  signed int v8; // ebx
  unsigned int v10; // r14d
  struct _DEVPROPERTY *v11; // rax
  __int64 v12; // rbp
  unsigned __int8 *LocaleName; // rcx
  __int64 v14; // r9
  PCWSTR v15; // rax

  v6 = 48 * a2;
  v7 = (struct _DEVPROPERTY *)DAF_user_alloc(v6);
  *a3 = v7;
  if ( v7 )
  {
    v8 = 0;
    memset_0(v7, 0, v6);
    v10 = 0;
    if ( !a2 )
      return (unsigned int)v8;
    while ( 1 )
    {
      v11 = *a3;
      v12 = v10;
      v11[v12].CompKey.Key.fmtid = a1[v12].CompKey.Key.fmtid;
      *(_OWORD *)&v11[v12].CompKey.Key.pid = *(_OWORD *)&a1[v12].CompKey.Key.pid;
      *(_OWORD *)&v11[v12].Type = *(_OWORD *)&a1[v12].Type;
      (*a3)[v12].CompKey.LocaleName = 0;
      (*a3)[v12].Buffer = 0;
      v8 = MidlCopyBuffer((unsigned __int8 *)a1[v12].Buffer, a1[v12].BufferSize, (unsigned __int8 **)&(*a3)[v12].Buffer);
      if ( v8 < 0 )
        break;
      LocaleName = (unsigned __int8 *)a1[v12].CompKey.LocaleName;
      if ( LocaleName )
      {
        v14 = 0x7FFFFFFF;
        v15 = a1[v12].CompKey.LocaleName;
        do
        {
          if ( !*v15 )
            break;
          ++v15;
          --v14;
        }
        while ( v14 );
        v8 = v14 == 0 ? 0x80070057 : 0;
        if ( !v14 )
          break;
        v8 = MidlCopyBuffer(
               LocaleName,
               v14 != 0 ? (unsigned int)(-2 - 2 * v14) + 2LL : 2LL,
               (unsigned __int8 **)&(*a3)[v12].CompKey.LocaleName);
        if ( v8 < 0 )
          break;
      }
      if ( ++v10 >= a2 )
        return (unsigned int)v8;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  if ( *a3 )
  {
    MidlFreeDevProperties(*a3, a2);
    *a3 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140019c5c  push    rbx
0x140019c5e  push    rbp
0x140019c5f  push    rsi
0x140019c60  push    rdi
0x140019c61  push    r12
0x140019c63  push    r14
0x140019c65  push    r15
0x140019c67  sub     rsp, 20h
0x140019c6b  lea     eax, [rdx+rdx*2]
0x140019c6e  mov     r15, rcx
0x140019c71  shl     eax, 4
0x140019c74  mov     rsi, r8
0x140019c77  mov     ecx, eax
0x140019c79  mov     edi, edx
0x140019c7b  mov     ebp, eax
0x140019c7d  call    DAF_user_alloc
0x140019c82  xor     r12d, r12d
0x140019c85  mov     [rsi], rax
0x140019c88  test    rax, rax
0x140019c8b  jnz     short loc_140019CB5
0x140019c8d  mov     ebx, 8007000Eh
0x140019c92  mov     rcx, [rsi]; struct _DEVPROPERTY *
0x140019c95  test    rcx, rcx
0x140019c98  jz      short loc_140019CA4
0x140019c9a  mov     edx, edi; unsigned int
0x140019c9c  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x140019ca1  mov     [rsi], r12
0x140019ca4  mov     eax, ebx
0x140019ca6  add     rsp, 20h
0x140019caa  pop     r15
0x140019cac  pop     r14
0x140019cae  pop     r12
0x140019cb0  pop     rdi
0x140019cb1  pop     rsi
0x140019cb2  pop     rbp
0x140019cb3  pop     rbx
0x140019cb4  retn
0x140019cb5  mov     r8, rbp; Size
0x140019cb8  xor     edx, edx; Val
0x140019cba  mov     rcx, rax; void *
0x140019cbd  mov     ebx, r12d
0x140019cc0  call    memset_0
0x140019cc5  mov     r14d, r12d
0x140019cc8  test    edi, edi
0x140019cca  jz      short loc_140019CA4
0x140019ccc  mov     eax, r14d
0x140019ccf  lea     rbp, [rax+rax*2]
0x140019cd3  mov     rax, [rsi]
0x140019cd6  shl     rbp, 4
0x140019cda  movups  xmm0, xmmword ptr [r15+rbp]
0x140019cdf  movups  xmmword ptr [rax+rbp], xmm0
0x140019ce3  movups  xmm1, xmmword ptr [r15+rbp+10h]
0x140019ce9  movups  xmmword ptr [rax+rbp+10h], xmm1
0x140019cee  movups  xmm0, xmmword ptr [r15+rbp+20h]
0x140019cf4  movups  xmmword ptr [rax+rbp+20h], xmm0
0x140019cf9  mov     rax, [rsi]
0x140019cfc  mov     [rax+rbp+18h], r12
0x140019d01  mov     rax, [rsi]
0x140019d04  mov     [rax+rbp+28h], r12
0x140019d09  mov     r8, [rsi]
0x140019d0c  mov     edx, [r15+rbp+24h]; Size
0x140019d11  add     r8, 28h ; '('
0x140019d15  mov     rcx, [r15+rbp+28h]; Src
0x140019d1a  add     r8, rbp; unsigned __int8 **
0x140019d1d  call    ?MidlCopyBuffer@@YAJPEAE_KPEAPEAE@Z; MidlCopyBuffer(uchar *,unsigned __int64,uchar * *)
0x140019d22  mov     ebx, eax
0x140019d24  test    eax, eax
0x140019d26  js      loc_140019C92
0x140019d2c  mov     rcx, [r15+rbp+18h]; Src
0x140019d31  test    rcx, rcx
0x140019d34  jz      short loc_140019D97
0x140019d36  mov     r9d, 7FFFFFFFh
0x140019d3c  mov     rax, rcx
0x140019d3f  cmp     [rax], r12w
0x140019d43  jz      short loc_140019D4F
0x140019d45  add     rax, 2
0x140019d49  sub     r9, 1
0x140019d4d  jnz     short loc_140019D3F
0x140019d4f  mov     rax, r9
0x140019d52  neg     rax
0x140019d55  sbb     ebx, ebx
0x140019d57  not     ebx
0x140019d59  and     ebx, 80070057h
0x140019d5f  test    r9, r9
0x140019d62  jz      loc_140019C92
0x140019d68  mov     r8, [rsi]
0x140019d6b  lea     eax, [r9+r9]
0x140019d6f  add     r8, 18h
0x140019d73  mov     edx, 0FFFFFFFEh
0x140019d78  sub     edx, eax
0x140019d7a  add     r8, rbp; unsigned __int8 **
0x140019d7d  neg     r9
0x140019d80  sbb     eax, eax
0x140019d82  and     edx, eax
0x140019d84  add     rdx, 2; Size
0x140019d88  call    ?MidlCopyBuffer@@YAJPEAE_KPEAPEAE@Z; MidlCopyBuffer(uchar *,unsigned __int64,uchar * *)
0x140019d8d  mov     ebx, eax
0x140019d8f  test    eax, eax
0x140019d91  js      loc_140019C92
0x140019d97  inc     r14d
0x140019d9a  cmp     r14d, edi
0x140019d9d  jb      loc_140019CCC
0x140019da3  jmp     loc_140019CA4
```
