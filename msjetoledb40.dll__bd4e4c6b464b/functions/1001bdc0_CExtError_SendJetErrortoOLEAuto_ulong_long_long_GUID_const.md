# CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)

- ea: `0x1001bdc0`
- end: `0x1001c36f`
- name: `?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z`
- size: `1455`
- prototype: `static int __stdcall(unsigned int, int, int, const struct _GUID *)`
- caller_count: `109`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1000d5b0`
- `0x1000d6c0`
- `0x1000d7d0`
- `0x1000d8e0`
- `0x1000da40`
- `0x1000ddb0`
- `0x1000e140`
- `0x1000fcf0`
- `0x10010b50`
- `0x10010f80`
- `0x10011530`
- `0x100118b0`
- `0x10011d40`
- `0x100132e0`
- `0x10013890`
- `0x10016690`
- `0x100176f0`
- `0x10019070`
- `0x100198d0`
- `0x1001a970`
- `0x1001af60`
- `0x1001d7f0`
- `0x1001df20`
- `0x1001e350`
- `0x1001ebc0`
- `0x10025bf0`
- `0x10025e70`
- `0x10026110`
- `0x10026240`
- `0x10026380`
- `0x10026470`
- `0x100265e0`
- `0x10026740`
- `0x10026890`
- `0x10026bc0`
- `0x10026d80`
- `0x10027410`
- `0x10027660`
- `0x10028340`
- `0x10029a90`
- `0x1002b570`
- `0x1002c7d0`
- `0x1002ca20`
- `0x1002cb80`
- `0x1002d790`
- `0x1002d9b0`
- `0x1002db00`
- `0x1002e0b0`
- `0x1002e3e0`
- `0x1002ef90`

## callees

- `0x1000ed00`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`

## import_xrefs

