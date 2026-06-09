# CXMLTag::InitStatChunk(tagSTAT_CHUNK *)

- ea: `0x18000bea0`
- end: `0x18000c532`
- name: `?InitStatChunk@CXMLTag@@UEAAHPEAUtagSTAT_CHUNK@@@Z`
- size: `1682`
- prototype: `__int64 __fastcall(CXMLTag *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005470`
- `0x180007048`
- `0x180007aa0`
- `0x180008210`
- `0x18000aab0`
- `0x18000bea0`
- `0x18000c5f0`
- `0x18000cb70`
- `0x18000cce0`
- `0x180011170`
- `0x1800111bc`
- `0x180011204`
- `0x180011564`
- `0x180013500`
- `0x180013694`
- `0x180014130`
- `0x180023388`
- `0x180025010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c16f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c1a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c46a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c4a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c16f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c1a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c46a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000c4a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c2fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c2fb`

## string_xrefs

- `0x18000c168`: `urn:schemas-microsoft-com:office:office`
- `0x18000c463`: `urn:schemas-microsoft-com:office:office`
- `0x18000c36f`: `onecoreuap\base\appmodel\search\filters\html\nlhtml\xmltag.cxx`
- `0x18000c2ce`: `LINK.OFFICECHILD`

## pseudocode

