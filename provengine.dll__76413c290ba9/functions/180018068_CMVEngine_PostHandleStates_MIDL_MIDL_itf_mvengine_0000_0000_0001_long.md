# CMVEngine::PostHandleStates(__MIDL___MIDL_itf_mvengine_0000_0000_0001 *,long)

- ea: `0x180018068`
- end: `0x180018432`
- name: `?PostHandleStates@CMVEngine@@AEAAXPEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@Z`
- size: `970`
- prototype: `void __fastcall(CMVEngine *__hidden this, enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800119b8`
- `0x180011bb0`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x180013de0`
- `0x180018068`
- `0x18001f95c`
- `0x180033984`
- `0x180033a08`
- `0x180033ac8`
- `0x180041070`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180018320`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180018320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018124`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001810f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001810f`
- `OLEAUT32!__imp_VariantInit` at `0x1800180c7`
- `OLEAUT32!__imp_VariantInit` at `0x1800180d3`
- `OLEAUT32!__imp_VariantInit` at `0x180018109`
- `OLEAUT32!__imp_VariantInit` at `0x1800180c7`
- `OLEAUT32!__imp_VariantInit` at `0x1800180d3`
- `OLEAUT32!__imp_VariantInit` at `0x180018109`
- `OLEAUT32!__imp_VariantClear` at `0x18001811c`
- `OLEAUT32!__imp_VariantClear` at `0x1800183ed`
- `OLEAUT32!__imp_VariantClear` at `0x1800183f9`
- `OLEAUT32!__imp_VariantClear` at `0x18001811c`
- `OLEAUT32!__imp_VariantClear` at `0x1800183ed`
- `OLEAUT32!__imp_VariantClear` at `0x1800183f9`
- `DMCmnUtils!DmWnfPublish` at `0x1800183b4`
- `DMCmnUtils!DmWnfPublish` at `0x1800183b4`
- `DMCmnUtils!DmWnfQuery` at `0x18001835c`
- `DMCmnUtils!DmWnfQuery` at `0x18001835c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
void __fastcall CMVEngine::PostHandleStates(
        CMVEngine *this,
        enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *a2,
        int a3)
{
  int v3; // r14d
  enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *v4; // r15
  CMVEngine *v5; // rsi
  int v6; // ecx
  __int128 v7; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  DWORD LastError; // ebx
  __int64 i; // rbx
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  wil *v14; // rcx
  __int64 j; // rbx
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // ecx
  __int64 v20; // rdx
  int v21; // r10d
  int v22; // eax
  int v23; // [rsp+20h] [rbp-308h]
  int v24; // [rsp+30h] [rbp-2F8h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-2F0h] BYREF
  enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 *v26; // [rsp+50h] [rbp-2D8h]
  CMVEngine *v27; // [rsp+58h] [rbp-2D0h]
  VARIANTARG v28; // [rsp+60h] [rbp-2C8h] BYREF
  __int128 v29; // [rsp+78h] [rbp-2B0h] BYREF
  int v30; // [rsp+88h] [rbp-2A0h]
  _BYTE v31[32]; // [rsp+90h] [rbp-298h] BYREF
  int *v32; // [rsp+B0h] [rbp-278h]
  __int64 v33; // [rsp+B8h] [rbp-270h]
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  if ( a2 )
  {
    v3 = a3;
    v4 = a2;
    v5 = this;
    v27 = this;
    if ( a3 )
    {
      v26 = a2;
      VariantInit(&pvarg);
      VariantInit(&v28);
      if ( (*(int (__fastcall **)(CMVEngine *, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v5 + 56LL))(
             v5,
             L"slotstatus",
             &v28) >= 0 )
      {
        v7 = *(_OWORD *)&v28.vt;
        pRecInfo = v28.pRecInfo;
        VariantInit(&v28);
        LastError = GetLastError();
        VariantClear(&pvarg);
        SetLastError(LastError);
        *(_OWORD *)&pvarg.vt = v7;
        pvarg.pRecInfo = pRecInfo;
      }
      for ( i = 0; (int)i < v3; i = (unsigned int)(i + 1) )
      {
        if ( *((_DWORD *)v4 + i) == 1 )
        {
          v11 = MvSetLanguageProvisioningComplete(v6);
          v6 = dword_18005A000;
          if ( (unsigned int)dword_18005A000 > 5 )
          {
            v24 = v11;
            v32 = &v24;
            v33 = 4;
            tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &dword_18004EEEC, 0, 0, 3, v31);
          }
        }
        if ( !*((_DWORD *)v5 + 34) )
        {
          if ( *((_DWORD *)v4 + i) == 6 )
          {
            if ( *((_DWORD *)v5 + 29) )
            {
              if ( pvarg.vt == 19 && pvarg.lVal == 1 )
              {
                v12 = MvSetOneTimeProvisioningComplete(v6);
                if ( (unsigned int)dword_18005A000 > 5 )
                {
                  v24 = v12;
                  v32 = &v24;
                  v33 = 4;
                  tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004FA02, 0, 0, 3, v31);
                }
              }
            }
          }
          v24 = 0;
          MvIsPrimaryAppProvisioningComplete(&v24);
          if ( !v24 && *((_DWORD *)v4 + i) == 7 )
            CMVEngine::SetPrimaryAppProvisioningCompleteIfApplicable(v5);
        }
      }
      if ( pvarg.vt == 19 && pvarg.lVal )
      {
        try
        {
          v13 = 0;
          SetProvStatus();
        }
        catch ( ... )
        {
          v24 = wil::ResultFromCaughtException(v14);
          v3 = a3;
          v13 = v24;
          v4 = v26;
          v5 = v27;
        }
        if ( (unsigned int)dword_18005A000 > 5 )
        {
          v24 = v13;
          v32 = &v24;
          v33 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004EC02, 0, 0, 3, v31);
        }
      }
      if ( *((_DWORD *)v5 + 34) )
        goto LABEL_43;
      if ( *((_DWORD *)v5 + 28) )
      {
        for ( j = 0; (int)j < v3; j = (unsigned int)(j + 1) )
        {
          if ( (int)GetDeviceUpdateSettingsGroupRegKey(*((unsigned int *)v4 + j), SubKey) >= 0 )
            RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
        }
      }
      v24 = 0;
      v29 = 0;
      v30 = 0;
      v16 = DmWnfQuery(
              (struct _WNF_STATE_NAME)WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS,
              0x14u,
              (unsigned __int8 *)&v29,
              (unsigned int *)&v24);
      if ( v16 >= 0 )
      {
        if ( v24 == 20 && (v19 = v29, (unsigned int)v29 <= 2) )
        {
          v20 = 0;
          if ( (_DWORD)v29 )
          {
            do
            {
              v21 = *((_DWORD *)v5 + *((unsigned int *)&v29 + 2 * v20 + 1) + 4);
              if ( v21 )
              {
                *((_DWORD *)&v29 + 2 * v20 + 2) = v21;
                v19 = v29;
              }
              v20 = (unsigned int)(v20 + 1);
            }
            while ( (unsigned int)v20 < v19 );
          }
          v22 = DmWnfPublish(
                  (struct _WNF_STATE_NAME)WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS,
                  (const unsigned __int8 *)&v29,
                  0x14u);
          if ( v22 >= 0 )
            goto LABEL_43;
          v17 = (unsigned int)v22;
          v18 = 2976;
        }
        else
        {
          v17 = 2147549183LL;
          v18 = 2965;
        }
      }
      else
      {
        v17 = (unsigned int)v16;
        v18 = 2963;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)v17,
        v23);
LABEL_43:
      VariantClear(&v28);
      VariantClear(&pvarg);
    }
  }
}

```