- `msvcrt!_itow` at `0x1001c1ef`
- `msvcrt!_itow` at `0x1001c1ef`
- `KERNEL32!DeleteCriticalSection` at `0x1001c308`
- `KERNEL32!DeleteCriticalSection` at `0x1001c308`
- `KERNEL32!InitializeCriticalSection` at `0x1001c185`
- `KERNEL32!InitializeCriticalSection` at `0x1001c185`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1001c105`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1001c200`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1001c105`
- `OLEAUT32!__imp__SysAllocString@4` at `0x1001c200`
- `OLEAUT32!__imp__SysAllocStringLen@8` at `0x1001c0f8`
- `OLEAUT32!__imp__SysAllocStringLen@8` at `0x1001c0f8`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1001c2fe`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1001c2fe`
- `OLEAUT32!__imp__VariantInit@4` at `0x1001bfe8`
- `OLEAUT32!__imp__VariantInit@4` at `0x1001bfe8`
- `OLEAUT32!__imp__GetErrorInfo@8` at `0x1001be4d`
- `OLEAUT32!__imp__GetErrorInfo@8` at `0x1001be4d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001c288`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001c288`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1001be6e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1001be6e`
- `msjet40!__imp__JetGetLastErrorInfo@40` at `0x1001beeb`
- `msjet40!__imp__JetGetLastErrorInfo@40` at `0x1001beeb`
- `msjter40!__imp__JetErrIDAForError@8` at `0x1001c13d`
- `msjter40!__imp__JetErrIDAForError@8` at `0x1001c13d`
- `msjter40!__imp__JetErrFormattedMessage@32` at `0x1001bf86`
- `msjter40!__imp__JetErrFormattedMessage@32` at `0x1001bf86`

## pseudocode

```c
HRESULT __userpurge CExtError::SendJetErrortoOLEAuto@<eax>(
        int a1@<edx>,
        char *a2@<ecx>,
        unsigned int a3,
        int a4,
        int a5,
        const struct _GUID *a6)
{
  int v6; // ebx
  char *v7; // edi
  IErrorInfo *v9; // eax
  HRESULT Instance; // ebx
  HRESULT v11; // eax
  _DWORD *v12; // edx
  unsigned int i; // esi
  int v14; // ecx
  int v15; // esi
  int v16; // esi
  unsigned int v17; // edx
  const OLECHAR *v18; // ecx
  int v19; // ebx
  int v20; // esi
  BSTR v21; // eax
  unsigned int v22; // ecx
  char *v23; // eax
  char *v24; // eax
  BSTR v25; // eax
  _DWORD *v26; // eax
  struct tagDISPPARAMS *v27; // [esp+30h] [ebp-D20h]
  int v28; // [esp+34h] [ebp-D1Ch]
  int v29; // [esp+3Ch] [ebp-D14h] BYREF
  IErrorInfo *pperrinfo; // [esp+40h] [ebp-D10h] BYREF
  _DWORD v31[2]; // [esp+44h] [ebp-D0Ch] BYREF
  unsigned int v32; // [esp+4Ch] [ebp-D04h]
  int v33; // [esp+50h] [ebp-D00h]
  int v34; // [esp+54h] [ebp-CFCh]
  int Value; // [esp+58h] [ebp-CF8h] BYREF
  int v36; // [esp+5Ch] [ebp-CF4h] BYREF
  char *v37; // [esp+60h] [ebp-CF0h]
  int v38; // [esp+64h] [ebp-CECh]
  _DWORD v39[8]; // [esp+68h] [ebp-CE8h] BYREF
  int v40; // [esp+88h] [ebp-CC8h] BYREF
  int v41; // [esp+8Ch] [ebp-CC4h] BYREF
  int v42; // [esp+90h] [ebp-CC0h] BYREF
  int v43; // [esp+94h] [ebp-CBCh] BYREF
  int v44; // [esp+98h] [ebp-CB8h] BYREF
  unsigned int v45; // [esp+9Ch] [ebp-CB4h]
  int v46; // [esp+A0h] [ebp-CB0h]
  __int64 v47; // [esp+A4h] [ebp-CACh]
  int v48; // [esp+ACh] [ebp-CA4h] BYREF
  _DWORD v49[5]; // [esp+B0h] [ebp-CA0h]
  __int128 v50; // [esp+C4h] [ebp-C8Ch]
  int v51; // [esp+D4h] [ebp-C7Ch]
  wchar_t Buffer[52]; // [esp+D8h] [ebp-C78h] BYREF
  _WORD v53[256]; // [esp+140h] [ebp-C10h] BYREF
  _WORD v54[256]; // [esp+340h] [ebp-A10h] BYREF
  _WORD v55[256]; // [esp+540h] [ebp-810h] BYREF
  char v56[1548]; // [esp+740h] [ebp-610h] BYREF

  v6 = a1;
  v37 = a2;
  v7 = 0;
  v38 = a1;
  v34 = a4;
  Value = 0;
  pperrinfo = 0;
  v36 = 0;
  v29 = 0;
  v32 = 6;
  v31[1] = 0;
  v33 = 0;
  v31[0] = 0;
  if ( a1 == -2147024882 )
    return -2147467259;
  GetErrorInfo(0, &pperrinfo);
  v9 = pperrinfo;
  if ( pperrinfo )
    goto LABEL_8;
  Instance = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&pperrinfo);
  if ( Instance < 0 )
    goto LABEL_44;
  v9 = pperrinfo;
  if ( pperrinfo )
  {
    v6 = v38;
LABEL_8:
    ((void (__thiscall *)(HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **), IErrorInfo *, GUID *, int *))v9->lpVtbl->QueryInterface)(
      v9->lpVtbl->QueryInterface,
      v9,
      &IID_IErrorRecords,
      &v36);
    if ( !JetGetLastErrorInfo(v37, &v44, 20, v55, 256, v54, 256, v53, 256, &v40) )
      goto LABEL_11;
    v53[0] = 0;
    v54[0] = 0;
    v55[0] = 0;
    v47 = 0;
    v46 = 0;
    memset(&v39[2], 0, 12);
    v39[5] = v55;
    v39[6] = v54;
    v39[7] = v53;
    v45 = a3;
    v39[0] = 32;
    v39[1] = a3;
    if ( JetErrFormattedMessage(a3, v39, &Value, v56, 769, &v43, &v42, &v41) != 1069 )
    {
LABEL_11:
      v12 = (_DWORD *)(*(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12))(
                        *(_DWORD *)(*(_DWORD *)Sys + 12),
                        Sys,
                        16 * v32);
      v31[0] = v12;
      if ( v12 )
      {
        for ( i = 0; i < v32; ++i )
        {
          VariantInit((VARIANTARG *)&v12[4 * i]);
          v12 = (_DWORD *)v31[0];
        }
        v48 = v6;
        v49[0] = (unsigned __int16)a3 | (v45 << 16);
        v14 = 0;
        *(GUID *)&v49[1] = CLSID_JOLT;
        v51 = 0;
        v50 = *(_OWORD *)v34;
        while ( 1 )
        {
          while ( 1 )
          {
            v15 = 2 * v14;
            if ( v14 )
              break;
            v14 = 1;
            v12[2] = v46;
            *(_WORD *)(v31[0] + 8 * v15) = 3;
            v12 = (_DWORD *)v31[0];
          }
          if ( v14 != 1 )
            break;
          v14 = 2;
          v12[6] = v47;
          *(_WORD *)(v31[0] + 8 * v15) = 3;
          v12 = (_DWORD *)v31[0];
        }
        v12[10] = HIDWORD(v47);
        *(_WORD *)(v31[0] + 32) = 3;
        v16 = v31[0];
        v17 = 3;
        v34 = 3;
        while ( 1 )
        {
          v18 = 0;
          switch ( v17 )
          {
            case 3u:
              v18 = v55;
              break;
            case 4u:
              v18 = v54;
              break;
            case 5u:
              v18 = v53;
              break;
          }
          v19 = 2 * v17;
          *(_WORD *)(v16 + 16 * v17) = 8;
          v20 = v31[0];
          v21 = *v18 ? SysAllocStringLen(v18, 0x100u) : SysAllocString(&word_100046A0);
          *(_DWORD *)(v20 + 8 * v19 + 8) = v21;
          v16 = v31[0];
          if ( !*(_DWORD *)(v31[0] + 8 * v19 + 8) )
            break;
          v17 = v34 + 1;
          v34 = v17;
          if ( v17 >= 6 )
          {
            v22 = a3;
            if ( v45 )
              v22 = v45;
            if ( JetErrIDAForError(v22, &Value) || !Value )
              goto LABEL_39;
            v23 = (char *)operator new(0x30u);
            v7 = v23;
            v37 = v23;
            if ( !v23 )
            {
              v7 = 0;
              break;
            }
            *(_DWORD *)v23 = &CCustomErrorObject::`vftable';
            *((_DWORD *)v23 + 1) = 0;
            *((_DWORD *)v23 + 3) = 0;
            InitializeCriticalSection((LPCRITICAL_SECTION)(v23 + 16));
            *((_DWORD *)v7 + 10) = 0;
            *((_DWORD *)v7 + 11) = 0;
            *((_DWORD *)v7 + 2) = v7;
            v24 = (char *)operator new(0xCu);
            v37 = v24;
            if ( !v24 )
            {
              *((_DWORD *)v7 + 3) = 0;
              break;
            }
            *(_DWORD *)v24 = &CImpISQLErrorInfo::`vftable';
            *((_DWORD *)v24 + 1) = 0;
            *((_DWORD *)v24 + 2) = v7;
            *((_DWORD *)v7 + 3) = v24;
            *((_DWORD *)v7 + 10) = v49[0];
            Buffer[0] = 0;
            __itow(Value, Buffer, 10);
            v25 = SysAllocString(Buffer);
            *((_DWORD *)v7 + 11) = v25;
            if ( !v25 )
              break;
            Instance = (**(int (__thiscall ***)(_DWORD, void *, GUID *, int *))v7)(
                         **(_DWORD **)v7,
                         v7,
                         &IID_ISQLErrorInfo,
                         &v29);
            if ( Instance >= 0 )
            {
LABEL_39:
              Instance = (*(int (__thiscall **)(_DWORD, int, int *, _DWORD, _DWORD *, int, _DWORD))(*(_DWORD *)v36 + 12))(
                           *(_DWORD *)(*(_DWORD *)v36 + 12),
                           v36,
                           &v48,
                           v49[0],
                           v31,
                           v29,
                           0);
              v7 = 0;
              if ( Instance < 0 )
                goto LABEL_44;
              if ( v29 )
              {
                (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v29 + 8))(*(_DWORD *)(*(_DWORD *)v29 + 8), v29);
                v29 = 0;
              }
              v11 = SetErrorInfo(0, pperrinfo);
              v7 = 0;
              goto LABEL_43;
            }
            goto LABEL_44;
          }
        }
      }
      Instance = -2147024882;
      CError::ClearDispParams(v27);
      goto LABEL_48;
    }
    v11 = CExtError::SendHRtoOLEAuto(v34, a3, (const struct _GUID *)v27, v28);
