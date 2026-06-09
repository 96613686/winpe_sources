# ScheduleOMADMClientTaskHelper

- ea: `0x180021748`
- end: `0x180021b81`
- name: `ScheduleOMADMClientTaskHelper`
- size: `1081`
- prototype: `__int64 __fastcall(OLECHAR *, unsigned __int16 *, OLECHAR *psz, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021690`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x18000c63c`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001dd58`
- `0x180021748`
- `0x1800245fc`
- `0x180024b94`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021ac5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021ac5`
- `OLEAUT32!__imp_SysAllocString` at `0x180021986`
- `OLEAUT32!__imp_SysAllocString` at `0x1800219cf`
- `OLEAUT32!__imp_SysAllocString` at `0x180021986`
- `OLEAUT32!__imp_SysAllocString` at `0x1800219cf`
- `OLEAUT32!__imp_VariantInit` at `0x18002194f`
- `OLEAUT32!__imp_VariantInit` at `0x180021964`
- `OLEAUT32!__imp_VariantInit` at `0x18002194f`
- `OLEAUT32!__imp_VariantInit` at `0x180021964`
- `OLEAUT32!__imp_VariantClear` at `0x180021a61`
- `OLEAUT32!__imp_VariantClear` at `0x180021a73`
- `OLEAUT32!__imp_VariantClear` at `0x180021a85`
- `OLEAUT32!__imp_VariantClear` at `0x180021a61`
- `OLEAUT32!__imp_VariantClear` at `0x180021a73`
- `OLEAUT32!__imp_VariantClear` at `0x180021a85`

## string_xrefs

- `0x1800217e9`: `ScheduleOMADMClientTaskHelper`
- `0x180021ad4`: `ScheduleOMADMClientTaskHelper`
- `0x180021902`: `%windir%\system32\omadmclient.exe `
- `0x180021aad`: `54RegisterTaskDefinition`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTaskHelper(OLECHAR *a1, unsigned __int16 *a2, OLECHAR *psz, int a4)
{
  unsigned int v7; // ebx
  void (*v8)(void); // rax
  void (*v9)(void); // rax
  __int64 *v11; // rsi
  __int64 v12; // r15
  __int128 v13; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v15; // xmm10
  IRecordInfo *v16; // xmm11_8
  BSTR v17; // rax
  IRecordInfo *v18; // xmm7_8
  __int64 v19; // rdi
  __int128 v20; // xmm6
  BSTR *v21; // rbx
  BSTR v22; // rax
  BSTR v23; // rdx
  __int64 (__fastcall *v24)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  CEnrollmentLogger *Logger; // rax
  __int64 Data; // [rsp+78h] [rbp-90h] BYREF
  int v30[2]; // [rsp+80h] [rbp-88h] BYREF
  int v31[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v32; // [rsp+90h] [rbp-78h] BYREF
  int v33[2]; // [rsp+98h] [rbp-70h] BYREF
  int v34[2]; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v35[2]; // [rsp+A8h] [rbp-60h] BYREF
  BSTR *v36; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v37; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v38; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v40; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v41; // [rsp+118h] [rbp+10h]
  __int128 v42; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v43; // [rsp+138h] [rbp+30h]
  __int128 v44; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v45; // [rsp+158h] [rbp+50h]
  unsigned __int16 v46[264]; // [rsp+168h] [rbp+60h] BYREF

  *(_QWORD *)v34 = 0;
  *(_QWORD *)v31 = 0;
  *(_QWORD *)v30 = 0;
  *(_QWORD *)v33 = 0;
  v32 = 0;
  v7 = StringCchPrintfW(v46, 0x104u, L"/serverid \"%s\" /lookuptype 1 /initiator %d ", a1, a4);
  LODWORD(Data) = v7;
  v35[0] = "ScheduleOMADMClientTaskHelper";
  v35[1] = &Data;
  if ( (v7 & 0x80000000) != 0 )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v35);
    if ( !v32 )
      goto LABEL_5;
    v8 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
    goto LABEL_4;
  }
  LODWORD(Data) = CreateTask(
                    (LPVOID *)v34,
                    (BSTR ***)v31,
                    v30,
                    v33,
                    a1,
                    L"%windir%\\system32\\omadmclient.exe ",
                    v46,
                    a2,
                    0,
                    1,
                    0,
                    0,
                    0);
  v7 = Data;
  if ( (int)Data < 0 )
  {
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v35);
    if ( !v32 )
    {
LABEL_5:
      if ( *(_QWORD *)v33 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
      if ( *(_QWORD *)v30 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 16LL))(*(_QWORD *)v30);
      if ( *(_QWORD *)v31 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
      if ( *(_QWORD *)v34 )
      {
        v9 = *(void (**)(void))(**(_QWORD **)v34 + 16LL);
LABEL_13:
        v9();
        return v7;
      }
      return v7;
    }
    v8 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
LABEL_4:
    v8();
    goto LABEL_5;
  }
  v11 = *(__int64 **)v31;
  v12 = **(_QWORD **)v31;
  VariantInit(&pvarg);
  v13 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v38);
  v15 = *(_OWORD *)&v38.vt;
  v16 = v38.pRecInfo;
  if ( !a2 )
    a2 = L"S-1-5-18";
  v17 = SysAllocString(a2);
  if ( !v17 )
    goto LABEL_39;
  v18 = v37.pRecInfo;
  v19 = *(_QWORD *)v30;
  v37.vt = 8;
  v37.llVal = (LONGLONG)v17;
  v20 = *(_OWORD *)&v37.vt;
  v21 = (BSTR *)operator new(0x18u);
  v21[1] = 0;
  *((_DWORD *)v21 + 4) = 1;
  v22 = SysAllocString(psz);
  *v21 = v22;
  if ( !v22 )
  {
    if ( psz )
LABEL_39:
      _com_issue_error(-2147024882);
  }
  v36 = v21;
  v23 = v22;
  v24 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(v12 + 136);
  v40 = v13;
  v41 = pRecInfo;
  v42 = v15;
  v43 = v16;
  v44 = v20;
  v45 = v18;
  LODWORD(Data) = v24(v11, v23, v19, 6, &v44, &v42, 3, &v40, &v32);
  _bstr_t::~_bstr_t((_bstr_t *)&v36);
  v25 = VariantClear(&v37);
  if ( v25 < 0 )
    _com_issue_error(v25);
  v26 = VariantClear(&v38);
  if ( v26 < 0 )
    _com_issue_error(v26);
  v27 = VariantClear(&pvarg);
  if ( v27 < 0 )
    _com_issue_error(v27);
  v7 = Data;
  if ( (int)Data < 0 )
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"54RegisterTaskDefinition", 4u, &Data, 4u);
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data, "ScheduleOMADMClientTaskHelper");
    v7 = Data;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v35);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( *(_QWORD *)v33 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
  if ( *(_QWORD *)v30 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 16LL))(*(_QWORD *)v30);
  if ( *(_QWORD *)v31 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
  if ( *(_QWORD *)v34 )
  {
    v9 = *(void (**)(void))(**(_QWORD **)v34 + 16LL);
    goto LABEL_13;
  }
  return v7;
}

```

