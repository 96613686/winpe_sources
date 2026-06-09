# FwStringBuild

- ea: `0x180002c10`
- end: `0x180002e5c`
- name: `FwStringBuild`
- size: `588`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x180001680`
- `0x1800048c0`
- `0x18001f990`
- `0x18001fcd0`
- `0x1800201a0`
- `0x180020c50`
- `0x180020e00`
- `0x18002acb0`
- `0x18002baa0`
- `0x18002bef0`

## callees

- `0x180002c10`
- `0x180004750`
- `0x1800047e0`
- `0x1800130bc`
- `0x180017b58`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ce0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ce0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ccf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ccf`

## pseudocode

```c
__int64 FwStringBuild(_QWORD *a1, _WORD *a2, ...)
{
  va_list v2; // r9
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // edi
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v11; // rax
  _WORD *v12; // r11
  va_list v13; // r10
  _WORD *v14; // rdx
  SIZE_T v15; // rbx
  SIZE_T v16; // rcx
  _WORD *v17; // rax
  SIZE_T v18; // r9
  __int64 v19; // rcx
  bool v20; // zf
  SIZE_T v21; // r8
  _WORD *v22; // r9
  _WORD *v23; // rcx
  int v24; // r8d
  _WORD *v25; // [rsp+78h] [rbp+10h]
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  v25 = a2;
  *a1 = 0;
  va_copy(v2, va);
  v4 = 1;
  while ( 1 )
  {
    if ( !a2 )
    {
      if ( v4 > 0x7FFFFFFFFFFFFFFFLL )
      {
        v7 = -2147024362;
        FwReportReturnError((int)"FwStringBuild", 2147942934LL, v4);
      }
      else
      {
        v9 = 2 * v4;
        if ( 2 * v4 )
        {
          ProcessHeap = GetProcessHeap();
          v11 = HeapAlloc(ProcessHeap, 8u, v9);
          v12 = v11;
          if ( v11 )
          {
            *v11 = 0;
            va_copy(v13, va);
            v14 = v25;
            v7 = 0;
            if ( v25 )
            {
              v15 = v9 >> 1;
              do
              {
                if ( v15 - 1 <= 0x7FFFFFFE )
                {
                  v16 = v15;
                  v17 = v12;
                  while ( *v17 )
                  {
                    ++v17;
                    if ( !--v16 )
                    {
                      v18 = 0;
                      goto LABEL_21;
                    }
                  }
                  v18 = v15 - v16;
LABEL_21:
                  if ( v16 )
                  {
                    v19 = 2147483646;
                    v21 = v15 - v18;
                    v20 = v15 == v18;
                    v22 = &v12[v18];
                    if ( !v20 )
                    {
                      do
                      {
                        if ( !v19 )
                          break;
                        if ( !*v14 )
                          break;
                        *v22++ = *v14++;
                        --v19;
                        --v21;
                      }
                      while ( v21 );
                    }
                    v23 = v22 - 1;
                    if ( v21 )
                      v23 = v22;
                    *v23 = 0;
                  }
                }
                v14 = *(_WORD **)v13;
                v13 += 8;
              }
              while ( v14 );
            }
            *a1 = v12;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, v12);
            return v7;
          }
        }
        else
        {
          SetLastError(0x57u);
        }
        v7 = FwReportErrorAsWinError((int)"FwStringBuild", (__int64)"FwAlloc", 8);
        if ( (v7 & 0x80000000) == 0 )
          return v7;
      }
      return FwReportReturnError((int)"FwStringBuild", v7, v4);
    }
    v5 = v4;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v4 += v6;
    if ( v5 > v4 )
      break;
    a2 = *(_WORD **)v2;
    v2 += 8;
  }
  v7 = -2147024362;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return FwReportReturnError((int)"FwStringBuild", v7, v4);
  WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, v4, (unsigned int)"FwStringBuild", 22);
  return FwReportReturnError((int)"FwStringBuild", 2147942934LL, v24);
}

```

## disassembly

