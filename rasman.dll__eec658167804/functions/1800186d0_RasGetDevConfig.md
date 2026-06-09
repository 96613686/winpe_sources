# RasGetDevConfig

- ea: `0x1800186d0`
- end: `0x180018990`
- name: `RasGetDevConfig`
- size: `704`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180011790`
- `0x1800119c4`
- `0x180011b40`
- `0x1800186d0`
- `0x180021000`
- `0x1800219f4`
- `0x180023aa0`
- `0x1800263c2`

## pseudocode

```c
__int64 __fastcall RasGetDevConfig(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, unsigned int *a5)
{
  unsigned int v9; // ebx
  PVOID *v10; // r10
  __int64 v11; // rdx
  unsigned int *v12; // r14
  unsigned int DevConfig; // eax
  unsigned int v14; // edi
  unsigned int v15; // eax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 486, a3, a2, a1);
  }
  if ( (unsigned int)ValidatePortHandle(a2) )
  {
    if ( !(unsigned int)ValidateConnectionHandle(a1) )
    {
      v9 = -2147024809;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_47;
      v11 = 488;
      goto LABEL_45;
    }
    if ( a1 && *(_DWORD *)(a1 + 12) == 4 )
    {
      v12 = a5;
      LODWORD(Size) = *a5;
      DevConfig = RemoteRasGetDevConfig(a1, a2, a3, (_DWORD)a4, (__int64)&Size);
      v9 = DevConfig;
      if ( DevConfig )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          v14 = Size;
LABEL_23:
          if ( v14 )
          {
            if ( *v12 < (unsigned __int64)v14 + 20 )
            {
              v9 = 603;
              if ( v10 == &WPP_GLOBAL_Control )
                return v9;
              if ( (*((_BYTE *)v10 + 28) & 0x40) == 0 || *((_BYTE *)v10 + 25) < 2u )
                goto LABEL_47;
              v11 = 490;
              goto LABEL_45;
            }
            *v12 = v14 + 20;
LABEL_46:
            v10 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_47;
          }
LABEL_34:
          *v12 = v14;
          goto LABEL_46;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 489, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, DevConfig);
        v14 = Size;
      }
      else
      {
        v14 = Size;
        if ( !(_DWORD)Size )
          goto LABEL_34;
        if ( *v12 >= (unsigned __int64)(unsigned int)Size + 20 )
        {
          memmove_0(a4 + 4, a4, (unsigned int)Size);
          *a4 = 16;
          a4[1] = v14;
          *((_QWORD *)a4 + 1) = 0;
          goto LABEL_46;
        }
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_23;
    }
    v15 = SubmitRequest(a1, 73, a2, a3);
    v9 = v15;
    if ( v15 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 491, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v15);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_41:
    if ( v10 == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)v10 + 28) & 0x40) == 0 || *((_BYTE *)v10 + 25) < 6u )
      goto LABEL_47;
    v11 = 492;
    goto LABEL_45;
  }
  v9 = 601;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 487;
LABEL_45:
    WPP_SF_d(v10[2], v11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
    goto LABEL_46;
  }
