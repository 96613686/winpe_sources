# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180002024`
- end: `0x180002130`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `268`
- prototype: `__int64 __fastcall(FH4 *this, unsigned __int8 *, struct FH4::FuncInfo4 *, int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002720`

## callees

- `0x180002024`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // bl
  _BYTE *v6; // r10
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  _BYTE *v12; // rdx
  _BYTE *v13; // r8
  __int64 v14; // rcx
  _DWORD *v15; // r8
  unsigned int v16; // r10d
  int v17; // ecx
  __int64 v18; // rcx

  v5 = *(_BYTE *)this;
  v6 = (char *)this + 1;
  *a2 = *(_BYTE *)this;
  if ( (v5 & 4) != 0 )
  {
    v9 = *v6 & 0xF;
    v6 -= *((char *)&FH4::s_negLengthTab + v9);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v9);
  }
  if ( (v5 & 8) != 0 )
  {
    v10 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 2) = v10;
  }
  if ( (v5 & 0x10) != 0 )
  {
    v11 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 3) = v11;
  }
  v12 = v6 + 4;
  if ( a5 || (v5 & 2) == 0 )
  {
    *((_DWORD *)a2 + 4) = *(_DWORD *)v6;
  }
  else
  {
    *((_DWORD *)a2 + 4) = 0;
    if ( !*(_DWORD *)v6 )
      __fastfail(7u);
    v13 = (char *)a3 + *(int *)v6;
    v14 = *v13 & 0xF;
    v15 = &v13[-*((char *)&FH4::s_negLengthTab + v14)];
    v16 = *(v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    v17 = 0;
    if ( v16 )
    {
      while ( *v15 != a4 )
      {
        v15 += 2;
        if ( ++v17 >= v16 )
          goto LABEL_17;
      }
      *((_DWORD *)a2 + 4) = v15[1];
    }
  }
LABEL_17:
  if ( (v5 & 1) != 0 )
  {
    v18 = *v12 & 0xF;
    v12 -= *((char *)&FH4::s_negLengthTab + v18);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v18);
  }
  return v12 - (_BYTE *)this;
}

```

## disassembly

```asm
0x180002024  push    rbx
0x180002026  push    rbp
0x180002027  push    rsi
0x180002028  push    rdi
0x180002029  mov     bl, [rcx]
0x18000202b  lea     r10, [rcx+1]
0x18000202f  mov     [rdx], bl
0x180002031  mov     esi, r9d
0x180002034  lea     rbp, cs:180000000h
0x18000203b  mov     r11, rdx
0x18000203e  mov     rdi, rcx
0x180002041  test    bl, 4
0x180002044  jz      short loc_180002069
0x180002046  movzx   ecx, byte ptr [r10]
0x18000204a  and     ecx, 0Fh
0x18000204d  movsx   rax, byte ptr [rcx+rbp+10238h]
0x180002056  mov     cl, [rcx+rbp+10248h]
0x18000205d  sub     r10, rax
0x180002060  mov     eax, [r10-4]
0x180002064  shr     eax, cl
0x180002066  mov     [rdx+4], eax
0x180002069  test    bl, 8
0x18000206c  jz      short loc_180002078
0x18000206e  mov     eax, [r10]
0x180002071  add     r10, 4
0x180002075  mov     [rdx+8], eax
0x180002078  test    bl, 10h
0x18000207b  jz      short loc_180002087
0x18000207d  mov     eax, [r10]
0x180002080  add     r10, 4
0x180002084  mov     [rdx+0Ch], eax
0x180002087  xor     r9d, r9d
0x18000208a  lea     rdx, [r10+4]
0x18000208e  cmp     [rsp+20h+arg_20], r9b
0x180002093  jnz     short loc_1800020F7
0x180002095  test    bl, 2
0x180002098  jz      short loc_1800020F7
0x18000209a  mov     [r11+10h], r9d
0x18000209e  cmp     [r10], r9d
0x1800020a1  jz      short loc_1800020EE
0x1800020a3  movsxd  rax, dword ptr [r10]
0x1800020a6  add     r8, rax
0x1800020a9  movzx   ecx, byte ptr [r8]
0x1800020ad  and     ecx, 0Fh
0x1800020b0  movsx   rax, byte ptr [rcx+rbp+10238h]
0x1800020b9  mov     cl, [rcx+rbp+10248h]
0x1800020c0  sub     r8, rax
0x1800020c3  mov     r10d, [r8-4]
0x1800020c7  shr     r10d, cl
0x1800020ca  mov     ecx, r9d
0x1800020cd  test    r10d, r10d
0x1800020d0  jz      short loc_1800020FE
0x1800020d2  mov     r9d, [r8+4]
0x1800020d6  cmp     [r8], esi
0x1800020d9  jz      short loc_1800020E8
0x1800020db  add     r8, 8
0x1800020df  inc     ecx
0x1800020e1  cmp     ecx, r10d
0x1800020e4  jb      short loc_1800020D2
0x1800020e6  jmp     short loc_1800020FE
0x1800020e8  mov     [r11+10h], r9d
0x1800020ec  jmp     short loc_1800020FE
0x1800020ee  mov     ecx, 7
0x1800020f3  int     29h; Win8: RtlFailFast(ecx)
0x1800020f5  jmp     short loc_1800020FE
0x1800020f7  mov     eax, [r10]
0x1800020fa  mov     [r11+10h], eax
0x1800020fe  test    bl, 1
0x180002101  jz      short loc_180002125
0x180002103  movzx   ecx, byte ptr [rdx]
0x180002106  and     ecx, 0Fh
0x180002109  movsx   rax, byte ptr [rcx+rbp+10238h]
0x180002112  mov     cl, [rcx+rbp+10248h]
0x180002119  sub     rdx, rax
0x18000211c  mov     eax, [rdx-4]
0x18000211f  shr     eax, cl
0x180002121  mov     [r11+14h], eax
0x180002125  sub     rdx, rdi
0x180002128  mov     rax, rdx
0x18000212b  pop     rdi
0x18000212c  pop     rsi
0x18000212d  pop     rbp
0x18000212e  pop     rbx
0x18000212f  retn
```