```asm
0x180002c10  mov     r11, rsp
0x180002c13  mov     [r11+10h], rdx
0x180002c17  mov     [r11+18h], r8
0x180002c1b  mov     [r11+20h], r9
0x180002c1f  push    rbp
0x180002c20  push    rsi
0x180002c21  sub     rsp, 58h
0x180002c25  mov     rax, cs:__security_cookie
0x180002c2c  xor     rax, rsp
0x180002c2f  mov     [rsp+68h+var_30], rax
0x180002c34  xor     ebp, ebp
0x180002c36  mov     [r11-18h], rbx
0x180002c3a  mov     [rcx], rbp
0x180002c3d  lea     r9, [r11+18h]
0x180002c41  mov     rsi, rcx
0x180002c44  mov     [r11-20h], rdi
0x180002c48  mov     r8d, 1
0x180002c4e  xchg    ax, ax
0x180002c50  test    rdx, rdx
0x180002c53  jz      short loc_180002CAF
0x180002c55  mov     rcx, r8
0x180002c58  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002c5f  nop
0x180002c60  inc     rax
0x180002c63  cmp     [rdx+rax*2], bp
0x180002c67  jnz     short loc_180002C60
0x180002c69  add     r8, rax
0x180002c6c  cmp     rcx, r8
0x180002c6f  ja      short loc_180002C7A
0x180002c71  mov     rdx, [r9]
0x180002c74  add     r9, 8
0x180002c78  jmp     short loc_180002C50
0x180002c7a  mov     edi, 80070216h
0x180002c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c86  lea     rax, WPP_GLOBAL_Control
0x180002c8d  cmp     rcx, rax
0x180002c90  jz      short loc_180002C9C
0x180002c92  test    byte ptr [rcx+1Ch], 1
0x180002c96  jnz     loc_180002DCE
0x180002c9c  mov     edx, edi
0x180002c9e  lea     rcx, aFwstringbuild_0; "FwStringBuild"
0x180002ca5  call    FwReportReturnError
0x180002caa  jmp     loc_180002DB0
0x180002caf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002cb9  cmp     r8, rax
0x180002cbc  ja      loc_180002E1A
0x180002cc2  lea     rbx, [r8+r8]
0x180002cc6  test    rbx, rbx
0x180002cc9  jz      loc_180002E32
0x180002ccf  call    cs:__imp_GetProcessHeap
0x180002cd5  mov     r8, rbx; dwBytes
0x180002cd8  mov     edx, 8; dwFlags
0x180002cdd  mov     rcx, rax; hHeap
0x180002ce0  call    cs:__imp_HeapAlloc
0x180002ce6  mov     r11, rax
0x180002ce9  test    rax, rax
0x180002cec  jz      loc_180002DF6
0x180002cf2  mov     [rax], bp
0x180002cf5  lea     r10, [rsp+68h+arg_10]
0x180002cfd  mov     rdx, [rsp+68h+arg_8]
0x180002d02  mov     edi, ebp
0x180002d04  test    rdx, rdx
0x180002d07  jz      loc_180002D8E
0x180002d0d  shr     rbx, 1
0x180002d10  lea     rax, [rbx-1]
0x180002d14  cmp     rax, 7FFFFFFEh
0x180002d1a  ja      short loc_180002D82
0x180002d1c  mov     rcx, rbx
0x180002d1f  mov     rax, r11
0x180002d22  mov     r9, rbx
0x180002d25  cmp     [rax], bp
0x180002d28  jz      short loc_180002D39
0x180002d2a  add     rax, 2
0x180002d2e  sub     rcx, 1
0x180002d32  jnz     short loc_180002D25
0x180002d34  mov     r9, rbp
0x180002d37  jmp     short loc_180002D3C
0x180002d39  sub     r9, rcx
0x180002d3c  test    rcx, rcx
0x180002d3f  jz      short loc_180002D82
0x180002d41  mov     r8, rbx
0x180002d44  mov     ecx, 7FFFFFFEh
0x180002d49  sub     r8, r9
0x180002d4c  lea     r9, [r11+r9*2]
0x180002d50  jz      short loc_180002D74
0x180002d52  test    rcx, rcx
0x180002d55  jz      short loc_180002D74
0x180002d57  movzx   eax, word ptr [rdx]
0x180002d5a  test    ax, ax
0x180002d5d  jz      short loc_180002D74
0x180002d5f  mov     [r9], ax
0x180002d63  add     rdx, 2
0x180002d67  add     r9, 2
0x180002d6b  dec     rcx
0x180002d6e  sub     r8, 1
0x180002d72  jnz     short loc_180002D52
0x180002d74  test    r8, r8
0x180002d77  lea     rcx, [r9-2]
0x180002d7b  cmovnz  rcx, r9
0x180002d7f  mov     [rcx], bp
0x180002d82  mov     rdx, [r10]
0x180002d85  add     r10, 8
0x180002d89  test    rdx, rdx
0x180002d8c  jnz     short loc_180002D10
0x180002d8e  mov     [rsi], r11
0x180002d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d98  lea     rax, WPP_GLOBAL_Control
0x180002d9f  cmp     rcx, rax
0x180002da2  jz      short loc_180002DAE
0x180002da4  test    byte ptr [rcx+1Ch], 4
0x180002da8  jnz     loc_180002E3F
0x180002dae  mov     eax, edi
0x180002db0  mov     rdi, [rsp+68h+var_20]
0x180002db5  mov     rbx, [rsp+68h+var_18]
0x180002dba  mov     rcx, [rsp+68h+var_30]
0x180002dbf  xor     rcx, rsp; StackCookie
0x180002dc2  call    __security_check_cookie
0x180002dc7  add     rsp, 58h
0x180002dcb  pop     rsi
0x180002dcc  pop     rbp
0x180002dcd  retn
0x180002dce  mov     rcx, [rcx+10h]
0x180002dd2  lea     r9, aFwstringbuild_0; "FwStringBuild"
0x180002dd9  mov     [rsp+68h+var_48], 80070216h
0x180002de1  call    WPP_SF_sD
0x180002de6  mov     edx, edi
0x180002de8  lea     rcx, aFwstringbuild_0; "FwStringBuild"
0x180002def  call    FwReportReturnError
0x180002df4  jmp     short loc_180002DB0
0x180002df6  mov     r8d, 8
0x180002dfc  lea     rdx, aFwalloc_0; "FwAlloc"
0x180002e03  lea     rcx, aFwstringbuild_0; "FwStringBuild"
0x180002e0a  call    FwReportErrorAsWinError
0x180002e0f  mov     edi, eax
0x180002e11  test    eax, eax
0x180002e13  jns     short loc_180002DAE
0x180002e15  jmp     loc_180002C9C
0x180002e1a  mov     edi, 80070216h
0x180002e1f  lea     rcx, aFwstringbuild_0; "FwStringBuild"
0x180002e26  mov     edx, edi
0x180002e28  call    FwReportReturnError
0x180002e2d  jmp     loc_180002C9C
0x180002e32  mov     ecx, 57h ; 'W'; dwErrCode
0x180002e37  call    cs:__imp_SetLastError
0x180002e3d  jmp     short loc_180002DF6
0x180002e3f  mov     rcx, [rcx+10h]
0x180002e43  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x180002e4a  mov     edx, 10h
0x180002e4f  mov     r9, r11
0x180002e52  call    WPP_SF_S
0x180002e57  jmp     loc_180002DAE
```
