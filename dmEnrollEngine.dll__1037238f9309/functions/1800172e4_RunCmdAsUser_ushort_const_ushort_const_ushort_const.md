# RunCmdAsUser(ushort const *,ushort const *,ushort const *)

- ea: `0x1800172e4`
- end: `0x180017885`
- name: `?RunCmdAsUser@@YAJPEBG00@Z`
- size: `1441`
- prototype: `__int64 __fastcall(char *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180066f10`

## callees

- `0x18000efc4`
- `0x180011938`
- `0x1800172e4`
- `0x180017de4`
- `0x18002e570`
- `0x1800434d0`
- `0x180043544`
- `0x180060974`
- `0x18006257c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017735`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017735`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017719`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017719`
- `OLEAUT32!__imp_SysFreeString` at `0x1800175e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800177d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800175e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800177d3`
- `OLEAUT32!__imp_VariantInit` at `0x1800174ff`
- `OLEAUT32!__imp_VariantInit` at `0x180017512`
- `OLEAUT32!__imp_VariantInit` at `0x18001766e`
- `OLEAUT32!__imp_VariantInit` at `0x1800174ff`
- `OLEAUT32!__imp_VariantInit` at `0x180017512`
- `OLEAUT32!__imp_VariantInit` at `0x18001766e`

## pseudocode

```c
__int64 __fastcall RunCmdAsUser(char *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v4; // eax
  unsigned int v5; // edi
  struct ITaskDefinition *v6; // rsi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  struct ITaskFolder *v12; // rbx
  HRESULT (__stdcall *RegisterTaskDefinition)(ITaskFolder *, BSTR, ITaskDefinition *, LONG, VARIANT, VARIANT, TASK_LOGON_TYPE, VARIANT, IRegisteredTask **); // rdi
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  _variant_t *v18; // rax
  __int128 v19; // xmm10
  IRecordInfo *v20; // xmm11_8
  _bstr_t *v21; // rax
  __int64 v22; // rdx
  BSTR *v23; // rdi
  BSTR v24; // rcx
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, VARIANTARG *, __int64); // rdi
  char *v27; // rax
  HRESULT (__stdcall *DeleteTask)(ITaskFolder *, BSTR, LONG); // rdi
  _bstr_t *v29; // rax
  __int64 v30; // rdx
  BSTR *v31; // rbx
  BSTR v32; // rcx
  int v34; // [rsp+28h] [rbp-E0h]
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-90h] BYREF
  void *Block; // [rsp+80h] [rbp-88h] BYREF
  __int64 v41; // [rsp+88h] [rbp-80h] BYREF
  struct ITaskFolder *v42; // [rsp+98h] [rbp-70h] BYREF
  struct ITaskDefinition *v43; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v45; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v46; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v47; // [rsp+108h] [rbp+0h]
  IRecordInfo *v48; // [rsp+118h] [rbp+10h]
  __int128 v49; // [rsp+128h] [rbp+20h]
  IRecordInfo *v50; // [rsp+138h] [rbp+30h]
  _BYTE v51[128]; // [rsp+148h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]
  char *v53; // [rsp+1F8h] [rbp+F0h] BYREF
  DWORD dwProcessId; // [rsp+210h] [rbp+108h] BYREF

  v53 = a1;
  v43 = 0;
  v42 = 0;
  v4 = CreateTaskForUser((const unsigned __int16 *)a1, &v43, &v42, a2, a3);
  v5 = v4;
  LODWORD(v53) = v4;
  if ( v4 >= 0 )
  {
    v35 = 0;
    v6 = v43;
    v7 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v43->lpVtbl->get_Triggers)(v43, &v35);
    v5 = v7;
    LODWORD(v53) = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEFA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v7,
        v34);
LABEL_54:
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v35);
      goto LABEL_55;
    }
    v36 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v35 + 80LL))(v35, 9, &v36);
    v5 = v8;
    LODWORD(v53) = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEFE,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v8,
        v34);
LABEL_53:
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v36);
      goto LABEL_54;
    }
    v37 = 0;
    v9 = (**v36)(v36, &IID_ILogonTrigger, &v37);
    v5 = v9;
    LODWORD(v53) = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF02,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v9,
        v34);