LABEL_43:
    Instance = v11;
LABEL_44:
    CError::ClearDispParams(v27);
    if ( Instance >= 0 )
      goto LABEL_56;
LABEL_48:
    if ( v29 )
    {
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v29 + 8))(*(_DWORD *)(*(_DWORD *)v29 + 8), v29);
      v29 = 0;
    }
    if ( v7 )
    {
      v26 = (_DWORD *)*((_DWORD *)v7 + 3);
      *(_DWORD *)v7 = &CCustomErrorObject::`vftable';
      if ( v26 )
      {
        *v26 = &CImpISQLErrorInfo::`vftable';
        operator delete(v26);
      }
      if ( *((_DWORD *)v7 + 11) )
        SysFreeString(*((BSTR *)v7 + 11));
      DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      operator delete(v7);
    }
    goto LABEL_56;
  }
  CError::ClearDispParams(v27);
LABEL_56:
  if ( v36 )
  {
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v36 + 8))(*(_DWORD *)(*(_DWORD *)v36 + 8), v36);
    v36 = 0;
  }
  if ( pperrinfo )
    ((void (__thiscall *)(ULONG (__stdcall *)(IErrorInfo *), IErrorInfo *))pperrinfo->lpVtbl->Release)(
      pperrinfo->lpVtbl->Release,
      pperrinfo);
  return Instance;
}

