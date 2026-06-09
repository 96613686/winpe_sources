# CIncomingConnectionSummaryPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001cd30`
- end: `0x18001ce97`
- name: `?CanRunPage@CIncomingConnectionSummaryPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `359`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001cd30`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001ce56`
- `rtutils!TracePrintfExA` at `0x18001ce85`
- `rtutils!TracePrintfExA` at `0x18001ce56`
- `rtutils!TracePrintfExA` at `0x18001ce85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cdcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cdcd`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSummaryPage::CanRunPage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  _QWORD *v9; // r14
  __int64 v12; // rcx
  __int64 v13; // rax
  char *v14; // rax
  char *v15; // rbx
  int v16; // edx
  unsigned int v17; // ebx

  v9 = a9;
  *a9 = 0;
  *(_QWORD *)(a1 + 64) = a8;
  if ( (int)HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 72) >= 0 )
  {
    v12 = *(_QWORD *)(a1 + 72);
    a9 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, GUID *, const wchar_t *, _QWORD **, _QWORD))(*(_QWORD *)v12 + 48LL))(
            v12,
            &CLSID_IncomingConnectionCheckDevsPage,
            L"ICCDevicesPresent",
            &a9,
            0);
    if ( !(_DWORD)v13 )
      *(_DWORD *)(a1 + 80) = a9 != (_QWORD *)v13;
  }
  if ( (a4 & 0x22) != 0 )
  {
    v14 = (char *)CoTaskMemAlloc(0x68u);
    v15 = v14;
    if ( v14 )
    {
      memset_0(v14 + 8, 0, 0x60u);
      *(_DWORD *)v15 = 104;
      *((_DWORD *)v15 + 1) = 4096;
      *((_QWORD *)v15 + 1) = hInst;
      *((_QWORD *)v15 + 6) = a1;
      v16 = *(_DWORD *)(a1 + 80);
      *((_QWORD *)v15 + 2) = 136LL - (v16 != 0);
      *((_QWORD *)v15 + 9) = 3063LL - (v16 != 0);
      *((_QWORD *)v15 + 5) = CIncomingConnectionSummaryPage::PageDlgProc;
      *v9 = v15;
      return 0;
    }
    else
    {
      v17 = -2147024882;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x",
          -2147024882);
    }
  }
  else
  {
    v17 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v17;
}

```

## disassembly

```asm
0x18001cd30  push    rbx
0x18001cd32  push    rsi
0x18001cd33  push    rdi
0x18001cd34  push    r14
0x18001cd36  sub     rsp, 38h
0x18001cd3a  mov     r14, [rsp+58h+arg_40]
0x18001cd42  lea     rdx, IID_IXWizardPropertyBag
0x18001cd49  mov     rsi, rcx
0x18001cd4c  mov     edi, r9d
0x18001cd4f  mov     rcx, [rsp+58h+arg_38]
0x18001cd57  mov     qword ptr [r14], 0
0x18001cd5e  lea     r8, [rsi+48h]
0x18001cd62  mov     [rsi+40h], rcx
0x18001cd66  call    HrEnsureTearOffInterfaceLoaded
0x18001cd6b  test    eax, eax
0x18001cd6d  js      short loc_18001CDBC
0x18001cd6f  mov     rcx, [rsi+48h]
0x18001cd73  lea     r9, [rsp+58h+arg_40]
0x18001cd7b  mov     [rsp+58h+arg_40], 0
0x18001cd87  lea     r8, aIccdevicespres_0; "ICCDevicesPresent"
0x18001cd8e  lea     rdx, CLSID_IncomingConnectionCheckDevsPage
0x18001cd95  mov     [rsp+58h+var_38], 0
0x18001cd9e  mov     rax, [rcx]
0x18001cda1  mov     rax, [rax+30h]
0x18001cda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdaa  test    eax, eax
0x18001cdac  jnz     short loc_18001CDBC
0x18001cdae  cmp     [rsp+58h+arg_40], rax
0x18001cdb6  setnz   al
0x18001cdb9  mov     [rsi+50h], eax
0x18001cdbc  test    dil, 22h
0x18001cdc0  jz      loc_18001CE5E
0x18001cdc6  mov     edi, 68h ; 'h'
0x18001cdcb  mov     ecx, edi; cb
0x18001cdcd  call    cs:__imp_CoTaskMemAlloc
0x18001cdd3  mov     rbx, rax
0x18001cdd6  test    rax, rax
0x18001cdd9  jz      short loc_18001CE37
0x18001cddb  lea     rcx, [rax+8]; void *
0x18001cddf  xor     edx, edx; Val
0x18001cde1  lea     r8d, [rdi-8]; Size
0x18001cde5  call    memset_0
0x18001cdea  mov     [rbx], edi
0x18001cdec  mov     dword ptr [rbx+4], 1000h
0x18001cdf3  mov     rcx, cs:hInst
0x18001cdfa  mov     [rbx+8], rcx
0x18001cdfe  mov     [rbx+30h], rsi
0x18001ce02  mov     edx, [rsi+50h]
0x18001ce05  mov     ecx, edx
0x18001ce07  neg     ecx
0x18001ce09  sbb     rax, rax
0x18001ce0c  add     rax, 88h
0x18001ce12  mov     [rbx+10h], rax
0x18001ce16  neg     edx
0x18001ce18  sbb     rax, rax
0x18001ce1b  add     rax, 0BF7h
0x18001ce21  mov     [rbx+48h], rax
0x18001ce25  lea     rax, ?PageDlgProc@CIncomingConnectionSummaryPage@@CAHPEAUHWND__@@I_K_J@Z; CIncomingConnectionSummaryPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001ce2c  mov     [rbx+28h], rax
0x18001ce30  mov     [r14], rbx
0x18001ce33  xor     ebx, ebx
0x18001ce35  jmp     short loc_18001CE8B
0x18001ce37  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ce3d  mov     ebx, 8007000Eh
0x18001ce42  cmp     ecx, 0FFFFFFFFh
0x18001ce45  jz      short loc_18001CE8B
0x18001ce47  mov     r9d, ebx
0x18001ce4a  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001ce51  mov     edx, 0Ch; dwFlags
0x18001ce56  call    cs:__imp_TracePrintfExA
0x18001ce5c  jmp     short loc_18001CE8B
0x18001ce5e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ce64  mov     ebx, 80004001h
0x18001ce69  cmp     ecx, 0FFFFFFFFh
0x18001ce6c  jz      short loc_18001CE8B
0x18001ce6e  mov     [rsp+58h+var_30], ebx
0x18001ce72  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001ce79  mov     r9d, edi
0x18001ce7c  mov     dword ptr [rsp+58h+var_38], edi
0x18001ce80  mov     edx, 0Ch; dwFlags
0x18001ce85  call    cs:__imp_TracePrintfExA
0x18001ce8b  mov     eax, ebx
0x18001ce8d  add     rsp, 38h
0x18001ce91  pop     r14
0x18001ce93  pop     rdi
0x18001ce94  pop     rsi
0x18001ce95  pop     rbx
0x18001ce96  retn
```
