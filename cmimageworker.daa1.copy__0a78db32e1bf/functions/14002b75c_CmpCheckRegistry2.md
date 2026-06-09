# CmpCheckRegistry2

- ea: `0x14002b75c`
- end: `0x14002bae9`
- name: `CmpCheckRegistry2`
- size: `909`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a338`

## callees

- `0x14002a580`
- `0x14002b61c`
- `0x14002b75c`
- `0x14002d7d4`
- `0x14002d9bc`
- `0x14002dae8`
- `0x14003135c`
- `0x140031378`
- `0x140031390`
- `0x140031b88`
- `0x140034010`

## pseudocode

```c
__int64 __fastcall CmpCheckRegistry2(__int64 a1, __int64 a2, int a3, int a4, char a5, __int64 a6, __int64 a7, int *a8)
{
  __int64 v10; // rax
  __int64 v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rsi
  int *v14; // rcx
  unsigned int v15; // r15d
  int v16; // r12d
  int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  int SubKeyByNumber; // eax
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  int v28; // r8d
  unsigned int v29; // r11d
  int v30; // r9d
  bool v31; // cf
  int v33; // [rsp+20h] [rbp-58h]
  char v34; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v35; // [rsp+88h] [rbp+10h] BYREF
  int v36; // [rsp+98h] [rbp+20h]

  v36 = a4;
  v35 = 0;
  HvpGetCellContextInitialize(&v34);
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(a1 + 24))(10240, 0, 1935887683);
  v11 = v10;
  if ( v10 )
  {
    v13 = a7;
    LOBYTE(v36) = 0;
    if ( a7 )
      *(_QWORD *)(a7 + 232) = v10;
    v14 = a8;
    *(_DWORD *)v10 = a3;
    v15 = 0;
    *(_DWORD *)(v10 + 4) = -1;
    v16 = 1;
    *(_DWORD *)(v10 + 8) = -1;
    *v14 = 0;
    *(_DWORD *)(v10 + 12) = 0;
    *(_BYTE *)(v10 + 16) = 0;
    while ( 1 )
    {
      if ( !*(_BYTE *)(v11 + 20LL * v15 + 16) )
      {
        v17 = *v14;
        *(_BYTE *)(v11 + 20LL * v15 + 16) = 1;
        if ( v17 != -1 )
          *v14 = v17 + 1;
        v18 = CmpCheckKey(a1, 1638400, *(_DWORD *)(v11 + 20LL * v15), *(_DWORD *)(v11 + 20LL * v15 + 4), a5, a6, v13);
        v12 = v18;
        if ( v18 == -2147483606 )
        {
          LOBYTE(v36) = 1;
        }
        else
        {
          if ( (int)(v18 + 0x80000000) >= 0 && v18 != -1073741492 )
            goto LABEL_51;
          if ( v18 == -1073741492 )
          {
            v27 = 16;
LABEL_35:
            SetFailureLocation(v13, v16, 13, v12, v27);
            if ( !v15 )
            {
              v12 = v29;
              SetFailureLocation(v13, 0, v28, v29, 24);
              goto LABEL_51;
            }
            SubKeyByNumber = CmpRemoveSubKeyCellNoCellRef(
                               a1,
                               *(unsigned int *)(v11 + 20LL * v15 + 4),
                               *(unsigned int *)(v11 + 20LL * v15));
            v12 = SubKeyByNumber;
            if ( SubKeyByNumber >= 0 )
            {
              v12 = -1073741267;
              *(_DWORD *)(*(_QWORD *)(a1 + 64) + 4088LL) |= 4u;
              goto LABEL_51;
            }
            v33 = 32;
LABEL_38:
            v30 = SubKeyByNumber;
            goto LABEL_50;
          }
        }
        if ( v15 )
        {
          v19 = *(unsigned int *)(v11 + 20LL * v15 - 12);
          if ( (_DWORD)v19 != -1 )
          {
            v12 = CmpCheckLexicographicalOrder(a1, v19, *(unsigned int *)(v11 + 20LL * v15));
            if ( (int)(v12 + 0x80000000) >= 0 && v12 != -1073741492 )
            {
              v33 = 37;
              goto LABEL_49;
            }
            if ( v12 == -1073741492 )
            {
              v16 = 0;
              v12 = -1073741492;
              v27 = 48;
              goto LABEL_35;
            }
          }
          *(_DWORD *)(v11 + 20LL * v15 - 12) = *(_DWORD *)(v11 + 20LL * v15);
        }
      }
      v20 = *(unsigned int *)(v11 + 20LL * v15);
      v21 = (*(_BYTE *)(a1 + 140) & 1) != 0 ? HvpGetCellFlat(a1, v20, &v34) : HvpGetCellPaged(a1, v20, &v34);
      if ( !v21 )
        break;
      v23 = *(unsigned int *)(v11 + 20LL * v15 + 12);
      if ( (unsigned int)v23 >= *(_DWORD *)(v21 + 20) )
      {
        v26 = -1;
      }
      else
      {
        SubKeyByNumber = CmpFindSubKeyByNumber(a1, v21, v23, &v35);
        v12 = SubKeyByNumber;
        if ( SubKeyByNumber < 0 )
        {
          v33 = 80;
          goto LABEL_38;
        }
        v22 = v35;
        if ( v35 == -1 )
        {
          v30 = -1073741670;
          v33 = 88;
          v12 = -1073741670;
          goto LABEL_50;
        }
        ++*(_DWORD *)(v11 + 20LL * v15 + 12);
        if ( v15 == 511 )
        {
          v33 = 96;
          goto LABEL_48;
        }
        v25 = 5 * (v15 + 1LL);
        *(_DWORD *)(v11 + 4 * v25 + 4) = *(_DWORD *)(v11 + 20LL * v15);
        v26 = 1;
        *(_DWORD *)(v11 + 4 * v25) = v22;
        *(_DWORD *)(v11 + 4 * v25 + 8) = -1;
        *(_DWORD *)(v11 + 4 * v25 + 12) = 0;
        *(_BYTE *)(v11 + 4 * v25 + 16) = 0;
      }
      v15 += v26;
      if ( (v15 & 0x80000000) != 0 )
      {
        SubKeyByNumber = CmpCheckAndFixSecurityCellsRefcount(a1, v22, 0);
        v12 = SubKeyByNumber;
        if ( SubKeyByNumber >= 0 )
        {
          v31 = (_BYTE)v36 != 0;
          LOBYTE(v36) = -(char)v36;
          v12 = v31 ? 0x8000002A : 0;
          goto LABEL_51;
        }
        v33 = 112;
        goto LABEL_38;
      }
      v14 = a8;
    }
    v33 = 64;
LABEL_48:
    v12 = -1073741492;
LABEL_49:
    v30 = v12;
LABEL_50:
    SetFailureLocation(v13, 0, 13, v30, v33);
LABEL_51:
    (*(void (__fastcall **)(__int64, __int64))(a1 + 32))(v11, 10240);
  }
  else
  {
    v12 = -1073741670;
    SetFailureLocation(a7, 0, 13, -1073741670, 0);
  }
  return v12;
}

