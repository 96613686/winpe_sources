# PopupErrorMessage(long,ulong)

- ea: `0x140001c68`
- end: `0x140001e6b`
- name: `?PopupErrorMessage@@YAXJK@Z`
- size: `515`
- prototype: `void __fastcall(DWORD dwMessageId, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400023ac`

## callees

- `0x140001008`
- `0x140001014`
- `0x1400019ec`
- `0x140001bf0`
- `0x140001c68`
- `0x140002168`
- `0x1400021dc`
- `0x140002cb0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140001ced`
- `KERNEL32!FormatMessageW` at `0x140001ced`
- `KERNEL32!LocalFree` at `0x140001d14`
- `KERNEL32!LocalFree` at `0x140001d14`

## pseudocode

```c
void __fastcall PopupErrorMessage(DWORD dwMessageId)
{
  __int64 v1; // rax
  unsigned __int64 v2; // rbx
  __int64 v3; // rcx
  unsigned __int64 v4; // rbx
  HWND v5; // rdx
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM dwInitParam[2]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-90h]
  __int16 v10; // [rsp+78h] [rbp-88h]
  void *v11; // [rsp+2C0h] [rbp+1C0h]
  unsigned __int16 v12[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v13[296]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v14[296]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v15[296]; // [rsp+980h] [rbp+880h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm);
  dwInitParam[1] = 0;
  dwInitParam[0] = (LPARAM)&CMessageDlg::`vftable';
  Block = 0;
  v11 = 0;
  v10 = 0;
  *(_QWORD *)Buffer = 0;
  if ( FormatMessageW(0x1100u, 0, dwMessageId, 0, Buffer, 0, 0) )
  {
    StringCchCopyW(v13, 0x122u, *(unsigned __int16 **)Buffer);
    LocalFree(*(HLOCAL *)Buffer);
  }
  else
  {
    StringCchCopyW(v13, 0x122u, L"Error message not found.");
  }
  LoadStr(0x72u, v15, 0x122u, L"%s");
  LoadStr(0x6Du, v12, 0x104u, &qword_1400044B0);
  StringCchPrintfW(v14, 0x122u, v15, v13);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v1 = -1;
  do
    ++v1;
  while ( v14[v1] );
  v2 = (int)v1 + 1;
  Block = operator new(saturated_mul(v2, 2u));
  StringCchCopyW((unsigned __int16 *)Block, v2, v14);
  v3 = -1;
  do
    ++v3;
  while ( v12[v3] );
  v4 = (int)v3 + 1;
  v11 = operator new(saturated_mul(v4, 2u));
  StringCchCopyW((unsigned __int16 *)v11, v4, v12);
  CDlg::_DoModalDlg((LPARAM)dwInitParam, v5, 107);
  dwInitParam[0] = (LPARAM)&CMessageDlg::`vftable';
  operator delete(Block);
  operator delete(v11);
}

```

## disassembly