LABEL_47:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 493, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800186d0  mov     [rsp+arg_8], rbx
0x1800186d5  mov     [rsp+arg_10], rbp
0x1800186da  push    rsi
0x1800186db  push    rdi
0x1800186dc  push    r12
0x1800186de  push    r13
0x1800186e0  push    r14
0x1800186e2  sub     rsp, 30h
0x1800186e6  mov     rsi, r9
0x1800186e9  mov     rbp, r8
0x1800186ec  mov     rdi, rdx
0x1800186ef  mov     rbx, rcx
0x1800186f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186f9  lea     r12, WPP_GLOBAL_Control
0x180018700  cmp     rcx, r12
0x180018703  jz      short loc_180018727
0x180018705  test    byte ptr [rcx+1Ch], 40h
0x180018709  jz      short loc_180018727
0x18001870b  cmp     byte ptr [rcx+19h], 6
0x18001870f  jb      short loc_180018727
0x180018711  mov     rcx, [rcx+10h]
0x180018715  mov     edx, 1E6h
0x18001871a  mov     r9, rdi
0x18001871d  mov     [rsp+58h+var_38], rbx
0x180018722  call    WPP_SF_qq
0x180018727  mov     rcx, rdi
0x18001872a  call    ValidatePortHandle
0x18001872f  lea     r13, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018736  test    eax, eax
0x180018738  jnz     short loc_18001876D
0x18001873a  mov     ebx, 259h
0x18001873f  mov     r10, cs:WPP_GLOBAL_Control
0x180018746  cmp     r10, r12
0x180018749  jz      loc_180018977
0x18001874f  test    byte ptr [r10+1Ch], 40h
0x180018754  jz      loc_180018950
0x18001875a  cmp     byte ptr [r10+19h], 2
0x18001875f  jb      loc_180018950
0x180018765  lea     edx, [rbx-72h]
0x180018768  jmp     loc_18001893A
0x18001876d  mov     rcx, rbx
0x180018770  call    ValidateConnectionHandle
0x180018775  test    eax, eax
0x180018777  jnz     short loc_1800187AE
0x180018779  mov     ebx, 80070057h
0x18001877e  mov     r10, cs:WPP_GLOBAL_Control
0x180018785  cmp     r10, r12
0x180018788  jz      loc_180018977
0x18001878e  test    byte ptr [r10+1Ch], 40h
0x180018793  jz      loc_180018950
0x180018799  cmp     byte ptr [r10+19h], 2
0x18001879e  jb      loc_180018950
0x1800187a4  mov     edx, 1E8h
0x1800187a9  jmp     loc_18001893A
0x1800187ae  test    rbx, rbx
0x1800187b1  jz      loc_1800188C2
0x1800187b7  cmp     dword ptr [rbx+0Ch], 4
0x1800187bb  jnz     loc_1800188C2
0x1800187c1  mov     r14, [rsp+58h+arg_20]
0x1800187c9  mov     r9, rsi
0x1800187cc  mov     r8, rbp
0x1800187cf  mov     rdx, rdi
0x1800187d2  mov     rcx, rbx
0x1800187d5  mov     eax, [r14]
0x1800187d8  mov     dword ptr [rsp+58h+Size], eax
0x1800187dc  lea     rax, [rsp+58h+Size]
0x1800187e1  mov     [rsp+58h+var_38], rax
0x1800187e6  call    RemoteRasGetDevConfig
0x1800187eb  mov     ebx, eax
0x1800187ed  test    eax, eax
0x1800187ef  jz      loc_180018876
0x1800187f5  mov     r10, cs:WPP_GLOBAL_Control
0x1800187fc  cmp     r10, r12
0x1800187ff  jz      short loc_180018870
0x180018801  test    byte ptr [r10+1Ch], 40h
0x180018806  jz      short loc_180018870
0x180018808  cmp     byte ptr [r10+19h], 2
0x18001880d  jb      short loc_180018870
0x18001880f  mov     rcx, [r10+10h]
0x180018813  mov     edx, 1E9h
0x180018818  mov     r9d, eax
0x18001881b  mov     r8, r13
0x18001881e  call    WPP_SF_d
0x180018823  mov     edi, dword ptr [rsp+58h+Size]
0x180018827  mov     r10, cs:WPP_GLOBAL_Control
0x18001882e  test    edi, edi
0x180018830  jz      loc_1800188BA
0x180018836  mov     eax, [r14]
0x180018839  mov     ecx, edi
0x18001883b  add     rcx, 14h
0x18001883f  cmp     rax, rcx
0x180018842  jnb     short loc_1800188AF
0x180018844  mov     ebx, 25Bh
0x180018849  cmp     r10, r12
0x18001884c  jz      loc_180018977
0x180018852  test    byte ptr [r10+1Ch], 40h
0x180018857  jz      loc_180018950
0x18001885d  cmp     byte ptr [r10+19h], 2
0x180018862  jb      loc_180018950
0x180018868  lea     edx, [rbx-71h]
0x18001886b  jmp     loc_18001893A
0x180018870  mov     edi, dword ptr [rsp+58h+Size]
0x180018874  jmp     short loc_18001882E
0x180018876  mov     edi, dword ptr [rsp+58h+Size]
0x18001887a  test    edi, edi
0x18001887c  jz      short loc_1800188BA
0x18001887e  mov     eax, [r14]
0x180018881  lea     rcx, [rdi+14h]
0x180018885  mov     r8d, edi; Size
0x180018888  cmp     rax, rcx
0x18001888b  jb      short loc_180018827
0x18001888d  lea     rcx, [rsi+10h]; void *
0x180018891  mov     rdx, rsi; Src
0x180018894  call    memmove_0
0x180018899  mov     dword ptr [rsi], 10h
0x18001889f  mov     [rsi+4], edi
0x1800188a2  mov     qword ptr [rsi+8], 0
0x1800188aa  jmp     loc_180018949
0x1800188af  lea     eax, [rdi+14h]
0x1800188b2  mov     [r14], eax
0x1800188b5  jmp     loc_180018949
0x1800188ba  mov     [r14], edi
0x1800188bd  jmp     loc_180018949
0x1800188c2  mov     rax, [rsp+58h+arg_20]
0x1800188ca  mov     edx, 49h ; 'I'
0x1800188cf  mov     [rsp+58h+var_30], rax
0x1800188d4  mov     r9, rbp
0x1800188d7  mov     r8, rdi
0x1800188da  mov     [rsp+58h+var_38], rsi
0x1800188df  mov     rcx, rbx
0x1800188e2  call    SubmitRequest
0x1800188e7  mov     ebx, eax
0x1800188e9  test    eax, eax
0x1800188eb  jz      short loc_18001891B
0x1800188ed  mov     r10, cs:WPP_GLOBAL_Control
0x1800188f4  cmp     r10, r12
0x1800188f7  jz      short loc_180018977
0x1800188f9  test    byte ptr [r10+1Ch], 40h
0x1800188fe  jz      short loc_180018922
0x180018900  cmp     byte ptr [r10+19h], 2
0x180018905  jb      short loc_180018922
0x180018907  mov     rcx, [r10+10h]
0x18001890b  mov     edx, 1EBh
0x180018910  mov     r9d, eax
0x180018913  mov     r8, r13
0x180018916  call    WPP_SF_d
0x18001891b  mov     r10, cs:WPP_GLOBAL_Control
0x180018922  cmp     r10, r12
0x180018925  jz      short loc_180018977
0x180018927  test    byte ptr [r10+1Ch], 40h
0x18001892c  jz      short loc_180018950
0x18001892e  cmp     byte ptr [r10+19h], 6
0x180018933  jb      short loc_180018950
0x180018935  mov     edx, 1ECh
0x18001893a  mov     rcx, [r10+10h]
0x18001893e  mov     r9d, ebx
0x180018941  mov     r8, r13
0x180018944  call    WPP_SF_d
0x180018949  mov     r10, cs:WPP_GLOBAL_Control
0x180018950  cmp     r10, r12
0x180018953  jz      short loc_180018977
0x180018955  test    byte ptr [r10+1Ch], 40h
0x18001895a  jz      short loc_180018977
0x18001895c  cmp     byte ptr [r10+19h], 6
0x180018961  jb      short loc_180018977
0x180018963  mov     rcx, [r10+10h]
0x180018967  mov     edx, 1EDh
0x18001896c  mov     r9d, ebx
0x18001896f  mov     r8, r13
0x180018972  call    WPP_SF_d
0x180018977  mov     rbp, [rsp+58h+arg_10]
0x18001897c  mov     eax, ebx
0x18001897e  mov     rbx, [rsp+58h+arg_8]
0x180018983  add     rsp, 30h
0x180018987  pop     r14
0x180018989  pop     r13
0x18001898b  pop     r12
0x18001898d  pop     rdi
0x18001898e  pop     rsi
0x18001898f  retn
```
