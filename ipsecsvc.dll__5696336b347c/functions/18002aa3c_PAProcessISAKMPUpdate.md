# PAProcessISAKMPUpdate

- ea: `0x18002aa3c`
- end: `0x18002aba1`
- name: `PAProcessISAKMPUpdate`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18002afd0`

## callees

- `0x180007b54`
- `0x18000c51c`
- `0x18000e510`
- `0x18001b298`
- `0x180027408`
- `0x180027604`
- `0x1800278e0`
- `0x18002791c`
- `0x18002a268`
- `0x18002aa3c`

## pseudocode

```c
__int64 PAProcessISAKMPUpdate(__int128 *a1, __int64 a2, unsigned int a3, ...)
{
  __int128 v3; // xmm0
  __int64 v4; // rbx
  __int64 MMPolicyState; // rax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdi
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rsi
  unsigned int v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int128 v19; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+8h] BYREF
  __int64 v21; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v23; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  v23 = va_arg(va1, _QWORD);
  v3 = *a1;
  v4 = v21;
  lpMem = 0;
  v19 = v3;
  MMPolicyState = FindMMPolicyState(&v19);
  v10 = MMPolicyState;
  if ( !MMPolicyState )
    goto LABEL_2;
  if ( !*(_DWORD *)(MMPolicyState + 24) )
  {
    PADeleteMMPolicyState(MMPolicyState);
LABEL_2:
    PAAddMMPolicies((__int64 *)va, v8, (unsigned int)v23);
    return PAAddMMFilters(v4, a2, a3, (unsigned int)v23);
  }
  if ( (unsigned int)EqualISAKMPData(v9, v4) )
    return 0;
  v12 = PACreateMMPolicy(v4, v10, &lpMem);
  v15 = lpMem;
  v16 = v12;
  if ( v12 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v18 = 14;
LABEL_16:
        WPP_SF_d(v17[2], v18, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v12);
        v17 = WPP_GLOBAL_Control;
        goto LABEL_17;
      }
      goto LABEL_17;
    }
  }
  else
  {
    v12 = SetMMPolicy(v14, v13, *(_QWORD *)(v10 + 16));
    v16 = v12;
    if ( v12 == 13024 )
    {
      v16 = 0;
    }
    else if ( v12 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 15;
          goto LABEL_16;
        }
LABEL_17:
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x10) != 0 )
          WPP_SF_d(v17[2], 16, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids, v16);
      }
    }
  }
  if ( v15 )
    PAFreeQMPolicy(v15);
  return v16;
}

```

## disassembly

```asm
0x18002aa3c  mov     rax, rsp
0x18002aa3f  mov     [rax+10h], rbx
0x18002aa43  mov     [rax+20h], r9
0x18002aa47  push    rbp
0x18002aa48  push    rsi
0x18002aa49  push    rdi
0x18002aa4a  sub     rsp, 40h
0x18002aa4e  movups  xmm0, xmmword ptr [rcx]
0x18002aa51  mov     rbx, r9
0x18002aa54  mov     qword ptr [rax+8], 0
0x18002aa5c  mov     r9, rcx
0x18002aa5f  mov     esi, r8d
0x18002aa62  lea     rcx, [rax-28h]
0x18002aa66  mov     rbp, rdx
0x18002aa69  movdqu  xmmword ptr [rax-28h], xmm0
0x18002aa6e  call    FindMMPolicyState
0x18002aa73  mov     rdi, rax
0x18002aa76  test    rax, rax
0x18002aa79  jnz     short loc_18002AAA8
0x18002aa7b  mov     r8d, dword ptr [rsp+58h+arg_20]
0x18002aa83  lea     rcx, [rsp+58h+arg_18]
0x18002aa88  call    PAAddMMPolicies
0x18002aa8d  mov     r9d, dword ptr [rsp+58h+arg_20]
0x18002aa95  mov     r8d, esi
0x18002aa98  mov     rdx, rbp
0x18002aa9b  mov     rcx, rbx
0x18002aa9e  call    PAAddMMFilters
0x18002aaa3  jmp     loc_18002AB94
0x18002aaa8  cmp     dword ptr [rax+18h], 0
0x18002aaac  jnz     short loc_18002AAB8
0x18002aaae  mov     rcx, rdi
0x18002aab1  call    PADeleteMMPolicyState
0x18002aab6  jmp     short loc_18002AA7B
0x18002aab8  mov     rdx, rbx
0x18002aabb  mov     rcx, r9
0x18002aabe  call    EqualISAKMPData
0x18002aac3  test    eax, eax
0x18002aac5  jz      short loc_18002AACE
0x18002aac7  xor     eax, eax
0x18002aac9  jmp     loc_18002AB94
0x18002aace  lea     r8, [rsp+58h+lpMem]
0x18002aad3  mov     rdx, rdi
0x18002aad6  mov     rcx, rbx
0x18002aad9  call    PACreateMMPolicy
0x18002aade  mov     rsi, [rsp+58h+lpMem]
0x18002aae3  mov     ebx, eax
0x18002aae5  mov     ebp, 10h
0x18002aaea  test    eax, eax
0x18002aaec  jz      short loc_18002AB10
0x18002aaee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaf5  lea     rdi, WPP_GLOBAL_Control
0x18002aafc  cmp     rcx, rdi
0x18002aaff  jz      loc_18002AB85
0x18002ab05  test    [rcx+1Ch], bpl
0x18002ab09  jz      short loc_18002AB61
0x18002ab0b  lea     edx, [rbp-2]
0x18002ab0e  jmp     short loc_18002AB47
0x18002ab10  mov     r8, [rdi+10h]
0x18002ab14  mov     r9, rsi
0x18002ab17  call    SetMMPolicy
0x18002ab1c  mov     ebx, eax
0x18002ab1e  cmp     eax, 32E0h
0x18002ab23  jz      short loc_18002AB83
0x18002ab25  test    eax, eax
0x18002ab27  jz      short loc_18002AB85
0x18002ab29  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab30  lea     rdi, WPP_GLOBAL_Control
0x18002ab37  cmp     rcx, rdi
0x18002ab3a  jz      short loc_18002AB85
0x18002ab3c  test    [rcx+1Ch], bpl
0x18002ab40  jz      short loc_18002AB61
0x18002ab42  mov     edx, 0Fh
0x18002ab47  mov     rcx, [rcx+10h]
0x18002ab4b  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002ab52  mov     r9d, eax
0x18002ab55  call    WPP_SF_d
0x18002ab5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab61  cmp     rcx, rdi
0x18002ab64  jz      short loc_18002AB85
0x18002ab66  test    [rcx+1Ch], bpl
0x18002ab6a  jz      short loc_18002AB85
0x18002ab6c  mov     rcx, [rcx+10h]
0x18002ab70  lea     r8, WPP_47679c2dfd963daebcc0d8b26e9f494e_Traceguids
0x18002ab77  mov     edx, ebp
0x18002ab79  mov     r9d, ebx
0x18002ab7c  call    WPP_SF_d
0x18002ab81  jmp     short loc_18002AB85
0x18002ab83  xor     ebx, ebx
0x18002ab85  test    rsi, rsi
0x18002ab88  jz      short loc_18002AB92
0x18002ab8a  mov     rcx, rsi; lpMem
0x18002ab8d  call    PAFreeQMPolicy
0x18002ab92  mov     eax, ebx
0x18002ab94  mov     rbx, [rsp+58h+arg_8]
0x18002ab99  add     rsp, 40h
0x18002ab9d  pop     rdi
0x18002ab9e  pop     rsi
0x18002ab9f  pop     rbp
0x18002aba0  retn
```
