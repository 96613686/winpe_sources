# NetworkIncident::Validate(long *)

- ea: `0x18000f4dc`
- end: `0x18000fb2d`
- name: `?Validate@NetworkIncident@@QEAAJPEAJ@Z`
- size: `1617`
- prototype: `__int64 __fastcall(NetworkIncident *__hidden this, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001cc54`

## callees

- `0x180005350`
- `0x18000579c`
- `0x180006d58`
- `0x180006df8`
- `0x180008c84`
- `0x18000bca0`
- `0x18000c42c`
- `0x18000f4dc`
- `0x1800103e0`
- `0x18001b3a8`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000f897`
- `KERNEL32!WaitForSingleObject` at `0x18000f897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f64c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f64c`

## string_xrefs

- `0x18000f634`: `Could not update the progress string. HRESULT: 0x%x`
- `0x18000f694`: `Warning: HelperClass '%s' not found in the HC Discovery Registry. HRESULT: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NetworkIncident::Validate(NetworkIncident *this, int *a2, __int64 a3)
{
  __int64 v5; // rcx
  int v7; // r14d
  _QWORD *v8; // rcx
  __int64 v9; // r8
  struct NetworkDiagnosticsEngine *v10; // r13
  __int64 **v11; // rsi
  unsigned int v12; // r15d
  __int64 v13; // rbx
  int v14; // edx
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // bl
  __int64 v24; // r8
  struct _FILETIME *TickCount; // rax
  unsigned __int64 v26; // rdx
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r9
  unsigned __int64 v30; // r10
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r9
  __int64 v34; // rbx
  __int64 v35; // r10
  __int64 v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-50h]
  unsigned int v38; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  __int64 v40; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME v41; // [rsp+48h] [rbp-28h] BYREF
  __int64 v42; // [rsp+50h] [rbp-20h] BYREF
  struct _FILETIME v43[2]; // [rsp+58h] [rbp-18h] BYREF

  if ( !*((_QWORD *)this + 25) )
  {
    v5 = *((_QWORD *)this + 27);
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v5 + 96LL))(
        v5,
        3,
        L"Nothing to Validate, skipping validation and returning success.");
    return 0;
  }
  if ( (byte_180041BC1 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(this, StartNDFValidate, a3, 1, v43);
  v38 = 1;
  v7 = 0;
  v10 = NetworkDiagnosticsEngine::Instance();
  v11 = (__int64 **)*((_QWORD *)this + 25);
  v12 = 5;
  while ( 2 )
  {
    while ( 2 )
    {
      if ( v38 != 1 )
        goto LABEL_74;
      *((_DWORD *)v11 + 24) = 6;
      if ( *((_QWORD *)this + 10) )
      {
        if ( v10 )
        {
          v8 = (_QWORD *)*((_QWORD *)v10 + 3);
          if ( v8 )
          {
            v13 = (*v11)[2];
            if ( !*(_DWORD *)(v13 - 16) )
              v13 = **v11;
            v40 = 0;
            v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(*v8 + 24LL))(v8, v13, &v40);
            if ( v14 < 0 )
            {
              v20 = *((_QWORD *)this + 27);
              if ( v20 )
              {
                LODWORD(v37) = v14;
                (*(void (**)(__int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v20 + 104LL))(
                  v20,
                  0,
                  L"Warning: HelperClass '%s' not found in the HC Discovery Registry. HRESULT: 0x%x",
                  v13,
                  v37);
              }
            }
            else
            {
              pv = 0;
              v15 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 64LL))(v40, &pv);
              v16 = v15;
              if ( v15 < 0 )
              {
                v19 = *((_QWORD *)this + 27);
                if ( v19 )
                  (*(void (**)(__int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v19 + 104LL))(
                    v19,
                    0,
                    L"Could not retrieve the current HC's progress string. HRESULT: 0x%x",
                    (unsigned int)v15);
              }
              else
              {
                v17 = DiagnosticsClient::SetProgress(
                        *((DiagnosticsClient **)this + 10),
                        (const unsigned __int16 *)0xCA,
                        pv);
                v16 = v17;
                if ( v17 < 0 )
                {
                  v18 = *((_QWORD *)this + 27);
                  if ( v18 )
                    (*(void (**)(__int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v18 + 104LL))(
                      v18,
                      0,
                      L"Could not update the progress string. HRESULT: 0x%x",
                      (unsigned int)v17);
                  v16 = 0;
                }
                CoTaskMemFree(pv);
              }
              if ( v16 >= 0 )
                goto LABEL_28;
            }
            DiagnosticsClient::SetProgress(*((DiagnosticsClient **)this + 10), &dword_180033E1C);
LABEL_28:
            ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v40);
            goto LABEL_29;
          }
        }
      }
      while ( 1 )
      {
LABEL_29:
        if ( *((_DWORD *)this + 6) == 13 )
          goto LABEL_69;
        ATL::CFileTime::GetTickCount(&v41);
        if ( (byte_180041BC1 & 2) != 0 )
        {
          v22 = (*v11)[2];
          if ( !*(_DWORD *)(v22 - 16) )
            v22 = **v11;
          McTemplateU0z_EventWriteTransfer(v21, StartNDFHCValidate, v22);
        }
        if ( *((int *)*v11 + 57) >= 0 )
        {
          v23 = 0;
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 56LL))(*((_QWORD *)this + 10));
          if ( v7 < 0 )
            goto LABEL_40;
          v23 = 1;
        }
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *))(*(_QWORD *)(*v11)[9] + 80LL))(
               (*v11)[9],
               *((unsigned int *)v11 + 7),
               a2,
               &v38);
        if ( v23 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10));
