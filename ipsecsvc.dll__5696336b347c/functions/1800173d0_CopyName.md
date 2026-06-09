# CopyName

- ea: `0x1800173d0`
- end: `0x18001752d`
- name: `CopyName`
- size: `349`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, _QWORD *)`
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cea0`
- `0x18001d020`
- `0x18001f4b4`
- `0x18001f5e8`
- `0x18001fb20`
- `0x18001fcb0`
- `0x180021e30`
- `0x180021f80`
- `0x1800250ec`
- `0x1800251f8`
- `0x1800258a0`
- `0x1800259f0`
- `0x180030cb0`
- `0x180033b40`
- `0x180033e7c`

## callees

- `0x18000e510`
- `0x18000f570`
- `0x1800173d0`
- `0x180017534`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall CopyName(STRSAFE_LPCWSTR pszSrc, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r11
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  size_t v9; // rsi
  unsigned __int16 v10; // ax
  unsigned __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp+18h]

  pszDest = 0;
  v12 = 0;
  v4 = 0;
  v5 = 0;
  if ( !pszSrc || !*pszSrc )
    goto LABEL_23;
  v6 = -1;
  do
    ++v6;
  while ( pszSrc[v6] );
  v4 = NsuSizeTMultiply(v6, 2, &v12);
  if ( !v4 )
  {
    v9 = v12 + 2;
    if ( v12 >= v12 + 2 )
    {
      v4 = 534;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_22;
      v8 = 11;
      goto LABEL_21;
    }
    v4 = SPDApiBufferAllocate(v12 + 2);
    if ( v4 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_22;
      v8 = 12;
      goto LABEL_21;
    }
    v10 = StringCbCopyW(pszDest, v9, pszSrc);
    v4 = v10;
    if ( v10 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_22;
      v8 = 13;
      goto LABEL_21;
    }
LABEL_23:
    *a2 = v5;
    return v4;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_22;
  v8 = 10;
LABEL_21:
  WPP_SF_d(v7[2], v8, WPP_bb8ad0123c3f3ab26dbf6222817f5839_Traceguids, v4);
LABEL_22:
  *a2 = 0;
  return v4;
}

```

## disassembly

```asm
0x1800173d0  mov     rax, rsp
0x1800173d3  mov     [rax+10h], rbx
0x1800173d7  mov     [rax+20h], rbp
0x1800173db  push    rsi
0x1800173dc  push    rdi
0x1800173dd  push    r14
0x1800173df  sub     rsp, 20h
0x1800173e3  xor     ebp, ebp
0x1800173e5  mov     r14, rdx
0x1800173e8  mov     [rax+18h], rbp
0x1800173ec  mov     rdi, rcx
0x1800173ef  mov     [rax+8], rbp
0x1800173f3  mov     ebx, ebp
0x1800173f5  mov     r11d, ebp
0x1800173f8  test    rcx, rcx
0x1800173fb  jz      loc_180017515
0x180017401  cmp     [rcx], bp
0x180017404  jz      loc_180017515
0x18001740a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001740e  inc     rcx
0x180017411  cmp     [rdi+rcx*2], bp
0x180017415  jnz     short loc_18001740E
0x180017417  lea     r8, [rsp+38h+arg_0]
0x18001741c  mov     edx, 2
0x180017421  call    NsuSizeTMultiply
0x180017426  mov     ebx, eax
0x180017428  test    eax, eax
0x18001742a  jz      short loc_180017457
0x18001742c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017433  lea     rax, WPP_GLOBAL_Control
0x18001743a  cmp     rcx, rax
0x18001743d  jz      loc_180017510
0x180017443  test    byte ptr [rcx+1Ch], 10h
0x180017447  jz      loc_180017510
0x18001744d  mov     edx, 0Ah
0x180017452  jmp     loc_1800174FD
0x180017457  mov     rax, [rsp+38h+arg_0]
0x18001745c  lea     rsi, [rax+2]
0x180017460  cmp     rax, rsi
0x180017463  jbe     short loc_180017492
0x180017465  mov     ebx, 216h
0x18001746a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017471  lea     rax, WPP_GLOBAL_Control
0x180017478  cmp     rcx, rax
0x18001747b  jz      loc_180017510
0x180017481  test    byte ptr [rcx+1Ch], 10h
0x180017485  jz      loc_180017510
0x18001748b  mov     edx, 0Bh
0x180017490  jmp     short loc_1800174FD
0x180017492  lea     rdx, [rsp+38h+pszDest]
0x180017497  mov     rcx, rsi; Size
0x18001749a  call    SPDApiBufferAllocate
0x18001749f  mov     ebx, eax
0x1800174a1  test    eax, eax
0x1800174a3  jz      short loc_1800174C5
0x1800174a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174ac  lea     rax, WPP_GLOBAL_Control
0x1800174b3  cmp     rcx, rax
0x1800174b6  jz      short loc_180017510
0x1800174b8  test    byte ptr [rcx+1Ch], 10h
0x1800174bc  jz      short loc_180017510
0x1800174be  mov     edx, 0Ch
0x1800174c3  jmp     short loc_1800174FD
0x1800174c5  mov     r11, [rsp+38h+pszDest]
0x1800174ca  mov     r8, rdi; pszSrc
0x1800174cd  mov     rcx, r11; pszDest
0x1800174d0  mov     rdx, rsi; cbDest
0x1800174d3  call    StringCbCopyW
0x1800174d8  movzx   ebx, ax
0x1800174db  test    ebx, ebx
0x1800174dd  jz      short loc_180017515
0x1800174df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174e6  lea     rax, WPP_GLOBAL_Control
0x1800174ed  cmp     rcx, rax
0x1800174f0  jz      short loc_180017510
0x1800174f2  test    byte ptr [rcx+1Ch], 10h
0x1800174f6  jz      short loc_180017510
0x1800174f8  mov     edx, 0Dh
0x1800174fd  mov     rcx, [rcx+10h]
0x180017501  lea     r8, WPP_bb8ad0123c3f3ab26dbf6222817f5839_Traceguids
0x180017508  mov     r9d, ebx
0x18001750b  call    WPP_SF_d
0x180017510  mov     [r14], rbp
0x180017513  jmp     short loc_180017518
0x180017515  mov     [r14], r11
0x180017518  mov     rbp, [rsp+38h+arg_18]
0x18001751d  mov     eax, ebx
0x18001751f  mov     rbx, [rsp+38h+arg_8]
0x180017524  add     rsp, 20h
0x180017528  pop     r14
0x18001752a  pop     rdi
0x18001752b  pop     rsi
0x18001752c  retn
```
