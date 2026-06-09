# CDBDataSourceAdmin::CreateDataSource(ulong,tagDBPROPSET * const,IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x18007a4e0`
- end: `0x18007adc9`
- name: `?CreateDataSource@CDBDataSourceAdmin@@UEAAJKQEAUtagDBPROPSET@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU3@@Z`
- size: `2281`
- prototype: `__int64 __fastcall(CDBDataSourceAdmin *__hidden this, unsigned int, struct tagDBPROPSET *const, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x18001ceb0`
- `0x18001d07c`
- `0x180022ce0`
- `0x180029560`
- `0x18002a93c`
- `0x18002c024`
- `0x18002ec0c`
- `0x18005b3a0`
- `0x18006e3b0`
- `0x180072cec`
- `0x180078e50`
- `0x18007a4e0`
- `0x180087010`

## string_xrefs

- `0x18007a56e`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a59e`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a5f0`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a665`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a683`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a6fc`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a71a`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a79c`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a7ba`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a861`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a87f`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a8e3`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a9b6`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a9d2`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007ab05`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007ab23`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007abef`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007ac0d`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007ad38`: `<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> `
- `0x18007a69e`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007a735`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007a7d5`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007a89a`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007a902`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007a9ed`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007ab42`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007ac2c`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007ad53`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `
- `0x18007ad9a`: `<CDBDataSourceAdmin::CreateDataSource|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDBDataSourceAdmin::CreateDataSource(
        CDBDataSourceAdmin *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3,
        struct IUnknown *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  const struct _GUID *v8; // r12
  __int64 v9; // rax
  int v11; // esi
  int inserted; // edi
  CAcm *v13; // rcx
  void *ProviderInterface; // r14
  struct CDPO *CDPO; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // edi
  int v20; // edi
  int v21; // edi
  CAcm *v22; // r15
  _BYTE *v23; // rsi
  struct IUnknown *v24; // rax
  struct IUnknown *v25; // r15
  const struct _GUID *v26; // rdx
  CSCM *v27; // rsi
  struct IUnknown *v28; // rdx
  int v29; // esi
  int v30; // esi
  unsigned int v31; // edi
  __int64 v32; // rax
  CAcm *v33; // rcx
  int v34; // [rsp+40h] [rbp-A8h]
  CAcm *v35; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-98h] BYREF
  struct IUnknown *v37; // [rsp+58h] [rbp-90h] BYREF
  CSCM *v38; // [rsp+60h] [rbp-88h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp-80h] BYREF
  int v40; // [rsp+6Ch] [rbp-7Ch] BYREF
  int v41; // [rsp+70h] [rbp-78h] BYREF
  int v42; // [rsp+74h] [rbp-74h] BYREF
  int v43; // [rsp+78h] [rbp-70h] BYREF
  int v44; // [rsp+7Ch] [rbp-6Ch] BYREF
  int v45; // [rsp+80h] [rbp-68h] BYREF
  int v46; // [rsp+84h] [rbp-64h] BYREF
  unsigned int v47; // [rsp+88h] [rbp-60h] BYREF
  void *v48; // [rsp+90h] [rbp-58h]
  __int64 v49; // [rsp+98h] [rbp-50h] BYREF
  struct _GUID v50; // [rsp+A0h] [rbp-48h] BYREF

  v37 = 0;
  v36 = 0;
  v35 = 0;
  if ( a6 )
  {
    *a6 = 0;
    if ( a4 )
    {
      v8 = a5;
      v9 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
      if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
        v9 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IUnknown.Data4;
      if ( v9 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147217886, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x33u);
        return 2147749410LL;
      }
      goto LABEL_14;
    }
LABEL_13:
    v8 = a5;
