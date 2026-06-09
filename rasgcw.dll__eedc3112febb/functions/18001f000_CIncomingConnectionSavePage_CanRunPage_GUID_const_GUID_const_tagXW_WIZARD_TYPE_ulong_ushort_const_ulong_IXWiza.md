# CIncomingConnectionSavePage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001f000`
- end: `0x18001f16e`
- name: `?CanRunPage@CIncomingConnectionSavePage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `366`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001f000`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001f098`
- `rtutils!TracePrintfExA` at `0x18001f12d`
- `rtutils!TracePrintfExA` at `0x18001f15c`
- `rtutils!TracePrintfExA` at `0x18001f098`
- `rtutils!TracePrintfExA` at `0x18001f12d`
- `rtutils!TracePrintfExA` at `0x18001f15c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f0b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f0b7`

## string_xrefs

- `0x18001f08c`: `CIncomingConnectionSavePage::CanRunPage: Failed to get c_szICCPageHandle = %#x`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSavePage::CanRunPage(
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
  _QWORD *v11; // rbx
  int v12; // eax
  char *v13; // rax
  char *v14; // rbx
  unsigned int v15; // ebx

  *a9 = 0;
  v11 = (_QWORD *)(a1 + 136);
  *(_OWORD *)(a1 + 104) = *a2;
  *(_QWORD *)(a1 + 128) = a8;
  if ( (int)HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 136) >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, const wchar_t *, __int64, _QWORD))(*(_QWORD *)*v11 + 48LL))(
            *v11,
            &CLSID_IncomingConnectionHookPage,
            L"ICCPageHandle",
            a1 + 120,
            0);
    if ( v12 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "CIncomingConnectionSavePage::CanRunPage: Failed to get c_szICCPageHandle = %#x",
          v12);
      *(_QWORD *)(a1 + 120) = 0;
    }
  }
  if ( (a4 & 0x22) != 0 )
  {
    v13 = (char *)CoTaskMemAlloc(0x68u);
    v14 = v13;
    if ( v13 )
    {
      memset_0(v13 + 8, 0, 0x60u);
      *(_DWORD *)v14 = 104;
      *((_DWORD *)v14 + 1) = 4096;
      *((_QWORD *)v14 + 1) = hInst;
      *((_QWORD *)v14 + 5) = CIncomingConnectionSavePage::PageDlgProc;
      *((_QWORD *)v14 + 6) = a1;
      *((_QWORD *)v14 + 2) = 134;
      *((_QWORD *)v14 + 9) = 3061;
      *a9 = v14;
      return 0;
    }
    else
    {
      v15 = -2147024882;
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
    v15 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v15;
}

```

## disassembly

```asm
0x18001f000  push    rbx
0x18001f002  push    rsi
0x18001f003  push    rdi
0x18001f004  push    r14
0x18001f006  sub     rsp, 38h
0x18001f00a  mov     r14, [rsp+58h+arg_40]
0x18001f012  mov     rsi, rcx
0x18001f015  mov     edi, r9d
0x18001f018  mov     qword ptr [r14], 0
0x18001f01f  lea     rbx, [rsi+88h]
0x18001f026  movups  xmm0, xmmword ptr [rdx]
0x18001f029  mov     r8, rbx
0x18001f02c  lea     rdx, IID_IXWizardPropertyBag
0x18001f033  movdqu  xmmword ptr [rcx+68h], xmm0
0x18001f038  mov     rcx, [rsp+58h+arg_38]
0x18001f040  mov     [rsi+80h], rcx
0x18001f047  call    HrEnsureTearOffInterfaceLoaded
0x18001f04c  test    eax, eax
0x18001f04e  js      short loc_18001F0A6
0x18001f050  mov     rcx, [rbx]
0x18001f053  lea     r9, [rsi+78h]
0x18001f057  lea     r8, aIccpagehandle_3; "ICCPageHandle"
0x18001f05e  mov     [rsp+58h+var_38], 0
0x18001f067  lea     rdx, CLSID_IncomingConnectionHookPage
0x18001f06e  mov     rax, [rcx]
0x18001f071  mov     rax, [rax+30h]
0x18001f075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f07a  test    eax, eax
0x18001f07c  jns     short loc_18001F0A6
0x18001f07e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f084  cmp     ecx, 0FFFFFFFFh
0x18001f087  jz      short loc_18001F09E
0x18001f089  mov     r9d, eax
0x18001f08c  lea     r8, aCincomingconne; "CIncomingConnectionSavePage::CanRunPage"...
0x18001f093  mov     edx, 0Ch; dwFlags
0x18001f098  call    cs:__imp_TracePrintfExA
0x18001f09e  mov     qword ptr [rsi+78h], 0
0x18001f0a6  test    dil, 22h
0x18001f0aa  jz      loc_18001F135
0x18001f0b0  mov     edi, 68h ; 'h'
0x18001f0b5  mov     ecx, edi; cb
0x18001f0b7  call    cs:__imp_CoTaskMemAlloc
0x18001f0bd  mov     rbx, rax
0x18001f0c0  test    rax, rax
0x18001f0c3  jz      short loc_18001F10E
0x18001f0c5  lea     rcx, [rax+8]; void *
0x18001f0c9  xor     edx, edx; Val
0x18001f0cb  lea     r8d, [rdi-8]; Size
0x18001f0cf  call    memset_0
0x18001f0d4  mov     [rbx], edi
0x18001f0d6  lea     rax, ?PageDlgProc@CIncomingConnectionSavePage@@CAHPEAUHWND__@@I_K_J@Z; CIncomingConnectionSavePage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001f0dd  mov     dword ptr [rbx+4], 1000h
0x18001f0e4  mov     rcx, cs:hInst
0x18001f0eb  mov     [rbx+8], rcx
0x18001f0ef  mov     [rbx+28h], rax
0x18001f0f3  mov     [rbx+30h], rsi
0x18001f0f7  mov     qword ptr [rbx+10h], 86h
0x18001f0ff  mov     qword ptr [rbx+48h], 0BF5h
0x18001f107  mov     [r14], rbx
0x18001f10a  xor     ebx, ebx
0x18001f10c  jmp     short loc_18001F162
0x18001f10e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f114  mov     ebx, 8007000Eh
0x18001f119  cmp     ecx, 0FFFFFFFFh
0x18001f11c  jz      short loc_18001F162
0x18001f11e  mov     r9d, ebx
0x18001f121  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001f128  mov     edx, 0Ch; dwFlags
0x18001f12d  call    cs:__imp_TracePrintfExA
0x18001f133  jmp     short loc_18001F162
0x18001f135  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f13b  mov     ebx, 80004001h
0x18001f140  cmp     ecx, 0FFFFFFFFh
0x18001f143  jz      short loc_18001F162
0x18001f145  mov     [rsp+58h+var_30], ebx
0x18001f149  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001f150  mov     r9d, edi
0x18001f153  mov     dword ptr [rsp+58h+var_38], edi
0x18001f157  mov     edx, 0Ch; dwFlags
0x18001f15c  call    cs:__imp_TracePrintfExA
0x18001f162  mov     eax, ebx
0x18001f164  add     rsp, 38h
0x18001f168  pop     r14
0x18001f16a  pop     rdi
0x18001f16b  pop     rsi
0x18001f16c  pop     rbx
0x18001f16d  retn
```
