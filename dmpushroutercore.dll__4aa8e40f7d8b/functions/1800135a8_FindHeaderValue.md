# FindHeaderValue

- ea: `0x1800135a8`
- end: `0x180013750`
- name: `FindHeaderValue`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019ce4`

## callees

- `0x1800127c4`
- `0x180013528`
- `0x1800135a8`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x180013727`
- `DMCmnUtils!CopyString` at `0x180013727`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800136e0`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800136e0`

## pseudocode

```c
__int64 __fastcall FindHeaderValue(unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // r15
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // r12
  unsigned __int16 *v13; // rcx
  int v14; // r8d
  unsigned __int16 v15; // ax
  int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v19; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v20; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v21; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v22; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v23; // [rsp+98h] [rbp+58h] BYREF

  v21 = a1;
  v19 = a1;
  v22 = 0;
  v5 = a1;
  if ( a3 )
  {
    *a3 = 0;
    if ( a2 )
    {
      v7 = a2;
      v8 = 0x7FFFFFFF;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v8;
      }
      while ( v8 );
      v6 = v8 == 0 ? 0x80070057 : 0;
      v9 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
      if ( v8 && a1 )
      {
        v10 = 0x7FFFFFFF;
        v11 = v5;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v10;
        }
        while ( v10 );
        v6 = v10 == 0 ? 0x80070057 : 0;
        if ( v10 )
        {
          v12 = &v5[(0x7FFFFFFF - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64)];
          while ( (unsigned int)FindEndOfHeader((const unsigned __int16 **)&v21, v12, &v22) )
          {
            v13 = v5;
            v14 = 0;
            if ( v22 )
            {
              while ( 1 )
              {
                v15 = *v13++;
                if ( v15 == 58 )
                  break;
                if ( ++v14 >= v22 )
                  goto LABEL_21;
              }
              v20 = v13;
              v23 = v13 - v5 - 1;
              v18 = v22 - v23;
              if ( (unsigned int)Trim((const unsigned __int16 **)&v19, &v23) )
              {
                if ( v23 == v9 && !InvStrCmpNIW(v19, a2, v9) )
                {
                  v16 = Trim((const unsigned __int16 **)&v20, &v18);
                  return (unsigned int)CopyString(v20, v16 != 0 ? v18 : 0, a3);
                }
              }
            }
LABEL_21:
            v5 = v21;
            v19 = v21;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x1800135a8  mov     [rsp-38h+arg_8], rbx
0x1800135ad  mov     [rsp-38h+arg_0], rcx
0x1800135b2  push    rbp
0x1800135b3  push    rsi
0x1800135b4  push    rdi
0x1800135b5  push    r12
0x1800135b7  push    r13
0x1800135b9  push    r14
0x1800135bb  push    r15
0x1800135bd  mov     rbp, rsp
0x1800135c0  sub     rsp, 40h
0x1800135c4  xor     r13d, r13d
0x1800135c7  mov     [rbp+var_18], rcx
0x1800135cb  mov     [rbp+arg_10], r13d
0x1800135cf  mov     rsi, r8
0x1800135d2  mov     r14, rdx
0x1800135d5  mov     rdi, rcx
0x1800135d8  test    r8, r8
0x1800135db  jnz     short loc_1800135E7
0x1800135dd  mov     ebx, 80004003h
0x1800135e2  jmp     loc_180013736
0x1800135e7  mov     [r8], r13
0x1800135ea  test    r14, r14
0x1800135ed  jz      loc_180013731
0x1800135f3  mov     r9d, 7FFFFFFFh
0x1800135f9  mov     rax, r14
0x1800135fc  mov     r8d, r9d
0x1800135ff  cmp     [rax], r13w
0x180013603  jz      short loc_18001360F
0x180013605  add     rax, 2
0x180013609  sub     r8, 1
0x18001360d  jnz     short loc_1800135FF
0x18001360f  mov     rax, r8
0x180013612  mov     edx, 80070057h
0x180013617  neg     rax
0x18001361a  mov     rcx, r9
0x18001361d  mov     rax, r8
0x180013620  sbb     ebx, ebx
0x180013622  sub     rcx, r8
0x180013625  not     ebx
0x180013627  and     ebx, edx
0x180013629  neg     rax
0x18001362c  sbb     r15, r15
0x18001362f  and     r15, rcx
0x180013632  test    r8, r8
0x180013635  jz      loc_180013736
0x18001363b  test    rdi, rdi
0x18001363e  jz      loc_180013736
0x180013644  mov     rcx, r9
0x180013647  mov     rax, rdi
0x18001364a  cmp     [rax], r13w
0x18001364e  jz      short loc_18001365A
0x180013650  add     rax, 2
0x180013654  sub     rcx, 1
0x180013658  jnz     short loc_18001364A
0x18001365a  mov     rax, rcx
0x18001365d  neg     rax
0x180013660  mov     rax, rcx
0x180013663  sbb     ebx, ebx
0x180013665  sub     r9, rcx
0x180013668  not     ebx
0x18001366a  and     ebx, edx
0x18001366c  neg     rax
0x18001366f  sbb     rdx, rdx
0x180013672  and     rdx, r9
0x180013675  test    rcx, rcx
0x180013678  jz      loc_180013736
0x18001367e  lea     r12, [rdi+rdx*2]
0x180013682  jmp     short loc_1800136F2
0x180013684  mov     edx, [rbp+arg_10]
0x180013687  mov     rcx, rdi
0x18001368a  mov     r8d, r13d
0x18001368d  test    edx, edx
0x18001368f  jz      short loc_1800136EA
0x180013691  movzx   eax, word ptr [rcx]
0x180013694  add     rcx, 2
0x180013698  cmp     ax, 3Ah ; ':'
0x18001369c  jz      short loc_1800136A8
0x18001369e  inc     r8d
0x1800136a1  cmp     r8d, edx
0x1800136a4  jb      short loc_180013691
0x1800136a6  jmp     short loc_1800136EA
0x1800136a8  mov     [rbp+var_10], rcx
0x1800136ac  sub     rcx, rdi
0x1800136af  sar     rcx, 1
0x1800136b2  lea     eax, [rcx-1]
0x1800136b5  sub     edx, eax
0x1800136b7  mov     [rbp+arg_18], eax
0x1800136ba  mov     [rbp+var_20], edx
0x1800136bd  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x1800136c1  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800136c5  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x1800136ca  test    eax, eax
0x1800136cc  jz      short loc_1800136EA
0x1800136ce  mov     eax, [rbp+arg_18]
0x1800136d1  cmp     rax, r15
0x1800136d4  jnz     short loc_1800136EA
0x1800136d6  mov     rcx, [rbp+var_18]
0x1800136da  mov     r8, r15
0x1800136dd  mov     rdx, r14
0x1800136e0  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1800136e6  test    eax, eax
0x1800136e8  jz      short loc_18001370C
0x1800136ea  mov     rdi, [rbp+arg_0]
0x1800136ee  mov     [rbp+var_18], rdi
0x1800136f2  lea     r8, [rbp+arg_10]; unsigned int *
0x1800136f6  mov     rdx, r12; unsigned __int16 *
0x1800136f9  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x1800136fd  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x180013702  test    eax, eax
0x180013704  jnz     loc_180013684
0x18001370a  jmp     short loc_180013736
0x18001370c  lea     rdx, [rbp+var_20]; unsigned int *
0x180013710  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x180013714  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x180013719  mov     rcx, [rbp+var_10]
0x18001371d  neg     eax
0x18001371f  mov     r8, rsi
0x180013722  sbb     edx, edx
0x180013724  and     edx, [rbp+var_20]
0x180013727  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001372d  mov     ebx, eax
0x18001372f  jmp     short loc_180013736
0x180013731  mov     ebx, 80070057h
0x180013736  mov     eax, ebx
0x180013738  mov     rbx, [rsp+40h+arg_8]
0x180013740  add     rsp, 40h
0x180013744  pop     r15
0x180013746  pop     r14
0x180013748  pop     r13
0x18001374a  pop     r12
0x18001374c  pop     rdi
0x18001374d  pop     rsi
0x18001374e  pop     rbp
0x18001374f  retn
```
