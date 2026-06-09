# Variant::toStream(tagVARIANT,IStream * *,ushort * *)

- ea: `0x1800e9550`
- end: `0x1800e99e3`
- name: `?toStream@Variant@@SAJUtagVARIANT@@PEAPEAUIStream@@PEAPEAG@Z`
- size: `1171`
- prototype: `__int64 __fastcall(struct tagVARIANT *__struct_ptr, struct IStream **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800f38b8`

## callees

- `0x18001ad40`
- `0x18001da4c`
- `0x18001f080`
- `0x180026c28`
- `0x18003e82c`
- `0x18005f9b8`
- `0x180064034`
- `0x1800654ec`
- `0x18006ccbc`
- `0x1800e8e98`
- `0x1800e8f30`
- `0x1800e912c`
- `0x1800e9380`
- `0x1800e9550`
- `0x180102d20`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800e9804`
- `msvcrt!_resetstkoflw` at `0x1800e9804`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e9857`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e9857`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e97f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e9883`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e97f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e9883`

## string_xrefs

- `0x1800e9720`: `text/xml`
- `0x1800e97c2`: `text/xml`

## pseudocode

```c
__int64 __fastcall Variant::toStream(struct tagVARIANT *a1, struct IStream **a2, struct CachingStreamForExternal **a3)
{
  struct CachingStreamForExternal *v6; // r15
  int v7; // eax
  int v8; // esi
  MemoryStreamForExternal *v9; // rax
  MemoryStreamForExternal *v10; // r14
  unsigned __int8 *v11; // rbx
  int (__fastcall ***llVal)(_QWORD, GUID *, struct IUnknown **); // r14
  struct String *Encoding; // rbx
  Document *ObjectFromIUnk; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v18; // [rsp+28h] [rbp-C0h]
  unsigned int v19; // [rsp+28h] [rbp-C0h]
  unsigned int v20; // [rsp+28h] [rbp-C0h]
  unsigned int v21[2]; // [rsp+30h] [rbp-B8h] BYREF
  int v22; // [rsp+38h] [rbp-B0h]
  struct CachingStreamForExternal *v23; // [rsp+40h] [rbp-A8h] BYREF
  struct IStream *v24; // [rsp+48h] [rbp-A0h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int8 *v26; // [rsp+58h] [rbp-90h] BYREF
  struct IUnknown *v27; // [rsp+60h] [rbp-88h] BYREF
  _QWORD v28[3]; // [rsp+68h] [rbp-80h] BYREF
  struct tagVARIANT v29; // [rsp+80h] [rbp-68h] BYREF

  v28[1] = a2;
  v28[2] = a3;
  v28[0] = 0;
  v24 = 0;
  v26 = 0;
  v21[0] = 0;
  v27 = 0;
  v6 = 0;
  v23 = 0;
  v29 = *a1;
  v7 = Variant::toBuffer(&v29, &v26, v21);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 != 1 || ((a1->vt - 9) & 0xFFFB) != 0 )
    {
      v8 = -2147024809;
      goto LABEL_32;
    }
    llVal = (int (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))a1->llVal;
    if ( llVal )
    {
      if ( (**llVal)(llVal, &IID_IXMLDOMDocument, &v27) >= 0 )
      {
        Encoding = 0;
        ObjectFromIUnk = (Document *)Object::getObjectFromIUnk(v27, &IID_Document);
        if ( ObjectFromIUnk )
          Encoding = Document::getEncoding(ObjectFromIUnk);
        if ( Encoding )
        {
          *(_OWORD *)&v29.vt = *(_OWORD *)L"; charset=";
          *(ULONGLONG *)((char *)&v29.decVal.Lo64 + 6) = *(_QWORD *)L"et=";
          *(_QWORD *)v21 = 0;
          v6 = (struct CachingStreamForExternal *)new_array_size<unsigned short>(v15, *((int *)Encoding + 4), v16, v21);
          v23 = v6;
          v25 = (unsigned __int16 *)v6;
          *(_WORD *)v6 = 0;
          v8 = StringCchCatExW(
                 (unsigned __int16 *)v6,
                 *(unsigned __int64 *)v21,
                 L"text/xml",
                 &v25,
                 (unsigned __int64 *)v21,
                 v18);
          v22 = v8;
          if ( v8 < 0 )
            goto LABEL_32;
          v8 = StringCchCatExW(v25, *(unsigned __int64 *)v21, &v29.vt, &v25, (unsigned __int64 *)v21, v19);
          v22 = v8;
          if ( v8 < 0 )
            goto LABEL_32;
          v8 = StringCchCatExW(
                 v25,
                 *(unsigned __int64 *)v21,
                 *((const unsigned __int16 **)Encoding + 3),
                 &v25,
                 (unsigned __int64 *)v21,
                 v20);
          v22 = v8;
          if ( v8 < 0 )
            goto LABEL_32;
          (*(void (__fastcall **)(struct String *))(*(_QWORD *)Encoding + 104LL))(Encoding);
        }
        else
        {
          v8 = allocStrWHR(L"text/xml", (unsigned __int16 **)&v23, 8u);
          v22 = v8;
          if ( v8 < 0 )
          {
            v6 = v23;
            goto LABEL_32;
          }
          v6 = v23;
        }
      }
      if ( (**llVal)(llVal, &IID_IPersistStreamInit, (struct IUnknown **)v28) >= 0 )
      {
        v23 = 0;
        v8 = CachingStreamForExternal::New(&v23);
        v24 = v23;
        if ( v8 >= 0 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, struct CachingStreamForExternal *, __int64))(*(_QWORD *)v28[0] + 48LL))(
                 v28[0],
                 v23,
                 1);