LABEL_52:
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v37);
      goto LABEL_53;
    }
    v38 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 80LL))(v37, &v38);
    v5 = v10;
    LODWORD(v53) = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 96LL))(v38, 0);
      v5 = v10;
      LODWORD(v53) = v10;
      if ( v10 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64))v6->lpVtbl->put_Triggers)(v6, v35);
        v5 = v10;
        LODWORD(v53) = v10;
        if ( v10 >= 0 )
        {
          v39 = 0;
          v12 = v42;
          RegisterTaskDefinition = v42->lpVtbl->RegisterTaskDefinition;
          VariantInit(&pvarg);
          v14 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v46);
          v16 = *(_OWORD *)&v46.vt;
          v17 = v46.pRecInfo;
          v18 = _variant_t::_variant_t((_variant_t *)v51, a3);
          v19 = *(_OWORD *)v18;
          v20 = (IRecordInfo *)*((_QWORD *)v18 + 2);
          v21 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Run a Cmd as the User");
          if ( *(_QWORD *)v21 )
            v22 = **(_QWORD **)v21;
          else
            v22 = 0;
          v47 = v14;
          v48 = pRecInfo;
          v49 = v16;
          v50 = v17;
          *(_OWORD *)&v45.vt = v19;
          v45.pRecInfo = v20;
          LODWORD(v53) = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, struct ITaskDefinition *, __int64))RegisterTaskDefinition)(
                           v12,
                           v22,
                           v6,
                           6);
          v23 = (BSTR *)Block;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v23 )
            {
              if ( *v23 )
              {
                SysFreeString(*v23);
                *v23 = 0;
              }
              v24 = v23[1];
              if ( v24 )
              {
                operator delete(v24);
                v23[1] = 0;
              }
              operator delete(v23);
            }
            Block = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v51);
          _variant_t::~_variant_t((_variant_t *)&v46);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          v5 = (unsigned int)v53;
          if ( (int)v53 >= 0 )
          {
            v41 = 0;
            v25 = v39;
            v26 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v39 + 104LL);
            VariantInit(&pvarg);
            v45 = pvarg;
            LODWORD(v53) = v26(v25, &v45, 2);
            _variant_t::~_variant_t((_variant_t *)&pvarg);
            v5 = (unsigned int)v53;
            if ( (int)v53 >= 0 )
            {
              dwProcessId = 0;
              LODWORD(v53) = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v41 + 112LL))(v41, &dwProcessId);
              if ( (int)v53 >= 0 )
              {
                v27 = (char *)OpenProcess(0x101000u, 0, dwProcessId);
                Block = v27;
                if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  WaitForSingleObject(v27, 0xFFFFFFFF);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
              }
              LODWORD(v53) = 0;
              (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v39 + 128LL))(v39, &v53);
              if ( (_DWORD)v53 != 267011 )
              {
                DeleteTask = v12->lpVtbl->DeleteTask;
                v29 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Run a Cmd as the User");
                v30 = *(_QWORD *)v29 ? **(_QWORD **)v29 : 0LL;
                ((void (__fastcall *)(struct ITaskFolder *, __int64, _QWORD))DeleteTask)(v12, v30, 0);
                v31 = (BSTR *)Block;
                if ( Block )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v31 )
                  {
                    if ( *v31 )
                    {
                      SysFreeString(*v31);
                      *v31 = 0;
                    }
                    v32 = v31[1];
                    if ( v32 )
                    {
                      operator delete(v32);
                      v31[1] = 0;
                    }
                    operator delete(v31);
                  }
                }
              }
              v5 = (unsigned int)v53;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF21,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
                (const char *)(unsigned int)v53,
                0);
            }
            ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v41);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF18,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
              (const char *)(unsigned int)v53,
              (int)&v45);
          }
          ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v39);
          goto LABEL_51;
        }
        v11 = 3852;
      }
      else
      {
        v11 = 3849;
      }
    }
    else
    {
      v11 = 3846;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v10,
      v34);
