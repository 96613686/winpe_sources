# DecompressCBlockTo8X2

- ea: `0x180004dbc`
- end: `0x18000517e`
- name: `DecompressCBlockTo8X2`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005c30`

## callees

- `0x180004dbc`

## pseudocode

```c
unsigned __int8 *__fastcall DecompressCBlockTo8X2(int *a1, unsigned __int8 *a2, int *a3, int a4, _DWORD *a5)
{
  int v5; // eax
  unsigned __int8 v6; // r11
  __int64 v7; // r14
  unsigned __int8 *v8; // r10
  int v10; // edi
  unsigned __int8 *v11; // rdx
  int v13; // ecx
  int v14; // eax
  unsigned __int8 v15; // r9
  unsigned __int8 *v16; // r10
  int v17; // ecx
  unsigned __int8 v18; // al
  int v19; // ecx
  int v20; // esi
  int v21; // r9d
  unsigned __int8 v22; // dl
  int v23; // eax
  unsigned __int8 *v24; // r10
  unsigned __int8 v25; // cl
  int v26; // r11d
  int v27; // r12d
  int v28; // r15d
  char v29; // dl
  char v30; // al
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  unsigned __int8 *v34; // r10
  unsigned __int8 v35; // dl
  int v36; // ecx
  unsigned __int8 v37; // al
  int v38; // ecx
  int v39; // esi
  int v40; // r9d
  unsigned __int8 v41; // dl
  unsigned __int8 *v42; // r10
  int v43; // r15d
  int v44; // r11d
  int v45; // r8d
  char v46; // dl
  char v47; // al
  int v48; // ecx
  int v49; // eax
  int v50; // eax
  unsigned __int8 v51; // dl
  int v52; // eax
  int v53; // esi
  int v54; // r9d
  int v55; // r8d
  char v56; // dl
  char v57; // al
  int v58; // ecx
  int v59; // eax
  int v60; // eax
  unsigned __int8 *v61; // [rsp+38h] [rbp+10h]

  v5 = *a3;
  v6 = 0;
  v7 = a4;
  v8 = a2;
  if ( (unsigned int)*a3 > 1 )
  {
    v10 = *(unsigned __int16 *)a2;
    v5 -= 2;
    v11 = a2 + 2;
    *a3 = v5;
    if ( (v10 & 0x8000u) == 0 )
    {
      v8 = v11;
      goto LABEL_36;
    }
    if ( (v10 & 0xFFFFFC00) == 0x8400 )
    {
      *a5 = (v10 & 0x3FF) - 1;
      return v11;
    }
    if ( (v10 & 0xFFFFFC00) == 0x8000 )
    {
      v13 = (unsigned __int8)v10
          | (((unsigned __int8)v10 | (((unsigned __int8)v10 | ((unsigned __int8)v10 << 8)) << 8)) << 8);
      v14 = 8;
      do
      {
        *a1 = v13;
        a1[1] = v13;
        a1 = (int *)((char *)a1 + a4);
        --v14;
      }
      while ( v14 );
      return v11;
    }
    if ( v5 )
    {
      v15 = *v11;
      v17 = v5 - 1;
      *a3 = v5 - 1;
      v16 = v11 + 1;
      v61 = v11 + 1;
      if ( v5 != 1 )
      {
        v18 = *v16;
        v16 = v11 + 2;
        v19 = v17 - 1;
        v61 = v11 + 2;
        *a3 = v19;
LABEL_16:
        v20 = v18 | ((v18 | ((v18 | (v18 << 8)) << 8)) << 8);
        v21 = v20 ^ (v15 | ((v15 | ((v15 | (v15 << 8)) << 8)) << 8));
        if ( v19 )
        {
          v22 = *v16;
          v23 = v19 - 1;
          v24 = v16 + 1;
          *a3 = v19 - 1;
          v61 = v24;
          if ( v19 != 1 )
          {
            v25 = *v24;
            v61 = v24 + 1;
            *a3 = v23 - 1;
            goto LABEL_21;
          }
        }
        else
        {
          v22 = 0;
        }
        v25 = 0;
LABEL_21:
        v26 = 2;
        v27 = v25 | ((v25 | ((v25 | (v25 << 8)) << 8)) << 8);
        v28 = v27 ^ (v22 | ((v22 | ((v22 | (v22 << 8)) << 8)) << 8));
        do
        {
          v29 = v10;
          v30 = v10;
          LOWORD(v10) = (unsigned __int16)v10 >> 4;
          v31 = v20 ^ v21 & *((_DWORD *)Bits2Bytes + (v30 & 3));
          v32 = v28 & *((_DWORD *)Bits2Bytes + (v29 & 0xC));
          *a1 = v31;
          v33 = v27 ^ v32;
          *(int *)((char *)a1 + v7) = v31;
          a1[1] = v33;
          *(int *)((char *)a1 + v7 + 4) = v33;
          a1 = (int *)((char *)a1 + 2 * (int)v7);
          --v26;
        }
        while ( v26 );
        v34 = v61;
        if ( *a3 )
        {
          v35 = *v61;
          v34 = v61 + 1;
          v36 = *a3 - 1;
          ++v61;
          *a3 = v36;
          if ( v36 )
          {
            v37 = *v34++;
            v38 = v36 - 1;
            v61 = v34;
            *a3 = v38;
            goto LABEL_28;
          }
        }
        else
        {
          v35 = 0;
        }
        v37 = 0;
        v38 = 0;
LABEL_28:
        v39 = v37 | ((v37 | ((v37 | (v37 << 8)) << 8)) << 8);
        v40 = v39 ^ (v35 | ((v35 | ((v35 | (v35 << 8)) << 8)) << 8));
        if ( v38 )
        {
          v41 = *v34;
          v42 = v34 + 1;
          *a3 = v38 - 1;
          v61 = v42;
          if ( v38 != 1 )
          {
            LOBYTE(v26) = *v42;
            v61 = v42 + 1;
            *a3 = v38 - 2;
          }
        }
        else
        {
          v41 = 0;
        }
        v43 = 2;
        v44 = (unsigned __int8)v26
            | (((unsigned __int8)v26 | (((unsigned __int8)v26 | ((unsigned __int8)v26 << 8)) << 8)) << 8);
        v45 = v44 ^ (v41 | ((v41 | ((v41 | (v41 << 8)) << 8)) << 8));
        do
        {
          v46 = v10;
          v47 = v10;
          LOWORD(v10) = (unsigned __int16)v10 >> 4;
          v48 = v39 ^ v40 & *((_DWORD *)Bits2Bytes + (v47 & 3));
          v49 = v45 & *((_DWORD *)Bits2Bytes + (v46 & 0xC));
          *a1 = v48;
          v50 = v44 ^ v49;
          *(int *)((char *)a1 + v7) = v48;
          a1[1] = v50;
          *(int *)((char *)a1 + v7 + 4) = v50;
          a1 = (int *)((char *)a1 + 2 * (int)v7);
          --v43;
        }
        while ( v43 );
        return v61;
      }
    }
    else
    {
      v15 = 0;
      v61 = v11;
      v16 = v11;
    }
    v18 = 0;
    v19 = 0;
    goto LABEL_16;
  }
  LOWORD(v10) = 0;
LABEL_36:
  if ( v5 )
  {
    v51 = *v8++;
    v52 = v5 - 1;
    *a3 = v52;
    if ( v52 )
    {
      v6 = *v8++;
      *a3 = v52 - 1;
    }
  }
  else
  {
    v51 = 0;
  }
  v53 = 4;
  v54 = v6 | ((v6 | ((v6 | (v6 << 8)) << 8)) << 8);
  v55 = v54 ^ (v51 | ((v51 | ((v51 | (v51 << 8)) << 8)) << 8));
  do
  {
    v56 = v10;
    v57 = v10;
    LOWORD(v10) = (unsigned __int16)v10 >> 4;
    v58 = v54 ^ v55 & *((_DWORD *)Bits2Bytes + (v57 & 3));
    v59 = v55 & *((_DWORD *)Bits2Bytes + (v56 & 0xC));
    *a1 = v58;
    v60 = v54 ^ v59;
    *(int *)((char *)a1 + v7) = v58;
    a1[1] = v60;
    *(int *)((char *)a1 + v7 + 4) = v60;
    a1 = (int *)((char *)a1 + 2 * (int)v7);
    --v53;
  }
  while ( v53 );
  return v8;
}