LABEL_40:
        if ( (byte_180041BC1 & 2) != 0 )
        {
          v24 = (*v11)[2];
          if ( !*(_DWORD *)(v24 - 16) )
            v24 = **v11;
          McTemplateU0z_EventWriteTransfer(v8, StopNDFHCValidate, v24);
        }
        if ( v7 == -2147467263 )
        {
          v8 = (_QWORD *)*((_QWORD *)this + 27);
          if ( v8 )
            (*(void (__fastcall **)(_QWORD *, __int64 *, __int64, __int64, __int64))(*v8 + 80LL))(
              v8,
              *v11,
              (*v11)[14] + 112LL * *((unsigned int *)this + 52),
              3,
              (*v11)[5]);
          goto LABEL_68;
        }
        if ( v7 < 0 )
        {
          v8 = (_QWORD *)*((_QWORD *)this + 27);
          if ( v8 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64 *, __int64, __int64, __int64))(*v8 + 80LL))(
              v8,
              *v11,
              (*v11)[14] + 112LL * *((unsigned int *)this + 52),
              4,
              (*v11)[5]);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v42);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              (__int64)&v42,
              (__int64)L"Validation failed. HRESULT=0x%x",
              (unsigned int)v7);
            v34 = v42;
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 27) + 96LL))(
              *((_QWORD *)this + 27),
              3,
              v42);
            ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
          }
LABEL_68:
          v7 = 0;
          v38 = 1;
          goto LABEL_69;
        }
        if ( *((_QWORD *)this + 15) )
        {
          TickCount = ATL::CFileTime::GetTickCount(v43);
          v26 = *(_QWORD *)TickCount - *(_QWORD *)&v41;
          v27 = *v11;
          v28 = (*v11)[3];
          if ( !*(_DWORD *)(v28 - 16) )
            v28 = v27[1];
          v29 = v27[2];
          if ( !*(_DWORD *)(v29 - 16) )
            v29 = *v27;
          v30 = v26 / 0x2710;
          v31 = (v26 / 0x2710 * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
          (*(void (__fastcall **)(_QWORD, unsigned __int64, _QWORD, __int64, __int64))(**((_QWORD **)this + 15) + 152LL))(
            *((_QWORD *)this + 15),
            (((v30 - v31) >> 1) + v31) >> 6,
            v38,
            v29,
            v28);
        }
        if ( v38 != 3 )
          break;
        if ( *((_DWORD *)this + 6) == 13 )
          goto LABEL_69;
        v32 = *((_QWORD *)this + 27);
        if ( v32 )
          (*(void (__fastcall **)(__int64, __int64 *, __int64, __int64, __int64))(*(_QWORD *)v32 + 80LL))(
            v32,
            *v11,
            (*v11)[14] + 112LL * *((unsigned int *)this + 52),
            6,
            (*v11)[5]);
        if ( !WaitForSingleObject(*((HANDLE *)this + 9), 1000 * *a2) )
          return 2147500036LL;
      }
      v8 = (_QWORD *)*((_QWORD *)this + 27);
      if ( v8 )
      {
        v33 = 2;
        if ( v38 != 1 )
          v33 = 5;
        (*(void (__fastcall **)(_QWORD *, __int64 *, __int64, __int64, __int64))(*v8 + 80LL))(
          v8,
          *v11,
          (*v11)[14] + 112LL * *((unsigned int *)this + 52),
          v33,
          (*v11)[5]);
      }
      if ( v38 == 2 )
      {
        *((_DWORD *)*v11 + 24) = 7;
        *((_DWORD *)*v11 + 25) = 7;
        *((_DWORD *)*v11 + 61) = -2146895610;
      }
