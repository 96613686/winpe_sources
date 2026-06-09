# XMLScrSite::GetInfo(ulong,IServiceProvider *,tagVARIANT *,tagVARIANT *)

- ea: `0x140008a80`
- end: `0x140008c13`
- name: `?GetInfo@XMLScrSite@@UEAAJKPEAUIServiceProvider@@PEAUtagVARIANT@@1@Z`
- size: `403`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned int, struct IServiceProvider *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x140008a80`
- `0x140017010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x140008bed`
- `USER32!GetActiveWindow` at `0x140008bed`

## pseudocode

```c
__int64 __fastcall XMLScrSite::GetInfo(
        XMLScrSite *this,
        int a2,
        struct IServiceProvider *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5)
{
  int v6; // edx
  BSTR bstrVal; // r11
  const unsigned __int16 *v9; // rbx
  unsigned __int64 v10; // r9
  BSTR v11; // r10
  unsigned __int64 v12; // rcx
  OLECHAR v13; // dx
  OLECHAR v14; // cx
  __int16 lpVtbl; // dx
  LONGLONG v16; // rcx

  v6 = a2 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      return 2147500033LL;
    if ( !a4 || a4->vt != 8 )
      return 2147500037LL;
    bstrVal = a4->bstrVal;
    v9 = L"WScript";
    v10 = -1;
    v11 = bstrVal;
    if ( !bstrVal )
      goto LABEL_10;
    v12 = -1;
    do
      ++v12;
    while ( bstrVal[v12] );
    if ( v12 <= 7 )
LABEL_10:
      v12 = 7;
    while ( v12 )
    {
      v13 = *v11;
      a3 = (struct IServiceProvider *)*v9;
      if ( *v11 == (_WORD)a3 )
      {
        if ( !v13 )
          break;
      }
      else
      {
        if ( !(_WORD)a3 || !v13 )
          goto LABEL_20;
        if ( (unsigned __int16)(v13 - 65) <= 0x19u )
          v13 += 32;
        if ( (unsigned __int16)((_WORD)a3 - 65) <= 0x19u )
          LOWORD(a3) = (_WORD)a3 + 32;
        if ( v13 != (_WORD)a3 )
        {
LABEL_20:
          a3 = (struct IServiceProvider *)L"WSH";
          if ( !bstrVal )
            goto LABEL_23;
          do
            ++v10;
          while ( bstrVal[v10] );
          if ( v10 <= 3 )
LABEL_23:
            v10 = 3;
          while ( v10 )
          {
            v14 = *bstrVal;
            lpVtbl = (__int16)a3->lpVtbl;
            if ( *bstrVal == LOWORD(a3->lpVtbl) )
            {
              if ( !v14 )
                goto LABEL_38;
            }
            else
            {
              if ( !lpVtbl || !v14 )
                return 2147500037LL;
              if ( (unsigned __int16)(v14 - 65) <= 0x19u )
                v14 += 32;
              if ( (unsigned __int16)(lpVtbl - 65) <= 0x19u )
                lpVtbl += 32;
              if ( v14 != lpVtbl )
                return 2147500037LL;
            }
            --v10;
            ++bstrVal;
            a3 = (struct IServiceProvider *)((char *)a3 + 2);
          }
          break;
        }
      }
      --v12;
      ++v11;
      ++v9;
    }
LABEL_38:
    a5->vt = 9;
    v16 = *(_QWORD *)(*((_QWORD *)this + 4) + 624LL);
    a5->llVal = v16;
    (*(void (__fastcall **)(LONGLONG, struct tagVARIANT *, struct IServiceProvider *, unsigned __int64))(*(_QWORD *)v16 + 8LL))(
      v16,
      a5,
      a3,
      v10);
  }
  else
  {
    a5->llVal = (LONGLONG)GetActiveWindow();
    a5->vt = 0x4000;
  }
  return 0;
}

