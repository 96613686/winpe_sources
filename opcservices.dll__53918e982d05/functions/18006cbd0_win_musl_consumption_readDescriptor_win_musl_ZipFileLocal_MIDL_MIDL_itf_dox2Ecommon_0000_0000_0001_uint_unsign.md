# win_musl::consumption::readDescriptor(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,uint,unsigned __int64,unsigned __int64,uint *,uint *)

- ea: `0x18006cbd0`
- end: `0x18006d008`
- name: `?readDescriptor@consumption@win_musl@@YA?AW4type_t@ZipHeaderResult@12@PEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@I_K2PEAI3@Z`
- size: `1080`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006c4a0`

## callees

- `0x18002db70`
- `0x18006cbd0`
- `0x18006d010`
- `0x18006d160`
- `0x1800cd6fc`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006cc89`
- `msvcrt!memmove_s` at `0x18006cc89`

## string_xrefs

- `0x18006cf49`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x18006cfd8`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x18006cf85`: `win_musl::detail::vector_read`
- `0x18006cf3a`: `win_musl::consumption::readDescriptor`
- `0x18006cfc9`: `win_musl::consumption::readDescriptor`

## pseudocode

```c
__int64 __fastcall win_musl::consumption::readDescriptor(
        _QWORD *a1,
        unsigned int *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        _DWORD *a7)
{
  __int64 v7; // r15
  __int64 v8; // r12
  _QWORD *v9; // r8
  _DWORD *v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  char v13; // dl
  char *v14; // rcx
  int v15; // ecx
  __int64 result; // rax
  unsigned int v17; // ecx
  bool v18; // cf
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rsi
  __int64 v22; // rax
  _QWORD *v23; // rdx
  char *v24; // rsi
  unsigned int v25; // eax
  unsigned int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r8
  _QWORD *v30; // rdx
  _BYTE v31[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  int Destination; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  _BYTE pExceptionObject[160]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = *a2;
  v8 = a3;
  v9 = a1;
  *a6 = 8;
  v37 = a4;
  v34 = a1;
  if ( (unsigned int)v7 < 8 )
    goto LABEL_24;
  v10 = (_DWORD *)*((_QWORD *)a2 + 1);
  if ( *v10 == 134695760 )
  {
    if ( !v10 || (v12 = (unsigned __int64)(v10 + 1), v24 = (char *)v10 + v7, (_DWORD *)((char *)v10 + v7) == v10 + 1) )
    {
      v13 = 1;
      v11 = 0;
      DWORD1(v32) = 0;
      v12 = 0;
    }
    else
    {
      if ( (unsigned __int64)v10 > v12 || v12 > (unsigned __int64)v24 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x16Du,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expres"
                                                  "sion (cursor + sizeof(uint32_t))");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v11 = (unsigned int)((_DWORD)v24 - v12);
      DWORD1(v32) = 0;
      v13 = 1;
    }
  }
  else
  {
    if ( !v10 || (_DWORD *)((char *)v10 + v7) == v10 )
    {
      v11 = 0;
      DWORD1(v32) = 0;
      v12 = 0;
    }
    else
    {
      if ( (_DWORD *)((char *)v10 + v7) < v10 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x172u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expression (cursor)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v11 = (unsigned int)v7;
      DWORD1(v32) = 0;
      v12 = (unsigned __int64)v10;
    }
    v13 = 0;
  }
  v31[0] = v13;
  if ( (unsigned int)v11 < 4 )
  {
    v15 = 0;
  }
  else
  {
    Destination = 0;
    memmove_s(&Destination, 4u, (const void *const)v12, 4u);
    if ( v12 )
    {
      v14 = (char *)(v12 + 4);
      v11 += v12;
      if ( v11 == v12 + 4 )
      {
        LODWORD(v11) = 0;
        v12 = 0;
      }
      else
      {
        if ( v12 > (unsigned __int64)v14 || (unsigned __int64)v14 > v11 )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)pExceptionObject,
            0xABu,
            0x80070057,
            (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expr"
                                                    "ession (vector_begin(vector) + sizeof(T))");
          throw (SplException::THResultException *)pExceptionObject;
        }
        LODWORD(v11) = v11 - (_DWORD)v14;
        v12 += 4LL;
      }
    }
    else
    {
      LODWORD(v11) = 0;
      v12 = 0;
    }
    v15 = Destination;
    v13 = v31[0];
    v9 = v34;
    DWORD1(v32) = 0;
  }
  if ( v15 != (_DWORD)v8 )
    goto LABEL_16;
  v17 = 12;
  *a6 = 12;
  if ( v13 )
  {
    v17 = 16;
    *a6 = 16;
  }
  if ( (unsigned int)v7 < v17 )
  {
LABEL_24:
    result = 2;
    goto LABEL_17;
  }
  v18 = *((_BYTE *)v9 + 204) < 0x2Du;
  *(_QWORD *)&v32 = (unsigned int)v11;
  *((_QWORD *)&v32 + 1) = v12;
  if ( v18 )
  {
    *(_QWORD *)&v35 = (unsigned int)v11;
    *((_QWORD *)&v35 + 1) = v12;
    v36 = v35;
    v31[0] = 0;
    v25 = win_musl::detail::vector_read<unsigned int>(&v36, &v35, v31);
    v36 = v35;
    v26 = v25;
    v27 = win_musl::detail::vector_read<unsigned int>(&v36, &v35, v31);
    v28 = v26;
    v19 = v37;
    if ( v28 == v37 )
    {
      v29 = v27;
      if ( v27 == a5 )
      {
        v30 = v34;
        *a7 = v7 - v35;
        v30[21] = 4;
        v30[24] = (v8 << 32) | 4;
        result = 0;
        v30[22] = v28;
        v30[19] = 4;
        v30[20] = v29;
        return result;
      }
    }
  }
  else
  {
    v19 = v37;
  }
  *a6 += 8;
  if ( (unsigned int)v7 < *a6 )
    goto LABEL_24;
  v36 = v32;
  v31[0] = 0;
  v20 = win_musl::detail::vector_read<unsigned __int64>(&v36, &v32, v31);
  v36 = v32;
  v21 = v20;
  v22 = win_musl::detail::vector_read<unsigned __int64>(&v36, &v32, v31);
  if ( v21 != v19 || v22 != a5 )
  {
LABEL_16:
    result = 1;
LABEL_17:
    *a7 = 0;
    return result;
  }
  v23 = v34;
  *a7 = v7 - v32;
  v23[20] = v22;
  v23[24] = (v8 << 32) | 4;
  result = 0;
  v23[21] = 4;
  v23[22] = v21;
  v23[19] = 4;
  return result;
}

```