```

## disassembly

```asm
0x1001bdc0  mov     edi, edi
0x1001bdc2  push    ebp
0x1001bdc3  mov     ebp, esp
0x1001bdc5  and     esp, 0FFFFFFF8h
0x1001bdc8  sub     esp, 0D14h
0x1001bdce  mov     eax, ___security_cookie
0x1001bdd3  xor     eax, esp
0x1001bdd5  mov     [esp+0D14h+var_4], eax
0x1001bddc  mov     eax, [ebp+arg_4]
0x1001bddf  push    ebx
0x1001bde0  push    esi; int
0x1001bde1  mov     ebx, edx
0x1001bde3  mov     [esp+0D1Ch+var_CF0], ecx
0x1001bde7  push    edi; struct tagDISPPARAMS *
0x1001bde8  xor     edi, edi
0x1001bdea  mov     [esp+0D20h+var_CEC], ebx
0x1001bdee  mov     [esp+0D20h+var_CFC], eax
0x1001bdf2  mov     [esp+0D20h+Value], 0
0x1001bdfa  mov     [esp+0D20h+pperrinfo], 0
0x1001be02  mov     [esp+0D20h+var_CF4], 0
0x1001be0a  mov     [esp+0D20h+var_D14], edi
0x1001be0e  mov     [esp+0D20h+var_D04], 6
0x1001be16  mov     [esp+0D20h+var_D08], edi
0x1001be1a  mov     [esp+0D20h+var_D00], edi
0x1001be1e  mov     [esp+0D20h+var_D0C], edi
0x1001be22  cmp     ebx, 8007000Eh
0x1001be28  jnz     short loc_1001BE46
0x1001be2a  mov     eax, 80004005h
0x1001be2f  pop     edi
0x1001be30  pop     esi
0x1001be31  pop     ebx
0x1001be32  mov     ecx, [esp+0D14h+var_4]
0x1001be39  xor     ecx, esp; StackCookie
0x1001be3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001be40  mov     esp, ebp
0x1001be42  pop     ebp
0x1001be43  retn    8
0x1001be46  lea     eax, [esp+0D20h+pperrinfo]
0x1001be4a  push    eax; pperrinfo
0x1001be4b  push    0; dwReserved
0x1001be4d  call    ds:__imp__GetErrorInfo@8; GetErrorInfo(x,x)
0x1001be53  mov     eax, [esp+0D20h+pperrinfo]
0x1001be57  test    eax, eax
0x1001be59  jnz     short loc_1001BE98
0x1001be5b  lea     eax, [esp+0D20h+pperrinfo]
0x1001be5f  push    eax; ppv
0x1001be60  push    offset _IID_IErrorInfo; riid
0x1001be65  push    1; dwClsContext
0x1001be67  push    0; pUnkOuter
0x1001be69  push    offset ?CLSID_EXTENDEDERRORINFO@@3U_GUID@@B; rclsid
0x1001be6e  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1001be74  mov     ebx, eax
0x1001be76  test    ebx, ebx
0x1001be78  js      loc_1001C292
0x1001be7e  mov     eax, [esp+0D20h+pperrinfo]
0x1001be82  test    eax, eax
0x1001be84  jnz     short loc_1001BE94
0x1001be86  lea     ecx, [esp+0D20h+var_D0C]
0x1001be8a  call    ?ClearDispParams@CError@@SGXPAUtagDISPPARAMS@@@Z; CError::ClearDispParams(tagDISPPARAMS *)
0x1001be8f  jmp     loc_1001C317
0x1001be94  mov     ebx, [esp+0D20h+var_CEC]
0x1001be98  mov     esi, [eax]
0x1001be9a  lea     ecx, [esp+0D20h+var_CF4]
0x1001be9e  push    ecx
0x1001be9f  push    offset _IID_IErrorRecords
0x1001bea4  push    eax
0x1001bea5  mov     esi, [esi]
0x1001bea7  mov     ecx, esi
0x1001bea9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001beaf  call    esi
0x1001beb1  lea     eax, [esp+0D20h+var_CC8]
0x1001beb5  push    eax
0x1001beb6  push    100h
0x1001bebb  lea     eax, [esp+0D28h+var_C10]
0x1001bec2  push    eax
0x1001bec3  push    100h
0x1001bec8  lea     eax, [esp+0D30h+var_A10]
0x1001becf  push    eax
0x1001bed0  push    100h
0x1001bed5  lea     eax, [esp+0D38h+var_810]
0x1001bedc  push    eax
0x1001bedd  push    14h
0x1001bedf  lea     eax, [esp+0D40h+var_CB8]
0x1001bee6  push    eax
0x1001bee7  push    [esp+0D44h+var_CF0]
0x1001beeb  call    ds:__imp__JetGetLastErrorInfo@40; JetGetLastErrorInfo(x,x,x,x,x,x,x,x,x,x)
0x1001bef1  test    eax, eax
0x1001bef3  jz      loc_1001BFA5
0x1001bef9  xor     eax, eax
0x1001befb  mov     esi, [ebp+arg_0]
0x1001befe  mov     [esp+0D20h+var_C10], ax
0x1001bf06  mov     [esp+0D20h+var_A10], ax
0x1001bf0e  mov     [esp+0D20h+var_810], ax
0x1001bf16  mov     dword ptr [esp+0D20h+var_CB0+8], eax
0x1001bf1a  mov     dword ptr [esp+0D20h+var_CB0+4], eax
0x1001bf1e  mov     dword ptr [esp+0D20h+var_CB0], eax
0x1001bf22  mov     [esp+0D20h+var_CE0], eax
0x1001bf26  mov     [esp+0D20h+var_CDC], eax
0x1001bf2a  mov     [esp+0D20h+var_CD8], eax
0x1001bf2e  lea     eax, [esp+0D20h+var_810]
0x1001bf35  mov     dword ptr [esp+0D20h+var_CD4], eax
0x1001bf39  lea     eax, [esp+0D20h+var_A10]
0x1001bf40  mov     dword ptr [esp+0D20h+var_CD0], eax
0x1001bf44  lea     eax, [esp+0D20h+var_C10]
0x1001bf4b  mov     dword ptr [esp+0D20h+var_CCC], eax
0x1001bf4f  lea     eax, [esp+0D20h+var_CC4]
0x1001bf53  push    eax
0x1001bf54  lea     eax, [esp+0D24h+var_CC0]
0x1001bf58  mov     [esp+0D24h+var_CB4], esi
0x1001bf5c  push    eax
0x1001bf5d  lea     eax, [esp+0D28h+var_CBC]
0x1001bf61  mov     [esp+0D28h+var_CE8], 20h ; ' '
0x1001bf69  push    eax
0x1001bf6a  push    301h
0x1001bf6f  lea     eax, [esp+0D30h+var_610]
0x1001bf76  mov     [esp+0D30h+var_CE4], esi
0x1001bf7a  push    eax
0x1001bf7b  lea     eax, [esp+0D34h+Value]
0x1001bf7f  push    eax
0x1001bf80  lea     eax, [esp+0D38h+var_CE8]
0x1001bf84  push    eax
0x1001bf85  push    esi
0x1001bf86  call    ds:__imp__JetErrFormattedMessage@32; JetErrFormattedMessage(x,x,x,x,x,x,x,x)
0x1001bf8c  cmp     eax, 42Dh
0x1001bf91  jnz     short loc_1001BFA5
0x1001bf93  mov     eax, [esp+0D20h+var_CFC]
0x1001bf97  mov     edx, ebx
0x1001bf99  push    esi; int
0x1001bf9a  push    eax; int
0x1001bf9b  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1001bfa0  jmp     loc_1001C290
0x1001bfa5  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1001bfab  mov     eax, [esp+0D20h+var_D04]
0x1001bfaf  shl     eax, 4
0x1001bfb2  push    eax
0x1001bfb3  mov     esi, [ecx]
0x1001bfb5  push    ecx
0x1001bfb6  mov     esi, [esi+0Ch]
0x1001bfb9  mov     ecx, esi
0x1001bfbb  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001bfc1  call    esi
0x1001bfc3  mov     edx, eax
0x1001bfc5  mov     [esp+0D20h+var_D0C], edx
0x1001bfc9  test    edx, edx
0x1001bfcb  jz      loc_1001C2A8
0x1001bfd1  xor     esi, esi
0x1001bfd3  cmp     [esp+0D20h+var_D04], esi
0x1001bfd7  jbe     short loc_1001BFF9
0x1001bfd9  nop     dword ptr [eax+00000000h]
0x1001bfe0  mov     eax, esi
0x1001bfe2  shl     eax, 4
0x1001bfe5  add     eax, edx
0x1001bfe7  push    eax; pvarg
0x1001bfe8  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1001bfee  mov     edx, [esp+0D20h+var_D0C]
0x1001bff2  inc     esi
0x1001bff3  cmp     esi, [esp+0D20h+var_D04]
0x1001bff7  jb      short loc_1001BFE0
0x1001bff9  mov     ecx, [esp+0D20h+var_CB4]
0x1001bffd  mov     eax, [ebp+arg_0]
0x1001c000  movups  xmm0, xmmword ptr ds:?CLSID_JOLT@@3U_GUID@@B.Data1; _GUID const CLSID_JOLT ...
0x1001c007  shl     ecx, 10h
0x1001c00a  movzx   eax, ax
0x1001c00d  or      ecx, eax
0x1001c00f  mov     dword ptr [esp+0D20h+var_CB0+0Ch], ebx
0x1001c013  mov     eax, [esp+0D20h+var_CFC]
0x1001c017  mov     dword ptr [esp+0D20h+var_CA0], ecx
0x1001c01e  xor     ecx, ecx
0x1001c020  movups  xmmword ptr [esp+0D20h+var_CA0+4], xmm0
0x1001c028  mov     [esp+0D20h+var_C7C], edi
0x1001c02f  movups  xmm0, xmmword ptr [eax]
0x1001c032  lea     ebx, [ecx+3]
0x1001c035  movups  [esp+0D20h+var_C8C], xmm0
0x1001c03d  nop     dword ptr [eax]
0x1001c040  mov     esi, ecx
0x1001c042  mov     eax, ecx
0x1001c044  add     esi, esi
0x1001c046  sub     eax, 0
0x1001c049  jz      short loc_1001C07A
0x1001c04b  sub     eax, 1
0x1001c04e  jz      short loc_1001C064
0x1001c050  sub     eax, 1
0x1001c053  jz      short loc_1001C090
0x1001c055  inc     ecx
0x1001c056  mov     [edx+esi*8], bx
0x1001c05a  cmp     ecx, ebx
0x1001c05c  jnb     short loc_1001C09F
0x1001c05e  mov     edx, [esp+0D20h+var_D0C]
0x1001c062  jmp     short loc_1001C040
0x1001c064  mov     eax, dword ptr [esp+0D20h+var_CB0+4]
0x1001c068  inc     ecx
0x1001c069  mov     [edx+18h], eax
0x1001c06c  mov     eax, [esp+0D20h+var_D0C]
0x1001c070  mov     [eax+esi*8], bx
0x1001c074  mov     edx, [esp+0D20h+var_D0C]
0x1001c078  jmp     short loc_1001C040
0x1001c07a  mov     eax, dword ptr [esp+0D20h+var_CB0]
0x1001c07e  inc     ecx
0x1001c07f  mov     [edx+8], eax
0x1001c082  mov     eax, [esp+0D20h+var_D0C]
0x1001c086  mov     [eax+esi*8], bx
0x1001c08a  mov     edx, [esp+0D20h+var_D0C]
0x1001c08e  jmp     short loc_1001C040
0x1001c090  mov     eax, dword ptr [esp+0D20h+var_CB0+8]
0x1001c094  mov     [edx+28h], eax
0x1001c097  mov     eax, [esp+0D20h+var_D0C]
0x1001c09b  mov     [eax+esi*8], bx
0x1001c09f  mov     esi, [esp+0D20h+var_D0C]
0x1001c0a3  mov     edx, ebx
0x1001c0a5  mov     [esp+0D20h+var_CFC], edx
0x1001c0a9  nop     dword ptr [eax+00000000h]
0x1001c0b0  mov     eax, edx
0x1001c0b2  xor     ecx, ecx
0x1001c0b4  sub     eax, 3
0x1001c0b7  jz      short loc_1001C0D5
0x1001c0b9  sub     eax, 1
0x1001c0bc  jz      short loc_1001C0CC
0x1001c0be  sub     eax, 1
0x1001c0c1  jnz     short loc_1001C0DC
0x1001c0c3  lea     ecx, [esp+0D20h+var_C10]
0x1001c0ca  jmp     short loc_1001C0DC
0x1001c0cc  lea     ecx, [esp+0D20h+var_A10]
0x1001c0d3  jmp     short loc_1001C0DC
0x1001c0d5  lea     ecx, [esp+0D20h+var_810]
0x1001c0dc  mov     ebx, edx
0x1001c0de  mov     eax, 8
0x1001c0e3  add     ebx, ebx
0x1001c0e5  mov     [esi+ebx*8], ax
0x1001c0e9  mov     esi, [esp+0D20h+var_D0C]
0x1001c0ed  cmp     [ecx], di
0x1001c0f0  jz      short loc_1001C100
0x1001c0f2  push    100h; ui
0x1001c0f7  push    ecx; strIn
0x1001c0f8  call    ds:__imp__SysAllocStringLen@8; SysAllocStringLen(x,x)
0x1001c0fe  jmp     short loc_1001C10B
0x1001c100  push    offset word_100046A0; psz
0x1001c105  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1001c10b  mov     [esi+ebx*8+8], eax
0x1001c10f  mov     esi, [esp+0D20h+var_D0C]
0x1001c113  cmp     [esi+ebx*8+8], edi
0x1001c117  jz      loc_1001C2A8
0x1001c11d  mov     edx, [esp+0D20h+var_CFC]
0x1001c121  inc     edx
0x1001c122  mov     [esp+0D20h+var_CFC], edx
0x1001c126  cmp     edx, 6
0x1001c129  jb      short loc_1001C0B0
0x1001c12b  mov     ecx, [ebp+arg_0]
0x1001c12e  lea     eax, [esp+0D20h+Value]
0x1001c132  push    eax
0x1001c133  mov     eax, [esp+0D24h+var_CB4]
0x1001c137  test    eax, eax
0x1001c139  cmovnz  ecx, eax
0x1001c13c  push    ecx
0x1001c13d  call    ds:__imp__JetErrIDAForError@8; JetErrIDAForError(x,x)
0x1001c143  test    eax, eax
0x1001c145  jnz     loc_1001C230
0x1001c14b  cmp     [esp+0D20h+Value], edi
0x1001c14f  jz      loc_1001C230
0x1001c155  push    30h ; '0'; Size
0x1001c157  call    ??2@YAPAXI@Z; operator new(uint)
0x1001c15c  mov     edi, eax
0x1001c15e  add     esp, 4
0x1001c161  mov     [esp+0D20h+var_CF0], edi
0x1001c165  test    edi, edi
0x1001c167  jz      loc_1001C368
0x1001c16d  lea     ecx, [edi+10h]
0x1001c170  mov     dword ptr [edi], offset ??_7CCustomErrorObject@@6B@; const CCustomErrorObject::`vftable'
0x1001c176  push    ecx; lpCriticalSection
0x1001c177  mov     dword ptr [edi+4], 0
0x1001c17e  mov     dword ptr [edi+0Ch], 0
0x1001c185  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1001c18b  mov     dword ptr [edi+28h], 0
0x1001c192  mov     dword ptr [edi+2Ch], 0
0x1001c199  mov     [edi+8], edi
0x1001c19c  test    edi, edi
0x1001c19e  jz      loc_1001C2A8
0x1001c1a4  push    0Ch; Size
0x1001c1a6  call    ??2@YAPAXI@Z; operator new(uint)
0x1001c1ab  add     esp, 4
0x1001c1ae  mov     [esp+0D20h+var_CF0], eax
0x1001c1b2  test    eax, eax
0x1001c1b4  jz      loc_1001C2A1
0x1001c1ba  mov     dword ptr [eax], offset ??_7CImpISQLErrorInfo@@6B@; const CImpISQLErrorInfo::`vftable'
0x1001c1c0  mov     dword ptr [eax+4], 0
0x1001c1c7  mov     [eax+8], edi
0x1001c1ca  mov     [edi+0Ch], eax
0x1001c1cd  mov     eax, dword ptr [esp+0D20h+var_CA0]
0x1001c1d4  mov     [edi+28h], eax
0x1001c1d7  xor     eax, eax
0x1001c1d9  mov     [esp+0D20h+Buffer], ax
0x1001c1e1  lea     eax, [esp+0D20h+Buffer]
0x1001c1e8  push    0Ah; Radix
0x1001c1ea  push    eax; Buffer
0x1001c1eb  push    [esp+0D28h+Value]; Value
0x1001c1ef  call    ds:__imp___itow
0x1001c1f5  add     esp, 0Ch
0x1001c1f8  lea     eax, [esp+0D20h+Buffer]
0x1001c1ff  push    eax; psz
0x1001c200  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1001c206  mov     [edi+2Ch], eax
  ... truncated ...
```
