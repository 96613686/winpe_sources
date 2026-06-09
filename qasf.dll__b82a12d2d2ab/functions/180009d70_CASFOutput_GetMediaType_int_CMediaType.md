# CASFOutput::GetMediaType(int,CMediaType *)

- ea: `0x180009d70`
- end: `0x18000a17b`
- name: `?GetMediaType@CASFOutput@@UEAAJHPEAVCMediaType@@@Z`
- size: `1035`
- prototype: `int(CASFOutput *__hidden this, int, struct CMediaType *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001460`
- `0x180007104`
- `0x180007210`
- `0x18000724c`
- `0x180009d70`
- `0x180016314`
- `0x18001be68`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009da0`
- `KERNEL32!EnterCriticalSection` at `0x180009da0`
- `KERNEL32!LeaveCriticalSection` at `0x18000a158`
- `KERNEL32!LeaveCriticalSection` at `0x18000a158`
- `ole32!CoTaskMemFree` at `0x18000a148`
- `ole32!CoTaskMemFree` at `0x18000a148`

## pseudocode

```c
__int64 __fastcall CASFOutput::GetMediaType(CASFOutput *this, int a2, struct CMediaType *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  struct _AMMediaType *v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  unsigned __int64 v14; // rdx
  struct _AMMediaType *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  struct _AMMediaType *v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rdx
  struct _AMMediaType *v22; // rax
  const struct _AMMediaType *v23; // rax
  struct _AMMediaType *v24; // rdi
  unsigned __int64 v26; // [rsp+30h] [rbp-30h] BYREF
  __int64 v27; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 v29; // [rsp+48h] [rbp-18h] BYREF
  __int64 v30; // [rsp+50h] [rbp-10h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 8);
  EnterCriticalSection(v3);
  if ( a2 < 0 )
  {
    v7 = -2147024809;
    goto LABEL_59;
  }
  v8 = *((_QWORD *)this + 37);
  if ( *(_DWORD *)(v8 + 448) )
  {
    v9 = *((unsigned int *)this + 76);
    v28 = 0;
    v10 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(**(_QWORD **)(v8 + 344) + 64LL))(
            *(_QWORD *)(v8 + 344),
            v9,
            &v28);
    v12 = 0;
    v27 = 0;
    if ( v11 < 0
      || (v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 37)
                                                                                           + 344LL)
                                                                             + 72LL))(
                  *(_QWORD *)(*((_QWORD *)this + 37) + 344LL),
                  *((unsigned int *)this + 76),
                  (unsigned int)a2,
                  &v27),
          v12 = v27,
          v13 < 0) )
    {
      if ( !*((_DWORD *)this + 103) && !*((_DWORD *)this + 102) )
      {
        v7 = 262403;
LABEL_48:
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_59;
      }
      v16 = *((_QWORD *)this + 37);
      v17 = *((unsigned int *)this + 76);
      LODWORD(v26) = 0;
      v30 = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *))(**(_QWORD **)(v16 + 344) + 72LL))(
             *(_QWORD *)(v16 + 344),
             v17,
             0,
             &v30);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v30 + 32LL))(v30, 0, &v26);
        if ( v7 >= 0 )
        {
          v19 = (struct _AMMediaType *)operator new[]((unsigned int)v26);
          v10 = v19;
          if ( v19 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType *, unsigned __int64 *))(*(_QWORD *)v30 + 32LL))(
                   v30,
                   v19,
                   &v26);
            if ( v7 >= 0 )
            {
              if ( *(_QWORD *)&MEDIATYPE_Video.Data1 == *(_QWORD *)&v10->majortype.Data1
                && *(_QWORD *)MEDIATYPE_Video.Data4 == *(_QWORD *)v10->majortype.Data4 )
              {
                CMediaType::Set((struct _AMMediaType *)a3, v10);
              }
              else
              {
                v7 = -2147418113;
              }
            }
          }
          else
          {
            v7 = -2147024882;
          }
        }
      }
      operator delete(v10, v18);
      if ( v7 >= 0
        && *(_QWORD *)&FORMAT_VideoInfo.Data1 == *(_QWORD *)((char *)a3 + 44)
        && *(_QWORD *)FORMAT_VideoInfo.Data4 == *(_QWORD *)((char *)a3 + 52) )
      {
        if ( v28 && a2 + 1 >= v28 && a2 + 1 < 2 * v28 )
        {
          v20 = *((_QWORD *)this + 37);
          v29 = 0;
          v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(**(_QWORD **)(v20 + 344) + 72LL))(
                 *(_QWORD *)(v20 + 344),
                 *((unsigned int *)this + 76),
                 a2 - v28,
                 &v29);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v29 + 32LL))(v29, 0, &v26);
            if ( v7 >= 0 )
            {
              v22 = (struct _AMMediaType *)operator new[]((unsigned int)v26);
              v10 = v22;
              if ( v22 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType *, unsigned __int64 *))(*(_QWORD *)v29 + 32LL))(
                       v29,
                       v22,
                       &v26);
                if ( v7 >= 0 )
                  CMediaType::Set((struct _AMMediaType *)a3, v10);
              }
              else
              {
                v7 = -2147024882;
              }
            }
          }
          operator delete(v10, v21);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        else
        {
          v7 = 262403;
        }
      }
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    else
    {
      LODWORD(v26) = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v27 + 32LL))(v27, 0, &v26);
      if ( v7 >= 0 )
      {
        v15 = (struct _AMMediaType *)operator new[]((unsigned int)v26);
        v10 = v15;
        if ( v15 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType *, unsigned __int64 *))(*(_QWORD *)v27 + 32LL))(
                 v27,
                 v15,
                 &v26);
          if ( v7 >= 0 )
            CMediaType::Set((struct _AMMediaType *)a3, v10);
        }
        else
        {
          v7 = -2147024882;
        }
      }
      operator delete(v10, v14);
      if ( *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_VideoInfo.Data1
        && *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4
        && (*((_DWORD *)this + 103) || *((_DWORD *)this + 102)) )
      {
        v7 = ConvertVideoInfoToVideoInfo2((__int64)a3);
      }
    }
    if ( v7 < 0 )
      FreeMediaType((struct _AMMediaType *)a3);
    v12 = v27;
    goto LABEL_48;
  }
  if ( a2 )
  {
    if ( a2 == 1
      && *(_QWORD *)((char *)this + 148) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
      && *(_QWORD *)((char *)this + 156) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
    {
      v23 = ConstructVIH1Type((const struct _AMMediaType *)((char *)this + 104));
      v24 = (struct _AMMediaType *)v23;
      if ( v23 )
      {
        v7 = CopyMediaType((struct _AMMediaType *)a3, v23);
        CoTaskMemFree(v24);
      }
      else
      {
        v7 = -2147024882;
      }
    }
    else
    {
      v7 = 262403;
    }
  }
  else
  {
    v7 = 0;
    CMediaType::Set((struct _AMMediaType *)a3, (const struct _AMMediaType *)((char *)this + 104));
  }
LABEL_59:
  LeaveCriticalSection(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009d70  push    rbp
0x180009d72  push    rbx
0x180009d73  push    rsi
0x180009d74  push    rdi
0x180009d75  push    r12
0x180009d77  push    r14
0x180009d79  push    r15
0x180009d7b  mov     rbp, rsp
0x180009d7e  sub     rsp, 60h
0x180009d82  mov     rax, cs:__security_cookie
0x180009d89  xor     rax, rsp
0x180009d8c  mov     [rbp+var_8], rax
0x180009d90  mov     r12, [rcx+40h]
0x180009d94  mov     rsi, rcx
0x180009d97  mov     rcx, r12; lpCriticalSection
0x180009d9a  mov     r14, r8
0x180009d9d  mov     r15d, edx
0x180009da0  call    cs:__imp_EnterCriticalSection
0x180009da6  test    r15d, r15d
0x180009da9  jns     short loc_180009DB5
0x180009dab  mov     ebx, 80070057h
0x180009db0  jmp     loc_18000A155
0x180009db5  mov     rcx, [rsi+128h]
0x180009dbc  cmp     dword ptr [rcx+1C0h], 0
0x180009dc3  jz      loc_18000A0E5
0x180009dc9  mov     edx, [rsi+130h]
0x180009dcf  lea     r8, [rbp+var_20]
0x180009dd3  mov     [rbp+var_20], 0
0x180009dda  xor     edi, edi
0x180009ddc  mov     rcx, [rcx+158h]
0x180009de3  mov     rax, [rcx]
0x180009de6  mov     rax, [rax+40h]
0x180009dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009def  xor     ecx, ecx
0x180009df1  mov     [rbp+var_28], rcx
0x180009df5  test    eax, eax
0x180009df7  js      loc_180009ED9
0x180009dfd  mov     rax, [rsi+128h]
0x180009e04  lea     r9, [rbp+var_28]
0x180009e08  mov     edx, [rsi+130h]
0x180009e0e  mov     r8d, r15d
0x180009e11  mov     rcx, [rax+158h]
0x180009e18  mov     rax, [rcx]
0x180009e1b  mov     rax, [rax+48h]
0x180009e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e24  mov     rcx, [rbp+var_28]
0x180009e28  test    eax, eax
0x180009e2a  js      loc_180009ED9
0x180009e30  mov     dword ptr [rbp+var_30], edi
0x180009e33  lea     r8, [rbp+var_30]
0x180009e37  mov     rax, [rcx]
0x180009e3a  xor     edx, edx
0x180009e3c  mov     rax, [rax+20h]
0x180009e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e45  mov     ebx, eax
0x180009e47  test    eax, eax
0x180009e49  js      short loc_180009E8A
0x180009e4b  mov     ecx, dword ptr [rbp+var_30]; unsigned __int64
0x180009e4e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009e53  mov     rdi, rax
0x180009e56  test    rax, rax
0x180009e59  jnz     short loc_180009E62
0x180009e5b  mov     ebx, 8007000Eh
0x180009e60  jmp     short loc_180009E8A
0x180009e62  mov     rcx, [rbp+var_28]
0x180009e66  lea     r8, [rbp+var_30]
0x180009e6a  mov     rdx, rdi
0x180009e6d  mov     rax, [rcx]
0x180009e70  mov     rax, [rax+20h]
0x180009e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e79  mov     ebx, eax
0x180009e7b  test    eax, eax
0x180009e7d  js      short loc_180009E8A
0x180009e7f  mov     rdx, rdi; struct _AMMediaType *
0x180009e82  mov     rcx, r14; this
0x180009e85  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180009e8a  mov     rcx, rdi; void *
0x180009e8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009e92  mov     rax, [r14+2Ch]
0x180009e96  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180009e9d  jnz     loc_18000A0C2
0x180009ea3  mov     rax, [r14+34h]
0x180009ea7  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180009eae  jnz     loc_18000A0C2
0x180009eb4  cmp     dword ptr [rsi+19Ch], 0
0x180009ebb  jnz     short loc_180009ECA
0x180009ebd  cmp     dword ptr [rsi+198h], 0
0x180009ec4  jz      loc_18000A0C2
0x180009eca  mov     rcx, r14
0x180009ecd  call    ConvertVideoInfoToVideoInfo2
0x180009ed2  mov     ebx, eax
0x180009ed4  jmp     loc_18000A0C2
0x180009ed9  cmp     [rsi+19Ch], edi
0x180009edf  jnz     short loc_180009EF3
0x180009ee1  cmp     [rsi+198h], edi
0x180009ee7  jnz     short loc_180009EF3
0x180009ee9  mov     ebx, 40103h
0x180009eee  jmp     loc_18000A0D2
0x180009ef3  mov     rax, [rsi+128h]
0x180009efa  lea     r9, [rbp+var_10]
0x180009efe  mov     edx, [rsi+130h]
0x180009f04  xor     r8d, r8d
0x180009f07  mov     dword ptr [rbp+var_30], edi
0x180009f0a  mov     [rbp+var_10], rdi
0x180009f0e  mov     rcx, [rax+158h]
0x180009f15  mov     rax, [rcx]
0x180009f18  mov     rax, [rax+48h]
0x180009f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f21  mov     ebx, eax
0x180009f23  test    eax, eax
0x180009f25  js      short loc_180009FA2
0x180009f27  mov     rcx, [rbp+var_10]
0x180009f2b  lea     r8, [rbp+var_30]
0x180009f2f  xor     edx, edx
0x180009f31  mov     rax, [rcx]
0x180009f34  mov     rax, [rax+20h]
0x180009f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3d  mov     ebx, eax
0x180009f3f  test    eax, eax
0x180009f41  js      short loc_180009FA2
0x180009f43  mov     ecx, dword ptr [rbp+var_30]; unsigned __int64
0x180009f46  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009f4b  mov     rdi, rax
0x180009f4e  test    rax, rax
0x180009f51  jnz     short loc_180009F5A
0x180009f53  mov     ebx, 8007000Eh
0x180009f58  jmp     short loc_180009FA2
0x180009f5a  mov     rcx, [rbp+var_10]
0x180009f5e  lea     r8, [rbp+var_30]
0x180009f62  mov     rdx, rdi
0x180009f65  mov     rax, [rcx]
0x180009f68  mov     rax, [rax+20h]
0x180009f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f71  mov     ebx, eax
0x180009f73  test    eax, eax
0x180009f75  js      short loc_180009FA2
0x180009f77  mov     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x180009f7e  cmp     rax, [rdi]
0x180009f81  jnz     short loc_180009F9D
0x180009f83  mov     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x180009f8a  cmp     rax, [rdi+8]
0x180009f8e  jnz     short loc_180009F9D
0x180009f90  mov     rdx, rdi; struct _AMMediaType *
0x180009f93  mov     rcx, r14; this
0x180009f96  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180009f9b  jmp     short loc_180009FA2
0x180009f9d  mov     ebx, 8000FFFFh
0x180009fa2  mov     rcx, rdi; void *
0x180009fa5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009faa  test    ebx, ebx
0x180009fac  js      loc_18000A0AD
0x180009fb2  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180009fb9  cmp     rax, [r14+2Ch]
0x180009fbd  jnz     loc_18000A0AD
0x180009fc3  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180009fca  cmp     rax, [r14+34h]
0x180009fce  jnz     loc_18000A0AD
0x180009fd4  mov     edx, [rbp+var_20]
0x180009fd7  test    edx, edx
0x180009fd9  jz      loc_18000A0A8
0x180009fdf  lea     ecx, [r15+1]
0x180009fe3  cmp     ecx, edx
0x180009fe5  jb      loc_18000A0A8
0x180009feb  lea     eax, [rdx+rdx]
0x180009fee  cmp     ecx, eax
0x180009ff0  jnb     loc_18000A0A8
0x180009ff6  mov     rax, [rsi+128h]
0x180009ffd  lea     r9, [rbp+var_18]
0x18000a001  mov     [rbp+var_18], 0
0x18000a009  sub     r15d, edx
0x18000a00c  mov     edx, [rsi+130h]
0x18000a012  mov     r8d, r15d
0x18000a015  mov     rcx, [rax+158h]
0x18000a01c  mov     rax, [rcx]
0x18000a01f  mov     rax, [rax+48h]
0x18000a023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a028  mov     ebx, eax
0x18000a02a  test    eax, eax
0x18000a02c  js      short loc_18000A089
0x18000a02e  mov     rcx, [rbp+var_18]
0x18000a032  lea     r8, [rbp+var_30]
0x18000a036  xor     edx, edx
0x18000a038  mov     rax, [rcx]
0x18000a03b  mov     rax, [rax+20h]
0x18000a03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a044  mov     ebx, eax
0x18000a046  test    eax, eax
0x18000a048  js      short loc_18000A089
0x18000a04a  mov     ecx, dword ptr [rbp+var_30]; unsigned __int64
0x18000a04d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a052  mov     rdi, rax
0x18000a055  test    rax, rax
0x18000a058  jnz     short loc_18000A061
0x18000a05a  mov     ebx, 8007000Eh
0x18000a05f  jmp     short loc_18000A089
0x18000a061  mov     rcx, [rbp+var_18]
0x18000a065  lea     r8, [rbp+var_30]
0x18000a069  mov     rdx, rdi
0x18000a06c  mov     rax, [rcx]
0x18000a06f  mov     rax, [rax+20h]
0x18000a073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a078  mov     ebx, eax
0x18000a07a  test    eax, eax
0x18000a07c  js      short loc_18000A089
0x18000a07e  mov     rdx, rdi; struct _AMMediaType *
0x18000a081  mov     rcx, r14; this
0x18000a084  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18000a089  mov     rcx, rdi; void *
0x18000a08c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a091  mov     rcx, [rbp+var_18]
0x18000a095  test    rcx, rcx
0x18000a098  jz      short loc_18000A0AD
0x18000a09a  mov     rax, [rcx]
0x18000a09d  mov     rax, [rax+10h]
0x18000a0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a6  jmp     short loc_18000A0AD
0x18000a0a8  mov     ebx, 40103h
0x18000a0ad  mov     rcx, [rbp+var_10]
0x18000a0b1  test    rcx, rcx
0x18000a0b4  jz      short loc_18000A0C2
0x18000a0b6  mov     rax, [rcx]
0x18000a0b9  mov     rax, [rax+10h]
0x18000a0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c2  test    ebx, ebx
0x18000a0c4  jns     short loc_18000A0CE
0x18000a0c6  mov     rcx, r14; struct _AMMediaType *
0x18000a0c9  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000a0ce  mov     rcx, [rbp+var_28]
0x18000a0d2  test    rcx, rcx
0x18000a0d5  jz      short loc_18000A155
0x18000a0d7  mov     rax, [rcx]
0x18000a0da  mov     rax, [rax+10h]
0x18000a0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e3  jmp     short loc_18000A155
0x18000a0e5  test    r15d, r15d
0x18000a0e8  jnz     short loc_18000A0FA
0x18000a0ea  xor     ebx, ebx
0x18000a0ec  lea     rdx, [rsi+68h]; struct _AMMediaType *
0x18000a0f0  mov     rcx, r14; this
0x18000a0f3  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18000a0f8  jmp     short loc_18000A155
0x18000a0fa  cmp     r15d, 1
0x18000a0fe  jnz     short loc_18000A150
0x18000a100  mov     rax, [rsi+94h]
0x18000a107  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000a10e  jnz     short loc_18000A150
0x18000a110  mov     rax, [rsi+9Ch]
0x18000a117  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18000a11e  jnz     short loc_18000A150
0x18000a120  lea     rcx, [rsi+68h]; struct _AMMediaType *
0x18000a124  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x18000a129  mov     rdi, rax
0x18000a12c  test    rax, rax
0x18000a12f  jnz     short loc_18000A138
0x18000a131  mov     ebx, 8007000Eh
0x18000a136  jmp     short loc_18000A155
0x18000a138  mov     rdx, rdi; struct _AMMediaType *
0x18000a13b  mov     rcx, r14; struct _AMMediaType *
0x18000a13e  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x18000a143  mov     rcx, rdi; pv
0x18000a146  mov     ebx, eax
0x18000a148  call    cs:__imp_CoTaskMemFree
0x18000a14e  jmp     short loc_18000A155
0x18000a150  mov     ebx, 40103h
0x18000a155  mov     rcx, r12; lpCriticalSection
0x18000a158  call    cs:__imp_LeaveCriticalSection
0x18000a15e  mov     eax, ebx
0x18000a160  mov     rcx, [rbp+var_8]
0x18000a164  xor     rcx, rsp; StackCookie
0x18000a167  call    __security_check_cookie
0x18000a16c  add     rsp, 60h
0x18000a170  pop     r15
0x18000a172  pop     r14
0x18000a174  pop     r12
0x18000a176  pop     rdi
0x18000a177  pop     rsi
0x18000a178  pop     rbx
0x18000a179  pop     rbp
0x18000a17a  retn
```