LABEL_69:
      if ( !v11[9] )
        goto LABEL_74;
      v8 = (_QWORD *)*v11[8];
      if ( *(_DWORD *)(v8[2] + 96LL) != 6 )
      {
        v11 = (__int64 **)v8[2];
        continue;
      }
      break;
    }
    if ( *(__int64 ***)this != v11 )
    {
      v11 = *(__int64 ***)this;
      continue;
    }
    break;
  }
LABEL_74:
  v35 = *((_QWORD *)this + 27);
  if ( v38 == 1 )
  {
    *((_WORD *)this + 46) = 5;
    if ( v35 )
      (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 80LL))(
        v35,
        **((_QWORD **)this + 25),
        *(_QWORD *)(**((_QWORD **)this + 25) + 112LL) + 112LL * *((unsigned int *)this + 52),
        0,
        0);
  }
  else
  {
    v12 = 2;
    *((_WORD *)this + 46) = 2;
    if ( v35 )
      (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64, _QWORD))(*(_QWORD *)v35 + 80LL))(
        v35,
        **((_QWORD **)this + 25),
        *(_QWORD *)(**((_QWORD **)this + 25) + 112LL) + 112LL * *((unsigned int *)this + 52),
        1,
        0);
    v7 = -2146895610;
  }
  if ( (byte_180041BC1 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, StopNDFValidate, v9, 1, v43);
  v36 = *((_QWORD *)this + 15);
  if ( v36 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v36 + 208LL))(
      v36,
      *(_QWORD *)(**((_QWORD **)this + 25) + 112LL) + 112LL * *((unsigned int *)this + 52),
      *(unsigned int *)(**((_QWORD **)this + 25) + 216LL),
      v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f4dc  mov     [rsp-38h+arg_10], rbx
0x18000f4e1  push    rbp
0x18000f4e2  push    rsi
0x18000f4e3  push    rdi
0x18000f4e4  push    r12
0x18000f4e6  push    r13
0x18000f4e8  push    r14
0x18000f4ea  push    r15
0x18000f4ec  mov     rbp, rsp
0x18000f4ef  sub     rsp, 70h
0x18000f4f3  mov     rax, cs:__security_cookie
0x18000f4fa  xor     rax, rsp
0x18000f4fd  mov     [rbp+var_8], rax
0x18000f501  mov     r12, rdx
0x18000f504  mov     rdi, rcx
0x18000f507  cmp     qword ptr [rcx+0C8h], 0
0x18000f50f  jnz     short loc_18000F53C
0x18000f511  mov     rcx, [rcx+0D8h]
0x18000f518  test    rcx, rcx
0x18000f51b  jz      short loc_18000F535
0x18000f51d  mov     rax, [rcx]
0x18000f520  lea     r8, aNothingToValid; "Nothing to Validate, skipping validatio"...
0x18000f527  mov     edx, 3
0x18000f52c  mov     rax, [rax+60h]
0x18000f530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f535  xor     eax, eax
0x18000f537  jmp     loc_18000FB09
0x18000f53c  test    cs:byte_180041BC1, 4
0x18000f543  jz      short loc_18000F560
0x18000f545  lea     rax, [rbp+var_18]
0x18000f549  mov     [rsp+70h+var_50], rax
0x18000f54e  mov     r9d, 1
0x18000f554  lea     rdx, StartNDFValidate
0x18000f55b  call    McGenEventWrite_EventWriteTransfer
0x18000f560  mov     [rbp+var_40], 1
0x18000f567  xor     r14d, r14d
0x18000f56a  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x18000f56f  mov     r13, rax
0x18000f572  mov     rsi, [rdi+0C8h]
0x18000f579  lea     ebx, [r14+2]
0x18000f57d  lea     r15d, [r14+5]
0x18000f581  cmp     [rbp+var_40], 1
0x18000f585  jnz     loc_18000FA14
0x18000f58b  mov     dword ptr [rsi+60h], 6
0x18000f592  cmp     qword ptr [rdi+50h], 0
0x18000f597  jz      loc_18000F6C5
0x18000f59d  test    r13, r13
0x18000f5a0  jz      loc_18000F6C5
0x18000f5a6  mov     rcx, [r13+18h]
0x18000f5aa  test    rcx, rcx
0x18000f5ad  jz      loc_18000F6C5
0x18000f5b3  mov     rax, [rsi]
0x18000f5b6  mov     rbx, [rax+10h]
0x18000f5ba  cmp     dword ptr [rbx-10h], 0
0x18000f5be  jnz     short loc_18000F5C3
0x18000f5c0  mov     rbx, [rax]
0x18000f5c3  mov     [rbp+var_30], 0
0x18000f5cb  mov     rax, [rcx]
0x18000f5ce  lea     r8, [rbp+var_30]
0x18000f5d2  mov     rdx, rbx
0x18000f5d5  mov     rax, [rax+18h]
0x18000f5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5de  mov     edx, eax
0x18000f5e0  test    eax, eax
0x18000f5e2  js      loc_18000F67E
0x18000f5e8  mov     [rbp+pv], 0
0x18000f5f0  mov     rcx, [rbp+var_30]
0x18000f5f4  mov     rax, [rcx]
0x18000f5f7  lea     rdx, [rbp+pv]
0x18000f5fb  mov     rax, [rax+40h]
0x18000f5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f604  mov     ebx, eax
0x18000f606  test    eax, eax
0x18000f608  js      short loc_18000F654
0x18000f60a  mov     r8, [rbp+pv]
0x18000f60e  mov     edx, 0CAh; unsigned __int16 *
0x18000f613  mov     rcx, [rdi+50h]; this
0x18000f617  call    ?SetProgress@DiagnosticsClient@@QEAAJPEBGZZ; DiagnosticsClient::SetProgress(ushort const *,...)
0x18000f61c  mov     ebx, eax
0x18000f61e  test    eax, eax
0x18000f620  jns     short loc_18000F648
0x18000f622  mov     rcx, [rdi+0D8h]
0x18000f629  test    rcx, rcx
0x18000f62c  jz      short loc_18000F646
0x18000f62e  mov     rax, [rcx]
0x18000f631  mov     r9d, ebx
0x18000f634  lea     r8, aCouldNotUpdate; "Could not update the progress string. H"...
0x18000f63b  xor     edx, edx
0x18000f63d  mov     rax, [rax+68h]
0x18000f641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f646  xor     ebx, ebx
0x18000f648  mov     rcx, [rbp+pv]; pv
0x18000f64c  call    cs:__imp_CoTaskMemFree
0x18000f652  jmp     short loc_18000F678
0x18000f654  mov     rcx, [rdi+0D8h]
0x18000f65b  test    rcx, rcx
0x18000f65e  jz      short loc_18000F678
0x18000f660  mov     rax, [rcx]
0x18000f663  mov     r9d, ebx
0x18000f666  lea     r8, aCouldNotRetrie; "Could not retrieve the current HC's pro"...
0x18000f66d  xor     edx, edx
0x18000f66f  mov     rax, [rax+68h]
0x18000f673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f678  test    ebx, ebx
0x18000f67a  jns     short loc_18000F6B7
0x18000f67c  jmp     short loc_18000F6A6
0x18000f67e  mov     rcx, [rdi+0D8h]
0x18000f685  test    rcx, rcx
0x18000f688  jz      short loc_18000F6A6
0x18000f68a  mov     rax, [rcx]
0x18000f68d  mov     dword ptr [rsp+70h+var_50], edx
0x18000f691  mov     r9, rbx
0x18000f694  lea     r8, aWarningHelperc; "Warning: HelperClass '%s' not found in "...
0x18000f69b  xor     edx, edx
0x18000f69d  mov     rax, [rax+68h]
0x18000f6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6a6  lea     rdx, dword_180033E1C; unsigned __int16 *
0x18000f6ad  mov     rcx, [rdi+50h]; this
0x18000f6b1  call    ?SetProgress@DiagnosticsClient@@QEAAJPEBGZZ; DiagnosticsClient::SetProgress(ushort const *,...)
0x18000f6b6  nop
0x18000f6b7  lea     rcx, [rbp+var_30]
0x18000f6bb  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18000f6c0  mov     ebx, 2
0x18000f6c5  cmp     dword ptr [rdi+18h], 0Dh
0x18000f6c9  jz      loc_18000F9E7
0x18000f6cf  lea     rcx, [rbp+var_28]
0x18000f6d3  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x18000f6d8  test    cs:byte_180041BC1, bl
0x18000f6de  jz      short loc_18000F6FD
0x18000f6e0  mov     rax, [rsi]
0x18000f6e3  mov     r8, [rax+10h]
0x18000f6e7  cmp     dword ptr [r8-10h], 0
0x18000f6ec  jnz     short loc_18000F6F1
0x18000f6ee  mov     r8, [rax]
0x18000f6f1  lea     rdx, StartNDFHCValidate
0x18000f6f8  call    McTemplateU0z_EventWriteTransfer
0x18000f6fd  mov     rax, [rsi]
0x18000f700  cmp     dword ptr [rax+0E4h], 0
0x18000f707  jge     short loc_18000F724
0x18000f709  mov     rcx, [rdi+50h]
0x18000f70d  mov     rax, [rcx]
0x18000f710  mov     rax, [rax+38h]
0x18000f714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f719  mov     r14d, eax
0x18000f71c  test    eax, eax
0x18000f71e  js      short loc_18000F764
0x18000f720  mov     bl, 1
0x18000f722  jmp     short loc_18000F72B
0x18000f724  xor     bl, bl
0x18000f726  test    r14d, r14d
0x18000f729  js      short loc_18000F75F
0x18000f72b  mov     rax, [rsi]
0x18000f72e  mov     rcx, [rax+48h]
0x18000f732  mov     rax, [rcx]
0x18000f735  lea     r9, [rbp+var_40]
0x18000f739  mov     r8, r12
0x18000f73c  mov     edx, [rsi+1Ch]
0x18000f73f  mov     rax, [rax+50h]
0x18000f743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f748  mov     r14d, eax
0x18000f74b  test    bl, bl
0x18000f74d  jz      short loc_18000F75F
0x18000f74f  mov     rcx, [rdi+50h]
0x18000f753  mov     rax, [rcx]
0x18000f756  mov     rax, [rax+40h]
0x18000f75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f75f  mov     ebx, 2
0x18000f764  test    cs:byte_180041BC1, bl
0x18000f76a  jz      short loc_18000F789
0x18000f76c  mov     rax, [rsi]
0x18000f76f  mov     r8, [rax+10h]
0x18000f773  cmp     dword ptr [r8-10h], 0
0x18000f778  jnz     short loc_18000F77D
0x18000f77a  mov     r8, [rax]
0x18000f77d  lea     rdx, StopNDFHCValidate
0x18000f784  call    McTemplateU0z_EventWriteTransfer
0x18000f789  cmp     r14d, 80004001h
0x18000f790  jz      loc_18000F9A5
0x18000f796  test    r14d, r14d
0x18000f799  js      loc_18000F91C
0x18000f79f  cmp     qword ptr [rdi+78h], 0
0x18000f7a4  jz      loc_18000F843
0x18000f7aa  lea     rcx, [rbp+var_18]
0x18000f7ae  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x18000f7b3  mov     edx, [rax+4]
0x18000f7b6  shl     rdx, 20h
0x18000f7ba  mov     eax, [rax]
0x18000f7bc  or      rdx, rax
0x18000f7bf  mov     ecx, dword ptr [rbp+var_28+4]
0x18000f7c2  shl     rcx, 20h
0x18000f7c6  mov     eax, dword ptr [rbp+var_28]
0x18000f7c9  or      rcx, rax
0x18000f7cc  sub     rdx, rcx
0x18000f7cf  mov     r11, [rdi+78h]
0x18000f7d3  mov     rax, [r11]
0x18000f7d6  mov     rbx, [rax+98h]
0x18000f7dd  mov     rax, [rsi]
0x18000f7e0  mov     rcx, [rax+18h]
0x18000f7e4  cmp     dword ptr [rcx-10h], 0
0x18000f7e8  jnz     short loc_18000F7EE
0x18000f7ea  mov     rcx, [rax+8]
0x18000f7ee  mov     r9, [rax+10h]
0x18000f7f2  cmp     dword ptr [r9-10h], 0
0x18000f7f7  jnz     short loc_18000F7FC
0x18000f7f9  mov     r9, [rax]
0x18000f7fc  mov     rax, 346DC5D63886594Bh
0x18000f806  mul     rdx
0x18000f809  mov     r10, rdx
0x18000f80c  shr     r10, 0Bh
0x18000f810  mov     rax, 47AE147AE147AE15h
0x18000f81a  mul     r10
0x18000f81d  sub     r10, rdx
0x18000f820  shr     r10, 1
0x18000f823  add     rdx, r10
0x18000f826  shr     rdx, 6
0x18000f82a  mov     [rsp+70h+var_50], rcx
0x18000f82f  mov     r8d, [rbp+var_40]
0x18000f833  mov     rcx, r11
0x18000f836  mov     rax, rbx
0x18000f839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f83e  mov     ebx, 2
0x18000f843  cmp     [rbp+var_40], 3
0x18000f847  jnz     short loc_18000F8AF
0x18000f849  cmp     dword ptr [rdi+18h], 0Dh
0x18000f84d  jz      loc_18000F9E7
0x18000f853  mov     rcx, [rdi+0D8h]
0x18000f85a  test    rcx, rcx
0x18000f85d  jz      short loc_18000F88B
0x18000f85f  mov     rdx, [rsi]
0x18000f862  mov     r9, [rcx]
0x18000f865  mov     eax, [rdi+0D0h]
0x18000f86b  imul    r8, rax, 70h ; 'p'
0x18000f86f  add     r8, [rdx+70h]
0x18000f873  mov     rax, [r9+50h]
0x18000f877  mov     r9, [rdx+28h]
0x18000f87b  mov     [rsp+70h+var_50], r9
0x18000f880  mov     r9d, 6
0x18000f886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88b  imul    edx, [r12], 3E8h; dwMilliseconds
0x18000f893  mov     rcx, [rdi+48h]; hHandle
0x18000f897  call    cs:__imp_WaitForSingleObject
0x18000f89d  test    eax, eax
0x18000f89f  jnz     loc_18000F6C5
0x18000f8a5  mov     eax, 80004004h
0x18000f8aa  jmp     loc_18000FB09
0x18000f8af  mov     rcx, [rdi+0D8h]
0x18000f8b6  test    rcx, rcx
0x18000f8b9  jz      short loc_18000F8F0
0x18000f8bb  mov     rdx, [rsi]
0x18000f8be  mov     r9, [rdx+28h]
0x18000f8c2  mov     rax, [rcx]
0x18000f8c5  mov     r10, [rax+50h]
0x18000f8c9  mov     eax, [rdi+0D0h]
0x18000f8cf  imul    r8, rax, 70h ; 'p'
0x18000f8d3  add     r8, [rdx+70h]
0x18000f8d7  mov     [rsp+70h+var_50], r9
0x18000f8dc  mov     rax, r10
0x18000f8df  cmp     [rbp+var_40], 1
0x18000f8e3  mov     r9d, ebx
0x18000f8e6  jz      short loc_18000F8EB
0x18000f8e8  mov     r9d, r15d
0x18000f8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f0  cmp     [rbp+var_40], ebx
0x18000f8f3  jnz     loc_18000F9E7
0x18000f8f9  mov     rax, [rsi]
0x18000f8fc  mov     edx, 7
0x18000f901  mov     [rax+60h], edx
0x18000f904  mov     rax, [rsi]
0x18000f907  mov     [rax+64h], edx
0x18000f90a  mov     rax, [rsi]
0x18000f90d  mov     dword ptr [rax+0F4h], 8008F906h
0x18000f917  jmp     loc_18000F9E7
0x18000f91c  mov     rcx, [rdi+0D8h]
0x18000f923  test    rcx, rcx
0x18000f926  jz      loc_18000F9DD
0x18000f92c  mov     rdx, [rsi]
0x18000f92f  mov     r9, [rcx]
0x18000f932  mov     eax, [rdi+0D0h]
0x18000f938  imul    r8, rax, 70h ; 'p'
0x18000f93c  add     r8, [rdx+70h]
0x18000f940  mov     rax, [r9+50h]
0x18000f944  mov     r9, [rdx+28h]
0x18000f948  mov     [rsp+70h+var_50], r9
0x18000f94d  mov     r9d, 4
0x18000f953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f958  lea     rcx, [rbp+var_20]
0x18000f95c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000f961  nop
0x18000f962  mov     r8d, r14d
0x18000f965  lea     rdx, aValidationFail; "Validation failed. HRESULT=0x%x"
0x18000f96c  lea     rcx, [rbp+var_20]
0x18000f970  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000f975  mov     rcx, [rdi+0D8h]
0x18000f97c  mov     rax, [rcx]
0x18000f97f  mov     rbx, [rbp+var_20]
0x18000f983  mov     r8, rbx
0x18000f986  mov     edx, 3
0x18000f98b  mov     rax, [rax+60h]
0x18000f98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f994  nop
  ... truncated ...
```