```

## disassembly

```asm
0x140008a80  mov     [rsp+arg_0], rbx
0x140008a85  mov     [rsp+arg_8], rsi
0x140008a8a  push    rdi
0x140008a8b  sub     rsp, 20h
0x140008a8f  mov     rdi, rcx
0x140008a92  sub     edx, 1
0x140008a95  jz      loc_140008BED
0x140008a9b  cmp     edx, 1
0x140008a9e  jz      short loc_140008AAA
0x140008aa0  mov     eax, 80004001h
0x140008aa5  jmp     loc_140008C03
0x140008aaa  xor     esi, esi
0x140008aac  test    r9, r9
0x140008aaf  jz      loc_140008B98
0x140008ab5  lea     eax, [rsi+8]
0x140008ab8  cmp     ax, [r9]
0x140008abc  jnz     loc_140008B98
0x140008ac2  mov     r11, [r9+8]
0x140008ac6  lea     rbx, ?GWSZ_WSCRIPT@@3QBGB; "WScript"
0x140008acd  or      r9, 0FFFFFFFFFFFFFFFFh
0x140008ad1  mov     r10, r11
0x140008ad4  test    r11, r11
0x140008ad7  jz      short loc_140008AEC
0x140008ad9  mov     rcx, r9
0x140008adc  inc     rcx
0x140008adf  cmp     [r11+rcx*2], si
0x140008ae4  jnz     short loc_140008ADC
0x140008ae6  cmp     rcx, 7
0x140008aea  ja      short loc_140008AF1
0x140008aec  mov     ecx, 7
0x140008af1  cmp     rcx, 1
0x140008af5  jb      loc_140008BC6
0x140008afb  movzx   edx, word ptr [r10]
0x140008aff  movzx   r8d, word ptr [rbx]
0x140008b03  cmp     dx, r8w
0x140008b07  jz      loc_140008B9F
0x140008b0d  cmp     si, r8w
0x140008b11  jz      short loc_140008B3A
0x140008b13  cmp     si, dx
0x140008b16  jz      short loc_140008B3A
0x140008b18  lea     eax, [rdx-41h]
0x140008b1b  cmp     ax, 19h
0x140008b1f  ja      short loc_140008B25
0x140008b21  add     dx, 20h ; ' '
0x140008b25  lea     eax, [r8-41h]
0x140008b29  cmp     ax, 19h
0x140008b2d  ja      short loc_140008B34
0x140008b2f  add     r8w, 20h ; ' '
0x140008b34  cmp     dx, r8w
0x140008b38  jz      short loc_140008BA4
0x140008b3a  lea     r8, ?GWSZ_WSH@@3QBGB; "WSH"
0x140008b41  test    r11, r11
0x140008b44  jz      short loc_140008B56
0x140008b46  inc     r9
0x140008b49  cmp     [r11+r9*2], si
0x140008b4e  jnz     short loc_140008B46
0x140008b50  cmp     r9, 3
0x140008b54  ja      short loc_140008B5C
0x140008b56  mov     r9d, 3
0x140008b5c  cmp     r9, 1
0x140008b60  jb      short loc_140008BC6
0x140008b62  movzx   ecx, word ptr [r11]
0x140008b66  movzx   edx, word ptr [r8]
0x140008b6a  cmp     cx, dx
0x140008b6d  jz      short loc_140008BB4
0x140008b6f  cmp     si, dx
0x140008b72  jz      short loc_140008B98
0x140008b74  cmp     si, cx
0x140008b77  jz      short loc_140008B98
0x140008b79  lea     eax, [rcx-41h]
0x140008b7c  cmp     ax, 19h
0x140008b80  ja      short loc_140008B86
0x140008b82  add     cx, 20h ; ' '
0x140008b86  lea     eax, [rdx-41h]
0x140008b89  cmp     ax, 19h
0x140008b8d  ja      short loc_140008B93
0x140008b8f  add     dx, 20h ; ' '
0x140008b93  cmp     cx, dx
0x140008b96  jz      short loc_140008BB9
0x140008b98  mov     eax, 80004005h
0x140008b9d  jmp     short loc_140008C03
0x140008b9f  cmp     si, dx
0x140008ba2  jz      short loc_140008BC6
0x140008ba4  dec     rcx
0x140008ba7  add     r10, 2
0x140008bab  add     rbx, 2
0x140008baf  jmp     loc_140008AF1
0x140008bb4  cmp     si, cx
0x140008bb7  jz      short loc_140008BC6
0x140008bb9  dec     r9
0x140008bbc  add     r11, 2
0x140008bc0  add     r8, 2
0x140008bc4  jmp     short loc_140008B5C
0x140008bc6  mov     rdx, [rsp+28h+arg_20]
0x140008bcb  mov     word ptr [rdx], 9
0x140008bd0  mov     rax, [rdi+20h]
0x140008bd4  mov     rcx, [rax+270h]
0x140008bdb  mov     [rdx+8], rcx
0x140008bdf  mov     rax, [rcx]
0x140008be2  mov     rax, [rax+8]
0x140008be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008beb  jmp     short loc_140008C01
0x140008bed  call    cs:__imp_GetActiveWindow
0x140008bf3  mov     rcx, [rsp+28h+arg_20]
0x140008bf8  mov     [rcx+8], rax
0x140008bfc  mov     word ptr [rcx], 4000h
0x140008c01  xor     eax, eax
0x140008c03  mov     rbx, [rsp+28h+arg_0]
0x140008c08  mov     rsi, [rsp+28h+arg_8]
0x140008c0d  add     rsp, 20h
0x140008c11  pop     rdi
0x140008c12  retn
```
