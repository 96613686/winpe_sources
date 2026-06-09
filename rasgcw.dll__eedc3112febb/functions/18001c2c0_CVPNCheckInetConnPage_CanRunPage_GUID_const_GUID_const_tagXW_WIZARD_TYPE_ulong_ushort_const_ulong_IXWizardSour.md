# CVPNCheckInetConnPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001c2c0`
- end: `0x18001c450`
- name: `?CanRunPage@CVPNCheckInetConnPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `400`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001c2c0`
- `0x18001c950`
- `0x18001cc68`
- `0x18002f382`

## import_xrefs

- `connect!IsInternetConnectedGUID` at `0x18001c31b`
- `connect!IsInternetConnectedGUID` at `0x18001c31b`
- `rtutils!TracePrintfExA` at `0x18001c3fb`
- `rtutils!TracePrintfExA` at `0x18001c41a`
- `rtutils!TracePrintfExA` at `0x18001c43e`
- `rtutils!TracePrintfExA` at `0x18001c3fb`
- `rtutils!TracePrintfExA` at `0x18001c41a`
- `rtutils!TracePrintfExA` at `0x18001c43e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c342`

## string_xrefs

- `0x18001c42f`: `HrEnsurePropertyBagAccess failed. hr = %#x`

## pseudocode