## disassembly

```asm
0x180018068  test    rdx, rdx
0x18001806b  jz      locret_180018431
0x180018071  mov     rax, rsp
0x180018074  mov     [rax+10h], rbx
0x180018078  mov     [rax+18h], r8d
0x18001807c  push    rsi
0x18001807d  push    r12
0x18001807f  push    r13
0x180018081  push    r14
0x180018083  push    r15
0x180018085  sub     rsp, 300h
0x18001808c  movaps  xmmword ptr [rax-38h], xmm6
0x180018090  movaps  xmmword ptr [rax-48h], xmm7
0x180018094  mov     rax, cs:__security_cookie
0x18001809b  xor     rax, rsp
0x18001809e  mov     [rsp+328h+var_58], rax
0x1800180a6  mov     r14d, r8d
0x1800180a9  mov     r15, rdx
0x1800180ac  mov     rsi, rcx
0x1800180af  mov     [rsp+328h+var_2D0], rcx
0x1800180b4  test    r8d, r8d
0x1800180b7  jz      loc_1800183FF
0x1800180bd  mov     [rsp+328h+var_2D8], rdx
0x1800180c2  lea     rcx, [rsp+328h+pvarg]; pvarg
0x1800180c7  call    cs:__imp_VariantInit
0x1800180cd  nop
0x1800180ce  lea     rcx, [rsp+328h+var_2C8]; pvarg
0x1800180d3  call    cs:__imp_VariantInit
0x1800180d9  nop
0x1800180da  mov     rax, [rsi]
0x1800180dd  lea     r8, [rsp+328h+var_2C8]
0x1800180e2  lea     rdx, ?gc_wszSlotStatusContext@@3QBGB; "slotstatus"
0x1800180e9  mov     rcx, rsi
0x1800180ec  mov     rax, [rax+38h]
0x1800180f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180f5  test    eax, eax
0x1800180f7  js      short loc_180018135
0x1800180f9  movups  xmm6, xmmword ptr [rsp+328h+var_2C8]
0x1800180fe  movsd   xmm7, qword ptr [rsp+328h+var_2C8+10h]
0x180018104  lea     rcx, [rsp+328h+var_2C8]; pvarg
0x180018109  call    cs:__imp_VariantInit
0x18001810f  call    cs:__imp_GetLastError
0x180018115  mov     ebx, eax
0x180018117  lea     rcx, [rsp+328h+pvarg]; pvarg
0x18001811c  call    cs:__imp_VariantClear
0x180018122  mov     ecx, ebx; dwErrCode
0x180018124  call    cs:__imp_SetLastError
0x18001812a  movups  xmmword ptr [rsp+328h+pvarg], xmm6
0x18001812f  movsd   qword ptr [rsp+328h+pvarg+10h], xmm7
0x180018135  xor     ebx, ebx
0x180018137  lea     r13d, [rbx+13h]
0x18001813b  test    r14d, r14d
0x18001813e  jle     loc_18001825D
0x180018144  cmp     dword ptr [r15+rbx*4], 1
0x180018149  jnz     short loc_1800181A6
0x18001814b  call    ?MvSetLanguageProvisioningComplete@@YAJH@Z; MvSetLanguageProvisioningComplete(int)
0x180018150  mov     ecx, cs:dword_18005A000
0x180018156  cmp     ecx, 5
0x180018159  jbe     short loc_1800181A6
0x18001815b  mov     [rsp+328h+var_2F8], eax
0x18001815f  lea     rax, [rsp+328h+var_2F8]
0x180018164  mov     [rsp+328h+var_278], rax
0x18001816c  mov     [rsp+328h+var_270], 4
0x180018178  lea     rax, [rsp+328h+var_298]
0x180018180  mov     [rsp+328h+var_300], rax
0x180018185  mov     [rsp+328h+var_308], 3
0x18001818d  xor     r9d, r9d
0x180018190  xor     r8d, r8d
0x180018193  lea     rdx, dword_18004EEEC
0x18001819a  lea     rcx, dword_18005A000
0x1800181a1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800181a6  cmp     dword ptr [rsi+88h], 0
0x1800181ad  jnz     loc_180018252
0x1800181b3  cmp     dword ptr [r15+rbx*4], 6
0x1800181b8  jnz     short loc_18001822A
0x1800181ba  cmp     dword ptr [rsi+74h], 0
0x1800181be  jz      short loc_18001822A
0x1800181c0  cmp     r13w, word ptr [rsp+328h+pvarg]
0x1800181c6  jnz     short loc_18001822A
0x1800181c8  cmp     dword ptr [rsp+328h+pvarg+8], 1
0x1800181cd  jnz     short loc_18001822A
0x1800181cf  call    ?MvSetOneTimeProvisioningComplete@@YAJH@Z; MvSetOneTimeProvisioningComplete(int)
0x1800181d4  mov     ecx, cs:dword_18005A000
0x1800181da  cmp     ecx, 5
0x1800181dd  jbe     short loc_18001822A
0x1800181df  mov     [rsp+328h+var_2F8], eax
0x1800181e3  lea     rax, [rsp+328h+var_2F8]
0x1800181e8  mov     [rsp+328h+var_278], rax
0x1800181f0  mov     [rsp+328h+var_270], 4
0x1800181fc  lea     rax, [rsp+328h+var_298]
0x180018204  mov     [rsp+328h+var_300], rax
0x180018209  mov     [rsp+328h+var_308], 3
0x180018211  xor     r9d, r9d
0x180018214  xor     r8d, r8d
0x180018217  lea     rdx, word_18004FA02
0x18001821e  lea     rcx, dword_18005A000
0x180018225  call    _tlgWriteTransfer_EventWriteTransfer
0x18001822a  mov     [rsp+328h+var_2F8], 0
0x180018232  lea     rcx, [rsp+328h+var_2F8]; int *
0x180018237  call    ?MvIsPrimaryAppProvisioningComplete@@YAJPEAH@Z; MvIsPrimaryAppProvisioningComplete(int *)
0x18001823c  cmp     [rsp+328h+var_2F8], 0
0x180018241  jnz     short loc_180018252
0x180018243  cmp     dword ptr [r15+rbx*4], 7
0x180018248  jnz     short loc_180018252
0x18001824a  mov     rcx, rsi; this
0x18001824d  call    ?SetPrimaryAppProvisioningCompleteIfApplicable@CMVEngine@@AEAAJXZ; CMVEngine::SetPrimaryAppProvisioningCompleteIfApplicable(void)
0x180018252  inc     ebx
0x180018254  cmp     ebx, r14d
0x180018257  jl      loc_180018144
0x18001825d  cmp     r13w, word ptr [rsp+328h+pvarg]
0x180018263  jnz     short loc_1800182E2
0x180018265  cmp     dword ptr [rsp+328h+pvarg+8], 0
0x18001826a  jz      short loc_1800182E2
0x18001826c  xor     ebx, ebx
0x18001826e  call    ?SetProvStatus@@YAXW4ProvStatus@@@Z; SetProvStatus(ProvStatus)
0x180018273  nop
0x180018274  jmp     short loc_18001828C
0x180018276  mov     r14d, [rsp+328h+arg_10]
0x18001827e  mov     ebx, [rsp+328h+var_2F8]
0x180018282  mov     r15, [rsp+328h+var_2D8]
0x180018287  mov     rsi, [rsp+328h+var_2D0]
0x18001828c  mov     eax, cs:dword_18005A000
0x180018292  cmp     eax, 5
0x180018295  jbe     short loc_1800182E2
0x180018297  mov     [rsp+328h+var_2F8], ebx
0x18001829b  lea     rax, [rsp+328h+var_2F8]
0x1800182a0  mov     [rsp+328h+var_278], rax
0x1800182a8  mov     [rsp+328h+var_270], 4
0x1800182b4  lea     rax, [rsp+328h+var_298]
0x1800182bc  mov     [rsp+328h+var_300], rax
0x1800182c1  mov     [rsp+328h+var_308], 3; int
0x1800182c9  xor     r9d, r9d
0x1800182cc  xor     r8d, r8d
0x1800182cf  lea     rdx, word_18004EC02
0x1800182d6  lea     rcx, dword_18005A000
0x1800182dd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800182e2  cmp     dword ptr [rsi+88h], 0
0x1800182e9  jnz     loc_1800183E8
0x1800182ef  cmp     dword ptr [rsi+70h], 0
0x1800182f3  jz      short loc_18001832D
0x1800182f5  xor     ebx, ebx
0x1800182f7  test    r14d, r14d
0x1800182fa  jle     short loc_18001832D
0x1800182fc  lea     rdx, [rsp+328h+SubKey]
0x180018304  mov     ecx, [r15+rbx*4]
0x180018308  call    ?GetDeviceUpdateSettingsGroupRegKey@@YAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAGK@Z; GetDeviceUpdateSettingsGroupRegKey(__MIDL___MIDL_itf_mvengine_0000_0000_0001,ushort *,ulong)
0x18001830d  test    eax, eax
0x18001830f  js      short loc_180018326
0x180018311  lea     rdx, [rsp+328h+SubKey]; lpSubKey
0x180018319  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018320  call    cs:__imp_RegDeleteTreeW
0x180018326  inc     ebx
0x180018328  cmp     ebx, r14d
0x18001832b  jl      short loc_1800182FC
0x18001832d  mov     [rsp+328h+var_2F8], 0
0x180018335  xorps   xmm0, xmm0
0x180018338  xor     eax, eax
0x18001833a  movups  [rsp+328h+var_2B0], xmm0
0x18001833f  mov     [rsp+328h+var_2A0], eax
0x180018346  lea     r9, [rsp+328h+var_2F8]
0x18001834b  lea     r8, [rsp+328h+var_2B0]
0x180018350  lea     ebx, [rax+14h]
0x180018353  mov     edx, ebx
0x180018355  mov     rcx, cs:WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS
0x18001835c  call    cs:__imp_?DmWnfQuery@@YAJU_WNF_STATE_NAME@@KPEAEPEAK@Z; DmWnfQuery(_WNF_STATE_NAME,ulong,uchar *,ulong *)
0x180018362  test    eax, eax
0x180018364  jns     short loc_180018370
0x180018366  mov     r9d, eax
0x180018369  mov     edx, 0B93h
0x18001836e  jmp     short loc_1800183D3
0x180018370  cmp     [rsp+328h+var_2F8], ebx
0x180018374  jnz     short loc_1800183C8
0x180018376  mov     ecx, dword ptr [rsp+328h+var_2B0]
0x18001837a  cmp     ecx, 2
0x18001837d  ja      short loc_1800183C8
0x18001837f  xor     edx, edx
0x180018381  test    ecx, ecx
0x180018383  jz      short loc_1800183A5
0x180018385  mov     eax, dword ptr [rsp+rdx*8+328h+var_2B0+4]
0x180018389  mov     r10d, [rsi+rax*4+10h]
0x18001838e  test    r10d, r10d
0x180018391  jz      short loc_18001839F
0x180018393  mov     dword ptr [rsp+rdx*8+328h+var_2B0+8], r10d
0x18001839b  mov     ecx, dword ptr [rsp+328h+var_2B0]
0x18001839f  inc     edx
0x1800183a1  cmp     edx, ecx
0x1800183a3  jb      short loc_180018385
0x1800183a5  mov     r8d, ebx
0x1800183a8  lea     rdx, [rsp+328h+var_2B0]
0x1800183ad  mov     rcx, cs:WNF_DEVM_MULTIVARIANT_PROVISIONING_SESSIONS
0x1800183b4  call    cs:__imp_?DmWnfPublish@@YAJU_WNF_STATE_NAME@@PEBEK@Z; DmWnfPublish(_WNF_STATE_NAME,uchar const *,ulong)
0x1800183ba  test    eax, eax
0x1800183bc  jns     short loc_1800183E8
0x1800183be  mov     r9d, eax
0x1800183c1  mov     edx, 0BA0h
0x1800183c6  jmp     short loc_1800183D3
0x1800183c8  mov     r9d, 8000FFFFh; char *
0x1800183ce  mov     edx, 0B95h; void *
0x1800183d3  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800183da  mov     rcx, [rsp+328h]; this
0x1800183e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800183e7  nop
0x1800183e8  lea     rcx, [rsp+328h+var_2C8]; pvarg
0x1800183ed  call    cs:__imp_VariantClear
0x1800183f3  nop
0x1800183f4  lea     rcx, [rsp+328h+pvarg]; pvarg
0x1800183f9  call    cs:__imp_VariantClear
0x1800183ff  mov     rcx, [rsp+328h+var_58]
0x180018407  xor     rcx, rsp; StackCookie
0x18001840a  call    __security_check_cookie
0x18001840f  lea     r11, [rsp+328h+var_28]
0x180018417  mov     rbx, [r11+38h]
0x18001841b  movaps  xmm6, xmmword ptr [r11-10h]
0x180018420  movaps  xmm7, xmmword ptr [r11-20h]
0x180018425  mov     rsp, r11
0x180018428  pop     r15
0x18001842a  pop     r14
0x18001842c  pop     r13
0x18001842e  pop     r12
0x180018430  pop     rsi
0x180018431  retn
```
