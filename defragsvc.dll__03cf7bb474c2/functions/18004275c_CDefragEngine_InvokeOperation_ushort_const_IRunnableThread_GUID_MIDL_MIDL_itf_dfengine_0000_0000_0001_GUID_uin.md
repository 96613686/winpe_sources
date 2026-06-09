# CDefragEngine::_InvokeOperation(ushort const *,IRunnableThread *,_GUID *,__MIDL___MIDL_itf_dfengine_0000_0000_0001,_GUID *,uint)

- ea: `0x18004275c`
- end: `0x180042b38`
- name: `?_InvokeOperation@CDefragEngine@@AEAAJPEBGPEAUIRunnableThread@@PEAU_GUID@@W4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@2I@Z`
- size: `988`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, __int64, int, GUID *, unsigned int)`
- caller_count: `12`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003a2e0`
- `0x18003a540`
- `0x18003af80`
- `0x18003b3b0`
- `0x18003b970`
- `0x18003be80`
- `0x18003f150`
- `0x1800409c0`
- `0x180041af0`
- `0x1800420d0`
- `0x180045300`
- `0x180045b80`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180013824`
- `0x180017e94`
- `0x18001df64`
- `0x1800280bc`
- `0x18002dd8c`
- `0x18004275c`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042aa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042aa7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800428f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800428f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042ad7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004282c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004282c`

## pseudocode