```c
__int64 __fastcall CVPNCheckInetConnPage::CanRunPage(
        __int64 a1,
        _OWORD *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  int v11; // ebx
  char *v12; // rax
  char *v13; // rbx
  int v14; // edx
  __int64 (__fastcall *v15)(HWND, unsigned int, unsigned __int64, __int64); // rax

  *a9 = 0;
  *(_OWORD *)(a1 + 64) = *a2;
  *(_QWORD *)(a1 + 80) = a8;
  v11 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 88);
  if ( v11 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrEnsurePropertyBagAccess failed. hr = %#x", (unsigned int)v11);
  }
  else
  {
    CVPNCheckInetConnPage::UpdateRASVPNInternetChkProperty((CVPNCheckInetConnPage *)a1, 0);
    if ( !(unsigned int)IsInternetConnectedGUID(0, 0) )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Skipping VPNCheckInetConnPage page as it is not required");
      return 0;
    }
    CVPNCheckInetConnPage::GetRasInternetEntries((CVPNCheckInetConnPage *)a1);
    if ( (a4 & 0x22) != 0 )
    {
      v12 = (char *)CoTaskMemAlloc(0x68u);
      v13 = v12;
      if ( v12 )
      {
        memset_0(v12 + 8, 0, 0x60u);
        *(_DWORD *)v13 = 104;
        *((_DWORD *)v13 + 1) = 4096;
        *((_QWORD *)v13 + 1) = hInst;
        *((_QWORD *)v13 + 6) = a1;
        v14 = *(_DWORD *)(a1 + 104);
        *((_QWORD *)v13 + 2) = 103LL - (v14 != 0);
        v15 = CVPNCheckInetConnPage::DlgProcDoubleDial;
        *((_QWORD *)v13 + 9) = v14 != 0 ? 3024LL : 3021LL;
        if ( !v14 )
          v15 = CVPNCheckInetConnPage::DlgProcNoInternet;
        *((_QWORD *)v13 + 5) = v15;
        *a9 = v13;
        return 0;
      }
      v11 = -2147024882;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x",
          2147942414LL);
    }
    else
    {
      v11 = -2147467263;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001c2c0  push    rbx
0x18001c2c2  push    rsi
0x18001c2c3  push    rdi
0x18001c2c4  push    r14
0x18001c2c6  sub     rsp, 38h
0x18001c2ca  mov     r14, [rsp+58h+arg_40]
0x18001c2d2  mov     rdi, rcx
0x18001c2d5  mov     esi, r9d
0x18001c2d8  mov     qword ptr [r14], 0
0x18001c2df  lea     r8, [rdi+58h]
0x18001c2e3  movups  xmm0, xmmword ptr [rdx]
0x18001c2e6  lea     rdx, IID_IXWizardPropertyBag
0x18001c2ed  movdqu  xmmword ptr [rcx+40h], xmm0
0x18001c2f2  mov     rcx, [rsp+58h+arg_38]
0x18001c2fa  mov     [rdi+50h], rcx
0x18001c2fe  call    HrEnsureTearOffInterfaceLoaded
0x18001c303  mov     ebx, eax
0x18001c305  test    eax, eax
0x18001c307  js      loc_18001C424
0x18001c30d  xor     edx, edx; void *
0x18001c30f  mov     rcx, rdi; this
0x18001c312  call    ?UpdateRASVPNInternetChkProperty@CVPNCheckInetConnPage@@AEAAXPEAX@Z; CVPNCheckInetConnPage::UpdateRASVPNInternetChkProperty(void *)
0x18001c317  xor     edx, edx
0x18001c319  xor     ecx, ecx
0x18001c31b  call    cs:__imp_IsInternetConnectedGUID
0x18001c321  test    eax, eax
0x18001c323  jz      loc_18001C403
0x18001c329  mov     rcx, rdi; this
0x18001c32c  call    ?GetRasInternetEntries@CVPNCheckInetConnPage@@AEAAHXZ; CVPNCheckInetConnPage::GetRasInternetEntries(void)
0x18001c331  test    sil, 22h
0x18001c335  jz      loc_18001C3D4
0x18001c33b  mov     esi, 68h ; 'h'
0x18001c340  mov     ecx, esi; cb
0x18001c342  call    cs:__imp_CoTaskMemAlloc
0x18001c348  mov     rbx, rax
0x18001c34b  test    rax, rax
0x18001c34e  jz      short loc_18001C3BB
0x18001c350  lea     rcx, [rax+8]; void *
0x18001c354  xor     edx, edx; Val
0x18001c356  lea     r8d, [rsi-8]; Size
0x18001c35a  call    memset_0
0x18001c35f  mov     [rbx], esi
0x18001c361  mov     dword ptr [rbx+4], 1000h
0x18001c368  mov     rcx, cs:hInst
0x18001c36f  mov     [rbx+8], rcx
0x18001c373  mov     [rbx+30h], rdi
0x18001c377  mov     edx, [rdi+68h]
0x18001c37a  mov     ecx, edx
0x18001c37c  neg     ecx
0x18001c37e  sbb     rax, rax
0x18001c381  add     rax, 67h ; 'g'
0x18001c385  mov     [rbx+10h], rax
0x18001c389  mov     eax, edx
0x18001c38b  neg     eax
0x18001c38d  lea     rax, ?DlgProcDoubleDial@CVPNCheckInetConnPage@@CAHPEAUHWND__@@I_K_J@Z; CVPNCheckInetConnPage::DlgProcDoubleDial(HWND__ *,uint,unsigned __int64,__int64)
0x18001c394  sbb     rcx, rcx
0x18001c397  and     ecx, 3
0x18001c39a  add     rcx, 0BCDh
0x18001c3a1  mov     [rbx+48h], rcx
0x18001c3a5  test    edx, edx
0x18001c3a7  lea     rcx, ?DlgProcNoInternet@CVPNCheckInetConnPage@@CAHPEAUHWND__@@I_K_J@Z; CVPNCheckInetConnPage::DlgProcNoInternet(HWND__ *,uint,unsigned __int64,__int64)
0x18001c3ae  cmovz   rax, rcx
0x18001c3b2  mov     [rbx+28h], rax
0x18001c3b6  mov     [r14], rbx
0x18001c3b9  jmp     short loc_18001C420
0x18001c3bb  mov     ecx, cs:g_dwTraceId
0x18001c3c1  mov     ebx, 8007000Eh
0x18001c3c6  cmp     ecx, 0FFFFFFFFh
0x18001c3c9  jz      short loc_18001C444
0x18001c3cb  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001c3d2  jmp     short loc_18001C436
0x18001c3d4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c3da  mov     ebx, 80004001h
0x18001c3df  cmp     ecx, 0FFFFFFFFh
0x18001c3e2  jz      short loc_18001C444
0x18001c3e4  mov     [rsp+58h+var_30], ebx
0x18001c3e8  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001c3ef  mov     r9d, esi
0x18001c3f2  mov     [rsp+58h+var_38], esi
0x18001c3f6  mov     edx, 0Ch; dwFlags
0x18001c3fb  call    cs:__imp_TracePrintfExA
0x18001c401  jmp     short loc_18001C444
0x18001c403  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c409  cmp     ecx, 0FFFFFFFFh
0x18001c40c  jz      short loc_18001C420
0x18001c40e  lea     r8, aSkippingVpnche; "Skipping VPNCheckInetConnPage page as i"...
0x18001c415  mov     edx, 0Ch; dwFlags
0x18001c41a  call    cs:__imp_TracePrintfExA
0x18001c420  xor     ebx, ebx
0x18001c422  jmp     short loc_18001C444
0x18001c424  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c42a  cmp     ecx, 0FFFFFFFFh
0x18001c42d  jz      short loc_18001C444
0x18001c42f  lea     r8, aHrensureproper; "HrEnsurePropertyBagAccess failed. hr = "...
0x18001c436  mov     r9d, ebx
0x18001c439  mov     edx, 0Ch; dwFlags
0x18001c43e  call    cs:__imp_TracePrintfExA
0x18001c444  mov     eax, ebx
0x18001c446  add     rsp, 38h
0x18001c44a  pop     r14
0x18001c44c  pop     rdi
0x18001c44d  pop     rsi
0x18001c44e  pop     rbx
0x18001c44f  retn
```
