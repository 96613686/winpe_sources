# PAUpdateMMFilterSpecs

- ea: `0x18002b08c`
- end: `0x18002b22f`
- name: `PAUpdateMMFilterSpecs`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18002aba8`

## callees

- `0x18001cc18`
- `0x180027408`
- `0x180027af4`
- `0x180028c28`
- `0x18002912c`
- `0x180029368`
- `0x18002a1e0`
- `0x18002a418`
- `0x18002a4bc`
- `0x18002b08c`

## pseudocode

```c
__int64 __fastcall PAUpdateMMFilterSpecs(
        _OWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8)
{
  __int64 MMPolicyState; // rax
  __int64 MMAuthState; // rax
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // r14
  __int64 FilterSpec; // rax
  __int64 v16; // r15
  int v17; // eax
  __int128 v18; // xmm1
  __int64 MMFilterState; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _OWORD *v23; // r9
  __int128 v24; // [rsp+20h] [rbp-20h] BYREF
  __int128 v25; // [rsp+30h] [rbp-10h] BYREF

  v24 = *a1;
  MMPolicyState = FindMMPolicyState(&v24);
  if ( !MMPolicyState || !*(_DWORD *)(MMPolicyState + 24) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 87;
    v22 = 21;
    v23 = a1;
    goto LABEL_21;
  }
  v24 = *(_OWORD *)(a5 + 8);
  MMAuthState = FindMMAuthState(&v24);
  if ( !MMAuthState || !*(_DWORD *)(MMAuthState + 16) )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 87;
    v22 = 22;
    v23 = (_OWORD *)(a5 + 8);
LABEL_21:
    WPP_SF__guid_(v21[2], v22, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v23);
    return 87;
  }
  v12 = 0;
  v13 = 0;
  if ( a6 )
  {
    while ( 1 )
    {
      v14 = *(_QWORD *)(a7 + 8 * v13);
      FilterSpec = FindFilterSpec(v14, v11);
      v16 = FilterSpec;
      if ( !FilterSpec )
        goto LABEL_12;
      v17 = EqualFilterSpecs(FilterSpec, v14);
      v18 = *(_OWORD *)(v16 + 24);
      if ( !v17 )
        break;
      v25 = *(_OWORD *)(a5 + 8);
      v24 = v18;
      MMFilterState = FindMMFilterState(&v24, &v25);
      if ( !MMFilterState )
        goto LABEL_12;
      if ( !*(_QWORD *)(MMFilterState + 64) )
      {
        PADeleteMMFilterState(MMFilterState);
        goto LABEL_12;
      }
LABEL_13:
      v11 = a4;
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= a6 )
        return v12;
    }
    v25 = *(_OWORD *)(v16 + 24);
    v24 = *(_OWORD *)(a2 + 8);
    PADeleteMMFilter(&v25, &v24);
LABEL_12:
    v12 = PAAddMMFilterSpec(a1, a5, v14, a8);
    goto LABEL_13;
  }
  return v12;
}

