# CBody::AppendAnchorItems(HMENU__ *,IDispatch *)

- ea: `0x180076f64`
- end: `0x180077181`
- name: `?AppendAnchorItems@CBody@@AEAAJPEAUHMENU__@@PEAUIDispatch@@@Z`
- size: `541`
- prototype: `int(CBody *__hidden this, HMENU, struct IDispatch *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007e940`

## callees

- `0x180076f64`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!StrCmpNIW` at `0x18007706d`
- `SHLWAPI!StrCmpNIW` at `0x1800770e5`
- `SHLWAPI!StrCmpNIW` at `0x1800770fe`
- `SHLWAPI!StrCmpNIW` at `0x18007706d`
- `SHLWAPI!StrCmpNIW` at `0x1800770e5`
- `SHLWAPI!StrCmpNIW` at `0x1800770fe`
- `USER32!LoadStringA` at `0x18007708e`
- `USER32!LoadStringA` at `0x18007711f`
- `USER32!LoadStringA` at `0x18007708e`
- `USER32!LoadStringA` at `0x18007711f`
- `USER32!RemoveMenu` at `0x1800770c7`
- `USER32!RemoveMenu` at `0x1800770c7`
- `USER32!AppendMenuA` at `0x1800770a2`
- `USER32!AppendMenuA` at `0x1800770b6`
- `USER32!AppendMenuA` at `0x180077133`
- `USER32!AppendMenuA` at `0x180077147`
- `USER32!AppendMenuA` at `0x1800770a2`
- `USER32!AppendMenuA` at `0x1800770b6`
- `USER32!AppendMenuA` at `0x180077133`
- `USER32!AppendMenuA` at `0x180077147`
- `OLEAUT32!__imp_SysFreeString` at `0x180077157`
- `OLEAUT32!__imp_SysFreeString` at `0x180077157`

## pseudocode

```c
__int64 __fastcall CBody::AppendAnchorItems(CBody *this, HMENU a2, struct IDispatch *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // edi
  WCHAR *v8; // rcx
  PCWSTR psz1; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h]
  CHAR Buffer[512]; // [rsp+50h] [rbp-B0h] BYREF

  psz1 = 0;
  v10 = 0;
  v11 = 10;
  v12 = 11;
  if ( !a3 )
    return 0;
  v6 = *((_QWORD *)this + 43);
  v7 = 0;
  if ( v6
    && !(*(unsigned int (__fastcall **)(__int64, __int64 *, __int64, __int64 *, _QWORD))(*(_QWORD *)v6 + 24LL))(
          v6,
          &CMDSETID_MimeEditHost,
          2,
          &v11,
          0) )
  {
    if ( !((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
            a3,
            &IID_IHTMLAnchorElement,
            &v10) )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v10 + 64LL))(v10, &psz1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v8 = (WCHAR *)psz1;
    if ( psz1 )
    {
      Buffer[0] = 0;
      if ( (v11 & 0x200000000LL) != 0 )
      {
        if ( !StrCmpNIW(psz1, aMailto_0, 6) )
        {
          LoadStringA(g_hLocRes, 0x492u, Buffer, 512);
          AppendMenuA(a2, 0x800u, 0, 0);
          AppendMenuA(a2, 0, 0x7Du, Buffer);
          RemoveMenu(a2, 0xE0u, 0);
          goto LABEL_16;
        }
        v8 = (WCHAR *)psz1;
      }
      if ( (v12 & 0x200000000LL) == 0 )
        goto LABEL_17;
      if ( !StrCmpNIW(v8, aHttp_2, 6) || !StrCmpNIW(psz1, aFile_1, 6) )
      {
        LoadStringA(g_hLocRes, 0x491u, Buffer, 512);
        AppendMenuA(a2, 0x800u, 0, 0);
        AppendMenuA(a2, 0, 0x7Cu, Buffer);
      }
LABEL_16:
      v8 = (WCHAR *)psz1;
LABEL_17:
      if ( v8 )
        SysFreeString(v8);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180076f64  mov     [rsp-8+arg_18], rbx
0x180076f69  push    rbp
0x180076f6a  push    rsi
0x180076f6b  push    rdi
0x180076f6c  lea     rbp, [rsp-160h]
0x180076f74  sub     rsp, 260h
0x180076f7b  mov     rax, cs:__security_cookie
0x180076f82  xor     rax, rsp
0x180076f85  mov     [rbp+170h+var_20], rax
0x180076f8c  mov     [rsp+270h+psz1], 0
0x180076f95  mov     rbx, r8
0x180076f98  mov     [rsp+270h+var_238], 0
0x180076fa1  mov     rsi, rdx
0x180076fa4  mov     [rsp+270h+var_230], 0Ah
0x180076fad  mov     [rsp+270h+var_228], 0Bh
0x180076fb6  test    r8, r8
0x180076fb9  jnz     short loc_180076FC2
0x180076fbb  xor     eax, eax
0x180076fbd  jmp     loc_18007715F
0x180076fc2  mov     rcx, [rcx+158h]
0x180076fc9  xor     edi, edi
0x180076fcb  test    rcx, rcx
0x180076fce  jz      loc_18007715D
0x180076fd4  mov     rax, [rcx]
0x180076fd7  lea     r9, [rsp+270h+var_230]
0x180076fdc  lea     r8d, [rdi+2]
0x180076fe0  mov     [rsp+270h+var_250], rdi
0x180076fe5  lea     rdx, CMDSETID_MimeEditHost
0x180076fec  mov     rax, [rax+18h]
0x180076ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ff5  test    eax, eax
0x180076ff7  jnz     loc_18007715D
0x180076ffd  mov     rax, [rbx]
0x180077000  lea     r8, [rsp+270h+var_238]
0x180077005  lea     rdx, IID_IHTMLAnchorElement
0x18007700c  mov     rcx, rbx
0x18007700f  mov     rax, [rax]
0x180077012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077017  test    eax, eax
0x180077019  jnz     short loc_180077044
0x18007701b  mov     rcx, [rsp+270h+var_238]
0x180077020  lea     rdx, [rsp+270h+psz1]
0x180077025  mov     rax, [rcx]
0x180077028  mov     rax, [rax+40h]
0x18007702c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077031  mov     rcx, [rsp+270h+var_238]
0x180077036  mov     edi, eax
0x180077038  mov     rdx, [rcx]
0x18007703b  mov     rax, [rdx+10h]
0x18007703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077044  mov     rcx, [rsp+270h+psz1]; psz1
0x180077049  test    rcx, rcx
0x18007704c  jz      loc_18007715D
0x180077052  test    byte ptr [rsp+270h+var_230+4], 2
0x180077057  mov     ebx, 6
0x18007705c  mov     [rsp+270h+Buffer], 0
0x180077061  jz      short loc_1800770D4
0x180077063  mov     r8d, ebx; nChar
0x180077066  lea     rdx, aMailto_0; "mailto:"
0x18007706d  call    cs:__imp_StrCmpNIW
0x180077073  test    eax, eax
0x180077075  jnz     short loc_1800770CF
0x180077077  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007707e  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x180077083  mov     r9d, 200h; cchBufferMax
0x180077089  mov     edx, 492h; uID
0x18007708e  call    cs:__imp_LoadStringA
0x180077094  xor     r9d, r9d; lpNewItem
0x180077097  xor     r8d, r8d; uIDNewItem
0x18007709a  mov     edx, 800h; uFlags
0x18007709f  mov     rcx, rsi; hMenu
0x1800770a2  call    cs:__imp_AppendMenuA
0x1800770a8  lea     r9, [rsp+270h+Buffer]; lpNewItem
0x1800770ad  xor     edx, edx; uFlags
0x1800770af  lea     r8d, [rbx+77h]; uIDNewItem
0x1800770b3  mov     rcx, rsi; hMenu
0x1800770b6  call    cs:__imp_AppendMenuA
0x1800770bc  xor     r8d, r8d; uFlags
0x1800770bf  mov     edx, 0E0h; uPosition
0x1800770c4  mov     rcx, rsi; hMenu
0x1800770c7  call    cs:__imp_RemoveMenu
0x1800770cd  jmp     short loc_18007714D
0x1800770cf  mov     rcx, [rsp+270h+psz1]; psz1
0x1800770d4  test    byte ptr [rsp+270h+var_228+4], 2
0x1800770d9  jz      short loc_180077152
0x1800770db  mov     r8d, ebx; nChar
0x1800770de  lea     rdx, aHttp_2; "http://"
0x1800770e5  call    cs:__imp_StrCmpNIW
0x1800770eb  test    eax, eax
0x1800770ed  jz      short loc_180077108
0x1800770ef  mov     rcx, [rsp+270h+psz1]; psz1
0x1800770f4  lea     rdx, aFile_1; "file://"
0x1800770fb  mov     r8d, ebx; nChar
0x1800770fe  call    cs:__imp_StrCmpNIW
0x180077104  test    eax, eax
0x180077106  jnz     short loc_18007714D
0x180077108  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007710f  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x180077114  mov     r9d, 200h; cchBufferMax
0x18007711a  mov     edx, 491h; uID
0x18007711f  call    cs:__imp_LoadStringA
0x180077125  xor     r9d, r9d; lpNewItem
0x180077128  xor     r8d, r8d; uIDNewItem
0x18007712b  mov     edx, 800h; uFlags
0x180077130  mov     rcx, rsi; hMenu
0x180077133  call    cs:__imp_AppendMenuA
0x180077139  xor     edx, edx; uFlags
0x18007713b  lea     r9, [rsp+270h+Buffer]; lpNewItem
0x180077140  mov     rcx, rsi; hMenu
0x180077143  lea     r8d, [rdx+7Ch]; uIDNewItem
0x180077147  call    cs:__imp_AppendMenuA
0x18007714d  mov     rcx, [rsp+270h+psz1]; bstrString
0x180077152  test    rcx, rcx
0x180077155  jz      short loc_18007715D
0x180077157  call    cs:__imp_SysFreeString
0x18007715d  mov     eax, edi
0x18007715f  mov     rcx, [rbp+170h+var_20]
0x180077166  xor     rcx, rsp; StackCookie
0x180077169  call    __security_check_cookie
0x18007716e  mov     rbx, [rsp+270h+arg_18]
0x180077176  add     rsp, 260h
0x18007717d  pop     rdi
0x18007717e  pop     rsi
0x18007717f  pop     rbp
0x180077180  retn
```
