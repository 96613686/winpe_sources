# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1800169d8`
- end: `0x180016b60`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800158cc`
- `0x180015eb4`
- `0x180016554`

## callees

- `0x1800169d8`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= *((char *)qword_180082058 + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_180082058[2] + v5);
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= *((char *)qword_180082058 + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_180082058[2] + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - *((char *)qword_180082058 + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&qword_180082058[2] + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)qword_180082058 + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&qword_180082058[2] + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)qword_180082058 + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&qword_180082058[2] + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x1800169d8  xor     eax, eax
0x1800169da  lea     r11, cs:180000000h
0x1800169e1  mov     [rcx+18h], al
0x1800169e4  xorps   xmm0, xmm0
0x1800169e7  mov     [rcx+1Ch], rax
0x1800169eb  mov     r8, rcx
0x1800169ee  mov     [rcx+24h], rax
0x1800169f2  movups  xmmword ptr [rcx+30h], xmm0
0x1800169f6  mov     rax, [rcx+8]
0x1800169fa  mov     r10b, [rax]
0x1800169fd  lea     rdx, [rax+1]
0x180016a01  mov     [rcx+18h], r10b
0x180016a05  mov     [rcx+8], rdx
0x180016a09  test    r10b, 1
0x180016a0d  jz      short loc_180016A36
0x180016a0f  movzx   ecx, byte ptr [rdx]
0x180016a12  and     ecx, 0Fh
0x180016a15  movsx   rax, byte ptr [rcx+r11+82058h]
0x180016a1e  mov     cl, [rcx+r11+82068h]
0x180016a26  sub     rdx, rax
0x180016a29  mov     eax, [rdx-4]
0x180016a2c  shr     eax, cl
0x180016a2e  mov     [r8+1Ch], eax
0x180016a32  mov     [r8+8], rdx
0x180016a36  test    r10b, 2
0x180016a3a  jz      short loc_180016A4A
0x180016a3c  mov     eax, [rdx]
0x180016a3e  add     rdx, 4
0x180016a42  mov     [r8+8], rdx
0x180016a46  mov     [r8+20h], eax
0x180016a4a  test    r10b, 4
0x180016a4e  jz      short loc_180016A77
0x180016a50  movzx   ecx, byte ptr [rdx]
0x180016a53  and     ecx, 0Fh
0x180016a56  movsx   rax, byte ptr [rcx+r11+82058h]
0x180016a5f  mov     cl, [rcx+r11+82068h]
0x180016a67  sub     rdx, rax
0x180016a6a  mov     eax, [rdx-4]
0x180016a6d  shr     eax, cl
0x180016a6f  mov     [r8+24h], eax
0x180016a73  mov     [r8+8], rdx
0x180016a77  mov     eax, [rdx]
0x180016a79  lea     r9, [rdx+4]
0x180016a7d  mov     [r8+28h], eax
0x180016a81  mov     al, r10b
0x180016a84  and     al, 30h
0x180016a86  mov     [r8+8], r9
0x180016a8a  test    r10b, 8
0x180016a8e  jz      short loc_180016ACB
0x180016a90  cmp     al, 10h
0x180016a92  jnz     short loc_180016AA4
0x180016a94  movsxd  rcx, dword ptr [r9]
0x180016a97  lea     rax, [r9+4]
0x180016a9b  mov     [r8+8], rax
0x180016a9f  mov     [r8+30h], rcx
0x180016aa3  retn
0x180016aa4  cmp     al, 20h ; ' '
0x180016aa6  jnz     locret_180016B5F
0x180016aac  movsxd  rax, dword ptr [r9]
0x180016aaf  lea     rdx, [r9+4]
0x180016ab3  mov     [r8+8], rdx
0x180016ab7  mov     [r8+30h], rax
0x180016abb  lea     rax, [rdx+4]
0x180016abf  movsxd  rcx, dword ptr [rdx]
0x180016ac2  mov     [r8+8], rax
0x180016ac6  jmp     loc_180016B5B
0x180016acb  cmp     al, 10h
0x180016acd  jnz     short loc_180016AFF
0x180016acf  movzx   ecx, byte ptr [r9]
0x180016ad3  and     ecx, 0Fh
0x180016ad6  movsx   rax, byte ptr [rcx+r11+82058h]
0x180016adf  mov     cl, [rcx+r11+82068h]
0x180016ae7  sub     r9, rax
0x180016aea  mov     eax, [r8+48h]
0x180016aee  mov     edx, [r9-4]
0x180016af2  shr     edx, cl
0x180016af4  add     eax, edx
0x180016af6  mov     [r8+8], r9
0x180016afa  mov     [r8+30h], rax
0x180016afe  retn
0x180016aff  cmp     al, 20h ; ' '
0x180016b01  jnz     short locret_180016B5F
0x180016b03  movzx   ecx, byte ptr [r9]
0x180016b07  mov     edx, [r8+48h]
0x180016b0b  and     ecx, 0Fh
0x180016b0e  movsx   rax, byte ptr [rcx+r11+82058h]
0x180016b17  mov     cl, [rcx+r11+82068h]
0x180016b1f  sub     r9, rax
0x180016b22  mov     eax, [r9-4]
0x180016b26  shr     eax, cl
0x180016b28  mov     [r8+8], r9
0x180016b2c  lea     ecx, [rdx+rax]
0x180016b2f  mov     [r8+30h], rcx
0x180016b33  movzx   ecx, byte ptr [r9]
0x180016b37  and     ecx, 0Fh
0x180016b3a  movsx   rax, byte ptr [rcx+r11+82058h]
0x180016b43  mov     cl, [rcx+r11+82068h]
0x180016b4b  sub     r9, rax
0x180016b4e  mov     eax, [r9-4]
0x180016b52  shr     eax, cl
0x180016b54  mov     [r8+8], r9
0x180016b58  lea     ecx, [rdx+rax]
0x180016b5b  mov     [r8+38h], rcx
0x180016b5f  retn
```
