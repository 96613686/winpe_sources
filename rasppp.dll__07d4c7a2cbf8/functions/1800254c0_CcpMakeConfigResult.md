# CcpMakeConfigResult

- ea: `0x1800254c0`
- end: `0x18002572f`
- name: `CcpMakeConfigResult`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006080`
- `0x180024b08`
- `0x1800254c0`
- `0x180025738`
- `0x180032460`

## pseudocode

```c
__int64 __fastcall CcpMakeConfigResult(_DWORD *a1, unsigned __int8 *a2, char *a3, int a4, int a5)
{
  _BYTE *v5; // r14
  unsigned int v7; // ecx
  ULONG v8; // esi
  unsigned __int8 *v9; // r13
  int *v10; // rdi
  int v11; // eax
  int v12; // edx
  unsigned int v14; // edx
  int v15; // ebx
  char v16; // r12
  __int64 result; // rax
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  unsigned int v21; // edx
  char v22; // al
  unsigned int v23; // r14d
  __int64 v24; // rdx
  unsigned __int8 *v25; // r8
  __int16 v26; // r9
  ULONG v27; // [rsp+30h] [rbp-58h]
  int v28; // [rsp+34h] [rbp-54h]
  ULONG pulResult; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v30; // [rsp+98h] [rbp+10h]
  int v31; // [rsp+A0h] [rbp+18h] BYREF
  int v32; // [rsp+A8h] [rbp+20h]

  v32 = a4;
  v5 = a2 + 4;
  v7 = 0;
  v27 = a4 - 4;
  v8 = a4 - 4;
  pulResult = a4 - 4;
  v9 = (unsigned __int8 *)(a3 + 4);
  v10 = a1 + 287;
  v11 = a2[3] - 4;
  v12 = a2[2] << 8;
  v31 = 0;
  v14 = v11 + v12;
  a1[287] = 0;
  v15 = 2;
  v16 = 3;
  while ( 1 )
  {
    v30 = v7;
    if ( v14 < 2 )
      break;
    v28 = v14 - (unsigned __int8)v5[1];
    if ( v28 < 0 )
      return 722;
    result = CcpCheckOption(a1, (__int64)(a1 + 194), v5, &v31, 1);
    if ( (_DWORD)result )
      return result;
    v18 = v31;
    if ( v15 == 2 && v31 != 2 )
      goto LABEL_9;
    if ( v15 != 3 )
      goto LABEL_10;
    if ( v31 == 4 )
    {
LABEL_9:
      v8 = v27;
      v9 = (unsigned __int8 *)(a3 + 4);
      pulResult = v27;
      v15 = v31;
LABEL_10:
      if ( v31 == 4 )
        goto LABEL_18;
    }
    if ( *v5 != 0xFF )
    {
      v19 = *v10;
      if ( *v5 )
      {
        if ( *v5 == 18 )
          v20 = v19 | 1;
        else
          v20 = v19 | 4;
      }
      else
      {
        v20 = v19 | 2;
      }
      *v10 = v20;
    }
LABEL_18:
    if ( v18 == v15 && (v18 == 4 || v18 == 3 && a5) )
    {
      if ( ULongSub(v8, (unsigned __int8)v5[1], &pulResult) < 0 )
        return 722;
      memcpy_0(v9, v5, v21);
      v8 = pulResult;
      v9 += v9[1];
    }
    v7 = v30 + 1;
    v14 = v28;
    v5 += (unsigned __int8)v5[1];
  }
  if ( v15 != 3 || (v22 = 4, !a5) )
    v22 = v15;
  *a3 = v22;
  if ( !v7 && a1[4] )
  {
    v23 = 1;
    *v10 = 1;
    v15 = 3;
    goto LABEL_34;
  }
  if ( (unsigned int)(v15 - 2) <= 1 && v7 )
  {
    v23 = v30;
LABEL_34:
    if ( (*(_BYTE *)v10 & 1) != 0 )
    {
      *v10 = 1;
      v24 = 18;
      v25 = v9;
    }
    else
    {
      v25 = v9;
      if ( (*(_BYTE *)v10 & 2) != 0 )
      {
        *v10 = 2;
        v24 = 0;
      }
      else
      {
        *v10 = 4;
        v24 = 254;
      }
    }
    result = CcpMakeOption(a1 + 287, v24, v25, v8);
    if ( !(_DWORD)result )
    {
      if ( v23 <= 1 || v15 != 2 )
        v16 = v15;
      *a3 = v16;
      if ( ULongSub(v8, v9[1], &pulResult) < 0 )
        return 722;
      LOWORD(v8) = pulResult;
      goto LABEL_46;
    }
  }
  else
  {
LABEL_46:
    if ( *a3 == 4 )
      a1[6] = a1[7];
    else
      a1[7] = a1[6];
    v26 = v32 - v8;
    a3[3] = v32 - v8;
    a3[2] = HIBYTE(v26);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800254c0  mov     r11, rsp
0x1800254c3  mov     [r11+20h], r9d
0x1800254c7  push    rbx
0x1800254c8  push    rbp
0x1800254c9  push    rsi
0x1800254ca  push    rdi
0x1800254cb  push    r12
0x1800254cd  push    r13
0x1800254cf  push    r14
0x1800254d1  push    r15
0x1800254d3  sub     rsp, 48h
0x1800254d7  mov     rax, rdx
0x1800254da  lea     r14, [rdx+4]
0x1800254de  lea     edx, [r9-4]
0x1800254e2  mov     rbp, rcx
0x1800254e5  xor     ecx, ecx
0x1800254e7  mov     [rsp+88h+var_58], edx
0x1800254eb  mov     esi, edx
0x1800254ed  mov     [r11+8], edx
0x1800254f1  movzx   edx, byte ptr [rax+2]
0x1800254f5  lea     r13, [r8+4]
0x1800254f9  movzx   eax, byte ptr [rax+3]
0x1800254fd  lea     rdi, [rbp+47Ch]
0x180025504  add     eax, 0FFFFFFFCh
0x180025507  shl     edx, 8
0x18002550a  mov     r15, r8
0x18002550d  mov     [r11+18h], ecx
0x180025511  add     edx, eax
0x180025513  mov     [rdi], ecx
0x180025515  lea     ebx, [rcx+2]
0x180025518  lea     r8d, [rcx+1]
0x18002551c  lea     r12d, [rcx+3]
0x180025520  mov     [rsp+88h+arg_8], ecx
0x180025527  cmp     edx, 2
0x18002552a  jb      loc_18002562D
0x180025530  movzx   eax, byte ptr [r14+1]
0x180025535  sub     edx, eax
0x180025537  mov     [rsp+88h+var_54], edx
0x18002553b  js      loc_1800256BF
0x180025541  mov     [rsp+88h+var_68], r8d
0x180025546  lea     rdx, [rbp+308h]
0x18002554d  mov     r8, r14
0x180025550  lea     r9, [rsp+88h+arg_10]
0x180025558  mov     rcx, rbp
0x18002555b  call    CcpCheckOption
0x180025560  test    eax, eax
0x180025562  jnz     loc_18002571E
0x180025568  mov     ecx, [rsp+88h+arg_10]
0x18002556f  cmp     ebx, 2
0x180025572  jnz     short loc_180025578
0x180025574  cmp     ecx, ebx
0x180025576  jnz     short loc_180025582
0x180025578  cmp     ebx, r12d
0x18002557b  jnz     short loc_180025593
0x18002557d  cmp     ecx, 4
0x180025580  jnz     short loc_180025598
0x180025582  mov     esi, [rsp+88h+var_58]
0x180025586  lea     r13, [r15+4]
0x18002558a  mov     [rsp+88h+pulResult], esi
0x180025591  mov     ebx, ecx
0x180025593  cmp     ecx, 4
0x180025596  jz      short loc_1800255BB
0x180025598  cmp     byte ptr [r14], 0FEh
0x18002559c  ja      short loc_1800255BB
0x18002559e  cmp     byte ptr [r14], 0
0x1800255a2  mov     eax, [rdi]
0x1800255a4  jz      short loc_1800255B6
0x1800255a6  cmp     byte ptr [r14], 12h
0x1800255aa  jz      short loc_1800255B1
0x1800255ac  or      eax, 4
0x1800255af  jmp     short loc_1800255B9
0x1800255b1  or      eax, 1
0x1800255b4  jmp     short loc_1800255B9
0x1800255b6  or      eax, 2
0x1800255b9  mov     [rdi], eax
0x1800255bb  cmp     ecx, ebx
0x1800255bd  jnz     short loc_18002560C
0x1800255bf  cmp     ecx, 4
0x1800255c2  jz      short loc_1800255D3
0x1800255c4  cmp     ecx, r12d
0x1800255c7  jnz     short loc_18002560C
0x1800255c9  cmp     [rsp+88h+arg_20], 0
0x1800255d1  jz      short loc_18002560C
0x1800255d3  movzx   edx, byte ptr [r14+1]; ulSubtrahend
0x1800255d8  lea     r8, [rsp+88h+pulResult]; pulResult
0x1800255e0  mov     ecx, esi; ulMinuend
0x1800255e2  call    ULongSub
0x1800255e7  test    eax, eax
0x1800255e9  js      loc_1800256BF
0x1800255ef  mov     r8d, edx; Size
0x1800255f2  mov     rcx, r13; void *
0x1800255f5  mov     rdx, r14; Src
0x1800255f8  call    memcpy_0
0x1800255fd  movzx   eax, byte ptr [r13+1]
0x180025602  mov     esi, [rsp+88h+pulResult]
0x180025609  add     r13, rax
0x18002560c  mov     ecx, [rsp+88h+arg_8]
0x180025613  mov     r8d, 1
0x180025619  movzx   eax, byte ptr [r14+1]
0x18002561e  add     ecx, r8d
0x180025621  mov     edx, [rsp+88h+var_54]
0x180025625  add     r14, rax
0x180025628  jmp     loc_180025520
0x18002562d  cmp     ebx, r12d
0x180025630  jnz     short loc_18002563E
0x180025632  cmp     [rsp+88h+arg_20], 0
0x18002563a  mov     al, 4
0x18002563c  jnz     short loc_180025640
0x18002563e  mov     al, bl
0x180025640  mov     [r15], al
0x180025643  test    ecx, ecx
0x180025645  jnz     short loc_180025657
0x180025647  cmp     [rbp+10h], ecx
0x18002564a  jz      short loc_180025657
0x18002564c  mov     r14d, r8d
0x18002564f  mov     [rdi], r8d
0x180025652  mov     ebx, r12d
0x180025655  jmp     short loc_180025673
0x180025657  lea     eax, [rbx-2]
0x18002565a  cmp     eax, r8d
0x18002565d  ja      loc_1800256EC
0x180025663  test    ecx, ecx
0x180025665  jz      loc_1800256EC
0x18002566b  mov     r14d, [rsp+88h+arg_8]
0x180025673  mov     r9d, esi
0x180025676  mov     rcx, rdi
0x180025679  test    [rdi], r8b
0x18002567c  jz      short loc_1800256C6
0x18002567e  mov     [rdi], r8d
0x180025681  mov     edx, 12h
0x180025686  mov     r8, r13
0x180025689  call    CcpMakeOption
0x18002568e  test    eax, eax
0x180025690  jnz     loc_18002571E
0x180025696  cmp     r14d, 1
0x18002569a  jbe     short loc_1800256A1
0x18002569c  cmp     ebx, 2
0x18002569f  jz      short loc_1800256A4
0x1800256a1  mov     r12b, bl
0x1800256a4  mov     [r15], r12b
0x1800256a7  lea     r8, [rsp+88h+pulResult]; pulResult
0x1800256af  movzx   edx, byte ptr [r13+1]; ulSubtrahend
0x1800256b4  mov     ecx, esi; ulMinuend
0x1800256b6  call    ULongSub
0x1800256bb  test    eax, eax
0x1800256bd  jns     short loc_1800256E5
0x1800256bf  mov     eax, 2D2h
0x1800256c4  jmp     short loc_18002571E
0x1800256c6  test    byte ptr [rdi], 2
0x1800256c9  mov     r8, r13
0x1800256cc  jz      short loc_1800256D8
0x1800256ce  mov     dword ptr [rdi], 2
0x1800256d4  xor     edx, edx
0x1800256d6  jmp     short loc_180025689
0x1800256d8  mov     dword ptr [rdi], 4
0x1800256de  mov     edx, 0FEh
0x1800256e3  jmp     short loc_180025689
0x1800256e5  mov     esi, [rsp+88h+pulResult]
0x1800256ec  cmp     byte ptr [r15], 4
0x1800256f0  jnz     short loc_1800256FA
0x1800256f2  mov     eax, [rbp+1Ch]
0x1800256f5  mov     [rbp+18h], eax
0x1800256f8  jmp     short loc_180025700
0x1800256fa  mov     eax, [rbp+18h]
0x1800256fd  mov     [rbp+1Ch], eax
0x180025700  mov     r9d, [rsp+88h+arg_18]
0x180025708  sub     r9w, si
0x18002570c  movzx   eax, r9w
0x180025710  mov     [r15+3], r9b
0x180025714  shr     ax, 8
0x180025718  mov     [r15+2], al
0x18002571c  xor     eax, eax
0x18002571e  add     rsp, 48h
0x180025722  pop     r15
0x180025724  pop     r14
0x180025726  pop     r13
0x180025728  pop     r12
0x18002572a  pop     rdi
0x18002572b  pop     rsi
0x18002572c  pop     rbp
0x18002572d  pop     rbx
0x18002572e  retn
```
