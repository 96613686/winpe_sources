# CClipBase::GetClipboardDataWorker(tagSTGMEDIUM *,uint)

- ea: `0x1800cf26c`
- end: `0x1800cf55c`
- name: `?GetClipboardDataWorker@CClipBase@@AEAAJPEAUtagSTGMEDIUM@@I@Z`
- size: `752`
- prototype: `__int64 __fastcall(CClipBase *this, struct tagSTGMEDIUM *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d2560`

## callees

- `0x1800071c0`
- `0x1800091a8`
- `0x18002e600`
- `0x1800598d0`
- `0x1800cf26c`
- `0x1800d82c4`
- `0x1800d8ab0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf3d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf3ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf406`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf41d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf3d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf3ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf406`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf41d`
- `OLE32!OleGetClipboard` at `0x1800cf304`
- `OLE32!OleGetClipboard` at `0x1800cf304`

## pseudocode

```c
__int64 __fastcall CClipBase::GetClipboardDataWorker(CClipBase *this, struct tagSTGMEDIUM *a2, __int64 a3)
{
  int v3; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  HRESULT Clipboard; // ebx
  RdpEdpPolicyManager *v9; // rcx
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  int v13; // eax
  unsigned __int16 *v15; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v16; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-30h] BYREF
  __int128 v18; // [rsp+48h] [rbp-28h] BYREF
  __int128 v19; // [rsp+58h] [rbp-18h]
  LPDATAOBJECT ppDataObj; // [rsp+98h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+38h] BYREF

  ppDataObj = 0;
  v3 = a3;
  v18 = 0;
  v19 = 0;
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
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v10,
          (__int64)v12,
          Clipboard);
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
    LOWORD(v18) = v3;
    v13 = 1;
    *(_QWORD *)&v19 = 0xFFFFFFFF00000001uLL;
    *((_QWORD *)&v18 + 1) = 0;
    if ( v3 == 3 )
    {
      DWORD2(v19) = 32;
    }
    else
    {
      if ( v3 == 9 )
        v13 = 16;
      DWORD2(v19) = v13;
    }
    Clipboard = ((__int64 (__fastcall *)(LPDATAOBJECT, __int128 *, struct tagSTGMEDIUM *))ppDataObj->lpVtbl->GetData)(
                  ppDataObj,
                  &v18,
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
  v15 = 0;
  v16 = 0;
  v17 = 0;
  Clipboard = RdpEdpPolicyManager::GetClipboardWithEnterpriseInfo(
                v9,
                &ppDataObj,
                (unsigned __int16 **)&pv,
                &v15,
                &v16,
                &v17);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
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
  TCntPtr<IRdpSQMLogger>::SafeRelease(&ppDataObj, a2, a3);
  return (unsigned int)Clipboard;
}

```

## disassembly

