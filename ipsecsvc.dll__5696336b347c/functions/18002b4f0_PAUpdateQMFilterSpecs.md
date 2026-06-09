# PAUpdateQMFilterSpecs

- ea: `0x18002b4f0`
- end: `0x18002b681`
- name: `PAUpdateQMFilterSpecs`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18002acb8`

## callees

- `0x18001cc18`
- `0x18002833c`
- `0x18002a1e0`
- `0x18002a418`
- `0x18002a6f8`
- `0x18002a868`
- `0x18002a9d0`
- `0x18002b438`
- `0x18002b4f0`

## pseudocode

```c
__int64 __fastcall PAUpdateQMFilterSpecs(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 QMPolicyState; // rax
  __int64 v9; // r9
  __int64 v10; // r10
  __int64 v11; // rbx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 result; // rax
  __int64 v17; // rbp
  __int64 v18; // rsi
  __int64 FilterSpec; // rax
  __int64 v20; // r14
  _OWORD v21[3]; // [rsp+20h] [rbp-38h] BYREF

  QMPolicyState = FindQMPolicyState(*(_QWORD *)(a4 + 104), a2, (unsigned int)a2, *(_QWORD *)(a4 + 104));
  v11 = QMPolicyState;
  if ( !QMPolicyState )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 87;
    v13 = 24;
LABEL_15:
    WPP_SF__guid_(v12[2], v13, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v9);
    return 87;
  }
  v14 = *(_QWORD *)(QMPolicyState + 40) - 0x11D177E38A171DD2LL;
  if ( !v14 )
    v14 = *(_QWORD *)(v11 + 48) - 1335908742LL;
  if ( v14 )
  {
    v15 = *(_QWORD *)(v11 + 40) - 0x11D176473F91A819LL;
    if ( *(_QWORD *)(v11 + 40) == 0x11D176473F91A819LL )
      v15 = *(_QWORD *)(v11 + 48) - 1792298374LL;
    if ( v15 && !*(_DWORD *)(v11 + 64) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return 87;
      v13 = 25;
      goto LABEL_15;
    }
  }
  result = 0;
  v17 = 0;
  if ( a5 )
  {
    while ( 1 )
    {
      v18 = *(_QWORD *)(a6 + 8 * v17);
      FilterSpec = FindFilterSpec(v18, v10);
      v20 = FilterSpec;
      if ( !FilterSpec )
        goto LABEL_19;
      if ( !(unsigned int)EqualFilterSpecs(FilterSpec, v18) )
        break;
      result = PAUpdateQMFilterSpec(a4, v11, v18, a7);
LABEL_25:
      v10 = a3;
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= a5 )
        return result;
    }
    v21[0] = *(_OWORD *)(v20 + 24);
    PADeleteQMFilter(a1, v21);
