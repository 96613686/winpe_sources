# CCTWUserInfoPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180019320`
- end: `0x18001959b`
- name: `?CanRunPage@CCTWUserInfoPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `635`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, int, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x180019320`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001954b`
- `rtutils!TracePrintfExA` at `0x180019586`
- `rtutils!TracePrintfExA` at `0x18001954b`
- `rtutils!TracePrintfExA` at `0x180019586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800194b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800194b6`

## string_xrefs

- `0x180019577`: `HrEnsurePropertyBagAccess failed. hr = %#x`

## pseudocode

```c
__int64 __fastcall CCTWUserInfoPage::CanRunPage(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  _QWORD *v10; // r15
  __int128 v12; // xmm0
  int v13; // ebx
  __int64 v14; // rcx
  _DWORD *v15; // rcx
  __int64 v16; // rbx
  _BYTE *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  _BYTE *v20; // rax
  __int64 v21; // rax
  char *v22; // rax
  char *v23; // rbx

  v10 = a9;
  *a9 = 0;
  v12 = *a2;
  *(_DWORD *)(a1 + 24) = a5;
  *(_OWORD *)(a1 + 8) = v12;
  *(_QWORD *)(a1 + 56) = a8;
  v13 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 64);
  if ( v13 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrEnsurePropertyBagAccess failed. hr = %#x", (unsigned int)v13);
  }
  else
  {
    v14 = *(_QWORD *)(a1 + 64);
    a9 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD **, _QWORD))(*(_QWORD *)v14 + 48LL))(
            v14,
            a1 + 8,
            L"RASConnectionDetails",
            &a9,
            0);
    if ( v13 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to query property bag for rasncw. hr = %#x", (unsigned int)v13);
      return (unsigned int)v13;
    }
    if ( a9 && (v15 = (_DWORD *)*a9) != 0 )
    {
      *(_QWORD *)(a1 + 40) = v15;
      if ( *v15 == 2 )
      {
        v16 = 514;
        memset_0(v15 + 455, 0, 0x202u);
        v17 = (_BYTE *)(*(_QWORD *)(a1 + 40) + 2334LL);
        do
        {
          *v17++ = 0;
          --v16;
        }
        while ( v16 );
        v18 = *(_QWORD *)(a1 + 40);
        *(_OWORD *)(v18 + 2848) = 0;
        *(_OWORD *)(v18 + 2864) = 0;
        *(_WORD *)(v18 + 2880) = 0;
        return 0;
      }
      if ( v15[454] )
      {
        v19 = 514;
        memset_0(v15 + 455, 0, 0x202u);
        v20 = (_BYTE *)(*(_QWORD *)(a1 + 40) + 2334LL);
        do
        {
          *v20++ = 0;
          --v19;
        }
        while ( v19 );
        v21 = *(_QWORD *)(a1 + 40);
        *(_OWORD *)(v21 + 2848) = 0;
        *(_OWORD *)(v21 + 2864) = 0;
        *(_WORD *)(v21 + 2880) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 2888LL) = 0;
        return 0;
      }
      if ( (a4 & 0x22) != 0 )
      {
        v22 = (char *)CoTaskMemAlloc(0x68u);
        v23 = v22;
        if ( v22 )
        {
          memset_0(v22 + 8, 0, 0x60u);
          *(_DWORD *)v23 = 104;
          *((_DWORD *)v23 + 1) = 4096;
          *((_QWORD *)v23 + 1) = hInst;
          *((_QWORD *)v23 + 5) = CCTWUserInfoPage::PageDlgProc;
          *((_QWORD *)v23 + 6) = a1;
          *((_QWORD *)v23 + 2) = 101;
          *((_QWORD *)v23 + 9) = 3023;
          *v10 = v23;
          return 0;
        }
        v13 = -2147024882;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x",
            2147942414LL);
      }
      else
      {
        v13 = -2147467263;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
      }
    }
    else
    {
      v13 = -2147467259;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Unable to get RasNcwInfo handle. hr = %#x", 2147500037LL);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019320  push    rbx
0x180019322  push    rbp
0x180019323  push    rsi
0x180019324  push    rdi
0x180019325  push    r14
0x180019327  push    r15
0x180019329  sub     rsp, 38h
0x18001932d  mov     eax, [rsp+68h+arg_20]
0x180019334  mov     rdi, rcx
0x180019337  mov     r15, [rsp+68h+arg_40]
0x18001933f  mov     esi, r9d
0x180019342  lea     r8, [rdi+40h]
0x180019346  mov     qword ptr [r15], 0
0x18001934d  movups  xmm0, xmmword ptr [rdx]
0x180019350  lea     rdx, IID_IXWizardPropertyBag
0x180019357  mov     [rdi+18h], eax
0x18001935a  movdqu  xmmword ptr [rcx+8], xmm0
0x18001935f  mov     rcx, [rsp+68h+arg_38]
0x180019367  mov     [rdi+38h], rcx
0x18001936b  call    HrEnsureTearOffInterfaceLoaded
0x180019370  mov     ebx, eax
0x180019372  test    eax, eax
0x180019374  js      loc_18001956C
0x18001937a  mov     rcx, [rdi+40h]
0x18001937e  lea     r9, [rsp+68h+arg_40]
0x180019386  mov     [rsp+68h+arg_40], 0
0x180019392  lea     r8, aRasconnectiond_1; "RASConnectionDetails"
0x180019399  lea     rdx, [rdi+8]
0x18001939d  mov     [rsp+68h+var_48], 0
0x1800193a6  mov     rax, [rcx]
0x1800193a9  mov     rax, [rax+30h]
0x1800193ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193b2  mov     ebx, eax
0x1800193b4  test    eax, eax
0x1800193b6  jns     short loc_1800193D3
0x1800193b8  mov     ecx, cs:g_dwTraceId
0x1800193be  cmp     ecx, 0FFFFFFFFh
0x1800193c1  jz      loc_18001958C
0x1800193c7  lea     r8, aFailedToQueryP; "Failed to query property bag for rasncw"...
0x1800193ce  jmp     loc_18001957E
0x1800193d3  mov     rcx, [rsp+68h+arg_40]
0x1800193db  test    rcx, rcx
0x1800193de  jz      loc_180019553
0x1800193e4  mov     rcx, [rcx]
0x1800193e7  test    rcx, rcx
0x1800193ea  jz      loc_180019553
0x1800193f0  mov     [rdi+28h], rcx
0x1800193f4  cmp     dword ptr [rcx], 2
0x1800193f7  jnz     short loc_180019445
0x1800193f9  mov     ebx, 202h
0x1800193fe  add     rcx, 71Ch; void *
0x180019405  mov     r8d, ebx; Size
0x180019408  xor     edx, edx; Val
0x18001940a  call    memset_0
0x18001940f  mov     rax, [rdi+28h]
0x180019413  add     rax, 91Eh
0x180019419  mov     byte ptr [rax], 0
0x18001941c  inc     rax
0x18001941f  sub     rbx, 1
0x180019423  jnz     short loc_180019419
0x180019425  mov     rax, [rdi+28h]
0x180019429  xorps   xmm0, xmm0
0x18001942c  xor     ecx, ecx
0x18001942e  movups  xmmword ptr [rax+0B20h], xmm0
0x180019435  movups  xmmword ptr [rax+0B30h], xmm0
0x18001943c  mov     [rax+0B40h], cx
0x180019443  jmp     short loc_1800194A2
0x180019445  cmp     dword ptr [rcx+718h], 0
0x18001944c  jz      short loc_1800194A9
0x18001944e  mov     ebx, 202h
0x180019453  add     rcx, 71Ch; void *
0x18001945a  mov     r8d, ebx; Size
0x18001945d  xor     edx, edx; Val
0x18001945f  call    memset_0
0x180019464  mov     rax, [rdi+28h]
0x180019468  add     rax, 91Eh
0x18001946e  mov     byte ptr [rax], 0
0x180019471  inc     rax
0x180019474  sub     rbx, 1
0x180019478  jnz     short loc_18001946E
0x18001947a  mov     rax, [rdi+28h]
0x18001947e  xorps   xmm0, xmm0
0x180019481  xor     ecx, ecx
0x180019483  movups  xmmword ptr [rax+0B20h], xmm0
0x18001948a  movups  xmmword ptr [rax+0B30h], xmm0
0x180019491  mov     [rax+0B40h], cx
0x180019498  mov     rax, [rdi+28h]
0x18001949c  mov     [rax+0B48h], ecx
0x1800194a2  xor     ebx, ebx
0x1800194a4  jmp     loc_18001958C
0x1800194a9  test    sil, 22h
0x1800194ad  jz      short loc_180019524
0x1800194af  mov     esi, 68h ; 'h'
0x1800194b4  mov     ecx, esi; cb
0x1800194b6  call    cs:__imp_CoTaskMemAlloc
0x1800194bc  mov     rbx, rax
0x1800194bf  test    rax, rax
0x1800194c2  jz      short loc_18001950B
0x1800194c4  lea     rcx, [rax+8]; void *
0x1800194c8  xor     edx, edx; Val
0x1800194ca  lea     r8d, [rsi-8]; Size
0x1800194ce  call    memset_0
0x1800194d3  mov     [rbx], esi
0x1800194d5  lea     rax, ?PageDlgProc@CCTWUserInfoPage@@CAHPEAUHWND__@@I_K_J@Z; CCTWUserInfoPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800194dc  mov     dword ptr [rbx+4], 1000h
0x1800194e3  mov     rcx, cs:hInst
0x1800194ea  mov     [rbx+8], rcx
0x1800194ee  mov     [rbx+28h], rax
0x1800194f2  mov     [rbx+30h], rdi
0x1800194f6  mov     qword ptr [rbx+10h], 65h ; 'e'
0x1800194fe  mov     qword ptr [rbx+48h], 0BCFh
0x180019506  mov     [r15], rbx
0x180019509  jmp     short loc_1800194A2
0x18001950b  mov     ecx, cs:g_dwTraceId
0x180019511  mov     ebx, 8007000Eh
0x180019516  cmp     ecx, 0FFFFFFFFh
0x180019519  jz      short loc_18001958C
0x18001951b  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x180019522  jmp     short loc_18001957E
0x180019524  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001952a  mov     ebx, 80004001h
0x18001952f  cmp     ecx, 0FFFFFFFFh
0x180019532  jz      short loc_18001958C
0x180019534  mov     [rsp+68h+var_40], ebx
0x180019538  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001953f  mov     r9d, esi
0x180019542  mov     dword ptr [rsp+68h+var_48], esi
0x180019546  mov     edx, 0Ch; dwFlags
0x18001954b  call    cs:__imp_TracePrintfExA
0x180019551  jmp     short loc_18001958C
0x180019553  mov     ecx, cs:g_dwTraceId
0x180019559  mov     ebx, 80004005h
0x18001955e  cmp     ecx, 0FFFFFFFFh
0x180019561  jz      short loc_18001958C
0x180019563  lea     r8, aUnableToGetRas_0; "Unable to get RasNcwInfo handle. hr = %"...
0x18001956a  jmp     short loc_18001957E
0x18001956c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180019572  cmp     ecx, 0FFFFFFFFh
0x180019575  jz      short loc_18001958C
0x180019577  lea     r8, aHrensureproper; "HrEnsurePropertyBagAccess failed. hr = "...
0x18001957e  mov     r9d, ebx
0x180019581  mov     edx, 0Ch; dwFlags
0x180019586  call    cs:__imp_TracePrintfExA
0x18001958c  mov     eax, ebx
0x18001958e  add     rsp, 38h
0x180019592  pop     r15
0x180019594  pop     r14
0x180019596  pop     rdi
0x180019597  pop     rsi
0x180019598  pop     rbp
0x180019599  pop     rbx
0x18001959a  retn
```
