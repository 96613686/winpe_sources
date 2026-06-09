# FormatEtcSaveToStream(IStream *,tagFORMATETC const *)

- ea: `0x180019cf0`
- end: `0x180019e2f`
- name: `?FormatEtcSaveToStream@@YAJPEAUIStream@@PEBUtagFORMATETC@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(struct IStream *pstm, const struct tagFORMATETC *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a4a0`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180019cf0`

## import_xrefs

- `SHLWAPI!__imp_IStream_Write` at `0x180019db8`
- `SHLWAPI!__imp_IStream_Write` at `0x180019dd0`
- `SHLWAPI!__imp_IStream_Write` at `0x180019de7`
- `SHLWAPI!__imp_IStream_Write` at `0x180019db8`
- `SHLWAPI!__imp_IStream_Write` at `0x180019dd0`
- `SHLWAPI!__imp_IStream_Write` at `0x180019de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019def`
- `KERNEL32!lstrlenW` at `0x180019d6d`
- `KERNEL32!lstrlenW` at `0x180019d6d`
- `USER32!GetClipboardFormatNameW` at `0x180019d5a`
- `USER32!GetClipboardFormatNameW` at `0x180019d5a`

## pseudocode

```c
HRESULT __fastcall FormatEtcSaveToStream(struct IStream *pstm, const struct tagFORMATETC *a2)
{
  HRESULT result; // eax
  ULONG cb; // [rsp+20h] [rbp-E0h] BYREF
  _WORD pv[2]; // [rsp+28h] [rbp-D8h] BYREF
  int v7; // [rsp+2Ch] [rbp-D4h]
  DWORD dwAspect; // [rsp+30h] [rbp-D0h]
  LONG lindex; // [rsp+34h] [rbp-CCh]
  DWORD tymed; // [rsp+38h] [rbp-C8h]
  WCHAR szFormatName[264]; // [rsp+40h] [rbp-C0h] BYREF

  result = -2147024809;
  if ( pstm && !a2->ptd )
  {
    memset_0(szFormatName, 0, 0x208u);
    if ( GetClipboardFormatNameW(a2->cfFormat, szFormatName, 260) )
    {
      v7 = 0;
      cb = 2 * lstrlenW(szFormatName) + 2;
      pv[1] = 0;
      pv[0] = a2->cfFormat;
      dwAspect = a2->dwAspect;
      lindex = a2->lindex;
      tymed = a2->tymed;
      result = IStream_Write(pstm, pv, 0x14u);
      if ( result >= 0 )
      {
        result = IStream_Write(pstm, &cb, 4u);
        if ( result >= 0 )
          return IStream_Write(pstm, szFormatName, cb);
      }
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      if ( result >= 0 )
        return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019cf0  mov     [rsp-8+arg_10], rbx
0x180019cf5  mov     [rsp-8+arg_18], rdi
0x180019cfa  push    rbp
0x180019cfb  lea     rbp, [rsp-160h]
0x180019d03  sub     rsp, 260h
0x180019d0a  mov     rax, cs:__security_cookie
0x180019d11  xor     rax, rsp
0x180019d14  mov     [rbp+160h+var_10], rax
0x180019d1b  mov     rdi, rdx
0x180019d1e  mov     rbx, rcx
0x180019d21  mov     eax, 80070057h
0x180019d26  test    rcx, rcx
0x180019d29  jz      loc_180019E0B
0x180019d2f  cmp     qword ptr [rdx+8], 0
0x180019d34  jnz     loc_180019E0B
0x180019d3a  xor     edx, edx; Val
0x180019d3c  lea     rcx, [rsp+260h+szFormatName]; void *
0x180019d41  mov     r8d, 208h; Size
0x180019d47  call    memset_0
0x180019d4c  movzx   ecx, word ptr [rdi]; format
0x180019d4f  lea     rdx, [rsp+260h+szFormatName]; lpszFormatName
0x180019d54  mov     r8d, 104h; cchMaxCount
0x180019d5a  call    cs:__imp_GetClipboardFormatNameW
0x180019d60  test    eax, eax
0x180019d62  jz      loc_180019DEF
0x180019d68  lea     rcx, [rsp+260h+szFormatName]; lpString
0x180019d6d  call    cs:__imp_lstrlenW
0x180019d73  mov     r8d, 14h; cb
0x180019d79  mov     [rsp+260h+var_234], 0
0x180019d81  lea     rdx, [rsp+260h+pv]; pv
0x180019d86  mov     rcx, rbx; pstm
0x180019d89  lea     eax, ds:2[rax*2]
0x180019d90  mov     [rsp+260h+cb], eax
0x180019d94  xor     eax, eax
0x180019d96  mov     [rsp+260h+var_236], ax
0x180019d9b  movzx   eax, word ptr [rdi]
0x180019d9e  mov     [rsp+260h+pv], ax
0x180019da3  mov     eax, [rdi+10h]
0x180019da6  mov     [rsp+260h+var_230], eax
0x180019daa  mov     eax, [rdi+14h]
0x180019dad  mov     [rsp+260h+var_22C], eax
0x180019db1  mov     eax, [rdi+18h]
0x180019db4  mov     [rsp+260h+var_228], eax
0x180019db8  call    cs:__imp_IStream_Write
0x180019dbe  test    eax, eax
0x180019dc0  js      short loc_180019E0B
0x180019dc2  mov     r8d, 4; cb
0x180019dc8  lea     rdx, [rsp+260h+cb]; pv
0x180019dcd  mov     rcx, rbx; pstm
0x180019dd0  call    cs:__imp_IStream_Write
0x180019dd6  test    eax, eax
0x180019dd8  js      short loc_180019E0B
0x180019dda  mov     r8d, [rsp+260h+cb]; cb
0x180019ddf  lea     rdx, [rsp+260h+szFormatName]; pv
0x180019de4  mov     rcx, rbx; pstm
0x180019de7  call    cs:__imp_IStream_Write
0x180019ded  jmp     short loc_180019E0B
0x180019def  call    cs:__imp_GetLastError
0x180019df5  test    eax, eax
0x180019df7  jle     short loc_180019E01
0x180019df9  movzx   eax, ax
0x180019dfc  or      eax, 80070000h
0x180019e01  test    eax, eax
0x180019e03  mov     ecx, 80004005h
0x180019e08  cmovns  eax, ecx
0x180019e0b  mov     rcx, [rbp+160h+var_10]
0x180019e12  xor     rcx, rsp; StackCookie
0x180019e15  call    __security_check_cookie
0x180019e1a  lea     r11, [rsp+260h+var_s0]
0x180019e22  mov     rbx, [r11+20h]
0x180019e26  mov     rdi, [r11+28h]
0x180019e2a  mov     rsp, r11
0x180019e2d  pop     rbp
0x180019e2e  retn
```