LABEL_19:
    if ( (*(_BYTE *)(a4 + 76) & 3) != 0 )
      result = PAAddTnFilterSpec(a4, v11, v18, a7);
    else
      result = PAAddTxFilterSpec(a4, v11, v18, a7);
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x18002b4f0  mov     rax, rsp
0x18002b4f3  mov     [rax+20h], rbx
0x18002b4f7  mov     [rax+18h], r8
0x18002b4fb  mov     [rax+10h], edx
0x18002b4fe  mov     [rax+8], rcx
0x18002b502  push    rbp
0x18002b503  push    rsi
0x18002b504  push    rdi
0x18002b505  push    r13
0x18002b507  push    r14
0x18002b509  sub     rsp, 30h
0x18002b50d  mov     rdi, r9
0x18002b510  mov     r10, r8
0x18002b513  mov     r9, [r9+68h]
0x18002b517  mov     r8d, edx
0x18002b51a  mov     rcx, r9
0x18002b51d  call    FindQMPolicyState
0x18002b522  mov     rbx, rax
0x18002b525  test    rax, rax
0x18002b528  jnz     short loc_18002B548
0x18002b52a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b531  lea     rax, WPP_GLOBAL_Control
0x18002b538  cmp     rcx, rax
0x18002b53b  jz      short loc_18002B5B6
0x18002b53d  test    byte ptr [rcx+1Ch], 10h
0x18002b541  jz      short loc_18002B5B6
0x18002b543  lea     edx, [rbx+18h]
0x18002b546  jmp     short loc_18002B5A6
0x18002b548  mov     rax, [rax+28h]
0x18002b54c  sub     rax, cs:qword_180055CD8
0x18002b553  jnz     short loc_18002B560
0x18002b555  mov     rax, [rbx+30h]
0x18002b559  sub     rax, cs:qword_180055CE0
0x18002b560  test    rax, rax
0x18002b563  jz      short loc_18002B5C0
0x18002b565  mov     rax, [rbx+28h]
0x18002b569  sub     rax, cs:qword_180055F00
0x18002b570  jnz     short loc_18002B57D
0x18002b572  mov     rax, [rbx+30h]
0x18002b576  sub     rax, cs:qword_180055F08
0x18002b57d  test    rax, rax
0x18002b580  jz      short loc_18002B5C0
0x18002b582  cmp     dword ptr [rbx+40h], 0
0x18002b586  jnz     short loc_18002B5C0
0x18002b588  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b58f  lea     rax, WPP_GLOBAL_Control
0x18002b596  cmp     rcx, rax
0x18002b599  jz      short loc_18002B5B6
0x18002b59b  test    byte ptr [rcx+1Ch], 10h
0x18002b59f  jz      short loc_18002B5B6
0x18002b5a1  mov     edx, 19h
0x18002b5a6  mov     rcx, [rcx+10h]
0x18002b5aa  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002b5b1  call    WPP_SF__guid_
0x18002b5b6  mov     eax, 57h ; 'W'
0x18002b5bb  jmp     loc_18002B670
0x18002b5c0  mov     r13, [rsp+58h+arg_28]
0x18002b5c8  xor     eax, eax
0x18002b5ca  xor     ebp, ebp
0x18002b5cc  cmp     [rsp+58h+arg_20], eax
0x18002b5d3  jbe     loc_18002B670
0x18002b5d9  mov     rsi, [r13+rbp*8+0]
0x18002b5de  mov     rdx, r10
0x18002b5e1  mov     rcx, rsi
0x18002b5e4  call    FindFilterSpec
0x18002b5e9  mov     r14, rax
0x18002b5ec  test    rax, rax
0x18002b5ef  jnz     short loc_18002B60F
0x18002b5f1  test    byte ptr [rdi+4Ch], 3
0x18002b5f5  mov     r8, rsi
0x18002b5f8  mov     r9d, [rsp+58h+arg_30]
0x18002b600  mov     rdx, rbx
0x18002b603  mov     rcx, rdi
0x18002b606  jnz     short loc_18002B63A
0x18002b608  call    PAAddTxFilterSpec
0x18002b60d  jmp     short loc_18002B657
0x18002b60f  mov     rdx, rsi
0x18002b612  mov     rcx, r14
0x18002b615  call    EqualFilterSpecs
0x18002b61a  test    eax, eax
0x18002b61c  jnz     short loc_18002B641
0x18002b61e  movups  xmm0, xmmword ptr [r14+18h]
0x18002b623  mov     rcx, [rsp+58h+arg_0]
0x18002b628  lea     rdx, [rsp+58h+var_38]
0x18002b62d  movdqu  [rsp+58h+var_38], xmm0
0x18002b633  call    PADeleteQMFilter
0x18002b638  jmp     short loc_18002B5F1
0x18002b63a  call    PAAddTnFilterSpec
0x18002b63f  jmp     short loc_18002B657
0x18002b641  mov     r9d, [rsp+58h+arg_30]
0x18002b649  mov     r8, rsi
0x18002b64c  mov     rdx, rbx
0x18002b64f  mov     rcx, rdi
0x18002b652  call    PAUpdateQMFilterSpec
0x18002b657  mov     r10, [rsp+58h+arg_10]
0x18002b65c  inc     ebp
0x18002b65e  mov     r8d, [rsp+58h+arg_8]
0x18002b663  cmp     ebp, [rsp+58h+arg_20]
0x18002b66a  jb      loc_18002B5D9
0x18002b670  mov     rbx, [rsp+58h+arg_18]
0x18002b675  add     rsp, 30h
0x18002b679  pop     r14
0x18002b67b  pop     r13
0x18002b67d  pop     rdi
0x18002b67e  pop     rsi
0x18002b67f  pop     rbp
0x18002b680  retn
```
