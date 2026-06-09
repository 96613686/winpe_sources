# CSyncMLCmdGet::DoShallowGet(IConfigNode *,ushort * *)

- ea: `0x18000cfb0`
- end: `0x18000d504`
- name: `?DoShallowGet@CSyncMLCmdGet@@AEBAJPEAUIConfigNode@@PEAPEAG@Z`
- size: `1364`
- prototype: `__int64 __fastcall(CSyncMLCmdGet *__hidden this, struct IConfigNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x1800044e0`
- `0x18000cfb0`
- `0x180014330`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d4c2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d4c2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d289`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d289`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d33d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d376`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d39c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d33d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d376`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d39c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d028`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d028`
- `DMCmnUtils!InvStrCmpIW` at `0x18000d170`
- `DMCmnUtils!InvStrCmpIW` at `0x18000d170`
- `DMCmnUtils!BigStrcat` at `0x18000d2dc`
- `DMCmnUtils!BigStrcat` at `0x18000d35b`
- `DMCmnUtils!BigStrcat` at `0x18000d2dc`
- `DMCmnUtils!BigStrcat` at `0x18000d35b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d068`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d068`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSyncMLCmdGet::DoShallowGet(CSyncMLCmdGet *this, struct IConfigNode *a2, unsigned __int16 **a3)
{
  __int64 v3; // rax
  int v4; // edi
  __int64 (__fastcall *v7)(struct IConfigNode *, __int64 *); // rax
  unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // rsi
  HRESULT Instance; // ebx
  unsigned __int16 *v12; // rax
  __int64 v13; // rax
  const unsigned __int16 *v14; // rcx
  struct IConfigManager2URI *v15; // rdi
  int IsWmiQuery; // eax
  struct IConfigManager2URI *v17; // rcx
  int (__fastcall **v18)(struct IConfigManager2URI *, GUID *, struct IConfigManager2URI **); // rax
  __int64 v19; // rax
  __int64 v20; // r8
  BSTR v21; // rax
  int v23; // [rsp+30h] [rbp-69h] BYREF
  struct IConfigManager2URI *v24; // [rsp+38h] [rbp-61h] BYREF
  BSTR v25; // [rsp+40h] [rbp-59h] BYREF
  __int64 v26; // [rsp+48h] [rbp-51h] BYREF
  struct IConfigManager2URI *ppv; // [rsp+50h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-41h] BYREF
  __int64 v29; // [rsp+60h] [rbp-39h] BYREF
  HRESULT v30; // [rsp+68h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  char *v33; // [rsp+90h] [rbp-9h]
  int v34; // [rsp+98h] [rbp-1h]
  int v35; // [rsp+9Ch] [rbp+3h]
  HRESULT *v36; // [rsp+A0h] [rbp+7h]
  __int64 v37; // [rsp+A8h] [rbp+Fh]

  v3 = *(_QWORD *)a2;
  v4 = 0;
  v29 = 0;
  v26 = 0;
  ppv = 0;
  v7 = *(__int64 (__fastcall **)(struct IConfigNode *, __int64 *))(v3 + 192);
  bstrString = 0;
  v9 = 0;
  v25 = 0;
  v10 = 0;
  v23 = 0;
  Instance = v7(a2, &v29);
  if ( Instance >= 0 )
  {
    v12 = (unsigned __int16 *)LocalAlloc(0, 2u);
    v9 = v12;
    if ( !v12 )
    {
LABEL_3:
      Instance = -2147024882;
      goto LABEL_46;
    }
    *v12 = 0;
    Instance = CoCreateInstance(
                 &GUID_c196b2be_ba06_4049_8518_322e1e04282b,
                 0,
                 1u,
                 &GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30,
                 (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 176LL))(
                   ppv,
                   L"foo",
                   0);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v29 + 24LL))(
                     v29,
                     1,
                     &v26,
                     &v23);
        if ( Instance >= 0 )
        {
          if ( v23 == 1 )
          {
            while ( 1 )
            {
              SysFreeString(bstrString);
              bstrString = 0;
              SysFreeString(v25);
              v25 = 0;
              Instance = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 128LL))(v26, &bstrString);
              if ( Instance < 0 )
                goto LABEL_46;
              Instance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, BSTR, _QWORD))(*(_QWORD *)ppv + 192LL))(
                           ppv,
                           0,
                           bstrString,
                           0);
              if ( Instance < 0 )
                goto LABEL_46;
              v13 = *((_QWORD *)this + 9);
              if ( !v13 )
                goto LABEL_20;
              v14 = *(const unsigned __int16 **)(v13 + 24);
              v15 = ppv;
              if ( v14 )
              {
                if ( InvStrCmpIW(v14, L"1.0") )
                  break;
              }
              IsWmiQuery = CSyncMLCmd::IsWmiQuery(v15);
              v4 = 0;
              if ( IsWmiQuery != 1 )
                goto LABEL_20;
              v17 = ppv;
              v25 = 0;
              if ( !ppv )
                goto LABEL_35;
              v18 = *(int (__fastcall ***)(struct IConfigManager2URI *, GUID *, struct IConfigManager2URI **))ppv;
              v24 = 0;
              if ( (*v18)(ppv, &GUID_e8e62e9d_37fc_47a0_846a_29781dfa97d9, &v24) >= 0 )
                (*(void (__fastcall **)(struct IConfigManager2URI *, BSTR *))(*(_QWORD *)v24 + 24LL))(v24, &v25);
              if ( v24 )
              {
                (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v24 + 16LL))(v24);
                v24 = 0;
              }
LABEL_33:
              if ( !v25 )
              {
                v17 = ppv;
LABEL_35:
                Instance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v17 + 64LL))(
                             v17,
                             0,
                             0,
                             &v25);
              }
              if ( Instance < 0 )
                goto LABEL_46;
              v10 = BigStrcat(2u, v9, v25);
              if ( !v10 )
                goto LABEL_3;
              if ( v26 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                v26 = 0;
              }
              v23 = 0;
              Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v29 + 24LL))(
                           v29,
                           1,
                           &v26,
                           &v23);
              if ( Instance < 0 )
                goto LABEL_46;
              if ( v26 )
              {
                LocalFree(v9);
                v9 = v10;
                v10 = BigStrcat(2u, v10, L"/");
                if ( !v10 )
                  goto LABEL_3;
                LocalFree(v9);
                v9 = v10;
                v10 = 0;
              }
              if ( v23 != 1 )
                goto LABEL_45;
            }
            v4 = 0;
LABEL_20:
            v19 = *(_QWORD *)a2;
            v24 = 0;
            if ( (*(int (__fastcall **)(struct IConfigNode *, struct IConfigManager2URI **))(v19 + 120))(a2, &v24) >= 0 )
              v4 = CSyncMLCmd::IsWmiQuery(v24);
            if ( v24 )
            {
              (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v24 + 16LL))(v24);
              v24 = 0;
            }
            if ( v4 )
            {
              if ( !bstrString )
              {
                Instance = -2147024809;
                goto LABEL_46;
              }
              v20 = 0x7FFFFFFF;
              v21 = bstrString;
              do
              {
                if ( !*v21 )
                  break;
                ++v21;
                --v20;
              }
              while ( v20 );
              v4 = 0;
              Instance = -2147024809;
              if ( !v20 )
                goto LABEL_46;
              Instance = 0;
              v25 = SysAllocStringLen(bstrString, 0x7FFFFFFF - (int)v20);
              if ( !v25 )
                goto LABEL_3;
            }
            else
            {
              v4 = 0;
            }
            goto LABEL_33;
          }
LABEL_45:
          *a3 = v10;
          v10 = 0;
        }
      }
    }
  }
LABEL_46:
  LocalFree(v9);
  LocalFree(v10);
  SysFreeString(bstrString);
  SysFreeString(v25);
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v30 = Instance;
    v36 = &v30;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v37 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v33 = byte_18003684B;
    UserData.Reserved = 2;
    v34 = 25;
    v35 = 1;
    LODWORD(v24) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000cfb0  mov     [rsp-8+arg_18], rbx
0x18000cfb5  push    rbp
0x18000cfb6  push    rsi
0x18000cfb7  push    rdi
0x18000cfb8  push    r12
0x18000cfba  push    r13
0x18000cfbc  push    r14
0x18000cfbe  push    r15
0x18000cfc0  lea     rbp, [rsp-27h]
0x18000cfc5  sub     rsp, 0C0h
0x18000cfcc  mov     rax, cs:__security_cookie
0x18000cfd3  xor     rax, rsp
0x18000cfd6  mov     [rbp+57h+var_40], rax
0x18000cfda  mov     rax, [rdx]
0x18000cfdd  xor     edi, edi
0x18000cfdf  mov     r15, rdx
0x18000cfe2  mov     [rbp+57h+var_90], rdi
0x18000cfe6  mov     r13, rcx
0x18000cfe9  mov     [rbp+57h+var_A8], rdi
0x18000cfed  lea     rdx, [rbp+57h+var_90]
0x18000cff1  mov     [rbp+57h+var_A0], rdi
0x18000cff5  mov     rax, [rax+0C0h]
0x18000cffc  mov     rcx, r15
0x18000cfff  mov     r12, r8
0x18000d002  mov     [rbp+57h+bstrString], rdi
0x18000d006  mov     r14d, edi
0x18000d009  mov     [rbp+57h+var_B0], rdi
0x18000d00d  mov     esi, edi
0x18000d00f  mov     [rbp+57h+var_C0], edi
0x18000d012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d017  mov     ebx, eax
0x18000d019  test    eax, eax
0x18000d01b  js      loc_18000D399
0x18000d021  mov     edx, 2; uBytes
0x18000d026  xor     ecx, ecx; uFlags
0x18000d028  call    cs:__imp_LocalAlloc
0x18000d02f  nop     dword ptr [rax+rax+00h]
0x18000d034  mov     r14, rax
0x18000d037  test    rax, rax
0x18000d03a  jnz     short loc_18000D046
0x18000d03c  mov     ebx, 8007000Eh
0x18000d041  jmp     loc_18000D399
0x18000d046  mov     [rax], di
0x18000d049  lea     r9, _GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30; riid
0x18000d050  lea     rax, [rbp+57h+var_A0]
0x18000d054  xor     edx, edx; pUnkOuter
0x18000d056  mov     r8d, 1; dwClsContext
0x18000d05c  mov     [rsp+0F0h+ppv], rax; ppv
0x18000d061  lea     rcx, _GUID_c196b2be_ba06_4049_8518_322e1e04282b; rclsid
0x18000d068  call    cs:__imp_CoCreateInstance
0x18000d06f  nop     dword ptr [rax+rax+00h]
0x18000d074  mov     ebx, eax
0x18000d076  test    eax, eax
0x18000d078  js      loc_18000D399
0x18000d07e  mov     rcx, [rbp+57h+var_A0]
0x18000d082  lea     rdx, aFoo; "foo"
0x18000d089  xor     r8d, r8d
0x18000d08c  mov     rax, [rcx]
0x18000d08f  mov     rax, [rax+0B0h]
0x18000d096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d09b  mov     ebx, eax
0x18000d09d  test    eax, eax
0x18000d09f  js      loc_18000D399
0x18000d0a5  mov     rcx, [rbp+57h+var_90]
0x18000d0a9  lea     r9, [rbp+57h+var_C0]
0x18000d0ad  lea     r8, [rbp+57h+var_A8]
0x18000d0b1  mov     edx, 1
0x18000d0b6  mov     rax, [rcx]
0x18000d0b9  mov     rax, [rax+18h]
0x18000d0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0c2  mov     ebx, eax
0x18000d0c4  test    eax, eax
0x18000d0c6  js      loc_18000D399
0x18000d0cc  cmp     [rbp+57h+var_C0], 1
0x18000d0d0  jnz     loc_18000D392
0x18000d0d6  nop     word ptr [rax+rax+00000000h]
0x18000d0e0  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000d0e4  call    cs:__imp_SysFreeString
0x18000d0eb  nop     dword ptr [rax+rax+00h]
0x18000d0f0  mov     rcx, [rbp+57h+var_B0]; bstrString
0x18000d0f4  mov     [rbp+57h+bstrString], rdi
0x18000d0f8  call    cs:__imp_SysFreeString
0x18000d0ff  nop     dword ptr [rax+rax+00h]
0x18000d104  mov     rcx, [rbp+57h+var_A8]
0x18000d108  lea     rdx, [rbp+57h+bstrString]
0x18000d10c  mov     [rbp+57h+var_B0], rdi
0x18000d110  mov     rax, [rcx]
0x18000d113  mov     rax, [rax+80h]
0x18000d11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11f  mov     ebx, eax
0x18000d121  test    eax, eax
0x18000d123  js      loc_18000D399
0x18000d129  mov     rcx, [rbp+57h+var_A0]
0x18000d12d  xor     r9d, r9d
0x18000d130  mov     r8, [rbp+57h+bstrString]
0x18000d134  xor     edx, edx
0x18000d136  mov     rax, [rcx]
0x18000d139  mov     rax, [rax+0C0h]
0x18000d140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d145  mov     ebx, eax
0x18000d147  test    eax, eax
0x18000d149  js      loc_18000D399
0x18000d14f  mov     rax, [r13+48h]
0x18000d153  test    rax, rax
0x18000d156  jz      loc_18000D1F6
0x18000d15c  mov     rcx, [rax+18h]
0x18000d160  mov     rdi, [rbp+57h+var_A0]
0x18000d164  test    rcx, rcx
0x18000d167  jz      short loc_18000D180
0x18000d169  lea     rdx, a10; "1.0"
0x18000d170  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18000d177  nop     dword ptr [rax+rax+00h]
0x18000d17c  test    eax, eax
0x18000d17e  jnz     short loc_18000D1F4
0x18000d180  mov     rcx, rdi; struct IConfigManager2URI *
0x18000d183  call    ?IsWmiQuery@CSyncMLCmd@@KAHPEAUIConfigManager2URI@@@Z; CSyncMLCmd::IsWmiQuery(IConfigManager2URI *)
0x18000d188  xor     edi, edi
0x18000d18a  cmp     eax, 1
0x18000d18d  jnz     short loc_18000D1F6
0x18000d18f  mov     rcx, [rbp+57h+var_A0]
0x18000d193  mov     [rbp+57h+var_B0], rdi
0x18000d197  test    rcx, rcx
0x18000d19a  jz      loc_18000D2B1
0x18000d1a0  mov     rax, [rcx]
0x18000d1a3  lea     r8, [rbp+57h+var_B8]
0x18000d1a7  lea     rdx, _GUID_e8e62e9d_37fc_47a0_846a_29781dfa97d9
0x18000d1ae  mov     [rbp+57h+var_B8], rdi
0x18000d1b2  mov     rax, [rax]
0x18000d1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ba  test    eax, eax
0x18000d1bc  js      short loc_18000D1D2
0x18000d1be  mov     rcx, [rbp+57h+var_B8]
0x18000d1c2  lea     rdx, [rbp+57h+var_B0]
0x18000d1c6  mov     rax, [rcx]
0x18000d1c9  mov     rax, [rax+18h]
0x18000d1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d2  mov     rcx, [rbp+57h+var_B8]
0x18000d1d6  test    rcx, rcx
0x18000d1d9  jz      loc_18000D2A6
0x18000d1df  mov     rax, [rcx]
0x18000d1e2  mov     rax, [rax+10h]
0x18000d1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1eb  mov     [rbp+57h+var_B8], rdi
0x18000d1ef  jmp     loc_18000D2A6
0x18000d1f4  xor     edi, edi
0x18000d1f6  mov     rax, [r15]
0x18000d1f9  lea     rdx, [rbp+57h+var_B8]
0x18000d1fd  mov     rcx, r15
0x18000d200  mov     [rbp+57h+var_B8], 0
0x18000d208  mov     rax, [rax+78h]
0x18000d20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d211  test    eax, eax
0x18000d213  js      short loc_18000D220
0x18000d215  mov     rcx, [rbp+57h+var_B8]; struct IConfigManager2URI *
0x18000d219  call    ?IsWmiQuery@CSyncMLCmd@@KAHPEAUIConfigManager2URI@@@Z; CSyncMLCmd::IsWmiQuery(IConfigManager2URI *)
0x18000d21e  mov     edi, eax
0x18000d220  mov     rcx, [rbp+57h+var_B8]
0x18000d224  test    rcx, rcx
0x18000d227  jz      short loc_18000D23D
0x18000d229  mov     rdx, [rcx]
0x18000d22c  mov     rax, [rdx+10h]
0x18000d230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d235  mov     [rbp+57h+var_B8], 0
0x18000d23d  test    edi, edi
0x18000d23f  jz      short loc_18000D2A4
0x18000d241  mov     rcx, [rbp+57h+bstrString]; strIn
0x18000d245  test    rcx, rcx
0x18000d248  jz      loc_18000D4F8
0x18000d24e  mov     r8d, 7FFFFFFFh
0x18000d254  mov     rax, rcx
0x18000d257  cmp     word ptr [rax], 0
0x18000d25b  jz      short loc_18000D267
0x18000d25d  add     rax, 2
0x18000d261  sub     r8, 1
0x18000d265  jnz     short loc_18000D257
0x18000d267  xor     edi, edi
0x18000d269  mov     ebx, 80070057h
0x18000d26e  test    r8, r8
0x18000d271  mov     edx, 7FFFFFFFh
0x18000d276  cmovnz  ebx, edi
0x18000d279  sub     rdx, r8
0x18000d27c  test    r8, r8
0x18000d27f  cmovz   rdx, rdi; ui
0x18000d283  jz      loc_18000D399
0x18000d289  call    cs:__imp_SysAllocStringLen
0x18000d290  nop     dword ptr [rax+rax+00h]
0x18000d295  mov     [rbp+57h+var_B0], rax
0x18000d299  test    rax, rax
0x18000d29c  jz      loc_18000D03C
0x18000d2a2  jmp     short loc_18000D2A6
0x18000d2a4  xor     edi, edi
0x18000d2a6  cmp     [rbp+57h+var_B0], 0
0x18000d2ab  jnz     short loc_18000D2C8
0x18000d2ad  mov     rcx, [rbp+57h+var_A0]
0x18000d2b1  mov     rax, [rcx]
0x18000d2b4  lea     r9, [rbp+57h+var_B0]
0x18000d2b8  xor     r8d, r8d
0x18000d2bb  xor     edx, edx
0x18000d2bd  mov     rax, [rax+40h]
0x18000d2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2c6  mov     ebx, eax
0x18000d2c8  test    ebx, ebx
0x18000d2ca  js      loc_18000D399
0x18000d2d0  mov     r8, [rbp+57h+var_B0]
0x18000d2d4  mov     rdx, r14
0x18000d2d7  mov     ecx, 2
0x18000d2dc  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18000d2e3  nop     dword ptr [rax+rax+00h]
0x18000d2e8  mov     rsi, rax
0x18000d2eb  test    rax, rax
0x18000d2ee  jz      loc_18000D03C
0x18000d2f4  mov     rcx, [rbp+57h+var_A8]
0x18000d2f8  test    rcx, rcx
0x18000d2fb  jz      short loc_18000D30D
0x18000d2fd  mov     rdx, [rcx]
0x18000d300  mov     rax, [rdx+10h]
0x18000d304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d309  mov     [rbp+57h+var_A8], rdi
0x18000d30d  mov     rcx, [rbp+57h+var_90]
0x18000d311  lea     r9, [rbp+57h+var_C0]
0x18000d315  mov     [rbp+57h+var_C0], edi
0x18000d318  lea     r8, [rbp+57h+var_A8]
0x18000d31c  mov     edx, 1
0x18000d321  mov     rax, [rcx]
0x18000d324  mov     rax, [rax+18h]
0x18000d328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d32d  mov     ebx, eax
0x18000d32f  test    eax, eax
0x18000d331  js      short loc_18000D399
0x18000d333  cmp     [rbp+57h+var_A8], 0
0x18000d338  jz      short loc_18000D388
0x18000d33a  mov     rcx, r14; hMem
0x18000d33d  call    cs:__imp_LocalFree
0x18000d344  nop     dword ptr [rax+rax+00h]
0x18000d349  lea     r8, asc_180032DA8; "/"
0x18000d350  mov     rdx, rsi
0x18000d353  mov     ecx, 2
0x18000d358  mov     r14, rsi
0x18000d35b  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18000d362  nop     dword ptr [rax+rax+00h]
0x18000d367  mov     rsi, rax
0x18000d36a  test    rax, rax
0x18000d36d  jz      loc_18000D03C
0x18000d373  mov     rcx, r14; hMem
0x18000d376  call    cs:__imp_LocalFree
0x18000d37d  nop     dword ptr [rax+rax+00h]
0x18000d382  mov     r14, rsi
0x18000d385  mov     rsi, rdi
0x18000d388  cmp     [rbp+57h+var_C0], 1
0x18000d38c  jz      loc_18000D0E0
0x18000d392  mov     [r12], rsi
0x18000d396  mov     rsi, rdi
0x18000d399  mov     rcx, r14; hMem
0x18000d39c  call    cs:__imp_LocalFree
0x18000d3a3  nop     dword ptr [rax+rax+00h]
0x18000d3a8  mov     rcx, rsi; hMem
0x18000d3ab  call    cs:__imp_LocalFree
0x18000d3b2  nop     dword ptr [rax+rax+00h]
0x18000d3b7  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000d3bb  call    cs:__imp_SysFreeString
0x18000d3c2  nop     dword ptr [rax+rax+00h]
0x18000d3c7  mov     rcx, [rbp+57h+var_B0]; bstrString
0x18000d3cb  call    cs:__imp_SysFreeString
0x18000d3d2  nop     dword ptr [rax+rax+00h]
0x18000d3d7  mov     rcx, [rbp+57h+var_90]
0x18000d3db  test    rcx, rcx
0x18000d3de  jz      short loc_18000D3F0
0x18000d3e0  mov     rax, [rcx]
0x18000d3e3  mov     rax, [rax+10h]
0x18000d3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3ec  mov     [rbp+57h+var_90], rdi
0x18000d3f0  mov     rcx, [rbp+57h+var_A8]
0x18000d3f4  test    rcx, rcx
0x18000d3f7  jz      short loc_18000D409
0x18000d3f9  mov     rax, [rcx]
0x18000d3fc  mov     rax, [rax+10h]
0x18000d400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d405  mov     [rbp+57h+var_A8], rdi
0x18000d409  mov     rcx, [rbp+57h+var_A0]
0x18000d40d  test    rcx, rcx
0x18000d410  jz      short loc_18000D422
0x18000d412  mov     rax, [rcx]
0x18000d415  mov     rax, [rax+10h]
0x18000d419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d41e  mov     [rbp+57h+var_A0], rdi
0x18000d422  mov     eax, cs:dword_18003E048
0x18000d428  cmp     eax, 5
0x18000d42b  jbe     loc_18000D4CE
0x18000d431  lea     rax, [rbp+57h+var_88]
0x18000d435  mov     [rbp+57h+var_88], ebx
0x18000d438  mov     [rbp+57h+var_50], rax
0x18000d43c  lea     rcx, _TraceLoggingMetadata
0x18000d443  movzx   eax, cs:word_180036841
0x18000d44a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000d44e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000d451  xor     r9d, r9d; RelatedActivityId
0x18000d454  mov     rax, cs:off_18003E050
0x18000d45b  xor     r8d, r8d; ActivityId
0x18000d45e  mov     [rbp+57h+var_70.Ptr], rax
0x18000d462  mov     [rbp+57h+var_48], 4
  ... truncated ...
```
