# CWMWriterInputPin::SetWMSDKType(CMediaType const *)

- ea: `0x180014f78`
- end: `0x180015210`
- name: `?SetWMSDKType@CWMWriterInputPin@@QEAAJPEBVCMediaType@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, const struct CMediaType *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014de0`

## callees

- `0x180001460`
- `0x180007104`
- `0x180007210`
- `0x180013178`
- `0x180013278`
- `0x180014f78`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::SetWMSDKType(CWMWriterInputPin *this, const struct CMediaType *a2)
{
  _QWORD *v4; // r14
  __int64 v5; // rcx
  __int64 result; // rax
  int v7; // r15d
  __int64 v8; // rdx
  struct _AMMediaType *v9; // rdi
  __int64 v10; // rcx
  int v11; // eax
  BYTE *pbFormat; // rcx
  int v13; // ebx
  struct tagBITMAPINFOHEADER *v14; // rax
  __int64 v15; // r9
  int v16; // ecx
  struct _AMMediaType *v17; // [rsp+30h] [rbp-A8h] BYREF
  struct _AMMediaType v18; // [rsp+40h] [rbp-98h] BYREF

  if ( *(_DWORD *)(*((_QWORD *)this + 43) + 232LL) )
  {
    v16 = *((_DWORD *)this + 106);
    if ( v16 == 1
      && *(_QWORD *)&MEDIATYPE_Audio.Data1 == *(_QWORD *)a2
      && *(_QWORD *)MEDIATYPE_Audio.Data4 == *((_QWORD *)a2 + 1) )
    {
      return 0;
    }
    v13 = 0;
    if ( v16 == 2
      && *(_QWORD *)&MEDIATYPE_Video.Data1 == *(_QWORD *)a2
      && *(_QWORD *)MEDIATYPE_Video.Data4 == *((_QWORD *)a2 + 1) )
    {
      return 0;
    }
    return (unsigned int)v13;
  }
  v4 = (_QWORD *)((char *)this + 416);
  v5 = *((_QWORD *)this + 52);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *v4 = 0;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)(*((_QWORD *)this + 43) + 312LL) + 56LL))(
             *(_QWORD *)(*((_QWORD *)this + 43) + 312LL),
             *((unsigned int *)this + 99),
             v4);
  v7 = result;
  if ( (int)result >= 0 )
  {
    v8 = *(_QWORD *)&MEDIATYPE_Video.Data1;
    v9 = (struct _AMMediaType *)((char *)this + 104);
    v10 = *(_QWORD *)MEDIATYPE_Video.Data4;
    v17 = (struct _AMMediaType *)((char *)this + 104);
    if ( *(_QWORD *)&MEDIATYPE_Video.Data1 == *(_QWORD *)a2
      && *(_QWORD *)MEDIATYPE_Video.Data4 == *((_QWORD *)a2 + 1)
      && *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)((char *)a2 + 44)
      && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)((char *)a2 + 52) )
    {
      v11 = MediaTypeCreateVIHFromVIH2(&v17, (__int128 *)a2);
      v10 = *(_QWORD *)MEDIATYPE_Video.Data4;
      v7 = v11;
      v8 = *(_QWORD *)&MEDIATYPE_Video.Data1;
      v9 = v17;
    }
    if ( v9
      && *(_QWORD *)&v9->majortype.Data1 == v8
      && *(_QWORD *)v9->majortype.Data4 == v10
      && (pbFormat = v9->pbFormat) != 0
      && v9->cbFormat
      && (*(_QWORD *)&MEDIASUBTYPE_YUY2.Data1 == *(_QWORD *)&v9->subtype.Data1
       && *(_QWORD *)MEDIASUBTYPE_YUY2.Data4 == *(_QWORD *)v9->subtype.Data4
       || *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1 == *(_QWORD *)&v9->subtype.Data1
       && *(_QWORD *)MEDIASUBTYPE_UYVY.Data4 == *(_QWORD *)v9->subtype.Data4
       || *(_QWORD *)&MEDIASUBTYPE_CLJR.Data1 == *(_QWORD *)&v9->subtype.Data1
       && *(_QWORD *)MEDIASUBTYPE_CLJR.Data4 == *(_QWORD *)v9->subtype.Data4)
      && *((int *)pbFormat + 14) < 0 )
    {
      v13 = CopyMediaType(&v18, v9);
      if ( v13 >= 0 )
      {
        v13 = v7;
        if ( v7 >= 0 )
        {
          GetbmiHeader(&v18);
          v14 = GetbmiHeader(v9);
          if ( v15 && v14 )
          {
            *(_DWORD *)(v15 + 8) = -v14->biHeight;
            v13 = (*(__int64 (__fastcall **)(_QWORD, struct _AMMediaType *))(*(_QWORD *)*v4 + 40LL))(*v4, &v18);
          }
          else
          {
            v13 = -2147467259;
          }
        }
      }
      FreeMediaType(&v18);
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, struct _AMMediaType *))(*(_QWORD *)*v4 + 40LL))(*v4, v9);
    }
    if ( v13 >= 0 && !*((_DWORD *)this + 114) )
      return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 43)
                                                                                           + 312LL)
                                                                             + 64LL))(
                             *(_QWORD *)(*((_QWORD *)this + 43) + 312LL),
                             *((unsigned int *)this + 99),
                             *v4);
    return (unsigned int)v13;
  }
  return result;
}

