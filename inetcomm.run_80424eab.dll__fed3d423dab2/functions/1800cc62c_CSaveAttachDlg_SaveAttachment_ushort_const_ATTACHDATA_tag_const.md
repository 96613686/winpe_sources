# CSaveAttachDlg::SaveAttachment(ushort const *,ATTACHDATA_tag const *)

- ea: `0x1800cc62c`
- end: `0x1800cc849`
- name: `?SaveAttachment@CSaveAttachDlg@@AEAAJPEBGPEBUATTACHDATA_tag@@@Z`
- size: `541`
- prototype: `int(CSaveAttachDlg *__hidden this, const unsigned __int16 *, const struct ATTACHDATA_tag *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800cc2e8`

## callees

- `0x180002098`
- `0x1800055bc`
- `0x18000910c`
- `0x18008ed30`
- `0x1800cacb8`
- `0x1800cc62c`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!MessageBoxInstW` at `0x1800cc74f`
- `MSOERT2!MessageBoxInstW` at `0x1800cc74f`
- `SHLWAPI!PathAppendW` at `0x1800cc68e`
- `SHLWAPI!PathAppendW` at `0x1800cc68e`
- `SHLWAPI!PathFileExistsW` at `0x1800cc6a1`
- `SHLWAPI!PathFileExistsW` at `0x1800cc6a1`
- `USER32!MessageBoxW` at `0x1800cc6eb`
- `USER32!LoadStringW` at `0x1800cc6c8`
- `USER32!LoadStringW` at `0x1800cc7a8`
- `USER32!LoadStringW` at `0x1800cc6c8`
- `USER32!LoadStringW` at `0x1800cc732`
- `USER32!LoadStringW` at `0x1800cc7a8`

## pseudocode

```c
__int64 __fastcall CSaveAttachDlg::SaveAttachment(
        CSaveAttachDlg *this,
        const unsigned __int16 *a2,
        const struct ATTACHDATA_tag *a3)
{
  int v5; // eax
  int AttachmentServices; // ebx
  void *v8[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[512]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v11[776]; // [rsp+680h] [rbp+580h] BYREF

  v8[0] = 0;
  Buffer[0] = 0;
  if ( (int)StringCchCopyW(pszPath, 0x104u, a2) < 0 || !PathAppendW(pszPath, (LPCWSTR)a3 + 520) )
    return 2147500037LL;
  if ( !PathFileExistsW(pszPath) )
    goto LABEL_8;
  LoadStringW(g_hLocRes, 0x501u, Buffer, 512);
  StringCchPrintfW(v11, 0x304u, Buffer, pszPath);
  v5 = MessageBoxInstW(g_hLocRes, *((_QWORD *)this + 2), 1279, v11, 0, 307, LoadStringW, MessageBoxW, 0, 0, 0, 0);
  if ( v5 == 2 )
    return 2148275971LL;
  if ( v5 == 7 )
    return 0;
LABEL_8:
  AttachmentServices = HrSaveAttachToFile(*((_QWORD *)this + 1), *((_QWORD *)a3 + 198), pszPath);
  if ( AttachmentServices >= 0 )
  {
    LoadStringW(g_hLocRes, 0x57Au, Buffer, 512);
    AttachmentServices = CreateAttachmentServices(Buffer, &IID_IAttachmentExecute, v8);
    if ( AttachmentServices >= 0 )
    {
      AttachmentServices = (*(__int64 (__fastcall **)(void *, WCHAR *))(*(_QWORD *)v8[0] + 40LL))(v8[0], pszPath);
      if ( AttachmentServices >= 0 )
      {
        if ( *((_DWORD *)this + 140) )
          (*(void (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v8[0] + 64LL))(v8[0], L"about:internet");
        AttachmentServices = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v8[0] + 88LL))(v8[0]);
      }
    }
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(v8);
  return (unsigned int)AttachmentServices;
}

```

## disassembly

```asm
0x1800cc62c  push    rbp
0x1800cc62e  push    rbx
0x1800cc62f  push    rdi
0x1800cc630  lea     rbp, [rsp-0BA0h]
0x1800cc638  sub     rsp, 0CA0h
0x1800cc63f  mov     rax, cs:__security_cookie
0x1800cc646  xor     rax, rsp
0x1800cc649  mov     [rbp+0BB0h+var_20], rax
0x1800cc650  mov     rbx, r8
0x1800cc653  mov     [rsp+0CB0h+var_C50], 0
0x1800cc65c  mov     r8, rdx; unsigned __int16 *
0x1800cc65f  mov     rdi, rcx
0x1800cc662  xor     eax, eax
0x1800cc664  lea     rcx, [rsp+0CB0h+pszPath]; unsigned __int16 *
0x1800cc669  mov     edx, 104h; unsigned __int64
0x1800cc66e  mov     [rbp+0BB0h+Buffer], ax
0x1800cc675  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cc67a  test    eax, eax
0x1800cc67c  js      loc_1800CC82A
0x1800cc682  lea     rdx, [rbx+410h]; pszMore
0x1800cc689  lea     rcx, [rsp+0CB0h+pszPath]; pszPath
0x1800cc68e  call    cs:__imp_PathAppendW
0x1800cc694  test    eax, eax
0x1800cc696  jz      loc_1800CC82A
0x1800cc69c  lea     rcx, [rsp+0CB0h+pszPath]; pszPath
0x1800cc6a1  call    cs:__imp_PathFileExistsW
0x1800cc6a7  test    eax, eax
0x1800cc6a9  jz      loc_1800CC770
0x1800cc6af  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800cc6b6  lea     r8, [rbp+0BB0h+Buffer]; lpBuffer
0x1800cc6bd  mov     r9d, 200h; cchBufferMax
0x1800cc6c3  mov     edx, 501h; uID
0x1800cc6c8  call    cs:__imp_LoadStringW
0x1800cc6ce  lea     r9, [rsp+0CB0h+pszPath]
0x1800cc6d3  mov     edx, 304h; unsigned __int64
0x1800cc6d8  lea     r8, [rbp+0BB0h+Buffer]; unsigned __int16 *
0x1800cc6df  lea     rcx, [rbp+0BB0h+var_630]; unsigned __int16 *
0x1800cc6e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cc6eb  mov     rax, cs:__imp_MessageBoxW
0x1800cc6f2  lea     r9, [rbp+0BB0h+var_630]
0x1800cc6f9  mov     rdx, [rdi+10h]
0x1800cc6fd  mov     r8d, 4FFh
0x1800cc703  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x1800cc70a  mov     [rsp+0CB0h+var_C58], 0
0x1800cc712  mov     [rsp+0CB0h+var_C60], 0
0x1800cc71b  mov     [rsp+0CB0h+var_C68], 0
0x1800cc724  mov     [rsp+0CB0h+var_C70], 0
0x1800cc72d  mov     [rsp+0CB0h+var_C78], rax
0x1800cc732  mov     rax, cs:__imp_LoadStringW
0x1800cc739  mov     [rsp+0CB0h+var_C80], rax
0x1800cc73e  mov     [rsp+0CB0h+var_C88], 133h
0x1800cc746  mov     [rsp+0CB0h+var_C90], 0
0x1800cc74f  call    cs:__imp_MessageBoxInstW
0x1800cc755  cmp     eax, 2
0x1800cc758  jnz     short loc_1800CC764
0x1800cc75a  mov     eax, 800C1703h
0x1800cc75f  jmp     loc_1800CC82F
0x1800cc764  cmp     eax, 7
0x1800cc767  jnz     short loc_1800CC770
0x1800cc769  xor     eax, eax
0x1800cc76b  jmp     loc_1800CC82F
0x1800cc770  mov     rdx, [rbx+630h]
0x1800cc777  lea     r8, [rsp+0CB0h+pszPath]
0x1800cc77c  mov     rcx, [rdi+8]
0x1800cc780  call    HrSaveAttachToFile
0x1800cc785  mov     ebx, eax
0x1800cc787  test    eax, eax
0x1800cc789  js      loc_1800CC81C
0x1800cc78f  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800cc796  lea     r8, [rbp+0BB0h+Buffer]; lpBuffer
0x1800cc79d  mov     r9d, 200h; cchBufferMax
0x1800cc7a3  mov     edx, 57Ah; uID
0x1800cc7a8  call    cs:__imp_LoadStringW
0x1800cc7ae  lea     r8, [rsp+0CB0h+var_C50]; void **
0x1800cc7b3  lea     rdx, IID_IAttachmentExecute; struct _GUID *
0x1800cc7ba  lea     rcx, [rbp+0BB0h+Buffer]; unsigned __int16 *
0x1800cc7c1  call    ?CreateAttachmentServices@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateAttachmentServices(ushort const *,_GUID const &,void * *)
0x1800cc7c6  mov     ebx, eax
0x1800cc7c8  test    eax, eax
0x1800cc7ca  js      short loc_1800CC81C
0x1800cc7cc  mov     rcx, [rsp+0CB0h+var_C50]
0x1800cc7d1  lea     rdx, [rsp+0CB0h+pszPath]
0x1800cc7d6  mov     rax, [rcx]
0x1800cc7d9  mov     rax, [rax+28h]
0x1800cc7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc7e2  mov     ebx, eax
0x1800cc7e4  test    eax, eax
0x1800cc7e6  js      short loc_1800CC81C
0x1800cc7e8  cmp     dword ptr [rdi+230h], 0
0x1800cc7ef  jz      short loc_1800CC809
0x1800cc7f1  mov     rcx, [rsp+0CB0h+var_C50]
0x1800cc7f6  lea     rdx, aAboutInternet; "about:internet"
0x1800cc7fd  mov     rax, [rcx]
0x1800cc800  mov     rax, [rax+40h]
0x1800cc804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc809  mov     rcx, [rsp+0CB0h+var_C50]
0x1800cc80e  mov     rax, [rcx]
0x1800cc811  mov     rax, [rax+58h]
0x1800cc815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc81a  mov     ebx, eax
0x1800cc81c  lea     rcx, [rsp+0CB0h+var_C50]
0x1800cc821  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800cc826  mov     eax, ebx
0x1800cc828  jmp     short loc_1800CC82F
0x1800cc82a  mov     eax, 80004005h
0x1800cc82f  mov     rcx, [rbp+0BB0h+var_20]
0x1800cc836  xor     rcx, rsp; StackCookie
0x1800cc839  call    __security_check_cookie
0x1800cc83e  add     rsp, 0CA0h
0x1800cc845  pop     rdi
0x1800cc846  pop     rbx
0x1800cc847  pop     rbp
0x1800cc848  retn
```