```asm
0x1800cf26c  mov     [rsp-18h+arg_0], rbx
0x1800cf271  push    rbp
0x1800cf272  push    rsi
0x1800cf273  push    rdi
0x1800cf274  mov     rbp, rsp
0x1800cf277  sub     rsp, 70h
0x1800cf27b  mov     [rbp+ppDataObj], 0
0x1800cf283  xorps   xmm0, xmm0
0x1800cf286  mov     edi, r8d
0x1800cf289  mov     rsi, rdx
0x1800cf28c  movups  [rbp+var_28], xmm0
0x1800cf290  movups  [rbp+var_18], xmm0
0x1800cf294  test    rdx, rdx
0x1800cf297  jnz     short loc_1800CF2F0
0x1800cf299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf2a0  lea     rax, WPP_GLOBAL_Control
0x1800cf2a7  cmp     rcx, rax
0x1800cf2aa  jz      short loc_1800CF2E6
0x1800cf2ac  test    byte ptr [rcx+1Ch], 8
0x1800cf2b0  jz      short loc_1800CF2E6
0x1800cf2b2  cmp     byte ptr [rcx+19h], 2
0x1800cf2b6  jb      short loc_1800CF2E6
0x1800cf2b8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cf2bd  lea     edx, [rsi+77h]
0x1800cf2c0  lea     rcx, aPstgmedium; "pStgMedium"
0x1800cf2c7  mov     [rsp+70h+var_50], rcx
0x1800cf2cc  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800cf2d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf2da  mov     r9d, eax
0x1800cf2dd  mov     rcx, [rcx+10h]
0x1800cf2e1  call    WPP_SF_Ds
0x1800cf2e6  mov     ebx, 80004003h
0x1800cf2eb  jmp     loc_1800CF541
0x1800cf2f0  mov     rcx, [rcx+330h]; this
0x1800cf2f7  test    rcx, rcx
0x1800cf2fa  jnz     loc_1800CF38A
0x1800cf300  lea     rcx, [rbp+ppDataObj]; ppDataObj
0x1800cf304  call    cs:__imp_OleGetClipboard
0x1800cf30a  mov     ebx, eax
0x1800cf30c  cmp     eax, 80004001h
0x1800cf311  jnz     short loc_1800CF31E
0x1800cf313  lea     rcx, [rbp+ppDataObj]
0x1800cf317  call    OleGetClipboardWithFallbackInternal
0x1800cf31c  mov     ebx, eax
0x1800cf31e  test    ebx, ebx
0x1800cf320  jns     loc_1800CF470
0x1800cf326  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf32d  lea     rax, WPP_GLOBAL_Control
0x1800cf334  cmp     rcx, rax
0x1800cf337  jz      loc_1800CF541
0x1800cf33d  test    byte ptr [rcx+1Ch], 8
0x1800cf341  jz      loc_1800CF541
0x1800cf347  cmp     byte ptr [rcx+19h], 2
0x1800cf34b  jb      loc_1800CF541
0x1800cf351  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cf356  mov     edx, 78h ; 'x'
0x1800cf35b  lea     rcx, aOlegetclipboar_1; "OleGetClipboard failed!"
0x1800cf362  mov     dword ptr [rsp+70h+var_48], ebx
0x1800cf366  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800cf36d  mov     [rsp+70h+var_50], rcx
0x1800cf372  mov     r9d, eax
0x1800cf375  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf37c  mov     rcx, [rcx+10h]
0x1800cf380  call    WPP_SF_DsD
0x1800cf385  jmp     loc_1800CF541
0x1800cf38a  lea     rax, [rbp+var_30]
0x1800cf38e  mov     [rbp+pv], 0
0x1800cf396  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x1800cf39b  lea     r9, [rbp+var_40]; unsigned __int16 **
0x1800cf39f  lea     rax, [rbp+var_38]
0x1800cf3a3  mov     [rbp+var_40], 0
0x1800cf3ab  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800cf3af  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x1800cf3b4  lea     rdx, [rbp+ppDataObj]; struct IDataObject **
0x1800cf3b8  mov     [rbp+var_38], 0
0x1800cf3c0  mov     [rbp+var_30], 0
0x1800cf3c8  call    ?GetClipboardWithEnterpriseInfo@RdpEdpPolicyManager@@QEAAJPEAPEAUIDataObject@@PEAPEAG111@Z; RdpEdpPolicyManager::GetClipboardWithEnterpriseInfo(IDataObject * *,ushort * *,ushort * *,ushort * *,ushort * *)
0x1800cf3cd  mov     rcx, [rbp+pv]; pv
0x1800cf3d1  mov     ebx, eax
0x1800cf3d3  test    rcx, rcx
0x1800cf3d6  jz      short loc_1800CF3E6
0x1800cf3d8  call    cs:__imp_CoTaskMemFree
0x1800cf3de  mov     [rbp+pv], 0
0x1800cf3e6  mov     rcx, [rbp+var_40]; pv
0x1800cf3ea  test    rcx, rcx
0x1800cf3ed  jz      short loc_1800CF3FD
0x1800cf3ef  call    cs:__imp_CoTaskMemFree
0x1800cf3f5  mov     [rbp+var_40], 0
0x1800cf3fd  mov     rcx, [rbp+var_38]; pv
0x1800cf401  test    rcx, rcx
0x1800cf404  jz      short loc_1800CF414
0x1800cf406  call    cs:__imp_CoTaskMemFree
0x1800cf40c  mov     [rbp+var_38], 0
0x1800cf414  mov     rcx, [rbp+var_30]; pv
0x1800cf418  test    rcx, rcx
0x1800cf41b  jz      short loc_1800CF42B
0x1800cf41d  call    cs:__imp_CoTaskMemFree
0x1800cf423  mov     [rbp+var_30], 0
0x1800cf42b  test    ebx, ebx
0x1800cf42d  jns     short loc_1800CF470
0x1800cf42f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf436  lea     rax, WPP_GLOBAL_Control
0x1800cf43d  cmp     rcx, rax
0x1800cf440  jz      loc_1800CF541
0x1800cf446  test    byte ptr [rcx+1Ch], 8
0x1800cf44a  jz      loc_1800CF541
0x1800cf450  cmp     byte ptr [rcx+19h], 2
0x1800cf454  jb      loc_1800CF541
0x1800cf45a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cf45f  mov     edx, 79h ; 'y'
0x1800cf464  lea     rcx, aGetclipboardwi_0; "GetClipboardWithEnterpriseInfo failed."
0x1800cf46b  jmp     loc_1800CF362
0x1800cf470  mov     rcx, [rbp+ppDataObj]
0x1800cf474  test    rcx, rcx
0x1800cf477  jnz     short loc_1800CF4BA
0x1800cf479  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf480  lea     rax, WPP_GLOBAL_Control
0x1800cf487  cmp     rcx, rax
0x1800cf48a  jz      loc_1800CF2E6
0x1800cf490  test    byte ptr [rcx+1Ch], 8
0x1800cf494  jz      loc_1800CF2E6
0x1800cf49a  cmp     byte ptr [rcx+19h], 2
0x1800cf49e  jb      loc_1800CF2E6
0x1800cf4a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cf4a9  mov     edx, 7Ah ; 'z'
0x1800cf4ae  lea     rcx, aSpdataobject; "spDataObject"
0x1800cf4b5  jmp     loc_1800CF2C7
0x1800cf4ba  mov     word ptr [rbp+var_28], di
0x1800cf4be  mov     eax, 1
0x1800cf4c3  mov     dword ptr [rbp+var_18], eax
0x1800cf4c6  mov     qword ptr [rbp+var_28+8], 0
0x1800cf4ce  mov     dword ptr [rbp+var_18+4], 0FFFFFFFFh
0x1800cf4d5  cmp     edi, 3
0x1800cf4d8  jnz     short loc_1800CF4E3
0x1800cf4da  mov     dword ptr [rbp+var_18+8], 20h ; ' '
0x1800cf4e1  jmp     short loc_1800CF4F1
0x1800cf4e3  cmp     edi, 9
0x1800cf4e6  mov     edx, 10h
0x1800cf4eb  cmovz   eax, edx
0x1800cf4ee  mov     dword ptr [rbp+var_18+8], eax
0x1800cf4f1  mov     rax, [rcx]
0x1800cf4f4  lea     rdx, [rbp+var_28]
0x1800cf4f8  mov     r8, rsi
0x1800cf4fb  mov     rax, [rax+18h]
0x1800cf4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf504  mov     ebx, eax
0x1800cf506  test    eax, eax
0x1800cf508  jns     short loc_1800CF53F
0x1800cf50a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf511  lea     rax, WPP_GLOBAL_Control
0x1800cf518  cmp     rcx, rax
0x1800cf51b  jz      short loc_1800CF541
0x1800cf51d  test    byte ptr [rcx+1Ch], 8
0x1800cf521  jz      short loc_1800CF541
0x1800cf523  cmp     byte ptr [rcx+19h], 2
0x1800cf527  jb      short loc_1800CF541
0x1800cf529  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cf52e  mov     edx, 7Ch ; '|'
0x1800cf533  lea     rcx, aGetdataFailed; "GetData failed!"
0x1800cf53a  jmp     loc_1800CF362
0x1800cf53f  xor     ebx, ebx
0x1800cf541  lea     rcx, [rbp+ppDataObj]
0x1800cf545  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800cf54a  mov     eax, ebx
0x1800cf54c  mov     rbx, [rsp+70h+arg_0]
0x1800cf554  add     rsp, 70h
0x1800cf558  pop     rdi
0x1800cf559  pop     rsi
0x1800cf55a  pop     rbp
0x1800cf55b  retn
```
