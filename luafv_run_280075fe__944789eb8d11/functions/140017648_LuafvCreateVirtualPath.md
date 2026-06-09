# LuafvCreateVirtualPath

- ea: `0x140017648`
- end: `0x140017827`
- name: `LuafvCreateVirtualPath`
- size: `479`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x140018f70`
- `0x140022de8`

## callees

- `0x1400172c8`
- `0x140017648`
- `0x140017830`
- `0x140017e60`
- `0x140018080`
- `0x14002199c`
- `0x1400230a8`
- `0x140023d14`

## pseudocode

```c
__int64 __fastcall LuafvCreateVirtualPath(PFLT_INSTANCE Instance, struct _FLT_CALLBACK_DATA *a2, __m128i *a3)
{
  __int64 v3; // rax
  unsigned int v5; // r14d
  __int64 v8; // r9
  unsigned int v9; // esi
  int v10; // ebx
  char v11; // di
  unsigned __int16 v12; // dx
  char v13; // al
  int v14; // r14d
  int UserStorePath; // eax
  __m128i v17; // [rsp+30h] [rbp-48h] BYREF
  __m128i v18; // [rsp+40h] [rbp-38h] BYREF
  __int128 v19; // [rsp+50h] [rbp-28h] BYREF
  __int128 v20; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+58h]

  v3 = a3[6].m128i_i64[1];
  v17 = 0;
  v18 = 0;
  v5 = *(unsigned __int16 *)(v3 + 40);
  v21 = v5;
  v8 = 2;
  v19 = 0;
  v20 = 0;
  if ( *(_BYTE *)(v3 + 80) )
    v9 = 0;
  else
    v9 = v5 - *(unsigned __int16 *)(*(_QWORD *)(v3 + 16) + 88LL) - 2;
  v10 = 0;
  v11 = 1;
  v17 = a3[3];
  v12 = _mm_cvtsi128_si32(*a3);
  v18 = *a3;
  if ( v12 >= 2u && *(_WORD *)(v18.m128i_i64[1] + 2 * ((unsigned __int64)v12 >> 1) - 2) == 92 )
  {
    v17.m128i_i16[0] -= 2;
    v18.m128i_i16[0] = v12 - 2;
  }
  while ( 1 )
  {
    v13 = v11 ? LuafvSplitRootPathLeft(&v17, &v19, 0, v8) : LuafvSplitPathRight(&v17, &v19, 0, v8);
    if ( !v13 || !v11 && !(_WORD)v19 )
      break;
    if ( v17.m128i_u16[0] <= v5 )
    {
      if ( v17.m128i_u16[0] > v9 )
      {
        if ( v11 )
          LuafvSplitRootPathLeft(&v18, &v20, 0, v8);
        UserStorePath = LuafvCreateUserStorePath(Instance, 0, a3[6].m128i_i64[1]);
        goto LABEL_28;
      }
      if ( v17.m128i_u16[0] == v9 )
      {
        UserStorePath = LuafvCreateStoreRootPath(Instance);
LABEL_28:
        v10 = UserStorePath;
        goto LABEL_29;
      }
      v10 = 0;
LABEL_34:
      v11 = 0;
    }
    else
    {
      if ( v11 )
        LuafvSplitRootPathLeft(&v18, &v20, 0, v8);
      else
        LuafvSplitPathRight(&v18, &v20, 0, v8);
      v14 = LuafvCopyFile(Instance, a2, &v18, &v17, 0, 1);
      if ( v14 >= 0 )
        LuafvUpdateFileTableForFileChange(&v17, 0);
      v10 = 0;
      if ( v14 != -1073741771 )
        v10 = v14;
      v5 = v21;
LABEL_29:
      if ( v10 >= 0 )
        goto LABEL_34;
      if ( !v11 || v10 != -1073741766 )
        return (unsigned int)v10;
    }
  }
  if ( v10 >= 0 )
    LuafvLogUtcEvent(qword_14000E230, qword_14000E240, 0, a2, a3, 2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140017648  push    rbp
0x14001764a  push    rbx
0x14001764b  push    rsi
0x14001764c  push    rdi
0x14001764d  push    r12
0x14001764f  push    r13
0x140017651  push    r14
0x140017653  push    r15
0x140017655  mov     rbp, rsp
0x140017658  sub     rsp, 78h
0x14001765c  mov     rax, [r8+68h]
0x140017660  xorps   xmm0, xmm0
0x140017663  movups  [rbp+var_48], xmm0
0x140017667  mov     r15, r8
0x14001766a  xor     r8d, r8d
0x14001766d  movups  [rbp+var_38], xmm0
0x140017671  movzx   r14d, word ptr [rax+28h]
0x140017676  mov     r13, rdx
0x140017679  xorps   xmm1, xmm1
0x14001767c  mov     [rbp+arg_10], r14d
0x140017680  mov     r12, rcx
0x140017683  mov     r9d, 2
0x140017689  movups  [rbp+var_28], xmm1
0x14001768d  movups  [rbp+var_18], xmm1
0x140017691  cmp     [rax+50h], r8b
0x140017695  jz      short loc_14001769C
0x140017697  mov     esi, r8d
0x14001769a  jmp     short loc_1400176AC
0x14001769c  mov     rax, [rax+10h]
0x1400176a0  mov     esi, r14d
0x1400176a3  movzx   ecx, word ptr [rax+58h]
0x1400176a7  sub     esi, ecx
0x1400176a9  sub     esi, r9d
0x1400176ac  movups  xmm0, xmmword ptr [r15+30h]
0x1400176b1  mov     ebx, r8d
0x1400176b4  mov     dil, 1
0x1400176b7  movdqu  [rbp+var_48], xmm0
0x1400176bc  movups  xmm0, xmmword ptr [r15]
0x1400176c0  movd    edx, xmm0
0x1400176c4  movups  [rbp+var_38], xmm0
0x1400176c8  cmp     dx, r9w
0x1400176cc  jb      short loc_1400176F0
0x1400176ce  mov     rax, qword ptr [rbp+var_38+8]
0x1400176d2  movzx   ecx, dx
0x1400176d5  shr     rcx, 1
0x1400176d8  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400176de  jnz     short loc_1400176F0
0x1400176e0  mov     eax, 0FFFEh
0x1400176e5  add     dx, ax
0x1400176e8  add     word ptr [rbp+var_48], ax
0x1400176ec  mov     word ptr [rbp+var_38], dx
0x1400176f0  lea     rdx, [rbp+var_28]
0x1400176f4  lea     rcx, [rbp+var_48]
0x1400176f8  test    dil, dil
0x1400176fb  jz      short loc_140017704
0x1400176fd  call    LuafvSplitRootPathLeft
0x140017702  jmp     short loc_140017709
0x140017704  call    LuafvSplitPathRight
0x140017709  xor     r8d, r8d
0x14001770c  test    al, al
0x14001770e  jz      loc_1400177EC
0x140017714  test    dil, dil
0x140017717  jnz     short loc_140017724
0x140017719  cmp     word ptr [rbp+var_28], r8w
0x14001771e  jz      loc_1400177EC
0x140017724  movzx   eax, word ptr [rbp+var_48]
0x140017728  cmp     eax, r14d
0x14001772b  jbe     short loc_140017793
0x14001772d  lea     rdx, [rbp+var_18]
0x140017731  lea     rcx, [rbp+var_38]
0x140017735  test    dil, dil
0x140017738  jz      short loc_140017741
0x14001773a  call    LuafvSplitRootPathLeft
0x14001773f  jmp     short loc_140017746
0x140017741  call    LuafvSplitPathRight
0x140017746  mov     [rsp+78h+var_50], 1; char
0x14001774b  lea     r9, [rbp+var_48]
0x14001774f  lea     r8, [rbp+var_38]
0x140017753  mov     [rsp+78h+var_58], 0; __int64
0x14001775c  mov     rdx, r13
0x14001775f  mov     rcx, r12; Instance
0x140017762  call    LuafvCopyFile
0x140017767  xor     r8d, r8d
0x14001776a  mov     r14d, eax
0x14001776d  test    eax, eax
0x14001776f  js      short loc_14001777F
0x140017771  xor     edx, edx
0x140017773  lea     rcx, [rbp+var_48]
0x140017777  call    LuafvUpdateFileTableForFileChange
0x14001777c  xor     r8d, r8d
0x14001777f  cmp     r14d, 0C0000035h
0x140017786  mov     ebx, r8d
0x140017789  cmovnz  ebx, r14d
0x14001778d  mov     r14d, [rbp+arg_10]
0x140017791  jmp     short loc_1400177CA
0x140017793  cmp     eax, esi
0x140017795  jbe     short loc_1400177B9
0x140017797  test    dil, dil
0x14001779a  jz      short loc_1400177A9
0x14001779c  lea     rdx, [rbp+var_18]
0x1400177a0  lea     rcx, [rbp+var_38]
0x1400177a4  call    LuafvSplitRootPathLeft
0x1400177a9  mov     r8, [r15+68h]
0x1400177ad  xor     edx, edx
0x1400177af  mov     rcx, r12; Instance
0x1400177b2  call    LuafvCreateUserStorePath
0x1400177b7  jmp     short loc_1400177C5
0x1400177b9  jnz     short loc_1400177E1
0x1400177bb  xor     edx, edx
0x1400177bd  mov     rcx, r12; FltObject
0x1400177c0  call    LuafvCreateStoreRootPath
0x1400177c5  xor     r8d, r8d
0x1400177c8  mov     ebx, eax
0x1400177ca  test    ebx, ebx
0x1400177cc  jns     short loc_1400177E4
0x1400177ce  test    dil, dil
0x1400177d1  jz      short loc_140017813
0x1400177d3  cmp     ebx, 0C000003Ah
0x1400177d9  jz      loc_1400176F0
0x1400177df  jmp     short loc_140017813
0x1400177e1  mov     ebx, r8d
0x1400177e4  mov     dil, r8b
0x1400177e7  jmp     loc_1400176F0
0x1400177ec  test    ebx, ebx
0x1400177ee  js      short loc_140017813
0x1400177f0  mov     dword ptr [rsp+78h+var_50], 2
0x1400177f8  lea     rdx, qword_14000E240
0x1400177ff  mov     r9, r13
0x140017802  mov     [rsp+78h+var_58], r15
0x140017807  lea     rcx, qword_14000E230
0x14001780e  call    LuafvLogUtcEvent
0x140017813  mov     eax, ebx
0x140017815  add     rsp, 78h
0x140017819  pop     r15
0x14001781b  pop     r14
0x14001781d  pop     r13
0x14001781f  pop     r12
0x140017821  pop     rdi
0x140017822  pop     rsi
0x140017823  pop     rbx
0x140017824  pop     rbp
0x140017825  retn
```
