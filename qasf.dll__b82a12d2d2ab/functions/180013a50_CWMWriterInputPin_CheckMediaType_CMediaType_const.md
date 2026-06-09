# CWMWriterInputPin::CheckMediaType(CMediaType const *)

- ea: `0x180013a50`
- end: `0x180013ecf`
- name: `?CheckMediaType@CWMWriterInputPin@@UEAAJPEBVCMediaType@@@Z`
- size: `1151`
- prototype: `int(CWMWriterInputPin *__hidden this, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001460`
- `0x1800071e8`
- `0x180007294`
- `0x180007300`
- `0x180013178`
- `0x180013278`
- `0x180013a50`
- `0x18001404c`
- `0x18001452c`
- `0x1800146a0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::CheckMediaType(CWMWriterInputPin *this, const struct CMediaType *a2)
{
  __int64 result; // rax
  int v5; // ebx
  __int64 v6; // r8
  unsigned int v7; // r15d
  const struct CMediaType *v8; // rsi
  __int64 v9; // rcx
  int v10; // eax
  int v11; // r13d
  __int64 v12; // rax
  const struct tWAVEFORMATEX **v13; // rbp
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned __int16 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int16 v19; // r9
  __int64 v20; // r11
  __int64 v21; // r10
  const struct _AMMediaType *v22; // rcx
  struct tagBITMAPINFOHEADER *v23; // rax
  __int64 v24; // r9
  struct tagBITMAPINFOHEADER *v25; // rax
  __int64 v26; // r9
  struct tagBITMAPINFOHEADER *v27; // rax
  _DWORD *v28; // r9
  struct tagBITMAPINFOHEADER *v29; // rax
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // rcx
  const struct tWAVEFORMATEX *v34; // rdx
  int v35; // edx
  BOOL v36; // [rsp+30h] [rbp-58h]
  unsigned __int64 v37; // [rsp+38h] [rbp-50h] BYREF

  *((_DWORD *)this + 114) = 0;
  if ( *(_OWORD *)&FORMAT_VideoInfo == *(_OWORD *)((char *)a2 + 44) )
  {
    result = CheckVideoInfoType((__int64)a2);
  }
  else
  {
    v5 = 0;
    if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 != *(_QWORD *)((char *)a2 + 44)
      || *(_QWORD *)FORMAT_VideoInfo2.Data4 != *(_QWORD *)((char *)a2 + 52) )
    {
      goto LABEL_4;
    }
    result = CheckVideoInfo2Type((__int64)a2);
  }
  v5 = result;
  if ( (int)result < 0 )
    return result;
LABEL_4:
  v6 = *(_QWORD *)&MEDIATYPE_Video.Data1;
  v7 = -2147220950;
  v8 = a2;
  v9 = *(_QWORD *)MEDIATYPE_Video.Data4;
  v36 = 0;
  v37 = (unsigned __int64)a2;
  if ( *(_QWORD *)&MEDIATYPE_Video.Data1 == *(_QWORD *)a2
    && *(_QWORD *)MEDIATYPE_Video.Data4 == *((_QWORD *)a2 + 1)
    && *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)((char *)a2 + 44)
    && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)((char *)a2 + 52) )
  {
    v10 = MediaTypeCreateVIHFromVIH2(&v37, (__int128 *)a2);
    v8 = (const struct CMediaType *)v37;
    v5 = v10;
    v9 = *(_QWORD *)MEDIATYPE_Video.Data4;
    v6 = *(_QWORD *)&MEDIATYPE_Video.Data1;
    v36 = v10 >= 0;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 43) + 232LL) )
  {
    v35 = *((_DWORD *)this + 106);
    if ( v35 == 1
      && *(_QWORD *)&MEDIATYPE_Audio.Data1 == *(_QWORD *)a2
      && *(_QWORD *)MEDIATYPE_Audio.Data4 == *((_QWORD *)a2 + 1)
      || v35 == 2 && v6 == *(_QWORD *)a2 && v9 == *((_QWORD *)a2 + 1) )
    {
      v7 = 0;
    }
  }
  else
  {
    v11 = 0;
    if ( v5 >= 0 )
    {
      while ( v11 < *((_DWORD *)this + 108) )
      {
        v12 = *((_QWORD *)this + 55);
        LODWORD(v37) = 0;
        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64 *))(**(_QWORD **)(v12 + 8LL * v11) + 32LL))(
               *(_QWORD *)(v12 + 8LL * v11),
               0,
               &v37);
        if ( ((v5 + 0x80000000) & 0x80000000) != 0 || v5 == -1072887855 )
        {
          v13 = (const struct tWAVEFORMATEX **)operator new[]((unsigned int)v37);
          if ( !v13 )
            return 2147942414LL;
          v14 = *(_QWORD *)(*((_QWORD *)this + 55) + 8LL * v11);
          v5 = (*(__int64 (__fastcall **)(__int64, const struct tWAVEFORMATEX **, unsigned __int64 *))(*(_QWORD *)v14 + 32LL))(
                 v14,
                 v13,
                 &v37);
          if ( v5 >= 0
            && *(const struct tWAVEFORMATEX **)a2 == *v13
            && *((const struct tWAVEFORMATEX **)a2 + 1) == v13[1] )
          {
            if ( !v11 )
            {
              if ( (unsigned int)CWMWriterInputPin::IsFormatStructureWAVEFORMATEX((const struct _AMMediaType *)v8) )
              {
                if ( (unsigned int)CWMWriterInputPin::IsFormatStructureWAVEFORMATEX((const struct _AMMediaType *)v13) )
                {
                  if ( FormatTagFromWfx(*((const struct tWAVEFORMATEX **)v8 + 10)) == 1 )
                  {
                    v16 = *(_WORD *)(v15 + 2);
                    if ( (v16 > 2u || v16 == 2 && *(_WORD *)(v15 + 14) > 0x10u)
                      && FormatTagFromWfx(v13[10]) != 1
                      && *(_WORD *)(v17 + 2) == v19
                      && *(_DWORD *)(v17 + 4) == *(_DWORD *)(v18 + 4)
                      && *(_WORD *)(v17 + 14) == *(_WORD *)(v18 + 14) )
                    {
                      v7 = 0;
                      *((_DWORD *)this + 114) = 0;
                      goto LABEL_64;
                    }
                  }
                }
              }
            }
            if ( (unsigned int)IsAmTypeEqualWmType((struct _AMMediaType *)v8, (struct _WMMediaType *)v13) )
            {
              if ( v11 || !*((_QWORD *)this + 56) )
                goto LABEL_63;
              v20 = *(_QWORD *)&MEDIATYPE_Video.Data1;
              v21 = *(_QWORD *)MEDIATYPE_Video.Data4;
              if ( *(_QWORD *)v8 == *(_QWORD *)&MEDIATYPE_Video.Data1
                && *((_QWORD *)v8 + 1) == *(_QWORD *)MEDIATYPE_Video.Data4 )
              {
                if ( GetbmiHeader((const struct _AMMediaType *)v13) )
                {
                  if ( GetbmiHeader((const struct _AMMediaType *)v8) )
                  {
                    if ( GetbmiHeader((const struct _AMMediaType *)v13)->biCompression )
                    {
                      GetbmiHeader(v22);
                      v23 = GetbmiHeader((const struct _AMMediaType *)v8);
                      if ( v23->biWidth == *(_DWORD *)(v24 + 4) )
                      {
                        GetbmiHeader((const struct _AMMediaType *)v13);
                        v25 = GetbmiHeader((const struct _AMMediaType *)v8);
                        if ( v25->biHeight == *(_DWORD *)(v26 + 8) )
                        {
                          GetbmiHeader((const struct _AMMediaType *)v13);
                          v27 = GetbmiHeader((const struct _AMMediaType *)v8);
                          if ( v27->biSize == *v28 )
                          {
                            GetbmiHeader((const struct _AMMediaType *)v13);
                            v29 = GetbmiHeader((const struct _AMMediaType *)v8);
                            if ( v29->biBitCount == *(_WORD *)(v30 + 14) )
                            {
LABEL_62:
                              *((_DWORD *)this + 114) = 1;
LABEL_63:
                              v7 = 0;
LABEL_64:
                              operator delete(v13);
                              break;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              v31 = *(_QWORD *)&MEDIATYPE_Audio.Data1;
              v32 = *(_QWORD *)MEDIATYPE_Audio.Data4;
              if ( *(_QWORD *)&MEDIATYPE_Audio.Data1 != *(_QWORD *)v8 )
                goto LABEL_58;
              if ( *((_QWORD *)v8 + 1) == *(_QWORD *)MEDIATYPE_Audio.Data4 )
              {
                if ( (unsigned int)CWMWriterInputPin::IsFormatStructureWAVEFORMATEX((const struct _AMMediaType *)v8) )
                {
                  if ( (unsigned int)CWMWriterInputPin::IsFormatStructureWAVEFORMATEX((const struct _AMMediaType *)v13) )
                  {
                    if ( FormatTagFromWfx(*((const struct tWAVEFORMATEX **)v8 + 10)) != 1 )
                    {
                      v34 = v13[10];
                      if ( v34->nChannels == *(_WORD *)(v33 + 2)
                        && v34->nSamplesPerSec == *(_DWORD *)(v33 + 4)
                        && v34->nAvgBytesPerSec == *(_DWORD *)(v33 + 8)
                        && v34->nBlockAlign == *(_WORD *)(v33 + 12)
                        && v34->wBitsPerSample == *(_WORD *)(v33 + 14) )
                      {
                        goto LABEL_62;
                      }
                    }
                  }
                }
              }
              if ( v31 != *(_QWORD *)v8 || v32 != *((_QWORD *)v8 + 1) )
              {
LABEL_58:
                if ( v20 != *(_QWORD *)v8 || v21 != *((_QWORD *)v8 + 1) )
                  goto LABEL_62;
              }
            }
          }
          operator delete(v13);
        }
        if ( v5 < 0 )
          break;
        ++v11;
      }
    }
  }
  if ( v36 )
    DeleteMediaType((struct _AMMediaType *)v8);
  if ( v5 >= 0 )
    return v7;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013a50  mov     [rsp+arg_10], rbx
0x180013a55  push    rbp
0x180013a56  push    rsi
0x180013a57  push    rdi
0x180013a58  push    r12
0x180013a5a  push    r13
0x180013a5c  push    r14
0x180013a5e  push    r15
0x180013a60  sub     rsp, 50h
0x180013a64  mov     rax, cs:__security_cookie
0x180013a6b  xor     rax, rsp
0x180013a6e  mov     [rsp+88h+var_48], rax
0x180013a73  mov     dword ptr [rcx+1C8h], 0
0x180013a7d  mov     rdi, rdx
0x180013a80  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180013a87  mov     r14, rcx
0x180013a8a  mov     rbp, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180013a91  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180013a98  cmp     rax, [rdx+2Ch]
0x180013a9c  jnz     loc_180013C8E
0x180013aa2  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180013aa9  cmp     rax, [rdx+34h]
0x180013aad  jnz     loc_180013C8E
0x180013ab3  mov     rcx, rdx
0x180013ab6  call    CheckVideoInfoType
0x180013abb  mov     ebx, eax
0x180013abd  test    eax, eax
0x180013abf  js      loc_180013EAA
0x180013ac5  mov     r8, qword ptr cs:MEDIATYPE_Video.Data1
0x180013acc  mov     r15d, 8004022Ah
0x180013ad2  mov     rsi, rdi
0x180013ad5  mov     rcx, qword ptr cs:MEDIATYPE_Video.Data4
0x180013adc  mov     r13d, 1
0x180013ae2  mov     [rsp+88h+var_58], 0
0x180013aea  mov     [rsp+88h+var_50], rdi
0x180013aef  cmp     r8, [rdi]
0x180013af2  jnz     short loc_180013B36
0x180013af4  cmp     rcx, [rdi+8]
0x180013af8  jnz     short loc_180013B36
0x180013afa  cmp     r12, [rdi+2Ch]
0x180013afe  jnz     short loc_180013B36
0x180013b00  cmp     rbp, [rdi+34h]
0x180013b04  jnz     short loc_180013B36
0x180013b06  mov     rdx, rdi
0x180013b09  lea     rcx, [rsp+88h+var_50]
0x180013b0e  call    MediaTypeCreateVIHFromVIH2
0x180013b13  mov     edx, [rsp+88h+var_58]
0x180013b17  test    eax, eax
0x180013b19  mov     rsi, [rsp+88h+var_50]
0x180013b1e  mov     ebx, eax
0x180013b20  mov     rcx, qword ptr cs:MEDIATYPE_Video.Data4
0x180013b27  cmovns  edx, r13d
0x180013b2b  mov     r8, qword ptr cs:MEDIATYPE_Video.Data1
0x180013b32  mov     [rsp+88h+var_58], edx
0x180013b36  mov     rax, [r14+158h]
0x180013b3d  cmp     dword ptr [rax+0E8h], 0
0x180013b44  jnz     loc_180013E5B
0x180013b4a  xor     r13d, r13d
0x180013b4d  test    ebx, ebx
0x180013b4f  js      loc_180013E93
0x180013b55  mov     ebp, 80000000h
0x180013b5a  cmp     r13d, [r14+1B0h]
0x180013b61  jge     loc_180013E93
0x180013b67  mov     rax, [r14+1B8h]
0x180013b6e  lea     r8, [rsp+88h+var_50]
0x180013b73  mov     dword ptr [rsp+88h+var_50], 0
0x180013b7b  xor     edx, edx
0x180013b7d  movsxd  r12, r13d
0x180013b80  mov     rcx, [rax+r12*8]
0x180013b84  mov     rax, [rcx]
0x180013b87  mov     rax, [rax+20h]
0x180013b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b90  mov     ebx, eax
0x180013b92  add     eax, ebp
0x180013b94  test    ebp, eax
0x180013b96  jnz     short loc_180013BA4
0x180013b98  cmp     ebx, 0C00D07D1h
0x180013b9e  jnz     loc_180013E34
0x180013ba4  mov     ecx, dword ptr [rsp+88h+var_50]; unsigned __int64
0x180013ba8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013bad  mov     rbp, rax
0x180013bb0  test    rax, rax
0x180013bb3  jz      loc_180013E54
0x180013bb9  mov     rcx, [r14+1B8h]
0x180013bc0  lea     r8, [rsp+88h+var_50]
0x180013bc5  mov     rcx, [rcx+r12*8]
0x180013bc9  mov     rdx, [rcx]
0x180013bcc  mov     rax, [rdx+20h]
0x180013bd0  mov     rdx, rbp
0x180013bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd8  mov     ebx, eax
0x180013bda  test    eax, eax
0x180013bdc  js      loc_180013E27
0x180013be2  mov     rax, [rdi]
0x180013be5  cmp     rax, [rbp+0]
0x180013be9  jnz     loc_180013E27
0x180013bef  mov     rax, [rdi+8]
0x180013bf3  cmp     rax, [rbp+8]
0x180013bf7  jnz     loc_180013E27
0x180013bfd  test    r13d, r13d
0x180013c00  jnz     loc_180013CB1
0x180013c06  mov     rcx, rsi; struct _AMMediaType *
0x180013c09  call    ?IsFormatStructureWAVEFORMATEX@CWMWriterInputPin@@KAHPEBU_AMMediaType@@@Z; CWMWriterInputPin::IsFormatStructureWAVEFORMATEX(_AMMediaType const *)
0x180013c0e  test    eax, eax
0x180013c10  jz      loc_180013CB1
0x180013c16  mov     rcx, rbp; struct _AMMediaType *
0x180013c19  call    ?IsFormatStructureWAVEFORMATEX@CWMWriterInputPin@@KAHPEBU_AMMediaType@@@Z; CWMWriterInputPin::IsFormatStructureWAVEFORMATEX(_AMMediaType const *)
0x180013c1e  test    eax, eax
0x180013c20  jz      loc_180013CB1
0x180013c26  mov     r8, [rsi+50h]
0x180013c2a  mov     rcx, r8; struct tWAVEFORMATEX *
0x180013c2d  call    ?FormatTagFromWfx@@YAGPEBUtWAVEFORMATEX@@@Z; FormatTagFromWfx(tWAVEFORMATEX const *)
0x180013c32  lea     r12d, [r13+1]
0x180013c36  cmp     r12w, ax
0x180013c3a  jnz     short loc_180013CB7
0x180013c3c  movzx   r9d, word ptr [r8+2]
0x180013c41  lea     eax, [r13+2]
0x180013c45  cmp     r9w, ax
0x180013c49  ja      short loc_180013C55
0x180013c4b  jnz     short loc_180013CB7
0x180013c4d  cmp     word ptr [r8+0Eh], 10h
0x180013c53  jbe     short loc_180013CB7
0x180013c55  mov     rcx, [rbp+50h]; struct tWAVEFORMATEX *
0x180013c59  call    ?FormatTagFromWfx@@YAGPEBUtWAVEFORMATEX@@@Z; FormatTagFromWfx(tWAVEFORMATEX const *)
0x180013c5e  cmp     r12w, ax
0x180013c62  jz      short loc_180013CB7
0x180013c64  cmp     [rcx+2], r9w
0x180013c69  jnz     short loc_180013CB7
0x180013c6b  mov     eax, [r8+4]
0x180013c6f  cmp     [rcx+4], eax
0x180013c72  jnz     short loc_180013CB7
0x180013c74  movzx   eax, word ptr [r8+0Eh]
0x180013c79  cmp     [rcx+0Eh], ax
0x180013c7d  jnz     short loc_180013CB7
0x180013c7f  xor     r15d, r15d
0x180013c82  mov     [r14+1C8h], r15d
0x180013c89  jmp     loc_180013E4A
0x180013c8e  xor     ebx, ebx
0x180013c90  cmp     r12, [rdx+2Ch]
0x180013c94  jnz     loc_180013AC5
0x180013c9a  cmp     rbp, [rdx+34h]
0x180013c9e  jnz     loc_180013AC5
0x180013ca4  mov     rcx, rdi
0x180013ca7  call    CheckVideoInfo2Type
0x180013cac  jmp     loc_180013ABB
0x180013cb1  mov     r12d, 1
0x180013cb7  mov     rdx, rbp; struct _WMMediaType *
0x180013cba  mov     rcx, rsi; struct _AMMediaType *
0x180013cbd  call    ?IsAmTypeEqualWmType@@YAHPEAU_AMMediaType@@PEAU_WMMediaType@@@Z; IsAmTypeEqualWmType(_AMMediaType *,_WMMediaType *)
0x180013cc2  test    eax, eax
0x180013cc4  jz      loc_180013E27
0x180013cca  test    r13d, r13d
0x180013ccd  jnz     loc_180013E47
0x180013cd3  cmp     qword ptr [r14+1C0h], 0
0x180013cdb  jz      loc_180013E47
0x180013ce1  mov     r11, qword ptr cs:MEDIATYPE_Video.Data1
0x180013ce8  mov     r10, qword ptr cs:MEDIATYPE_Video.Data4
0x180013cef  cmp     [rsi], r11
0x180013cf2  jnz     loc_180013D9F
0x180013cf8  cmp     [rsi+8], r10
0x180013cfc  jnz     loc_180013D9F
0x180013d02  mov     rcx, rbp; struct _AMMediaType *
0x180013d05  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d0a  test    rax, rax
0x180013d0d  jz      loc_180013D9F
0x180013d13  mov     rcx, rsi; struct _AMMediaType *
0x180013d16  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d1b  test    rax, rax
0x180013d1e  jz      short loc_180013D9F
0x180013d20  mov     rcx, rbp; struct _AMMediaType *
0x180013d23  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d28  cmp     [rax+10h], r13d
0x180013d2c  jz      short loc_180013D9F
0x180013d2e  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d33  mov     rcx, rsi; struct _AMMediaType *
0x180013d36  mov     r9, rax
0x180013d39  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d3e  mov     ecx, [r9+4]
0x180013d42  cmp     [rax+4], ecx
0x180013d45  jnz     short loc_180013D9F
0x180013d47  mov     rcx, rbp; struct _AMMediaType *
0x180013d4a  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d4f  mov     rcx, rsi; struct _AMMediaType *
0x180013d52  mov     r9, rax
0x180013d55  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d5a  mov     ecx, [r9+8]
0x180013d5e  cmp     [rax+8], ecx
0x180013d61  jnz     short loc_180013D9F
0x180013d63  mov     rcx, rbp; struct _AMMediaType *
0x180013d66  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d6b  mov     rcx, rsi; struct _AMMediaType *
0x180013d6e  mov     r9, rax
0x180013d71  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d76  mov     ecx, [r9]
0x180013d79  cmp     [rax], ecx
0x180013d7b  jnz     short loc_180013D9F
0x180013d7d  mov     rcx, rbp; struct _AMMediaType *
0x180013d80  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d85  mov     rcx, rsi; struct _AMMediaType *
0x180013d88  mov     r9, rax
0x180013d8b  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180013d90  movzx   ecx, word ptr [r9+0Eh]
0x180013d95  cmp     [rax+0Eh], cx
0x180013d99  jz      loc_180013E40
0x180013d9f  mov     r9, qword ptr cs:MEDIATYPE_Audio.Data1
0x180013da6  mov     r8, qword ptr cs:MEDIATYPE_Audio.Data4
0x180013dad  cmp     r9, [rsi]
0x180013db0  jnz     short loc_180013E1C
0x180013db2  cmp     [rsi+8], r8
0x180013db6  jnz     short loc_180013E11
0x180013db8  mov     rcx, rsi; struct _AMMediaType *
0x180013dbb  call    ?IsFormatStructureWAVEFORMATEX@CWMWriterInputPin@@KAHPEBU_AMMediaType@@@Z; CWMWriterInputPin::IsFormatStructureWAVEFORMATEX(_AMMediaType const *)
0x180013dc0  test    eax, eax
0x180013dc2  jz      short loc_180013E11
0x180013dc4  mov     rcx, rbp; struct _AMMediaType *
0x180013dc7  call    ?IsFormatStructureWAVEFORMATEX@CWMWriterInputPin@@KAHPEBU_AMMediaType@@@Z; CWMWriterInputPin::IsFormatStructureWAVEFORMATEX(_AMMediaType const *)
0x180013dcc  test    eax, eax
0x180013dce  jz      short loc_180013E11
0x180013dd0  mov     rcx, [rsi+50h]; struct tWAVEFORMATEX *
0x180013dd4  call    ?FormatTagFromWfx@@YAGPEBUtWAVEFORMATEX@@@Z; FormatTagFromWfx(tWAVEFORMATEX const *)
0x180013dd9  cmp     r12w, ax
0x180013ddd  jz      short loc_180013E11
0x180013ddf  mov     rdx, [rbp+50h]; unsigned __int64
0x180013de3  movzx   eax, word ptr [rcx+2]
0x180013de7  cmp     [rdx+2], ax
0x180013deb  jnz     short loc_180013E11
0x180013ded  mov     eax, [rcx+4]
0x180013df0  cmp     [rdx+4], eax
0x180013df3  jnz     short loc_180013E11
0x180013df5  mov     eax, [rcx+8]
0x180013df8  cmp     [rdx+8], eax
0x180013dfb  jnz     short loc_180013E11
0x180013dfd  movzx   eax, word ptr [rcx+0Ch]
0x180013e01  cmp     [rdx+0Ch], ax
0x180013e05  jnz     short loc_180013E11
0x180013e07  movzx   eax, word ptr [rcx+0Eh]
0x180013e0b  cmp     [rdx+0Eh], ax
0x180013e0f  jz      short loc_180013E40
0x180013e11  cmp     r9, [rsi]
0x180013e14  jnz     short loc_180013E1C
0x180013e16  cmp     r8, [rsi+8]
0x180013e1a  jz      short loc_180013E27
0x180013e1c  cmp     r11, [rsi]
0x180013e1f  jnz     short loc_180013E40
0x180013e21  cmp     r10, [rsi+8]
0x180013e25  jnz     short loc_180013E40
0x180013e27  mov     rcx, rbp; void *
0x180013e2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013e2f  mov     ebp, 80000000h
0x180013e34  test    ebx, ebx
0x180013e36  js      short loc_180013E93
0x180013e38  inc     r13d
0x180013e3b  jmp     loc_180013B5A
0x180013e40  mov     [r14+1C8h], r12d
0x180013e47  xor     r15d, r15d
0x180013e4a  mov     rcx, rbp; void *
0x180013e4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013e52  jmp     short loc_180013E93
0x180013e54  mov     eax, 8007000Eh
0x180013e59  jmp     short loc_180013EAA
0x180013e5b  mov     edx, [r14+1A8h]
0x180013e62  cmp     edx, r13d
0x180013e65  jnz     short loc_180013E80
0x180013e67  mov     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x180013e6e  cmp     rax, [rdi]
0x180013e71  jnz     short loc_180013E80
0x180013e73  mov     rax, qword ptr cs:MEDIATYPE_Audio.Data4
0x180013e7a  cmp     rax, [rdi+8]
0x180013e7e  jz      short loc_180013E90
0x180013e80  cmp     edx, 2
0x180013e83  jnz     short loc_180013E93
0x180013e85  cmp     r8, [rdi]
0x180013e88  jnz     short loc_180013E93
0x180013e8a  cmp     rcx, [rdi+8]
0x180013e8e  jnz     short loc_180013E93
0x180013e90  xor     r15d, r15d
0x180013e93  cmp     [rsp+88h+var_58], 0
0x180013e98  jz      short loc_180013EA2
0x180013e9a  mov     rcx, rsi; pv
0x180013e9d  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180013ea2  test    ebx, ebx
0x180013ea4  cmovns  ebx, r15d
0x180013ea8  mov     eax, ebx
0x180013eaa  mov     rcx, [rsp+88h+var_48]
0x180013eaf  xor     rcx, rsp; StackCookie
0x180013eb2  call    __security_check_cookie
0x180013eb7  mov     rbx, [rsp+88h+arg_10]
0x180013ebf  add     rsp, 50h
0x180013ec3  pop     r15
0x180013ec5  pop     r14
0x180013ec7  pop     r13
0x180013ec9  pop     r12
0x180013ecb  pop     rdi
0x180013ecc  pop     rsi
0x180013ecd  pop     rbp
0x180013ece  retn
```
