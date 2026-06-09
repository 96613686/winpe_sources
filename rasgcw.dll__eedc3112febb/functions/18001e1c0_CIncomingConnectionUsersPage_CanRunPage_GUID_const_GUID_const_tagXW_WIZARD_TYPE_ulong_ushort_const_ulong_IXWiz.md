# CIncomingConnectionUsersPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001e1c0`
- end: `0x18001e323`
- name: `?CanRunPage@CIncomingConnectionUsersPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `355`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001e1c0`
- `0x18001fe10`
- `0x180021438`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001e2dd`
- `rtutils!TracePrintfExA` at `0x18001e311`
- `rtutils!TracePrintfExA` at `0x18001e2dd`
- `rtutils!TracePrintfExA` at `0x18001e311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e2b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e2b6`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionUsersPage::CanRunPage(
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
      *v12 = 64;
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
0x18001e1c0  push    rbx
0x18001e1c2  push    rsi
0x18001e1c3  push    rdi
0x18001e1c4  push    r14
0x18001e1c6  sub     rsp, 38h
0x18001e1ca  mov     r14, [rsp+58h+arg_40]
0x18001e1d2  mov     rdi, rcx
0x18001e1d5  mov     rax, [rsp+58h+arg_38]
0x18001e1dd  mov     qword ptr [r14], 0
0x18001e1e4  movups  xmm0, xmmword ptr [rdx]
0x18001e1e7  mov     [rcx+50h], rax
0x18001e1eb  movdqu  xmmword ptr [rcx+40h], xmm0
0x18001e1f0  test    r9b, 22h
0x18001e1f4  jz      loc_18001E2EC
0x18001e1fa  mov     ebx, 1
0x18001e1ff  mov     edx, ebx
0x18001e201  lea     ecx, [rbx+17h]
0x18001e204  call    RassrvAlloc
0x18001e209  mov     [rdi+60h], rax
0x18001e20d  test    rax, rax
0x18001e210  jz      short loc_18001E223
0x18001e212  mov     dword ptr [rax], 40h ; '@'
0x18001e218  mov     rax, [rdi+60h]
0x18001e21c  mov     dword ptr [rax+4], 3
0x18001e223  cmp     qword ptr [rdi+60h], 0
0x18001e228  jz      loc_18001E2E5
0x18001e22e  mov     rcx, [rdi+50h]
0x18001e232  lea     r8, [rdi+58h]
0x18001e236  lea     rdx, IID_IXWizardPropertyBag
0x18001e23d  call    HrEnsureTearOffInterfaceLoaded
0x18001e242  test    eax, eax
0x18001e244  js      loc_18001E317
0x18001e24a  mov     rcx, [rdi+58h]
0x18001e24e  lea     r8, aIccpagehandle_2; "ICCPageHandle"
0x18001e255  mov     r9, [rdi+60h]
0x18001e259  lea     rdx, CLSID_IncomingConnectionHookPage
0x18001e260  add     r9, 8
0x18001e264  mov     [rsp+58h+var_38], 0
0x18001e26d  mov     rax, [rcx]
0x18001e270  mov     rax, [rax+30h]
0x18001e274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e279  mov     ecx, 68h ; 'h'; cb
0x18001e27e  mov     ebx, eax
0x18001e280  call    cs:__imp_CoTaskMemAlloc
0x18001e286  mov     rsi, rax
0x18001e289  test    rax, rax
0x18001e28c  jz      short loc_18001E2BE
0x18001e28e  xor     edx, edx; Val
0x18001e290  mov     rcx, rax; void *
0x18001e293  lea     r8d, [rdx+68h]; Size
0x18001e297  call    memset_0
0x18001e29c  mov     rdx, [rdi+60h]
0x18001e2a0  mov     rcx, rsi
0x18001e2a3  call    RasSrvAddPropPage
0x18001e2a8  test    eax, eax
0x18001e2aa  jnz     short loc_18001E2B3
0x18001e2ac  mov     [r14], rsi
0x18001e2af  xor     ebx, ebx
0x18001e2b1  jmp     short loc_18001E317
0x18001e2b3  mov     rcx, rsi; pv
0x18001e2b6  call    cs:__imp_CoTaskMemFree
0x18001e2bc  jmp     short loc_18001E317
0x18001e2be  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e2c4  mov     ebx, 8007000Eh
0x18001e2c9  cmp     ecx, 0FFFFFFFFh
0x18001e2cc  jz      short loc_18001E317
0x18001e2ce  mov     r9d, ebx
0x18001e2d1  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001e2d8  mov     edx, 0Ch; dwFlags
0x18001e2dd  call    cs:__imp_TracePrintfExA
0x18001e2e3  jmp     short loc_18001E317
0x18001e2e5  mov     ebx, 8007000Eh
0x18001e2ea  jmp     short loc_18001E317
0x18001e2ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e2f2  mov     ebx, 80004001h
0x18001e2f7  cmp     ecx, 0FFFFFFFFh
0x18001e2fa  jz      short loc_18001E317
0x18001e2fc  mov     [rsp+58h+var_30], ebx
0x18001e300  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001e307  mov     edx, 0Ch; dwFlags
0x18001e30c  mov     dword ptr [rsp+58h+var_38], r9d
0x18001e311  call    cs:__imp_TracePrintfExA
0x18001e317  mov     eax, ebx
0x18001e319  add     rsp, 38h
0x18001e31d  pop     r14
0x18001e31f  pop     rdi
0x18001e320  pop     rsi
0x18001e321  pop     rbx
0x18001e322  retn
```
