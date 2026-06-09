# URLMONStream::deferedOpen(IMoniker *,IBindCtx *)

- ea: `0x18003eaf0`
- end: `0x18003ed1e`
- name: `?deferedOpen@URLMONStream@@UEAAJPEAUIMoniker@@PEAUIBindCtx@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(URLMONStream *__hidden this, struct IMoniker *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180012000`
- `0x18001ecd0`
- `0x18003eaf0`
- `0x18003ed24`
- `0x18004e1e0`
- `0x1800f3f20`
- `0x180107010`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18003eb8a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18003eb8a`
- `urlmon!CreateURLMonikerEx` at `0x18003ec89`
- `urlmon!CreateURLMonikerEx` at `0x18003ec89`
- `urlmon!RevokeBindStatusCallback` at `0x18003ebbc`
- `urlmon!RevokeBindStatusCallback` at `0x18003ebbc`
- `urlmon!RegisterBindStatusCallback` at `0x18003ec66`
- `urlmon!RegisterBindStatusCallback` at `0x18003ec66`

## pseudocode

```c
__int64 __fastcall URLMONStream::deferedOpen(URLMONStream *this, struct IMoniker *a2, struct IBindCtx *a3)
{
  const WCHAR *v4; // rcx
  __int64 result; // rax
  HRESULT v8; // ebx
  IBindCtx *v9; // rcx
  int v10; // ecx
  LPMONIKER v11; // rcx
  void *v12; // rcx
  void *v13; // [rsp+30h] [rbp-10h] BYREF
  LPBC ppbc; // [rsp+60h] [rbp+20h] BYREF
  LPMONIKER ppmk; // [rsp+78h] [rbp+38h] BYREF

  ppmk = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 2);
  v13 = 0;
  result = URL::IsSafeScheme(v4);
  if ( (int)result < 0 )
    return result;
  result = URL::accessAllowed(
             *((_BYTE *)this + 56),
             *((const unsigned __int16 **)this + 2),
             0,
             *((const unsigned __int16 **)this + 5),
             *((_BYTE *)this + 216),
             0);
  if ( (int)result < 0 )
    return result;
  if ( *((_BYTE *)this + 216) && URLStream::OpenPreloadResource(this, *((const unsigned __int16 **)this + 2)) >= 0 )
    return 0;
  ppbc = 0;
  if ( a3 )
  {
    assign((struct IUnknown **)&ppbc, a3);
  }
  else
  {
    v8 = CreateBindCtx(0, &ppbc);
    if ( v8 < 0 )
      goto LABEL_8;
  }
  assign((struct IUnknown **)this + 24, 0);
  assign((struct IUnknown **)this + 23, ppbc);
  v8 = RegisterBindStatusCallback(
         ppbc,
         (IBindStatusCallback *)(((unsigned __int64)this + 160)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
         (IBindStatusCallback **)this + 24,
         0);
  if ( v8 >= 0 )
  {
    if ( a2 )
    {
      ppmk = a2;
      ((void (__fastcall *)(struct IMoniker *))a2->lpVtbl->AddRef)(a2);
    }
    else
    {
      v8 = CreateURLMonikerEx(0, *((LPCWSTR *)this + 2), &ppmk, 1u);
      if ( v8 < 0 )
        goto LABEL_8;
    }
    v11 = ppmk;
    *((_DWORD *)this + 38) = -2147483638;
    v8 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, void **))v11->lpVtbl->BindToStorage)(
           v11,
           ppbc,
           0,
           &IID_IStream,
           &v13);
    if ( v8 >= 0 )
    {
      v12 = v13;
      v8 = 0;
      if ( v13 )
      {
        if ( !*((_QWORD *)this + 8) )
        {
          assign((struct IUnknown **)this + 8, v13);
          v12 = v13;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      }
      goto LABEL_10;
    }
  }
