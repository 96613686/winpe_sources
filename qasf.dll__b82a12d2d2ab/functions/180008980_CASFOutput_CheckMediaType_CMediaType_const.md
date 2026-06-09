# CASFOutput::CheckMediaType(CMediaType const *)

- ea: `0x180008980`
- end: `0x180008b96`
- name: `?CheckMediaType@CASFOutput@@UEAAJPEBVCMediaType@@@Z`
- size: `534`
- prototype: `int(CASFOutput *__hidden this, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001460`
- `0x180001cfc`
- `0x180007088`
- `0x180007104`
- `0x180007210`
- `0x180008980`
- `0x180016314`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008a58`
- `ole32!CoTaskMemFree` at `0x180008a58`

## pseudocode

```c
__int64 __fastcall CASFOutput::CheckMediaType(CASFOutput *this, const struct CMediaType *a2)
{
  const struct _AMMediaType *v4; // rax
  struct _AMMediaType *v5; // rdi
  int v7; // ebx
  unsigned int i; // esi
  __int64 v9; // rax
  struct _AMMediaType v10; // [rsp+20h] [rbp-89h] BYREF
  struct _AMMediaType v11; // [rsp+80h] [rbp-29h] BYREF

  if ( *(_DWORD *)(*((_QWORD *)this + 37) + 448LL) )
  {
    for ( i = 0; ; ++i )
    {
      memset_0(&v11, 0, sizeof(v11));
      v9 = *(_QWORD *)this;
      v11.lSampleSize = 1;
      v11.bFixedSizeSamples = 1;
      if ( (*(unsigned int (__fastcall **)(CASFOutput *, _QWORD, struct _AMMediaType *))(v9 + 104))(this, i, &v11) )
        break;
      if ( (unsigned int)CMediaType::operator==(a2, &v11)
        || *(_QWORD *)&MEDIATYPE_Video.Data1 == *(_QWORD *)a2
        && *(_QWORD *)MEDIATYPE_Video.Data4 == *((_QWORD *)a2 + 1)
        && *(_QWORD *)a2 == *(_QWORD *)&v11.majortype.Data1
        && *((_QWORD *)a2 + 1) == *(_QWORD *)v11.majortype.Data4
        && *((_QWORD *)a2 + 2) == *(_QWORD *)&v11.subtype.Data1
        && *((_QWORD *)a2 + 3) == *(_QWORD *)v11.subtype.Data4
        && *(_QWORD *)((char *)a2 + 44) == *(_QWORD *)&v11.formattype.Data1
        && *(_QWORD *)((char *)a2 + 52) == *(_QWORD *)v11.formattype.Data4
        && *((_DWORD *)a2 + 8) == v11.bFixedSizeSamples
        && *((_DWORD *)a2 + 9) == v11.bTemporalCompression
        && *((_DWORD *)a2 + 18) >= v11.cbFormat
        && *((_DWORD *)a2 + 10) >= v11.lSampleSize )
      {
        FreeMediaType(&v11);
        return 0;
      }
      FreeMediaType(&v11);
    }
    FreeMediaType(&v11);
  }
  else
  {
    if ( *(_QWORD *)&FORMAT_VideoInfo.Data1 != *(_QWORD *)((char *)a2 + 44)
      || *(_QWORD *)FORMAT_VideoInfo.Data4 != *(_QWORD *)((char *)a2 + 52)
      || *(_QWORD *)&FORMAT_VideoInfo2.Data1 != *(_QWORD *)((char *)this + 148)
      || *(_QWORD *)FORMAT_VideoInfo2.Data4 != *(_QWORD *)((char *)this + 156) )
    {
      return (unsigned int)CMediaType::operator==(a2, (char *)this + 104) == 0;
    }
    v4 = ConstructVIH1Type((const struct _AMMediaType *)((char *)this + 104));
    v5 = (struct _AMMediaType *)v4;
    if ( !v4 )
      return 2147942414LL;
    CopyMediaType(&v10, v4);
    CopyMediaType(&v11, (const struct _AMMediaType *)a2);
    v7 = CMediaType::operator==(&v10, &v11);
    FreeMediaType(&v11);
    FreeMediaType(&v10);
    CoTaskMemFree(v5);
    if ( v7 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180008980  mov     [rsp-8+arg_10], rbx
0x180008985  push    rbp
0x180008986  push    rsi
0x180008987  push    rdi
0x180008988  lea     rbp, [rsp-47h]
0x18000898d  sub     rsp, 0F0h
0x180008994  mov     rax, cs:__security_cookie
0x18000899b  xor     rax, rsp
0x18000899e  mov     [rbp+57h+var_20], rax
0x1800089a2  mov     rax, [rcx+128h]
0x1800089a9  mov     rbx, rdx
0x1800089ac  mov     rdi, rcx
0x1800089af  cmp     dword ptr [rax+1C0h], 0
0x1800089b6  jnz     loc_180008A87
0x1800089bc  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800089c3  cmp     rax, [rdx+2Ch]
0x1800089c7  jnz     loc_180008A6D
0x1800089cd  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800089d4  cmp     rax, [rdx+34h]
0x1800089d8  jnz     loc_180008A6D
0x1800089de  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800089e5  cmp     rax, [rcx+94h]
0x1800089ec  jnz     short loc_180008A6D
0x1800089ee  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800089f5  cmp     rax, [rcx+9Ch]
0x1800089fc  jnz     short loc_180008A6D
0x1800089fe  add     rcx, 68h ; 'h'; struct _AMMediaType *
0x180008a02  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x180008a07  mov     rdi, rax
0x180008a0a  test    rax, rax
0x180008a0d  jnz     short loc_180008A19
0x180008a0f  mov     eax, 8007000Eh
0x180008a14  jmp     loc_180008B77
0x180008a19  mov     rdx, rdi; struct _AMMediaType *
0x180008a1c  lea     rcx, [rsp+100h+var_E0]; struct _AMMediaType *
0x180008a21  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180008a26  mov     rdx, rbx; struct _AMMediaType *
0x180008a29  lea     rcx, [rbp+57h+var_80]; struct _AMMediaType *
0x180008a2d  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180008a32  lea     rdx, [rbp+57h+var_80]
0x180008a36  lea     rcx, [rsp+100h+var_E0]
0x180008a3b  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x180008a40  lea     rcx, [rbp+57h+var_80]; struct _AMMediaType *
0x180008a44  mov     ebx, eax
0x180008a46  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008a4b  lea     rcx, [rsp+100h+var_E0]; struct _AMMediaType *
0x180008a50  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008a55  mov     rcx, rdi; pv
0x180008a58  call    cs:__imp_CoTaskMemFree
0x180008a5e  test    ebx, ebx
0x180008a60  jz      loc_180008B72
0x180008a66  xor     eax, eax
0x180008a68  jmp     loc_180008B77
0x180008a6d  lea     rdx, [rcx+68h]
0x180008a71  mov     rcx, rbx
0x180008a74  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x180008a79  xor     ecx, ecx
0x180008a7b  test    eax, eax
0x180008a7d  setz    cl
0x180008a80  mov     eax, ecx
0x180008a82  jmp     loc_180008B77
0x180008a87  xor     esi, esi
0x180008a89  xor     edx, edx; Val
0x180008a8b  lea     rcx, [rbp+57h+var_80]; void *
0x180008a8f  lea     r8d, [rdx+58h]; Size
0x180008a93  call    memset_0
0x180008a98  mov     rax, [rdi]
0x180008a9b  lea     r8, [rbp+57h+var_80]
0x180008a9f  mov     edx, esi
0x180008aa1  mov     [rbp+57h+var_80.lSampleSize], 1
0x180008aa8  mov     rcx, rdi
0x180008aab  mov     [rbp+57h+var_80.bFixedSizeSamples], 1
0x180008ab2  mov     rax, [rax+68h]
0x180008ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008abb  test    eax, eax
0x180008abd  jnz     loc_180008B69
0x180008ac3  lea     rdx, [rbp+57h+var_80]
0x180008ac7  mov     rcx, rbx
0x180008aca  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x180008acf  test    eax, eax
0x180008ad1  jnz     loc_180008B5B
0x180008ad7  mov     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x180008ade  cmp     rax, [rbx]
0x180008ae1  jnz     short loc_180008B4B
0x180008ae3  mov     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x180008aea  cmp     rax, [rbx+8]
0x180008aee  jnz     short loc_180008B4B
0x180008af0  mov     rax, [rbx]
0x180008af3  cmp     rax, qword ptr [rbp+57h+var_80.majortype.Data1]
0x180008af7  jnz     short loc_180008B4B
0x180008af9  mov     rax, [rbx+8]
0x180008afd  cmp     rax, qword ptr [rbp+57h+var_80.majortype.Data4]
0x180008b01  jnz     short loc_180008B4B
0x180008b03  mov     rax, [rbx+10h]
0x180008b07  cmp     rax, qword ptr [rbp+57h+var_80.subtype.Data1]
0x180008b0b  jnz     short loc_180008B4B
0x180008b0d  mov     rax, [rbx+18h]
0x180008b11  cmp     rax, qword ptr [rbp+57h+var_80.subtype.Data4]
0x180008b15  jnz     short loc_180008B4B
0x180008b17  mov     rax, [rbx+2Ch]
0x180008b1b  cmp     rax, qword ptr [rbp+57h+var_80.formattype.Data1]
0x180008b1f  jnz     short loc_180008B4B
0x180008b21  mov     rax, [rbx+34h]
0x180008b25  cmp     rax, qword ptr [rbp+57h+var_80.formattype.Data4]
0x180008b29  jnz     short loc_180008B4B
0x180008b2b  mov     eax, [rbp+57h+var_80.bFixedSizeSamples]
0x180008b2e  cmp     [rbx+20h], eax
0x180008b31  jnz     short loc_180008B4B
0x180008b33  mov     eax, [rbp+57h+var_80.bTemporalCompression]
0x180008b36  cmp     [rbx+24h], eax
0x180008b39  jnz     short loc_180008B4B
0x180008b3b  mov     eax, [rbp+57h+var_80.cbFormat]
0x180008b3e  cmp     [rbx+48h], eax
0x180008b41  jb      short loc_180008B4B
0x180008b43  mov     eax, [rbp+57h+var_80.lSampleSize]
0x180008b46  cmp     [rbx+28h], eax
0x180008b49  jnb     short loc_180008B5B
0x180008b4b  inc     esi
0x180008b4d  lea     rcx, [rbp+57h+var_80]; struct _AMMediaType *
0x180008b51  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008b56  jmp     loc_180008A89
0x180008b5b  lea     rcx, [rbp+57h+var_80]; struct _AMMediaType *
0x180008b5f  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008b64  jmp     loc_180008A66
0x180008b69  lea     rcx, [rbp+57h+var_80]; struct _AMMediaType *
0x180008b6d  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008b72  mov     eax, 1
0x180008b77  mov     rcx, [rbp+57h+var_20]
0x180008b7b  xor     rcx, rsp; StackCookie
0x180008b7e  call    __security_check_cookie
0x180008b83  mov     rbx, [rsp+100h+arg_10]
0x180008b8b  add     rsp, 0F0h
0x180008b92  pop     rdi
0x180008b93  pop     rsi
0x180008b94  pop     rbp
0x180008b95  retn
```
