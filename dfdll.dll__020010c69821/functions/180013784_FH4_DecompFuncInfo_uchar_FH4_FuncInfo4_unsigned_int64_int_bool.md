# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x180013784`
- end: `0x1800138a6`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `290`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013e38`

## callees

- `0x180013784`

## pseudocode

```c
__int64 __fastcall FH4::DecompFuncInfo(FH4 *this, unsigned __int8 *a2, struct FH4::FuncInfo4 *a3, int a4, char a5)
{
  unsigned __int8 v5; // bl
  _BYTE *v6; // r10
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  _BYTE *v15; // r8
  int v16; // r9d
  __int64 v17; // rcx
  int *v18; // rdx
  unsigned int v19; // r10d
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rcx

  v5 = *(_BYTE *)this;
  v6 = (char *)this + 1;
  *a2 = *(_BYTE *)this;
  if ( (v5 & 4) != 0 )
  {
    v11 = *v6 & 0xF;
    v6 -= *((char *)&FH4::s_negLengthTab + v11);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
  }
  if ( (v5 & 8) != 0 )
  {
    v12 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 2) = v12;
  }
  if ( (v5 & 0x10) != 0 )
  {
    v13 = *(_DWORD *)v6;
    v6 += 4;
    *((_DWORD *)a2 + 3) = v13;
  }
  v14 = *(int *)v6;
  v15 = v6 + 4;
  v16 = 0;
  if ( a5 || (v5 & 2) == 0 )
  {
    *((_DWORD *)a2 + 4) = v14;
  }
  else
  {
    v17 = *((_BYTE *)a3 + v14) & 0xF;
    v18 = (int *)((char *)a3 + v14 - *((char *)&FH4::s_negLengthTab + v17));
    v19 = (unsigned int)*(v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
    *((_DWORD *)a2 + 4) = 0;
    if ( v19 )
    {
      while ( 1 )
      {
        v20 = *v18;
        v21 = v18[1];
        v18 += 2;
        if ( v20 == a4 )
          break;
        if ( ++v16 >= v19 )
          goto LABEL_15;
      }
      *((_DWORD *)a2 + 4) = v21;
    }
  }
LABEL_15:
  if ( (v5 & 1) != 0 )
  {
    v22 = *v15 & 0xF;
    v15 -= *((char *)&FH4::s_negLengthTab + v22);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v22);
  }
  return v15 - (_BYTE *)this;
}

```

## disassembly

```asm
0x180013784  mov     rax, rsp
0x180013787  mov     [rax+8], rbx
0x18001378b  mov     [rax+10h], rbp
0x18001378f  mov     [rax+18h], rsi
0x180013793  mov     [rax+20h], rdi
0x180013797  push    r14
0x180013799  mov     bl, [rcx]
0x18001379b  lea     r10, [rcx+1]
0x18001379f  mov     [rdx], bl
0x1800137a1  mov     esi, r9d
0x1800137a4  lea     r14, cs:180000000h
0x1800137ab  mov     rbp, r8
0x1800137ae  mov     r11, rdx
0x1800137b1  mov     rdi, rcx
0x1800137b4  test    bl, 4
0x1800137b7  jz      short loc_1800137DD
0x1800137b9  movzx   ecx, byte ptr [r10]
0x1800137bd  and     ecx, 0Fh
0x1800137c0  movsx   rax, byte ptr [rcx+r14+21B70h]
0x1800137c9  mov     cl, [rcx+r14+21B80h]
0x1800137d1  sub     r10, rax
0x1800137d4  mov     eax, [r10-4]
0x1800137d8  shr     eax, cl
0x1800137da  mov     [rdx+4], eax
0x1800137dd  test    bl, 8
0x1800137e0  jz      short loc_1800137EC
0x1800137e2  mov     eax, [r10]
0x1800137e5  add     r10, 4
0x1800137e9  mov     [rdx+8], eax
0x1800137ec  test    bl, 10h
0x1800137ef  jz      short loc_1800137FB
0x1800137f1  mov     eax, [r10]
0x1800137f4  add     r10, 4
0x1800137f8  mov     [rdx+0Ch], eax
0x1800137fb  movsxd  rax, dword ptr [r10]
0x1800137fe  lea     r8, [r10+4]
0x180013802  xor     r9d, r9d
0x180013805  cmp     [rsp+8+arg_20], r9b
0x18001380a  jnz     short loc_18001385C
0x18001380c  test    bl, 2
0x18001380f  jz      short loc_18001385C
0x180013811  lea     rdx, [rax+rbp]
0x180013815  movzx   ecx, byte ptr [rdx]
0x180013818  and     ecx, 0Fh
0x18001381b  movsx   rax, byte ptr [rcx+r14+21B70h]
0x180013824  mov     cl, [rcx+r14+21B80h]
0x18001382c  sub     rdx, rax
0x18001382f  mov     r10d, [rdx-4]
0x180013833  shr     r10d, cl
0x180013836  mov     [r11+10h], r9d
0x18001383a  test    r10d, r10d
0x18001383d  jz      short loc_18001385F
0x18001383f  mov     eax, [rdx]
0x180013841  mov     ecx, [rdx+4]
0x180013844  lea     rdx, [rdx+8]
0x180013848  cmp     eax, esi
0x18001384a  jz      short loc_180013856
0x18001384c  inc     r9d
0x18001384f  cmp     r9d, r10d
0x180013852  jb      short loc_18001383F
0x180013854  jmp     short loc_18001385F
0x180013856  mov     [r11+10h], ecx
0x18001385a  jmp     short loc_18001385F
0x18001385c  mov     [rdx+10h], eax
0x18001385f  test    bl, 1
0x180013862  jz      short loc_180013889
0x180013864  movzx   ecx, byte ptr [r8]
0x180013868  and     ecx, 0Fh
0x18001386b  movsx   rdx, byte ptr [rcx+r14+21B70h]
0x180013874  mov     cl, [rcx+r14+21B80h]
0x18001387c  sub     r8, rdx
0x18001387f  mov     edx, [r8-4]
0x180013883  shr     edx, cl
0x180013885  mov     [r11+14h], edx
0x180013889  mov     rbx, [rsp+8+arg_0]
0x18001388e  sub     r8, rdi
0x180013891  mov     rbp, [rsp+8+arg_8]
0x180013896  mov     rax, r8
0x180013899  mov     rsi, [rsp+8+arg_10]
0x18001389e  mov     rdi, [rsp+8+arg_18]
0x1800138a3  pop     r14
0x1800138a5  retn
```
