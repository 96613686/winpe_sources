# PAProcessNegPolUpdate

- ea: `0x18000cd90`
- end: `0x18000cfa0`
- name: `PAProcessNegPolUpdate`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18002ada0`

## callees

- `0x18000cd90`
- `0x18000cfa8`
- `0x18000cfdc`
- `0x18000e510`
- `0x1800195d4`
- `0x18002791c`
- `0x18002833c`
- `0x180028648`
- `0x180028b2c`
- `0x18002a31c`

## pseudocode

```c
__int64 __fastcall PAProcessNegPolUpdate(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4)
{
  __int64 v4; // r11
  __int64 QMPolicyState; // rax
  __int64 v9; // r9
  __int64 v10; // r11
  __int64 v11; // rbx
  __int64 result; // rax
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  bool v18; // zf
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  void *v26; // rsi
  unsigned int v27; // edi
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int128 v31; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 104);
  lpMem = 0;
  *a3 = 0;
  QMPolicyState = FindQMPolicyState(v4, a2, a3, a1);
  v11 = QMPolicyState;
  if ( !QMPolicyState )
    goto LABEL_2;
  v13 = *(_QWORD *)(a2 + 104);
  v14 = *(_QWORD *)(QMPolicyState + 40) - 0x11D177E38A171DD2LL;
  if ( !v14 )
    v14 = *(_QWORD *)(v11 + 48) - 1335908742LL;
  if ( !v14 )
  {
    v15 = *(_QWORD *)(v13 + 16) - 0x11D177E38A171DD2LL;
    if ( *(_QWORD *)(v13 + 16) != 0x11D177E38A171DD2LL )
      goto LABEL_9;
    v16 = *(_QWORD *)(v13 + 24);
    goto LABEL_8;
  }
  v17 = *(_QWORD *)(v11 + 40) - 0x11D176473F91A819LL;
  if ( *(_QWORD *)(v11 + 40) == 0x11D176473F91A819LL )
    v17 = *(_QWORD *)(v11 + 48) - 1792298374LL;
  v18 = v17 == 0;
  v19 = *(_QWORD *)(v13 + 16);
  if ( v18 )
  {
    v15 = v19 - 0x11D176473F91A819LL;
    if ( v15 )
      goto LABEL_9;
    v20 = *(_QWORD *)(v13 + 24);
    goto LABEL_16;
  }
  v21 = v19 - 0x11D177E38A171DD2LL;
  if ( !v21 )
    v21 = *(_QWORD *)(v13 + 24) - 1335908742LL;
  if ( !v21 )
  {
    v15 = *(_QWORD *)(v11 + 40) - 0x11D177E38A171DD2LL;
    if ( *(_QWORD *)(v11 + 40) == 0x11D177E38A171DD2LL )
    {
      v16 = *(_QWORD *)(v11 + 48);
LABEL_8:
      v15 = v16 - 1335908742;
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  v22 = *(_QWORD *)(v13 + 16) - 0x11D176473F91A819LL;
  if ( *(_QWORD *)(v13 + 16) == 0x11D176473F91A819LL )
    v22 = *(_QWORD *)(v13 + 24) - 1792298374LL;
  if ( !v22 )
  {
    v15 = *(_QWORD *)(v11 + 40) - 0x11D176473F91A819LL;
    if ( *(_QWORD *)(v11 + 40) == 0x11D176473F91A819LL )
    {
      v20 = *(_QWORD *)(v11 + 48);
LABEL_16:
      v15 = v20 - 1792298374;
    }
LABEL_9:
    if ( v15 )
    {
      PADeleteQMInfoForNFA(v9);
LABEL_2:
      result = PAAddQMInfoForNFA(a2, a4);
      *a3 = 1;
      return result;
    }
    return 0;
  }
  if ( !*(_DWORD *)(v11 + 64) )
  {
    v31 = *(_OWORD *)v11;
    PADeleteQMPolicy(&v31);
    goto LABEL_2;
  }
  if ( (unsigned int)EqualNegPolData(v10, *(_QWORD *)(a2 + 104)) )
    return 0;
  *(_OWORD *)(v11 + 24) = *(_OWORD *)(v13 + 32);
  *(_OWORD *)(v11 + 40) = *(_OWORD *)(v13 + 16);
  v23 = PACreateQMPolicy(a2, v11, &lpMem);
  v26 = lpMem;
  v27 = v23;
  if ( v23 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v29 = 19;
LABEL_35:
      WPP_SF_d(v28[2], v29, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v27);
    }
  }
  else
  {
    v30 = SetQMPolicy(v25, v24, *(_QWORD *)(v11 + 16), lpMem);
    v27 = v30;
    if ( v30 == 13025 )
    {
      v27 = 0;
      goto LABEL_42;
    }
    if ( v30 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v29 = 20;
        goto LABEL_35;
      }
    }
  }
