# FH4::DecompFuncInfo(uchar *,FH4::FuncInfo4 &,unsigned __int64,int,bool)

- ea: `0x18000cdac`
- end: `0x18000cea7`
- name: `?DecompFuncInfo@FH4@@YA_JPEAEAEAUFuncInfo4@1@_KH_N@Z`
- size: `251`
- prototype: `__int64 __fastcall(FH4 *__hidden this, unsigned __int8 *, struct FH4::FuncInfo4 *, unsigned __int64, char, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dae0`

## callees

- `0x18000cdac`

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
  __int64 v13; // rax
  _BYTE *v14; // r8
  __int64 v15; // rcx
  _DWORD *v16; // r8
  unsigned int v17; // r10d
  int v18; // ecx
  __int64 v19; // rcx

  v5 = *(_BYTE *)this;
  v6 = (char *)this + 1;
  *a2 = *(_BYTE *)this;
  if ( (v5 & 4) != 0 )
  {
    v9 = *v6 & 0xF;
    v6 -= *((char *)qword_1800814B8 + v9);
    *((_DWORD *)a2 + 1) = *((_DWORD *)v6 - 1) >> *((_BYTE *)&qword_1800814B8[2] + v9);
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
  v13 = *(int *)v6;
  if ( a5 || (v5 & 2) == 0 )
  {
    *((_DWORD *)a2 + 4) = v13;
  }
  else
  {
    v14 = (char *)a3 + v13;
    v15 = *v14 & 0xF;
    v16 = &v14[-*((char *)qword_1800814B8 + v15)];
    v17 = *(v16 - 1) >> *((_BYTE *)&qword_1800814B8[2] + v15);
    v18 = 0;
    *((_DWORD *)a2 + 4) = 0;
    if ( v17 )
    {
      while ( *v16 != a4 )
      {
        v16 += 2;
        if ( ++v18 >= v17 )
          goto LABEL_15;
      }
      *((_DWORD *)a2 + 4) = v16[1];
    }
  }
LABEL_15:
  if ( (v5 & 1) != 0 )
  {
    v19 = *v12 & 0xF;
    v12 -= *((char *)qword_1800814B8 + v19);
    *((_DWORD *)a2 + 5) = *((_DWORD *)v12 - 1) >> *((_BYTE *)&qword_1800814B8[2] + v19);
  }
  return v12 - (_BYTE *)this;
}

```

## disassembly

```asm
0x18000cdac  push    rbx
0x18000cdae  push    rbp
0x18000cdaf  push    rsi
0x18000cdb0  push    rdi
0x18000cdb1  mov     bl, [rcx]
0x18000cdb3  lea     r10, [rcx+1]
0x18000cdb7  mov     [rdx], bl
0x18000cdb9  mov     esi, r9d
0x18000cdbc  lea     rbp, cs:180000000h
0x18000cdc3  mov     r11, rdx
0x18000cdc6  mov     rdi, rcx
0x18000cdc9  test    bl, 4
0x18000cdcc  jz      short loc_18000CDF1
0x18000cdce  movzx   ecx, byte ptr [r10]
0x18000cdd2  and     ecx, 0Fh
0x18000cdd5  movsx   rax, byte ptr [rcx+rbp+814B8h]
0x18000cdde  mov     cl, [rcx+rbp+814C8h]
0x18000cde5  sub     r10, rax
0x18000cde8  mov     eax, [r10-4]
0x18000cdec  shr     eax, cl
0x18000cdee  mov     [rdx+4], eax
0x18000cdf1  test    bl, 8
0x18000cdf4  jz      short loc_18000CE00
0x18000cdf6  mov     eax, [r10]
0x18000cdf9  add     r10, 4
0x18000cdfd  mov     [rdx+8], eax
0x18000ce00  test    bl, 10h
0x18000ce03  jz      short loc_18000CE0F
0x18000ce05  mov     eax, [r10]
0x18000ce08  add     r10, 4
0x18000ce0c  mov     [rdx+0Ch], eax
0x18000ce0f  cmp     [rsp+20h+arg_20], 0
0x18000ce14  lea     rdx, [r10+4]
0x18000ce18  movsxd  rax, dword ptr [r10]
0x18000ce1b  jnz     short loc_18000CE71
0x18000ce1d  test    bl, 2
0x18000ce20  jz      short loc_18000CE71
0x18000ce22  add     r8, rax
0x18000ce25  movzx   ecx, byte ptr [r8]
0x18000ce29  and     ecx, 0Fh
0x18000ce2c  movsx   rax, byte ptr [rcx+rbp+814B8h]
0x18000ce35  mov     cl, [rcx+rbp+814C8h]
0x18000ce3c  sub     r8, rax
0x18000ce3f  mov     r10d, [r8-4]
0x18000ce43  shr     r10d, cl
0x18000ce46  xor     ecx, ecx
0x18000ce48  mov     dword ptr [r11+10h], 0
0x18000ce50  test    r10d, r10d
0x18000ce53  jz      short loc_18000CE75
0x18000ce55  mov     r9d, [r8+4]
0x18000ce59  cmp     [r8], esi
0x18000ce5c  jz      short loc_18000CE6B
0x18000ce5e  add     r8, 8
0x18000ce62  inc     ecx
0x18000ce64  cmp     ecx, r10d
0x18000ce67  jb      short loc_18000CE55
0x18000ce69  jmp     short loc_18000CE75
0x18000ce6b  mov     [r11+10h], r9d
0x18000ce6f  jmp     short loc_18000CE75
0x18000ce71  mov     [r11+10h], eax
0x18000ce75  test    bl, 1
0x18000ce78  jz      short loc_18000CE9C
0x18000ce7a  movzx   ecx, byte ptr [rdx]
0x18000ce7d  and     ecx, 0Fh
0x18000ce80  movsx   rax, byte ptr [rcx+rbp+814B8h]
0x18000ce89  mov     cl, [rcx+rbp+814C8h]
0x18000ce90  sub     rdx, rax
0x18000ce93  mov     eax, [rdx-4]
0x18000ce96  shr     eax, cl
0x18000ce98  mov     [r11+14h], eax
0x18000ce9c  sub     rdx, rdi
0x18000ce9f  mov     rax, rdx
0x18000cea2  pop     rdi
0x18000cea3  pop     rsi
0x18000cea4  pop     rbp
0x18000cea5  pop     rbx
0x18000cea6  retn
```