```

## disassembly

```asm
0x14002b75c  mov     rax, rsp
0x14002b75f  mov     [rax+18h], rbx
0x14002b763  mov     [rax+20h], r9d
0x14002b767  mov     [rax+10h], edx
0x14002b76a  push    rbp
0x14002b76b  push    rsi
0x14002b76c  push    rdi
0x14002b76d  push    r12
0x14002b76f  push    r13
0x14002b771  push    r14
0x14002b773  push    r15
0x14002b775  sub     rsp, 40h
0x14002b779  mov     r14, rcx
0x14002b77c  mov     dword ptr [rax+10h], 0
0x14002b783  lea     rcx, [rax+8]
0x14002b787  mov     ebx, r8d
0x14002b78a  call    HvpGetCellContextInitialize
0x14002b78f  mov     rax, [r14+18h]
0x14002b793  mov     ecx, 2800h
0x14002b798  xor     edx, edx
0x14002b79a  mov     r8d, 73634D43h
0x14002b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b7a5  xor     r8d, r8d
0x14002b7a8  mov     rdi, rax
0x14002b7ab  test    rax, rax
0x14002b7ae  jnz     short loc_14002B7D6
0x14002b7b0  mov     rcx, [rsp+78h+arg_30]
0x14002b7b8  mov     r9d, 0C000009Ah
0x14002b7be  mov     [rsp+78h+var_58], r8d
0x14002b7c3  xor     edx, edx
0x14002b7c5  lea     r8d, [rax+0Dh]
0x14002b7c9  mov     ebx, r9d
0x14002b7cc  call    SetFailureLocation
0x14002b7d1  jmp     loc_14002BACE
0x14002b7d6  mov     rsi, [rsp+78h+arg_30]
0x14002b7de  mov     byte ptr [rsp+78h+arg_18], r8b
0x14002b7e6  test    rsi, rsi
0x14002b7e9  jz      short loc_14002B7F2
0x14002b7eb  mov     [rsi+0E8h], rdi
0x14002b7f2  mov     rcx, [rsp+78h+arg_38]
0x14002b7fa  or      r9d, 0FFFFFFFFh
0x14002b7fe  mov     [rax], ebx
0x14002b800  mov     r15d, r8d
0x14002b803  mov     [rax+4], r9d
0x14002b807  mov     r12d, 1
0x14002b80d  mov     [rax+8], r9d
0x14002b811  mov     [rcx], r8d
0x14002b814  mov     [rax+0Ch], r8d
0x14002b818  mov     [rax+10h], r8b
0x14002b81c  mov     r13d, r15d
0x14002b81f  lea     rbp, ds:0[r13*4]
0x14002b827  add     rbp, r13
0x14002b82a  cmp     [rdi+rbp*4+10h], r8b
0x14002b82f  jnz     loc_14002B901
0x14002b835  mov     eax, [rcx]
0x14002b837  mov     [rdi+rbp*4+10h], r12b
0x14002b83c  cmp     eax, r9d
0x14002b83f  jnb     short loc_14002B845
0x14002b841  inc     eax
0x14002b843  mov     [rcx], eax
0x14002b845  mov     rax, [rsp+78h+arg_28]
0x14002b84d  mov     edx, 190000h
0x14002b852  mov     r9d, [rdi+rbp*4+4]
0x14002b857  mov     rcx, r14
0x14002b85a  mov     r8d, [rdi+rbp*4]
0x14002b85e  mov     [rsp+78h+var_48], rsi
0x14002b863  mov     [rsp+78h+var_50], rax
0x14002b868  mov     al, [rsp+78h+arg_20]
0x14002b86f  mov     byte ptr [rsp+78h+var_58], al
0x14002b873  call    CmpCheckKey
0x14002b878  mov     ebx, eax
0x14002b87a  cmp     eax, 8000002Ah
0x14002b87f  jnz     short loc_14002B88B
0x14002b881  mov     byte ptr [rsp+78h+arg_18], r12b
0x14002b889  jmp     short loc_14002B8B1
0x14002b88b  mov     r10d, 80000000h
0x14002b891  mov     r11d, 0C000014Ch
0x14002b897  add     eax, r10d
0x14002b89a  test    r10d, eax
0x14002b89d  jnz     short loc_14002B8A8
0x14002b89f  cmp     ebx, r11d
0x14002b8a2  jnz     loc_14002BABD
0x14002b8a8  cmp     ebx, r11d
0x14002b8ab  jz      loc_14002B9E0
0x14002b8b1  test    r15d, r15d
0x14002b8b4  jz      short loc_14002B901
0x14002b8b6  lea     r13, [r13+r13*4+0]
0x14002b8bb  mov     edx, [rdi+r13*4-0Ch]
0x14002b8c0  cmp     edx, 0FFFFFFFFh
0x14002b8c3  jz      short loc_14002B8F9
0x14002b8c5  mov     r8d, [rdi+rbp*4]
0x14002b8c9  mov     rcx, r14
0x14002b8cc  call    CmpCheckLexicographicalOrder
0x14002b8d1  mov     r10d, 80000000h
0x14002b8d7  mov     ebx, eax
0x14002b8d9  add     eax, r10d
0x14002b8dc  mov     r11d, 0C000014Ch
0x14002b8e2  test    r10d, eax
0x14002b8e5  jnz     short loc_14002B8F0
0x14002b8e7  cmp     ebx, r11d
0x14002b8ea  jnz     loc_14002B9C6
0x14002b8f0  cmp     ebx, r11d
0x14002b8f3  jz      loc_14002B9D3
0x14002b8f9  mov     eax, [rdi+rbp*4]
0x14002b8fc  mov     [rdi+r13*4-0Ch], eax
0x14002b901  lea     r8, [rsp+78h+arg_0]
0x14002b909  mov     edx, [rdi+rbp*4]
0x14002b90c  mov     rcx, r14
0x14002b90f  test    [r14+8Ch], r12b
0x14002b916  jz      short loc_14002B91F
0x14002b918  call    HvpGetCellFlat
0x14002b91d  jmp     short loc_14002B924
0x14002b91f  call    HvpGetCellPaged
0x14002b924  test    rax, rax
0x14002b927  jz      loc_14002BA9D
0x14002b92d  mov     r8d, [rdi+rbp*4+0Ch]
0x14002b932  cmp     r8d, [rax+14h]
0x14002b936  jnb     short loc_14002B9A6
0x14002b938  lea     r9, [rsp+78h+arg_8]
0x14002b940  mov     rdx, rax
0x14002b943  mov     rcx, r14
0x14002b946  call    CmpFindSubKeyByNumber
0x14002b94b  xor     r8d, r8d
0x14002b94e  mov     ebx, eax
0x14002b950  test    eax, eax
0x14002b952  js      loc_14002BA6A
0x14002b958  mov     edx, [rsp+78h+arg_8]
0x14002b95f  or      r9d, 0FFFFFFFFh
0x14002b963  cmp     edx, r9d
0x14002b966  jz      loc_14002BA57
0x14002b96c  add     [rdi+rbp*4+0Ch], r12d
0x14002b971  cmp     r15d, 1FFh
0x14002b978  jz      loc_14002BA4D
0x14002b97e  mov     eax, r15d
0x14002b981  add     rax, r12
0x14002b984  lea     rcx, [rax+rax*4]
0x14002b988  mov     eax, [rdi+rbp*4]
0x14002b98b  mov     [rdi+rcx*4+4], eax
0x14002b98f  mov     eax, r12d
0x14002b992  mov     [rdi+rcx*4], edx
0x14002b995  mov     [rdi+rcx*4+8], r9d
0x14002b99a  mov     [rdi+rcx*4+0Ch], r8d
0x14002b99f  mov     [rdi+rcx*4+10h], r8b
0x14002b9a4  jmp     short loc_14002B9B0
0x14002b9a6  or      eax, 0FFFFFFFFh
0x14002b9a9  xor     r8d, r8d
0x14002b9ac  or      r9d, 0FFFFFFFFh
0x14002b9b0  add     r15d, eax
0x14002b9b3  js      loc_14002BA74
0x14002b9b9  mov     rcx, [rsp+78h+arg_38]
0x14002b9c1  jmp     loc_14002B81C
0x14002b9c6  mov     [rsp+78h+var_58], 25h ; '%'
0x14002b9ce  jmp     loc_14002BAAA
0x14002b9d3  xor     r12d, r12d
0x14002b9d6  mov     ebx, r11d
0x14002b9d9  lea     eax, [r12+30h]
0x14002b9de  jmp     short loc_14002B9E5
0x14002b9e0  mov     eax, 10h
0x14002b9e5  mov     r9d, ebx
0x14002b9e8  mov     [rsp+78h+var_58], eax
0x14002b9ec  mov     r8d, 0Dh
0x14002b9f2  mov     edx, r12d
0x14002b9f5  mov     rcx, rsi
0x14002b9f8  call    SetFailureLocation
0x14002b9fd  test    r15d, r15d
0x14002ba00  jz      short loc_14002BA3D
0x14002ba02  mov     r8d, [rdi+rbp*4]
0x14002ba06  mov     rcx, r14
0x14002ba09  mov     edx, [rdi+rbp*4+4]
0x14002ba0d  call    CmpRemoveSubKeyCellNoCellRef
0x14002ba12  mov     ebx, eax
0x14002ba14  test    eax, eax
0x14002ba16  jns     short loc_14002BA28
0x14002ba18  mov     [rsp+78h+var_58], 20h ; ' '
0x14002ba20  mov     r9d, eax
0x14002ba23  jmp     loc_14002BAAD
0x14002ba28  mov     rax, [r14+40h]
0x14002ba2c  mov     ebx, 0C000022Dh
0x14002ba31  or      dword ptr [rax+0FF8h], 4
0x14002ba38  jmp     loc_14002BABD
0x14002ba3d  mov     ebx, r11d
0x14002ba40  mov     [rsp+78h+var_58], 18h
0x14002ba48  mov     r9d, r11d
0x14002ba4b  jmp     short loc_14002BAB3
0x14002ba4d  mov     [rsp+78h+var_58], 60h ; '`'
0x14002ba55  jmp     short loc_14002BAA5
0x14002ba57  mov     r9d, 0C000009Ah
0x14002ba5d  mov     [rsp+78h+var_58], 58h ; 'X'
0x14002ba65  mov     ebx, r9d
0x14002ba68  jmp     short loc_14002BAAD
0x14002ba6a  mov     [rsp+78h+var_58], 50h ; 'P'
0x14002ba72  jmp     short loc_14002BA20
0x14002ba74  mov     rcx, r14
0x14002ba77  call    CmpCheckAndFixSecurityCellsRefcount
0x14002ba7c  mov     ebx, eax
0x14002ba7e  test    eax, eax
0x14002ba80  jns     short loc_14002BA8C
0x14002ba82  mov     [rsp+78h+var_58], 70h ; 'p'
0x14002ba8a  jmp     short loc_14002BA20
0x14002ba8c  neg     byte ptr [rsp+78h+arg_18]
0x14002ba93  sbb     ebx, ebx
0x14002ba95  and     ebx, 8000002Ah
0x14002ba9b  jmp     short loc_14002BABD
0x14002ba9d  mov     [rsp+78h+var_58], 40h ; '@'
0x14002baa5  mov     ebx, 0C000014Ch
0x14002baaa  mov     r9d, ebx
0x14002baad  mov     r8d, 0Dh
0x14002bab3  xor     edx, edx
0x14002bab5  mov     rcx, rsi
0x14002bab8  call    SetFailureLocation
0x14002babd  mov     rax, [r14+20h]
0x14002bac1  mov     edx, 2800h
0x14002bac6  mov     rcx, rdi
0x14002bac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bace  mov     eax, ebx
0x14002bad0  mov     rbx, [rsp+78h+arg_10]
0x14002bad8  add     rsp, 40h
0x14002badc  pop     r15
0x14002bade  pop     r14
0x14002bae0  pop     r13
0x14002bae2  pop     r12
0x14002bae4  pop     rdi
0x14002bae5  pop     rsi
0x14002bae6  pop     rbp
0x14002bae7  retn
```