LABEL_42:
  if ( v26 )
    PAFreeQMPolicy(v26);
  return v27;
}

```

## disassembly

```asm
0x18000cd90  mov     [rsp+arg_8], rbx
0x18000cd95  mov     [rsp+arg_10], rbp
0x18000cd9a  push    rsi
0x18000cd9b  push    rdi
0x18000cd9c  push    r14
0x18000cd9e  sub     rsp, 40h
0x18000cda2  mov     r11, [rcx+68h]
0x18000cda6  mov     ebp, r9d
0x18000cda9  mov     r9, rcx
0x18000cdac  mov     [rsp+58h+lpMem], 0
0x18000cdb5  mov     rcx, r11
0x18000cdb8  mov     dword ptr [r8], 0
0x18000cdbf  mov     r14, r8
0x18000cdc2  mov     rsi, rdx
0x18000cdc5  call    FindQMPolicyState
0x18000cdca  mov     rbx, rax
0x18000cdcd  test    rax, rax
0x18000cdd0  jnz     short loc_18000CDE8
0x18000cdd2  mov     edx, ebp
0x18000cdd4  mov     rcx, rsi
0x18000cdd7  call    PAAddQMInfoForNFA
0x18000cddc  mov     dword ptr [r14], 1
0x18000cde3  jmp     loc_18000CF8D
0x18000cde8  mov     rax, [rax+28h]
0x18000cdec  mov     r8, cs:qword_180055CD8
0x18000cdf3  mov     rdi, [rsi+68h]
0x18000cdf7  mov     rcx, cs:qword_180055CE0
0x18000cdfe  sub     rax, r8
0x18000ce01  jnz     short loc_18000CE0A
0x18000ce03  mov     rax, [rbx+30h]
0x18000ce07  sub     rax, rcx
0x18000ce0a  test    rax, rax
0x18000ce0d  jnz     short loc_18000CE32
0x18000ce0f  mov     rax, [rdi+10h]
0x18000ce13  sub     rax, r8
0x18000ce16  jnz     short loc_18000CE1F
0x18000ce18  mov     rax, [rdi+18h]
0x18000ce1c  sub     rax, rcx
0x18000ce1f  test    rax, rax
0x18000ce22  jz      loc_18000CEDC
0x18000ce28  mov     rcx, r9
0x18000ce2b  call    PADeleteQMInfoForNFA
0x18000ce30  jmp     short loc_18000CDD2
0x18000ce32  mov     rax, [rbx+28h]
0x18000ce36  mov     r10, cs:qword_180055F00
0x18000ce3d  mov     rdx, cs:qword_180055F08
0x18000ce44  sub     rax, r10
0x18000ce47  jnz     short loc_18000CE50
0x18000ce49  mov     rax, [rbx+30h]
0x18000ce4d  sub     rax, rdx
0x18000ce50  test    rax, rax
0x18000ce53  mov     rax, [rdi+10h]
0x18000ce57  jnz     short loc_18000CE67
0x18000ce59  sub     rax, r10
0x18000ce5c  jnz     short loc_18000CE1F
0x18000ce5e  mov     rax, [rdi+18h]
0x18000ce62  sub     rax, rdx
0x18000ce65  jmp     short loc_18000CE1F
0x18000ce67  sub     rax, r8
0x18000ce6a  jnz     short loc_18000CE73
0x18000ce6c  mov     rax, [rdi+18h]
0x18000ce70  sub     rax, rcx
0x18000ce73  test    rax, rax
0x18000ce76  jnz     short loc_18000CE87
0x18000ce78  mov     rax, [rbx+28h]
0x18000ce7c  sub     rax, r8
0x18000ce7f  jnz     short loc_18000CE1F
0x18000ce81  mov     rax, [rbx+30h]
0x18000ce85  jmp     short loc_18000CE1C
0x18000ce87  mov     rax, [rdi+10h]
0x18000ce8b  sub     rax, r10
0x18000ce8e  jnz     short loc_18000CE97
0x18000ce90  mov     rax, [rdi+18h]
0x18000ce94  sub     rax, rdx
0x18000ce97  test    rax, rax
0x18000ce9a  jnz     short loc_18000CEAF
0x18000ce9c  mov     rax, [rbx+28h]
0x18000cea0  sub     rax, r10
0x18000cea3  jnz     loc_18000CE1F
0x18000cea9  mov     rax, [rbx+30h]
0x18000cead  jmp     short loc_18000CE62
0x18000ceaf  cmp     dword ptr [rbx+40h], 0
0x18000ceb3  jnz     short loc_18000CECD
0x18000ceb5  movups  xmm0, xmmword ptr [rbx]
0x18000ceb8  lea     rcx, [rsp+58h+var_28]
0x18000cebd  movdqu  [rsp+58h+var_28], xmm0
0x18000cec3  call    PADeleteQMPolicy
0x18000cec8  jmp     loc_18000CDD2
0x18000cecd  mov     rdx, rdi
0x18000ced0  mov     rcx, r11
0x18000ced3  call    EqualNegPolData
0x18000ced8  test    eax, eax
0x18000ceda  jz      short loc_18000CEE3
0x18000cedc  xor     eax, eax
0x18000cede  jmp     loc_18000CF8D
0x18000cee3  movups  xmm0, xmmword ptr [rdi+20h]
0x18000cee7  lea     r8, [rsp+58h+lpMem]
0x18000ceec  mov     rdx, rbx
0x18000ceef  mov     rcx, rsi
0x18000cef2  movdqu  xmmword ptr [rbx+18h], xmm0
0x18000cef7  movups  xmm1, xmmword ptr [rdi+10h]
0x18000cefb  movdqu  xmmword ptr [rbx+28h], xmm1
0x18000cf00  call    PACreateQMPolicy
0x18000cf05  mov     rsi, [rsp+58h+lpMem]
0x18000cf0a  mov     edi, eax
0x18000cf0c  test    eax, eax
0x18000cf0e  jz      short loc_18000CF43
0x18000cf10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf17  lea     rax, WPP_GLOBAL_Control
0x18000cf1e  cmp     rcx, rax
0x18000cf21  jz      short loc_18000CF7E
0x18000cf23  test    byte ptr [rcx+1Ch], 10h
0x18000cf27  jz      short loc_18000CF7E
0x18000cf29  mov     edx, 13h
0x18000cf2e  mov     rcx, [rcx+10h]
0x18000cf32  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18000cf39  mov     r9d, edi
0x18000cf3c  call    WPP_SF_d
0x18000cf41  jmp     short loc_18000CF7E
0x18000cf43  mov     r8, [rbx+10h]
0x18000cf47  mov     r9, rsi
0x18000cf4a  call    SetQMPolicy
0x18000cf4f  mov     edi, eax
0x18000cf51  cmp     eax, 32E1h
0x18000cf56  jz      short loc_18000CF7C
0x18000cf58  test    eax, eax
0x18000cf5a  jz      short loc_18000CF7E
0x18000cf5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf63  lea     rax, WPP_GLOBAL_Control
0x18000cf6a  cmp     rcx, rax
0x18000cf6d  jz      short loc_18000CF7E
0x18000cf6f  test    byte ptr [rcx+1Ch], 10h
0x18000cf73  jz      short loc_18000CF7E
0x18000cf75  mov     edx, 14h
0x18000cf7a  jmp     short loc_18000CF2E
0x18000cf7c  xor     edi, edi
0x18000cf7e  test    rsi, rsi
0x18000cf81  jz      short loc_18000CF8B
0x18000cf83  mov     rcx, rsi; lpMem
0x18000cf86  call    PAFreeQMPolicy
0x18000cf8b  mov     eax, edi
0x18000cf8d  mov     rbx, [rsp+58h+arg_8]
0x18000cf92  mov     rbp, [rsp+58h+arg_10]
0x18000cf97  add     rsp, 40h
0x18000cf9b  pop     r14
0x18000cf9d  pop     rdi
0x18000cf9e  pop     rsi
0x18000cf9f  retn
```
