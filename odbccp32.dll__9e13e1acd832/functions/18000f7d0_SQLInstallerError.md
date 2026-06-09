# SQLInstallerError

- ea: `0x18000f7d0`
- end: `0x18000f8ae`
- name: `SQLInstallerError`
- size: `222`
- prototype: `SQLRETURN __stdcall(WORD iError, DWORD *pfErrorCode, LPSTR lpszErrorMsg, WORD cchErrorMsgMax, WORD *pcchErrorMsg)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x180004d40`
- `0x18000f7d0`
- `0x180013c2c`

## import_xrefs

- `msvcrt!calloc` at `0x18000f82e`
- `msvcrt!calloc` at `0x18000f82e`

## pseudocode

```c
SQLRETURN __stdcall SQLInstallerError(
        WORD iError,
        DWORD *pfErrorCode,
        LPSTR lpszErrorMsg,
        WORD cchErrorMsgMax,
        WORD *pcchErrorMsg)
{
  WORD *v5; // r14
  WCHAR *v10; // rbx
  SQLRETURN v11; // si
  __int64 v12; // rcx
  LPSTR v14; // [rsp+40h] [rbp-38h] BYREF
  __int16 v15; // [rsp+90h] [rbp+18h] BYREF

  v14 = lpszErrorMsg;
  v5 = (WORD *)&v15;
  v15 = 0;
  if ( pcchErrorMsg )
    v5 = pcchErrorMsg;
  if ( lpszErrorMsg && cchErrorMsgMax )
  {
    v10 = (WCHAR *)calloc((unsigned __int16)(2 * cchErrorMsgMax), 1u);
    if ( !v10 )
    {
      v11 = -1;
      goto LABEL_12;
    }
  }
  else
  {
    v10 = 0;
  }
  v11 = SQLInstallerErrorW(iError, pfErrorCode, v10, cchErrorMsgMax, v5);
  if ( (v11 & 0xFFFE) == 0 && lpszErrorMsg && cchErrorMsgMax )
    LConvertToAnsiWordLengths(v12, v10, *v5, &v14, cchErrorMsgMax, v5);
LABEL_12:
  OFree(v10);
  return v11;
}

```

## disassembly

```asm
0x18000f7d0  mov     rax, rsp
0x18000f7d3  mov     [rax+8], rbx
0x18000f7d7  mov     [rax+10h], rbp
0x18000f7db  push    rsi
0x18000f7dc  push    rdi
0x18000f7dd  push    r12
0x18000f7df  push    r14
0x18000f7e1  push    r15
0x18000f7e3  sub     rsp, 50h
0x18000f7e7  xor     r12d, r12d
0x18000f7ea  mov     [rax-38h], r8
0x18000f7ee  lea     r14, [rax+18h]
0x18000f7f2  mov     [rax+18h], r12w
0x18000f7f7  mov     rax, [rsp+78h+pcchErrorMsg]
0x18000f7ff  movzx   edi, r9w
0x18000f803  test    rax, rax
0x18000f806  mov     rbp, r8
0x18000f809  mov     rsi, rdx
0x18000f80c  movzx   r15d, cx
0x18000f810  cmovnz  r14, rax
0x18000f814  test    r8, r8
0x18000f817  jz      short loc_18000F841
0x18000f819  test    r9w, r9w
0x18000f81d  jz      short loc_18000F841
0x18000f81f  movzx   eax, r9w
0x18000f823  lea     edx, [r12+1]; Size
0x18000f828  add     ax, ax
0x18000f82b  movzx   ecx, ax; Count
0x18000f82e  call    cs:__imp_calloc
0x18000f834  mov     rbx, rax
0x18000f837  test    rax, rax
0x18000f83a  jnz     short loc_18000F844
0x18000f83c  or      esi, 0FFFFFFFFh
0x18000f83f  jmp     short loc_18000F88A
0x18000f841  mov     rbx, r12
0x18000f844  movzx   r9d, di; cchErrorMsgMax
0x18000f848  mov     [rsp+78h+var_58], r14; pcchErrorMsg
0x18000f84d  mov     r8, rbx; lpszErrorMsg
0x18000f850  mov     rdx, rsi; pfErrorCode
0x18000f853  movzx   ecx, r15w; iError
0x18000f857  call    SQLInstallerErrorW
0x18000f85c  movzx   esi, ax
0x18000f85f  test    ax, 0FFFEh
0x18000f863  jnz     short loc_18000F88A
0x18000f865  test    rbp, rbp
0x18000f868  jz      short loc_18000F88A
0x18000f86a  test    di, di
0x18000f86d  jz      short loc_18000F88A
0x18000f86f  movzx   r8d, word ptr [r14]
0x18000f873  lea     r9, [rsp+78h+var_38]
0x18000f878  mov     [rsp+78h+var_50], r14
0x18000f87d  mov     rdx, rbx
0x18000f880  mov     word ptr [rsp+78h+var_58], di
0x18000f885  call    LConvertToAnsiWordLengths
0x18000f88a  mov     rcx, rbx
0x18000f88d  call    OFree
0x18000f892  lea     r11, [rsp+78h+var_28]
0x18000f897  movzx   eax, si
0x18000f89a  mov     rbx, [r11+30h]
0x18000f89e  mov     rbp, [r11+38h]
0x18000f8a2  mov     rsp, r11
0x18000f8a5  pop     r15
0x18000f8a7  pop     r14
0x18000f8a9  pop     r12
0x18000f8ab  pop     rdi
0x18000f8ac  pop     rsi
0x18000f8ad  retn
```
