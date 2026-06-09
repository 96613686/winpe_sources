# CClipBase::GetClipboardDataWorker(tagSTGMEDIUM *,uint)

- ea: `0x14005039c`
- end: `0x14005068c`
- name: `?GetClipboardDataWorker@CClipBase@@AEAAJPEAUtagSTGMEDIUM@@I@Z`
- size: `752`
- prototype: `__int64 __fastcall(CClipBase *__hidden this, struct tagSTGMEDIUM *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140053860`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x1400081d0`
- `0x140011054`
- `0x14005039c`
- `0x1400595f4`
- `0x14006032c`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140050508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005051f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140050536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005054d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140050508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005051f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140050536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005054d`
- `api-ms-win-rtcore-ole32-clipboard-l1-1-0!OleGetClipboard` at `0x140050434`
- `api-ms-win-rtcore-ole32-clipboard-l1-1-0!OleGetClipboard` at `0x140050434`

## pseudocode

```c
__int64 __fastcall CClipBase::GetClipboardDataWorker(CClipBase *this, struct tagSTGMEDIUM *a2, int a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  HRESULT Clipboard; // ebx
  RdpEdpPolicyManager *v9; // rcx
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  int v13; // eax
  unsigned __int16 **v15; // [rsp+28h] [rbp-48h]
  unsigned __int16 *v16; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v18; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+48h] [rbp-28h] BYREF
  __int128 v20; // [rsp+58h] [rbp-18h]
  LPDATAOBJECT ppDataObj; // [rsp+98h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+38h] BYREF

  ppDataObj = 0;
  v19 = 0;
  v20 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 119;
    v7 = "pStgMedium";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v7);
LABEL_7:
    Clipboard = -2147467261;
    goto LABEL_46;
  }
  v9 = (RdpEdpPolicyManager *)*((_QWORD *)this + 102);
  if ( !v9 )
  {
    Clipboard = OleGetClipboard(&ppDataObj);
    if ( Clipboard == -2147467263 )
      Clipboard = OleGetClipboardWithFallbackInternal(&ppDataObj);
    if ( Clipboard < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 120;
        v12 = "OleGetClipboard failed!";
LABEL_16:
        LODWORD(v15) = Clipboard;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v10,
          (__int64)v12,
          v15,
          v16,
          v17,
          v18,
          v19,
          v20);
        goto LABEL_46;
      }
      goto LABEL_46;
    }
LABEL_30:
    if ( !ppDataObj )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 122;
      v7 = "spDataObject";
      goto LABEL_6;
    }
    LOWORD(v19) = a3;
    v13 = 1;
    *(_QWORD *)&v20 = 0xFFFFFFFF00000001uLL;
    *((_QWORD *)&v19 + 1) = 0;
    if ( a3 == 3 )
    {
      DWORD2(v20) = 32;
    }
    else
    {
      if ( a3 == 9 )
        v13 = 16;
      DWORD2(v20) = v13;
    }
    Clipboard = ((__int64 (__fastcall *)(LPDATAOBJECT, __int128 *, struct tagSTGMEDIUM *))ppDataObj->lpVtbl->GetData)(
                  ppDataObj,
                  &v19,
                  a2);
    if ( Clipboard >= 0 )
    {
      Clipboard = 0;
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 124;
      v12 = "GetData failed!";
      goto LABEL_16;
    }
    goto LABEL_46;
  }
  pv = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  Clipboard = RdpEdpPolicyManager::GetClipboardWithEnterpriseInfo(
                v9,
                &ppDataObj,
                (unsigned __int16 **)&pv,
                &v16,
                &v17,
                &v18);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v16 )
  {
    CoTaskMemFree(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    CoTaskMemFree(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    CoTaskMemFree(v18);
    v18 = 0;
  }
  if ( Clipboard >= 0 )
    goto LABEL_30;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 121;
    v12 = "GetClipboardWithEnterpriseInfo failed.";
    goto LABEL_16;
  }
LABEL_46:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&ppDataObj);
  return (unsigned int)Clipboard;
}

```

## disassembly