LABEL_51:
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v38);
    goto LABEL_52;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEF6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
    (const char *)(unsigned int)v4,
    v34);
LABEL_55:
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v42);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v43);
  return v5;
}

```

## disassembly

```asm
0x1800172e4  mov     rax, rsp
0x1800172e7  mov     [rax+10h], rbx
0x1800172eb  mov     [rax+8], rcx
0x1800172ef  push    rbp
0x1800172f0  push    rsi
0x1800172f1  push    rdi
0x1800172f2  push    r14
0x1800172f4  push    r15
0x1800172f6  lea     rbp, [rax-0E8h]
0x1800172fd  sub     rsp, 1C0h
0x180017304  movaps  xmmword ptr [rax-38h], xmm6
0x180017308  movaps  xmmword ptr [rax-48h], xmm7
0x18001730c  movaps  xmmword ptr [rax-58h], xmm8
0x180017311  movaps  xmmword ptr [rax-68h], xmm9
0x180017316  movaps  xmmword ptr [rax-78h], xmm10
0x18001731b  movaps  xmmword ptr [rax-88h], xmm11
0x180017323  mov     r14, r8
0x180017326  xor     r15d, r15d
0x180017329  mov     [rbp+0E0h+var_148], r15
0x18001732d  mov     [rbp+0E0h+var_150], r15
0x180017331  mov     [rsp+1E0h+var_1C0], r8; int
0x180017336  mov     r9, rdx; unsigned __int16 *
0x180017339  lea     r8, [rbp+0E0h+var_150]; struct ITaskFolder **
0x18001733d  lea     rdx, [rbp+0E0h+var_148]; struct ITaskDefinition **
0x180017341  call    ?CreateTaskForUser@@YAJPEBGPEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@00@Z; CreateTaskForUser(ushort const *,ITaskDefinition * *,ITaskFolder * *,ushort const *,ushort const *)
0x180017346  mov     edi, eax
0x180017348  mov     dword ptr [rbp+0E0h+arg_0], eax
0x18001734e  test    eax, eax
0x180017350  jns     short loc_180017372
0x180017352  mov     rcx, [rbp+0E8h]; this
0x180017359  mov     r9d, eax; char *
0x18001735c  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180017363  mov     edx, 0EF6h; void *
0x180017368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001736d  jmp     loc_18001783C
0x180017372  mov     [rsp+1E0h+var_190], r15
0x180017377  mov     rsi, [rbp+0E0h+var_148]
0x18001737b  mov     rax, [rsi]
0x18001737e  lea     rdx, [rsp+1E0h+var_190]
0x180017383  mov     rcx, rsi
0x180017386  mov     rax, [rax+48h]
0x18001738a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001738f  mov     edi, eax
0x180017391  mov     dword ptr [rbp+0E0h+arg_0], eax
0x180017397  test    eax, eax
0x180017399  jns     short loc_1800173BB
0x18001739b  mov     rcx, [rbp+0E8h]; this
0x1800173a2  mov     r9d, eax; char *
0x1800173a5  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800173ac  mov     edx, 0EFAh; void *
0x1800173b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173b6  jmp     loc_180017832
0x1800173bb  mov     [rsp+1E0h+var_188], r15
0x1800173c0  mov     rcx, [rsp+1E0h+var_190]
0x1800173c5  mov     rax, [rcx]
0x1800173c8  lea     r8, [rsp+1E0h+var_188]
0x1800173cd  mov     edx, 9
0x1800173d2  mov     rax, [rax+50h]
0x1800173d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173db  mov     edi, eax
0x1800173dd  mov     dword ptr [rbp+0E0h+arg_0], eax
0x1800173e3  test    eax, eax
0x1800173e5  jns     short loc_180017407
0x1800173e7  mov     rcx, [rbp+0E8h]; this
0x1800173ee  mov     r9d, eax; char *
0x1800173f1  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800173f8  mov     edx, 0EFEh; void *
0x1800173fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017402  jmp     loc_180017828
0x180017407  mov     [rsp+1E0h+var_180], r15
0x18001740c  mov     rcx, [rsp+1E0h+var_188]
0x180017411  mov     rax, [rcx]
0x180017414  lea     r8, [rsp+1E0h+var_180]
0x180017419  lea     rdx, IID_ILogonTrigger
0x180017420  mov     rax, [rax]
0x180017423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017428  mov     edi, eax
0x18001742a  mov     dword ptr [rbp+0E0h+arg_0], eax
0x180017430  test    eax, eax
0x180017432  jns     short loc_180017454
0x180017434  mov     rcx, [rbp+0E8h]; this
0x18001743b  mov     r9d, eax; char *
0x18001743e  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180017445  mov     edx, 0F02h; void *
0x18001744a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001744f  jmp     loc_18001781E
0x180017454  mov     [rsp+1E0h+var_178], r15
0x180017459  mov     rcx, [rsp+1E0h+var_180]
0x18001745e  mov     rax, [rcx]
0x180017461  lea     rdx, [rsp+1E0h+var_178]
0x180017466  mov     rax, [rax+50h]
0x18001746a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746f  mov     edi, eax
0x180017471  mov     dword ptr [rbp+0E0h+arg_0], eax
0x180017477  test    eax, eax
0x180017479  jns     short loc_18001749B
0x18001747b  mov     edx, 0F06h; void *
0x180017480  mov     rcx, [rbp+0E8h]; this
0x180017487  mov     r9d, eax; char *
0x18001748a  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180017491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017496  jmp     loc_180017814
0x18001749b  mov     rcx, [rsp+1E0h+var_178]
0x1800174a0  mov     rax, [rcx]
0x1800174a3  xor     edx, edx
0x1800174a5  mov     rax, [rax+60h]
0x1800174a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ae  mov     edi, eax
0x1800174b0  mov     dword ptr [rbp+0E0h+arg_0], eax
0x1800174b6  test    eax, eax
0x1800174b8  jns     short loc_1800174C1
0x1800174ba  mov     edx, 0F09h
0x1800174bf  jmp     short loc_180017480
0x1800174c1  mov     rax, [rsi]
0x1800174c4  mov     rdx, [rsp+1E0h+var_190]
0x1800174c9  mov     rcx, rsi
0x1800174cc  mov     rax, [rax+50h]
0x1800174d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174d5  mov     edi, eax
0x1800174d7  mov     dword ptr [rbp+0E0h+arg_0], eax
0x1800174dd  test    eax, eax
0x1800174df  jns     short loc_1800174E8
0x1800174e1  mov     edx, 0F0Ch
0x1800174e6  jmp     short loc_180017480
0x1800174e8  mov     [rsp+1E0h+var_170], r15
0x1800174ed  mov     rbx, [rbp+0E0h+var_150]
0x1800174f1  mov     rax, [rbx]
0x1800174f4  mov     rdi, [rax+88h]
0x1800174fb  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x1800174ff  call    cs:__imp_VariantInit
0x180017505  movups  xmm6, xmmword ptr [rbp+0E0h+pvarg]
0x180017509  movsd   xmm7, qword ptr [rbp+0E0h+pvarg+10h]
0x18001750e  lea     rcx, [rbp+0E0h+var_100]; pvarg
0x180017512  call    cs:__imp_VariantInit
0x180017518  movups  xmm8, xmmword ptr [rbp+0E0h+var_100]
0x18001751d  movsd   xmm9, qword ptr [rbp+0E0h+var_100+10h]
0x180017523  mov     rdx, r14; unsigned __int16 *
0x180017526  lea     rcx, [rbp+0E0h+var_A0]; this
0x18001752a  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18001752f  movups  xmm10, xmmword ptr [rax]
0x180017533  movsd   xmm11, qword ptr [rax+10h]
0x180017539  lea     rdx, aRunACmdAsTheUs; "Run a Cmd as the User"
0x180017540  lea     rcx, [rsp+1E0h+Block]; this
0x180017545  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001754a  mov     rdx, [rax]
0x18001754d  test    rdx, rdx
0x180017550  jz      short loc_180017557
0x180017552  mov     rdx, [rdx]
0x180017555  jmp     short loc_18001755A
0x180017557  mov     rdx, r15
0x18001755a  movaps  [rbp+0E0h+var_E0], xmm6
0x18001755e  movsd   [rbp+0E0h+var_D0], xmm7
0x180017563  movaps  [rbp+0E0h+var_C0], xmm8
0x180017568  movsd   [rbp+0E0h+var_B0], xmm9
0x18001756e  movaps  xmmword ptr [rbp+0E0h+var_120], xmm10
0x180017573  movsd   [rbp+0E0h+var_110], xmm11
0x180017579  lea     rax, [rsp+1E0h+var_170]
0x18001757e  mov     [rsp+1E0h+var_1A0], rax
0x180017583  lea     rax, [rbp+0E0h+var_E0]
0x180017587  mov     [rsp+1E0h+var_1A8], rax
0x18001758c  mov     dword ptr [rsp+1E0h+var_1B0], 3
0x180017594  lea     rax, [rbp+0E0h+var_C0]
0x180017598  mov     qword ptr [rsp+1E0h+var_1B8], rax
0x18001759d  lea     rax, [rbp+0E0h+var_120]
0x1800175a1  mov     [rsp+1E0h+var_1C0], rax; int
0x1800175a6  mov     r9d, 6
0x1800175ac  mov     r8, rsi
0x1800175af  mov     rcx, rbx
0x1800175b2  mov     rax, rdi
0x1800175b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ba  mov     dword ptr [rbp+0E0h+arg_0], eax
0x1800175c0  or      r14d, 0FFFFFFFFh
0x1800175c4  mov     rdi, [rsp+1E0h+Block]
0x1800175c9  test    rdi, rdi
0x1800175cc  jz      short loc_180017615
0x1800175ce  mov     eax, r14d
0x1800175d1  lock xadd [rdi+10h], eax
0x1800175d6  add     eax, r14d
0x1800175d9  jnz     short loc_180017610
0x1800175db  test    rdi, rdi
0x1800175de  jz      short loc_180017610
0x1800175e0  mov     rcx, [rdi]; bstrString
0x1800175e3  test    rcx, rcx
0x1800175e6  jz      short loc_1800175F1
0x1800175e8  call    cs:__imp_SysFreeString
0x1800175ee  mov     [rdi], r15
0x1800175f1  mov     rcx, [rdi+8]; Block
0x1800175f5  test    rcx, rcx
0x1800175f8  jz      short loc_180017603
0x1800175fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800175ff  mov     [rdi+8], r15
0x180017603  mov     edx, 18h
0x180017608  mov     rcx, rdi; Block
0x18001760b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017610  mov     [rsp+1E0h+Block], r15
0x180017615  lea     rcx, [rbp+0E0h+var_A0]; this
0x180017619  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001761e  lea     rcx, [rbp+0E0h+var_100]; this
0x180017622  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180017627  lea     rcx, [rbp+0E0h+pvarg]; this
0x18001762b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180017630  mov     edi, dword ptr [rbp+0E0h+arg_0]
0x180017636  test    edi, edi
0x180017638  jns     short loc_18001765A
0x18001763a  mov     rcx, [rbp+0E8h]; this
0x180017641  mov     r9d, edi; char *
0x180017644  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001764b  mov     edx, 0F18h; void *
0x180017650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017655  jmp     loc_18001780A
0x18001765a  mov     [rbp+0E0h+var_160], r15
0x18001765e  mov     rsi, [rsp+1E0h+var_170]
0x180017663  mov     rax, [rsi]
0x180017666  mov     rdi, [rax+68h]
0x18001766a  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18001766e  call    cs:__imp_VariantInit
0x180017674  movups  xmm0, xmmword ptr [rbp+0E0h+pvarg]
0x180017678  movaps  xmmword ptr [rbp+0E0h+var_120], xmm0
0x18001767c  movsd   xmm1, qword ptr [rbp+0E0h+pvarg+10h]
0x180017681  movsd   [rbp+0E0h+var_110], xmm1
0x180017686  lea     rax, [rbp+0E0h+var_160]
0x18001768a  mov     qword ptr [rsp+1E0h+var_1B8], rax
0x18001768f  mov     [rsp+1E0h+var_1C0], r15; int
0x180017694  xor     r9d, r9d
0x180017697  lea     r8d, [r9+2]
0x18001769b  lea     rdx, [rbp+0E0h+var_120]
0x18001769f  mov     rcx, rsi
0x1800176a2  mov     rax, rdi
0x1800176a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176aa  mov     dword ptr [rbp+0E0h+arg_0], eax
0x1800176b0  lea     rcx, [rbp+0E0h+pvarg]; this
0x1800176b4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800176b9  mov     edi, dword ptr [rbp+0E0h+arg_0]
0x1800176bf  test    edi, edi
0x1800176c1  jns     short loc_1800176E3
0x1800176c3  mov     rcx, [rbp+0E8h]; this
0x1800176ca  mov     r9d, edi; char *
0x1800176cd  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800176d4  mov     edx, 0F21h; void *
0x1800176d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800176de  jmp     loc_180017801
0x1800176e3  mov     [rbp+0E0h+dwProcessId], r15d
0x1800176ea  mov     rcx, [rbp+0E0h+var_160]
0x1800176ee  mov     rax, [rcx]
0x1800176f1  lea     rdx, [rbp+0E0h+dwProcessId]
0x1800176f8  mov     rax, [rax+70h]
0x1800176fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017701  mov     dword ptr [rbp+0E0h+arg_0], eax
0x180017707  test    eax, eax
0x180017709  js      short loc_180017747
0x18001770b  mov     r8d, [rbp+0E0h+dwProcessId]; dwProcessId
0x180017712  xor     edx, edx; bInheritHandle
0x180017714  mov     ecx, 101000h; dwDesiredAccess
0x180017719  call    cs:__imp_OpenProcess
0x18001771f  nop
0x180017720  mov     [rsp+1E0h+Block], rax
0x180017725  lea     rcx, [rax-1]
0x180017729  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001772d  ja      short loc_18001773C
0x18001772f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017732  mov     rcx, rax; hHandle
0x180017735  call    cs:__imp_WaitForSingleObject
0x18001773b  nop
0x18001773c  lea     rcx, [rsp+1E0h+Block]
0x180017741  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017746  nop
0x180017747  mov     dword ptr [rbp+0E0h+arg_0], r15d
0x18001774e  mov     rcx, [rsp+1E0h+var_170]
0x180017753  mov     rax, [rcx]
0x180017756  lea     rdx, [rbp+0E0h+arg_0]
0x18001775d  mov     rax, [rax+80h]
0x180017764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017769  cmp     dword ptr [rbp+0E0h+arg_0], 41303h
0x180017773  jz      loc_1800177FB
0x180017779  mov     rax, [rbx]
0x18001777c  mov     rdi, [rax+78h]
0x180017780  lea     rdx, aRunACmdAsTheUs; "Run a Cmd as the User"
0x180017787  lea     rcx, [rsp+1E0h+Block]; this
0x18001778c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180017791  mov     rdx, [rax]
0x180017794  test    rdx, rdx
0x180017797  jz      short loc_18001779E
0x180017799  mov     rdx, [rdx]
0x18001779c  jmp     short loc_1800177A1
0x18001779e  mov     rdx, r15
0x1800177a1  xor     r8d, r8d
0x1800177a4  mov     rcx, rbx
0x1800177a7  mov     rax, rdi
0x1800177aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177af  mov     rbx, [rsp+1E0h+Block]
0x1800177b4  test    rbx, rbx
0x1800177b7  jz      short loc_1800177FB
0x1800177b9  mov     eax, r14d
0x1800177bc  lock xadd [rbx+10h], eax
0x1800177c1  add     eax, r14d
0x1800177c4  jnz     short loc_1800177FB
0x1800177c6  test    rbx, rbx
0x1800177c9  jz      short loc_1800177FB
0x1800177cb  mov     rcx, [rbx]; bstrString
0x1800177ce  test    rcx, rcx
  ... truncated ...
```
