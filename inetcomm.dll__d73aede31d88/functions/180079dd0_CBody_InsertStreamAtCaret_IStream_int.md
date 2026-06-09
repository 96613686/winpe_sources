# CBody::InsertStreamAtCaret(IStream *,int)

- ea: `0x180079dd0`
- end: `0x180079f40`
- name: `?InsertStreamAtCaret@CBody@@AEAAJPEAUIStream@@H@Z`
- size: `368`
- prototype: `__int64 __fastcall(CBody *__hidden this, IStream *pstm, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180079a8c`

## callees

- `0x180021140`
- `0x18002d1a0`
- `0x18002d690`
- `0x180079dd0`
- `0x180079f48`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrCopyStream` at `0x180079e5c`
- `MSOERT2!HrCopyStream` at `0x180079e5c`
- `MSOERT2!HrIStreamToBSTR` at `0x180079ee8`
- `MSOERT2!HrIStreamToBSTR` at `0x180079ee8`
- `MSOERT2!GetHtmlCharset` at `0x180079e6e`
- `MSOERT2!GetHtmlCharset` at `0x180079e6e`
- `SHLWAPI!__imp_IStream_Reset` at `0x180079e37`
- `SHLWAPI!__imp_IStream_Reset` at `0x180079e37`
- `KERNEL32!GetACP` at `0x180079ed9`
- `KERNEL32!GetACP` at `0x180079ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x180079f14`
- `OLEAUT32!__imp_SysFreeString` at `0x180079f14`

## pseudocode

```c
__int64 __fastcall CBody::InsertStreamAtCaret(CBody *this, IStream *pstm, int a3)
{
  struct IStream *v6; // rbx
  __int64 v7; // rcx
  UINT ACP; // eax
  int inserted; // ebx
  char *v11; // [rsp+20h] [rbp-89h] BYREF
  __int64 v12; // [rsp+28h] [rbp-81h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-79h] BYREF
  struct IStream *v14; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v15[140]; // [rsp+40h] [rbp-69h] BYREF
  UINT v16; // [rsp+CCh] [rbp+23h]

  bstrString = 0;
  memset_0(v15, 0, 0x98u);
  v11 = 0;
  v12 = 0;
  v14 = 0;
  IStream_Reset(pstm);
  if ( a3 && (int)MimeOleCreateVirtualStream(&v14) >= 0 )
  {
    v6 = v14;
    if ( (int)HrCopyStream(pstm, v14, 0) >= 0 && !GetHtmlCharset(v6, &v11) )
    {
      MimeOleFindCharset(v11, &v12);
      ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v11);
    }
    ((void (__fastcall *)(struct IStream *))v6->lpVtbl->Release)(v6);
  }
  v7 = v12;
  if ( !v12 && (v7 = *((_QWORD *)this + 33), (v12 = v7) == 0) || (MimeOleGetCharsetInfo(v7, v15), (ACP = v16) == 0) )
    ACP = GetACP();
  inserted = HrIStreamToBSTR(ACP, pstm, &bstrString);
  if ( inserted >= 0 )
  {
    inserted = CBody::InsertTextAtCaret(this, bstrString, a3, 1);
    if ( bstrString )
      SysFreeString(bstrString);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180079dd0  mov     [rsp-8+arg_10], rbx
0x180079dd5  mov     [rsp-8+arg_18], rsi
0x180079dda  push    rbp
0x180079ddb  push    rdi
0x180079ddc  push    r14
0x180079dde  lea     rbp, [rsp-47h]
0x180079de3  sub     rsp, 0F0h
0x180079dea  mov     rax, cs:__security_cookie
0x180079df1  xor     rax, rsp
0x180079df4  mov     [rbp+57h+var_20], rax
0x180079df8  mov     r14d, r8d
0x180079dfb  mov     [rbp+57h+bstrString], 0
0x180079e03  mov     rdi, rdx
0x180079e06  mov     rsi, rcx
0x180079e09  xor     edx, edx; Val
0x180079e0b  lea     rcx, [rbp+57h+var_C0]; void *
0x180079e0f  mov     r8d, 98h; Size
0x180079e15  call    memset_0
0x180079e1a  mov     rcx, rdi; pstm
0x180079e1d  mov     [rsp+100h+var_E0], 0
0x180079e26  mov     [rsp+100h+var_D8], 0
0x180079e2f  mov     [rbp+57h+var_C8], 0
0x180079e37  call    cs:__imp_IStream_Reset
0x180079e3d  test    r14d, r14d
0x180079e40  jz      short loc_180079EAE
0x180079e42  lea     rcx, [rbp+57h+var_C8]
0x180079e46  call    MimeOleCreateVirtualStream
0x180079e4b  test    eax, eax
0x180079e4d  js      short loc_180079EAE
0x180079e4f  mov     rbx, [rbp+57h+var_C8]
0x180079e53  xor     r8d, r8d
0x180079e56  mov     rdx, rbx
0x180079e59  mov     rcx, rdi
0x180079e5c  call    cs:__imp_HrCopyStream
0x180079e62  test    eax, eax
0x180079e64  js      short loc_180079E9F
0x180079e66  lea     rdx, [rsp+100h+var_E0]
0x180079e6b  mov     rcx, rbx
0x180079e6e  call    cs:__imp_?GetHtmlCharset@@YAJPEAUIStream@@PEAPEAD@Z; GetHtmlCharset(IStream *,char * *)
0x180079e74  test    eax, eax
0x180079e76  jnz     short loc_180079E9F
0x180079e78  mov     rcx, [rsp+100h+var_E0]
0x180079e7d  lea     rdx, [rsp+100h+var_D8]
0x180079e82  call    MimeOleFindCharset
0x180079e87  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180079e8e  mov     rdx, [rsp+100h+var_E0]
0x180079e93  mov     rax, [rcx]
0x180079e96  mov     rax, [rax+28h]
0x180079e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e9f  mov     rax, [rbx]
0x180079ea2  mov     rcx, rbx
0x180079ea5  mov     rax, [rax+10h]
0x180079ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079eae  mov     rcx, [rsp+100h+var_D8]
0x180079eb3  test    rcx, rcx
0x180079eb6  jnz     short loc_180079EC9
0x180079eb8  mov     rcx, [rsi+108h]
0x180079ebf  mov     [rsp+100h+var_D8], rcx
0x180079ec4  test    rcx, rcx
0x180079ec7  jz      short loc_180079ED9
0x180079ec9  lea     rdx, [rbp+57h+var_C0]
0x180079ecd  call    MimeOleGetCharsetInfo
0x180079ed2  mov     eax, [rbp+57h+var_34]
0x180079ed5  test    eax, eax
0x180079ed7  jnz     short loc_180079EDF
0x180079ed9  call    cs:__imp_GetACP
0x180079edf  lea     r8, [rbp+57h+bstrString]
0x180079ee3  mov     rdx, rdi
0x180079ee6  mov     ecx, eax
0x180079ee8  call    cs:__imp_HrIStreamToBSTR
0x180079eee  mov     ebx, eax
0x180079ef0  test    eax, eax
0x180079ef2  js      short loc_180079F1A
0x180079ef4  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180079ef8  mov     r9d, 1; int
0x180079efe  mov     r8d, r14d; int
0x180079f01  mov     rcx, rsi; this
0x180079f04  call    ?InsertTextAtCaret@CBody@@AEAAJPEAGHH@Z; CBody::InsertTextAtCaret(ushort *,int,int)
0x180079f09  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180079f0d  mov     ebx, eax
0x180079f0f  test    rcx, rcx
0x180079f12  jz      short loc_180079F1A
0x180079f14  call    cs:__imp_SysFreeString
0x180079f1a  mov     eax, ebx
0x180079f1c  mov     rcx, [rbp+57h+var_20]
0x180079f20  xor     rcx, rsp; StackCookie
0x180079f23  call    __security_check_cookie
0x180079f28  lea     r11, [rsp+100h+var_10]
0x180079f30  mov     rbx, [r11+30h]
0x180079f34  mov     rsi, [r11+38h]
0x180079f38  mov     rsp, r11
0x180079f3b  pop     r14
0x180079f3d  pop     rdi
0x180079f3e  pop     rbp
0x180079f3f  retn
```
