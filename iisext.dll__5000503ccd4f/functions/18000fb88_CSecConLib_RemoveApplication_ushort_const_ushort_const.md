# CSecConLib::RemoveApplication(ushort const *,ushort const *)

- ea: `0x18000fb88`
- end: `0x18000fd5e`
- name: `?RemoveApplication@CSecConLib@@QEAAJPEBG0@Z`
- size: `470`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009a10`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000f02c`
- `0x18000f1c0`
- `0x18000fb88`
- `0x18001011c`
- `0x1800111a2`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000fc84`
- `msvcrt!_wcsnicmp` at `0x18000fc84`
- `msvcrt!wcscpy_s` at `0x18000fcc1`
- `msvcrt!wcscpy_s` at `0x18000fcc1`

## pseudocode

```c
__int64 __fastcall CSecConLib::RemoveApplication(
        CSecConLib *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rdi
  int inited; // ebx
  __int64 v7; // r14
  wchar_t *v8; // rax
  const wchar_t *v9; // rbx
  char v10; // r13
  wchar_t *v11; // r12
  unsigned int v12; // r14d
  size_t v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  int v16; // eax
  void *Src; // [rsp+30h] [rbp-48h] BYREF
  size_t v19; // [rsp+38h] [rbp-40h]
  void *Block; // [rsp+40h] [rbp-38h]
  unsigned int v22; // [rsp+98h] [rbp+20h] BYREF

  Src = 0;
  v4 = -1;
  v22 = 0;
  do
    ++v4;
  while ( a2[v4] );
  inited = CSecConLib::InternalInitIfNecessary(this);
  if ( inited >= 0 )
  {
    inited = CSecConLib::GetMultiSZPropVal(this, a3, 0x877u, (unsigned __int16 **)&Src, &v22);
    if ( inited >= 0 )
    {
      v7 = v22;
      v8 = (wchar_t *)operator new[](saturated_mul(v22, 2u));
      v9 = v8;
      if ( v8 )
      {
        Block = v8;
        v10 = 0;
        memcpy_0(v8, Src, 2 * v7);
        v11 = (wchar_t *)Src;
        v12 = 1;
        if ( *v9 )
        {
          v13 = (unsigned int)v4;
          v19 = (unsigned int)v4;
          do
          {
            v14 = -1;
            do
              ++v14;
            while ( v9[v14] );
            v15 = (unsigned int)(v14 + 1);
            if ( _wcsnicmp(a2, v9, v13) || v9[v19] != 59 )
            {
              if ( !v11 )
              {
                inited = -2147024882;
                goto LABEL_24;
              }
              wcscpy_s(v11, v22 - (((char *)v11 - (_BYTE *)Src) >> 1), v9);
              v11 += v15;
              *v11 = 0;
              v12 += v15;
            }
            else
            {
              v10 = 1;
            }
            v9 += (unsigned int)v15;
            v13 = v19;
          }
          while ( *v9 );
          if ( !v10 )
            goto LABEL_23;
          if ( v12 >= 3 )
            v16 = CSecConLib::SetMultiSZPropVal(this, a3, 0x877u, (unsigned __int16 *)Src, v12);
          else
            v16 = CSecConLib::SetMultiSZPropVal(this, a3, 0x877u, 0, 0);
          inited = v16;
        }
        else
        {
LABEL_23:
          inited = -2146646015;
        }
LABEL_24:
        operator delete(Block);
      }
      else
      {
        inited = -2147024882;
      }
    }
    if ( Src )
      operator delete(Src);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000fb88  mov     rax, rsp
0x18000fb8b  mov     [rax+8], rbx
0x18000fb8f  mov     [rax+18h], rbp
0x18000fb93  mov     [rax+10h], rdx
0x18000fb97  push    rdi
0x18000fb98  push    r12
0x18000fb9a  push    r13
0x18000fb9c  push    r14
0x18000fb9e  push    r15
0x18000fba0  sub     rsp, 50h
0x18000fba4  xor     r12d, r12d
0x18000fba7  mov     r15, r8
0x18000fbaa  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000fbae  mov     [rax-48h], r12
0x18000fbb2  mov     rdi, r13
0x18000fbb5  mov     [rax+20h], r12d
0x18000fbb9  mov     rbp, rcx
0x18000fbbc  inc     rdi
0x18000fbbf  cmp     [rdx+rdi*2], r12w
0x18000fbc4  jnz     short loc_18000FBBC
0x18000fbc6  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000fbcb  mov     ebx, eax
0x18000fbcd  test    eax, eax
0x18000fbcf  js      loc_18000FD42
0x18000fbd5  lea     rax, [rsp+78h+arg_18]
0x18000fbdd  mov     r8d, 877h; unsigned int
0x18000fbe3  lea     r9, [rsp+78h+Src]; unsigned __int16 **
0x18000fbe8  mov     [rsp+78h+var_58], rax; unsigned int *
0x18000fbed  mov     rdx, r15; unsigned __int16 *
0x18000fbf0  mov     rcx, rbp; this
0x18000fbf3  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18000fbf8  mov     ebx, eax
0x18000fbfa  test    eax, eax
0x18000fbfc  js      loc_18000FD31
0x18000fc02  mov     r14d, [rsp+78h+arg_18]
0x18000fc0a  mov     eax, 2
0x18000fc0f  mul     r14
0x18000fc12  cmovb   rax, r13
0x18000fc16  mov     rcx, rax; unsigned __int64
0x18000fc19  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fc1e  mov     rbx, rax
0x18000fc21  test    rax, rax
0x18000fc24  jnz     short loc_18000FC30
0x18000fc26  mov     ebx, 8007000Eh
0x18000fc2b  jmp     loc_18000FD31
0x18000fc30  mov     rdx, [rsp+78h+Src]; Src
0x18000fc35  lea     r8, [r14+r14]; Size
0x18000fc39  mov     rcx, rbx; void *
0x18000fc3c  mov     [rsp+78h+Block], rbx
0x18000fc41  mov     r13b, r12b
0x18000fc44  call    memcpy_0
0x18000fc49  mov     r12, [rsp+78h+Src]
0x18000fc4e  xor     edx, edx
0x18000fc50  mov     r14d, 1
0x18000fc56  cmp     [rbx], dx
0x18000fc59  jz      loc_18000FD1F
0x18000fc5f  mov     ecx, edi
0x18000fc61  mov     [rsp+78h+var_40], rcx
0x18000fc66  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fc6a  inc     rax
0x18000fc6d  cmp     [rbx+rax*2], dx
0x18000fc71  jnz     short loc_18000FC6A
0x18000fc73  mov     r8, rcx; MaxCount
0x18000fc76  lea     edi, [rax+1]
0x18000fc79  mov     rcx, [rsp+78h+String1]; String1
0x18000fc81  mov     rdx, rbx; String2
0x18000fc84  call    cs:__imp__wcsnicmp
0x18000fc8a  xor     edx, edx
0x18000fc8c  test    eax, eax
0x18000fc8e  jnz     short loc_18000FCA1
0x18000fc90  mov     rax, [rsp+78h+var_40]
0x18000fc95  cmp     word ptr [rbx+rax*2], 3Bh ; ';'
0x18000fc9a  jnz     short loc_18000FCA1
0x18000fc9c  mov     r13b, 1
0x18000fc9f  jmp     short loc_18000FCD5
0x18000fca1  test    r12, r12
0x18000fca4  jz      short loc_18000FD18
0x18000fca6  mov     edx, [rsp+78h+arg_18]
0x18000fcad  mov     rax, r12
0x18000fcb0  sub     rax, [rsp+78h+Src]
0x18000fcb5  mov     r8, rbx; Source
0x18000fcb8  sar     rax, 1
0x18000fcbb  mov     rcx, r12; Destination
0x18000fcbe  sub     rdx, rax; SizeInWords
0x18000fcc1  call    cs:__imp_wcscpy_s
0x18000fcc7  xor     edx, edx
0x18000fcc9  lea     r12, [r12+rdi*2]
0x18000fccd  mov     [r12], dx
0x18000fcd2  add     r14d, edi
0x18000fcd5  mov     ecx, edi
0x18000fcd7  lea     rbx, [rbx+rcx*2]
0x18000fcdb  mov     rcx, [rsp+78h+var_40]
0x18000fce0  cmp     [rbx], dx
0x18000fce3  jnz     short loc_18000FC66
0x18000fce5  test    r13b, r13b
0x18000fce8  jz      short loc_18000FD1F
0x18000fcea  mov     r8d, 877h; unsigned int
0x18000fcf0  mov     rcx, rbp; this
0x18000fcf3  cmp     r14d, 3
0x18000fcf7  jnb     short loc_18000FD0C
0x18000fcf9  mov     dword ptr [rsp+78h+var_58], edx; unsigned int
0x18000fcfd  xor     r9d, r9d; unsigned __int16 *
0x18000fd00  mov     rdx, r15; unsigned __int16 *
0x18000fd03  call    ?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z; CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)
0x18000fd08  mov     ebx, eax
0x18000fd0a  jmp     short loc_18000FD24
0x18000fd0c  mov     r9, [rsp+78h+Src]
0x18000fd11  mov     dword ptr [rsp+78h+var_58], r14d
0x18000fd16  jmp     short loc_18000FD00
0x18000fd18  mov     ebx, 8007000Eh
0x18000fd1d  jmp     short loc_18000FD24
0x18000fd1f  mov     ebx, 800CC801h
0x18000fd24  mov     rcx, [rsp+78h+Block]; Block
0x18000fd29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fd2e  xor     r12d, r12d
0x18000fd31  cmp     [rsp+78h+Src], r12
0x18000fd36  jz      short loc_18000FD42
0x18000fd38  mov     rcx, [rsp+78h+Src]; Block
0x18000fd3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fd42  lea     r11, [rsp+78h+var_28]
0x18000fd47  mov     eax, ebx
0x18000fd49  mov     rbx, [r11+30h]
0x18000fd4d  mov     rbp, [r11+40h]
0x18000fd51  mov     rsp, r11
0x18000fd54  pop     r15
0x18000fd56  pop     r14
0x18000fd58  pop     r13
0x18000fd5a  pop     r12
0x18000fd5c  pop     rdi
0x18000fd5d  retn
```
