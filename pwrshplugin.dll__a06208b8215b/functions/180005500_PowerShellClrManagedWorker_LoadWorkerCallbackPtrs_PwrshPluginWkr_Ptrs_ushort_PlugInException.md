# PowerShellClrManagedWorker::LoadWorkerCallbackPtrs(_PwrshPluginWkr_Ptrs *,ushort *,PlugInException * *)

- ea: `0x180005500`
- end: `0x180005b95`
- name: `?LoadWorkerCallbackPtrs@PowerShellClrManagedWorker@@UEAAIPEAU_PwrshPluginWkr_Ptrs@@PEAGPEAPEAVPlugInException@@@Z`
- size: `1685`
- prototype: `__int64 __fastcall(PowerShellClrManagedWorker *this, struct _PwrshPluginWkr_Ptrs *, unsigned __int16 *, struct PlugInException **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001098`
- `0x180005344`
- `0x180005500`
- `0x1800062bc`
- `0x180009677`
- `0x18000b010`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000574c`
- `ATL!__imp_AtlComPtrAssign` at `0x18000574c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800055cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180005618`
- `OLEAUT32!__imp_SysAllocString` at `0x1800055cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180005618`
- `OLEAUT32!__imp_VariantInit` at `0x18000586e`
- `OLEAUT32!__imp_VariantInit` at `0x18000586e`
- `OLEAUT32!__imp_VariantClear` at `0x1800056d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800057e9`
- `OLEAUT32!__imp_VariantClear` at `0x180005923`
- `OLEAUT32!__imp_VariantClear` at `0x1800059ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800056d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800057e9`
- `OLEAUT32!__imp_VariantClear` at `0x180005923`
- `OLEAUT32!__imp_VariantClear` at `0x1800059ee`

## string_xrefs

- `0x1800055c5`: `System.Management.Automation, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x180005611`: `System.Management.Automation.Remoting.WSManPluginManagedEntryInstanceWrapper`

## pseudocode

```c
__int64 __fastcall PowerShellClrManagedWorker::LoadWorkerCallbackPtrs(
        PowerShellClrManagedWorker *this,
        struct _PwrshPluginWkr_Ptrs *a2,
        unsigned __int16 *a3,
        struct PlugInException **a4)
{
  int v6; // eax
  int v7; // eax
  BSTR *v8; // rax
  int v9; // ecx
  BSTR *v10; // rdi
  BSTR v11; // rax
  BSTR *v12; // rax
  int v13; // ecx
  BSTR *v14; // rbx
  BSTR v15; // rax
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // r8
  unsigned int v20; // ebx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // r9d
  __int64 v26; // rcx
  void (__fastcall *v27)(__int64, _QWORD, __int64, __int64); // rax
  int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  BSTR *v34; // [rsp+70h] [rbp-90h] BYREF
  BSTR *v35; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v37; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v38; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v40; // [rsp+C8h] [rbp-38h]
  _BYTE v41[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  unsigned int v43; // [rsp+140h] [rbp+40h] BYREF
  int v44; // [rsp+158h] [rbp+58h] BYREF

  *a4 = 0;
  v30 = 0;
  v31 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned __int16 *))(**((_QWORD **)this + 1) + 104LL))(
         *((_QWORD *)this + 1),
         &v31,
         a3);
  if ( v6 >= 0 && v31 )
  {
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *, _QWORD))v31)(
           v31,
           &GUID_05f696dc_2b29_3663_ad8b_c4389cf2a713,
           &v30,
           (unsigned int)v6);
    if ( v7 >= 0 && v30 )
    {
      v32 = 0;
      v8 = (BSTR *)operator new(0x18u);
      v10 = v8;
      v35 = v8;
      if ( v8 )
      {
        v8[1] = 0;
        *((_DWORD *)v8 + 4) = 1;
        v11 = SysAllocString(L"System.Management.Automation, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35");
        *v10 = v11;
        if ( !v11 )
          _com_issue_error(v9);
      }
      else
      {
        v10 = 0;
      }
      v35 = v10;
      if ( !v10 )
        _com_issue_error(v9);
      v12 = (BSTR *)operator new(0x18u);
      v14 = v12;
      v34 = v12;
      if ( v12 )
      {
        v12[1] = 0;
        *((_DWORD *)v12 + 4) = 1;
        v15 = SysAllocString(L"System.Management.Automation.Remoting.WSManPluginManagedEntryInstanceWrapper");
        *v14 = v15;
        if ( !v15 )
          _com_issue_error(v13);
      }
      else
      {
        v14 = 0;
      }
      v34 = v14;
      if ( !v14 )
        _com_issue_error(v13);
      v16 = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR, __int64 *))(*(_QWORD *)v30 + 296LL))(v30, *v10, *v14, &v32);
      if ( v16 >= 0 && v32 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64, _QWORD))(*(_QWORD *)v32 + 112LL))(
                v32,
                &pvarg,
                v17,
                (unsigned int)v16);
        if ( v18 >= 0 )
        {
          v33 = 0;
          AtlComPtrAssign(&v33, pvarg.llVal, v19, (unsigned int)v18);
          v37 = L"GetEntryDelegate";
          v43 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64, GUID *, const wchar_t **, __int64, int, unsigned int *))(*(_QWORD *)v33 + 40LL))(
                  v33,
                  &GUID_NULL,
                  &v37,
                  1,
                  2048,
                  &v43);
          if ( v21 >= 0 )
          {
            v39 = 0;
            v40 = 0;
            memset(&v38, 0, sizeof(v38));
            VariantInit(&v38);
            memset_0(v41, 0, 0x40u);
            v44 = 0;
            LOWORD(v29) = 1;
            v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64, int, __int128 *, VARIANTARG *, _BYTE *, int *))(*(_QWORD *)v33 + 48LL))(
                    v33,
                    v43,
                    &GUID_NULL,
                    2048,
                    v29,
                    &v39,
                    &v38,
                    v41,
                    &v44);
            v25 = v22;
            if ( v22 >= 0 && v38.llVal )
            {
              v20 = ((__int64 (__fastcall *)(struct _PwrshPluginWkr_Ptrs *, __int64, __int64, _QWORD))v38.llVal)(
                      a2,
                      v23,
                      v24,
                      (unsigned int)v22);
              if ( v33 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              if ( pvarg.vt == 4095 )
                pvarg.vt = 8;
              VariantClear(&pvarg);
              _bstr_t::~_bstr_t((_bstr_t *)&v34);
              _bstr_t::~_bstr_t((_bstr_t *)&v35);
              if ( v32 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              if ( v31 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            else
            {
              v26 = *((_QWORD *)this + 2);
              v27 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v26 + 8LL);
              if ( v25 == -2147352567 )
                v27(v26, 0, 10, v42);
              else
                ((void (__fastcall *)(__int64, _QWORD, __int64))v27)(v26, 0, 9);
              v20 = -65536;
              if ( v33 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              if ( pvarg.vt == 4095 )
                pvarg.vt = 8;
              VariantClear(&pvarg);
              _bstr_t::~_bstr_t((_bstr_t *)&v34);
              _bstr_t::~_bstr_t((_bstr_t *)&v35);
              if ( v32 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              if ( v31 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
              *((_QWORD *)this + 2),
              0,
              8,
              (unsigned int)v21);
            v20 = -65536;
            if ( v33 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            if ( pvarg.vt == 4095 )
              pvarg.vt = 8;
            VariantClear(&pvarg);
            _bstr_t::~_bstr_t((_bstr_t *)&v34);
            _bstr_t::~_bstr_t((_bstr_t *)&v35);
            if ( v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            if ( v31 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            if ( v30 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
            *((_QWORD *)this + 2),
            0,
            7,
            (unsigned int)v18);
          v20 = -65536;
          if ( pvarg.vt == 4095 )
            pvarg.vt = 8;
          VariantClear(&pvarg);
          _bstr_t::~_bstr_t((_bstr_t *)&v34);
          _bstr_t::~_bstr_t((_bstr_t *)&v35);
          if ( v32 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
          *((_QWORD *)this + 2),
          0,
          7,
          (unsigned int)v16);
        v20 = -65536;
        _bstr_t::~_bstr_t((_bstr_t *)&v34);
        _bstr_t::~_bstr_t((_bstr_t *)&v35);
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
        *((_QWORD *)this + 2),
        0,
        6,
        (unsigned int)v7);
      v20 = -65536;
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
      *((_QWORD *)this + 2),
      0,
      6,
      (unsigned int)v6);
    v20 = -65536;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return v20;
}

```

## disassembly

```asm
0x180005500  mov     [rsp-8+arg_8], rbx
0x180005505  push    rbp
0x180005506  push    rsi
0x180005507  push    rdi
0x180005508  push    r12
0x18000550a  push    r14
0x18000550c  lea     rbp, [rsp-10h]
0x180005511  sub     rsp, 110h
0x180005518  mov     r14, rdx
0x18000551b  mov     rsi, rcx
0x18000551e  mov     qword ptr [r9], 0
0x180005525  mov     [rsp+130h+var_E0], 0
0x18000552e  mov     [rsp+130h+var_D8], 0
0x180005537  mov     rcx, [rcx+8]
0x18000553b  mov     rax, [rcx]
0x18000553e  lea     rdx, [rsp+130h+var_D8]
0x180005543  mov     rax, [rax+68h]
0x180005547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554c  mov     r9d, eax
0x18000554f  test    eax, eax
0x180005551  js      loc_180005B1B
0x180005557  mov     rcx, [rsp+130h+var_D8]
0x18000555c  test    rcx, rcx
0x18000555f  jz      loc_180005B1B
0x180005565  mov     rax, [rcx]
0x180005568  lea     r8, [rsp+130h+var_E0]
0x18000556d  lea     rdx, _GUID_05f696dc_2b29_3663_ad8b_c4389cf2a713
0x180005574  mov     rax, [rax]
0x180005577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000557c  mov     r9d, eax
0x18000557f  test    eax, eax
0x180005581  js      loc_180005AD0
0x180005587  cmp     [rsp+130h+var_E0], 0
0x18000558d  jz      loc_180005AD0
0x180005593  mov     [rsp+130h+var_D0], 0
0x18000559c  mov     ebx, 18h
0x1800055a1  mov     ecx, ebx; Size
0x1800055a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800055a8  mov     rdi, rax
0x1800055ab  mov     [rsp+130h+var_B8], rax
0x1800055b0  lea     r12d, [rbx-17h]
0x1800055b4  test    rax, rax
0x1800055b7  jz      short loc_1800055E0
0x1800055b9  mov     qword ptr [rax+8], 0
0x1800055c1  mov     [rax+10h], r12d
0x1800055c5  lea     rcx, psz; "System.Management.Automation, Version=3"...
0x1800055cc  call    cs:__imp_SysAllocString
0x1800055d2  mov     [rdi], rax
0x1800055d5  test    rax, rax
0x1800055d8  jz      loc_180005B83
0x1800055de  jmp     short loc_1800055E2
0x1800055e0  xor     edi, edi
0x1800055e2  mov     [rsp+130h+var_B8], rdi
0x1800055e7  test    rdi, rdi
0x1800055ea  jz      loc_180005B8F
0x1800055f0  mov     rcx, rbx; Size
0x1800055f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800055f8  mov     rbx, rax
0x1800055fb  mov     [rsp+130h+var_C0], rax
0x180005600  test    rax, rax
0x180005603  jz      short loc_18000562C
0x180005605  mov     qword ptr [rax+8], 0
0x18000560d  mov     [rax+10h], r12d
0x180005611  lea     rcx, aSystemManageme_0; "System.Management.Automation.Remoting.W"...
0x180005618  call    cs:__imp_SysAllocString
0x18000561e  mov     [rbx], rax
0x180005621  test    rax, rax
0x180005624  jz      loc_180005B89
0x18000562a  jmp     short loc_18000562E
0x18000562c  xor     ebx, ebx
0x18000562e  mov     [rsp+130h+var_C0], rbx
0x180005633  test    rbx, rbx
0x180005636  jz      loc_180005B7D
0x18000563c  mov     rcx, [rsp+130h+var_E0]
0x180005641  mov     rax, [rcx]
0x180005644  lea     r9, [rsp+130h+var_D0]
0x180005649  mov     r8, [rbx]
0x18000564c  mov     rdx, [rdi]
0x18000564f  mov     rax, [rax+128h]
0x180005656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565b  mov     r9d, eax
0x18000565e  test    eax, eax
0x180005660  js      loc_180005A55
0x180005666  mov     rcx, [rsp+130h+var_D0]
0x18000566b  test    rcx, rcx
0x18000566e  jz      loc_180005A55
0x180005674  xorps   xmm0, xmm0
0x180005677  xor     eax, eax
0x180005679  movups  xmmword ptr [rbp+30h+pvarg], xmm0
0x18000567d  mov     qword ptr [rbp+30h+pvarg+10h], rax
0x180005681  mov     word ptr [rbp+30h+pvarg], ax
0x180005685  mov     rax, [rcx]
0x180005688  lea     rdx, [rbp+30h+pvarg]
0x18000568c  mov     rax, [rax+70h]
0x180005690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005695  mov     r9d, eax
0x180005698  test    eax, eax
0x18000569a  jns     loc_18000573A
0x1800056a0  mov     rcx, [rsi+10h]
0x1800056a4  mov     rdx, [rcx]
0x1800056a7  mov     rax, [rdx+8]
0x1800056ab  xor     edx, edx
0x1800056ad  lea     r8d, [rdx+7]
0x1800056b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b6  mov     ebx, 0FFFF0000h
0x1800056bb  mov     eax, 0FFFh
0x1800056c0  cmp     word ptr [rbp+30h+pvarg], ax
0x1800056c4  jnz     short loc_1800056CF
0x1800056c6  mov     edi, 8
0x1800056cb  mov     word ptr [rbp+30h+pvarg], di
0x1800056cf  lea     rcx, [rbp+30h+pvarg]; pvarg
0x1800056d3  call    cs:__imp_VariantClear
0x1800056d9  nop
0x1800056da  lea     rcx, [rsp+130h+var_C0]; this
0x1800056df  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800056e4  nop
0x1800056e5  lea     rcx, [rsp+130h+var_B8]; this
0x1800056ea  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800056ef  nop
0x1800056f0  mov     rcx, [rsp+130h+var_D0]
0x1800056f5  test    rcx, rcx
0x1800056f8  jz      short loc_180005707
0x1800056fa  mov     rax, [rcx]
0x1800056fd  mov     rax, [rax+10h]
0x180005701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005706  nop
0x180005707  mov     rcx, [rsp+130h+var_D8]
0x18000570c  test    rcx, rcx
0x18000570f  jz      short loc_18000571E
0x180005711  mov     rax, [rcx]
0x180005714  mov     rax, [rax+10h]
0x180005718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571d  nop
0x18000571e  mov     rcx, [rsp+130h+var_E0]
0x180005723  test    rcx, rcx
0x180005726  jz      short loc_180005735
0x180005728  mov     rax, [rcx]
0x18000572b  mov     rax, [rax+10h]
0x18000572f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005734  nop
0x180005735  jmp     loc_180005B64
0x18000573a  mov     [rsp+130h+var_C8], 0
0x180005743  mov     rdx, qword ptr [rbp+30h+pvarg+8]
0x180005747  lea     rcx, [rsp+130h+var_C8]
0x18000574c  call    cs:__imp_AtlComPtrAssign
0x180005752  lea     rax, aGetentrydelega; "GetEntryDelegate"
0x180005759  mov     [rbp+30h+var_98], rax
0x18000575d  mov     [rbp+30h+arg_0], 0
0x180005764  mov     rcx, [rsp+130h+var_C8]
0x180005769  mov     rax, [rcx]
0x18000576c  lea     rdx, [rbp+30h+arg_0]
0x180005770  mov     [rsp+130h+var_108], rdx
0x180005775  mov     ebx, 800h
0x18000577a  mov     [rsp+130h+var_110], ebx
0x18000577e  mov     r9d, r12d
0x180005781  lea     r8, [rbp+30h+var_98]
0x180005785  lea     rdx, GUID_NULL
0x18000578c  mov     rax, [rax+28h]
0x180005790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005795  mov     r9d, eax
0x180005798  test    eax, eax
0x18000579a  jns     loc_180005850
0x1800057a0  mov     rcx, [rsi+10h]
0x1800057a4  mov     rdx, [rcx]
0x1800057a7  mov     rax, [rdx+8]
0x1800057ab  mov     edi, 8
0x1800057b0  mov     r8d, edi
0x1800057b3  xor     edx, edx
0x1800057b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ba  mov     ebx, 0FFFF0000h
0x1800057bf  mov     rcx, [rsp+130h+var_C8]
0x1800057c4  test    rcx, rcx
0x1800057c7  jz      short loc_1800057D6
0x1800057c9  mov     rax, [rcx]
0x1800057cc  mov     rax, [rax+10h]
0x1800057d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d5  nop
0x1800057d6  mov     eax, 0FFFh
0x1800057db  cmp     word ptr [rbp+30h+pvarg], ax
0x1800057df  jnz     short loc_1800057E5
0x1800057e1  mov     word ptr [rbp+30h+pvarg], di
0x1800057e5  lea     rcx, [rbp+30h+pvarg]; pvarg
0x1800057e9  call    cs:__imp_VariantClear
0x1800057ef  nop
0x1800057f0  lea     rcx, [rsp+130h+var_C0]; this
0x1800057f5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800057fa  nop
0x1800057fb  lea     rcx, [rsp+130h+var_B8]; this
0x180005800  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180005805  nop
0x180005806  mov     rcx, [rsp+130h+var_D0]
0x18000580b  test    rcx, rcx
0x18000580e  jz      short loc_18000581D
0x180005810  mov     rax, [rcx]
0x180005813  mov     rax, [rax+10h]
0x180005817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581c  nop
0x18000581d  mov     rcx, [rsp+130h+var_D8]
0x180005822  test    rcx, rcx
0x180005825  jz      short loc_180005834
0x180005827  mov     rax, [rcx]
0x18000582a  mov     rax, [rax+10h]
0x18000582e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005833  nop
0x180005834  mov     rcx, [rsp+130h+var_E0]
0x180005839  test    rcx, rcx
0x18000583c  jz      short loc_18000584B
0x18000583e  mov     rax, [rcx]
0x180005841  mov     rax, [rax+10h]
0x180005845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000584a  nop
0x18000584b  jmp     loc_180005B64
0x180005850  xorps   xmm0, xmm0
0x180005853  movdqu  [rbp+30h+var_78], xmm0
0x180005858  mov     [rbp+30h+var_68], 0
0x180005860  xor     eax, eax
0x180005862  movups  xmmword ptr [rbp+30h+var_90], xmm0
0x180005866  mov     qword ptr [rbp+30h+var_90+10h], rax
0x18000586a  lea     rcx, [rbp+30h+var_90]; pvarg
0x18000586e  call    cs:__imp_VariantInit
0x180005874  xor     edx, edx; Val
0x180005876  lea     r8d, [rdx+40h]; Size
0x18000587a  lea     rcx, [rbp+30h+var_60]; void *
0x18000587e  call    memset_0
0x180005883  mov     [rbp+30h+arg_18], 0
0x18000588a  mov     rcx, [rsp+130h+var_C8]
0x18000588f  mov     rax, [rcx]
0x180005892  lea     rdx, [rbp+30h+arg_18]
0x180005896  mov     [rsp+130h+var_F0], rdx
0x18000589b  lea     rdx, [rbp+30h+var_60]
0x18000589f  mov     [rsp+130h+var_F8], rdx
0x1800058a4  lea     rdx, [rbp+30h+var_90]
0x1800058a8  mov     [rsp+130h+var_100], rdx
0x1800058ad  lea     rdx, [rbp+30h+var_78]
0x1800058b1  mov     [rsp+130h+var_108], rdx
0x1800058b6  mov     word ptr [rsp+130h+var_110], r12w
0x1800058bc  mov     r9d, ebx
0x1800058bf  lea     r8, GUID_NULL
0x1800058c6  mov     edx, [rbp+30h+arg_0]
0x1800058c9  mov     rax, [rax+30h]
0x1800058cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d2  mov     r9d, eax
0x1800058d5  test    eax, eax
0x1800058d7  js      loc_18000598A
0x1800058dd  mov     rax, qword ptr [rbp+30h+var_90+8]
0x1800058e1  test    rax, rax
0x1800058e4  jz      loc_18000598A
0x1800058ea  mov     rcx, r14
0x1800058ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f2  mov     ebx, eax
0x1800058f4  mov     rcx, [rsp+130h+var_C8]
0x1800058f9  test    rcx, rcx
0x1800058fc  jz      short loc_18000590B
0x1800058fe  mov     rdx, [rcx]
0x180005901  mov     rax, [rdx+10h]
0x180005905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000590a  nop
0x18000590b  mov     eax, 0FFFh
0x180005910  cmp     word ptr [rbp+30h+pvarg], ax
0x180005914  jnz     short loc_18000591F
0x180005916  mov     edi, 8
0x18000591b  mov     word ptr [rbp+30h+pvarg], di
0x18000591f  lea     rcx, [rbp+30h+pvarg]; pvarg
0x180005923  call    cs:__imp_VariantClear
0x180005929  nop
0x18000592a  lea     rcx, [rsp+130h+var_C0]; this
0x18000592f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180005934  nop
0x180005935  lea     rcx, [rsp+130h+var_B8]; this
0x18000593a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000593f  nop
0x180005940  mov     rcx, [rsp+130h+var_D0]
0x180005945  test    rcx, rcx
0x180005948  jz      short loc_180005957
0x18000594a  mov     rax, [rcx]
0x18000594d  mov     rax, [rax+10h]
0x180005951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005956  nop
0x180005957  mov     rcx, [rsp+130h+var_D8]
0x18000595c  test    rcx, rcx
0x18000595f  jz      short loc_18000596E
0x180005961  mov     rax, [rcx]
0x180005964  mov     rax, [rax+10h]
0x180005968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596d  nop
0x18000596e  mov     rcx, [rsp+130h+var_E0]
0x180005973  test    rcx, rcx
0x180005976  jz      short loc_180005985
0x180005978  mov     rax, [rcx]
0x18000597b  mov     rax, [rax+10h]
0x18000597f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005984  nop
0x180005985  jmp     loc_180005B64
0x18000598a  mov     rcx, [rsi+10h]
0x18000598e  mov     rax, [rcx]
0x180005991  xor     edx, edx
0x180005993  mov     rax, [rax+8]
0x180005997  cmp     r9d, 80020009h
0x18000599e  jnz     short loc_1800059AF
0x1800059a0  mov     r9, [rbp+30h+var_50]
  ... truncated ...
```
