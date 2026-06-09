# SendEmailThreadProc(void *)

- ea: `0x1800679b0`
- end: `0x180067b16`
- name: `?SendEmailThreadProc@@YAKPEAX@Z`
- size: `358`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800098dc`
- `0x1800254e0`
- `0x180025504`
- `0x180065e18`
- `0x180067504`
- `0x1800675cc`
- `0x1800676ec`
- `0x18006773c`
- `0x1800679b0`
- `0x180067b1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180067a1e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180067a1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800679df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800679df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067adc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067adc`
- `SHCORE!SHStrDupW` at `0x180067a39`
- `SHCORE!SHStrDupW` at `0x180067a39`

## pseudocode

```c
__int64 __fastcall SendEmailThreadProc(PVOID Parameter)
{
  struct MapiMessageW *v2; // rax
  unsigned int v3; // edx
  struct MapiMessageW *v4; // rbx
  LPWSTR *p_lpszSubject; // rsi
  bool v6; // cf
  LPVOID *lpOriginator; // rsi
  CUserObjectList *v8; // rcx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = (struct MapiMessageW *)LocalAlloc(0x40u, 0x60u);
  v4 = v2;
  if ( v2 )
  {
    p_lpszSubject = &v2->lpszSubject;
    v6 = *((_DWORD *)Parameter + 2) != 0;
    v2->lpszSubject = 0;
    if ( (LoadStringW(g_hInstance, v6 ? 3764 : 3762, Buffer, 260) || (int)ResultFromKnownLastError() >= 0)
      && SHStrDupW(Buffer, p_lpszSubject) >= 0
      && (int)GetNoteText(*(const unsigned __int16 **)Parameter, &v4->lpszNoteText) >= 0
      && (int)CreateOriginator(&v4->lpOriginator) >= 0
      && (int)CreateRecipients(*((struct CUserObjectList **)Parameter + 2), &v4->lpRecips, &v4->nRecipCount) >= 0 )
    {
      SendMapiMessage(v4);
    }
    CoTaskMemFree(*p_lpszSubject);
    CoTaskMemFree(v4->lpszNoteText);
    lpOriginator = (LPVOID *)v4->lpOriginator;
    if ( lpOriginator )
    {
      CoTaskMemFree(lpOriginator[1]);
      CoTaskMemFree(lpOriginator[2]);
      LocalFree(lpOriginator);
    }
    DestroyRecipients(v4->lpRecips, v4->nRecipCount);
    LocalFree(v4);
  }
  v8 = (CUserObjectList *)*((_QWORD *)Parameter + 2);
  if ( v8 )
    CUserObjectList::`scalar deleting destructor'(v8, v3);
  CoTaskMemFree(*(LPVOID *)Parameter);
  operator delete(Parameter, (const struct std::nothrow_t *)0x18);
  return 0;
}

```

## disassembly

```asm
0x1800679b0  mov     [rsp+arg_8], rbx
0x1800679b5  mov     [rsp+arg_10], rsi
0x1800679ba  push    rdi
0x1800679bb  sub     rsp, 240h
0x1800679c2  mov     rax, cs:__security_cookie
0x1800679c9  xor     rax, rsp
0x1800679cc  mov     [rsp+248h+var_18], rax
0x1800679d4  mov     edx, 60h ; '`'; uBytes
0x1800679d9  mov     rdi, rcx
0x1800679dc  lea     ecx, [rdx-20h]; uFlags
0x1800679df  call    cs:__imp_LocalAlloc
0x1800679e5  mov     rbx, rax
0x1800679e8  test    rax, rax
0x1800679eb  jz      loc_180067ACB
0x1800679f1  mov     ecx, [rdi+8]
0x1800679f4  lea     rsi, [rax+8]
0x1800679f8  neg     ecx
0x1800679fa  mov     qword ptr [rsi], 0
0x180067a01  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180067a08  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x180067a0d  sbb     edx, edx
0x180067a0f  mov     r9d, 104h; cchBufferMax
0x180067a15  and     edx, 2
0x180067a18  add     edx, 0EB2h; uID
0x180067a1e  call    cs:__imp_LoadStringW
0x180067a24  test    eax, eax
0x180067a26  jnz     short loc_180067A31
0x180067a28  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067a2d  test    eax, eax
0x180067a2f  js      short loc_180067A7D
0x180067a31  mov     rdx, rsi; ppwsz
0x180067a34  lea     rcx, [rsp+248h+Buffer]; psz
0x180067a39  call    cs:__imp_SHStrDupW
0x180067a3f  test    eax, eax
0x180067a41  js      short loc_180067A7D
0x180067a43  mov     rcx, [rdi]; unsigned __int16 *
0x180067a46  lea     rdx, [rbx+10h]; unsigned __int16 **
0x180067a4a  call    ?GetNoteText@@YAJPEBGPEAPEAG@Z; GetNoteText(ushort const *,ushort * *)
0x180067a4f  test    eax, eax
0x180067a51  js      short loc_180067A7D
0x180067a53  lea     rcx, [rbx+38h]; struct MapiRecipDescW **
0x180067a57  call    ?CreateOriginator@@YAJPEAPEAUMapiRecipDescW@@@Z; CreateOriginator(MapiRecipDescW * *)
0x180067a5c  test    eax, eax
0x180067a5e  js      short loc_180067A7D
0x180067a60  mov     rcx, [rdi+10h]; this
0x180067a64  lea     r8, [rbx+40h]; unsigned int *
0x180067a68  lea     rdx, [rbx+48h]; struct MapiRecipDescW **
0x180067a6c  call    ?CreateRecipients@@YAJPEAVCUserObjectList@@PEAPEAUMapiRecipDescW@@PEAK@Z; CreateRecipients(CUserObjectList *,MapiRecipDescW * *,ulong *)
0x180067a71  test    eax, eax
0x180067a73  js      short loc_180067A7D
0x180067a75  mov     rcx, rbx; struct MapiMessageW *
0x180067a78  call    ?SendMapiMessage@@YAJPEAUMapiMessageW@@@Z; SendMapiMessage(MapiMessageW *)
0x180067a7d  mov     rcx, [rsi]; pv
0x180067a80  call    cs:__imp_CoTaskMemFree
0x180067a86  mov     rcx, [rbx+10h]; pv
0x180067a8a  call    cs:__imp_CoTaskMemFree
0x180067a90  mov     rsi, [rbx+38h]
0x180067a94  test    rsi, rsi
0x180067a97  jz      short loc_180067AB6
0x180067a99  mov     rcx, [rsi+8]; pv
0x180067a9d  call    cs:__imp_CoTaskMemFree
0x180067aa3  mov     rcx, [rsi+10h]; pv
0x180067aa7  call    cs:__imp_CoTaskMemFree
0x180067aad  mov     rcx, rsi; hMem
0x180067ab0  call    cs:__imp_LocalFree
0x180067ab6  mov     edx, [rbx+40h]; int
0x180067ab9  mov     rcx, [rbx+48h]; hMem
0x180067abd  call    ?DestroyRecipients@@YAXPEAUMapiRecipDescW@@H@Z; DestroyRecipients(MapiRecipDescW *,int)
0x180067ac2  mov     rcx, rbx; hMem
0x180067ac5  call    cs:__imp_LocalFree
0x180067acb  mov     rcx, [rdi+10h]; this
0x180067acf  test    rcx, rcx
0x180067ad2  jz      short loc_180067AD9
0x180067ad4  call    ??_GCUserObjectList@@QEAAPEAXI@Z; CUserObjectList::`scalar deleting destructor'(uint)
0x180067ad9  mov     rcx, [rdi]; pv
0x180067adc  call    cs:__imp_CoTaskMemFree
0x180067ae2  mov     edx, 18h; struct std::nothrow_t *
0x180067ae7  mov     rcx, rdi; void *
0x180067aea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067aef  xor     eax, eax
0x180067af1  mov     rcx, [rsp+248h+var_18]
0x180067af9  xor     rcx, rsp; StackCookie
0x180067afc  call    __security_check_cookie
0x180067b01  lea     r11, [rsp+248h+var_8]
0x180067b09  mov     rbx, [r11+18h]
0x180067b0d  mov     rsi, [r11+20h]
0x180067b11  mov     rsp, r11
0x180067b14  pop     rdi
0x180067b15  retn
```