LABEL_14:
    v11 = -2147418113;
    inserted = -2147418113;
    v34 = -2147418113;
    v48 = 0;
    v13 = (CAcm *)*((_QWORD *)this + 7);
    if ( *((_BYTE *)v13 + 817) )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147217838, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x39u);
      return 2147749458LL;
    }
    else
    {
      try
      {
        ProviderInterface = CAcm::GetProviderInterface(v13, &IID_IDBDataSourceAdmin);
        v48 = ProviderInterface;
        if ( ProviderInterface )
        {
          CDPO = CDCM::GetCDPO(*((CDCM **)this + 7));
          if ( (*((_BYTE *)CDPO + 232) & 1) != 0 )
          {
            v19 = CDPO::CompleteSettingProps(CDPO);
            if ( v19 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v19, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x4Au);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v19, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x4Au);
                  if ( (bidGblFlags & 2) != 0 )
                    v19 = bidTraceHR(
                            off_1800C8528[0],
                            75785,
                            L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                            (unsigned int)v19);
                }
              }
              pExceptionObject = v19;
              throw (long *)&pExceptionObject;
            }
          }
          if ( !a6 )
          {
            v31 = (*(__int64 (__fastcall **)(void *, _QWORD, struct tagDBPROPSET *const, _QWORD, const struct _GUID *, _QWORD))(*(_QWORD *)ProviderInterface + 24LL))(
                    ProviderInterface,
                    a2,
                    a3,
                    0,
                    v8,
                    0);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v31, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x71u);
              if ( (bidGblFlags & 2) != 0 )
                v31 = bidTraceHR(off_1800C8528[0], 115721, L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ", v31);
            }
            v47 = v31;
            throw (long *)&v47;
          }
          v20 = NewCM<CSCM>::CoCreateCM(v17, v16, v18, &v37);
          if ( v20 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v20, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x52u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v20, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x52u);
                if ( (bidGblFlags & 2) != 0 )
                  v20 = bidTraceHR(
                          off_1800C8528[0],
                          83977,
                          L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                          (unsigned int)v20);
              }
            }
            v40 = v20;
            throw (long *)&v40;
          }
          v21 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, CAcm **))v37->lpVtbl->QueryInterface)(
                  v37,
                  &IID_IService,
                  &v35);
          if ( v21 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v21, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x55u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v21, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x55u);
                if ( (bidGblFlags & 2) != 0 )
                  v21 = bidTraceHR(
                          off_1800C8528[0],
                          87049,
                          L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                          (unsigned int)v21);
              }
            }
            v41 = v21;
            throw (long *)&v41;
          }
          v22 = v35;
          v38 = v35;
          inserted = (*(__int64 (__fastcall **)(void *, _QWORD, struct tagDBPROPSET *const, CAcm *, GUID *, __int64 *))(*(_QWORD *)ProviderInterface + 24LL))(
                       ProviderInterface,
                       a2,
                       a3,
                       v35,
                       &IID_IUnknown,
                       &v36);
          v34 = inserted;
          if ( inserted < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(inserted, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x62u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(inserted, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x62u);
                if ( (bidGblFlags & 2) != 0 )
                  inserted = bidTraceHR(
                               off_1800C8528[0],
                               100361,
                               L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                               (unsigned int)inserted);
              }
            }
            v42 = inserted;
            throw (long *)&v42;
          }
          if ( !v36 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(-2147418113, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", v36 + 100);
              if ( (bidGblFlags & 2) != 0 )
                v11 = bidTraceHR(
                        off_1800C8528[0],
                        102409,
                        L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                        2147549183LL);
            }
            v43 = v11;
            throw (long *)&v43;
          }
          v49 = 0;
          if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v36)(v36, &IID_IDBCreateCommand, &v49) >= 0 )
          {
            v50 = IID_IDBCreateCommand;
            inserted = CAcm::InsertDynamicInterface(v22, &v50);
            v34 = inserted;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            if ( inserted < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(inserted, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x7Eu);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(inserted, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x7Eu);
                  if ( (bidGblFlags & 2) != 0 )
                    inserted = bidTraceHR(
                                 off_1800C8528[0],
                                 129033,
                                 L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                                 (unsigned int)inserted);
                }
              }
              v44 = inserted;
              throw (long *)&v44;
            }
          }
          if ( (*(int (__fastcall **)(CAcm *, __int64))(*(_QWORD *)v35 + 24LL))(v35, v36) >= 0 )
          {
            v23 = (_BYTE *)*((_QWORD *)this + 7);
            v24 = (struct IUnknown *)CAcm::GetProviderInterface((CAcm *)v23, &IID_IDBInitialize);
            v25 = v24;
            v23[817] = 1;
            if ( v24 )
            {
              CSupportedPropDispenser::Initialize((CSupportedPropDispenser *)(v23 + 408), v24);
              ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
              CAcm::EnableDynamicInterface((CAcm *)v23, v26);
            }
            v27 = v38;
            CAcm::StoreParentCMUnknown(v38, *((void **)this + 7));
            *((_QWORD *)v27 + 44) = *((_QWORD *)this + 7) + 408LL;
            v28 = *(struct IUnknown **)(*((_QWORD *)this + 7) + 464LL);
            if ( v28 )
              CSCM::StoreDPO(v27, v28);
            if ( a4 )
            {
              v38 = 0;
              v30 = (**(__int64 (__fastcall ***)(CAcm *, GUID *, CSCM **))v35)(v35, &IID_IOuterUnknown, &v38);
              if ( v30 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v30, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0xA6u);
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(v30, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0xA6u);
                    if ( (bidGblFlags & 2) != 0 )
                      v30 = bidTraceHR(
                              off_1800C8528[0],
                              169993,
                              L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                              (unsigned int)v30);
                  }
                }
                v46 = v30;
                throw (long *)&v46;
              }
              if ( v35 )
              {
                (*(void (__fastcall **)(CAcm *))(*(_QWORD *)v35 + 16LL))(v35);
                v35 = 0;
              }
              (*(void (__fastcall **)(CSCM *, struct IUnknown *))(*(_QWORD *)v38 + 40LL))(v38, a4);
              if ( v38 )
              {
                (*(void (__fastcall **)(CSCM *))(*(_QWORD *)v38 + 16LL))(v38);
                v38 = 0;
              }
              *a6 = v37;
              v37 = 0;
            }
            else
            {
              v29 = (**(__int64 (__fastcall ***)(CAcm *, const struct _GUID *, struct IUnknown **))v35)(v35, v8, a6);
              if ( v29 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v29, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x9Bu);
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(v29, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x9Bu);
                    if ( (bidGblFlags & 2) != 0 )
                      v29 = bidTraceHR(
                              off_1800C8528[0],
                              158729,
                              L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                              (unsigned int)v29);
                  }
                }
                v45 = v29;
                throw (long *)&v45;
              }
              ((void (__fastcall *)(struct IUnknown *))v37->lpVtbl->Release)(v37);
              v37 = 0;
              if ( v35 )
              {
                (*(void (__fastcall **)(CAcm *))(*(_QWORD *)v35 + 16LL))(v35);
                v35 = 0;
              }
            }
            if ( v36 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              v36 = 0;
            }
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ProviderInterface + 16LL))(ProviderInterface);
          v48 = 0;
        }
      }
      catch ( ... )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800C8E38[0] )
          bidTraceA(off_1800C8528[0], 197632, off_1800C8E38[0], 0);
        v32 = *((_QWORD *)this + 7);
        if ( *(_BYTE *)(v32 + 817) )
        {
          v33 = (CAcm *)*((_QWORD *)this + 7);
          *(_WORD *)(v32 + 817) = 256;
          CAcm::DisableDynamicInterface(v33, &IID_IDBCreateSession);
        }
        if ( v48 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v48 + 16LL))(v48);
        if ( v35 )
        {
          (*(void (__fastcall **)(CAcm *))(*(_QWORD *)v35 + 16LL))(v35);
          v35 = 0;
        }
        if ( v36 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          v36 = 0;
        }
        if ( v37 )
          ((void (__fastcall *)(struct IUnknown *))v37->lpVtbl->Release)(v37);
        if ( a6 && *a6 )
        {
          ((void (__fastcall *)(_QWORD))(*a6)->lpVtbl->Release)(*a6);
          *a6 = 0;
        }
        if ( v34 >= 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            OLEDBTraceErr(-2147418113, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0xDFu);
          v34 = -2147418113;
        }
        inserted = v34;
      }
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C8528[0],
                               233481,
                               L"<CDBDataSourceAdmin::CreateDataSource|Trace|HR> ",
                               (unsigned int)inserted);
      return (unsigned int)inserted;
    }
  }
  if ( !a4 )
    goto LABEL_13;
  if ( (bidGblFlags & 2) != 0 )
    OLEDBTraceErr(-2147024809, L"<CDBDataSourceAdmin::CreateDataSource|OLEDB|ERR> ", 0x2Cu);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18007a4e0  mov     rax, rsp