LABEL_8:
  v9 = (IBindCtx *)*((_QWORD *)this + 23);
  if ( v9 )
  {
    RevokeBindStatusCallback(
      v9,
      (IBindStatusCallback *)(((unsigned __int64)this + 160)
                            & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
    assign((struct IUnknown **)this + 23, 0);
  }
LABEL_10:
  v10 = *((_DWORD *)this + 38);
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147483638 )
    v8 = *((_DWORD *)this + 38);
  if ( ppmk )
  {
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    ppmk = 0;
  }
  release((struct IUnknown **)&ppbc);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003eaf0  mov     [rsp-18h+arg_8], rbx
0x18003eaf5  push    rbp
0x18003eaf6  push    rsi
0x18003eaf7  push    rdi
0x18003eaf8  mov     rbp, rsp
0x18003eafb  sub     rsp, 40h
0x18003eaff  mov     rdi, rcx
0x18003eb02  mov     [rbp+ppmk], 0
0x18003eb0a  mov     rcx, [rcx+10h]; lpszUrl
0x18003eb0e  mov     rbx, r8
0x18003eb11  mov     rsi, rdx
0x18003eb14  mov     [rbp+var_10], 0
0x18003eb1c  call    ?IsSafeScheme@URL@@SAJPEBG@Z; URL::IsSafeScheme(ushort const *)
0x18003eb21  test    eax, eax
0x18003eb23  js      loc_18003EC0F
0x18003eb29  mov     al, [rdi+0D8h]
0x18003eb2f  xor     r8d, r8d; unsigned __int16 *
0x18003eb32  mov     r9, [rdi+28h]; unsigned __int16 *
0x18003eb36  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18003eb3a  mov     cl, [rdi+38h]; bool
0x18003eb3d  mov     [rsp+40h+var_18], 0; bool
0x18003eb42  mov     [rsp+40h+var_20], al; bool
0x18003eb46  call    ?accessAllowed@URL@@SAJ_NPEBG1100@Z; URL::accessAllowed(bool,ushort const *,ushort const *,ushort const *,bool,bool)
0x18003eb4b  test    eax, eax
0x18003eb4d  js      loc_18003EC0F
0x18003eb53  cmp     byte ptr [rdi+0D8h], 0
0x18003eb5a  jz      short loc_18003EB73
0x18003eb5c  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18003eb60  mov     rcx, rdi; this
0x18003eb63  call    ?OpenPreloadResource@URLStream@@IEAAJPEBG@Z; URLStream::OpenPreloadResource(ushort const *)
0x18003eb68  test    eax, eax
0x18003eb6a  js      short loc_18003EB73
0x18003eb6c  xor     eax, eax
0x18003eb6e  jmp     loc_18003EC0F
0x18003eb73  mov     [rbp+ppbc], 0
0x18003eb7b  test    rbx, rbx
0x18003eb7e  jnz     loc_18003EC1C
0x18003eb84  lea     rdx, [rbp+ppbc]; ppbc
0x18003eb88  xor     ecx, ecx; reserved
0x18003eb8a  call    cs:__imp_CreateBindCtx
0x18003eb90  mov     ebx, eax
0x18003eb92  test    eax, eax
0x18003eb94  jns     loc_18003EC28
0x18003eb9a  lea     rsi, [rdi+0B8h]
0x18003eba1  mov     rcx, [rsi]; pBC
0x18003eba4  test    rcx, rcx
0x18003eba7  jz      short loc_18003EBCC
0x18003eba9  lea     r8, [rdi+0A0h]
0x18003ebb0  mov     rax, rdi
0x18003ebb3  neg     rax
0x18003ebb6  sbb     rdx, rdx
0x18003ebb9  and     rdx, r8; pBSCb
0x18003ebbc  call    cs:__imp_RevokeBindStatusCallback
0x18003ebc2  xor     edx, edx; void *
0x18003ebc4  mov     rcx, rsi; struct IUnknown **
0x18003ebc7  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18003ebcc  mov     ecx, [rdi+98h]
0x18003ebd2  mov     edx, 80000000h
0x18003ebd7  lea     eax, [rcx+rdx]
0x18003ebda  test    edx, eax
0x18003ebdc  jnz     short loc_18003EBE7
0x18003ebde  cmp     ecx, 8000000Ah
0x18003ebe4  cmovnz  ebx, ecx
0x18003ebe7  mov     rcx, [rbp+ppmk]
0x18003ebeb  test    rcx, rcx
0x18003ebee  jz      short loc_18003EC04
0x18003ebf0  mov     rax, [rcx]
0x18003ebf3  mov     rax, [rax+10h]
0x18003ebf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebfc  mov     [rbp+ppmk], 0
0x18003ec04  lea     rcx, [rbp+ppbc]; struct IUnknown **
0x18003ec08  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18003ec0d  mov     eax, ebx
0x18003ec0f  mov     rbx, [rsp+40h+arg_8]
0x18003ec14  add     rsp, 40h
0x18003ec18  pop     rdi
0x18003ec19  pop     rsi
0x18003ec1a  pop     rbp
0x18003ec1b  retn
0x18003ec1c  mov     rdx, rbx; void *
0x18003ec1f  lea     rcx, [rbp+ppbc]; struct IUnknown **
0x18003ec23  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18003ec28  lea     rbx, [rdi+0C0h]
0x18003ec2f  xor     edx, edx; void *
0x18003ec31  mov     rcx, rbx; struct IUnknown **
0x18003ec34  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18003ec39  mov     rdx, [rbp+ppbc]; void *
0x18003ec3d  lea     rcx, [rdi+0B8h]; struct IUnknown **
0x18003ec44  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18003ec49  mov     rcx, [rbp+ppbc]; pBC
0x18003ec4d  lea     r9, [rdi+0A0h]
0x18003ec54  mov     rax, rdi
0x18003ec57  mov     r8, rbx; ppBSCBPrev
0x18003ec5a  neg     rax
0x18003ec5d  sbb     rdx, rdx
0x18003ec60  and     rdx, r9; pBSCb
0x18003ec63  xor     r9d, r9d; dwReserved
0x18003ec66  call    cs:__imp_RegisterBindStatusCallback
0x18003ec6c  mov     ebx, eax
0x18003ec6e  test    eax, eax
0x18003ec70  js      loc_18003EB9A
0x18003ec76  test    rsi, rsi
0x18003ec79  jnz     short loc_18003EC9A
0x18003ec7b  mov     rdx, [rdi+10h]; szURL
0x18003ec7f  lea     r9d, [rsi+1]; dwFlags
0x18003ec83  lea     r8, [rbp+ppmk]; ppmk
0x18003ec87  xor     ecx, ecx; pMkCtx
0x18003ec89  call    cs:__imp_CreateURLMonikerEx
0x18003ec8f  mov     ebx, eax
0x18003ec91  test    eax, eax
0x18003ec93  jns     short loc_18003ECAD
0x18003ec95  jmp     loc_18003EB9A
0x18003ec9a  mov     [rbp+ppmk], rsi
0x18003ec9e  mov     rcx, rsi
0x18003eca1  mov     rax, [rsi]
0x18003eca4  mov     rax, [rax+8]
0x18003eca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecad  mov     rcx, [rbp+ppmk]
0x18003ecb1  lea     rdx, [rbp+var_10]
0x18003ecb5  mov     dword ptr [rdi+98h], 8000000Ah
0x18003ecbf  lea     r9, IID_IStream
0x18003ecc6  mov     qword ptr [rsp+40h+var_20], rdx
0x18003eccb  xor     r8d, r8d
0x18003ecce  mov     rdx, [rbp+ppbc]
0x18003ecd2  mov     rax, [rcx]
0x18003ecd5  mov     rax, [rax+48h]
0x18003ecd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecde  mov     ebx, eax
0x18003ece0  test    eax, eax
0x18003ece2  js      loc_18003EB9A
0x18003ece8  mov     rcx, [rbp+var_10]
0x18003ecec  xor     ebx, ebx
0x18003ecee  test    rcx, rcx
0x18003ecf1  jz      loc_18003EBCC
0x18003ecf7  cmp     [rdi+40h], rbx
0x18003ecfb  jnz     short loc_18003ED0D
0x18003ecfd  mov     rdx, rcx; void *
0x18003ed00  lea     rcx, [rdi+40h]; struct IUnknown **
0x18003ed04  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18003ed09  mov     rcx, [rbp+var_10]
0x18003ed0d  mov     rax, [rcx]
0x18003ed10  mov     rax, [rax+10h]
0x18003ed14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed19  jmp     loc_18003EBCC
```