```

## disassembly

```asm
0x180004dbc  mov     [rsp+arg_0], rbx
0x180004dc1  mov     [rsp+arg_18], rsi
0x180004dc6  push    rdi
0x180004dc7  push    r12
0x180004dc9  push    r13
0x180004dcb  push    r14
0x180004dcd  push    r15
0x180004dcf  mov     eax, [r8]
0x180004dd2  xor     r11d, r11d
0x180004dd5  movsxd  r14, r9d
0x180004dd8  mov     r10, rdx
0x180004ddb  mov     rbx, rcx
0x180004dde  cmp     eax, 1
0x180004de1  ja      short loc_180004DEC
0x180004de3  movzx   edi, r11w
0x180004de7  jmp     loc_1800050BC
0x180004dec  movzx   edi, word ptr [rdx]
0x180004def  add     eax, 0FFFFFFFEh
0x180004df2  add     rdx, 2
0x180004df6  mov     [r8], eax
0x180004df9  test    di, di
0x180004dfc  jns     loc_1800050B9
0x180004e02  mov     r9d, edi
0x180004e05  mov     ecx, edi
0x180004e07  and     r9d, 0FFFFFC00h
0x180004e0e  cmp     r9d, 8400h
0x180004e15  jnz     short loc_180004E2E
0x180004e17  mov     rax, [rsp+28h+arg_20]
0x180004e1c  and     ecx, 3FFh
0x180004e22  dec     ecx
0x180004e24  mov     [rax], ecx
0x180004e26  mov     rax, rdx
0x180004e29  jmp     loc_18000516A
0x180004e2e  cmp     r9d, 8000h
0x180004e35  jnz     short loc_180004E60
0x180004e37  movzx   eax, dil
0x180004e3b  mov     ecx, eax
0x180004e3d  shl     ecx, 8
0x180004e40  or      ecx, eax
0x180004e42  shl     ecx, 8
0x180004e45  or      ecx, eax
0x180004e47  shl     ecx, 8
0x180004e4a  or      ecx, eax
0x180004e4c  mov     eax, 8
0x180004e51  mov     [rbx], ecx
0x180004e53  mov     [rbx+4], ecx
0x180004e56  add     rbx, r14
0x180004e59  add     eax, 0FFFFFFFFh
0x180004e5c  jnz     short loc_180004E51
0x180004e5e  jmp     short loc_180004E26
0x180004e60  test    eax, eax
0x180004e62  jnz     short loc_180004E71
0x180004e64  mov     r9b, r11b
0x180004e67  mov     [rsp+28h+arg_8], rdx
0x180004e6c  mov     r10, rdx
0x180004e6f  jmp     short loc_180004E87
0x180004e71  mov     r9b, [rdx]
0x180004e74  lea     ecx, [rax-1]
0x180004e77  mov     [r8], ecx
0x180004e7a  lea     r10, [rdx+1]
0x180004e7e  mov     [rsp+28h+arg_8], r10
0x180004e83  test    ecx, ecx
0x180004e85  jnz     short loc_180004E8F
0x180004e87  mov     al, r11b
0x180004e8a  mov     ecx, r11d
0x180004e8d  jmp     short loc_180004E9F
0x180004e8f  mov     al, [r10]
0x180004e92  inc     r10
0x180004e95  dec     ecx
0x180004e97  mov     [rsp+28h+arg_8], r10
0x180004e9c  mov     [r8], ecx
0x180004e9f  movzx   eax, al
0x180004ea2  mov     esi, eax
0x180004ea4  shl     esi, 8
0x180004ea7  or      esi, eax
0x180004ea9  shl     esi, 8
0x180004eac  or      esi, eax
0x180004eae  shl     esi, 8
0x180004eb1  or      esi, eax
0x180004eb3  movzx   eax, r9b
0x180004eb7  mov     r9d, eax
0x180004eba  shl     r9d, 8
0x180004ebe  or      r9d, eax
0x180004ec1  shl     r9d, 8
0x180004ec5  or      r9d, eax
0x180004ec8  shl     r9d, 8
0x180004ecc  or      r9d, eax
0x180004ecf  xor     r9d, esi
0x180004ed2  test    ecx, ecx
0x180004ed4  jnz     short loc_180004EDB
0x180004ed6  mov     dl, r11b
0x180004ed9  jmp     short loc_180004EF0
0x180004edb  mov     dl, [r10]
0x180004ede  lea     eax, [rcx-1]
0x180004ee1  inc     r10
0x180004ee4  mov     [r8], eax
0x180004ee7  mov     [rsp+28h+arg_8], r10
0x180004eec  test    eax, eax
0x180004eee  jnz     short loc_180004EF5
0x180004ef0  mov     cl, r11b
0x180004ef3  jmp     short loc_180004F05
0x180004ef5  mov     cl, [r10]
0x180004ef8  inc     r10
0x180004efb  dec     eax
0x180004efd  mov     [rsp+28h+arg_8], r10
0x180004f02  mov     [r8], eax
0x180004f05  movzx   eax, cl
0x180004f08  mov     r13, r14
0x180004f0b  mov     r12d, eax
0x180004f0e  mov     r11d, 2
0x180004f14  shl     r12d, 8
0x180004f18  or      r12d, eax
0x180004f1b  shl     r12d, 8
0x180004f1f  or      r12d, eax
0x180004f22  shl     r12d, 8
0x180004f26  or      r12d, eax
0x180004f29  movzx   eax, dl
0x180004f2c  mov     r15d, eax
0x180004f2f  shl     r15d, 8
0x180004f33  or      r15d, eax
0x180004f36  shl     r15d, 8
0x180004f3a  or      r15d, eax
0x180004f3d  shl     r15d, 8
0x180004f41  or      r15d, eax
0x180004f44  lea     eax, [r14+r14]
0x180004f48  cdqe
0x180004f4a  lea     r14, Bits2Bytes
0x180004f51  mov     [rsp+28h+arg_10], rax
0x180004f56  mov     r10, rax
0x180004f59  xor     r15d, r12d
0x180004f5c  movzx   edx, di
0x180004f5f  mov     eax, edx
0x180004f61  shr     di, 4
0x180004f65  and     eax, 3
0x180004f68  and     edx, 0Ch
0x180004f6b  mov     ecx, [r14+rax*4]
0x180004f6f  mov     eax, [r14+rdx*4]
0x180004f73  and     ecx, r9d
0x180004f76  xor     ecx, esi
0x180004f78  and     eax, r15d
0x180004f7b  mov     [rbx], ecx
0x180004f7d  xor     eax, r12d
0x180004f80  mov     [rbx+r13], ecx
0x180004f84  mov     [rbx+4], eax
0x180004f87  mov     [rbx+r13+4], eax
0x180004f8c  add     rbx, r10
0x180004f8f  add     r11d, 0FFFFFFFFh
0x180004f93  jnz     short loc_180004F5C
0x180004f95  mov     ecx, [r8]
0x180004f98  mov     r10, [rsp+28h+arg_8]
0x180004f9d  test    ecx, ecx
0x180004f9f  jnz     short loc_180004FA6
0x180004fa1  mov     dl, r11b
0x180004fa4  jmp     short loc_180004FB9
0x180004fa6  mov     dl, [r10]
0x180004fa9  inc     r10
0x180004fac  sub     ecx, 1
0x180004faf  mov     [rsp+28h+arg_8], r10
0x180004fb4  mov     [r8], ecx
0x180004fb7  jnz     short loc_180004FC1
0x180004fb9  mov     al, r11b
0x180004fbc  mov     ecx, r11d
0x180004fbf  jmp     short loc_180004FD1
0x180004fc1  mov     al, [r10]
0x180004fc4  inc     r10
0x180004fc7  dec     ecx
0x180004fc9  mov     [rsp+28h+arg_8], r10
0x180004fce  mov     [r8], ecx
0x180004fd1  movzx   eax, al
0x180004fd4  mov     esi, eax
0x180004fd6  shl     esi, 8
0x180004fd9  or      esi, eax
0x180004fdb  shl     esi, 8
0x180004fde  or      esi, eax
0x180004fe0  shl     esi, 8
0x180004fe3  or      esi, eax
0x180004fe5  movzx   eax, dl
0x180004fe8  mov     r9d, eax
0x180004feb  shl     r9d, 8
0x180004fef  or      r9d, eax
0x180004ff2  shl     r9d, 8
0x180004ff6  or      r9d, eax
0x180004ff9  shl     r9d, 8
0x180004ffd  or      r9d, eax
0x180005000  xor     r9d, esi
0x180005003  test    ecx, ecx
0x180005005  jnz     short loc_18000500C
0x180005007  mov     dl, r11b
0x18000500a  jmp     short loc_180005031
0x18000500c  mov     dl, [r10]
0x18000500f  lea     eax, [rcx-1]
0x180005012  inc     r10
0x180005015  mov     [r8], eax
0x180005018  mov     [rsp+28h+arg_8], r10
0x18000501d  test    eax, eax
0x18000501f  jz      short loc_180005031
0x180005021  mov     r11b, [r10]
0x180005024  inc     r10
0x180005027  dec     eax
0x180005029  mov     [rsp+28h+arg_8], r10
0x18000502e  mov     [r8], eax
0x180005031  mov     r10, [rsp+28h+arg_10]
0x180005036  mov     r15d, 2
0x18000503c  movzx   eax, r11b
0x180005040  mov     r11d, eax
0x180005043  shl     r11d, 8
0x180005047  or      r11d, eax
0x18000504a  shl     r11d, 8
0x18000504e  or      r11d, eax
0x180005051  shl     r11d, 8
0x180005055  or      r11d, eax
0x180005058  movzx   eax, dl
0x18000505b  mov     r8d, eax
0x18000505e  shl     r8d, 8
0x180005062  or      r8d, eax
0x180005065  shl     r8d, 8
0x180005069  or      r8d, eax
0x18000506c  shl     r8d, 8
0x180005070  or      r8d, eax
0x180005073  xor     r8d, r11d
0x180005076  movzx   edx, di
0x180005079  mov     eax, edx
0x18000507b  shr     di, 4
0x18000507f  and     eax, 3
0x180005082  and     edx, 0Ch
0x180005085  mov     ecx, [r14+rax*4]
0x180005089  mov     eax, [r14+rdx*4]
0x18000508d  and     ecx, r9d
0x180005090  xor     ecx, esi
0x180005092  and     eax, r8d
0x180005095  mov     [rbx], ecx
0x180005097  xor     eax, r11d
0x18000509a  mov     [rbx+r13], ecx
0x18000509e  mov     [rbx+4], eax
0x1800050a1  mov     [rbx+r13+4], eax
0x1800050a6  add     rbx, r10
0x1800050a9  add     r15d, 0FFFFFFFFh
0x1800050ad  jnz     short loc_180005076
0x1800050af  mov     r10, [rsp+28h+arg_8]
0x1800050b4  jmp     loc_180005167
0x1800050b9  mov     r10, rdx
0x1800050bc  test    eax, eax
0x1800050be  jnz     short loc_1800050C5
0x1800050c0  mov     dl, r11b
0x1800050c3  jmp     short loc_1800050DE
0x1800050c5  mov     dl, [r10]
0x1800050c8  inc     r10
0x1800050cb  sub     eax, 1
0x1800050ce  mov     [r8], eax
0x1800050d1  jz      short loc_1800050DE
0x1800050d3  mov     r11b, [r10]
0x1800050d6  inc     r10
0x1800050d9  dec     eax
0x1800050db  mov     [r8], eax
0x1800050de  movzx   eax, r11b
0x1800050e2  mov     esi, 4
0x1800050e7  mov     r9d, eax
0x1800050ea  mov     r11, r14
0x1800050ed  shl     r9d, 8
0x1800050f1  or      r9d, eax
0x1800050f4  shl     r9d, 8
0x1800050f8  or      r9d, eax
0x1800050fb  shl     r9d, 8
0x1800050ff  or      r9d, eax
0x180005102  movzx   eax, dl
0x180005105  mov     r8d, eax
0x180005108  shl     r8d, 8
0x18000510c  or      r8d, eax
0x18000510f  shl     r8d, 8
0x180005113  or      r8d, eax
0x180005116  shl     r8d, 8
0x18000511a  or      r8d, eax
0x18000511d  lea     eax, [r14+r14]
0x180005121  movsxd  r15, eax
0x180005124  lea     r14, Bits2Bytes
0x18000512b  xor     r8d, r9d
0x18000512e  movzx   edx, di
0x180005131  mov     eax, edx
0x180005133  shr     di, 4
0x180005137  and     eax, 3
0x18000513a  and     edx, 0Ch
0x18000513d  mov     ecx, [r14+rax*4]
0x180005141  mov     eax, [r14+rdx*4]
0x180005145  and     ecx, r8d
0x180005148  xor     ecx, r9d
0x18000514b  and     eax, r8d
0x18000514e  mov     [rbx], ecx
0x180005150  xor     eax, r9d
0x180005153  mov     [r11+rbx], ecx
0x180005157  mov     [rbx+4], eax
0x18000515a  mov     [r11+rbx+4], eax
0x18000515f  add     rbx, r15
0x180005162  add     esi, 0FFFFFFFFh
0x180005165  jnz     short loc_18000512E
0x180005167  mov     rax, r10
0x18000516a  mov     rbx, [rsp+28h+arg_0]
0x18000516f  mov     rsi, [rsp+28h+arg_18]
0x180005174  pop     r15
0x180005176  pop     r14
0x180005178  pop     r13
  ... truncated ...
```