## disassembly

```asm
0x18006cbd0  push    rbp
0x18006cbd2  push    rbx
0x18006cbd3  push    rsi
0x18006cbd4  push    rdi
0x18006cbd5  push    r12
0x18006cbd7  push    r13
0x18006cbd9  push    r14
0x18006cbdb  push    r15
0x18006cbdd  lea     rbp, [rsp-58h]
0x18006cbe2  sub     rsp, 158h
0x18006cbe9  mov     rax, cs:__security_cookie
0x18006cbf0  xor     rax, rsp
0x18006cbf3  mov     [rbp+90h+var_50], rax
0x18006cbf7  mov     r14, [rbp+90h+arg_28]
0x18006cbfe  mov     r15d, [rdx]
0x18006cc01  mov     r13, [rbp+90h+arg_30]
0x18006cc08  mov     r12d, r8d
0x18006cc0b  mov     r8, rcx
0x18006cc0e  mov     dword ptr [r14], 8
0x18006cc15  mov     [rbp+90h+var_100], r9
0x18006cc19  mov     [rsp+190h+var_128], rcx
0x18006cc1e  cmp     r15d, 8
0x18006cc22  jb      loc_18006D001
0x18006cc28  mov     rax, [rdx+8]
0x18006cc2c  mov     edx, cs:dword_18013AE68
0x18006cc32  cmp     edx, [rax]
0x18006cc34  jz      loc_18006CE09
0x18006cc3a  test    rax, rax
0x18006cc3d  jz      loc_18006CD4B
0x18006cc43  lea     rsi, [rax+r15]
0x18006cc47  cmp     rsi, rax
0x18006cc4a  jz      loc_18006CD4B
0x18006cc50  jb      loc_18006CFBD
0x18006cc56  sub     esi, eax
0x18006cc58  xor     ecx, ecx
0x18006cc5a  xor     edi, edi
0x18006cc5c  mov     dword ptr [rsp+190h+var_140+4], ecx
0x18006cc60  mov     rbx, rax
0x18006cc63  mov     eax, edi
0x18006cc65  xor     dl, dl
0x18006cc67  mov     [rsp+190h+var_150], dl
0x18006cc6b  cmp     esi, 4
0x18006cc6e  jb      loc_18006CF72
0x18006cc74  mov     r9d, 4; SourceSize
0x18006cc7a  mov     [rsp+190h+Destination], edi
0x18006cc7e  mov     edx, r9d; DestinationSize
0x18006cc81  lea     rcx, [rsp+190h+Destination]; Destination
0x18006cc86  mov     r8, rbx; Source
0x18006cc89  call    cs:__imp_memmove_s
0x18006cc8f  test    rbx, rbx
0x18006cc92  jz      loc_18006CD5C
0x18006cc98  lea     rcx, [rbx+4]
0x18006cc9c  add     rsi, rbx
0x18006cc9f  cmp     rsi, rcx
0x18006cca2  jz      loc_18006CE46
0x18006cca8  cmp     rbx, rcx
0x18006ccab  ja      loc_18006CF79
0x18006ccb1  cmp     rcx, rsi
0x18006ccb4  ja      loc_18006CF79
0x18006ccba  sub     esi, ecx
0x18006ccbc  mov     rbx, rcx
0x18006ccbf  mov     ecx, [rsp+190h+Destination]
0x18006ccc3  xor     eax, eax
0x18006ccc5  movzx   edx, [rsp+190h+var_150]
0x18006ccca  mov     r8, [rsp+190h+var_128]
0x18006cccf  mov     dword ptr [rsp+190h+var_140+4], eax
0x18006ccd3  mov     eax, edi
0x18006ccd5  cmp     ecx, r12d
0x18006ccd8  jz      short loc_18006CD03
0x18006ccda  mov     eax, 1
0x18006ccdf  mov     [r13+0], edi
0x18006cce3  mov     rcx, [rbp+90h+var_50]
0x18006cce7  xor     rcx, rsp; StackCookie
0x18006ccea  call    __security_check_cookie
0x18006ccef  add     rsp, 158h
0x18006ccf6  pop     r15
0x18006ccf8  pop     r14
0x18006ccfa  pop     r13
0x18006ccfc  pop     r12
0x18006ccfe  pop     rdi
0x18006ccff  pop     rsi
0x18006cd00  pop     rbx
0x18006cd01  pop     rbp
0x18006cd02  retn
0x18006cd03  mov     ecx, 0Ch
0x18006cd08  mov     [r14], ecx
0x18006cd0b  test    dl, dl
0x18006cd0d  jz      short loc_18006CD17
0x18006cd0f  mov     ecx, 10h
0x18006cd14  mov     [r14], ecx
0x18006cd17  cmp     r15d, ecx
0x18006cd1a  jb      short loc_18006CD44
0x18006cd1c  cmp     byte ptr [r8+0CCh], 2Dh ; '-'
0x18006cd24  mov     dword ptr [rsp+190h+var_140], esi
0x18006cd28  mov     dword ptr [rsp+190h+var_140+4], eax
0x18006cd2c  mov     qword ptr [rsp+190h+var_140+8], rbx
0x18006cd31  jb      loc_18006CE50
0x18006cd37  mov     rbx, [rbp+90h+var_100]
0x18006cd3b  add     dword ptr [r14], 8
0x18006cd3f  cmp     r15d, [r14]
0x18006cd42  jnb     short loc_18006CD66
0x18006cd44  mov     eax, 2
0x18006cd49  jmp     short loc_18006CCDF
0x18006cd4b  xor     edi, edi
0x18006cd4d  xor     eax, eax
0x18006cd4f  mov     esi, edi
0x18006cd51  mov     dword ptr [rsp+190h+var_140+4], eax
0x18006cd55  mov     ebx, edi
0x18006cd57  jmp     loc_18006CC65
0x18006cd5c  mov     esi, edi
0x18006cd5e  mov     rbx, rdi
0x18006cd61  jmp     loc_18006CCBF
0x18006cd66  movaps  xmm0, [rsp+190h+var_140]
0x18006cd6b  lea     r8, [rsp+190h+var_150]
0x18006cd70  lea     rdx, [rsp+190h+var_140]
0x18006cd75  movdqa  [rbp+90h+var_110], xmm0
0x18006cd7a  lea     rcx, [rbp+90h+var_110]
0x18006cd7e  mov     [rsp+190h+var_150], 0
0x18006cd83  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006cd88  movaps  xmm0, [rsp+190h+var_140]
0x18006cd8d  lea     r8, [rsp+190h+var_150]
0x18006cd92  lea     rdx, [rsp+190h+var_140]
0x18006cd97  movdqa  [rbp+90h+var_110], xmm0
0x18006cd9c  lea     rcx, [rbp+90h+var_110]
0x18006cda0  mov     rsi, rax
0x18006cda3  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006cda8  cmp     rsi, rbx
0x18006cdab  jnz     loc_18006CCDA
0x18006cdb1  cmp     rax, [rbp+90h+arg_20]
0x18006cdb8  jnz     loc_18006CCDA
0x18006cdbe  mov     rdx, [rsp+190h+var_128]
0x18006cdc3  mov     rcx, r12
0x18006cdc6  sub     r15d, dword ptr [rsp+190h+var_140]
0x18006cdcb  mov     [r13+0], r15d
0x18006cdcf  shl     rcx, 20h
0x18006cdd3  or      rcx, 4
0x18006cdd7  mov     [rdx+0A0h], rax
0x18006cdde  mov     [rdx+0C0h], rcx
0x18006cde5  xor     eax, eax
0x18006cde7  mov     qword ptr [rdx+0A8h], 4
0x18006cdf2  mov     [rdx+0B0h], rsi
0x18006cdf9  mov     qword ptr [rdx+98h], 4
0x18006ce04  jmp     loc_18006CCE3
0x18006ce09  test    rax, rax
0x18006ce0c  jz      loc_18006CF08
0x18006ce12  lea     rbx, [rax+4]
0x18006ce16  lea     rsi, [rax+r15]
0x18006ce1a  cmp     rsi, rbx
0x18006ce1d  jz      loc_18006CF1B
0x18006ce23  cmp     rax, rbx
0x18006ce26  ja      loc_18006CF2E
0x18006ce2c  cmp     rbx, rsi
0x18006ce2f  ja      loc_18006CF2E
0x18006ce35  xor     eax, eax
0x18006ce37  sub     esi, ebx
0x18006ce39  xor     edi, edi
0x18006ce3b  mov     dword ptr [rsp+190h+var_140+4], eax
0x18006ce3f  mov     dl, 1
0x18006ce41  jmp     loc_18006CC67
0x18006ce46  mov     esi, edi
0x18006ce48  mov     rbx, rdi
0x18006ce4b  jmp     loc_18006CCBF
0x18006ce50  mov     dword ptr [rsp+190h+var_120], esi
0x18006ce54  lea     r8, [rsp+190h+var_150]
0x18006ce59  mov     dword ptr [rsp+190h+var_120+4], eax
0x18006ce5d  lea     rdx, [rsp+190h+var_120]
0x18006ce62  mov     qword ptr [rsp+190h+var_120+8], rbx
0x18006ce67  lea     rcx, [rbp+90h+var_110]
0x18006ce6b  movaps  xmm0, [rsp+190h+var_120]
0x18006ce70  movdqa  [rbp+90h+var_110], xmm0
0x18006ce75  mov     [rsp+190h+var_150], 0
0x18006ce7a  call    ??$vector_read@I@detail@win_musl@@YAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<uint>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006ce7f  movaps  xmm0, [rsp+190h+var_120]
0x18006ce84  lea     r8, [rsp+190h+var_150]
0x18006ce89  lea     rdx, [rsp+190h+var_120]
0x18006ce8e  movdqa  [rbp+90h+var_110], xmm0
0x18006ce93  lea     rcx, [rbp+90h+var_110]
0x18006ce97  mov     ebx, eax
0x18006ce99  call    ??$vector_read@I@detail@win_musl@@YAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<uint>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006ce9e  mov     ecx, ebx
0x18006cea0  mov     rbx, [rbp+90h+var_100]
0x18006cea4  cmp     rcx, rbx
0x18006cea7  jnz     loc_18006CD3B
0x18006cead  mov     r8d, eax
0x18006ceb0  cmp     r8, [rbp+90h+arg_20]
0x18006ceb7  jnz     loc_18006CD3B
0x18006cebd  mov     rdx, [rsp+190h+var_128]
0x18006cec2  mov     rax, r12
0x18006cec5  sub     r15d, dword ptr [rsp+190h+var_120]
0x18006ceca  mov     [r13+0], r15d
0x18006cece  shl     rax, 20h
0x18006ced2  or      rax, 4
0x18006ced6  mov     qword ptr [rdx+0A8h], 4
0x18006cee1  mov     [rdx+0C0h], rax
0x18006cee8  xor     eax, eax
0x18006ceea  mov     [rdx+0B0h], rcx
0x18006cef1  mov     qword ptr [rdx+98h], 4
0x18006cefc  mov     [rdx+0A0h], r8
0x18006cf03  jmp     loc_18006CCE3
0x18006cf08  xor     edi, edi
0x18006cf0a  mov     dl, 1
0x18006cf0c  xor     eax, eax
0x18006cf0e  mov     esi, edi
0x18006cf10  mov     dword ptr [rsp+190h+var_140+4], eax
0x18006cf14  mov     ebx, edi
0x18006cf16  jmp     loc_18006CC67
0x18006cf1b  xor     edi, edi
0x18006cf1d  mov     dl, 1
0x18006cf1f  xor     eax, eax
0x18006cf21  mov     esi, edi
0x18006cf23  mov     dword ptr [rsp+190h+var_140+4], eax
0x18006cf27  mov     ebx, edi
0x18006cf29  jmp     loc_18006CC67
0x18006cf2e  lea     rax, aNewBeginIsOutO; "new_begin is out-of-range: vector expre"...
0x18006cf35  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x18006cf3a  lea     r9, aWinMuslConsump_0; "win_musl::consumption::readDescriptor"
0x18006cf41  mov     [rsp+190h+var_168], 80070057h; unsigned int
0x18006cf49  lea     r8, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006cf50  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18006cf54  mov     [rsp+190h+var_170], 16Dh; unsigned int
0x18006cf5c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006cf61  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006cf68  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18006cf6c  call    _CxxThrowException_0
0x18006cf72  mov     ecx, edi
0x18006cf74  jmp     loc_18006CCD5
0x18006cf79  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18006cf80  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x18006cf85  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18006cf8c  mov     [rsp+190h+var_168], 80070057h; unsigned int
0x18006cf94  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18006cf9b  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18006cf9f  mov     [rsp+190h+var_170], 0ABh; unsigned int
0x18006cfa7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006cfac  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006cfb3  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18006cfb7  call    _CxxThrowException_0
0x18006cfbd  lea     rax, aNewBeginIsOutO_9; "new_begin is out-of-range: vector expre"...
0x18006cfc4  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x18006cfc9  lea     r9, aWinMuslConsump_0; "win_musl::consumption::readDescriptor"
0x18006cfd0  mov     [rsp+190h+var_168], 80070057h; unsigned int
0x18006cfd8  lea     r8, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006cfdf  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18006cfe3  mov     [rsp+190h+var_170], 172h; unsigned int
0x18006cfeb  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006cff0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006cff7  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18006cffb  call    _CxxThrowException_0
0x18006d001  xor     edi, edi
0x18006d003  jmp     loc_18006CD44
```
