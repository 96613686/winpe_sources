# ProblemInstance::ProcessDiagFiles(DiagnosticsClient *)

- ea: `0x180013938`
- end: `0x180013c36`
- name: `?ProcessDiagFiles@ProblemInstance@@QEAAJPEAVDiagnosticsClient@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(ProblemInstance *__hidden this, struct DiagnosticsClient *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ede4`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x18000bca0`
- `0x180013938`
- `0x18001b3a8`
- `0x1800263e0`
- `0x18002c80e`
- `0x18002f010`

## import_xrefs

- `wdi!WdiAddFileToInstance` at `0x180013a08`
- `wdi!WdiAddFileToInstance` at `0x180013a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013be9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013be9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c16`

## pseudocode

```c
__int64 __fastcall ProblemInstance::ProcessDiagFiles(ProblemInstance *this, struct DiagnosticsClient *a2)
{
  int v5; // esi
  void *v6; // r15
  unsigned int v7; // r14d
  char *v8; // rbx
  int v9; // eax
  _QWORD *v10; // r9
  __int64 v11; // rbx
  _QWORD *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r13
  _QWORD *v15; // r8
  __int64 v16; // rbx
  _DWORD *v17; // rax
  __int64 v18; // [rsp+20h] [rbp-40h]
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v22; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+58h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v23 = 0;
  pv = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID *))(**((_QWORD **)this + 9) + 120LL))(
         *((_QWORD *)this + 9),
         &v23,
         &pv);
  if ( v5 >= 0 && pv )
  {
    if ( !*((_QWORD *)this + 36) && NetworkDiagnosticsEngine::Instance() )
      *((_QWORD *)this + 36) = *(_QWORD *)NetworkDiagnosticsEngine::Instance();
    v6 = pv;
    v7 = 0;
    if ( v23 )
    {
      v8 = (char *)pv;
      do
      {
        if ( *((_DWORD *)v8 + 2) == 10 )
        {
          if ( !wcscmp_0(*(const wchar_t **)pv, L"DiagnosisDataFile") )
          {
            if ( *((_QWORD *)v8 + 2) )
            {
              v9 = WdiAddFileToInstance(*((_QWORD *)a2 + 1));
              v5 = v9;
              if ( *((_QWORD *)this + 36) )
              {
                if ( v9 < 0 )
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v19);
                  v12 = (_QWORD *)*((_QWORD *)this + 2);
                  if ( !*((_DWORD *)v12 - 4) )
                    v12 = *(_QWORD **)this;
                  LODWORD(v18) = v5;
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                    &v19,
                    L"Failed when adding the file %s from %s to the Wdi instance. (HRESULT 0x%x)",
                    *((_QWORD *)pv + 2),
                    v12,
                    v18);
                  v11 = v19;
                  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 36) + 96LL))(
                    *((_QWORD *)this + 36),
                    0,
                    v19);
                }
                else
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
                  v10 = (_QWORD *)*((_QWORD *)this + 2);
                  if ( !*((_DWORD *)v10 - 4) )
                    v10 = *(_QWORD **)this;
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                    &v25,
                    L"Succesfully added file %s from %s to the Wdi instance.",
                    *((_QWORD *)pv + 2),
                    v10);
                  v11 = v25;
                  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 36) + 96LL))(
                    *((_QWORD *)this + 36),
                    0,
                    v25);
                }
                ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
              }
            }
          }
          CoTaskMemFree(*((LPVOID *)pv + 2));
        }
        else if ( *((_DWORD *)v8 + 2) == 11 && !wcscmp_0(*(const wchar_t **)pv, L"rootcauseid") )
        {
          v13 = *((_QWORD *)this + 42);
          if ( v13 )
          {
            v22 = *((_OWORD *)v8 + 1);
            (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v13 + 160LL))(v13, &v22);
          }
          *((_OWORD *)this + 16) = *((_OWORD *)pv + 1);
          if ( *((_QWORD *)this + 36) )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v20);
            v22 = *((_OWORD *)this + 16);
            AttributeConverter::GuidToString(&v22, &v20);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v21);
            v14 = v20;
            v15 = (_QWORD *)*((_QWORD *)this + 2);
            if ( !*((_DWORD *)v15 - 4) )
              v15 = *(_QWORD **)this;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              v21,
              L"%s returned Root Cause GUID %s",
              v15,
              v20);
            v16 = v21[0];
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 36) + 112LL))(
              *((_QWORD *)this + 36),
              0,
              v21[0],
              *((_QWORD *)this + 5));
            ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
          }
        }
        CoTaskMemFree(*(LPVOID *)pv);
        v17 = pv;
        if ( *((_DWORD *)pv + 2) == 14 )
        {
          CoTaskMemFree(*((LPVOID *)pv + 3));
          v17 = pv;
        }
        v17[2] = 0;
        ++v7;
        v8 = (char *)pv + 144;
        pv = (char *)pv + 144;
      }
      while ( v7 < v23 );
    }
    CoTaskMemFree(v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013938  mov     [rsp-38h+arg_0], rbx
0x18001393d  push    rbp
0x18001393e  push    rsi
0x18001393f  push    rdi
0x180013940  push    r12
0x180013942  push    r13
0x180013944  push    r14
0x180013946  push    r15
0x180013948  mov     rbp, rsp
0x18001394b  sub     rsp, 60h
0x18001394f  mov     r12, rdx
0x180013952  mov     rdi, rcx
0x180013955  xor     r13d, r13d
0x180013958  test    rdx, rdx
0x18001395b  jnz     short loc_180013967
0x18001395d  mov     eax, 80070057h
0x180013962  jmp     loc_180013C1E
0x180013967  mov     [rbp+arg_8], r13d
0x18001396b  mov     [rbp+pv], r13
0x18001396f  mov     rcx, [rcx+48h]
0x180013973  mov     rax, [rcx]
0x180013976  lea     r8, [rbp+pv]
0x18001397a  lea     rdx, [rbp+arg_8]
0x18001397e  mov     rax, [rax+78h]
0x180013982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013987  mov     esi, eax
0x180013989  test    eax, eax
0x18001398b  js      loc_180013C1C
0x180013991  cmp     [rbp+pv], r13
0x180013995  jz      loc_180013C1C
0x18001399b  cmp     [rdi+120h], r13
0x1800139a2  jnz     short loc_1800139BD
0x1800139a4  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x1800139a9  test    rax, rax
0x1800139ac  jz      short loc_1800139BD
0x1800139ae  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x1800139b3  mov     rcx, [rax]
0x1800139b6  mov     [rdi+120h], rcx
0x1800139bd  mov     r15, [rbp+pv]
0x1800139c1  mov     r14d, r13d
0x1800139c4  cmp     [rbp+arg_8], r13d
0x1800139c8  jbe     loc_180013C13
0x1800139ce  mov     rbx, r15
0x1800139d1  cmp     dword ptr [rbx+8], 0Ah
0x1800139d5  jnz     loc_180013ADB
0x1800139db  lea     rdx, aDiagnosisdataf; "DiagnosisDataFile"
0x1800139e2  mov     rcx, [rbp+pv]
0x1800139e6  mov     rcx, [rcx]; String1
0x1800139e9  call    wcscmp_0
0x1800139ee  test    eax, eax
0x1800139f0  jnz     loc_180013AC8
0x1800139f6  mov     rdx, [rbx+10h]
0x1800139fa  test    rdx, rdx
0x1800139fd  jz      loc_180013AC8
0x180013a03  mov     rcx, [r12+8]
0x180013a08  call    cs:__imp_WdiAddFileToInstance
0x180013a0e  mov     esi, eax
0x180013a10  cmp     [rdi+120h], r13
0x180013a17  jz      loc_180013AC8
0x180013a1d  test    eax, eax
0x180013a1f  js      short loc_180013A6F
0x180013a21  lea     rcx, [rbp+arg_18]
0x180013a25  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013a2a  nop
0x180013a2b  mov     r9, [rdi+10h]
0x180013a2f  cmp     [r9-10h], r13d
0x180013a33  jnz     short loc_180013A38
0x180013a35  mov     r9, [rdi]
0x180013a38  mov     r8, [rbp+pv]
0x180013a3c  mov     r8, [r8+10h]
0x180013a40  lea     rdx, aSuccesfullyAdd; "Succesfully added file %s from %s to th"...
0x180013a47  lea     rcx, [rbp+arg_18]
0x180013a4b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013a50  mov     rcx, [rdi+120h]
0x180013a57  mov     rax, [rcx]
0x180013a5a  mov     rbx, [rbp+arg_18]
0x180013a5e  mov     r8, rbx
0x180013a61  xor     edx, edx
0x180013a63  mov     rax, [rax+60h]
0x180013a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a6c  nop
0x180013a6d  jmp     short loc_180013ABF
0x180013a6f  lea     rcx, [rbp+var_30]
0x180013a73  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013a78  nop
0x180013a79  mov     r9, [rdi+10h]
0x180013a7d  cmp     [r9-10h], r13d
0x180013a81  jnz     short loc_180013A86
0x180013a83  mov     r9, [rdi]
0x180013a86  mov     [rsp+60h+var_40], esi
0x180013a8a  mov     r8, [rbp+pv]
0x180013a8e  mov     r8, [r8+10h]
0x180013a92  lea     rdx, aFailedWhenAddi; "Failed when adding the file %s from %s "...
0x180013a99  lea     rcx, [rbp+var_30]
0x180013a9d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013aa2  mov     rcx, [rdi+120h]
0x180013aa9  mov     rax, [rcx]
0x180013aac  mov     rbx, [rbp+var_30]
0x180013ab0  mov     r8, rbx
0x180013ab3  xor     edx, edx
0x180013ab5  mov     rax, [rax+60h]
0x180013ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013abe  nop
0x180013abf  lea     rcx, [rbx-18h]; this
0x180013ac3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013ac8  mov     rcx, [rbp+pv]
0x180013acc  mov     rcx, [rcx+10h]; pv
0x180013ad0  call    cs:__imp_CoTaskMemFree
0x180013ad6  jmp     loc_180013BCE
0x180013adb  cmp     dword ptr [rbx+8], 0Bh
0x180013adf  jnz     loc_180013BCE
0x180013ae5  lea     rdx, aRootcauseid; "rootcauseid"
0x180013aec  mov     rcx, [rbp+pv]
0x180013af0  mov     rcx, [rcx]; String1
0x180013af3  call    wcscmp_0
0x180013af8  test    eax, eax
0x180013afa  jnz     loc_180013BCE
0x180013b00  mov     rcx, [rdi+150h]
0x180013b07  test    rcx, rcx
0x180013b0a  jz      short loc_180013B28
0x180013b0c  movups  xmm0, xmmword ptr [rbx+10h]
0x180013b10  movdqu  [rbp+var_10], xmm0
0x180013b15  mov     rax, [rcx]
0x180013b18  lea     rdx, [rbp+var_10]
0x180013b1c  mov     rax, [rax+0A0h]
0x180013b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b28  mov     rax, [rbp+pv]
0x180013b2c  movups  xmm0, xmmword ptr [rax+10h]
0x180013b30  movdqu  xmmword ptr [rdi+100h], xmm0
0x180013b38  cmp     [rdi+120h], r13
0x180013b3f  jz      loc_180013BCE
0x180013b45  lea     rcx, [rbp+var_28]
0x180013b49  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013b4e  nop
0x180013b4f  movups  xmm0, xmmword ptr [rdi+100h]
0x180013b56  movdqu  [rbp+var_10], xmm0
0x180013b5b  lea     rdx, [rbp+var_28]
0x180013b5f  lea     rcx, [rbp+var_10]
0x180013b63  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180013b68  lea     rcx, [rbp+var_20]
0x180013b6c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013b71  nop
0x180013b72  mov     r13, [rbp+var_28]
0x180013b76  mov     r8, [rdi+10h]
0x180013b7a  cmp     dword ptr [r8-10h], 0
0x180013b7f  jnz     short loc_180013B84
0x180013b81  mov     r8, [rdi]
0x180013b84  mov     r9, r13
0x180013b87  lea     rdx, aSReturnedRootC; "%s returned Root Cause GUID %s"
0x180013b8e  lea     rcx, [rbp+var_20]
0x180013b92  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013b97  mov     rcx, [rdi+120h]
0x180013b9e  mov     rax, [rcx]
0x180013ba1  mov     r9, [rdi+28h]
0x180013ba5  mov     rbx, [rbp+var_20]
0x180013ba9  mov     r8, rbx
0x180013bac  xor     edx, edx
0x180013bae  mov     rax, [rax+70h]
0x180013bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb7  nop
0x180013bb8  lea     rcx, [rbx-18h]; this
0x180013bbc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013bc1  nop
0x180013bc2  lea     rcx, [r13-18h]; this
0x180013bc6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013bcb  xor     r13d, r13d
0x180013bce  mov     rcx, [rbp+pv]
0x180013bd2  mov     rcx, [rcx]; pv
0x180013bd5  call    cs:__imp_CoTaskMemFree
0x180013bdb  mov     rax, [rbp+pv]
0x180013bdf  cmp     dword ptr [rax+8], 0Eh
0x180013be3  jnz     short loc_180013BF3
0x180013be5  mov     rcx, [rax+18h]; pv
0x180013be9  call    cs:__imp_CoTaskMemFree
0x180013bef  mov     rax, [rbp+pv]
0x180013bf3  mov     [rax+8], r13d
0x180013bf7  inc     r14d
0x180013bfa  mov     rbx, [rbp+pv]
0x180013bfe  add     rbx, 90h
0x180013c05  mov     [rbp+pv], rbx
0x180013c09  cmp     r14d, [rbp+arg_8]
0x180013c0d  jb      loc_1800139D1
0x180013c13  mov     rcx, r15; pv
0x180013c16  call    cs:__imp_CoTaskMemFree
0x180013c1c  mov     eax, esi
0x180013c1e  mov     rbx, [rsp+60h+arg_0]
0x180013c26  add     rsp, 60h
0x180013c2a  pop     r15
0x180013c2c  pop     r14
0x180013c2e  pop     r13
0x180013c30  pop     r12
0x180013c32  pop     rdi
0x180013c33  pop     rsi
0x180013c34  pop     rbp
0x180013c35  retn
```
