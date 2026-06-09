# DusmDataPlan::EvaluateUsageState(_GUID const &,_DUSM_MEDIA_TYPE,std::unordered_set<ulong,std::hash<ulong>,std::equal_to<ulong>,std::allocator<ulong>> const &,_FILETIME const &,bool,bool *)

- ea: `0x18003e258`
- end: `0x18003e512`
- name: `?EvaluateUsageState@DusmDataPlan@@QEAAXAEBU_GUID@@W4_DUSM_MEDIA_TYPE@@AEBV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@AEBU_FILETIME@@_NPEA_N@Z`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800186fc`

## callees

- `0x180007140`
- `0x180007c90`
- `0x180013444`
- `0x1800173ac`
- `0x1800177b0`
- `0x1800191b0`
- `0x18003e258`
- `0x18003edd0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e2cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e2cd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003e3c5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003e3c5`

## pseudocode

```c
__int64 __fastcall DusmDataPlan::EvaluateUsageState(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        unsigned __int8 a6,
        char *a7)
{
  __int64 *v7; // r13
  FILETIME v8; // rax
  __int64 v10; // rcx
  FILETIME *v14; // rax
  FILETIME v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // edx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r9
  bool v26; // cc
  char v27; // al
  unsigned __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 result; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // [rsp+70h] [rbp-81h] BYREF
  int v36; // [rsp+74h] [rbp-7Dh] BYREF
  __int64 v37; // [rsp+78h] [rbp-79h] BYREF
  __int64 v38; // [rsp+80h] [rbp-71h] BYREF
  __int64 v39; // [rsp+88h] [rbp-69h] BYREF
  __int64 v40; // [rsp+90h] [rbp-61h] BYREF
  __int64 v41; // [rsp+98h] [rbp-59h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-51h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-41h] BYREF
  FILETIME FileTime2; // [rsp+B8h] [rbp-39h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-31h] BYREF
  FILETIME FileTime1; // [rsp+C8h] [rbp-29h] BYREF
  _BYTE v48[8]; // [rsp+D0h] [rbp-21h] BYREF
  _BYTE v49[8]; // [rsp+D8h] [rbp-19h] BYREF

  v7 = (__int64 *)(a1 + 52);
  v8 = *(FILETIME *)(a1 + 52);
  v10 = *(_QWORD *)(a1 + 88);
  FileTime2 = v8;
  v14 = (FILETIME *)(*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v10 + 8LL))(v10, &v38, a1);
  v15 = *v14;
  *v7 = (__int64)*v14;
  FileTime1 = v15;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v16 = (*(__int64 (__fastcall **)(_QWORD, struct _FILETIME *, __int64 *))(**(_QWORD **)(a1 + 88) + 16LL))(
          *(_QWORD *)(a1 + 88),
          &SystemTimeAsFileTime,
          v7);
  v17 = *(_QWORD *)(a1 + 88);
  *(_DWORD *)(a1 + 156) = v16;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v17 + 24LL))(v17, a1 + 72, a1);
  v19 = *(_QWORD *)(a1 + 88);
  v46 = v18;
  (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v19 + 32LL))(v19, v48, a1);
  v20 = (***(__int64 (__fastcall ****)(_QWORD, _BYTE *, _BYTE *, __int64, unsigned int, __int64, __int64, __int64))(a1 + 88))(
          *(_QWORD *)(a1 + 88),
          v48,
          v49,
          a2,
          a3,
          a4,
          a5,
          a1);
  v21 = *(_DWORD *)(a1 + 156);
  v22 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 144) = v20;
  v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int))(*(_QWORD *)v22 + 40LL))(
          v22,
          a1 + 144,
          a1 + 136,
          &v46,
          v21);
  v24 = *(_QWORD *)(a1 + 88);
  v25 = *(unsigned int *)(a1 + 156);
  *(_DWORD *)(a1 + 68) = v23;
  *(_DWORD *)(a1 + 152) = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v24 + 48LL))(
                            v24,
                            a1 + 144,
                            a1 + 136,
                            v25);
  if ( !*(_DWORD *)(a1 + 48)
    || !*(_QWORD *)&FileTime2
    || (v26 = CompareFileTime(&FileTime1, &FileTime2) <= 0, v27 = 1, v26) )
  {
    v27 = 0;
  }
  *a7 = v27;
  ShowNotification(a3, *(_DWORD *)(a1 + 68), *(_DWORD *)(a1 + 152), *(_DWORD *)(a1 + 80) == 3, v7, a6);
  if ( *a7 && DusmTraceLoggingProvider::IsEnabled(v29, v28) )
  {
    wil::details::static_lazy<DusmTraceLoggingProvider>::get(v29, v28);
    DusmTraceLoggingProvider::TelemetryDataPlanEndOfCycleImpl(
      v30,
      a1,
      a3,
      *(unsigned int *)(a1 + 80),
      *(_DWORD *)(a1 + 68));
  }
  result = **(unsigned int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v29, v28) + 8);
  if ( (unsigned int)result > 5 )
  {
    v32 = *(unsigned int *)(a1 + 68);
    v35 = (unsigned __int8)*a7;
    v36 = *(_DWORD *)(a1 + 152);
    v39 = DusmDpuStateToSz(v32);
    v40 = v46;
    LODWORD(v37) = *(_DWORD *)(a1 + 156);
    v41 = *(_QWORD *)(a1 + 144);
    v42 = *(_QWORD *)(a1 + 136);
    v43 = *v7;
    v38 = *(_QWORD *)(a1 + 24);
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
             v33,
             (int)byte_18005BD51,
             v33,
             v34,
             (__int64)&v38,
             (__int64)&v43,
             (__int64)&v42,
             (__int64)&v41,
             (__int64)&v37,
             (__int64)&v40,
             (const WCHAR **)&v39,
             (__int64)&v36,
             (__int64)&v35);
  }
  return result;
}

