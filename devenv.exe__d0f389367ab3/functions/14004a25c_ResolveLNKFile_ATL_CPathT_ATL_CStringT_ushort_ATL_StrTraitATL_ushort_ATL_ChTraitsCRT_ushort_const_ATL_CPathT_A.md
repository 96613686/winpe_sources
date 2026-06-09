# ResolveLNKFile(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &,ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)

- ea: `0x14004a25c`
- end: `0x14004a4d2`
- name: `?ResolveLNKFile@@YAJAEBV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@AEAV12@@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400467d0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x140003160`
- `0x140004950`
- `0x140033ab0`
- `0x14004a25c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004a3c0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004a3c0`
- `ole32!CoUninitialize` at `0x14004a469`
- `ole32!CoUninitialize` at `0x14004a469`
- `ole32!CoInitialize` at `0x14004a29f`
- `ole32!CoInitialize` at `0x14004a29f`
- `ole32!CoCreateInstance` at `0x14004a2da`
- `ole32!CoCreateInstance` at `0x14004a2da`
- `SHLWAPI!PathFileExistsW` at `0x14004a2a8`
- `SHLWAPI!PathFileExistsW` at `0x14004a2a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ResolveLNKFile(LPCWSTR *a1, __int64 a2)
{
  HRESULT v4; // edi
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v6; // rax
  const wchar_t *v7; // rbx
  LPVOID v8; // rdi
  int v9; // eax
  _QWORD *v10; // rdx
  const wchar_t *v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[600]; // [rsp+50h] [rbp-B0h] BYREF

  ppv = 0;
  v15 = 0;
  CoInitialize(0);
  if ( !PathFileExistsW(*a1) )
  {
    v4 = -2147287038;
    goto LABEL_21;
  }
  v4 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v15);
    if ( v4 >= 0 )
    {
      if ( v15 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, _QWORD))(*(_QWORD *)v15 + 40LL))(v15, *a1, 0);
        if ( v4 < 0 )
          goto LABEL_21;
        v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 152LL))(ppv, 0, 0);
        if ( v4 < 0 )
          goto LABEL_21;
        Instance = ATL::CAtlStringMgr::GetInstance();
        if ( !Instance )
          ATL::AtlThrowImpl(-2147467259);
        v6 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
        v7 = (const wchar_t *)(v6 + 24);
        v12 = (const wchar_t *)(v6 + 24);
        v8 = ppv;
        if ( ((1 - *(_DWORD *)(v6 + 16)) | (*(_DWORD *)(v6 + 12) - 260)) < 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v12, 260);
          v7 = v12;
        }
        v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64, _BYTE *, int))(*(_QWORD *)v8 + 24LL))(
               v8,
               v7,
               260,
               v16,
               1);
        v9 = wcsnlen(v7, *((int *)v7 - 3));
        if ( v9 < 0 || v9 > *((_DWORD *)v7 - 3) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v7 - 4) = v9;
        v7[v9] = 0;
        if ( v4 < 0 )
        {
          if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
          }
          goto LABEL_21;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v13,
          v7);
        ATL::CSimpleStringT<unsigned short,0>::operator=(a2, &v13);
        v10 = (_QWORD *)(v13 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
        }
      }
      v4 = 0;
    }
  }
LABEL_21:
  CoUninitialize();
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14004a25c  mov     [rsp-8+arg_10], rbx
0x14004a261  mov     [rsp-8+arg_18], rsi
0x14004a266  push    rbp
0x14004a267  push    rdi
0x14004a268  push    r14
0x14004a26a  lea     rbp, [rsp-1B0h]
0x14004a272  sub     rsp, 2B0h
0x14004a279  mov     rax, cs:__security_cookie
0x14004a280  xor     rax, rsp
0x14004a283  mov     [rbp+1C0h+var_18], rax
0x14004a28a  mov     rsi, rdx
0x14004a28d  mov     rbx, rcx
0x14004a290  xor     r14d, r14d
0x14004a293  mov     [rsp+2C0h+var_280], r14
0x14004a298  mov     [rsp+2C0h+var_278], r14
0x14004a29d  xor     ecx, ecx; pvReserved
0x14004a29f  call    cs:__imp_CoInitialize
0x14004a2a5  mov     rcx, [rbx]; pszPath
0x14004a2a8  call    cs:__imp_PathFileExistsW
0x14004a2ae  test    eax, eax
0x14004a2b0  jnz     short loc_14004A2BC
0x14004a2b2  mov     edi, 80030002h
0x14004a2b7  jmp     loc_14004A469
0x14004a2bc  lea     rax, [rsp+2C0h+var_280]
0x14004a2c1  mov     [rsp+2C0h+ppv], rax; ppv
0x14004a2c6  lea     r9, IID_IShellLinkW; riid
0x14004a2cd  xor     edx, edx; pUnkOuter
0x14004a2cf  lea     r8d, [rdx+1]; dwClsContext
0x14004a2d3  lea     rcx, CLSID_ShellLink; rclsid
0x14004a2da  call    cs:__imp_CoCreateInstance
0x14004a2e0  mov     edi, eax
0x14004a2e2  test    eax, eax
0x14004a2e4  js      loc_14004A469
0x14004a2ea  mov     rcx, [rsp+2C0h+var_280]
0x14004a2ef  mov     rax, [rcx]
0x14004a2f2  lea     r8, [rsp+2C0h+var_278]
0x14004a2f7  lea     rdx, IID_IPersistFile
0x14004a2fe  call    qword ptr [rax]
0x14004a300  mov     edi, eax
0x14004a302  test    eax, eax
0x14004a304  js      loc_14004A469
0x14004a30a  mov     rcx, [rsp+2C0h+var_278]
0x14004a30f  test    rcx, rcx
0x14004a312  jz      loc_14004A466
0x14004a318  mov     rax, [rcx]
0x14004a31b  xor     r8d, r8d
0x14004a31e  mov     rdx, [rbx]
0x14004a321  call    qword ptr [rax+28h]
0x14004a324  mov     edi, eax
0x14004a326  test    eax, eax
0x14004a328  js      loc_14004A469
0x14004a32e  mov     rcx, [rsp+2C0h+var_280]
0x14004a333  mov     rax, [rcx]
0x14004a336  xor     r8d, r8d
0x14004a339  xor     edx, edx
0x14004a33b  call    qword ptr [rax+98h]
0x14004a341  mov     edi, eax
0x14004a343  test    eax, eax
0x14004a345  js      loc_14004A469
0x14004a34b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004a350  mov     rcx, rax
0x14004a353  test    rax, rax
0x14004a356  jz      loc_14004A4B9
0x14004a35c  mov     rax, [rax]
0x14004a35f  call    qword ptr [rax+18h]
0x14004a362  lea     rbx, [rax+18h]
0x14004a366  mov     [rsp+2C0h+var_290], rbx
0x14004a36b  mov     rdi, [rsp+2C0h+var_280]
0x14004a370  mov     edx, 1
0x14004a375  sub     edx, [rbx-8]
0x14004a378  mov     eax, [rbx-0Ch]
0x14004a37b  sub     eax, 104h
0x14004a380  or      eax, edx
0x14004a382  jge     short loc_14004A398
0x14004a384  mov     edx, 104h
0x14004a389  lea     rcx, [rsp+2C0h+var_290]
0x14004a38e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14004a393  mov     rbx, [rsp+2C0h+var_290]
0x14004a398  mov     rax, [rdi]
0x14004a39b  mov     dword ptr [rsp+2C0h+ppv], 1
0x14004a3a3  lea     r9, [rsp+2C0h+var_270]
0x14004a3a8  mov     r8d, 104h
0x14004a3ae  mov     rdx, rbx
0x14004a3b1  mov     rcx, rdi
0x14004a3b4  call    qword ptr [rax+18h]
0x14004a3b7  mov     edi, eax
0x14004a3b9  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x14004a3bd  mov     rcx, rbx; Source
0x14004a3c0  call    cs:__imp_wcsnlen
0x14004a3c6  test    eax, eax
0x14004a3c8  js      loc_14004A4C7
0x14004a3ce  cmp     eax, [rbx-0Ch]
0x14004a3d1  jg      loc_14004A4C7
0x14004a3d7  mov     [rbx-10h], eax
0x14004a3da  cdqe
0x14004a3dc  mov     [rbx+rax*2], r14w
0x14004a3e1  test    edi, edi
0x14004a3e3  jns     short loc_14004A407
0x14004a3e5  lea     rdx, [rbx-18h]
0x14004a3e9  or      esi, 0FFFFFFFFh
0x14004a3ec  mov     eax, esi
0x14004a3ee  lock xadd [rdx+10h], eax
0x14004a3f3  add     eax, esi
0x14004a3f5  test    eax, eax
0x14004a3f7  jg      short loc_14004A469
0x14004a3f9  lfence
0x14004a3fc  mov     rcx, [rdx]
0x14004a3ff  mov     rax, [rcx]
0x14004a402  call    qword ptr [rax+8]
0x14004a405  jmp     short loc_14004A469
0x14004a407  mov     rdx, rbx
0x14004a40a  lea     rcx, [rsp+2C0h+var_288]
0x14004a40f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004a414  nop
0x14004a415  lea     rdx, [rsp+2C0h+var_288]
0x14004a41a  mov     rcx, rsi
0x14004a41d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004a422  nop
0x14004a423  mov     rdx, [rsp+2C0h+var_288]
0x14004a428  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004a42c  or      esi, 0FFFFFFFFh
0x14004a42f  mov     eax, esi
0x14004a431  lock xadd [rdx+10h], eax
0x14004a436  add     eax, esi
0x14004a438  test    eax, eax
0x14004a43a  jg      short loc_14004A449
0x14004a43c  lfence
0x14004a43f  mov     rcx, [rdx]
0x14004a442  mov     rax, [rcx]
0x14004a445  call    qword ptr [rax+8]
0x14004a448  nop
0x14004a449  lea     rdx, [rbx-18h]
0x14004a44d  mov     eax, esi
0x14004a44f  lock xadd [rdx+10h], eax
0x14004a454  add     eax, esi
0x14004a456  test    eax, eax
0x14004a458  jg      short loc_14004A466
0x14004a45a  lfence
0x14004a45d  mov     rcx, [rdx]
0x14004a460  mov     rax, [rcx]
0x14004a463  call    qword ptr [rax+8]
0x14004a466  mov     edi, r14d
0x14004a469  call    cs:__imp_CoUninitialize
0x14004a46f  mov     rcx, [rsp+2C0h+var_278]
0x14004a474  test    rcx, rcx
0x14004a477  jz      short loc_14004A480
0x14004a479  mov     rdx, [rcx]
0x14004a47c  call    qword ptr [rdx+10h]
0x14004a47f  nop
0x14004a480  mov     rcx, [rsp+2C0h+var_280]
0x14004a485  test    rcx, rcx
0x14004a488  jz      short loc_14004A490
0x14004a48a  mov     rdx, [rcx]
0x14004a48d  call    qword ptr [rdx+10h]
0x14004a490  mov     eax, edi
0x14004a492  mov     rcx, [rbp+1C0h+var_18]
0x14004a499  xor     rcx, rsp; StackCookie
0x14004a49c  call    __security_check_cookie
0x14004a4a1  lea     r11, [rsp+2C0h+var_10]
0x14004a4a9  mov     rbx, [r11+30h]
0x14004a4ad  mov     rsi, [r11+38h]
0x14004a4b1  mov     rsp, r11
0x14004a4b4  pop     r14
0x14004a4b6  pop     rdi
0x14004a4b7  pop     rbp
0x14004a4b8  retn
0x14004a4b9  mov     ecx, 80004005h; int
0x14004a4be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004a4c4  jmp     short $+2
0x14004a4c6  nop
0x14004a4c7  mov     ecx, 80070057h; int
0x14004a4cc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
