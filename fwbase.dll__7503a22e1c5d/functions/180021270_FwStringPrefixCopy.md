# FwStringPrefixCopy

- ea: `0x180021270`
- end: `0x1800213a3`
- name: `FwStringPrefixCopy`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180012b10`
- `0x1800201a0`
- `0x180020c50`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x18000c060`
- `0x1800130bc`
- `0x180021270`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180021357`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180021357`

## string_xrefs

- `0x18002130f`: `FwStringPrefixCopy`
- `0x18002133a`: `FwStringPrefixCopy`
- `0x18002137c`: `FwStringPrefixCopy`

## pseudocode

```c
__int64 __fastcall FwStringPrefixCopy(__int64 a1, unsigned __int64 a2, __int64 *a3)
{
  int v6; // ebx
  __int64 v7; // rdi
  unsigned __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, a1);
  v13 = 0;
  v6 = 0;
  *a3 = 0;
  v7 = 0;
  if ( a1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a1 + 2 * v8) );
    if ( a2 <= v8 )
    {
      v9 = FwSizeTMultiply(a2 + 1, 2, &v13);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v11 = FwAlloc(v13, v10);
        v7 = v11;
        if ( v11 )
        {
          if ( (unsigned int)_o_wcsncpy_s(v11, a2 + 1, a1, a2) )
          {
            v6 = -2147467259;
          }
          else
          {
            *a3 = v7;
            v7 = 0;
          }
        }
        else
        {
          v6 = FwReportErrorAsWinError("FwStringPrefixCopy", "FwAlloc", 8);
        }
      }
      else
      {
        FwReportReturnError("FwStringPrefixCopy", (unsigned int)v9);
      }
    }
    else
    {
      v6 = -2147024809;
    }
  }
  FwFree(v7);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwStringPrefixCopy", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021270  mov     [rsp+arg_8], rbx
0x180021275  mov     [rsp+arg_10], rbp
0x18002127a  push    rsi
0x18002127b  push    rdi
0x18002127c  push    r12
0x18002127e  push    r14
0x180021280  push    r15
0x180021282  sub     rsp, 20h
0x180021286  mov     r14, r8
0x180021289  mov     rbp, rdx
0x18002128c  mov     rsi, rcx
0x18002128f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021296  lea     rax, WPP_GLOBAL_Control
0x18002129d  cmp     rcx, rax
0x1800212a0  jz      short loc_1800212C0
0x1800212a2  test    byte ptr [rcx+1Ch], 4
0x1800212a6  jz      short loc_1800212C0
0x1800212a8  mov     rcx, [rcx+10h]
0x1800212ac  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x1800212b3  mov     edx, 0Eh
0x1800212b8  mov     r9, rsi
0x1800212bb  call    WPP_SF_S
0x1800212c0  xor     r12d, r12d
0x1800212c3  mov     [rsp+48h+arg_0], r12
0x1800212c8  mov     ebx, r12d
0x1800212cb  mov     [r14], r12
0x1800212ce  mov     edi, r12d
0x1800212d1  test    rsi, rsi
0x1800212d4  jz      loc_18002136E
0x1800212da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800212de  inc     rax
0x1800212e1  cmp     [rsi+rax*2], r12w
0x1800212e6  jnz     short loc_1800212DE
0x1800212e8  cmp     rbp, rax
0x1800212eb  jbe     short loc_1800212F4
0x1800212ed  mov     ebx, 80070057h
0x1800212f2  jmp     short loc_18002136E
0x1800212f4  lea     r8, [rsp+48h+arg_0]
0x1800212f9  mov     edx, 2
0x1800212fe  lea     rcx, [rbp+1]
0x180021302  call    FwSizeTMultiply
0x180021307  mov     ebx, eax
0x180021309  test    eax, eax
0x18002130b  jns     short loc_18002131D
0x18002130d  mov     edx, eax
0x18002130f  lea     rcx, aFwstringprefix_1; "FwStringPrefixCopy"
0x180021316  call    FwReportReturnError
0x18002131b  jmp     short loc_18002136E
0x18002131d  mov     rcx, [rsp+48h+arg_0]
0x180021322  call    FwAlloc
0x180021327  mov     rdi, rax
0x18002132a  test    rax, rax
0x18002132d  jnz     short loc_18002134A
0x18002132f  lea     r8d, [rax+8]
0x180021333  lea     rdx, aFwalloc_0; "FwAlloc"
0x18002133a  lea     rcx, aFwstringprefix_1; "FwStringPrefixCopy"
0x180021341  call    FwReportErrorAsWinError
0x180021346  mov     ebx, eax
0x180021348  jmp     short loc_18002136E
0x18002134a  mov     r9, rbp
0x18002134d  lea     rdx, [rbp+1]
0x180021351  mov     r8, rsi
0x180021354  mov     rcx, rdi
0x180021357  call    cs:__imp__o_wcsncpy_s
0x18002135d  test    eax, eax
0x18002135f  jz      short loc_180021368
0x180021361  mov     ebx, 80004005h
0x180021366  jmp     short loc_18002136E
0x180021368  mov     [r14], rdi
0x18002136b  mov     rdi, r12
0x18002136e  mov     rcx, rdi
0x180021371  call    FwFree
0x180021376  test    ebx, ebx
0x180021378  jns     short loc_18002138A
0x18002137a  mov     edx, ebx
0x18002137c  lea     rcx, aFwstringprefix_1; "FwStringPrefixCopy"
0x180021383  call    FwReportReturnError
0x180021388  mov     ebx, eax
0x18002138a  mov     rbp, [rsp+48h+arg_10]
0x18002138f  mov     eax, ebx
0x180021391  mov     rbx, [rsp+48h+arg_8]
0x180021396  add     rsp, 20h
0x18002139a  pop     r15
0x18002139c  pop     r14
0x18002139e  pop     r12
0x1800213a0  pop     rdi
0x1800213a1  pop     rsi
0x1800213a2  retn
```