LABEL_32:
        if ( v8 >= 0 )
          goto LABEL_36;
        goto LABEL_33;
      }
      v8 = (**llVal)(llVal, &IID_IStream, (struct IUnknown **)&v24);
      if ( v8 >= 0 )
        goto LABEL_32;
    }
    v8 = -2147024809;
    goto LABEL_33;
  }
  if ( !v26 || !v21[0] )
    goto LABEL_32;
  v9 = (MemoryStreamForExternal *)_MemAlloc(0x38u, 8u);
  if ( v9 )
    v10 = MemoryStreamForExternal::MemoryStreamForExternal(v9);
  else
    v10 = 0;
  if ( v10 )
  {
    v11 = v26;
    v8 = 0;
    MemoryStream::reset(v10);
    *((_QWORD *)v10 + 3) = v11;
    *((_QWORD *)v10 + 4) = v11;
    *((_QWORD *)v10 + 5) = v21[0];
    *((_BYTE *)v10 + 48) = 1;
  }
  else
  {
    v8 = -2147024882;
  }
  v24 = v10;
  if ( v8 >= 0 )
  {
    v26 = 0;
    goto LABEL_32;
  }
LABEL_33:
  if ( v24 )
  {
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  MemFreeObject(v6);
  v6 = 0;
LABEL_36:
  if ( v26 )
    MemFreeObject(v26);
  *a2 = v24;
  *a3 = v6;
  if ( v27 )
  {
    ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
    v27 = 0;
  }
  if ( v28[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800e9550  mov     r11, rsp
0x1800e9553  push    rbx
0x1800e9554  push    rsi
0x1800e9555  push    rdi
0x1800e9556  push    r12
0x1800e9558  push    r13
0x1800e955a  push    r14
0x1800e955c  push    r15
0x1800e955e  sub     rsp, 0B0h
0x1800e9565  mov     rax, cs:__security_cookie
0x1800e956c  xor     rax, rsp
0x1800e956f  mov     [rsp+0E8h+var_48], rax
0x1800e9577  mov     r13, r8
0x1800e957a  mov     r12, rdx
0x1800e957d  mov     r14, rcx
0x1800e9580  mov     [rsp+0E8h+var_78], rdx
0x1800e9585  mov     [rsp+0E8h+var_70], r8
0x1800e958a  xor     edi, edi
0x1800e958c  mov     [r11-80h], rdi
0x1800e9590  mov     [rsp+0E8h+var_A0], rdi
0x1800e9595  mov     [rsp+0E8h+var_90], rdi
0x1800e959a  mov     [rsp+0E8h+var_B8], edi
0x1800e959e  mov     [rsp+0E8h+var_88], rdi
0x1800e95a3  mov     r15d, edi
0x1800e95a6  mov     [rsp+0E8h+var_A8], rdi
0x1800e95ab  movaps  xmm0, xmmword ptr [rcx]
0x1800e95ae  movaps  xmmword ptr [r11-68h], xmm0
0x1800e95b3  movsd   xmm1, qword ptr [rcx+10h]
0x1800e95b8  movsd   qword ptr [r11-58h], xmm1
0x1800e95be  lea     r8, [rsp+0E8h+var_B8]; unsigned int *
0x1800e95c3  lea     rdx, [rsp+0E8h+var_90]; unsigned __int8 **
0x1800e95c8  lea     rcx, [r11-68h]; struct tagVARIANT
0x1800e95cc  call    ?toBuffer@Variant@@SAJUtagVARIANT@@PEAPEAEPEAK@Z; Variant::toBuffer(tagVARIANT,uchar * *,ulong *)
0x1800e95d1  mov     esi, eax
0x1800e95d3  test    eax, eax
0x1800e95d5  jnz     short loc_1800E9653
0x1800e95d7  cmp     [rsp+0E8h+var_90], rdi
0x1800e95dc  jz      loc_1800E9947
0x1800e95e2  cmp     [rsp+0E8h+var_B8], edi
0x1800e95e6  jz      loc_1800E9947
0x1800e95ec  lea     edx, [rdi+8]; unsigned int
0x1800e95ef  lea     ecx, [rdi+38h]; unsigned __int64
0x1800e95f2  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1800e95f7  test    rax, rax
0x1800e95fa  jz      short loc_1800E9609
0x1800e95fc  mov     rcx, rax; this
0x1800e95ff  call    ??0MemoryStreamForExternal@@QEAA@XZ; MemoryStreamForExternal::MemoryStreamForExternal(void)
0x1800e9604  mov     r14, rax
0x1800e9607  jmp     short loc_1800E960C
0x1800e9609  mov     r14, rdi
0x1800e960c  test    r14, r14
0x1800e960f  jz      short loc_1800E9637
0x1800e9611  mov     rbx, [rsp+0E8h+var_90]
0x1800e9616  mov     esi, edi
0x1800e9618  mov     rcx, r14; this
0x1800e961b  call    ?reset@MemoryStream@@QEAAXXZ; MemoryStream::reset(void)
0x1800e9620  mov     [r14+18h], rbx
0x1800e9624  mov     [r14+20h], rbx
0x1800e9628  mov     eax, [rsp+0E8h+var_B8]
0x1800e962c  mov     [r14+28h], rax
0x1800e9630  mov     byte ptr [r14+30h], 1
0x1800e9635  jmp     short loc_1800E963C
0x1800e9637  mov     esi, 8007000Eh
0x1800e963c  mov     [rsp+0E8h+var_A0], r14
0x1800e9641  test    esi, esi
0x1800e9643  js      loc_1800E994B
0x1800e9649  mov     [rsp+0E8h+var_90], rdi
0x1800e964e  jmp     loc_1800E9947
0x1800e9653  cmp     eax, 1
0x1800e9656  jnz     loc_1800E9942
0x1800e965c  movzx   eax, word ptr [r14]
0x1800e9660  sub     ax, 9
0x1800e9664  mov     ecx, 0FFFBh
0x1800e9669  test    cx, ax
0x1800e966c  jnz     loc_1800E9942
0x1800e9672  mov     r14, [r14+8]
0x1800e9676  test    r14, r14
0x1800e9679  jz      loc_1800E993B
0x1800e967f  mov     rax, [r14]
0x1800e9682  lea     r8, [rsp+0E8h+var_88]
0x1800e9687  lea     rdx, IID_IXMLDOMDocument
0x1800e968e  mov     rcx, r14
0x1800e9691  mov     rax, [rax]
0x1800e9694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9699  test    eax, eax
0x1800e969b  js      loc_1800E98C3
0x1800e96a1  mov     rbx, rdi
0x1800e96a4  lea     rdx, ?IID_Document@@3U_GUID@@B; struct _GUID *
0x1800e96ab  mov     rcx, [rsp+0E8h+var_88]; struct IUnknown *
0x1800e96b0  call    ?getObjectFromIUnk@Object@@SAPEAV1@PEAUIUnknown@@AEBU_GUID@@@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &)
0x1800e96b5  test    rax, rax
0x1800e96b8  jz      short loc_1800E96C5
0x1800e96ba  mov     rcx, rax; this
0x1800e96bd  call    ?getEncoding@Document@@QEAAPEAVString@@XZ; Document::getEncoding(void)
0x1800e96c2  mov     rbx, rax
0x1800e96c5  test    rbx, rbx
0x1800e96c8  jz      loc_1800E97B7
0x1800e96ce  movups  xmm0, xmmword ptr cs:aCharset_0; "; charset="
0x1800e96d5  movups  xmmword ptr [rsp+0E8h+var_68], xmm0
0x1800e96dd  movsd   xmm1, qword ptr cs:aCharset_0+0Eh; "et="
0x1800e96e5  movsd   qword ptr [rsp+0E8h+var_68+0Eh], xmm1
0x1800e96ee  mov     qword ptr [rsp+0E8h+var_B8], rdi
0x1800e96f3  movsxd  rdx, dword ptr [rbx+10h]
0x1800e96f7  lea     r9, [rsp+0E8h+var_B8]
0x1800e96fc  call    ??$new_array_size@G@@YAPEAG_J00PEA_K@Z; new_array_size<ushort>(__int64,__int64,__int64,unsigned __int64 *)
0x1800e9701  mov     r15, rax
0x1800e9704  mov     [rsp+0E8h+var_A8], rax
0x1800e9709  mov     [rsp+0E8h+var_98], rax
0x1800e970e  mov     [rax], di
0x1800e9711  lea     rax, [rsp+0E8h+var_B8]
0x1800e9716  mov     [rsp+0E8h+var_C8], rax; unsigned __int64 *
0x1800e971b  lea     r9, [rsp+0E8h+var_98]; unsigned __int16 **
0x1800e9720  lea     r8, aTextXml_0; "text/xml"
0x1800e9727  mov     rdx, qword ptr [rsp+0E8h+var_B8]; unsigned __int64
0x1800e972c  mov     rcx, r15; unsigned __int16 *
0x1800e972f  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800e9734  mov     esi, eax
0x1800e9736  mov     [rsp+0E8h+var_B0], eax
0x1800e973a  test    eax, eax
0x1800e973c  js      loc_1800E9947
0x1800e9742  lea     rax, [rsp+0E8h+var_B8]
0x1800e9747  mov     [rsp+0E8h+var_C8], rax; unsigned __int64 *
0x1800e974c  lea     r9, [rsp+0E8h+var_98]; unsigned __int16 **
0x1800e9751  lea     r8, [rsp+0E8h+var_68]; unsigned __int16 *
0x1800e9759  mov     rdx, qword ptr [rsp+0E8h+var_B8]; unsigned __int64
0x1800e975e  mov     rcx, [rsp+0E8h+var_98]; unsigned __int16 *
0x1800e9763  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800e9768  mov     esi, eax
0x1800e976a  mov     [rsp+0E8h+var_B0], eax
0x1800e976e  test    eax, eax
0x1800e9770  js      loc_1800E9947
0x1800e9776  lea     rax, [rsp+0E8h+var_B8]
0x1800e977b  mov     [rsp+0E8h+var_C8], rax; unsigned __int64 *
0x1800e9780  lea     r9, [rsp+0E8h+var_98]; unsigned __int16 **
0x1800e9785  mov     r8, [rbx+18h]; unsigned __int16 *
0x1800e9789  mov     rdx, qword ptr [rsp+0E8h+var_B8]; unsigned __int64
0x1800e978e  mov     rcx, [rsp+0E8h+var_98]; unsigned __int16 *
0x1800e9793  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800e9798  mov     esi, eax
0x1800e979a  mov     [rsp+0E8h+var_B0], eax
0x1800e979e  test    eax, eax
0x1800e97a0  js      loc_1800E9947
0x1800e97a6  mov     rax, [rbx]
0x1800e97a9  mov     rcx, rbx
0x1800e97ac  mov     rax, [rax+68h]
0x1800e97b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e97b5  jmp     short loc_1800E97E7
0x1800e97b7  mov     r8d, 8; unsigned __int64
0x1800e97bd  lea     rdx, [rsp+0E8h+var_A8]; unsigned __int16 **
0x1800e97c2  lea     rcx, aTextXml_0; "text/xml"
0x1800e97c9  call    ?allocStrWHR@@YAJPEBGPEAPEAG_K@Z; allocStrWHR(ushort const *,ushort * *,unsigned __int64)
0x1800e97ce  mov     esi, eax
0x1800e97d0  mov     [rsp+0E8h+var_B0], eax
0x1800e97d4  test    eax, eax
0x1800e97d6  jns     short loc_1800E97E2
0x1800e97d8  mov     r15, [rsp+0E8h+var_A8]
0x1800e97dd  jmp     loc_1800E9947
0x1800e97e2  mov     r15, [rsp+0E8h+var_A8]
0x1800e97e7  jmp     loc_1800E98C3
0x1800e97ec  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800e97f2  call    cs:__imp_TlsGetValue
0x1800e97f8  mov     rbx, rax
0x1800e97fb  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800e9802  jnz     short loc_1800E987D
0x1800e9804  call    cs:__imp__resetstkoflw
0x1800e980a  test    eax, eax
0x1800e980c  jnz     short loc_1800E985F
0x1800e980e  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800e9815  test    rcx, rcx
0x1800e9818  jz      short loc_1800E982C
0x1800e981a  cmp     [rcx+50h], rbx
0x1800e981e  jnz     short loc_1800E982C
0x1800e9820  mov     rax, [rcx]
0x1800e9823  mov     rax, [rax+20h]
0x1800e9827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e982c  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800e9833  test    rcx, rcx
0x1800e9836  jz      short loc_1800E984A
0x1800e9838  cmp     [rcx+50h], rbx
0x1800e983c  jnz     short loc_1800E984A
0x1800e983e  mov     rax, [rcx]
0x1800e9841  mov     rax, [rax+20h]
0x1800e9845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e984a  xor     r9d, r9d; lpArguments
0x1800e984d  xor     r8d, r8d; nNumberOfArguments
0x1800e9850  xor     edx, edx; dwExceptionFlags
0x1800e9852  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800e9857  call    cs:__imp_RaiseException
0x1800e985d  jmp     short loc_1800E987D
0x1800e985f  mov     rax, [rbx+60h]
0x1800e9863  mov     [rbx+68h], rax
0x1800e9867  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800e986e  mov     [rbx+60h], rax
0x1800e9872  mov     dword ptr [rbx+54h], 800703E9h
0x1800e9879  mov     byte ptr [rbx+78h], 0
0x1800e987d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800e9883  call    cs:__imp_TlsGetValue
0x1800e9889  mov     rcx, [rax+60h]; struct Exception *
0x1800e988d  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800e9892  mov     rdx, rax
0x1800e9895  mov     rcx, [rax]
0x1800e9898  mov     rax, [rcx+80h]
0x1800e989f  mov     rcx, rdx
0x1800e98a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e98a7  mov     esi, eax
0x1800e98a9  mov     [rsp+0E8h+var_B0], eax
0x1800e98ad  xor     edi, edi
0x1800e98af  mov     r15, [rsp+0E8h+var_A8]
0x1800e98b4  mov     r12, [rsp+0E8h+var_78]
0x1800e98b9  mov     r13, [rsp+0E8h+var_70]
0x1800e98be  jmp     loc_1800E9947
0x1800e98c3  mov     rax, [r14]
0x1800e98c6  lea     r8, [rsp+0E8h+var_80]
0x1800e98cb  lea     rdx, IID_IPersistStreamInit
0x1800e98d2  mov     rcx, r14
0x1800e98d5  mov     rax, [rax]
0x1800e98d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e98dd  test    eax, eax
0x1800e98df  js      short loc_1800E991B
0x1800e98e1  mov     [rsp+0E8h+var_A8], rdi
0x1800e98e6  lea     rcx, [rsp+0E8h+var_A8]; struct CachingStreamForExternal **
0x1800e98eb  call    ?New@CachingStreamForExternal@@SAJPEAPEAV1@@Z; CachingStreamForExternal::New(CachingStreamForExternal * *)
0x1800e98f0  mov     esi, eax
0x1800e98f2  mov     rdx, [rsp+0E8h+var_A8]
0x1800e98f7  mov     [rsp+0E8h+var_A0], rdx
0x1800e98fc  test    eax, eax
0x1800e98fe  js      short loc_1800E9947
0x1800e9900  mov     rcx, [rsp+0E8h+var_80]
0x1800e9905  mov     rax, [rcx]
0x1800e9908  mov     r8d, 1
0x1800e990e  mov     rax, [rax+30h]
0x1800e9912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9917  mov     esi, eax
0x1800e9919  jmp     short loc_1800E9947
0x1800e991b  mov     rax, [r14]
0x1800e991e  lea     r8, [rsp+0E8h+var_A0]
0x1800e9923  lea     rdx, IID_IStream
0x1800e992a  mov     rcx, r14
0x1800e992d  mov     rax, [rax]
0x1800e9930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9935  mov     esi, eax
0x1800e9937  test    eax, eax
0x1800e9939  jns     short loc_1800E9947
0x1800e993b  mov     esi, 80070057h
0x1800e9940  jmp     short loc_1800E994B
0x1800e9942  mov     esi, 80070057h
0x1800e9947  test    esi, esi
0x1800e9949  jns     short loc_1800E9971
0x1800e994b  mov     rcx, [rsp+0E8h+var_A0]
0x1800e9950  test    rcx, rcx
0x1800e9953  jz      short loc_1800E9966
0x1800e9955  mov     rax, [rcx]
0x1800e9958  mov     rax, [rax+10h]
0x1800e995c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9961  mov     [rsp+0E8h+var_A0], rdi
0x1800e9966  mov     rcx, r15; void *
0x1800e9969  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x1800e996e  mov     r15, rdi
0x1800e9971  mov     rcx, [rsp+0E8h+var_90]; void *
0x1800e9976  test    rcx, rcx
0x1800e9979  jz      short loc_1800E9980
0x1800e997b  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x1800e9980  mov     rax, [rsp+0E8h+var_A0]
0x1800e9985  mov     [r12], rax
0x1800e9989  mov     [r13+0], r15
0x1800e998d  mov     rcx, [rsp+0E8h+var_88]
0x1800e9992  test    rcx, rcx
0x1800e9995  jz      short loc_1800E99A8
0x1800e9997  mov     rax, [rcx]
0x1800e999a  mov     rax, [rax+10h]
0x1800e999e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e99a3  mov     [rsp+0E8h+var_88], rdi
0x1800e99a8  mov     rcx, [rsp+0E8h+var_80]
0x1800e99ad  test    rcx, rcx
0x1800e99b0  jz      short loc_1800E99BE
0x1800e99b2  mov     rax, [rcx]
0x1800e99b5  mov     rax, [rax+10h]
0x1800e99b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e99be  mov     eax, esi
0x1800e99c0  mov     rcx, [rsp+0E8h+var_48]
0x1800e99c8  xor     rcx, rsp; StackCookie
0x1800e99cb  call    __security_check_cookie
0x1800e99d0  add     rsp, 0B0h
0x1800e99d7  pop     r15
0x1800e99d9  pop     r14
0x1800e99db  pop     r13
0x1800e99dd  pop     r12
0x1800e99df  pop     rdi
0x1800e99e0  pop     rsi
0x1800e99e1  pop     rbx
0x1800e99e2  retn
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
  ... truncated ...
```