```asm
0x14005039c  mov     [rsp-18h+arg_0], rbx
0x1400503a1  push    rbp
0x1400503a2  push    rsi
0x1400503a3  push    rdi
0x1400503a4  mov     rbp, rsp
0x1400503a7  sub     rsp, 70h
0x1400503ab  mov     [rbp+ppDataObj], 0
0x1400503b3  xorps   xmm0, xmm0
0x1400503b6  mov     edi, r8d
0x1400503b9  mov     rsi, rdx
0x1400503bc  movups  [rbp+var_28], xmm0
0x1400503c0  movups  [rbp+var_18], xmm0
0x1400503c4  test    rdx, rdx
0x1400503c7  jnz     short loc_140050420
0x1400503c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400503d0  lea     rax, WPP_GLOBAL_Control
0x1400503d7  cmp     rcx, rax
0x1400503da  jz      short loc_140050416
0x1400503dc  test    byte ptr [rcx+1Ch], 8
0x1400503e0  jz      short loc_140050416
0x1400503e2  cmp     byte ptr [rcx+19h], 2
0x1400503e6  jb      short loc_140050416
0x1400503e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400503ed  lea     edx, [rsi+77h]
0x1400503f0  lea     rcx, aPstgmedium; "pStgMedium"
0x1400503f7  mov     [rsp+70h+var_50], rcx
0x1400503fc  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140050403  mov     rcx, cs:WPP_GLOBAL_Control
0x14005040a  mov     r9d, eax
0x14005040d  mov     rcx, [rcx+10h]
0x140050411  call    WPP_SF_Ds
0x140050416  mov     ebx, 80004003h
0x14005041b  jmp     loc_140050671
0x140050420  mov     rcx, [rcx+330h]; this
0x140050427  test    rcx, rcx
0x14005042a  jnz     loc_1400504BA
0x140050430  lea     rcx, [rbp+ppDataObj]; ppDataObj
0x140050434  call    cs:__imp_OleGetClipboard
0x14005043a  mov     ebx, eax
0x14005043c  cmp     eax, 80004001h
0x140050441  jnz     short loc_14005044E
0x140050443  lea     rcx, [rbp+ppDataObj]
0x140050447  call    OleGetClipboardWithFallbackInternal
0x14005044c  mov     ebx, eax
0x14005044e  test    ebx, ebx
0x140050450  jns     loc_1400505A0
0x140050456  mov     rcx, cs:WPP_GLOBAL_Control
0x14005045d  lea     rax, WPP_GLOBAL_Control
0x140050464  cmp     rcx, rax
0x140050467  jz      loc_140050671
0x14005046d  test    byte ptr [rcx+1Ch], 8
0x140050471  jz      loc_140050671
0x140050477  cmp     byte ptr [rcx+19h], 2
0x14005047b  jb      loc_140050671
0x140050481  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140050486  mov     edx, 78h ; 'x'
0x14005048b  lea     rcx, aOlegetclipboar_1; "OleGetClipboard failed!"
0x140050492  mov     dword ptr [rsp+70h+var_48], ebx
0x140050496  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14005049d  mov     [rsp+70h+var_50], rcx
0x1400504a2  mov     r9d, eax
0x1400504a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400504ac  mov     rcx, [rcx+10h]
0x1400504b0  call    WPP_SF_DsD
0x1400504b5  jmp     loc_140050671
0x1400504ba  lea     rax, [rbp+var_30]
0x1400504be  mov     [rbp+pv], 0
0x1400504c6  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x1400504cb  lea     r9, [rbp+var_40]; unsigned __int16 **
0x1400504cf  lea     rax, [rbp+var_38]
0x1400504d3  mov     [rbp+var_40], 0
0x1400504db  lea     r8, [rbp+pv]; unsigned __int16 **
0x1400504df  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x1400504e4  lea     rdx, [rbp+ppDataObj]; struct IDataObject **
0x1400504e8  mov     [rbp+var_38], 0
0x1400504f0  mov     [rbp+var_30], 0
0x1400504f8  call    ?GetClipboardWithEnterpriseInfo@RdpEdpPolicyManager@@QEAAJPEAPEAUIDataObject@@PEAPEAG111@Z; RdpEdpPolicyManager::GetClipboardWithEnterpriseInfo(IDataObject * *,ushort * *,ushort * *,ushort * *,ushort * *)
0x1400504fd  mov     rcx, [rbp+pv]; pv
0x140050501  mov     ebx, eax
0x140050503  test    rcx, rcx
0x140050506  jz      short loc_140050516
0x140050508  call    cs:__imp_CoTaskMemFree
0x14005050e  mov     [rbp+pv], 0
0x140050516  mov     rcx, [rbp+var_40]; pv
0x14005051a  test    rcx, rcx
0x14005051d  jz      short loc_14005052D
0x14005051f  call    cs:__imp_CoTaskMemFree
0x140050525  mov     [rbp+var_40], 0
0x14005052d  mov     rcx, [rbp+var_38]; pv
0x140050531  test    rcx, rcx
0x140050534  jz      short loc_140050544
0x140050536  call    cs:__imp_CoTaskMemFree
0x14005053c  mov     [rbp+var_38], 0
0x140050544  mov     rcx, [rbp+var_30]; pv
0x140050548  test    rcx, rcx
0x14005054b  jz      short loc_14005055B
0x14005054d  call    cs:__imp_CoTaskMemFree
0x140050553  mov     [rbp+var_30], 0
0x14005055b  test    ebx, ebx
0x14005055d  jns     short loc_1400505A0
0x14005055f  mov     rcx, cs:WPP_GLOBAL_Control
0x140050566  lea     rax, WPP_GLOBAL_Control
0x14005056d  cmp     rcx, rax
0x140050570  jz      loc_140050671
0x140050576  test    byte ptr [rcx+1Ch], 8
0x14005057a  jz      loc_140050671
0x140050580  cmp     byte ptr [rcx+19h], 2
0x140050584  jb      loc_140050671
0x14005058a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005058f  mov     edx, 79h ; 'y'
0x140050594  lea     rcx, aGetclipboardwi_0; "GetClipboardWithEnterpriseInfo failed."
0x14005059b  jmp     loc_140050492
0x1400505a0  mov     rcx, [rbp+ppDataObj]
0x1400505a4  test    rcx, rcx
0x1400505a7  jnz     short loc_1400505EA
0x1400505a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400505b0  lea     rax, WPP_GLOBAL_Control
0x1400505b7  cmp     rcx, rax
0x1400505ba  jz      loc_140050416
0x1400505c0  test    byte ptr [rcx+1Ch], 8
0x1400505c4  jz      loc_140050416
0x1400505ca  cmp     byte ptr [rcx+19h], 2
0x1400505ce  jb      loc_140050416
0x1400505d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400505d9  mov     edx, 7Ah ; 'z'
0x1400505de  lea     rcx, aSpdataobject; "spDataObject"
0x1400505e5  jmp     loc_1400503F7
0x1400505ea  mov     word ptr [rbp+var_28], di
0x1400505ee  mov     eax, 1
0x1400505f3  mov     dword ptr [rbp+var_18], eax
0x1400505f6  mov     qword ptr [rbp+var_28+8], 0
0x1400505fe  mov     dword ptr [rbp+var_18+4], 0FFFFFFFFh
0x140050605  cmp     edi, 3
0x140050608  jnz     short loc_140050613
0x14005060a  mov     dword ptr [rbp+var_18+8], 20h ; ' '
0x140050611  jmp     short loc_140050621
0x140050613  cmp     edi, 9
0x140050616  mov     edx, 10h
0x14005061b  cmovz   eax, edx
0x14005061e  mov     dword ptr [rbp+var_18+8], eax
0x140050621  mov     rax, [rcx]
0x140050624  lea     rdx, [rbp+var_28]
0x140050628  mov     r8, rsi
0x14005062b  mov     rax, [rax+18h]
0x14005062f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050634  mov     ebx, eax
0x140050636  test    eax, eax
0x140050638  jns     short loc_14005066F
0x14005063a  mov     rcx, cs:WPP_GLOBAL_Control
0x140050641  lea     rax, WPP_GLOBAL_Control
0x140050648  cmp     rcx, rax
0x14005064b  jz      short loc_140050671
0x14005064d  test    byte ptr [rcx+1Ch], 8
0x140050651  jz      short loc_140050671
0x140050653  cmp     byte ptr [rcx+19h], 2
0x140050657  jb      short loc_140050671
0x140050659  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005065e  mov     edx, 7Ch ; '|'
0x140050663  lea     rcx, aGetdataFailed; "GetData failed!"
0x14005066a  jmp     loc_140050492
0x14005066f  xor     ebx, ebx
0x140050671  lea     rcx, [rbp+ppDataObj]
0x140050675  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14005067a  mov     eax, ebx
0x14005067c  mov     rbx, [rsp+70h+arg_0]
0x140050684  add     rsp, 70h
0x140050688  pop     rdi
0x140050689  pop     rsi
0x14005068a  pop     rbp
0x14005068b  retn
```