```c
__int64 __fastcall CXMLTag::InitStatChunk(CXMLTag *this, struct tagSTAT_CHUNK *a2)
{
  unsigned int v4; // esi
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 v12; // rax
  __int64 v13; // rcx
  LCID v14; // eax
  __int64 v15; // rax
  int v16; // ecx
  const wchar_t *v17; // rdx
  int v18; // r12d
  const wchar_t *v19; // rdx
  __int64 v20; // r9
  void *v21; // rbx
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // r15
  unsigned int inited; // ebx
  unsigned int v27; // edi
  size_t v28; // rbx
  wchar_t *Buffer; // rax
  unsigned int v30; // r8d
  OLECHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  __int64 v36; // r9
  __int64 v37; // rbx
  int v38; // eax
  __int64 v39; // r9
  __int64 v40; // r15
  wchar_t *v41; // rax
  wchar_t *v42; // rax
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned int v44; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v46; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v47; // [rsp+58h] [rbp-A8h] BYREF
  void **v48; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  wchar_t v51[36]; // [rsp+78h] [rbp-88h] BYREF
  void **v52; // [rsp+C0h] [rbp-40h] BYREF
  void *v53; // [rsp+C8h] [rbp-38h]
  int v54; // [rsp+D0h] [rbp-30h]
  int v55; // [rsp+D4h] [rbp-2Ch]
  wchar_t v56[36]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = 0;
  v49 = v51;
  v50 = 33;
  v51[0] = 0;
  v48 = &TLMString<32,32,1024>::`vftable';
  v5 = *((_DWORD *)this + 34) - 31;
  if ( v5 && (v6 = v5 - 1) != 0 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( !v8 )
      {
        v33 = *((_DWORD *)this + 35);
        if ( *((_BYTE *)this + 904) )
          v34 = v33 != 0;
        else
          v34 = v33 != 0 ? 2 : 0;
        *((_DWORD *)this + 227) = v34;
        goto LABEL_16;
      }
      v9 = v8 - 1;
      if ( !v9 )
      {
        if ( *((_BYTE *)this + 904) && *((_BYTE *)this + 905) )
          v35 = *((_DWORD *)this + 35) != 0 ? 3 : 0;
        else
          v35 = *((_DWORD *)this + 35) != 0 ? 4 : 0;
        *((_DWORD *)this + 227) = v35;
        goto LABEL_16;
      }
      v10 = v9 - 26;
      if ( !v10 )
      {
        CHtmlScanner::ReadTag(*((CHtmlScanner **)this + 3), 1);
        *((_DWORD *)this + 197) = 0;
        if ( *((_DWORD *)this + 35) )
        {
          if ( *((_DWORD *)this + 43) )
          {
            Src = 0;
            v44 = 0;
            ((void (__fastcall *)(void ***, _QWORD, _QWORD, __int64))v48[4])(
              &v48,
              *((_QWORD *)this + 116),
              0,
              0xFFFFFFFFLL);
            ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v48[4])(
              &v48,
              L":dt",
              HIDWORD(v50),
              0xFFFFFFFFLL);
            CHtmlScanner::ScanTagBuffer(*((CHtmlScanner **)this + 3), v49, (wchar_t **)&Src, &v44);
            CXMLTag::SetTagDataType(this, (const wchar_t *)Src, v44);
            a2->flags = CHUNK_VALUE;
            a2->breakType = CHUNK_EOS;
            v12 = *((_QWORD *)this + 1);
            v13 = *(unsigned int *)(v12 + 5568);
            if ( (_DWORD)v13 == -1 || !*(_DWORD *)(v12 + 5584) )
              v14 = *(_DWORD *)(v12 + 5572);
            else
              v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 5576) + 8 * v13) + 12LL);
            a2->locale = v14;
            *(_QWORD *)&a2->cwcStartSource = 0;
            a2->idChunkSource = 0;
            a2->attribute.guidPropSet = FMTID_UserDefinedProperties;
            a2->attribute.psProperty.ulKind = 0;
            CXMLTag::CreateCustomPropertyNameFromTagName(
              this,
              (CXMLTag *)((char *)this + 152),
              &a2->attribute.psProperty.lpwstr);
            v15 = *((_QWORD *)this + 1);
            a2->idChunk = ++*(_DWORD *)(v15 + 96);
            *((_DWORD *)this + 62) = 0;
            if ( *((_DWORD *)this + 227) != 3 )
              CHtmlScanner::EatText(*((CHtmlScanner **)this + 3));
            v4 = *((_DWORD *)this + 227) == 3;
          }
          else
          {
            CHtmlScanner::EatText(*((CHtmlScanner **)this + 3));
          }
        }
        goto LABEL_8;
      }
      v16 = v10 - 1;
      if ( !v16 )
      {
LABEL_16:
        CHtmlScanner::ReadTag(*((CHtmlScanner **)this + 3), 0);
        goto LABEL_8;
      }
      if ( v16 == 1 )
      {
        CHtmlScanner::ReadTag(*((CHtmlScanner **)this + 3), 1);
        *((_DWORD *)this + 197) = 0;
        if ( *((_DWORD *)this + 35) )
        {
          CHtmlScanner::UnGetEndTag(*((CHtmlScanner **)this + 3));
          Src = 0;
          v44 = 0;
          CHtmlScanner::ScanTagBuffer(*((CHtmlScanner **)this + 3), L"href", (wchar_t **)&Src, &v44);
          v27 = v44;
          v28 = 2LL * v44;
          Buffer = CLMString::GetBuffer((CXMLTag *)((char *)this + 1016), v44 + 1);
          memcpy_0(Buffer, Src, v28);
          CLMString::Truncate((CXMLTag *)((char *)this + 1016), v27);
          *((_DWORD *)this + 228) = 8;
          a2->flags = CHUNK_VALUE;
          a2->breakType = CHUNK_EOS;
          a2->locale = 0;
          *(_QWORD *)&a2->cwcStartSource = 0;
          a2->idChunkSource = 0;
          v52 = &CLMString::`vftable';
          v53 = v56;
          v54 = 33;
          CLMString::AssignInConstructor((CLMString *)&v52, L"LINK.OFFICECHILD", v30);
          v52 = &TLMString<32,32,1024>::`vftable';
          a2->attribute.guidPropSet = (GUID)xmmword_18002C830;
          a2->attribute.psProperty.ulKind = 0;
          v31 = (OLECHAR *)CoTaskMemAlloc(2LL * (unsigned int)(v55 + 1));
          a2->attribute.psProperty.lpwstr = v31;
          if ( !v31 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1DF,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\xmltag.cxx",
              (const char *)0x8007000ELL,
              v43);
          memcpy_0(v31, v53, 2LL * (unsigned int)(v55 + 1));
          v32 = *((_QWORD *)this + 1);
          a2->idChunk = ++*(_DWORD *)(v32 + 96);
          *((_DWORD *)this + 62) = 0;
          if ( !*((_BYTE *)this + 904) )
            CHtmlScanner::EatText(*((CHtmlScanner **)this + 3));
          v4 = *((unsigned __int8 *)this + 904);
          v52 = &TLMString<32,32,1024>::`vftable';
          CLMString::DeleteBuf((CLMString *)&v52, v56);
        }
      }
      else
      {
        inited = CPropertyTag::InitStatChunk(this, a2);
        *((_DWORD *)this + 62) = 0;
        if ( *((_DWORD *)this + 227) != 1 )
          CHtmlScanner::EatText(*((CHtmlScanner **)this + 3));
        v4 = 0;
        if ( *((_DWORD *)this + 227) == 1 )
          v4 = inited;
      }
    }
    else
    {
      CHtmlScanner::ReadTag(*((CHtmlScanner **)this + 3), 1);
      if ( *((_DWORD *)this + 35) )
      {
        Src = 0;
        v44 = 0;
        v47 = 0;
        v46 = 0;
        CHtmlScanner::ScanTagBuffer(*((CHtmlScanner **)this + 3), L"ns", (wchar_t **)&Src, &v44);
        CHtmlScanner::ScanTagBuffer(*((CHtmlScanner **)this + 3), L"prefix", &v47, &v46);
        if ( v44 )
        {
          v37 = v44;
          v38 = _o__wcsnicmp(L"urn:schemas-microsoft-com:office:office", Src, v44, v36);
          v40 = v46;
          if ( !v38 )
          {
            *((_BYTE *)this + 904) = 1;
            CHtmlScanner::SetOffice9PropPrefix(*((CHtmlScanner **)this + 3), v47, v40);
          }
          if ( !(unsigned int)_o__wcsnicmp(L"uuid:C2F41010-65B3-11d1-A29F-00AA00C14882", Src, v37, v39) )
          {
            *((_BYTE *)this + 905) = 1;
            v41 = CLMString::GetBuffer((CXMLTag *)((char *)this + 920), (int)v40 + 1);
            memcpy_0(v41, v47, 2 * v40);
            CLMString::Truncate((CXMLTag *)((char *)this + 920), v40);
          }
        }
      }
    }
  }
  else
  {
    CHtmlScanner::ReadTag(*((CHtmlScanner **)this + 3), 1);
    if ( *((_DWORD *)this + 35) )
    {
      Src = 0;
      v44 = 0;
      v47 = 0;
      v46 = 0;
      v18 = 0;
      CHtmlScanner::ScanTagBufferEx(*((CHtmlScanner **)this + 3), v17, (wchar_t **)&Src, &v44, &v47, &v46, 0);
      while ( 1 )
      {
        v21 = Src;
        if ( !Src )
          break;
        if ( v44 )
        {
          v22 = v44;
          v23 = _o__wcsnicmp(L"urn:schemas-microsoft-com:office:office", Src, v44, v20);
          v25 = v46;
          if ( !v23 )
          {
            *((_BYTE *)this + 904) = 1;
            CHtmlScanner::SetOffice9PropPrefix(*((CHtmlScanner **)this + 3), v47, v25);
          }
          if ( !(unsigned int)_o__wcsnicmp(L"uuid:C2F41010-65B3-11d1-A29F-00AA00C14882", v21, v22, v24) )
          {
            *((_BYTE *)this + 905) = 1;
            v42 = CLMString::GetBuffer((CXMLTag *)((char *)this + 920), (int)v25 + 1);
            memcpy_0(v42, v47, 2 * v25);
            CLMString::Truncate((CXMLTag *)((char *)this + 920), v25);
          }
        }
        CHtmlScanner::ScanTagBufferEx(*((CHtmlScanner **)this + 3), v19, (wchar_t **)&Src, &v44, &v47, &v46, ++v18);
      }
    }
  }
LABEL_8:
  v48 = &TLMString<32,32,1024>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v48, v51);
  return v4;
}

```

## disassembly

```asm
0x18000bea0  mov     [rsp-8+arg_10], rbx
0x18000bea5  push    rbp
0x18000bea6  push    rsi
0x18000bea7  push    rdi
0x18000bea8  push    r12
0x18000beaa  push    r13
0x18000beac  push    r14
0x18000beae  push    r15
0x18000beb0  lea     rbp, [rsp-30h]
0x18000beb5  sub     rsp, 130h
0x18000bebc  mov     rax, cs:__security_cookie
0x18000bec3  xor     rax, rsp
0x18000bec6  mov     [rbp+60h+var_40], rax
0x18000beca  mov     r15, rdx
0x18000becd  mov     r14, rcx
0x18000bed0  xor     r13d, r13d
0x18000bed3  mov     esi, r13d
0x18000bed6  lea     rax, [rsp+160h+var_E8]
0x18000bedb  mov     [rsp+160h+var_F8], rax
0x18000bee0  mov     [rsp+160h+var_F0], 21h ; '!'
0x18000bee9  mov     [rsp+160h+var_E8], r13w
0x18000beef  lea     r12, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18000bef6  mov     [rsp+160h+var_100], r12
0x18000befb  mov     ecx, [rcx+88h]
0x18000bf01  sub     ecx, 1Fh
0x18000bf04  jz      loc_18000C0C4
0x18000bf0a  sub     ecx, 1
0x18000bf0d  jz      loc_18000C0C4
0x18000bf13  sub     ecx, 1
0x18000bf16  jz      loc_18000C3EA
0x18000bf1c  sub     ecx, 1
0x18000bf1f  jz      loc_18000C381
0x18000bf25  sub     ecx, 1
0x18000bf28  jz      loc_18000C3A5
0x18000bf2e  sub     ecx, 1Ah
0x18000bf31  jnz     loc_18000C0AB
0x18000bf37  lea     edx, [rcx+1]; int
0x18000bf3a  mov     rcx, [r14+18h]; this
0x18000bf3e  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000bf43  mov     [r14+314h], r13d
0x18000bf4a  cmp     [r14+8Ch], r13d
0x18000bf51  jnz     short loc_18000BF91
0x18000bf53  mov     [rsp+160h+var_100], r12
0x18000bf58  lea     rdx, [rsp+160h+var_E8]; wchar_t *
0x18000bf5d  lea     rcx, [rsp+160h+var_100]; this
0x18000bf62  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000bf67  nop
0x18000bf68  mov     eax, esi
0x18000bf6a  mov     rcx, [rbp+60h+var_40]
0x18000bf6e  xor     rcx, rsp; StackCookie
0x18000bf71  call    __security_check_cookie
0x18000bf76  mov     rbx, [rsp+160h+arg_10]
0x18000bf7e  add     rsp, 130h
0x18000bf85  pop     r15
0x18000bf87  pop     r14
0x18000bf89  pop     r13
0x18000bf8b  pop     r12
0x18000bf8d  pop     rdi
0x18000bf8e  pop     rsi
0x18000bf8f  pop     rbp
0x18000bf90  retn
0x18000bf91  lea     rbx, [r14+98h]
0x18000bf98  cmp     [rbx+14h], r13d
0x18000bf9c  jz      loc_18000C1BF
0x18000bfa2  mov     [rsp+160h+Src], r13
0x18000bfa7  mov     [rsp+160h+var_120], r13d
0x18000bfac  mov     rax, [rsp+160h+var_100]
0x18000bfb1  or      edi, 0FFFFFFFFh
0x18000bfb4  mov     r9d, edi
0x18000bfb7  xor     r8d, r8d
0x18000bfba  mov     rdx, [r14+3A0h]
0x18000bfc1  lea     rcx, [rsp+160h+var_100]
0x18000bfc6  mov     rax, [rax+20h]
0x18000bfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfcf  mov     rax, [rsp+160h+var_100]
0x18000bfd4  mov     r9d, edi
0x18000bfd7  mov     r8d, dword ptr [rsp+160h+var_F0+4]
0x18000bfdc  lea     rdx, aDt; ":dt"
0x18000bfe3  lea     rcx, [rsp+160h+var_100]
0x18000bfe8  mov     rax, [rax+20h]
0x18000bfec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff1  lea     r9, [rsp+160h+var_120]; unsigned int *
0x18000bff6  lea     r8, [rsp+160h+Src]; wchar_t **
0x18000bffb  mov     rdx, [rsp+160h+var_F8]; wchar_t *
0x18000c000  mov     rcx, [r14+18h]; this
0x18000c004  call    ?ScanTagBuffer@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI@Z; CHtmlScanner::ScanTagBuffer(wchar_t const *,wchar_t * &,uint &)
0x18000c009  mov     r8d, [rsp+160h+var_120]; unsigned int
0x18000c00e  mov     rdx, [rsp+160h+Src]; wchar_t *
0x18000c013  mov     rcx, r14; this
0x18000c016  call    ?SetTagDataType@CXMLTag@@AEAAXPEB_WI@Z; CXMLTag::SetTagDataType(wchar_t const *,uint)
0x18000c01b  mov     dword ptr [r15+8], 2
0x18000c023  mov     dword ptr [r15+4], 2
0x18000c02b  mov     rax, [r14+8]
0x18000c02f  mov     ecx, [rax+15C0h]
0x18000c035  cmp     ecx, 0FFFFFFFFh
0x18000c038  jnz     loc_18000C138
0x18000c03e  mov     eax, [rax+15C4h]
0x18000c044  mov     [r15+0Ch], eax
0x18000c048  mov     [r15+34h], r13
0x18000c04c  mov     [r15+30h], r13d
0x18000c050  movups  xmm0, xmmword ptr cs:FMTID_UserDefinedProperties.Data1
0x18000c057  movdqu  xmmword ptr [r15+10h], xmm0
0x18000c05d  mov     [r15+20h], r13d
0x18000c061  lea     r8, [r15+28h]; wchar_t **
0x18000c065  mov     rdx, rbx; struct CLMString *
0x18000c068  mov     rcx, r14; this
0x18000c06b  call    ?CreateCustomPropertyNameFromTagName@CXMLTag@@AEAAXAEBVCLMString@@PEAPEA_W@Z; CXMLTag::CreateCustomPropertyNameFromTagName(CLMString const &,wchar_t * *)
0x18000c070  mov     rax, [r14+8]
0x18000c074  inc     dword ptr [rax+60h]
0x18000c077  mov     eax, [rax+60h]
0x18000c07a  mov     [r15], eax
0x18000c07d  mov     [r14+0F8h], r13d
0x18000c084  cmp     dword ptr [r14+38Ch], 3
0x18000c08c  jz      short loc_18000C097
0x18000c08e  mov     rcx, [r14+18h]; this
0x18000c092  call    ?EatText@CHtmlScanner@@QEAAXXZ; CHtmlScanner::EatText(void)
0x18000c097  mov     esi, r13d
0x18000c09a  cmp     dword ptr [r14+38Ch], 3
0x18000c0a2  setz    sil
0x18000c0a6  jmp     loc_18000BF53
0x18000c0ab  sub     ecx, 1
0x18000c0ae  jnz     loc_18000C1CD
0x18000c0b4  xor     edx, edx; int
0x18000c0b6  mov     rcx, [r14+18h]; this
0x18000c0ba  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000c0bf  jmp     loc_18000BF53
0x18000c0c4  mov     edx, 1; int
0x18000c0c9  mov     rcx, [r14+18h]; this
0x18000c0cd  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000c0d2  cmp     [r14+8Ch], r13d
0x18000c0d9  jz      loc_18000BF53
0x18000c0df  mov     [rsp+160h+Src], r13
0x18000c0e4  mov     [rsp+160h+var_120], r13d
0x18000c0e9  mov     [rsp+160h+var_108], r13
0x18000c0ee  mov     [rsp+160h+var_110], r13d
0x18000c0f3  mov     r12d, r13d
0x18000c0f6  mov     [rsp+160h+var_130], r13d; int
0x18000c0fb  lea     rax, [rsp+160h+var_110]
0x18000c100  mov     [rsp+160h+var_138], rax; unsigned int *
0x18000c105  lea     rax, [rsp+160h+var_108]
0x18000c10a  mov     [rsp+160h+var_140], rax; wchar_t **
0x18000c10f  lea     r9, [rsp+160h+var_120]; unsigned int *
0x18000c114  lea     r8, [rsp+160h+Src]; wchar_t **
0x18000c119  mov     rcx, [r14+18h]; this
0x18000c11d  call    ?ScanTagBufferEx@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI12H@Z; CHtmlScanner::ScanTagBufferEx(wchar_t const *,wchar_t * &,uint &,wchar_t * &,uint &,int)
0x18000c122  mov     rbx, [rsp+160h+Src]
0x18000c127  test    rbx, rbx
0x18000c12a  jnz     short loc_18000C158
0x18000c12c  lea     r12, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18000c133  jmp     loc_18000BF53
0x18000c138  cmp     [rax+15D0h], r13d
0x18000c13f  jz      loc_18000C03E
0x18000c145  mov     rax, [rax+15C8h]
0x18000c14c  mov     rcx, [rax+rcx*8]
0x18000c150  mov     eax, [rcx+0Ch]
0x18000c153  jmp     loc_18000C044
0x18000c158  mov     eax, [rsp+160h+var_120]
0x18000c15c  test    eax, eax
0x18000c15e  jz      short loc_18000C1B2
0x18000c160  mov     edi, eax
0x18000c162  mov     r8d, eax
0x18000c165  mov     rdx, rbx
0x18000c168  lea     rcx, aUrnSchemasMicr; "urn:schemas-microsoft-com:office:office"
0x18000c16f  call    cs:__imp__o__wcsnicmp
0x18000c175  mov     r15d, [rsp+160h+var_110]
0x18000c17a  test    eax, eax
0x18000c17c  jnz     short loc_18000C197
0x18000c17e  mov     byte ptr [r14+388h], 1
0x18000c186  mov     r8d, r15d; unsigned int
0x18000c189  mov     rdx, [rsp+160h+var_108]; wchar_t *
0x18000c18e  mov     rcx, [r14+18h]; this
0x18000c192  call    ?SetOffice9PropPrefix@CHtmlScanner@@QEAAXPEB_WI@Z; CHtmlScanner::SetOffice9PropPrefix(wchar_t const *,uint)
0x18000c197  mov     r8, rdi
0x18000c19a  mov     rdx, rbx
0x18000c19d  lea     rcx, aUuidC2f4101065; "uuid:C2F41010-65B3-11d1-A29F-00AA00C148"...
0x18000c1a4  call    cs:__imp__o__wcsnicmp
0x18000c1aa  test    eax, eax
0x18000c1ac  jz      loc_18000C4F0
0x18000c1b2  inc     r12d
0x18000c1b5  mov     [rsp+160h+var_130], r12d
0x18000c1ba  jmp     loc_18000C0FB
0x18000c1bf  mov     rcx, [r14+18h]; this
0x18000c1c3  call    ?EatText@CHtmlScanner@@QEAAXXZ; CHtmlScanner::EatText(void)
0x18000c1c8  jmp     loc_18000BF53
0x18000c1cd  cmp     ecx, 1
0x18000c1d0  jz      short loc_18000C209
0x18000c1d2  mov     rcx, r14; this
0x18000c1d5  call    ?InitStatChunk@CPropertyTag@@UEAAHPEAUtagSTAT_CHUNK@@@Z; CPropertyTag::InitStatChunk(tagSTAT_CHUNK *)
0x18000c1da  mov     ebx, eax
0x18000c1dc  mov     [r14+0F8h], r13d
0x18000c1e3  cmp     dword ptr [r14+38Ch], 1
0x18000c1eb  jz      short loc_18000C1F6
0x18000c1ed  mov     rcx, [r14+18h]; this
0x18000c1f1  call    ?EatText@CHtmlScanner@@QEAAXXZ; CHtmlScanner::EatText(void)
0x18000c1f6  mov     esi, r13d
0x18000c1f9  cmp     dword ptr [r14+38Ch], 1
0x18000c201  cmovz   esi, ebx
0x18000c204  jmp     loc_18000BF53
0x18000c209  mov     edx, 1; int
0x18000c20e  mov     rcx, [r14+18h]; this
0x18000c212  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000c217  mov     [r14+314h], r13d
0x18000c21e  cmp     [r14+8Ch], r13d
0x18000c225  jz      loc_18000BF53
0x18000c22b  mov     rcx, [r14+18h]; this
0x18000c22f  call    ?UnGetEndTag@CHtmlScanner@@QEAAXXZ; CHtmlScanner::UnGetEndTag(void)
0x18000c234  mov     [rsp+160h+Src], r13
0x18000c239  mov     [rsp+160h+var_120], r13d
0x18000c23e  lea     r9, [rsp+160h+var_120]; unsigned int *
0x18000c243  lea     r8, [rsp+160h+Src]; wchar_t **
0x18000c248  lea     rdx, aHref; "href"
0x18000c24f  mov     rcx, [r14+18h]; this
0x18000c253  call    ?ScanTagBuffer@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI@Z; CHtmlScanner::ScanTagBuffer(wchar_t const *,wchar_t * &,uint &)
0x18000c258  lea     rsi, [r14+3F8h]
0x18000c25f  mov     edi, [rsp+160h+var_120]
0x18000c263  mov     ebx, edi
0x18000c265  add     rbx, rbx
0x18000c268  lea     edx, [rdi+1]; int
0x18000c26b  mov     rcx, rsi; this
0x18000c26e  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18000c273  mov     rcx, rax; void *
0x18000c276  mov     r8, rbx; Size
0x18000c279  mov     rdx, [rsp+160h+Src]; Src
0x18000c27e  call    memcpy_0
0x18000c283  mov     edx, edi; unsigned int
0x18000c285  mov     rcx, rsi; this
0x18000c288  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x18000c28d  mov     dword ptr [r14+390h], 8
0x18000c298  mov     dword ptr [r15+8], 2
0x18000c2a0  mov     dword ptr [r15+4], 2
0x18000c2a8  mov     [r15+0Ch], r13d
0x18000c2ac  mov     [r15+34h], r13
0x18000c2b0  mov     [r15+30h], r13d
0x18000c2b4  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000c2bb  mov     [rbp+60h+var_A0], rax
0x18000c2bf  lea     rax, [rbp+60h+var_88]
0x18000c2c3  mov     [rbp+60h+var_98], rax
0x18000c2c7  mov     [rbp+60h+var_90], 21h ; '!'
0x18000c2ce  lea     rdx, aLinkOfficechil; "LINK.OFFICECHILD"
0x18000c2d5  lea     rcx, [rbp+60h+var_A0]; this
0x18000c2d9  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x18000c2de  mov     [rbp+60h+var_A0], r12
0x18000c2e2  movups  xmm0, cs:xmmword_18002C830
0x18000c2e9  movdqu  xmmword ptr [r15+10h], xmm0
0x18000c2ef  mov     [r15+20h], r13d
0x18000c2f3  mov     ecx, [rbp+60h+var_8C]
0x18000c2f6  inc     ecx
0x18000c2f8  add     rcx, rcx; cb
0x18000c2fb  call    cs:__imp_CoTaskMemAlloc
0x18000c301  mov     rcx, rax; void *
0x18000c304  mov     [r15+28h], rax
0x18000c308  test    rax, rax
0x18000c30b  jz      short loc_18000C365
0x18000c30d  mov     r8d, [rbp+60h+var_8C]
0x18000c311  inc     r8d
0x18000c314  add     r8, r8; Size
0x18000c317  mov     rdx, [rbp+60h+var_98]; Src
0x18000c31b  call    memcpy_0
0x18000c320  mov     rax, [r14+8]
0x18000c324  inc     dword ptr [rax+60h]
0x18000c327  mov     eax, [rax+60h]
0x18000c32a  mov     [r15], eax
0x18000c32d  mov     [r14+0F8h], r13d
0x18000c334  cmp     [r14+388h], r13b
0x18000c33b  jnz     short loc_18000C346
0x18000c33d  mov     rcx, [r14+18h]; this
0x18000c341  call    ?EatText@CHtmlScanner@@QEAAXXZ; CHtmlScanner::EatText(void)
0x18000c346  movzx   esi, byte ptr [r14+388h]
0x18000c34e  mov     [rbp+60h+var_A0], r12
0x18000c352  lea     rdx, [rbp+60h+var_88]; wchar_t *
0x18000c356  lea     rcx, [rbp+60h+var_A0]; this
0x18000c35a  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000c35f  nop
0x18000c360  jmp     loc_18000BF53
0x18000c365  mov     rcx, [rbp+68h]; this
0x18000c369  mov     r9d, 8007000Eh; char *
0x18000c36f  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000c376  mov     edx, 1DFh; void *
0x18000c37b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c381  mov     ecx, [r14+8Ch]
0x18000c388  cmp     [r14+388h], r13b
0x18000c38f  jz      short loc_18000C3E1
0x18000c391  mov     eax, r13d
0x18000c394  test    ecx, ecx
0x18000c396  setnz   al
0x18000c399  mov     [r14+38Ch], eax
0x18000c3a0  jmp     loc_18000C0B4
0x18000c3a5  cmp     [r14+388h], r13b
0x18000c3ac  jz      short loc_18000C3C7
0x18000c3ae  cmp     [r14+389h], r13b
0x18000c3b5  jz      short loc_18000C3C7
0x18000c3b7  mov     eax, [r14+8Ch]
0x18000c3be  neg     eax
0x18000c3c0  sbb     ecx, ecx
0x18000c3c2  and     ecx, 3
0x18000c3c5  jmp     short loc_18000C3D5
0x18000c3c7  mov     eax, [r14+8Ch]
0x18000c3ce  neg     eax
0x18000c3d0  sbb     ecx, ecx
0x18000c3d2  and     ecx, 4
  ... truncated ...
```
