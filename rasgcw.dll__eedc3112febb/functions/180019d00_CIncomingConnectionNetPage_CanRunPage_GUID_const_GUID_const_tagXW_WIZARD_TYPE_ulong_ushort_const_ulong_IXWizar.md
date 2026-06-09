# CIncomingConnectionNetPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180019d00`
- end: `0x180019e63`
- name: `?CanRunPage@CIncomingConnectionNetPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `355`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x180019d00`
- `0x18001fe10`
- `0x180021438`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180019e1d`
- `rtutils!TracePrintfExA` at `0x180019e51`
- `rtutils!TracePrintfExA` at `0x180019e1d`
- `rtutils!TracePrintfExA` at `0x180019e51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019dc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019dc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019df6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019df6`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionNetPage::CanRunPage(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  __int128 v10; // xmm0
  unsigned int v11; // ebx
  _DWORD *v12; // rax
  void *v13; // rax
  void *v14; // rsi

  *a9 = 0;
  v10 = *a2;
  *(_QWORD *)(a1 + 80) = a8;
  *(_OWORD *)(a1 + 64) = v10;
  if ( (a4 & 0x22) != 0 )
  {
    v11 = 1;
    v12 = (_DWORD *)RassrvAlloc(24, 1);
    *(_QWORD *)(a1 + 96) = v12;
    if ( v12 )
    {
      *v12 = 128;
      *(_DWORD *)(*(_QWORD *)(a1 + 96) + 4LL) = 3;
    }
    if ( *(_QWORD *)(a1 + 96) )
    {
      if ( (int)HrEnsureTearOffInterfaceLoaded(*(_QWORD *)(a1 + 80), &IID_IXWizardPropertyBag, a1 + 88) >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, GUID *, const wchar_t *, __int64, _QWORD))(**(_QWORD **)(a1 + 88) + 48LL))(
                *(_QWORD *)(a1 + 88),
                &CLSID_IncomingConnectionHookPage,
                L"ICCPageHandle",
                *(_QWORD *)(a1 + 96) + 8LL,
                0);
        v13 = CoTaskMemAlloc(0x68u);
        v14 = v13;
        if ( v13 )
        {
          memset_0(v13, 0, 0x68u);
          if ( (unsigned int)RasSrvAddPropPage(v14, *(_QWORD *)(a1 + 96)) )
          {
            CoTaskMemFree(v14);
          }
          else
          {
            *a9 = v14;
            return 0;
          }
        }
        else
        {
          v11 = -2147024882;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x",
              -2147024882);
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v11 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v11;
}

```

## disassembly

```asm
0x180019d00  push    rbx
0x180019d02  push    rsi
0x180019d03  push    rdi
0x180019d04  push    r14
0x180019d06  sub     rsp, 38h
0x180019d0a  mov     r14, [rsp+58h+arg_40]
0x180019d12  mov     rdi, rcx
0x180019d15  mov     rax, [rsp+58h+arg_38]
0x180019d1d  mov     qword ptr [r14], 0
0x180019d24  movups  xmm0, xmmword ptr [rdx]
0x180019d27  mov     [rcx+50h], rax
0x180019d2b  movdqu  xmmword ptr [rcx+40h], xmm0
0x180019d30  test    r9b, 22h
0x180019d34  jz      loc_180019E2C
0x180019d3a  mov     ebx, 1
0x180019d3f  mov     edx, ebx
0x180019d41  lea     ecx, [rbx+17h]
0x180019d44  call    RassrvAlloc
0x180019d49  mov     [rdi+60h], rax
0x180019d4d  test    rax, rax
0x180019d50  jz      short loc_180019D63
0x180019d52  mov     dword ptr [rax], 80h
0x180019d58  mov     rax, [rdi+60h]
0x180019d5c  mov     dword ptr [rax+4], 3
0x180019d63  cmp     qword ptr [rdi+60h], 0
0x180019d68  jz      loc_180019E25
0x180019d6e  mov     rcx, [rdi+50h]
0x180019d72  lea     r8, [rdi+58h]
0x180019d76  lea     rdx, IID_IXWizardPropertyBag
0x180019d7d  call    HrEnsureTearOffInterfaceLoaded
0x180019d82  test    eax, eax
0x180019d84  js      loc_180019E57
0x180019d8a  mov     rcx, [rdi+58h]
0x180019d8e  lea     r8, aIccpagehandle_0; "ICCPageHandle"
0x180019d95  mov     r9, [rdi+60h]
0x180019d99  lea     rdx, CLSID_IncomingConnectionHookPage
0x180019da0  add     r9, 8
0x180019da4  mov     [rsp+58h+var_38], 0
0x180019dad  mov     rax, [rcx]
0x180019db0  mov     rax, [rax+30h]
0x180019db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019db9  mov     ecx, 68h ; 'h'; cb
0x180019dbe  mov     ebx, eax
0x180019dc0  call    cs:__imp_CoTaskMemAlloc
0x180019dc6  mov     rsi, rax
0x180019dc9  test    rax, rax
0x180019dcc  jz      short loc_180019DFE
0x180019dce  xor     edx, edx; Val
0x180019dd0  mov     rcx, rax; void *
0x180019dd3  lea     r8d, [rdx+68h]; Size
0x180019dd7  call    memset_0
0x180019ddc  mov     rdx, [rdi+60h]
0x180019de0  mov     rcx, rsi
0x180019de3  call    RasSrvAddPropPage
0x180019de8  test    eax, eax
0x180019dea  jnz     short loc_180019DF3
0x180019dec  mov     [r14], rsi
0x180019def  xor     ebx, ebx
0x180019df1  jmp     short loc_180019E57
0x180019df3  mov     rcx, rsi; pv
0x180019df6  call    cs:__imp_CoTaskMemFree
0x180019dfc  jmp     short loc_180019E57
0x180019dfe  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180019e04  mov     ebx, 8007000Eh
0x180019e09  cmp     ecx, 0FFFFFFFFh
0x180019e0c  jz      short loc_180019E57
0x180019e0e  mov     r9d, ebx
0x180019e11  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x180019e18  mov     edx, 0Ch; dwFlags
0x180019e1d  call    cs:__imp_TracePrintfExA
0x180019e23  jmp     short loc_180019E57
0x180019e25  mov     ebx, 8007000Eh
0x180019e2a  jmp     short loc_180019E57
0x180019e2c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180019e32  mov     ebx, 80004001h
0x180019e37  cmp     ecx, 0FFFFFFFFh
0x180019e3a  jz      short loc_180019E57
0x180019e3c  mov     [rsp+58h+var_30], ebx
0x180019e40  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x180019e47  mov     edx, 0Ch; dwFlags
0x180019e4c  mov     dword ptr [rsp+58h+var_38], r9d
0x180019e51  call    cs:__imp_TracePrintfExA
0x180019e57  mov     eax, ebx
0x180019e59  add     rsp, 38h
0x180019e5d  pop     r14
0x180019e5f  pop     rdi
0x180019e60  pop     rsi
0x180019e61  pop     rbx
0x180019e62  retn
```