```c
__int64 __fastcall CDefragEngine::_InvokeOperation(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        GUID *a6,
        unsigned int a7)
{
  int v10; // r14d
  struct IDefragAsyncWorker *v11; // rbx
  __int64 v12; // rcx
  GUID *v13; // rax
  __int16 v14; // ax
  CDefragEngine *v15; // rcx
  int VolumeDefragmentableStatus; // edi
  __int64 v17; // rdx
  int v18; // eax
  bool v19; // sf
  __int16 v20; // ax
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rax
  __int16 v22; // ax
  int v23; // eax
  unsigned int v24; // edi
  int v26; // [rsp+50h] [rbp-91h] BYREF
  HRESULT VolumeAsyncFromPath; // [rsp+58h] [rbp-89h] BYREF
  __int16 v28; // [rsp+5Ch] [rbp-85h]
  __int16 v29; // [rsp+5Eh] [rbp-83h]
  LPVOID pv; // [rsp+90h] [rbp-51h] BYREF
  unsigned __int16 *v31; // [rsp+98h] [rbp-49h] BYREF
  struct IDefragAsyncWorker *v32; // [rsp+A0h] [rbp-41h] BYREF
  CDfVolumeListItem *v33; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-31h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-29h]
  GUID v36; // [rsp+C0h] [rbp-21h] BYREF
  GUID pguid; // [rsp+D0h] [rbp-11h] BYREF

  v35 = a4;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&VolumeAsyncFromPath,
    "CDefragEngine::_InvokeOperation",
    0x1130u,
    1u);
  v10 = 0;
  v11 = 0;
  v32 = 0;
  pguid = 0;
  v33 = 0;
  pv = 0;
  v31 = 0;
  v34 = 0;
  v26 = 0;
  if ( !a6 )
  {
    v14 = 4415;
LABEL_35:
    VolumeAsyncFromPath = -2147024809;
    goto LABEL_36;
  }
  v12 = 16;
  v13 = a6;
  do
  {
    LOBYTE(v13->Data1) = 0;
    v13 = (GUID *)((char *)v13 + 1);
    --v12;
  }
  while ( v12 );
  v28 = 4415;
  v14 = 4416;
  if ( !a3 )
    goto LABEL_35;
  v28 = 4416;
  v14 = 4417;
  if ( !a2 )
    goto LABEL_35;
  VolumeAsyncFromPath = 0;
  v28 = 4417;
  VolumeAsyncFromPath = CoCreateGuid(&pguid);
  v14 = 4420;
  if ( VolumeAsyncFromPath >= 0 )
  {
    v28 = 4420;
    VolumeAsyncFromPath = CDefragEngine::_GetVolumeAsyncFromPath((CDefragEngine *)a1, a2, &v32, &v33);
    v11 = v32;
    v14 = 4423;
    if ( VolumeAsyncFromPath >= 0 )
    {
      v28 = 4423;
      VolumeAsyncFromPath = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, LPVOID *))(*(_QWORD *)v32 + 128LL))(
                              v32,
                              &pv);
      v14 = 4427;
      if ( VolumeAsyncFromPath >= 0 )
      {
        v28 = 4427;
        VolumeAsyncFromPath = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, unsigned __int16 **))(*(_QWORD *)v11 + 224LL))(
                                v11,
                                &v31);
        v14 = 4428;
        if ( VolumeAsyncFromPath >= 0 )
        {
          v28 = 4428;
          VolumeDefragmentableStatus = CDefragEngine::_GetVolumeDefragmentableStatus(v15, (unsigned __int16 *)pv, &v26);
          if ( VolumeDefragmentableStatus < 0 || v26 < 0 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
            v17 = (unsigned int)VolumeDefragmentableStatus;
            if ( VolumeDefragmentableStatus >= 0 )
              v17 = (unsigned int)v26;
            v18 = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, __int64))(*(_QWORD *)v11 + 72LL))(v11, v17);
            if ( v18 != -1996488694 )
            {
              VolumeAsyncFromPath = v18;
              v19 = v18 < 0;
              v20 = 4462;
              if ( v19 )
              {
LABEL_16:
                v29 = v20;
LABEL_33:
                LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
                goto LABEL_37;
              }
              v28 = 4462;
            }
            if ( VolumeDefragmentableStatus >= 0 )
            {
              VolumeAsyncFromPath = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, _QWORD))(*(_QWORD *)v11 + 248LL))(
                                      v11,
                                      (unsigned int)v26);
              v20 = 4473;
              if ( VolumeAsyncFromPath < 0 )
                goto LABEL_16;
              VolumeDefragmentableStatus = v26;
            }
            else
            {
              VolumeAsyncFromPath = CSxList<CDfVolumeList,CDfVolumeListItem>::Delete(*(_QWORD *)(a1 + 104), v33);
              v20 = 4468;
              if ( VolumeAsyncFromPath < 0 )
                goto LABEL_16;
            }
            v28 = v20;
            Log_DF_OPTIMIZE_RESULT(
              (struct CSxFunctionTracer *)&VolumeAsyncFromPath,
              0x117Du,
              v31,
              a7,
              VolumeDefragmentableStatus,
              0);
            VolumeAsyncFromPath = VolumeDefragmentableStatus;
            v20 = 4480;
            if ( VolumeDefragmentableStatus < 0 )
              goto LABEL_16;
            v10 = 1;
            v28 = 4480;
          }
          v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 216LL))(a1);
          VolumeAsyncFromPath = (**v21)(v21, &IID_IAsyncNotifications, &v34);
          v22 = 4486;
          if ( VolumeAsyncFromPath < 0 )
            goto LABEL_26;
          v28 = 4486;
          v36 = pguid;
          v23 = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, __int64, __int64, __int64, int, _DWORD, int, GUID *))(*(_QWORD *)v11 + 96LL))(
                  v11,
                  v34,
                  a3,
                  v35,
                  a5,
                  0,
                  100,
                  &v36);
          if ( v23 == -1996488704 )
          {
            VolumeAsyncFromPath = (*(__int64 (__fastcall **)(struct IDefragAsyncWorker *, GUID *))(*(_QWORD *)v11 + 152LL))(
                                    v11,
                                    &pguid);
            v22 = 4495;
            if ( VolumeAsyncFromPath >= 0 )
            {
              VolumeAsyncFromPath = 1;
LABEL_31:
              v28 = v22;
              *a6 = pguid;
LABEL_32:
              if ( !v10 )
                goto LABEL_37;
              goto LABEL_33;
            }
          }
          else
          {
            VolumeAsyncFromPath = v23;
            v19 = v23 < 0;
            v22 = 4500;
            if ( !v19 )
              goto LABEL_31;
          }
LABEL_26:
          v29 = v22;
          goto LABEL_32;
        }
      }
    }
  }
LABEL_36:
  v29 = v14;
LABEL_37:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v31);
  v31 = 0;
  v24 = VolumeAsyncFromPath;
  if ( v33 )
    CDfVolumeListItem::Release(v33);
  if ( v11 )
    (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)v11 + 16LL))(v11);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&VolumeAsyncFromPath);
  return v24;
}

```

## disassembly