0x18007a4e3  mov     [rax+20h], r9
0x18007a4e7  mov     [rax+18h], r8
0x18007a4eb  mov     [rax+10h], edx
0x18007a4ee  mov     [rax+8], rcx
0x18007a4f2  push    rbx
0x18007a4f3  push    rsi
0x18007a4f4  push    rdi
0x18007a4f5  push    r12
0x18007a4f7  push    r13
0x18007a4f9  push    r14
0x18007a4fb  push    r15
0x18007a4fd  sub     rsp, 0B0h
0x18007a504  mov     rax, r9
0x18007a507  mov     r15, r8
0x18007a50a  mov     rbx, rcx
0x18007a50d  xor     edx, edx
0x18007a50f  mov     [rsp+0E8h+var_90], rdx
0x18007a514  mov     [rsp+0E8h+var_98], rdx
0x18007a519  mov     [rsp+0E8h+var_A0], rdx
0x18007a51e  mov     r13, [rsp+0E8h+arg_28]
0x18007a526  test    r13, r13
0x18007a529  jz      short loc_18007A589
0x18007a52b  mov     [r13+0], rdx
0x18007a52f  test    rax, rax
0x18007a532  jz      loc_18007A5B9
0x18007a538  mov     r12, [rsp+0E8h+arg_20]
0x18007a540  mov     rax, [r12]
0x18007a544  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18007a54b  jnz     short loc_18007A559
0x18007a54d  mov     rax, [r12+8]
0x18007a552  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18007a559  test    rax, rax
0x18007a55c  jz      short loc_18007A5C1
0x18007a55e  mov     bl, 2
0x18007a560  test    byte ptr cs:_bidGblFlags, bl
0x18007a566  jz      short loc_18007A57F
0x18007a568  mov     r8d, 33h ; '3'; unsigned int
0x18007a56e  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a575  mov     ecx, 80040E22h; int
0x18007a57a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a57f  mov     eax, 80040E22h
0x18007a584  jmp     loc_18007ADB6
0x18007a589  test    rax, rax
0x18007a58c  jz      short loc_18007A5B9
0x18007a58e  mov     bl, 2
0x18007a590  test    byte ptr cs:_bidGblFlags, bl
0x18007a596  jz      short loc_18007A5AF
0x18007a598  mov     r8d, 2Ch ; ','; unsigned int
0x18007a59e  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a5a5  mov     ecx, 80070057h; int
0x18007a5aa  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a5af  mov     eax, 80070057h
0x18007a5b4  jmp     loc_18007ADB6
0x18007a5b9  mov     r12, [rsp+0E8h+arg_20]
0x18007a5c1  mov     esi, 8000FFFFh
0x18007a5c6  mov     edi, esi
0x18007a5c8  mov     [rsp+0E8h+var_A8], esi
0x18007a5cc  mov     [rsp+0E8h+var_58], rdx
0x18007a5d4  mov     rcx, [rcx+38h]; this
0x18007a5d8  cmp     [rcx+331h], dl
0x18007a5de  jz      short loc_18007A60B
0x18007a5e0  mov     bl, 2
0x18007a5e2  test    byte ptr cs:_bidGblFlags, bl
0x18007a5e8  jz      short loc_18007A601
0x18007a5ea  mov     r8d, 39h ; '9'; unsigned int
0x18007a5f0  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a5f7  mov     ecx, 80040E52h; int
0x18007a5fc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a601  mov     eax, 80040E52h
0x18007a606  jmp     loc_18007ADB6
0x18007a60b  lea     rdx, IID_IDBDataSourceAdmin; struct _GUID *
0x18007a612  call    ?GetProviderInterface@CAcm@@QEAAPEAXAEBU_GUID@@@Z; CAcm::GetProviderInterface(_GUID const &)
0x18007a617  mov     r14, rax
0x18007a61a  mov     [rsp+0E8h+var_58], rax
0x18007a622  test    rax, rax
0x18007a625  jz      loc_18007ACF1
0x18007a62b  mov     rcx, [rbx+38h]; this
0x18007a62f  call    ?GetCDPO@CDCM@@QEAAPEAVCDPO@@XZ; CDCM::GetCDPO(void)
0x18007a634  test    byte ptr [rax+0E8h], 1
0x18007a63b  jz      loc_18007A6CD
0x18007a641  mov     rcx, rax; this
0x18007a644  call    ?CompleteSettingProps@CDPO@@QEAAJXZ; CDPO::CompleteSettingProps(void)
0x18007a649  mov     edi, eax
0x18007a64b  mov     [rsp+0E8h+var_A8], eax
0x18007a64f  test    eax, eax
0x18007a651  jns     short loc_18007A6CD
0x18007a653  mov     eax, cs:_bidGblFlags
0x18007a659  mov     bl, 2
0x18007a65b  test    bl, al
0x18007a65d  jz      short loc_18007A6B8
0x18007a65f  mov     r8d, 4Ah ; 'J'; unsigned int
0x18007a665  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a66c  mov     ecx, edi; int
0x18007a66e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a673  mov     eax, cs:_bidGblFlags
0x18007a679  test    bl, al
0x18007a67b  jz      short loc_18007A6B8
0x18007a67d  mov     r8d, 4Ah ; 'J'; unsigned int
0x18007a683  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a68a  mov     ecx, edi; int
0x18007a68c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a691  mov     eax, cs:_bidGblFlags
0x18007a697  test    bl, al
0x18007a699  jz      short loc_18007A6B8
0x18007a69b  mov     r9d, edi
0x18007a69e  lea     r8, aCdbdatasourcea_4; "<CDBDataSourceAdmin::CreateDataSource|T"...
0x18007a6a5  mov     edx, 12809h
0x18007a6aa  mov     rcx, cs:off_1800C8528; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007a6b1  call    _bidTraceHR
0x18007a6b6  mov     edi, eax
0x18007a6b8  mov     [rsp+0E8h+pExceptionObject], edi
0x18007a6bc  lea     rdx, _TI1J; pThrowInfo
0x18007a6c3  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18007a6c8  call    _CxxThrowException_0
0x18007a6cd  test    r13, r13
0x18007a6d0  jz      loc_18007ACF6
0x18007a6d6  lea     r9, [rsp+0E8h+var_90]
0x18007a6db  call    ?CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z; NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)
0x18007a6e0  mov     edi, eax
0x18007a6e2  mov     [rsp+0E8h+var_A8], eax
0x18007a6e6  test    eax, eax
0x18007a6e8  jns     short loc_18007A764
0x18007a6ea  mov     eax, cs:_bidGblFlags
0x18007a6f0  mov     bl, 2
0x18007a6f2  test    bl, al
0x18007a6f4  jz      short loc_18007A74F
0x18007a6f6  mov     r8d, 52h ; 'R'; unsigned int
0x18007a6fc  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a703  mov     ecx, edi; int
0x18007a705  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a70a  mov     eax, cs:_bidGblFlags
0x18007a710  test    bl, al
0x18007a712  jz      short loc_18007A74F
0x18007a714  mov     r8d, 52h ; 'R'; unsigned int
0x18007a71a  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a721  mov     ecx, edi; int
0x18007a723  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a728  mov     eax, cs:_bidGblFlags
0x18007a72e  test    bl, al
0x18007a730  jz      short loc_18007A74F
0x18007a732  mov     r9d, edi
0x18007a735  lea     r8, aCdbdatasourcea_4; "<CDBDataSourceAdmin::CreateDataSource|T"...
0x18007a73c  mov     edx, 14809h
0x18007a741  mov     rcx, cs:off_1800C8528; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007a748  call    _bidTraceHR
0x18007a74d  mov     edi, eax
0x18007a74f  mov     [rsp+0E8h+var_7C], edi
0x18007a753  lea     rdx, _TI1J; pThrowInfo
0x18007a75a  lea     rcx, [rsp+0E8h+var_7C]; pExceptionObject
0x18007a75f  call    _CxxThrowException_0
0x18007a764  mov     rcx, [rsp+0E8h+var_90]
0x18007a769  mov     rax, [rcx]
0x18007a76c  lea     r8, [rsp+0E8h+var_A0]
0x18007a771  lea     rdx, IID_IService
0x18007a778  mov     rax, [rax]
0x18007a77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a780  mov     edi, eax
0x18007a782  mov     [rsp+0E8h+var_A8], eax
0x18007a786  test    eax, eax
0x18007a788  jns     short loc_18007A804
0x18007a78a  mov     eax, cs:_bidGblFlags
0x18007a790  mov     bl, 2
0x18007a792  test    bl, al
0x18007a794  jz      short loc_18007A7EF
0x18007a796  mov     r8d, 55h ; 'U'; unsigned int
0x18007a79c  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a7a3  mov     ecx, edi; int
0x18007a7a5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a7aa  mov     eax, cs:_bidGblFlags
0x18007a7b0  test    bl, al
0x18007a7b2  jz      short loc_18007A7EF
0x18007a7b4  mov     r8d, 55h ; 'U'; unsigned int
0x18007a7ba  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a7c1  mov     ecx, edi; int
0x18007a7c3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a7c8  mov     eax, cs:_bidGblFlags
0x18007a7ce  test    bl, al
0x18007a7d0  jz      short loc_18007A7EF
0x18007a7d2  mov     r9d, edi
0x18007a7d5  lea     r8, aCdbdatasourcea_4; "<CDBDataSourceAdmin::CreateDataSource|T"...
0x18007a7dc  mov     edx, 15409h
0x18007a7e1  mov     rcx, cs:off_1800C8528; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007a7e8  call    _bidTraceHR
0x18007a7ed  mov     edi, eax
0x18007a7ef  mov     [rsp+0E8h+var_78], edi
0x18007a7f3  lea     rdx, _TI1J; pThrowInfo
0x18007a7fa  lea     rcx, [rsp+0E8h+var_78]; pExceptionObject
0x18007a7ff  call    _CxxThrowException_0
0x18007a804  mov     r15, [rsp+0E8h+var_A0]
0x18007a809  mov     [rsp+0E8h+var_88], r15
0x18007a80e  mov     rax, [r14]
0x18007a811  lea     rcx, [rsp+0E8h+var_98]
0x18007a816  mov     [rsp+0E8h+var_C0], rcx
0x18007a81b  lea     rcx, IID_IUnknown
0x18007a822  mov     [rsp+0E8h+var_C8], rcx
0x18007a827  mov     r9, r15
0x18007a82a  mov     r8, [rsp+0E8h+arg_10]
0x18007a832  mov     edx, [rsp+0E8h+arg_8]
0x18007a839  mov     rcx, r14
0x18007a83c  mov     rax, [rax+18h]
0x18007a840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a845  mov     edi, eax
0x18007a847  mov     [rsp+0E8h+var_A8], eax
0x18007a84b  test    eax, eax
0x18007a84d  jns     short loc_18007A8C9
0x18007a84f  mov     eax, cs:_bidGblFlags
0x18007a855  mov     bl, 2
0x18007a857  test    bl, al
0x18007a859  jz      short loc_18007A8B4
0x18007a85b  mov     r8d, 62h ; 'b'; unsigned int
0x18007a861  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a868  mov     ecx, edi; int
0x18007a86a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a86f  mov     eax, cs:_bidGblFlags
0x18007a875  test    bl, al
0x18007a877  jz      short loc_18007A8B4
0x18007a879  mov     r8d, 62h ; 'b'; unsigned int
0x18007a87f  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a886  mov     ecx, edi; int
0x18007a888  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a88d  mov     eax, cs:_bidGblFlags
0x18007a893  test    bl, al
0x18007a895  jz      short loc_18007A8B4
0x18007a897  mov     r9d, edi
0x18007a89a  lea     r8, aCdbdatasourcea_4; "<CDBDataSourceAdmin::CreateDataSource|T"...
0x18007a8a1  mov     edx, 18809h
0x18007a8a6  mov     rcx, cs:off_1800C8528; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007a8ad  call    _bidTraceHR
0x18007a8b2  mov     edi, eax
0x18007a8b4  mov     [rsp+0E8h+var_74], edi
0x18007a8b8  lea     rdx, _TI1J; pThrowInfo
0x18007a8bf  lea     rcx, [rsp+0E8h+var_74]; pExceptionObject
0x18007a8c4  call    _CxxThrowException_0
0x18007a8c9  mov     rcx, [rsp+0E8h+var_98]
0x18007a8ce  test    rcx, rcx
0x18007a8d1  jnz     short loc_18007A937
0x18007a8d3  mov     eax, cs:_bidGblFlags
0x18007a8d9  mov     bl, 2
0x18007a8db  test    bl, al
0x18007a8dd  jz      short loc_18007A91E
0x18007a8df  lea     r8d, [rcx+64h]; unsigned int
0x18007a8e3  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a8ea  mov     ecx, esi; int
0x18007a8ec  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a8f1  mov     eax, cs:_bidGblFlags
0x18007a8f7  test    bl, al
0x18007a8f9  jz      short loc_18007A91E
0x18007a8fb  mov     [rsp+0E8h+var_A8], esi
0x18007a8ff  mov     r9d, esi
0x18007a902  lea     r8, aCdbdatasourcea_4; "<CDBDataSourceAdmin::CreateDataSource|T"...
0x18007a909  mov     edx, 19009h
0x18007a90e  mov     rcx, cs:off_1800C8528; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007a915  call    _bidTraceHR
0x18007a91a  mov     esi, eax
0x18007a91c  jmp     short loc_18007A922
0x18007a91e  mov     [rsp+0E8h+var_A8], esi
0x18007a922  mov     [rsp+0E8h+var_70], esi
0x18007a926  lea     rdx, _TI1J; pThrowInfo
0x18007a92d  lea     rcx, [rsp+0E8h+var_70]; pExceptionObject
0x18007a932  call    _CxxThrowException_0
0x18007a937  mov     [rsp+0E8h+var_50], 0
0x18007a943  mov     rax, [rcx]
0x18007a946  lea     r8, [rsp+0E8h+var_50]
0x18007a94e  lea     rdx, IID_IDBCreateCommand
0x18007a955  mov     rax, [rax]
0x18007a958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a95d  test    eax, eax
0x18007a95f  js      loc_18007AA1C
0x18007a965  movups  xmm0, xmmword ptr cs:IID_IDBCreateCommand.Data1
0x18007a96c  movdqu  xmmword ptr [rsp+0E8h+var_48.Data1], xmm0
0x18007a975  lea     rdx, [rsp+0E8h+var_48]; struct _GUID
0x18007a97d  mov     rcx, r15; this
0x18007a980  call    ?InsertDynamicInterface@CAcm@@QEAAJU_GUID@@@Z; CAcm::InsertDynamicInterface(_GUID)
0x18007a985  mov     edi, eax
0x18007a987  mov     [rsp+0E8h+var_A8], eax
0x18007a98b  mov     rcx, [rsp+0E8h+var_50]
0x18007a993  mov     rax, [rcx]
0x18007a996  mov     rax, [rax+10h]
0x18007a99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a99f  xor     r15d, r15d
0x18007a9a2  test    edi, edi
0x18007a9a4  jns     short loc_18007AA1F
0x18007a9a6  mov     eax, cs:_bidGblFlags
0x18007a9ac  mov     bl, 2
0x18007a9ae  test    bl, al
0x18007a9b0  jz      short loc_18007AA07
0x18007a9b2  lea     r8d, [r15+7Eh]; unsigned int
0x18007a9b6  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a9bd  mov     ecx, edi; int
0x18007a9bf  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a9c4  mov     eax, cs:_bidGblFlags
0x18007a9ca  test    bl, al
0x18007a9cc  jz      short loc_18007AA07
0x18007a9ce  lea     r8d, [r15+7Eh]; unsigned int
0x18007a9d2  lea     rdx, aCdbdatasourcea_6; "<CDBDataSourceAdmin::CreateDataSource|O"...
0x18007a9d9  mov     ecx, edi; int
0x18007a9db  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007a9e0  mov     eax, cs:_bidGblFlags
0x18007a9e6  test    bl, al
  ... truncated ...
```
