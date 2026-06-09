# HTMLWriteFileBegin(x,x,x,x,x)

- ea: `0x100268c0`
- end: `0x10026b05`
- name: `_HTMLWriteFileBegin@20`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1001e1e0`

## callees

- `0x100268c0`
- `0x10028bb0`
- `0x10028f80`
- `0x10029110`
- `0x1002b81a`

## pseudocode

```c
int __stdcall HTMLWriteFileBegin(int a1, int a2, void *a3, int a4, char a5)
{
  int v5; // eax
  unsigned int v6; // eax
  int result; // eax
  int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // eax
  bool v12; // sf
  int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // ecx
  wchar_t pszDest[30]; // [esp+14h] [ebp-40h] BYREF

  if ( (a5 & 1) != 0 )
  {
    v5 = TextWriteHTMLFile(a1, a2, L"<HTML DIR=RTL>", 14, a4, 1);
    if ( v5 )
    {
      v6 = -v5;
      if ( v6 >= 0x10 )
      {
LABEL_8:
        result = -5016;
        goto LABEL_10;
      }
      result = dword_100038B8[v6];
      if ( result )
        goto LABEL_10;
    }
    v8 = TextWriteHTMLFile(a1, a2, asc_1003F048, 2, a4, 0);
    if ( !v8 )
      goto LABEL_11;
    v9 = -v8;
    if ( v9 < 0x10 )
    {
      result = dword_100038B8[v9];
      goto LABEL_10;
    }
    goto LABEL_8;
  }
  result = WriteString(a1, a2, L"<HTML DIR=LTR>", 1, a4);
LABEL_10:
  if ( result < 0 )
    return result;
LABEL_11:
  v10 = TextWriteHTMLFile(a1, a2, L"<HEAD>", 6, a4, 1);
  if ( v10 )
  {
    v11 = -v10;
    if ( v11 >= 0x10 )
      goto LABEL_17;
    result = dword_100038B8[v11];
    v12 = result < 0;
    if ( result )
      goto LABEL_19;
  }
  v13 = TextWriteHTMLFile(a1, a2, asc_1003F048, 2, a4, 0);
  if ( v13 )
  {
    v14 = -v13;
    if ( v14 < 0x10 )
    {
      result = dword_100038B8[v14];
LABEL_18:
      v12 = result < 0;
LABEL_19:
      if ( v12 )
        return result;
      goto LABEL_20;
    }
LABEL_17:
    result = -5016;
    goto LABEL_18;
  }
LABEL_20:
  result = WriteString(a1, a2, L"<META HTTP-EQUIV=\"Content-Type\" CONTENT=\"text/html", 0, a4);
  if ( result >= 0 )
  {
    GetCodePageWWWName(a2, pszDest, 0x1Eu);
    if ( !pszDest[0]
      || (result = WriteString(a1, a2, L"; charset=", 0, a4), result >= 0)
      && (result = WriteString(a1, a2, pszDest, 0, a4), result >= 0) )
    {
      result = WriteString(a1, a2, L"\">", 1, a4);
      if ( result >= 0 )
      {
        result = WriteString(a1, a2, L"<TITLE>", 0, a4);
        if ( result >= 0 )
        {
          result = WriteString(a1, a2, a3, 2, a4);
          if ( result >= 0 )
          {
            result = WriteString(a1, a2, L"</TITLE>", 1, a4);
            if ( result >= 0 )
            {
              result = WriteString(a1, a2, L"</HEAD>", 1, a4);
              if ( result >= 0 )
              {
                result = WriteString(a1, a2, L"<BODY>", 1, a4);
                if ( result >= 0 )
                {
                  result = (a5 & 1) != 0
                         ? WriteString(a1, a2, L"<TABLE DIR=RTL BORDER>", 1, a4)
                         : WriteString(a1, a2, L"<TABLE DIR=LTR BORDER>", 1, a4);
                  if ( result >= 0 )
                  {
                    result = WriteString(a1, a2, L"<CAPTION>", 0, a4);
                    if ( result >= 0 )
                    {
                      result = WriteString(a1, a2, a3, 2, a4);
                      if ( result >= 0 )
                      {
                        v15 = WriteString(a1, a2, L"</CAPTION>", 1, a4);
                        v16 = 0;
                        if ( v15 < 0 )
                          return v15;
                        return v16;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x100268c0  sub     esp, 44h
0x100268c3  mov     eax, ___security_cookie
0x100268c8  xor     eax, esp
0x100268ca  mov     [esp+44h+var_4], eax
0x100268ce  mov     eax, [esp+44h+arg_8]
0x100268d2  push    ebx
0x100268d3  mov     ebx, [esp+48h+arg_0]
0x100268d7  push    ebp
0x100268d8  mov     ebp, [esp+4Ch+arg_10]
0x100268dc  mov     [esp+4Ch+var_44], eax
0x100268e0  push    esi
0x100268e1  mov     esi, [esp+50h+arg_4]
0x100268e5  push    edi
0x100268e6  mov     edi, [esp+54h+arg_C]
0x100268ea  and     ebp, 1
0x100268ed  jz      short loc_10026946
0x100268ef  push    1; int
0x100268f1  push    edi; int
0x100268f2  push    0Eh; int
0x100268f4  push    offset aHtmlDirRtl; "<HTML DIR=RTL>"
0x100268f9  push    esi; int
0x100268fa  push    ebx; int
0x100268fb  call    TextWriteHTMLFile
0x10026900  test    eax, eax
0x10026902  jz      short loc_10026918
0x10026904  neg     eax
0x10026906  js      short loc_1002693F
0x10026908  cmp     eax, 0Fh
0x1002690b  ja      short loc_1002693F
0x1002690d  mov     eax, ds:dword_100038B8[eax*4]
0x10026914  test    eax, eax
0x10026916  jnz     short loc_10026955
0x10026918  push    0; int
0x1002691a  push    edi; int
0x1002691b  push    2; int
0x1002691d  push    offset asc_1003F048; "\r\n"
0x10026922  push    esi; int
0x10026923  push    ebx; int
0x10026924  call    TextWriteHTMLFile
0x10026929  test    eax, eax
0x1002692b  jz      short loc_1002695D
0x1002692d  neg     eax
0x1002692f  js      short loc_1002693F
0x10026931  cmp     eax, 0Fh
0x10026934  ja      short loc_1002693F
0x10026936  mov     eax, ds:dword_100038B8[eax*4]
0x1002693d  jmp     short loc_10026955
0x1002693f  mov     eax, 0FFFFEC68h
0x10026944  jmp     short loc_10026955
0x10026946  push    edi; int
0x10026947  push    1; int
0x10026949  push    offset aHtmlDirLtr; "<HTML DIR=LTR>"
0x1002694e  push    esi; int
0x1002694f  push    ebx; int
0x10026950  call    WriteString
0x10026955  test    eax, eax
0x10026957  js      loc_10026AF0
0x1002695d  push    1; int
0x1002695f  push    edi; int
0x10026960  push    6; int
0x10026962  push    offset aHead; "<HEAD>"
0x10026967  push    esi; int
0x10026968  push    ebx; int
0x10026969  call    TextWriteHTMLFile
0x1002696e  test    eax, eax
0x10026970  jz      short loc_10026986
0x10026972  neg     eax
0x10026974  js      short loc_100269AD
0x10026976  cmp     eax, 0Fh
0x10026979  ja      short loc_100269AD
0x1002697b  mov     eax, ds:dword_100038B8[eax*4]
0x10026982  test    eax, eax
0x10026984  jnz     short loc_100269B4
0x10026986  push    0; int
0x10026988  push    edi; int
0x10026989  push    2; int
0x1002698b  push    offset asc_1003F048; "\r\n"
0x10026990  push    esi; int
0x10026991  push    ebx; int
0x10026992  call    TextWriteHTMLFile
0x10026997  test    eax, eax
0x10026999  jz      short loc_100269BA
0x1002699b  neg     eax
0x1002699d  js      short loc_100269AD
0x1002699f  cmp     eax, 0Fh
0x100269a2  ja      short loc_100269AD
0x100269a4  mov     eax, ds:dword_100038B8[eax*4]
0x100269ab  jmp     short loc_100269B2
0x100269ad  mov     eax, 0FFFFEC68h
0x100269b2  test    eax, eax
0x100269b4  js      loc_10026AF0
0x100269ba  push    edi; int
0x100269bb  push    0; int
0x100269bd  push    offset aMetaHttpEquivC; "<META HTTP-EQUIV=\"Content-Type\" CONTE"...
0x100269c2  push    esi; int
0x100269c3  push    ebx; int
0x100269c4  call    WriteString
0x100269c9  test    eax, eax
0x100269cb  js      loc_10026AF0
0x100269d1  push    1Eh; cchDest
0x100269d3  lea     eax, [esp+58h+pszDest]
0x100269d7  push    eax; pszDest
0x100269d8  push    esi; int
0x100269d9  call    _GetCodePageWWWName@12; GetCodePageWWWName(x,x,x)
0x100269de  cmp     [esp+54h+pszDest], 0
0x100269e4  jz      short loc_10026A14
0x100269e6  push    edi; int
0x100269e7  push    0; int
0x100269e9  push    offset aCharset_0; "; charset="
0x100269ee  push    esi; int
0x100269ef  push    ebx; int
0x100269f0  call    WriteString
0x100269f5  test    eax, eax
0x100269f7  js      loc_10026AF0
0x100269fd  push    edi; int
0x100269fe  push    0; int
0x10026a00  lea     eax, [esp+5Ch+pszDest]
0x10026a04  push    eax; void *
0x10026a05  push    esi; int
0x10026a06  push    ebx; int
0x10026a07  call    WriteString
0x10026a0c  test    eax, eax
0x10026a0e  js      loc_10026AF0
0x10026a14  push    edi; int
0x10026a15  push    1; int
0x10026a17  push    offset asc_10004A50; "\">"
0x10026a1c  push    esi; int
0x10026a1d  push    ebx; int
0x10026a1e  call    WriteString
0x10026a23  test    eax, eax
0x10026a25  js      loc_10026AF0
0x10026a2b  push    edi; int
0x10026a2c  push    0; int
0x10026a2e  push    offset aTitle_1; "<TITLE>"
0x10026a33  push    esi; int
0x10026a34  push    ebx; int
0x10026a35  call    WriteString
0x10026a3a  test    eax, eax
0x10026a3c  js      loc_10026AF0
0x10026a42  push    edi; int
0x10026a43  push    2; int
0x10026a45  push    [esp+5Ch+var_44]; void *
0x10026a49  push    esi; int
0x10026a4a  push    ebx; int
0x10026a4b  call    WriteString
0x10026a50  test    eax, eax
0x10026a52  js      loc_10026AF0
0x10026a58  push    edi; int
0x10026a59  push    1; int
0x10026a5b  push    offset aTitle_0; "</TITLE>"
0x10026a60  push    esi; int
0x10026a61  push    ebx; int
0x10026a62  call    WriteString
0x10026a67  test    eax, eax
0x10026a69  js      loc_10026AF0
0x10026a6f  push    edi; int
0x10026a70  push    1; int
0x10026a72  push    offset aHead_1; "</HEAD>"
0x10026a77  push    esi; int
0x10026a78  push    ebx; int
0x10026a79  call    WriteString
0x10026a7e  test    eax, eax
0x10026a80  js      short loc_10026AF0
0x10026a82  push    edi; int
0x10026a83  push    1; int
0x10026a85  push    offset aBody_1; "<BODY>"
0x10026a8a  push    esi; int
0x10026a8b  push    ebx; int
0x10026a8c  call    WriteString
0x10026a91  test    eax, eax
0x10026a93  js      short loc_10026AF0
0x10026a95  push    edi; int
0x10026a96  push    1; int
0x10026a98  test    ebp, ebp
0x10026a9a  jz      short loc_10026AA3
0x10026a9c  push    offset aTableDirRtlBor; "<TABLE DIR=RTL BORDER>"
0x10026aa1  jmp     short loc_10026AA8
0x10026aa3  push    offset aTableDirLtrBor; "<TABLE DIR=LTR BORDER>"
0x10026aa8  push    esi; int
0x10026aa9  push    ebx; int
0x10026aaa  call    WriteString
0x10026aaf  test    eax, eax
0x10026ab1  js      short loc_10026AF0
0x10026ab3  push    edi; int
0x10026ab4  push    0; int
0x10026ab6  push    offset aCaption; "<CAPTION>"
0x10026abb  push    esi; int
0x10026abc  push    ebx; int
0x10026abd  call    WriteString
0x10026ac2  test    eax, eax
0x10026ac4  js      short loc_10026AF0
0x10026ac6  push    edi; int
0x10026ac7  push    2; int
0x10026ac9  push    [esp+5Ch+var_44]; void *
0x10026acd  push    esi; int
0x10026ace  push    ebx; int
0x10026acf  call    WriteString
0x10026ad4  test    eax, eax
0x10026ad6  js      short loc_10026AF0
0x10026ad8  push    edi; int
0x10026ad9  push    1; int
0x10026adb  push    offset aCaption_1; "</CAPTION>"
0x10026ae0  push    esi; int
0x10026ae1  push    ebx; int
0x10026ae2  call    WriteString
0x10026ae7  xor     ecx, ecx
0x10026ae9  test    eax, eax
0x10026aeb  cmovs   ecx, eax
0x10026aee  mov     eax, ecx
0x10026af0  mov     ecx, [esp+54h+var_4]
0x10026af4  pop     edi
0x10026af5  pop     esi
0x10026af6  pop     ebp
0x10026af7  pop     ebx
0x10026af8  xor     ecx, esp; StackCookie
0x10026afa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10026aff  add     esp, 44h
0x10026b02  retn    14h
```