```asm
0x18004275c  push    rbp
0x18004275e  push    rbx
0x18004275f  push    rdi
0x180042760  push    r12
0x180042762  push    r13
0x180042764  push    r14
0x180042766  push    r15
0x180042768  lea     rbp, [rsp-0Fh]
0x18004276d  sub     rsp, 0F0h
0x180042774  mov     rax, cs:__security_cookie
0x18004277b  xor     rax, rsp
0x18004277e  mov     [rbp+3Fh+var_40], rax
0x180042782  mov     [rbp+3Fh+var_68], r9
0x180042786  mov     r13, r8
0x180042789  mov     rdi, rdx
0x18004278c  mov     r15, rcx
0x18004278f  mov     r12, [rbp+3Fh+arg_28]
0x180042793  mov     r9d, 1; unsigned __int16
0x180042799  mov     r8d, 1130h; unsigned __int16
0x18004279f  lea     rdx, aCdefragengineI_1; "CDefragEngine::_InvokeOperation"
0x1800427a6  lea     rcx, [rsp+120h+var_C8]; this
0x1800427ab  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800427b0  nop
0x1800427b1  xor     r14d, r14d
0x1800427b4  mov     ebx, r14d
0x1800427b7  mov     [rbp+3Fh+var_80], rbx
0x1800427bb  xorps   xmm0, xmm0
0x1800427be  movups  xmmword ptr [rbp+3Fh+pguid.Data1], xmm0
0x1800427c2  mov     [rbp+3Fh+var_78], r14
0x1800427c6  mov     [rbp+3Fh+pv], r14
0x1800427ca  mov     [rbp+3Fh+var_88], r14
0x1800427ce  mov     [rbp+3Fh+var_70], r14
0x1800427d2  mov     [rsp+120h+var_D0], r14d
0x1800427d7  test    r12, r12
0x1800427da  jz      loc_180042AAF
0x1800427e0  lea     ecx, [r14+10h]
0x1800427e4  mov     rax, r12
0x1800427e7  mov     [rax], r14b
0x1800427ea  inc     rax
0x1800427ed  sub     rcx, 1
0x1800427f1  jnz     short loc_1800427E7
0x1800427f3  mov     eax, 113Fh
0x1800427f8  mov     [rsp+120h+var_C4], ax
0x1800427fd  mov     eax, 1140h
0x180042802  test    r13, r13
0x180042805  jz      loc_180042AB4
0x18004280b  mov     [rsp+120h+var_C4], ax
0x180042810  mov     eax, 1141h
0x180042815  test    rdi, rdi
0x180042818  jz      loc_180042AB4
0x18004281e  mov     [rsp+120h+var_C8], r14d
0x180042823  mov     [rsp+120h+var_C4], ax
0x180042828  lea     rcx, [rbp+3Fh+pguid]; pguid
0x18004282c  call    cs:__imp_CoCreateGuid
0x180042832  mov     [rsp+120h+var_C8], eax
0x180042836  test    eax, eax
0x180042838  mov     eax, 1144h
0x18004283d  js      loc_180042ABC
0x180042843  mov     [rsp+120h+var_C4], ax
0x180042848  lea     r9, [rbp+3Fh+var_78]; struct CDfVolumeListItem **
0x18004284c  lea     r8, [rbp+3Fh+var_80]; struct IDefragAsyncWorker **
0x180042850  mov     rdx, rdi; Src
0x180042853  mov     rcx, r15; this
0x180042856  call    ?_GetVolumeAsyncFromPath@CDefragEngine@@AEAAJPEBGPEAPEAUIDefragAsyncWorker@@PEAPEAVCDfVolumeListItem@@@Z; CDefragEngine::_GetVolumeAsyncFromPath(ushort const *,IDefragAsyncWorker * *,CDfVolumeListItem * *)
0x18004285b  mov     [rsp+120h+var_C8], eax
0x18004285f  mov     rbx, [rbp+3Fh+var_80]
0x180042863  test    eax, eax
0x180042865  mov     eax, 1147h
0x18004286a  js      loc_180042ABC
0x180042870  mov     [rsp+120h+var_C4], ax
0x180042875  mov     rax, [rbx]
0x180042878  lea     rdx, [rbp+3Fh+pv]
0x18004287c  mov     rcx, rbx
0x18004287f  mov     rax, [rax+80h]
0x180042886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004288b  mov     [rsp+120h+var_C8], eax
0x18004288f  test    eax, eax
0x180042891  mov     eax, 114Bh
0x180042896  js      loc_180042ABC
0x18004289c  mov     [rsp+120h+var_C4], ax
0x1800428a1  mov     rax, [rbx]
0x1800428a4  lea     rdx, [rbp+3Fh+var_88]
0x1800428a8  mov     rcx, rbx
0x1800428ab  mov     rax, [rax+0E0h]
0x1800428b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428b7  mov     [rsp+120h+var_C8], eax
0x1800428bb  test    eax, eax
0x1800428bd  mov     eax, 114Ch
0x1800428c2  js      loc_180042ABC
0x1800428c8  mov     [rsp+120h+var_C4], ax
0x1800428cd  lea     r8, [rsp+120h+var_D0]; int *
0x1800428d2  mov     rdx, [rbp+3Fh+pv]; unsigned __int16 *
0x1800428d6  call    ?_GetVolumeDefragmentableStatus@CDefragEngine@@AEAAJPEAGPEAJ@Z; CDefragEngine::_GetVolumeDefragmentableStatus(ushort *,long *)
0x1800428db  mov     edi, eax
0x1800428dd  test    eax, eax
0x1800428df  js      short loc_1800428EF
0x1800428e1  cmp     [rsp+120h+var_D0], 0
0x1800428e6  jge     loc_1800429BD
0x1800428ec  xor     r14d, r14d
0x1800428ef  lea     rcx, [r15+40h]; lpCriticalSection
0x1800428f3  call    cs:__imp_EnterCriticalSection
0x1800428f9  mov     rcx, [rbx]
0x1800428fc  mov     rax, [rcx+48h]
0x180042900  mov     rcx, rbx
0x180042903  test    edi, edi
0x180042905  mov     edx, edi
0x180042907  js      short loc_18004290D
0x180042909  mov     edx, [rsp+120h+var_D0]
0x18004290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042912  cmp     eax, 8900000Ah
0x180042917  jz      short loc_180042935
0x180042919  mov     [rsp+120h+var_C8], eax
0x18004291d  test    eax, eax
0x18004291f  mov     eax, 116Eh
0x180042924  jns     short loc_180042930
0x180042926  mov     [rsp+120h+var_C2], ax
0x18004292b  jmp     loc_180042AA3
0x180042930  mov     [rsp+120h+var_C4], ax
0x180042935  test    edi, edi
0x180042937  jns     short loc_180042955
0x180042939  mov     rdx, [rbp+3Fh+var_78]
0x18004293d  mov     rcx, [r15+68h]
0x180042941  call    ?Delete@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAVCDfVolumeListItem@@@Z; CSxList<CDfVolumeList,CDfVolumeListItem>::Delete(CDfVolumeListItem *)
0x180042946  mov     [rsp+120h+var_C8], eax
0x18004294a  test    eax, eax
0x18004294c  mov     eax, 1174h
0x180042951  jns     short loc_18004297C
0x180042953  jmp     short loc_180042926
0x180042955  mov     rax, [rbx]
0x180042958  mov     edx, [rsp+120h+var_D0]
0x18004295c  mov     rcx, rbx
0x18004295f  mov     rax, [rax+0F8h]
0x180042966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004296b  mov     [rsp+120h+var_C8], eax
0x18004296f  test    eax, eax
0x180042971  mov     eax, 1179h
0x180042976  js      short loc_180042926
0x180042978  mov     edi, [rsp+120h+var_D0]
0x18004297c  mov     [rsp+120h+var_C4], ax
0x180042981  mov     [rsp+120h+var_F8], r14d; int
0x180042986  mov     [rsp+120h+var_100], edi; int
0x18004298a  mov     r9d, [rbp+3Fh+arg_30]; unsigned int
0x18004298e  mov     r8, [rbp+3Fh+var_88]; unsigned __int16 *
0x180042992  mov     edx, 117Dh; unsigned int
0x180042997  lea     rcx, [rsp+120h+var_C8]; this
0x18004299c  call    ?Log_DF_OPTIMIZE_RESULT@@YAJPEAVCSxFunctionTracer@@KPEBGIJH@Z; Log_DF_OPTIMIZE_RESULT(CSxFunctionTracer *,ulong,ushort const *,uint,long,int)
0x1800429a1  mov     [rsp+120h+var_C8], edi
0x1800429a5  mov     eax, 1180h
0x1800429aa  test    edi, edi
0x1800429ac  js      loc_180042926
0x1800429b2  mov     r14d, 1
0x1800429b8  mov     [rsp+120h+var_C4], ax
0x1800429bd  mov     rax, [r15]
0x1800429c0  mov     rcx, r15
0x1800429c3  mov     rax, [rax+0D8h]
0x1800429ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429cf  mov     r9, rax
0x1800429d2  mov     rcx, [rax]
0x1800429d5  mov     rax, [rcx]
0x1800429d8  lea     r8, [rbp+3Fh+var_70]
0x1800429dc  lea     rdx, IID_IAsyncNotifications
0x1800429e3  mov     rcx, r9
0x1800429e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429eb  mov     [rsp+120h+var_C8], eax
0x1800429ef  test    eax, eax
0x1800429f1  mov     eax, 1186h
0x1800429f6  jns     short loc_180042A02
0x1800429f8  mov     [rsp+120h+var_C2], ax
0x1800429fd  jmp     loc_180042A9E
0x180042a02  mov     [rsp+120h+var_C4], ax
0x180042a07  movaps  xmm0, xmmword ptr [rbp+3Fh+pguid.Data1]
0x180042a0b  movdqa  [rbp+3Fh+var_60], xmm0
0x180042a10  mov     rax, [rbx]
0x180042a13  lea     rcx, [rbp+3Fh+var_60]
0x180042a17  mov     [rsp+120h+var_E8], rcx
0x180042a1c  mov     [rsp+120h+var_F0], 64h ; 'd'
0x180042a24  mov     [rsp+120h+var_F8], 0
0x180042a2c  mov     ecx, [rbp+3Fh+arg_20]
0x180042a2f  mov     [rsp+120h+var_100], ecx
0x180042a33  mov     r9, [rbp+3Fh+var_68]
0x180042a37  mov     r8, r13
0x180042a3a  mov     rdx, [rbp+3Fh+var_70]
0x180042a3e  mov     rcx, rbx
0x180042a41  mov     rax, [rax+60h]
0x180042a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a4a  cmp     eax, 89000000h
0x180042a4f  jnz     short loc_180042A7E
0x180042a51  mov     rax, [rbx]
0x180042a54  lea     rdx, [rbp+3Fh+pguid]
0x180042a58  mov     rcx, rbx
0x180042a5b  mov     rax, [rax+98h]
0x180042a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a67  mov     [rsp+120h+var_C8], eax
0x180042a6b  test    eax, eax
0x180042a6d  mov     eax, 118Fh
0x180042a72  js      short loc_1800429F8
0x180042a74  mov     [rsp+120h+var_C8], 1
0x180042a7c  jmp     short loc_180042A8F
0x180042a7e  mov     [rsp+120h+var_C8], eax
0x180042a82  test    eax, eax
0x180042a84  mov     eax, 1194h
0x180042a89  js      loc_1800429F8
0x180042a8f  mov     [rsp+120h+var_C4], ax
0x180042a94  movaps  xmm0, xmmword ptr [rbp+3Fh+pguid.Data1]
0x180042a98  movdqu  xmmword ptr [r12], xmm0
0x180042a9e  test    r14d, r14d
0x180042aa1  jz      short loc_180042AC1
0x180042aa3  lea     rcx, [r15+40h]; lpCriticalSection
0x180042aa7  call    cs:__imp_LeaveCriticalSection
0x180042aad  jmp     short loc_180042AC1
0x180042aaf  mov     eax, 113Fh
0x180042ab4  mov     [rsp+120h+var_C8], 80070057h
0x180042abc  mov     [rsp+120h+var_C2], ax
0x180042ac1  mov     rcx, [rbp+3Fh+pv]; pv
0x180042ac5  call    cs:__imp_CoTaskMemFree
0x180042acb  mov     [rbp+3Fh+pv], 0
0x180042ad3  mov     rcx, [rbp+3Fh+var_88]; pv
0x180042ad7  call    cs:__imp_CoTaskMemFree
0x180042add  mov     [rbp+3Fh+var_88], 0
0x180042ae5  mov     edi, [rsp+120h+var_C8]
0x180042ae9  mov     rcx, [rbp+3Fh+var_78]; this
0x180042aed  test    rcx, rcx
0x180042af0  jz      short loc_180042AF8
0x180042af2  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x180042af7  nop
0x180042af8  test    rbx, rbx
0x180042afb  jz      short loc_180042B0D
0x180042afd  mov     rdx, [rbx]
0x180042b00  mov     rcx, rbx
0x180042b03  mov     rax, [rdx+10h]
0x180042b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b0c  nop
0x180042b0d  lea     rcx, [rsp+120h+var_C8]; this
0x180042b12  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180042b17  mov     eax, edi
0x180042b19  mov     rcx, [rbp+3Fh+var_40]
0x180042b1d  xor     rcx, rsp; StackCookie
0x180042b20  call    __security_check_cookie
0x180042b25  add     rsp, 0F0h
0x180042b2c  pop     r15
0x180042b2e  pop     r14
0x180042b30  pop     r13
0x180042b32  pop     r12
0x180042b34  pop     rdi
0x180042b35  pop     rbx
0x180042b36  pop     rbp
0x180042b37  retn
```