```

## disassembly

```asm
0x18002b08c  mov     rax, rsp
0x18002b08f  mov     [rax+8], rbx
0x18002b093  mov     [rax+20h], r9
0x18002b097  mov     [rax+18h], r8d
0x18002b09b  mov     [rax+10h], rdx
0x18002b09f  push    rbp
0x18002b0a0  push    rsi
0x18002b0a1  push    rdi
0x18002b0a2  push    r12
0x18002b0a4  push    r13
0x18002b0a6  push    r14
0x18002b0a8  push    r15
0x18002b0aa  mov     rbp, rsp
0x18002b0ad  sub     rsp, 40h
0x18002b0b1  movups  xmm0, xmmword ptr [rcx]
0x18002b0b4  mov     rsi, rcx
0x18002b0b7  lea     rcx, [rbp+var_20]
0x18002b0bb  movdqu  [rbp+var_20], xmm0
0x18002b0c0  call    FindMMPolicyState
0x18002b0c5  test    rax, rax
0x18002b0c8  jz      loc_18002B1E1
0x18002b0ce  cmp     dword ptr [rax+18h], 0
0x18002b0d2  jz      loc_18002B1E1
0x18002b0d8  mov     r13, [rbp+arg_20]
0x18002b0dc  lea     rcx, [rbp+var_20]
0x18002b0e0  lea     r12, [r13+8]
0x18002b0e4  movups  xmm0, xmmword ptr [r12]
0x18002b0e9  movdqu  [rbp+var_20], xmm0
0x18002b0ee  call    FindMMAuthState
0x18002b0f3  test    rax, rax
0x18002b0f6  jz      loc_18002B1BE
0x18002b0fc  cmp     dword ptr [rax+10h], 0
0x18002b100  jz      loc_18002B1BE
0x18002b106  xor     ebx, ebx
0x18002b108  xor     edi, edi
0x18002b10a  cmp     [rbp+arg_28], ebx
0x18002b10d  jbe     loc_18002B1BA
0x18002b113  mov     rcx, [rbp+arg_30]
0x18002b117  mov     rdx, r9
0x18002b11a  mov     r14, [rcx+rdi*8]
0x18002b11e  mov     rcx, r14
0x18002b121  call    FindFilterSpec
0x18002b126  mov     r15, rax
0x18002b129  test    rax, rax
0x18002b12c  jz      short loc_18002B193
0x18002b12e  mov     rdx, r14
0x18002b131  mov     rcx, rax
0x18002b134  call    EqualFilterSpecs
0x18002b139  movups  xmm1, xmmword ptr [r15+18h]
0x18002b13e  test    eax, eax
0x18002b140  jnz     short loc_18002B163
0x18002b142  mov     rax, [rbp+arg_8]
0x18002b146  lea     rdx, [rbp+var_20]
0x18002b14a  lea     rcx, [rbp+var_10]
0x18002b14e  movdqu  [rbp+var_10], xmm1
0x18002b153  movups  xmm0, xmmword ptr [rax+8]
0x18002b157  movdqu  [rbp+var_20], xmm0
0x18002b15c  call    PADeleteMMFilter
0x18002b161  jmp     short loc_18002B193
0x18002b163  movups  xmm0, xmmword ptr [r12]
0x18002b168  lea     rdx, [rbp+var_10]
0x18002b16c  lea     rcx, [rbp+var_20]
0x18002b170  movdqu  [rbp+var_10], xmm0
0x18002b175  movdqu  [rbp+var_20], xmm1
0x18002b17a  call    FindMMFilterState
0x18002b17f  test    rax, rax
0x18002b182  jz      short loc_18002B193
0x18002b184  cmp     qword ptr [rax+40h], 0
0x18002b189  jnz     short loc_18002B1A7
0x18002b18b  mov     rcx, rax
0x18002b18e  call    PADeleteMMFilterState
0x18002b193  mov     r9d, [rbp+arg_38]
0x18002b197  mov     r8, r14
0x18002b19a  mov     rdx, r13
0x18002b19d  mov     rcx, rsi
0x18002b1a0  call    PAAddMMFilterSpec
0x18002b1a5  mov     ebx, eax
0x18002b1a7  mov     r9, [rbp+arg_18]
0x18002b1ab  inc     edi
0x18002b1ad  mov     r8d, [rbp+arg_10]
0x18002b1b1  cmp     edi, [rbp+arg_28]
0x18002b1b4  jb      loc_18002B113
0x18002b1ba  mov     eax, ebx
0x18002b1bc  jmp     short loc_18002B217
0x18002b1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c5  lea     rax, WPP_GLOBAL_Control
0x18002b1cc  cmp     rcx, rax
0x18002b1cf  jz      short loc_18002B212
0x18002b1d1  test    byte ptr [rcx+1Ch], 10h
0x18002b1d5  jz      short loc_18002B212
0x18002b1d7  mov     edx, 16h
0x18002b1dc  mov     r9, r12
0x18002b1df  jmp     short loc_18002B202
0x18002b1e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1e8  lea     rax, WPP_GLOBAL_Control
0x18002b1ef  cmp     rcx, rax
0x18002b1f2  jz      short loc_18002B212
0x18002b1f4  test    byte ptr [rcx+1Ch], 10h
0x18002b1f8  jz      short loc_18002B212
0x18002b1fa  mov     edx, 15h
0x18002b1ff  mov     r9, rsi
0x18002b202  mov     rcx, [rcx+10h]
0x18002b206  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002b20d  call    WPP_SF__guid_
0x18002b212  mov     eax, 57h ; 'W'
0x18002b217  mov     rbx, [rsp+40h+arg_0]
0x18002b21f  add     rsp, 40h
0x18002b223  pop     r15
0x18002b225  pop     r14
0x18002b227  pop     r13
0x18002b229  pop     r12
0x18002b22b  pop     rdi
0x18002b22c  pop     rsi
0x18002b22d  pop     rbp
0x18002b22e  retn
```