```

## disassembly

```asm
0x18003e258  push    rbp
0x18003e25a  push    rbx
0x18003e25b  push    rsi
0x18003e25c  push    rdi
0x18003e25d  push    r12
0x18003e25f  push    r13
0x18003e261  push    r14
0x18003e263  push    r15
0x18003e265  lea     rbp, [rsp-7]
0x18003e26a  sub     rsp, 0F8h
0x18003e271  mov     rax, cs:__security_cookie
0x18003e278  xor     rax, rsp
0x18003e27b  mov     [rbp+3Fh+var_50], rax
0x18003e27f  mov     rbx, [rbp+3Fh+arg_20]
0x18003e283  lea     r13, [rcx+34h]
0x18003e287  mov     rax, [r13+0]
0x18003e28b  mov     r14, rcx
0x18003e28e  mov     rcx, [rcx+58h]
0x18003e292  mov     r12d, r8d
0x18003e295  mov     r15, [rbp+3Fh+arg_30]
0x18003e299  mov     rdi, rdx
0x18003e29c  mov     qword ptr [rbp+3Fh+FileTime2.dwLowDateTime], rax
0x18003e2a0  lea     rdx, [rbp+3Fh+var_B0]
0x18003e2a4  mov     r8, r14
0x18003e2a7  mov     rsi, r9
0x18003e2aa  mov     rax, [rcx]
0x18003e2ad  mov     rax, [rax+8]
0x18003e2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2b6  mov     rcx, [rax]
0x18003e2b9  mov     [r13+0], rcx
0x18003e2bd  mov     qword ptr [rbp+3Fh+FileTime1.dwLowDateTime], rcx
0x18003e2c1  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003e2c5  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003e2cd  call    cs:__imp_GetSystemTimeAsFileTime
0x18003e2d3  mov     rcx, [r14+58h]
0x18003e2d7  lea     rdx, [rbp+3Fh+SystemTimeAsFileTime]
0x18003e2db  mov     r8, r13
0x18003e2de  mov     rax, [rcx]
0x18003e2e1  mov     rax, [rax+10h]
0x18003e2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2ea  mov     rcx, [r14+58h]
0x18003e2ee  lea     rdx, [r14+48h]
0x18003e2f2  mov     [r14+9Ch], eax
0x18003e2f9  mov     r8, r14
0x18003e2fc  mov     rax, [rcx]
0x18003e2ff  mov     rax, [rax+18h]
0x18003e303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e308  mov     rcx, [r14+58h]
0x18003e30c  lea     rdx, [rbp+3Fh+var_60]
0x18003e310  mov     [rbp+3Fh+var_70], rax
0x18003e314  mov     r8, r14
0x18003e317  mov     rax, [rcx]
0x18003e31a  mov     rax, [rax+20h]
0x18003e31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e323  mov     rcx, [r14+58h]
0x18003e327  lea     r8, [rbp+3Fh+var_58]
0x18003e32b  mov     [rsp+130h+var_F8], r14
0x18003e330  lea     rdx, [rbp+3Fh+var_60]
0x18003e334  mov     [rsp+130h+var_100], rbx
0x18003e339  mov     r9, rdi
0x18003e33c  mov     [rsp+130h+var_108], rsi
0x18003e341  mov     rax, [rcx]
0x18003e344  mov     dword ptr [rsp+130h+var_110], r12d
0x18003e349  mov     rax, [rax]
0x18003e34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e351  mov     edx, [r14+9Ch]
0x18003e358  lea     rbx, [r14+90h]
0x18003e35f  mov     rcx, [r14+58h]
0x18003e363  lea     rdi, [r14+88h]
0x18003e36a  mov     [rbx], rax
0x18003e36d  lea     r9, [rbp+3Fh+var_70]
0x18003e371  mov     dword ptr [rsp+130h+var_110], edx
0x18003e375  mov     r8, rdi
0x18003e378  mov     rdx, rbx
0x18003e37b  mov     rax, [rcx]
0x18003e37e  mov     rax, [rax+28h]
0x18003e382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e387  mov     rcx, [r14+58h]
0x18003e38b  mov     r8, rdi
0x18003e38e  mov     r9d, [r14+9Ch]
0x18003e395  mov     rdx, rbx
0x18003e398  mov     [r14+44h], eax
0x18003e39c  mov     rax, [rcx]
0x18003e39f  mov     rax, [rax+30h]
0x18003e3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3a8  xor     esi, esi
0x18003e3aa  mov     [r14+98h], eax
0x18003e3b1  cmp     [r14+30h], esi
0x18003e3b5  jz      short loc_18003E3D1
0x18003e3b7  cmp     qword ptr [rbp+3Fh+FileTime2.dwLowDateTime], rsi
0x18003e3bb  jz      short loc_18003E3D1
0x18003e3bd  lea     rdx, [rbp+3Fh+FileTime2]; lpFileTime2
0x18003e3c1  lea     rcx, [rbp+3Fh+FileTime1]; lpFileTime1
0x18003e3c5  call    cs:__imp_CompareFileTime
0x18003e3cb  test    eax, eax
0x18003e3cd  mov     al, 1
0x18003e3cf  jg      short loc_18003E3D4
0x18003e3d1  mov     al, sil
0x18003e3d4  mov     [r15], al
0x18003e3d7  mov     r9d, esi
0x18003e3da  cmp     dword ptr [r14+50h], 3
0x18003e3df  mov     ecx, r12d
0x18003e3e2  movzx   eax, [rbp+3Fh+arg_28]
0x18003e3e6  mov     r8d, [r14+98h]
0x18003e3ed  setz    r9b
0x18003e3f1  mov     edx, [r14+44h]
0x18003e3f5  mov     dword ptr [rsp+130h+var_108], eax
0x18003e3f9  mov     [rsp+130h+var_110], r13
0x18003e3fe  call    ?ShowNotification@@YAXW4_DUSM_MEDIA_TYPE@@W4_DUSM_DPU_STATE@@HHAEBU_FILETIME@@H@Z; ShowNotification(_DUSM_MEDIA_TYPE,_DUSM_DPU_STATE,int,int,_FILETIME const &,int)
0x18003e403  cmp     [r15], sil
0x18003e406  jz      short loc_18003E42D
0x18003e408  call    ?IsEnabled@DusmTraceLoggingProvider@@SA_NE_K@Z; DusmTraceLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x18003e40d  test    al, al
0x18003e40f  jz      short loc_18003E42D
0x18003e411  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003e416  mov     eax, [r14+44h]
0x18003e41a  mov     r8d, r12d
0x18003e41d  mov     r9d, [r14+50h]
0x18003e421  mov     rdx, r14
0x18003e424  mov     dword ptr [rsp+130h+var_110], eax
0x18003e428  call    ?TelemetryDataPlanEndOfCycleImpl@DusmTraceLoggingProvider@@AEAAXAEBU_DUSM_DATAPLAN_STATUS@@W4_DUSM_MEDIA_TYPE@@W4_DUSM_SOURCE@@W4_DUSM_DPU_STATE@@@Z; DusmTraceLoggingProvider::TelemetryDataPlanEndOfCycleImpl(_DUSM_DATAPLAN_STATUS const &,_DUSM_MEDIA_TYPE,_DUSM_SOURCE,_DUSM_DPU_STATE)
0x18003e42d  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003e432  mov     r8, [rax+8]
0x18003e436  mov     eax, [r8]
0x18003e439  cmp     eax, 5
0x18003e43c  jbe     loc_18003E4F2
0x18003e442  movzx   eax, byte ptr [r15]
0x18003e446  mov     ecx, [r14+44h]
0x18003e44a  mov     dword ptr [rsp+130h+var_C0], eax
0x18003e44e  mov     eax, [r14+98h]
0x18003e455  mov     dword ptr [rbp+3Fh+var_C0+4], eax
0x18003e458  call    ?DusmDpuStateToSz@@YAPEB_WW4_DUSM_DPU_STATE@@@Z; DusmDpuStateToSz(_DUSM_DPU_STATE)
0x18003e45d  mov     [rbp+3Fh+var_A8], rax
0x18003e461  lea     rdx, byte_18005BD51
0x18003e468  mov     rax, [rbp+3Fh+var_70]
0x18003e46c  mov     rcx, r8; int
0x18003e46f  mov     [rbp+3Fh+var_A0], rax
0x18003e473  mov     eax, [r14+9Ch]
0x18003e47a  mov     dword ptr [rbp+3Fh+var_B8], eax
0x18003e47d  mov     rax, [rbx]
0x18003e480  mov     [rbp+3Fh+var_98], rax
0x18003e484  mov     rax, [rdi]
0x18003e487  mov     [rbp+3Fh+var_90], rax
0x18003e48b  mov     rax, [r13+0]
0x18003e48f  mov     [rbp+3Fh+var_88], rax
0x18003e493  mov     rax, [r14+18h]
0x18003e497  mov     [rbp+3Fh+var_B0], rax
0x18003e49b  lea     rax, [rsp+130h+var_C0]
0x18003e4a0  mov     [rsp+130h+var_D0], rax; __int64
0x18003e4a5  lea     rax, [rbp+3Fh+var_C0+4]
0x18003e4a9  mov     [rsp+130h+var_D8], rax; __int64
0x18003e4ae  lea     rax, [rbp+3Fh+var_A8]
0x18003e4b2  mov     [rsp+130h+var_E0], rax; __int64
0x18003e4b7  lea     rax, [rbp+3Fh+var_A0]
0x18003e4bb  mov     [rsp+130h+var_E8], rax; __int64
0x18003e4c0  lea     rax, [rbp+3Fh+var_B8]
0x18003e4c4  mov     [rsp+130h+var_F0], rax; __int64
0x18003e4c9  lea     rax, [rbp+3Fh+var_98]
0x18003e4cd  mov     [rsp+130h+var_F8], rax; __int64
0x18003e4d2  lea     rax, [rbp+3Fh+var_90]
0x18003e4d6  mov     [rsp+130h+var_100], rax; __int64
0x18003e4db  lea     rax, [rbp+3Fh+var_88]
0x18003e4df  mov     [rsp+130h+var_108], rax; __int64
0x18003e4e4  lea     rax, [rbp+3Fh+var_B0]
0x18003e4e8  mov     [rsp+130h+var_110], rax; __int64
0x18003e4ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@_W@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@333AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@_W@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e4f2  mov     rcx, [rbp+3Fh+var_50]
0x18003e4f6  xor     rcx, rsp; StackCookie
0x18003e4f9  call    __security_check_cookie
0x18003e4fe  add     rsp, 0F8h
0x18003e505  pop     r15
0x18003e507  pop     r14
0x18003e509  pop     r13
0x18003e50b  pop     r12
0x18003e50d  pop     rdi
0x18003e50e  pop     rsi
0x18003e50f  pop     rbx
0x18003e510  pop     rbp
0x18003e511  retn
```