```

## disassembly

```asm
0x180014f78  mov     [rsp+arg_10], rbx
0x180014f7d  push    rbp
0x180014f7e  push    rsi
0x180014f7f  push    rdi
0x180014f80  push    r14
0x180014f82  push    r15
0x180014f84  sub     rsp, 0B0h
0x180014f8b  mov     rax, cs:__security_cookie
0x180014f92  xor     rax, rsp
0x180014f95  mov     [rsp+0D8h+var_38], rax
0x180014f9d  mov     rax, [rcx+158h]
0x180014fa4  mov     rsi, rdx
0x180014fa7  mov     rbp, rcx
0x180014faa  cmp     dword ptr [rax+0E8h], 0
0x180014fb1  jnz     loc_1800151A1
0x180014fb7  lea     r14, [rcx+1A0h]
0x180014fbe  mov     rcx, [r14]
0x180014fc1  test    rcx, rcx
0x180014fc4  jz      short loc_180014FD9
0x180014fc6  mov     rax, [rcx]
0x180014fc9  mov     rax, [rax+10h]
0x180014fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fd2  mov     qword ptr [r14], 0
0x180014fd9  mov     rax, [rbp+158h]
0x180014fe0  mov     r8, r14
0x180014fe3  mov     edx, [rbp+18Ch]
0x180014fe9  mov     rcx, [rax+138h]
0x180014ff0  mov     rax, [rcx]
0x180014ff3  mov     rax, [rax+38h]
0x180014ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ffc  mov     r15d, eax
0x180014fff  test    eax, eax
0x180015001  js      loc_1800151E9
0x180015007  mov     rdx, qword ptr cs:MEDIATYPE_Video.Data1
0x18001500e  lea     rdi, [rbp+68h]
0x180015012  mov     rcx, qword ptr cs:MEDIATYPE_Video.Data4
0x180015019  mov     [rsp+0D8h+var_A8], rdi
0x18001501e  cmp     rdx, [rsi]
0x180015021  jnz     short loc_180015066
0x180015023  cmp     rcx, [rsi+8]
0x180015027  jnz     short loc_180015066
0x180015029  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180015030  cmp     rax, [rsi+2Ch]
0x180015034  jnz     short loc_180015066
0x180015036  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18001503d  cmp     rax, [rsi+34h]
0x180015041  jnz     short loc_180015066
0x180015043  mov     rdx, rsi
0x180015046  lea     rcx, [rsp+0D8h+var_A8]
0x18001504b  call    MediaTypeCreateVIHFromVIH2
0x180015050  mov     rcx, qword ptr cs:MEDIATYPE_Video.Data4
0x180015057  mov     r15d, eax
0x18001505a  mov     rdx, qword ptr cs:MEDIATYPE_Video.Data1
0x180015061  mov     rdi, [rsp+0D8h+var_A8]
0x180015066  test    rdi, rdi
0x180015069  jz      loc_180015159
0x18001506f  cmp     [rdi], rdx
0x180015072  jnz     loc_180015159
0x180015078  cmp     [rdi+8], rcx
0x18001507c  jnz     loc_180015159
0x180015082  mov     rcx, [rdi+50h]
0x180015086  test    rcx, rcx
0x180015089  jz      loc_180015159
0x18001508f  cmp     dword ptr [rdi+48h], 0
0x180015093  jz      loc_180015159
0x180015099  mov     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x1800150a0  cmp     rax, [rdi+10h]
0x1800150a4  jnz     short loc_1800150B3
0x1800150a6  mov     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x1800150ad  cmp     rax, [rdi+18h]
0x1800150b1  jz      short loc_1800150E7
0x1800150b3  mov     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data1
0x1800150ba  cmp     rax, [rdi+10h]
0x1800150be  jnz     short loc_1800150CD
0x1800150c0  mov     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data4
0x1800150c7  cmp     rax, [rdi+18h]
0x1800150cb  jz      short loc_1800150E7
0x1800150cd  mov     rax, qword ptr cs:MEDIASUBTYPE_CLJR.Data1
0x1800150d4  cmp     rax, [rdi+10h]
0x1800150d8  jnz     short loc_180015159
0x1800150da  mov     rax, qword ptr cs:MEDIASUBTYPE_CLJR.Data4
0x1800150e1  cmp     rax, [rdi+18h]
0x1800150e5  jnz     short loc_180015159
0x1800150e7  cmp     dword ptr [rcx+38h], 0
0x1800150eb  jge     short loc_180015159
0x1800150ed  mov     rdx, rdi; struct _AMMediaType *
0x1800150f0  lea     rcx, [rsp+0D8h+var_98]; struct _AMMediaType *
0x1800150f5  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x1800150fa  mov     ebx, eax
0x1800150fc  test    eax, eax
0x1800150fe  js      short loc_18001514D
0x180015100  mov     ebx, r15d
0x180015103  test    r15d, r15d
0x180015106  js      short loc_18001514D
0x180015108  lea     rcx, [rsp+0D8h+var_98]; struct _AMMediaType *
0x18001510d  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x180015112  mov     rcx, rdi; struct _AMMediaType *
0x180015115  mov     r9, rax
0x180015118  call    ?GetbmiHeader@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; GetbmiHeader(_AMMediaType const *)
0x18001511d  test    r9, r9
0x180015120  jz      short loc_180015148
0x180015122  test    rax, rax
0x180015125  jz      short loc_180015148
0x180015127  mov     ecx, [rax+8]
0x18001512a  lea     rdx, [rsp+0D8h+var_98]
0x18001512f  neg     ecx
0x180015131  mov     [r9+8], ecx
0x180015135  mov     rcx, [r14]
0x180015138  mov     rax, [rcx]
0x18001513b  mov     rax, [rax+28h]
0x18001513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015144  mov     ebx, eax
0x180015146  jmp     short loc_18001514D
0x180015148  mov     ebx, 80004005h
0x18001514d  lea     rcx, [rsp+0D8h+var_98]; struct _AMMediaType *
0x180015152  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180015157  jmp     short loc_18001516D
0x180015159  mov     rcx, [r14]
0x18001515c  mov     rdx, rdi
0x18001515f  mov     rax, [rcx]
0x180015162  mov     rax, [rax+28h]
0x180015166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001516b  mov     ebx, eax
0x18001516d  test    ebx, ebx
0x18001516f  js      short loc_1800151E7
0x180015171  cmp     dword ptr [rbp+1C8h], 0
0x180015178  jnz     short loc_1800151E7
0x18001517a  mov     rax, [rbp+158h]
0x180015181  mov     r8, [r14]
0x180015184  mov     edx, [rbp+18Ch]
0x18001518a  mov     rcx, [rax+138h]
0x180015191  mov     rax, [rcx]
0x180015194  mov     rax, [rax+40h]
0x180015198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001519d  mov     ebx, eax
0x18001519f  jmp     short loc_1800151E7
0x1800151a1  mov     ecx, [rcx+1A8h]
0x1800151a7  cmp     ecx, 1
0x1800151aa  jnz     short loc_1800151C5
0x1800151ac  mov     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x1800151b3  cmp     rax, [rdx]
0x1800151b6  jnz     short loc_1800151C5
0x1800151b8  mov     rax, qword ptr cs:MEDIATYPE_Audio.Data4
0x1800151bf  cmp     rax, [rdx+8]
0x1800151c3  jz      short loc_1800151E5
0x1800151c5  xor     ebx, ebx
0x1800151c7  cmp     ecx, 2
0x1800151ca  jnz     short loc_1800151E7
0x1800151cc  mov     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x1800151d3  cmp     rax, [rdx]
0x1800151d6  jnz     short loc_1800151E7
0x1800151d8  mov     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x1800151df  cmp     rax, [rdx+8]
0x1800151e3  jnz     short loc_1800151E7
0x1800151e5  xor     ebx, ebx
0x1800151e7  mov     eax, ebx
0x1800151e9  mov     rcx, [rsp+0D8h+var_38]
0x1800151f1  xor     rcx, rsp; StackCookie
0x1800151f4  call    __security_check_cookie
0x1800151f9  mov     rbx, [rsp+0D8h+arg_10]
0x180015201  add     rsp, 0B0h
0x180015208  pop     r15
0x18001520a  pop     r14
0x18001520c  pop     rdi
0x18001520d  pop     rsi
0x18001520e  pop     rbp
0x18001520f  retn
```