```asm
0x140001c68  mov     [rsp-8+arg_8], rbx
0x140001c6d  mov     [rsp-8+arg_10], rsi
0x140001c72  push    rbp
0x140001c73  push    rdi
0x140001c74  push    r14
0x140001c76  lea     rbp, [rsp-0AE0h]
0x140001c7e  sub     rsp, 0BE0h
0x140001c85  mov     rax, cs:__security_cookie
0x140001c8c  xor     rax, rsp
0x140001c8f  mov     [rbp+0AF0h+var_20], rax
0x140001c96  movdqa  xmm0, cs:__xmm@0000000000007f010000000000000000
0x140001c9e  lea     rax, [rsp+0BF0h+Buffer]
0x140001ca3  xor     edi, edi
0x140001ca5  movdqa  [rsp+0BF0h+var_B90], xmm0
0x140001cab  mov     [rsp+0BF0h+Arguments], rdi; Arguments
0x140001cb0  lea     r14, ??_7CMessageDlg@@6B@; const CMessageDlg::`vftable'
0x140001cb7  mov     r8d, ecx; dwMessageId
0x140001cba  mov     [rsp+0BF0h+nSize], edi; nSize
0x140001cbe  xor     r9d, r9d; dwLanguageId
0x140001cc1  mov     [rsp+0BF0h+lpBuffer], rax; lpBuffer
0x140001cc6  xor     edx, edx; lpSource
0x140001cc8  mov     [rsp+0BF0h+var_B98], rdi
0x140001ccd  mov     ecx, 1100h; dwFlags
0x140001cd2  mov     [rsp+0BF0h+dwInitParam], r14
0x140001cd7  mov     [rsp+0BF0h+Block], rdi
0x140001cdc  mov     [rbp+0AF0h+var_930], rdi
0x140001ce3  mov     [rsp+0BF0h+var_B78], di
0x140001ce8  mov     qword ptr [rsp+0BF0h+Buffer], rdi
0x140001ced  call    cs:__imp_FormatMessageW
0x140001cf3  mov     ebx, 122h
0x140001cf8  lea     rcx, [rbp+0AF0h+var_710]; unsigned __int16 *
0x140001cff  mov     edx, ebx; unsigned __int64
0x140001d01  test    eax, eax
0x140001d03  jz      short loc_140001D1C
0x140001d05  mov     r8, qword ptr [rsp+0BF0h+Buffer]; unsigned __int16 *
0x140001d0a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001d0f  mov     rcx, qword ptr [rsp+0BF0h+Buffer]; hMem
0x140001d14  call    cs:__imp_LocalFree
0x140001d1a  jmp     short loc_140001D28
0x140001d1c  lea     r8, aErrorMessageNo; "Error message not found."
0x140001d23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001d28  lea     r9, aS; "%s"
0x140001d2f  mov     r8d, ebx; unsigned int
0x140001d32  lea     rdx, [rbp+0AF0h+var_270]; unsigned __int16 *
0x140001d39  mov     ecx, 72h ; 'r'; uID
0x140001d3e  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x140001d43  lea     r9, qword_1400044B0; unsigned __int16 *
0x140001d4a  mov     r8d, 104h; unsigned int
0x140001d50  lea     rdx, [rbp+0AF0h+var_920]; unsigned __int16 *
0x140001d57  mov     ecx, 6Dh ; 'm'; uID
0x140001d5c  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x140001d61  lea     r9, [rbp+0AF0h+var_710]
0x140001d68  mov     rdx, rbx; unsigned __int64
0x140001d6b  lea     r8, [rbp+0AF0h+var_270]; unsigned __int16 *
0x140001d72  lea     rcx, [rbp+0AF0h+var_4C0]; unsigned __int16 *
0x140001d79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140001d7e  movdqa  xmm0, cs:__xmm@0000000000007f010000000000000000
0x140001d86  lea     rcx, [rbp+0AF0h+var_4C0]
0x140001d8d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140001d91  movdqa  [rsp+0BF0h+var_B90], xmm0
0x140001d97  mov     rax, rsi
0x140001d9a  inc     rax
0x140001d9d  cmp     [rcx+rax*2], di
0x140001da1  jnz     short loc_140001D9A
0x140001da3  inc     eax
0x140001da5  movsxd  rbx, eax
0x140001da8  mov     eax, 2
0x140001dad  mul     rbx
0x140001db0  cmovb   rax, rsi
0x140001db4  mov     rcx, rax; Size
0x140001db7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001dbc  lea     r8, [rbp+0AF0h+var_4C0]; unsigned __int16 *
0x140001dc3  mov     [rsp+0BF0h+Block], rax
0x140001dc8  mov     rdx, rbx; unsigned __int64
0x140001dcb  mov     rcx, rax; unsigned __int16 *
0x140001dce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001dd3  mov     rcx, rsi
0x140001dd6  lea     r11, [rbp+0AF0h+var_920]
0x140001ddd  inc     rcx
0x140001de0  cmp     [r11+rcx*2], di
0x140001de5  jnz     short loc_140001DDD
0x140001de7  inc     ecx
0x140001de9  mov     eax, 2
0x140001dee  movsxd  rbx, ecx
0x140001df1  mul     rbx
0x140001df4  cmovb   rax, rsi
0x140001df8  mov     rcx, rax; Size
0x140001dfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001e00  lea     r8, [rbp+0AF0h+var_920]; unsigned __int16 *
0x140001e07  mov     [rbp+0AF0h+var_930], rax
0x140001e0e  mov     rdx, rbx; unsigned __int64
0x140001e11  mov     rcx, rax; unsigned __int16 *
0x140001e14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001e19  mov     r8d, 6Bh ; 'k'; int
0x140001e1f  lea     rcx, [rsp+0BF0h+dwInitParam]; dwInitParam
0x140001e24  call    ?_DoModalDlg@CDlg@@IEAA_JPEAUHWND__@@H@Z; CDlg::_DoModalDlg(HWND__ *,int)
0x140001e29  mov     rcx, [rsp+0BF0h+Block]; Block
0x140001e2e  mov     [rsp+0BF0h+dwInitParam], r14
0x140001e33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001e38  mov     rcx, [rbp+0AF0h+var_930]; Block
0x140001e3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001e44  mov     rcx, [rbp+0AF0h+var_20]
0x140001e4b  xor     rcx, rsp; StackCookie
0x140001e4e  call    __security_check_cookie
0x140001e53  lea     r11, [rsp+0BF0h+var_10]
0x140001e5b  mov     rbx, [r11+28h]
0x140001e5f  mov     rsi, [r11+30h]
0x140001e63  mov     rsp, r11
0x140001e66  pop     r14
0x140001e68  pop     rdi
0x140001e69  pop     rbp
0x140001e6a  retn
```
