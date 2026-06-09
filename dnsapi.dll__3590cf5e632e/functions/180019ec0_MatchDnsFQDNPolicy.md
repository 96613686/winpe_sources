# MatchDnsFQDNPolicy

- ea: `0x180019ec0`
- end: `0x180019fd9`
- name: `MatchDnsFQDNPolicy`
- size: `281`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a58c`

## callees

- `0x180019ec0`
- `0x180019fe0`
- `0x1800dc038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180019ef2`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180019ef2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019f6a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019f6a`

## pseudocode

```c
__int64 __fastcall MatchDnsFQDNPolicy(WCHAR *lpString2, __int64 a2, _QWORD *a3)
{
  WCHAR v5; // ax
  unsigned int v6; // ebp
  PCNZWCH v7; // rdi
  unsigned int v8; // ebx
  int v9; // ecx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // r14
  _QWORD *i; // rdi
  _QWORD *v14; // rbx
  const WCHAR *v15; // r8

  *a3 = 0;
  v5 = *lpString2;
  v6 = 4312;
  v7 = lpString2;
  v8 = 0;
  while ( v5 )
  {
    ++v7;
    v9 = (unsigned __int16)_o_towlower(v5);
    v5 = *v7;
    v8 = v9 + 33 * v8;
  }
  v10 = xmmword_180112B70;
  if ( (_QWORD)xmmword_180112B70 )
  {
    v11 = v8 % 0x1F3;
    v12 = 2LL * v11;
    for ( i = *(_QWORD **)(xmmword_180112B70 + 16LL * v11); i != (_QWORD *)(v10 + 8 * v12); i = (_QWORD *)*i )
    {
      v14 = i - 1;
      v15 = (const WCHAR *)i[8];
      if ( v15 )
      {
        if ( CompareStringW(0x409u, 1u, v15, -1, lpString2, -1) == 2 )
        {
          ReferenceDnsPolicyConfigNode(i - 1);
          if ( i != (_QWORD *)8 )
          {
            v6 = 0;
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_SS(
                1035,
                25,
                (unsigned int)WPP_85172e4714023e67c3665ec5069963d4_Traceguids,
                (_DWORD)lpString2,
                v14[9]);
            *a3 = v14;
          }
          return v6;
        }
        v10 = xmmword_180112B70;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180019ec0  push    rbx
0x180019ec2  push    rbp
0x180019ec3  push    rsi
0x180019ec4  push    rdi
0x180019ec5  push    r12
0x180019ec7  push    r14
0x180019ec9  push    r15
0x180019ecb  sub     rsp, 30h
0x180019ecf  xor     r12d, r12d
0x180019ed2  mov     r15, r8
0x180019ed5  mov     [r8], r12
0x180019ed8  mov     rsi, rcx
0x180019edb  movzx   eax, word ptr [rcx]
0x180019ede  mov     ebp, 10D8h
0x180019ee3  mov     rdi, rcx
0x180019ee6  mov     ebx, r12d
0x180019ee9  jmp     short loc_180019F09
0x180019eeb  movzx   ecx, ax
0x180019eee  lea     rdi, [rdi+2]
0x180019ef2  call    cs:__imp__o_towlower
0x180019ef9  nop     dword ptr [rax+rax+00h]
0x180019efe  movzx   ecx, ax
0x180019f01  movzx   eax, word ptr [rdi]
0x180019f04  imul    ebx, 21h ; '!'
0x180019f07  add     ebx, ecx
0x180019f09  test    ax, ax
0x180019f0c  jnz     short loc_180019EEB
0x180019f0e  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019f15  test    rcx, rcx
0x180019f18  jz      loc_180019FA3
0x180019f1e  mov     eax, 20D56B39h
0x180019f23  mul     ebx
0x180019f25  shr     edx, 6
0x180019f28  imul    eax, edx, 1F3h
0x180019f2e  sub     ebx, eax
0x180019f30  mov     r14d, ebx
0x180019f33  add     r14, r14
0x180019f36  mov     rdi, [rcx+r14*8]
0x180019f3a  lea     rax, [rcx+r14*8]
0x180019f3e  cmp     rdi, rax
0x180019f41  jz      short loc_180019FA3
0x180019f43  lea     rbx, [rdi-8]
0x180019f47  mov     r8, [rbx+48h]; lpString1
0x180019f4b  test    r8, r8
0x180019f4e  jz      short loc_180019F82
0x180019f50  or      r9d, 0FFFFFFFFh; cchCount1
0x180019f54  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019f5c  mov     ecx, 409h; Locale
0x180019f61  mov     [rsp+68h+lpString2], rsi; lpString2
0x180019f66  lea     edx, [r9+2]; dwCmpFlags
0x180019f6a  call    cs:__imp_CompareStringW
0x180019f71  nop     dword ptr [rax+rax+00h]
0x180019f76  cmp     eax, 2
0x180019f79  jz      short loc_180019F87
0x180019f7b  mov     rcx, qword ptr cs:xmmword_180112B70
0x180019f82  mov     rdi, [rdi]
0x180019f85  jmp     short loc_180019F3A
0x180019f87  mov     rcx, rbx
0x180019f8a  call    ReferenceDnsPolicyConfigNode
0x180019f8f  test    rbx, rbx
0x180019f92  jz      short loc_180019FA3
0x180019f94  mov     ebp, r12d
0x180019f97  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180019f9e  jnz     short loc_180019FB5
0x180019fa0  mov     [r15], rbx
0x180019fa3  mov     eax, ebp
0x180019fa5  add     rsp, 30h
0x180019fa9  pop     r15
0x180019fab  pop     r14
0x180019fad  pop     r12
0x180019faf  pop     rdi
0x180019fb0  pop     rsi
0x180019fb1  pop     rbp
0x180019fb2  pop     rbx
0x180019fb3  retn
0x180019fb5  mov     r8, [rbx+48h]
0x180019fb9  mov     edx, 19h
0x180019fbe  mov     [rsp+68h+lpString2], r8
0x180019fc3  mov     ecx, 40Bh
0x180019fc8  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x180019fcf  mov     r9, rsi
0x180019fd2  call    WPP_SF_SS
0x180019fd7  jmp     short loc_180019FA0
```
