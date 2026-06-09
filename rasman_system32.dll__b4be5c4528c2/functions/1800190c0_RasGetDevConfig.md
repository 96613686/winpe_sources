# RasGetDevConfig

- ea: `0x1800190c0`
- end: `0x180019381`
- name: `RasGetDevConfig`
- size: `705`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180011f80`
- `0x1800121b4`
- `0x180012330`
- `0x1800190c0`
- `0x180021b14`
- `0x1800225a0`
- `0x180024788`
- `0x180027392`

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
    v15 = SubmitRequest(a1, 0x49u, a2, a3, a4, a5);
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
0x1800190c0  mov     [rsp+arg_8], rbx
0x1800190c5  mov     [rsp+arg_10], rbp
0x1800190ca  push    rsi
0x1800190cb  push    rdi
0x1800190cc  push    r12
0x1800190ce  push    r13
0x1800190d0  push    r14
0x1800190d2  sub     rsp, 30h
0x1800190d6  mov     rsi, r9
0x1800190d9  mov     rbp, r8
0x1800190dc  mov     rdi, rdx
0x1800190df  mov     rbx, rcx
0x1800190e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190e9  lea     r12, WPP_GLOBAL_Control
0x1800190f0  cmp     rcx, r12
0x1800190f3  jz      short loc_180019117
0x1800190f5  test    byte ptr [rcx+1Ch], 40h
0x1800190f9  jz      short loc_180019117
0x1800190fb  cmp     byte ptr [rcx+19h], 6
0x1800190ff  jb      short loc_180019117
0x180019101  mov     rcx, [rcx+10h]
0x180019105  mov     edx, 1E6h
0x18001910a  mov     r9, rdi
0x18001910d  mov     [rsp+58h+var_38], rbx
0x180019112  call    WPP_SF_qq
0x180019117  mov     rcx, rdi
0x18001911a  call    ValidatePortHandle
0x18001911f  lea     r13, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019126  test    eax, eax
0x180019128  jnz     short loc_18001915D
0x18001912a  mov     ebx, 259h
0x18001912f  mov     r10, cs:WPP_GLOBAL_Control
0x180019136  cmp     r10, r12
0x180019139  jz      loc_180019367
0x18001913f  test    byte ptr [r10+1Ch], 40h
0x180019144  jz      loc_180019340
0x18001914a  cmp     byte ptr [r10+19h], 2
0x18001914f  jb      loc_180019340
0x180019155  lea     edx, [rbx-72h]
0x180019158  jmp     loc_18001932A
0x18001915d  mov     rcx, rbx
0x180019160  call    ValidateConnectionHandle
0x180019165  test    eax, eax
0x180019167  jnz     short loc_18001919E
0x180019169  mov     ebx, 80070057h
0x18001916e  mov     r10, cs:WPP_GLOBAL_Control
0x180019175  cmp     r10, r12
0x180019178  jz      loc_180019367
0x18001917e  test    byte ptr [r10+1Ch], 40h
0x180019183  jz      loc_180019340
0x180019189  cmp     byte ptr [r10+19h], 2
0x18001918e  jb      loc_180019340
0x180019194  mov     edx, 1E8h
0x180019199  jmp     loc_18001932A
0x18001919e  test    rbx, rbx
0x1800191a1  jz      loc_1800192B2
0x1800191a7  cmp     dword ptr [rbx+0Ch], 4
0x1800191ab  jnz     loc_1800192B2
0x1800191b1  mov     r14, [rsp+58h+arg_20]
0x1800191b9  mov     r9, rsi
0x1800191bc  mov     r8, rbp
0x1800191bf  mov     rdx, rdi
0x1800191c2  mov     rcx, rbx
0x1800191c5  mov     eax, [r14]
0x1800191c8  mov     dword ptr [rsp+58h+Size], eax
0x1800191cc  lea     rax, [rsp+58h+Size]
0x1800191d1  mov     [rsp+58h+var_38], rax
0x1800191d6  call    RemoteRasGetDevConfig
0x1800191db  mov     ebx, eax
0x1800191dd  test    eax, eax
0x1800191df  jz      loc_180019266
0x1800191e5  mov     r10, cs:WPP_GLOBAL_Control
0x1800191ec  cmp     r10, r12
0x1800191ef  jz      short loc_180019260
0x1800191f1  test    byte ptr [r10+1Ch], 40h
0x1800191f6  jz      short loc_180019260
0x1800191f8  cmp     byte ptr [r10+19h], 2
0x1800191fd  jb      short loc_180019260
0x1800191ff  mov     rcx, [r10+10h]
0x180019203  mov     edx, 1E9h
0x180019208  mov     r9d, eax
0x18001920b  mov     r8, r13
0x18001920e  call    WPP_SF_d
0x180019213  mov     edi, dword ptr [rsp+58h+Size]
0x180019217  mov     r10, cs:WPP_GLOBAL_Control
0x18001921e  test    edi, edi
0x180019220  jz      loc_1800192AA
0x180019226  mov     eax, [r14]
0x180019229  mov     ecx, edi
0x18001922b  add     rcx, 14h
0x18001922f  cmp     rax, rcx
0x180019232  jnb     short loc_18001929F
0x180019234  mov     ebx, 25Bh
0x180019239  cmp     r10, r12
0x18001923c  jz      loc_180019367
0x180019242  test    byte ptr [r10+1Ch], 40h
0x180019247  jz      loc_180019340
0x18001924d  cmp     byte ptr [r10+19h], 2
0x180019252  jb      loc_180019340
0x180019258  lea     edx, [rbx-71h]
0x18001925b  jmp     loc_18001932A
0x180019260  mov     edi, dword ptr [rsp+58h+Size]
0x180019264  jmp     short loc_18001921E
0x180019266  mov     edi, dword ptr [rsp+58h+Size]
0x18001926a  test    edi, edi
0x18001926c  jz      short loc_1800192AA
0x18001926e  mov     eax, [r14]
0x180019271  lea     rcx, [rdi+14h]
0x180019275  mov     r8d, edi; Size
0x180019278  cmp     rax, rcx
0x18001927b  jb      short loc_180019217
0x18001927d  lea     rcx, [rsi+10h]; void *
0x180019281  mov     rdx, rsi; Src
0x180019284  call    memmove_0
0x180019289  mov     dword ptr [rsi], 10h
0x18001928f  mov     [rsi+4], edi
0x180019292  mov     qword ptr [rsi+8], 0
0x18001929a  jmp     loc_180019339
0x18001929f  lea     eax, [rdi+14h]
0x1800192a2  mov     [r14], eax
0x1800192a5  jmp     loc_180019339
0x1800192aa  mov     [r14], edi
0x1800192ad  jmp     loc_180019339
0x1800192b2  mov     rax, [rsp+58h+arg_20]
0x1800192ba  mov     edx, 49h ; 'I'
0x1800192bf  mov     [rsp+58h+var_30], rax
0x1800192c4  mov     r9, rbp
0x1800192c7  mov     r8, rdi
0x1800192ca  mov     [rsp+58h+var_38], rsi
0x1800192cf  mov     rcx, rbx
0x1800192d2  call    SubmitRequest
0x1800192d7  mov     ebx, eax
0x1800192d9  test    eax, eax
0x1800192db  jz      short loc_18001930B
0x1800192dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800192e4  cmp     r10, r12
0x1800192e7  jz      short loc_180019367
0x1800192e9  test    byte ptr [r10+1Ch], 40h
0x1800192ee  jz      short loc_180019312
0x1800192f0  cmp     byte ptr [r10+19h], 2
0x1800192f5  jb      short loc_180019312
0x1800192f7  mov     rcx, [r10+10h]
0x1800192fb  mov     edx, 1EBh
0x180019300  mov     r9d, eax
0x180019303  mov     r8, r13
0x180019306  call    WPP_SF_d
0x18001930b  mov     r10, cs:WPP_GLOBAL_Control
0x180019312  cmp     r10, r12
0x180019315  jz      short loc_180019367
0x180019317  test    byte ptr [r10+1Ch], 40h
0x18001931c  jz      short loc_180019340
0x18001931e  cmp     byte ptr [r10+19h], 6
0x180019323  jb      short loc_180019340
0x180019325  mov     edx, 1ECh
0x18001932a  mov     rcx, [r10+10h]
0x18001932e  mov     r9d, ebx
0x180019331  mov     r8, r13
0x180019334  call    WPP_SF_d
0x180019339  mov     r10, cs:WPP_GLOBAL_Control
0x180019340  cmp     r10, r12
0x180019343  jz      short loc_180019367
0x180019345  test    byte ptr [r10+1Ch], 40h
0x18001934a  jz      short loc_180019367
0x18001934c  cmp     byte ptr [r10+19h], 6
0x180019351  jb      short loc_180019367
0x180019353  mov     rcx, [r10+10h]
0x180019357  mov     edx, 1EDh
0x18001935c  mov     r9d, ebx
0x18001935f  mov     r8, r13
0x180019362  call    WPP_SF_d
0x180019367  mov     rbp, [rsp+58h+arg_10]
0x18001936c  mov     eax, ebx
0x18001936e  mov     rbx, [rsp+58h+arg_8]
0x180019373  add     rsp, 30h
0x180019377  pop     r14
0x180019379  pop     r13
0x18001937b  pop     r12
0x18001937d  pop     rdi
0x18001937e  pop     rsi
0x18001937f  retn
```