## disassembly

```asm
0x180021748  mov     rax, rsp
0x18002174b  push    rbp
0x18002174c  push    rbx
0x18002174d  push    rsi
0x18002174e  push    rdi
0x18002174f  push    r14
0x180021751  push    r15
0x180021753  lea     rbp, [rax-318h]
0x18002175a  sub     rsp, 3E8h
0x180021761  movaps  xmmword ptr [rax-48h], xmm6
0x180021765  movaps  xmmword ptr [rax-58h], xmm7
0x180021769  movaps  xmmword ptr [rax-68h], xmm8
0x18002176e  movaps  xmmword ptr [rax-78h], xmm9
0x180021773  movaps  xmmword ptr [rax-88h], xmm10
0x18002177b  movaps  xmmword ptr [rax-98h], xmm11
0x180021783  mov     rax, cs:__security_cookie
0x18002178a  xor     rax, rsp
0x18002178d  mov     [rbp+310h+var_A0], rax
0x180021794  mov     dword ptr [rsp+410h+lpData], r9d
0x180021799  mov     r14, r8
0x18002179c  mov     r9, rcx
0x18002179f  mov     qword ptr [rbp+310h+var_378], 0
0x1800217a7  mov     rdi, rdx
0x1800217aa  mov     qword ptr [rbp+310h+var_390], 0
0x1800217b2  mov     rsi, rcx
0x1800217b5  mov     qword ptr [rsp+410h+var_398], 0
0x1800217be  lea     rcx, [rbp+310h+var_2B0]; unsigned __int16 *
0x1800217c2  mov     qword ptr [rbp+310h+var_380], 0
0x1800217ca  lea     r8, aServeridSLooku; "/serverid \"%s\" /lookuptype 1 /initiat"...
0x1800217d1  mov     [rbp+310h+var_388], 0
0x1800217d9  mov     edx, 104h; unsigned __int64
0x1800217de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800217e3  mov     ebx, eax
0x1800217e5  mov     dword ptr [rsp+410h+Data], eax
0x1800217e9  lea     rax, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x1800217f0  mov     [rbp+310h+var_370], rax
0x1800217f4  lea     rax, [rsp+410h+Data]
0x1800217f9  mov     [rbp+310h+var_368], rax
0x1800217fd  test    ebx, ebx
0x1800217ff  jns     loc_1800218BB
0x180021805  lea     rcx, [rbp+310h+var_370]; this
0x180021809  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002180e  mov     rcx, [rbp+310h+var_388]
0x180021812  test    rcx, rcx
0x180021815  jz      short loc_180021823
0x180021817  mov     rax, [rcx]
0x18002181a  mov     rax, [rax+10h]
0x18002181e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021823  mov     rcx, qword ptr [rbp+310h+var_380]
0x180021827  test    rcx, rcx
0x18002182a  jz      short loc_180021838
0x18002182c  mov     rax, [rcx]
0x18002182f  mov     rax, [rax+10h]
0x180021833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021838  mov     rcx, qword ptr [rsp+410h+var_398]
0x18002183d  test    rcx, rcx
0x180021840  jz      short loc_18002184E
0x180021842  mov     rax, [rcx]
0x180021845  mov     rax, [rax+10h]
0x180021849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002184e  mov     rcx, qword ptr [rbp+310h+var_390]
0x180021852  test    rcx, rcx
0x180021855  jz      short loc_180021863
0x180021857  mov     rax, [rcx]
0x18002185a  mov     rax, [rax+10h]
0x18002185e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021863  mov     rcx, qword ptr [rbp+310h+var_378]
0x180021867  test    rcx, rcx
0x18002186a  jz      short loc_180021878
0x18002186c  mov     rax, [rcx]
0x18002186f  mov     rax, [rax+10h]
0x180021873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021878  mov     eax, ebx
0x18002187a  mov     rcx, [rbp+310h+var_A0]
0x180021881  xor     rcx, rsp; StackCookie
0x180021884  call    __security_check_cookie
0x180021889  lea     r11, [rsp+410h+var_28]
0x180021891  movaps  xmm6, xmmword ptr [r11-18h]
0x180021896  movaps  xmm7, xmmword ptr [r11-28h]
0x18002189b  movaps  xmm8, xmmword ptr [r11-38h]
0x1800218a0  movaps  xmm9, xmmword ptr [r11-48h]
0x1800218a5  movaps  xmm10, xmmword ptr [r11-58h]
0x1800218aa  movaps  xmm11, xmmword ptr [r11-68h]
0x1800218af  mov     rsp, r11
0x1800218b2  pop     r15
0x1800218b4  pop     r14
0x1800218b6  pop     rdi
0x1800218b7  pop     rsi
0x1800218b8  pop     rbx
0x1800218b9  pop     rbp
0x1800218ba  retn
0x1800218bb  mov     [rsp+410h+var_3B0], 0; Data
0x1800218c3  lea     rax, [rbp+310h+var_2B0]
0x1800218c7  mov     [rsp+410h+var_3B8], 0; int
0x1800218cf  lea     r9, [rbp+310h+var_380]; int
0x1800218d3  mov     [rsp+410h+var_3C0], 0; int
0x1800218db  lea     r8, [rsp+410h+var_398]; int
0x1800218e0  mov     [rsp+410h+var_3C8], 1; int
0x1800218e8  lea     rdx, [rbp+310h+var_390]; int
0x1800218ec  mov     [rsp+410h+var_3D0], 0; int
0x1800218f4  lea     rcx, [rbp+310h+var_378]; int
0x1800218f8  mov     [rsp+410h+var_3D8], rdi; unsigned __int16 *
0x1800218fd  mov     [rsp+410h+var_3E0], rax; unsigned __int16 *
0x180021902  lea     rax, aWindirSystem32; "%windir%\\system32\\omadmclient.exe "
0x180021909  mov     qword ptr [rsp+410h+cbData], rax; unsigned __int16 *
0x18002190e  mov     [rsp+410h+lpData], rsi; OLECHAR *
0x180021913  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180021918  mov     dword ptr [rsp+410h+Data], eax
0x18002191c  mov     ebx, eax
0x18002191e  test    eax, eax
0x180021920  jns     short loc_180021944
0x180021922  lea     rcx, [rbp+310h+var_370]; this
0x180021926  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002192b  mov     rcx, [rbp+310h+var_388]
0x18002192f  test    rcx, rcx
0x180021932  jz      loc_180021823
0x180021938  mov     rdx, [rcx]
0x18002193b  mov     rax, [rdx+10h]
0x18002193f  jmp     loc_18002181E
0x180021944  mov     rsi, qword ptr [rbp+310h+var_390]
0x180021948  lea     rcx, [rbp+310h+pvarg]; pvarg
0x18002194c  mov     r15, [rsi]
0x18002194f  call    cs:__imp_VariantInit
0x180021955  movups  xmm8, xmmword ptr [rbp+310h+pvarg]
0x18002195a  lea     rcx, [rbp+310h+var_340]; pvarg
0x18002195e  movsd   xmm9, qword ptr [rbp+310h+pvarg+10h]
0x180021964  call    cs:__imp_VariantInit
0x18002196a  movups  xmm10, xmmword ptr [rbp+310h+var_340]
0x18002196f  lea     rax, aS1518; "S-1-5-18"
0x180021976  test    rdi, rdi
0x180021979  movsd   xmm11, qword ptr [rbp+310h+var_340+10h]
0x18002197f  cmovz   rdi, rax
0x180021983  mov     rcx, rdi; psz
0x180021986  call    cs:__imp_SysAllocString
0x18002198c  test    rax, rax
0x18002198f  jz      loc_180021B66
0x180021995  movsd   xmm7, qword ptr [rbp+310h+var_358+10h]
0x18002199a  mov     ecx, 8
0x18002199f  mov     rdi, qword ptr [rsp+410h+var_398]
0x1800219a4  mov     word ptr [rbp+310h+var_358], cx
0x1800219a8  mov     ecx, 18h; Size
0x1800219ad  mov     qword ptr [rbp+310h+var_358+8], rax
0x1800219b1  movups  xmm6, xmmword ptr [rbp+310h+var_358]
0x1800219b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800219ba  mov     rcx, r14; psz
0x1800219bd  mov     rbx, rax
0x1800219c0  mov     qword ptr [rax+8], 0
0x1800219c8  mov     dword ptr [rax+10h], 1
0x1800219cf  call    cs:__imp_SysAllocString
0x1800219d5  mov     [rbx], rax
0x1800219d8  test    rax, rax
0x1800219db  jnz     short loc_1800219E6
0x1800219dd  test    r14, r14
0x1800219e0  jnz     loc_180021B66
0x1800219e6  lea     rcx, [rbp+310h+var_388]
0x1800219ea  mov     [rbp+310h+var_360], rbx
0x1800219ee  mov     qword ptr [rsp+410h+var_3D0], rcx
0x1800219f3  mov     rdx, rax
0x1800219f6  mov     rax, [r15+88h]
0x1800219fd  lea     rcx, [rbp+310h+var_310]
0x180021a01  mov     [rsp+410h+var_3D8], rcx
0x180021a06  mov     r9d, 6
0x180021a0c  lea     rcx, [rbp+310h+var_2F0]
0x180021a10  mov     dword ptr [rsp+410h+var_3E0], 3
0x180021a18  mov     qword ptr [rsp+410h+cbData], rcx
0x180021a1d  mov     r8, rdi
0x180021a20  lea     rcx, [rbp+310h+var_2D0]
0x180021a24  movaps  [rbp+310h+var_310], xmm8
0x180021a29  mov     [rsp+410h+lpData], rcx
0x180021a2e  mov     rcx, rsi
0x180021a31  movsd   [rbp+310h+var_300], xmm9
0x180021a37  movaps  [rbp+310h+var_2F0], xmm10
0x180021a3c  movsd   [rbp+310h+var_2E0], xmm11
0x180021a42  movaps  [rbp+310h+var_2D0], xmm6
0x180021a46  movsd   [rbp+310h+var_2C0], xmm7
0x180021a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a50  lea     rcx, [rbp+310h+var_360]; this
0x180021a54  mov     dword ptr [rsp+410h+Data], eax
0x180021a58  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180021a5d  lea     rcx, [rbp+310h+var_358]; pvarg
0x180021a61  call    cs:__imp_VariantClear
0x180021a67  test    eax, eax
0x180021a69  js      loc_180021B71
0x180021a6f  lea     rcx, [rbp+310h+var_340]; pvarg
0x180021a73  call    cs:__imp_VariantClear
0x180021a79  test    eax, eax
0x180021a7b  js      loc_180021B79
0x180021a81  lea     rcx, [rbp+310h+pvarg]; pvarg
0x180021a85  call    cs:__imp_VariantClear
0x180021a8b  test    eax, eax
0x180021a8d  js      loc_180021B5E
0x180021a93  mov     ebx, dword ptr [rsp+410h+Data]
0x180021a97  test    ebx, ebx
0x180021a99  jns     short loc_180021AE7
0x180021a9b  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180021aa2  lea     rax, [rsp+410h+Data]
0x180021aa7  mov     r9d, 4; dwType
0x180021aad  lea     r8, a54registertask; "54RegisterTaskDefinition"
0x180021ab4  mov     [rsp+410h+cbData], r9d; cbData
0x180021ab9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021ac0  mov     [rsp+410h+lpData], rax; lpData
0x180021ac5  call    cs:__imp_RegSetKeyValueW
0x180021acb  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180021ad0  mov     edx, dword ptr [rsp+410h+Data]; int
0x180021ad4  lea     r8, aScheduleomadmc; "ScheduleOMADMClientTaskHelper"
0x180021adb  mov     rcx, rax; this
0x180021ade  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180021ae3  mov     ebx, dword ptr [rsp+410h+Data]
0x180021ae7  lea     rcx, [rbp+310h+var_370]; this
0x180021aeb  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180021af0  mov     rcx, [rbp+310h+var_388]
0x180021af4  test    rcx, rcx
0x180021af7  jz      short loc_180021B05
0x180021af9  mov     rax, [rcx]
0x180021afc  mov     rax, [rax+10h]
0x180021b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b05  mov     rcx, qword ptr [rbp+310h+var_380]
0x180021b09  test    rcx, rcx
0x180021b0c  jz      short loc_180021B1A
0x180021b0e  mov     rax, [rcx]
0x180021b11  mov     rax, [rax+10h]
0x180021b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b1a  mov     rcx, qword ptr [rsp+410h+var_398]
0x180021b1f  test    rcx, rcx
0x180021b22  jz      short loc_180021B30
0x180021b24  mov     rax, [rcx]
0x180021b27  mov     rax, [rax+10h]
0x180021b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b30  mov     rcx, qword ptr [rbp+310h+var_390]
0x180021b34  test    rcx, rcx
0x180021b37  jz      short loc_180021B45
0x180021b39  mov     rax, [rcx]
0x180021b3c  mov     rax, [rax+10h]
0x180021b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b45  mov     rcx, qword ptr [rbp+310h+var_378]
0x180021b49  test    rcx, rcx
0x180021b4c  jz      loc_180021878
0x180021b52  mov     rdx, [rcx]
0x180021b55  mov     rax, [rdx+10h]
0x180021b59  jmp     loc_180021873
0x180021b5e  mov     ecx, eax; int
0x180021b60  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180021b66  mov     ecx, 8007000Eh; int
0x180021b6b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180021b71  mov     ecx, eax; int
0x180021b73  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180021b79  mov     ecx, eax; int
0x180021b7b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
