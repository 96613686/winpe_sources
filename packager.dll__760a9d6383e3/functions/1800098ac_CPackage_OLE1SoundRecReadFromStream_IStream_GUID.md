# CPackage::OLE1SoundRecReadFromStream(IStream *,_GUID)

- ea: `0x1800098ac`
- end: `0x180009bc0`
- name: `?OLE1SoundRecReadFromStream@CPackage@@IEAAJPEAUIStream@@U_GUID@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *, struct _GUID *Buf1)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009370`

## callees

- `0x1800079ac`
- `0x1800095e0`
- `0x1800098ac`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000abf0`
- `0x18000cba6`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009a7d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009a7d`

## pseudocode

```c
__int64 __fastcall CPackage::OLE1SoundRecReadFromStream(CPackage *this, struct IStream *a2, struct _GUID *Buf1)
{
  __int64 v6; // rsi
  const wchar_t *v7; // r8
  __int64 v8; // rdi
  _WORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  const wchar_t *v12; // r8
  __int64 v13; // rcx
  const wchar_t *v15; // r8
  __int64 v16; // rcx
  _WORD *v17; // rcx
  HRESULT (__stdcall *Read)(IStream *, void *, ULONG, ULONG *); // rax
  int TempFileName; // ebx
  __int64 v20; // rax
  const WCHAR *v21; // rcx
  _DWORD *v22; // rax
  _WORD *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  _WORD *v26; // rax
  _WORD *v27; // rdx
  __int64 v28; // rax
  _WORD *v29; // rcx
  _WORD *v30; // rax
  _WORD *v31; // rcx
  _DWORD v32[4]; // [rsp+30h] [rbp-258h] BYREF
  _BYTE v33[528]; // [rsp+40h] [rbp-248h] BYREF

  v32[0] = 0;
  if ( !memcmp_0(Buf1, &CLSID_SOUNDREC, 0x10u) || !memcmp_0(Buf1, &CLSID_OLE1SOUNDREC, 0x10u) )
  {
    v6 = 2147483646;
    v15 = L"OLE1EmbedStrm.wav";
    v8 = 260;
    v9 = v33;
    v16 = 2147483646;
    v11 = 260;
    do
    {
      if ( !v16 )
        break;
      if ( !*v15 )
        break;
      *v9++ = *v15++;
      --v16;
      --v11;
    }
    while ( v11 );
  }
  else if ( !memcmp_0(Buf1, &CLSID_AVIFile, 0x10u) )
  {
    v6 = 2147483646;
    v7 = L"OLE1EmbedStrm.avi";
    v8 = 260;
    v9 = v33;
    v10 = 2147483646;
    v11 = 260;
    do
    {
      if ( !v10 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v10;
      --v11;
    }
    while ( v11 );
  }
  else
  {
    if ( memcmp_0(Buf1, &CLSID_MIDFile, 0x10u) )
      return 2147549183LL;
    v6 = 2147483646;
    v12 = L"OLE1EmbedStrm.mid";
    v8 = 260;
    v9 = v33;
    v13 = 2147483646;
    v11 = 260;
    do
    {
      if ( !v13 )
        break;
      if ( !*v12 )
        break;
      *v9++ = *v12++;
      --v13;
      --v11;
    }
    while ( v11 );
  }
  v17 = v9 - 1;
  *((_DWORD *)this + 26) = 3;
  if ( v11 )
    v17 = v9;
  Read = a2->lpVtbl->Read;
  *v17 = 0;
  if ( ((int (__fastcall *)(struct IStream *, _DWORD *, __int64))Read)(a2, v32, 4) < 0 )
    return 2147500037LL;
  TempFileName = -2147467259;
  if ( v32[0] )
  {
    v20 = *((_QWORD *)this + 14);
    if ( v20 )
    {
      v21 = *(const WCHAR **)(v20 + 592);
      if ( v21 )
      {
        DeleteFileW(v21);
        operator delete(*(void **)(*((_QWORD *)this + 14) + 592LL));
      }
      operator delete(*((void **)this + 14));
    }
    v22 = operator new(0x270u);
    *((_QWORD *)this + 14) = v22;
    if ( v22 )
    {
      *v22 = 64;
      v23 = v33;
      v24 = 260;
      *(_DWORD *)(*((_QWORD *)this + 14) + 68LL) = v32[0];
      v25 = 2147483646;
      *(_DWORD *)(*((_QWORD *)this + 14) + 64LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 14) + 616LL) = 0;
      v26 = (_WORD *)(*((_QWORD *)this + 14) + 72LL);
      do
      {
        if ( !v25 )
          break;
        if ( !*v23 )
          break;
        *v26++ = *v23++;
        --v25;
        --v24;
      }
      while ( v24 );
      v27 = v26 - 1;
      if ( v24 )
        v27 = v26;
      *v27 = 0;
      TempFileName = CPackage::CreateTempFileName(this);
      if ( TempFileName >= 0 )
      {
        TempFileName = CopyStreamToFile(
                         a2,
                         *(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL),
                         *(_DWORD *)(*((_QWORD *)this + 14) + 68LL));
        if ( TempFileName >= 0 )
        {
          v28 = *((_QWORD *)this + 14);
          v29 = *(_WORD **)(v28 + 592);
          v30 = (_WORD *)(v28 + 72);
          do
          {
            if ( !v6 )
              break;
            if ( !*v29 )
              break;
            *v30++ = *v29++;
            --v6;
            --v8;
          }
          while ( v8 );
          v31 = v30 - 1;
          if ( v8 )
            v31 = v30;
          *v31 = 0;
          MarkFileUnsafe(*(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL));
        }
      }
    }
  }
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x1800098ac  mov     [rsp+arg_10], rbx
0x1800098b1  push    rbp
0x1800098b2  push    rsi
0x1800098b3  push    rdi
0x1800098b4  push    r14
0x1800098b6  push    r15
0x1800098b8  sub     rsp, 260h
0x1800098bf  mov     rax, cs:__security_cookie
0x1800098c6  xor     rax, rsp
0x1800098c9  mov     [rsp+288h+var_38], rax
0x1800098d1  mov     rbx, r8
0x1800098d4  xor     r15d, r15d
0x1800098d7  mov     r14, rdx
0x1800098da  mov     [rsp+288h+var_258], r15d
0x1800098df  mov     rbp, rcx
0x1800098e2  lea     rdx, CLSID_SOUNDREC; Buf2
0x1800098e9  mov     rcx, rbx; Buf1
0x1800098ec  lea     edi, [r15+10h]
0x1800098f0  mov     r8d, edi; Size
0x1800098f3  call    memcmp_0
0x1800098f8  test    eax, eax
0x1800098fa  jz      loc_1800099DB
0x180009900  mov     r8d, edi; Size
0x180009903  lea     rdx, CLSID_OLE1SOUNDREC; Buf2
0x18000990a  mov     rcx, rbx; Buf1
0x18000990d  call    memcmp_0
0x180009912  test    eax, eax
0x180009914  jz      loc_1800099DB
0x18000991a  mov     r8d, edi; Size
0x18000991d  lea     rdx, CLSID_AVIFile; Buf2
0x180009924  mov     rcx, rbx; Buf1
0x180009927  call    memcmp_0
0x18000992c  test    eax, eax
0x18000992e  jnz     short loc_18000997B
0x180009930  mov     esi, 7FFFFFFEh
0x180009935  lea     r8, aOle1embedstrmA; "OLE1EmbedStrm.avi"
0x18000993c  mov     edi, 104h
0x180009941  lea     rax, [rsp+288h+var_248]
0x180009946  mov     ecx, esi
0x180009948  mov     edx, edi
0x18000994a  test    rcx, rcx
0x18000994d  jz      loc_180009A19
0x180009953  movzx   r9d, word ptr [r8]
0x180009957  test    r9w, r9w
0x18000995b  jz      loc_180009A19
0x180009961  mov     [rax], r9w
0x180009965  add     r8, 2
0x180009969  add     rax, 2
0x18000996d  dec     rcx
0x180009970  sub     rdx, 1
0x180009974  jnz     short loc_18000994A
0x180009976  jmp     loc_180009A19
0x18000997b  mov     r8, rdi; Size
0x18000997e  lea     rdx, CLSID_MIDFile; Buf2
0x180009985  mov     rcx, rbx; Buf1
0x180009988  call    memcmp_0
0x18000998d  test    eax, eax
0x18000998f  jnz     short loc_1800099D1
0x180009991  mov     esi, 7FFFFFFEh
0x180009996  lea     r8, aOle1embedstrmM; "OLE1EmbedStrm.mid"
0x18000999d  mov     edi, 104h
0x1800099a2  lea     rax, [rsp+288h+var_248]
0x1800099a7  mov     ecx, esi
0x1800099a9  mov     edx, edi
0x1800099ab  test    rcx, rcx
0x1800099ae  jz      short loc_180009A19
0x1800099b0  movzx   r9d, word ptr [r8]
0x1800099b4  test    r9w, r9w
0x1800099b8  jz      short loc_180009A19
0x1800099ba  mov     [rax], r9w
0x1800099be  add     r8, 2
0x1800099c2  add     rax, 2
0x1800099c6  dec     rcx
0x1800099c9  sub     rdx, 1
0x1800099cd  jnz     short loc_1800099AB
0x1800099cf  jmp     short loc_180009A19
0x1800099d1  mov     eax, 8000FFFFh
0x1800099d6  jmp     loc_180009B99
0x1800099db  mov     esi, 7FFFFFFEh
0x1800099e0  lea     r8, aOle1embedstrmW; "OLE1EmbedStrm.wav"
0x1800099e7  mov     edi, 104h
0x1800099ec  lea     rax, [rsp+288h+var_248]
0x1800099f1  mov     ecx, esi
0x1800099f3  mov     edx, edi
0x1800099f5  test    rcx, rcx
0x1800099f8  jz      short loc_180009A19
0x1800099fa  movzx   r9d, word ptr [r8]
0x1800099fe  test    r9w, r9w
0x180009a02  jz      short loc_180009A19
0x180009a04  mov     [rax], r9w
0x180009a08  add     r8, 2
0x180009a0c  add     rax, 2
0x180009a10  dec     rcx
0x180009a13  sub     rdx, 1
0x180009a17  jnz     short loc_1800099F5
0x180009a19  lea     rcx, [rax-2]
0x180009a1d  mov     dword ptr [rbp+68h], 3
0x180009a24  test    rdx, rdx
0x180009a27  lea     rdx, [rsp+288h+var_258]
0x180009a2c  cmovnz  rcx, rax
0x180009a30  mov     rax, [r14]
0x180009a33  xor     r9d, r9d
0x180009a36  mov     rax, [rax+18h]
0x180009a3a  mov     [rcx], r15w
0x180009a3e  lea     r8d, [r9+4]
0x180009a42  mov     rcx, r14
0x180009a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a4a  test    eax, eax
0x180009a4c  jns     short loc_180009A58
0x180009a4e  mov     eax, 80004005h
0x180009a53  jmp     loc_180009B99
0x180009a58  mov     ebx, 80004005h
0x180009a5d  cmp     [rsp+288h+var_258], r15d
0x180009a62  jbe     loc_180009B97
0x180009a68  mov     rax, [rbp+70h]
0x180009a6c  test    rax, rax
0x180009a6f  jz      short loc_180009A9C
0x180009a71  mov     rcx, [rax+250h]; lpFileName
0x180009a78  test    rcx, rcx
0x180009a7b  jz      short loc_180009A93
0x180009a7d  call    cs:__imp_DeleteFileW
0x180009a83  mov     rcx, [rbp+70h]
0x180009a87  mov     rcx, [rcx+250h]; lpMem
0x180009a8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009a93  mov     rcx, [rbp+70h]; lpMem
0x180009a97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009a9c  mov     ecx, 270h; unsigned __int64
0x180009aa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009aa6  mov     [rbp+70h], rax
0x180009aaa  test    rax, rax
0x180009aad  jz      loc_180009B97
0x180009ab3  mov     dword ptr [rax], 40h ; '@'
0x180009ab9  lea     rdx, [rsp+288h+var_248]
0x180009abe  mov     rcx, [rbp+70h]
0x180009ac2  mov     r8, rdi
0x180009ac5  mov     eax, [rsp+288h+var_258]
0x180009ac9  mov     [rcx+44h], eax
0x180009acc  mov     rcx, rsi
0x180009acf  mov     rax, [rbp+70h]
0x180009ad3  mov     [rax+40h], r15d
0x180009ad7  mov     rax, [rbp+70h]
0x180009adb  mov     [rax+268h], r15d
0x180009ae2  mov     rax, [rbp+70h]
0x180009ae6  add     rax, 48h ; 'H'
0x180009aea  test    rcx, rcx
0x180009aed  jz      short loc_180009B0E
0x180009aef  movzx   r9d, word ptr [rdx]
0x180009af3  test    r9w, r9w
0x180009af7  jz      short loc_180009B0E
0x180009af9  mov     [rax], r9w
0x180009afd  add     rdx, 2
0x180009b01  add     rax, 2
0x180009b05  dec     rcx
0x180009b08  sub     r8, 1
0x180009b0c  jnz     short loc_180009AEA
0x180009b0e  test    r8, r8
0x180009b11  lea     rdx, [rax-2]
0x180009b15  mov     rcx, rbp; this
0x180009b18  cmovnz  rdx, rax
0x180009b1c  mov     [rdx], r15w
0x180009b20  call    ?CreateTempFileName@CPackage@@IEAAJXZ; CPackage::CreateTempFileName(void)
0x180009b25  mov     ebx, eax
0x180009b27  test    eax, eax
0x180009b29  js      short loc_180009B97
0x180009b2b  mov     rdx, [rbp+70h]
0x180009b2f  mov     rcx, r14; struct IStream *
0x180009b32  mov     r8d, [rdx+44h]; unsigned int
0x180009b36  mov     rdx, [rdx+250h]; unsigned __int16 *
0x180009b3d  call    ?CopyStreamToFile@@YAJPEAUIStream@@PEBGK@Z; CopyStreamToFile(IStream *,ushort const *,ulong)
0x180009b42  mov     ebx, eax
0x180009b44  test    eax, eax
0x180009b46  js      short loc_180009B97
0x180009b48  mov     rax, [rbp+70h]
0x180009b4c  mov     rcx, [rax+250h]
0x180009b53  add     rax, 48h ; 'H'
0x180009b57  test    rsi, rsi
0x180009b5a  jz      short loc_180009B78
0x180009b5c  movzx   edx, word ptr [rcx]
0x180009b5f  test    dx, dx
0x180009b62  jz      short loc_180009B78
0x180009b64  mov     [rax], dx
0x180009b67  add     rcx, 2
0x180009b6b  add     rax, 2
0x180009b6f  dec     rsi
0x180009b72  sub     rdi, 1
0x180009b76  jnz     short loc_180009B57
0x180009b78  test    rdi, rdi
0x180009b7b  lea     rcx, [rax-2]
0x180009b7f  cmovnz  rcx, rax
0x180009b83  mov     [rcx], r15w
0x180009b87  mov     rcx, [rbp+70h]
0x180009b8b  mov     rcx, [rcx+250h]; unsigned __int16 *
0x180009b92  call    ?MarkFileUnsafe@@YAJPEBG@Z; MarkFileUnsafe(ushort const *)
0x180009b97  mov     eax, ebx
0x180009b99  mov     rcx, [rsp+288h+var_38]
0x180009ba1  xor     rcx, rsp; StackCookie
0x180009ba4  call    __security_check_cookie
0x180009ba9  mov     rbx, [rsp+288h+arg_10]
0x180009bb1  add     rsp, 260h
0x180009bb8  pop     r15
0x180009bba  pop     r14
0x180009bbc  pop     rdi
0x180009bbd  pop     rsi
0x180009bbe  pop     rbp
0x180009bbf  retn
```
