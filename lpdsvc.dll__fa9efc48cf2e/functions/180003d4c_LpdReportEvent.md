# LpdReportEvent

- ea: `0x180003d4c`
- end: `0x180003e9a`
- name: `LpdReportEvent`
- size: `334`
- prototype: `void __fastcall(DWORD dwEventID, WORD, LPCSTR *, int)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180003480`
- `0x180003ee4`
- `0x180005910`
- `0x180006014`
- `0x1800063b4`
- `0x180007354`
- `0x180007c10`
- `0x180009370`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x180003d4c`

## import_xrefs

- `ADVAPI32!ReportEventA` at `0x180003e83`
- `ADVAPI32!ReportEventA` at `0x180003e83`

## pseudocode

```c
void __fastcall LpdReportEvent(DWORD dwEventID, WORD a2, LPCSTR *a3, int a4)
{
  _QWORD *v7; // rcx
  WORD v8; // bx
  DWORD dwDataSize; // esi
  DWORD v10; // eax
  int *lpRawData; // rbp
  __int64 v12; // rdx
  int v13; // [rsp+B8h] [rbp+20h] BYREF

  v13 = a4;
  v7 = WPP_GLOBAL_Control;
  v8 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_90a417783231378e8d16226d33123045_Traceguids, dwEventID);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !hLogHandleGLB )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      WPP_SF_(v7[2], 13, WPP_90a417783231378e8d16226d33123045_Traceguids);
    return;
  }
  dwDataSize = 0;
  v10 = dwEventID >> 30;
  lpRawData = 0;
  if ( dwEventID >> 30 == 1 )
  {
    v8 = 4;
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 2) == 0 )
      goto LABEL_24;
    v12 = 14;
  }
  else if ( v10 == 2 )
  {
    v8 = 2;
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 2) == 0 )
      goto LABEL_24;
    v12 = 15;
  }
  else if ( v10 == 3 )
  {
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 2) == 0 )
      goto LABEL_24;
    v12 = 16;
  }
  else
  {
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 8) == 0 )
      goto LABEL_24;
    v12 = 17;
  }
  WPP_SF_(v7[2], v12, WPP_90a417783231378e8d16226d33123045_Traceguids);
LABEL_24:
  if ( v13 )
  {
    lpRawData = &v13;
    dwDataSize = 4;
  }
  ReportEventA(hLogHandleGLB, v8, 0, dwEventID, 0, a2, dwDataSize, a3, lpRawData);
}

```

## disassembly

```asm
0x180003d4c  mov     [rsp+arg_18], r9d
0x180003d51  push    rbx
0x180003d52  push    rbp
0x180003d53  push    rsi
0x180003d54  push    rdi
0x180003d55  push    r12
0x180003d57  push    r13
0x180003d59  push    r14
0x180003d5b  push    r15
0x180003d5d  sub     rsp, 58h
0x180003d61  mov     r14, r8
0x180003d64  movzx   r15d, dx
0x180003d68  mov     edi, ecx
0x180003d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d71  lea     r12, WPP_GLOBAL_Control
0x180003d78  lea     r13, WPP_90a417783231378e8d16226d33123045_Traceguids
0x180003d7f  mov     ebx, 1
0x180003d84  cmp     rcx, r12
0x180003d87  jz      short loc_180003DA7
0x180003d89  test    [rcx+1Ch], bl
0x180003d8c  jz      short loc_180003DA7
0x180003d8e  mov     rcx, [rcx+10h]
0x180003d92  lea     edx, [rbx+0Bh]
0x180003d95  mov     r9d, edi
0x180003d98  mov     r8, r13
0x180003d9b  call    WPP_SF_d
0x180003da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003da7  cmp     cs:hLogHandleGLB, 0
0x180003daf  jnz     short loc_180003DDA
0x180003db1  cmp     rcx, r12
0x180003db4  jz      loc_180003E89
0x180003dba  test    byte ptr [rcx+1Ch], 8
0x180003dbe  jz      loc_180003E89
0x180003dc4  mov     rcx, [rcx+10h]
0x180003dc8  mov     edx, 0Dh
0x180003dcd  mov     r8, r13
0x180003dd0  call    WPP_SF_
0x180003dd5  jmp     loc_180003E89
0x180003dda  xor     esi, esi
0x180003ddc  mov     eax, edi
0x180003dde  shr     eax, 1Eh
0x180003de1  xor     ebp, ebp
0x180003de3  lea     edx, [rsi+4]
0x180003de6  cmp     eax, ebx
0x180003de8  jnz     short loc_180003DFD
0x180003dea  movzx   ebx, dx
0x180003ded  cmp     rcx, r12
0x180003df0  jz      short loc_180003E44
0x180003df2  test    byte ptr [rcx+1Ch], 2
0x180003df6  jz      short loc_180003E44
0x180003df8  lea     edx, [rsi+0Eh]
0x180003dfb  jmp     short loc_180003E38
0x180003dfd  cmp     eax, 2
0x180003e00  jnz     short loc_180003E13
0x180003e02  mov     ebx, eax
0x180003e04  cmp     rcx, r12
0x180003e07  jz      short loc_180003E44
0x180003e09  test    [rcx+1Ch], bl
0x180003e0c  jz      short loc_180003E44
0x180003e0e  lea     edx, [rax+0Dh]
0x180003e11  jmp     short loc_180003E38
0x180003e13  cmp     eax, 3
0x180003e16  jnz     short loc_180003E28
0x180003e18  cmp     rcx, r12
0x180003e1b  jz      short loc_180003E44
0x180003e1d  test    byte ptr [rcx+1Ch], 2
0x180003e21  jz      short loc_180003E44
0x180003e23  lea     edx, [rax+0Dh]
0x180003e26  jmp     short loc_180003E38
0x180003e28  cmp     rcx, r12
0x180003e2b  jz      short loc_180003E44
0x180003e2d  test    byte ptr [rcx+1Ch], 8
0x180003e31  jz      short loc_180003E44
0x180003e33  mov     edx, 11h
0x180003e38  mov     rcx, [rcx+10h]
0x180003e3c  mov     r8, r13
0x180003e3f  call    WPP_SF_
0x180003e44  cmp     [rsp+98h+arg_18], esi
0x180003e4b  jz      short loc_180003E5A
0x180003e4d  lea     rbp, [rsp+98h+arg_18]
0x180003e55  mov     esi, 4
0x180003e5a  mov     rcx, cs:hLogHandleGLB; hEventLog
0x180003e61  xor     r8d, r8d; wCategory
0x180003e64  mov     [rsp+98h+lpRawData], rbp; lpRawData
0x180003e69  mov     r9d, edi; dwEventID
0x180003e6c  mov     [rsp+98h+lpStrings], r14; lpStrings
0x180003e71  movzx   edx, bx; wType
0x180003e74  mov     [rsp+98h+dwDataSize], esi; dwDataSize
0x180003e78  mov     [rsp+98h+wNumStrings], r15w; wNumStrings
0x180003e7e  mov     [rsp+98h+lpUserSid], r8; lpUserSid
0x180003e83  call    cs:__imp_ReportEventA
0x180003e89  add     rsp, 58h
0x180003e8d  pop     r15
0x180003e8f  pop     r14
0x180003e91  pop     r13
0x180003e93  pop     r12
0x180003e95  pop     rdi
0x180003e96  pop     rsi
0x180003e97  pop     rbp
0x180003e98  pop     rbx
0x180003e99  retn
```
