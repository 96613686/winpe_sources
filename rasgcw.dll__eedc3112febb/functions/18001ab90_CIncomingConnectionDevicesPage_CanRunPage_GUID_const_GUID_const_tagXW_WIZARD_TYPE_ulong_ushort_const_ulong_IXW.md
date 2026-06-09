# CIncomingConnectionDevicesPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001ab90`
- end: `0x18001acf3`
- name: `?CanRunPage@CIncomingConnectionDevicesPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `355`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001ab90`
- `0x18001fe10`
- `0x180021438`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001acad`
- `rtutils!TracePrintfExA` at `0x18001ace1`
- `rtutils!TracePrintfExA` at `0x18001acad`
- `rtutils!TracePrintfExA` at `0x18001ace1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ac50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ac50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac86`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionDevicesPage::CanRunPage(
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
      *v12 = 16;
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
0x18001ab90  push    rbx
0x18001ab92  push    rsi
0x18001ab93  push    rdi
0x18001ab94  push    r14
0x18001ab96  sub     rsp, 38h
0x18001ab9a  mov     r14, [rsp+58h+arg_40]
0x18001aba2  mov     rdi, rcx
0x18001aba5  mov     rax, [rsp+58h+arg_38]
0x18001abad  mov     qword ptr [r14], 0
0x18001abb4  movups  xmm0, xmmword ptr [rdx]
0x18001abb7  mov     [rcx+50h], rax
0x18001abbb  movdqu  xmmword ptr [rcx+40h], xmm0
0x18001abc0  test    r9b, 22h
0x18001abc4  jz      loc_18001ACBC
0x18001abca  mov     ebx, 1
0x18001abcf  mov     edx, ebx
0x18001abd1  lea     ecx, [rbx+17h]
0x18001abd4  call    RassrvAlloc
0x18001abd9  mov     [rdi+60h], rax
0x18001abdd  test    rax, rax
0x18001abe0  jz      short loc_18001ABF3
0x18001abe2  mov     dword ptr [rax], 10h
0x18001abe8  mov     rax, [rdi+60h]
0x18001abec  mov     dword ptr [rax+4], 3
0x18001abf3  cmp     qword ptr [rdi+60h], 0
0x18001abf8  jz      loc_18001ACB5
0x18001abfe  mov     rcx, [rdi+50h]
0x18001ac02  lea     r8, [rdi+58h]
0x18001ac06  lea     rdx, IID_IXWizardPropertyBag
0x18001ac0d  call    HrEnsureTearOffInterfaceLoaded
0x18001ac12  test    eax, eax
0x18001ac14  js      loc_18001ACE7
0x18001ac1a  mov     rcx, [rdi+58h]
0x18001ac1e  lea     r8, aIccpagehandle_1; "ICCPageHandle"
0x18001ac25  mov     r9, [rdi+60h]
0x18001ac29  lea     rdx, CLSID_IncomingConnectionHookPage
0x18001ac30  add     r9, 8
0x18001ac34  mov     [rsp+58h+var_38], 0
0x18001ac3d  mov     rax, [rcx]
0x18001ac40  mov     rax, [rax+30h]
0x18001ac44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac49  mov     ecx, 68h ; 'h'; cb
0x18001ac4e  mov     ebx, eax
0x18001ac50  call    cs:__imp_CoTaskMemAlloc
0x18001ac56  mov     rsi, rax
0x18001ac59  test    rax, rax
0x18001ac5c  jz      short loc_18001AC8E
0x18001ac5e  xor     edx, edx; Val
0x18001ac60  mov     rcx, rax; void *
0x18001ac63  lea     r8d, [rdx+68h]; Size
0x18001ac67  call    memset_0
0x18001ac6c  mov     rdx, [rdi+60h]
0x18001ac70  mov     rcx, rsi
0x18001ac73  call    RasSrvAddPropPage
0x18001ac78  test    eax, eax
0x18001ac7a  jnz     short loc_18001AC83
0x18001ac7c  mov     [r14], rsi
0x18001ac7f  xor     ebx, ebx
0x18001ac81  jmp     short loc_18001ACE7
0x18001ac83  mov     rcx, rsi; pv
0x18001ac86  call    cs:__imp_CoTaskMemFree
0x18001ac8c  jmp     short loc_18001ACE7
0x18001ac8e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ac94  mov     ebx, 8007000Eh
0x18001ac99  cmp     ecx, 0FFFFFFFFh
0x18001ac9c  jz      short loc_18001ACE7
0x18001ac9e  mov     r9d, ebx
0x18001aca1  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001aca8  mov     edx, 0Ch; dwFlags
0x18001acad  call    cs:__imp_TracePrintfExA
0x18001acb3  jmp     short loc_18001ACE7
0x18001acb5  mov     ebx, 8007000Eh
0x18001acba  jmp     short loc_18001ACE7
0x18001acbc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001acc2  mov     ebx, 80004001h
0x18001acc7  cmp     ecx, 0FFFFFFFFh
0x18001acca  jz      short loc_18001ACE7
0x18001accc  mov     [rsp+58h+var_30], ebx
0x18001acd0  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001acd7  mov     edx, 0Ch; dwFlags
0x18001acdc  mov     dword ptr [rsp+58h+var_38], r9d
0x18001ace1  call    cs:__imp_TracePrintfExA
0x18001ace7  mov     eax, ebx
0x18001ace9  add     rsp, 38h
0x18001aced  pop     r14
0x18001acef  pop     rdi
0x18001acf0  pop     rsi
0x18001acf1  pop     rbx
0x18001acf2  retn
```
