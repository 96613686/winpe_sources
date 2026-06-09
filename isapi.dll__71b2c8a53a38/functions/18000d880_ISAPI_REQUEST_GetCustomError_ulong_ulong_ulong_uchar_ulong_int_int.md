# ISAPI_REQUEST::GetCustomError(ulong,ulong,ulong,uchar *,ulong *,int *,int *)

- ea: `0x18000d880`
- end: `0x18000dd2d`
- name: `?GetCustomError@ISAPI_REQUEST@@UEAAJKKKPEAEPEAKPEAH2@Z`
- size: `1197`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, unsigned int, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, int *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000d880`
- `0x180012476`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x18000dbf6`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x18000dbf6`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000dc33`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000dc33`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x18000dc0b`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x18000dc27`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x18000dc0b`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x18000dc27`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000dd05`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000dd05`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000d911`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000d911`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000dba2`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000dbe2`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000dba2`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000dbe2`

## string_xrefs

- `0x18000d9fc`: `defaultPath`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::GetCustomError(
        ISAPI_REQUEST *this,
        int a2,
        int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        int *a7,
        int *a8)
{
  __int64 (__fastcall ***v9)(_QWORD); // rax
  __int64 v10; // rbx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rax
  int v12; // edi
  __int64 v13; // rcx
  unsigned int i; // ebx
  unsigned int v15; // eax
  unsigned int CB; // ebx
  char *Str; // rax
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+7Ch] [rbp-84h]
  unsigned int v30; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v31; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v32; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[56]; // [rsp+98h] [rbp-68h] BYREF
  char v34[64]; // [rsp+D0h] [rbp-30h] BYREF

  v29 = a3;
  v28 = a2;
  v30 = a4;
  v27 = 0;
  v20 = 0;
  v25 = 0;
  v32 = 0;
  v26 = 0;
  v21 = 0;
  v19 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v31 = 0;
  STRA::STRA((STRA *)v33, v34, 0x40u);
  v9 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 160LL))(*((_QWORD *)this + 3));
  v10 = (**v9)(v9);
  v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v12 = (**v11)(v11, &IID_INativeConfigurationSystem, &v27);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v27 + 24LL))(
            v27,
            L"system.webServer/httpErrors",
            v10,
            &v20,
            0,
            0);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v20 + 48LL))(
              v20,
              L"defaultResponseMode",
              &v25,
              0,
              0);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v20 + 64LL))(
                v20,
                L"defaultPath",
                &v32,
                0,
                0);
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 40LL))(v20, &v26);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 24LL))(v26, &v21);
            if ( v12 >= 0 )
            {
              v13 = v19;
              for ( i = 0; i < v21; ++i )
              {
                v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, i, &v19);
                if ( v12 < 0 )
                  goto LABEL_34;
                v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v19 + 48LL))(
                        v19,
                        L"statusCode",
                        &v22,
                        0,
                        0);
                if ( v12 < 0 )
                  goto LABEL_34;
                if ( v22 == v28 )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v19 + 48LL))(
                          v19,
                          L"subStatusCode",
                          &v23,
                          0,
                          0);
                  if ( v12 < 0 )
                    goto LABEL_34;
                  if ( v23 == v29 )
                  {
                    v13 = v19;
                    break;
                  }
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                v13 = 0;
                v19 = 0;
              }
              if ( v13 )
              {
                v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v13 + 48LL))(
                        v13,
                        L"responseMode",
                        &v24,
                        0,
                        0);
                if ( v12 < 0 )
                  goto LABEL_34;
                if ( v24 == 1 )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v19 + 64LL))(
                          v19,
                          L"path",
                          &v31,
                          0,
                          0);
                  if ( v12 < 0 )
                    goto LABEL_34;
                  v12 = STRA::CopyW((STRA *)v33, v31);
                  if ( v12 < 0 )
                    goto LABEL_34;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                v19 = 0;
              }
              else if ( v32 )
              {
                if ( v25 == 1 )
                {
                  v12 = STRA::CopyW((STRA *)v33, v32);
                  if ( v12 < 0 )
                    goto LABEL_34;
                }
              }
              if ( STRA::IsEmpty((STRA *)v33) )
              {
                v12 = -2147024894;
              }
              else
              {
                v15 = STRA::QueryCB((STRA *)v33) + 1;
                *a6 = v15;
                if ( v15 <= v30 )
                {
                  CB = STRA::QueryCB((STRA *)v33);
                  Str = STRA::QueryStr((STRA *)v33);
                  memcpy_0(a5, Str, CB);
                  a5[*a6 - 1] = 0;
                  if ( a7 )
                    *a7 = 0;
                  if ( a8 )
                    *a8 = ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 112LL))(*((_QWORD *)this + 3))
                         & 8) == 0;
                  *((_DWORD *)this + 16) = 1;
                }
                else
                {
                  v12 = -2147024774;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_34:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  STRA::~STRA((STRA *)v33);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d880  push    rbp
0x18000d882  push    rbx
0x18000d883  push    rsi
0x18000d884  push    rdi
0x18000d885  push    r12
0x18000d887  push    r13
0x18000d889  push    r14
0x18000d88b  push    r15
0x18000d88d  lea     rbp, [rsp-28h]
0x18000d892  sub     rsp, 128h
0x18000d899  mov     rax, cs:__security_cookie
0x18000d8a0  xor     rax, rsp
0x18000d8a3  mov     [rbp+60h+var_50], rax
0x18000d8a7  mov     r13, [rbp+60h+arg_20]
0x18000d8ae  xor     eax, eax
0x18000d8b0  mov     r12, [rbp+60h+arg_28]
0x18000d8b7  mov     rsi, rcx
0x18000d8ba  mov     r15, [rbp+60h+arg_30]
0x18000d8c1  lea     rcx, [rbp+60h+var_C8]
0x18000d8c5  mov     r14, [rbp+60h+arg_38]
0x18000d8cc  mov     [rsp+160h+var_E4], r8d
0x18000d8d1  lea     r8d, [rax+40h]
0x18000d8d5  mov     [rsp+160h+var_E8], edx
0x18000d8d9  lea     rdx, [rbp+60h+var_90]
0x18000d8dd  mov     [rbp+60h+var_E0], r9d
0x18000d8e1  mov     [rsp+160h+var_F0], rax
0x18000d8e6  mov     [rsp+160h+var_118], rax
0x18000d8eb  mov     [rsp+160h+var_100], eax
0x18000d8ef  mov     [rbp+60h+var_D0], rax
0x18000d8f3  mov     [rsp+160h+var_F8], rax
0x18000d8f8  mov     [rsp+160h+var_110], eax
0x18000d8fc  mov     [rsp+160h+var_120], rax
0x18000d901  mov     [rsp+160h+var_10C], eax
0x18000d905  mov     [rsp+160h+var_108], eax
0x18000d909  mov     [rsp+160h+var_104], eax
0x18000d90d  mov     [rbp+60h+var_D8], rax
0x18000d911  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000d917  mov     rcx, [rsi+18h]
0x18000d91b  mov     rax, [rcx]
0x18000d91e  mov     rax, [rax+0A0h]
0x18000d925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92a  mov     rdx, rax
0x18000d92d  mov     rcx, [rax]
0x18000d930  mov     rax, [rcx]
0x18000d933  mov     rcx, rdx
0x18000d936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d93b  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000d942  mov     rbx, rax
0x18000d945  mov     rdx, [rcx]
0x18000d948  mov     rax, [rdx+38h]
0x18000d94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d951  mov     r9, rax
0x18000d954  lea     r8, [rsp+160h+var_F0]
0x18000d959  lea     rdx, IID_INativeConfigurationSystem
0x18000d960  mov     rcx, [rax]
0x18000d963  mov     rax, [rcx]
0x18000d966  mov     rcx, r9
0x18000d969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d96e  mov     edi, eax
0x18000d970  test    eax, eax
0x18000d972  js      loc_18000DC85
0x18000d978  mov     rcx, [rsp+160h+var_F0]
0x18000d97d  lea     r9, [rsp+160h+var_118]
0x18000d982  mov     [rsp+160h+var_138], 0
0x18000d98b  lea     rdx, aSystemWebserve_1; "system.webServer/httpErrors"
0x18000d992  mov     r8, rbx
0x18000d995  mov     [rsp+160h+var_140], 0
0x18000d99e  mov     rax, [rcx]
0x18000d9a1  mov     rax, [rax+18h]
0x18000d9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9aa  mov     edi, eax
0x18000d9ac  test    eax, eax
0x18000d9ae  js      loc_18000DC85
0x18000d9b4  mov     rcx, [rsp+160h+var_118]
0x18000d9b9  lea     r8, [rsp+160h+var_100]
0x18000d9be  xor     r9d, r9d
0x18000d9c1  mov     [rsp+160h+var_140], 0
0x18000d9ca  lea     rdx, aDefaultrespons; "defaultResponseMode"
0x18000d9d1  mov     rax, [rcx]
0x18000d9d4  mov     rax, [rax+30h]
0x18000d9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9dd  mov     edi, eax
0x18000d9df  test    eax, eax
0x18000d9e1  js      loc_18000DC85
0x18000d9e7  mov     rcx, [rsp+160h+var_118]
0x18000d9ec  lea     r8, [rbp+60h+var_D0]
0x18000d9f0  xor     r9d, r9d
0x18000d9f3  mov     [rsp+160h+var_140], 0
0x18000d9fc  lea     rdx, aDefaultpath; "defaultPath"
0x18000da03  mov     rax, [rcx]
0x18000da06  mov     rax, [rax+40h]
0x18000da0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da0f  mov     edi, eax
0x18000da11  test    eax, eax
0x18000da13  js      loc_18000DC85
0x18000da19  mov     rcx, [rsp+160h+var_118]
0x18000da1e  lea     rdx, [rsp+160h+var_F8]
0x18000da23  mov     rax, [rcx]
0x18000da26  mov     rax, [rax+28h]
0x18000da2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da2f  mov     edi, eax
0x18000da31  test    eax, eax
0x18000da33  js      loc_18000DC85
0x18000da39  mov     rcx, [rsp+160h+var_F8]
0x18000da3e  lea     rdx, [rsp+160h+var_110]
0x18000da43  mov     rax, [rcx]
0x18000da46  mov     rax, [rax+18h]
0x18000da4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da4f  mov     edi, eax
0x18000da51  test    eax, eax
0x18000da53  js      loc_18000DC85
0x18000da59  mov     rcx, [rsp+160h+var_120]
0x18000da5e  xor     ebx, ebx
0x18000da60  cmp     ebx, [rsp+160h+var_110]
0x18000da64  jnb     loc_18000DB2A
0x18000da6a  mov     rcx, [rsp+160h+var_F8]
0x18000da6f  lea     r8, [rsp+160h+var_120]
0x18000da74  mov     edx, ebx
0x18000da76  mov     rax, [rcx]
0x18000da79  mov     rax, [rax+20h]
0x18000da7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da82  mov     edi, eax
0x18000da84  test    eax, eax
0x18000da86  js      loc_18000DC85
0x18000da8c  mov     rcx, [rsp+160h+var_120]
0x18000da91  lea     r8, [rsp+160h+var_10C]
0x18000da96  xor     r9d, r9d
0x18000da99  mov     [rsp+160h+var_140], 0
0x18000daa2  lea     rdx, aStatuscode; "statusCode"
0x18000daa9  mov     rax, [rcx]
0x18000daac  mov     rax, [rax+30h]
0x18000dab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dab5  mov     edi, eax
0x18000dab7  test    eax, eax
0x18000dab9  js      loc_18000DC85
0x18000dabf  mov     eax, [rsp+160h+var_E8]
0x18000dac3  cmp     [rsp+160h+var_10C], eax
0x18000dac7  jnz     short loc_18000DB06
0x18000dac9  mov     rcx, [rsp+160h+var_120]
0x18000dace  lea     r8, [rsp+160h+var_108]
0x18000dad3  xor     r9d, r9d
0x18000dad6  mov     [rsp+160h+var_140], 0
0x18000dadf  lea     rdx, aSubstatuscode; "subStatusCode"
0x18000dae6  mov     rax, [rcx]
0x18000dae9  mov     rax, [rax+30h]
0x18000daed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf2  mov     edi, eax
0x18000daf4  test    eax, eax
0x18000daf6  js      loc_18000DC85
0x18000dafc  mov     eax, [rsp+160h+var_E4]
0x18000db00  cmp     [rsp+160h+var_108], eax
0x18000db04  jz      short loc_18000DB25
0x18000db06  mov     rcx, [rsp+160h+var_120]
0x18000db0b  mov     rax, [rcx]
0x18000db0e  mov     rax, [rax+10h]
0x18000db12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db17  xor     ecx, ecx
0x18000db19  mov     [rsp+160h+var_120], rcx
0x18000db1e  inc     ebx
0x18000db20  jmp     loc_18000DA60
0x18000db25  mov     rcx, [rsp+160h+var_120]
0x18000db2a  test    rcx, rcx
0x18000db2d  jz      loc_18000DBCE
0x18000db33  mov     rax, [rcx]
0x18000db36  lea     r8, [rsp+160h+var_104]
0x18000db3b  xor     r9d, r9d
0x18000db3e  mov     [rsp+160h+var_140], 0
0x18000db47  lea     rdx, aResponsemode; "responseMode"
0x18000db4e  mov     rax, [rax+30h]
0x18000db52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db57  mov     edi, eax
0x18000db59  test    eax, eax
0x18000db5b  js      loc_18000DC85
0x18000db61  cmp     [rsp+160h+var_104], 1
0x18000db66  jnz     short loc_18000DBB2
0x18000db68  mov     rcx, [rsp+160h+var_120]
0x18000db6d  lea     r8, [rbp+60h+var_D8]
0x18000db71  xor     r9d, r9d
0x18000db74  mov     [rsp+160h+var_140], 0
0x18000db7d  lea     rdx, aPath; "path"
0x18000db84  mov     rax, [rcx]
0x18000db87  mov     rax, [rax+40h]
0x18000db8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db90  mov     edi, eax
0x18000db92  test    eax, eax
0x18000db94  js      loc_18000DC85
0x18000db9a  mov     rdx, [rbp+60h+var_D8]
0x18000db9e  lea     rcx, [rbp+60h+var_C8]
0x18000dba2  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000dba8  mov     edi, eax
0x18000dbaa  test    eax, eax
0x18000dbac  js      loc_18000DC85
0x18000dbb2  mov     rcx, [rsp+160h+var_120]
0x18000dbb7  mov     rax, [rcx]
0x18000dbba  mov     rax, [rax+10h]
0x18000dbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc3  mov     [rsp+160h+var_120], 0
0x18000dbcc  jmp     short loc_18000DBF2
0x18000dbce  mov     rdx, [rbp+60h+var_D0]
0x18000dbd2  test    rdx, rdx
0x18000dbd5  jz      short loc_18000DBF2
0x18000dbd7  cmp     [rsp+160h+var_100], 1
0x18000dbdc  jnz     short loc_18000DBF2
0x18000dbde  lea     rcx, [rbp+60h+var_C8]
0x18000dbe2  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000dbe8  mov     edi, eax
0x18000dbea  test    eax, eax
0x18000dbec  js      loc_18000DC85
0x18000dbf2  lea     rcx, [rbp+60h+var_C8]
0x18000dbf6  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x18000dbfc  test    al, al
0x18000dbfe  jz      short loc_18000DC07
0x18000dc00  mov     edi, 80070002h
0x18000dc05  jmp     short loc_18000DC85
0x18000dc07  lea     rcx, [rbp+60h+var_C8]
0x18000dc0b  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x18000dc11  inc     eax
0x18000dc13  mov     [r12], eax
0x18000dc17  cmp     eax, [rbp+60h+var_E0]
0x18000dc1a  jbe     short loc_18000DC23
0x18000dc1c  mov     edi, 8007007Ah
0x18000dc21  jmp     short loc_18000DC85
0x18000dc23  lea     rcx, [rbp+60h+var_C8]
0x18000dc27  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x18000dc2d  lea     rcx, [rbp+60h+var_C8]
0x18000dc31  mov     ebx, eax
0x18000dc33  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000dc39  mov     r8d, ebx; Size
0x18000dc3c  mov     rcx, r13; void *
0x18000dc3f  mov     rdx, rax; Src
0x18000dc42  call    memcpy_0
0x18000dc47  mov     eax, [r12]
0x18000dc4b  dec     eax
0x18000dc4d  mov     byte ptr [rax+r13], 0
0x18000dc52  test    r15, r15
0x18000dc55  jz      short loc_18000DC5E
0x18000dc57  mov     dword ptr [r15], 0
0x18000dc5e  test    r14, r14
0x18000dc61  jz      short loc_18000DC7E
0x18000dc63  mov     rcx, [rsi+18h]
0x18000dc67  mov     rax, [rcx]
0x18000dc6a  mov     rax, [rax+70h]
0x18000dc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc73  shr     eax, 3
0x18000dc76  not     eax
0x18000dc78  and     eax, 1
0x18000dc7b  mov     [r14], eax
0x18000dc7e  mov     dword ptr [rsi+40h], 1
0x18000dc85  mov     rcx, [rsp+160h+var_120]
0x18000dc8a  test    rcx, rcx
0x18000dc8d  jz      short loc_18000DCA4
0x18000dc8f  mov     rax, [rcx]
0x18000dc92  mov     rax, [rax+10h]
0x18000dc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc9b  mov     [rsp+160h+var_120], 0
0x18000dca4  mov     rcx, [rsp+160h+var_F8]
0x18000dca9  test    rcx, rcx
0x18000dcac  jz      short loc_18000DCC3
0x18000dcae  mov     rax, [rcx]
0x18000dcb1  mov     rax, [rax+10h]
0x18000dcb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcba  mov     [rsp+160h+var_F8], 0
0x18000dcc3  mov     rcx, [rsp+160h+var_118]
0x18000dcc8  test    rcx, rcx
0x18000dccb  jz      short loc_18000DCE2
0x18000dccd  mov     rax, [rcx]
0x18000dcd0  mov     rax, [rax+10h]
0x18000dcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd9  mov     [rsp+160h+var_118], 0
0x18000dce2  mov     rcx, [rsp+160h+var_F0]
0x18000dce7  test    rcx, rcx
0x18000dcea  jz      short loc_18000DD01
0x18000dcec  mov     rax, [rcx]
0x18000dcef  mov     rax, [rax+10h]
0x18000dcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf8  mov     [rsp+160h+var_F0], 0
0x18000dd01  lea     rcx, [rbp+60h+var_C8]
0x18000dd05  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000dd0b  mov     eax, edi
0x18000dd0d  mov     rcx, [rbp+60h+var_50]
0x18000dd11  xor     rcx, rsp; StackCookie
0x18000dd14  call    __security_check_cookie
0x18000dd19  add     rsp, 128h
0x18000dd20  pop     r15
0x18000dd22  pop     r14
0x18000dd24  pop     r13
0x18000dd26  pop     r12
0x18000dd28  pop     rdi
0x18000dd29  pop     rsi
0x18000dd2a  pop     rbx
0x18000dd2b  pop     rbp
0x18000dd2c  retn
```
