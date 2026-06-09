# CDialupConnectionRetryPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001d230`
- end: `0x18001d516`
- name: `?CanRunPage@CDialupConnectionRetryPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `742`
- prototype: `__int64 __fastcall(__int64 *, __int128 *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010c38`
- `0x1800114d8`
- `0x18001d230`
- `0x18001d51c`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001d278`
- `rtutils!TracePrintfExA` at `0x18001d3b9`
- `rtutils!TracePrintfExA` at `0x18001d3f6`
- `rtutils!TracePrintfExA` at `0x18001d4b6`
- `rtutils!TracePrintfExA` at `0x18001d4db`
- `rtutils!TracePrintfExA` at `0x18001d4fd`
- `rtutils!TracePrintfExA` at `0x18001d278`
- `rtutils!TracePrintfExA` at `0x18001d3b9`
- `rtutils!TracePrintfExA` at `0x18001d3f6`
- `rtutils!TracePrintfExA` at `0x18001d4b6`
- `rtutils!TracePrintfExA` at `0x18001d4db`
- `rtutils!TracePrintfExA` at `0x18001d4fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d414`

## string_xrefs

- `0x18001d4f0`: `HrEnsurePropertyBagAccess failed. hr = %#x`
- `0x18001d366`: `Modem check is already in 'Connect to Internet', so skipping this page`
- `0x18001d3ec`: `There are no modems configured. Skipping Modem error pages, as this is dummy task`

## pseudocode

```c
__int64 __fastcall CDialupConnectionRetryPage::CanRunPage(
        __int64 *a1,
        __int128 *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  _QWORD *v9; // r14
  __int128 v13; // xmm0
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  char *v19; // rax
  char *v20; // rdi
  unsigned int v21; // ebx

  v9 = a9;
  *a9 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "In CDialupConnectionRetryPage::CanRunPage");
  v13 = *a2;
  a1[15] = a8;
  *(_OWORD *)(a1 + 1) = v13;
  v14 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 16);
  if ( v14 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrEnsurePropertyBagAccess failed. hr = %#x", (unsigned int)v14);
    return (unsigned int)v14;
  }
  v15 = a1[16];
  a9 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, const wchar_t *, _QWORD **, _QWORD))(*(_QWORD *)v15 + 48LL))(
          v15,
          a1 + 1,
          L"RASConnectionDetails",
          &a9,
          0);
  if ( v14 >= 0 )
  {
    if ( a9 && *a9 )
    {
      v16 = *a1;
      a1[12] = *a9;
      if ( (*(unsigned int (__fastcall **)(__int64 *))(v16 + 96))(a1) == 1 )
      {
        memset_0((void *)(a1[12] + 4436), 0, 0x202u);
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Modem check is already in 'Connect to Internet', so skipping this page");
        return 0;
      }
      CDialupConnectionRetryPage::EnumerateRasModemDevices((CDialupConnectionRetryPage *)a1);
      v17 = a1[12];
      if ( *((_DWORD *)a1 + 28) == 1 )
      {
        StringCchCopyW((unsigned __int16 *)(v17 + 4436), 0x101u, (unsigned __int16 *)a1[13]);
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "There is only one modem connected [%S] Hence skipping this page",
            (const wchar_t *)(a1[12] + 4436));
        return 0;
      }
      if ( (*(_BYTE *)(v17 + 4) & 4) != 0 && !*((_DWORD *)a1 + 28) )
      {
        memset_0((void *)(v17 + 4436), 0, 0x202u);
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "There are no modems configured. Skipping Modem error pages, as this is dummy task");
        return 0;
      }
      if ( (a4 & 0x22) != 0 )
      {
        v19 = (char *)CoTaskMemAlloc(0x68u);
        v20 = v19;
        if ( v19 )
        {
          memset_0(v19 + 8, 0, 0x60u);
          *(_DWORD *)v20 = 104;
          *((_DWORD *)v20 + 1) = 4096;
          *((_QWORD *)v20 + 1) = hInst;
          *((_QWORD *)v20 + 6) = a1;
          *((_QWORD *)v20 + 2) = 110;
          *((_QWORD *)v20 + 9) = (*((_DWORD *)a1 + 28) != 0) + 3025LL;
          v21 = 0;
          *((_QWORD *)v20 + 5) = CDialupConnectionRetryPage::PageDlgProc;
          *v9 = v20;
        }
        else
        {
          v21 = -2147024882;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "Unable to allocate memory for PROPSHEETPAGE structure. hr = %#x",
              2147942414LL);
        }
      }
      else
      {
        v21 = -2147467263;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
      }
    }
    else
    {
      v21 = -2147467259;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Unable to get RasNcwInfo handle. hr = %#x", 2147500037LL);
    }
    return v21;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "Failed to query property bag for rasncw. hr = %#x", (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001d230  push    rbx
0x18001d232  push    rbp
0x18001d233  push    rsi
0x18001d234  push    rdi
0x18001d235  push    r12
0x18001d237  push    r13
0x18001d239  push    r14
0x18001d23b  push    r15
0x18001d23d  sub     rsp, 38h
0x18001d241  mov     r14, [rsp+78h+arg_40]
0x18001d249  mov     rbx, rcx
0x18001d24c  or      r12d, 0FFFFFFFFh
0x18001d250  mov     esi, r9d
0x18001d253  mov     rdi, rdx
0x18001d256  mov     r13d, 0Ch
0x18001d25c  mov     qword ptr [r14], 0
0x18001d263  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d269  cmp     ecx, r12d
0x18001d26c  jz      short loc_18001D27E
0x18001d26e  lea     r8, aInCdialupconne; "In CDialupConnectionRetryPage::CanRunPa"...
0x18001d275  mov     edx, r13d; dwFlags
0x18001d278  call    cs:__imp_TracePrintfExA
0x18001d27e  movups  xmm0, xmmword ptr [rdi]
0x18001d281  mov     rcx, [rsp+78h+arg_38]
0x18001d289  lea     r15, [rbx+80h]
0x18001d290  mov     r8, r15
0x18001d293  mov     [rbx+78h], rcx
0x18001d297  lea     rdx, IID_IXWizardPropertyBag
0x18001d29e  movdqu  xmmword ptr [rbx+8], xmm0
0x18001d2a3  call    HrEnsureTearOffInterfaceLoaded
0x18001d2a8  mov     edi, eax
0x18001d2aa  test    eax, eax
0x18001d2ac  js      loc_18001D4E5
0x18001d2b2  mov     rcx, [r15]
0x18001d2b5  lea     r9, [rsp+78h+arg_40]
0x18001d2bd  mov     [rsp+78h+arg_40], 0
0x18001d2c9  lea     r8, aRasconnectiond_4; "RASConnectionDetails"
0x18001d2d0  lea     rdx, [rbx+8]
0x18001d2d4  mov     [rsp+78h+var_58], 0
0x18001d2dd  mov     rax, [rcx]
0x18001d2e0  mov     rax, [rax+30h]
0x18001d2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2e9  mov     edi, eax
0x18001d2eb  test    eax, eax
0x18001d2ed  jns     short loc_18001D30A
0x18001d2ef  mov     ecx, cs:g_dwTraceId
0x18001d2f5  cmp     ecx, r12d
0x18001d2f8  jz      loc_18001D503
0x18001d2fe  lea     r8, aFailedToQueryP; "Failed to query property bag for rasncw"...
0x18001d305  jmp     loc_18001D4F7
0x18001d30a  mov     rax, [rsp+78h+arg_40]
0x18001d312  test    rax, rax
0x18001d315  jz      loc_18001D4BE
0x18001d31b  mov     rcx, [rax]
0x18001d31e  test    rcx, rcx
0x18001d321  jz      loc_18001D4BE
0x18001d327  mov     rax, [rbx]
0x18001d32a  mov     [rbx+60h], rcx
0x18001d32e  mov     rcx, rbx
0x18001d331  mov     rax, [rax+60h]
0x18001d335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d33a  cmp     eax, 1
0x18001d33d  jnz     short loc_18001D372
0x18001d33f  mov     rcx, [rbx+60h]
0x18001d343  xor     edx, edx; Val
0x18001d345  add     rcx, 1154h; void *
0x18001d34c  mov     r8d, 202h; Size
0x18001d352  call    memset_0
0x18001d357  mov     ecx, cs:g_dwTraceId
0x18001d35d  cmp     ecx, r12d
0x18001d360  jz      loc_18001D3FC
0x18001d366  lea     r8, aModemCheckIsAl; "Modem check is already in 'Connect to I"...
0x18001d36d  jmp     loc_18001D3F3
0x18001d372  mov     rcx, rbx; this
0x18001d375  call    ?EnumerateRasModemDevices@CDialupConnectionRetryPage@@AEAAXXZ; CDialupConnectionRetryPage::EnumerateRasModemDevices(void)
0x18001d37a  cmp     dword ptr [rbx+70h], 1
0x18001d37e  mov     rcx, [rbx+60h]
0x18001d382  jnz     short loc_18001D3C1
0x18001d384  mov     r8, [rbx+68h]; unsigned __int16 *
0x18001d388  add     rcx, 1154h; unsigned __int16 *
0x18001d38f  mov     edx, 101h; unsigned __int64
0x18001d394  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d399  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d39f  cmp     ecx, r12d
0x18001d3a2  jz      short loc_18001D3FC
0x18001d3a4  mov     r9, [rbx+60h]
0x18001d3a8  lea     r8, aThereIsOnlyOne; "There is only one modem connected [%S] "...
0x18001d3af  add     r9, 1154h
0x18001d3b6  mov     edx, r13d; dwFlags
0x18001d3b9  call    cs:__imp_TracePrintfExA
0x18001d3bf  jmp     short loc_18001D3FC
0x18001d3c1  test    byte ptr [rcx+4], 4
0x18001d3c5  jz      short loc_18001D403
0x18001d3c7  cmp     dword ptr [rbx+70h], 0
0x18001d3cb  jnz     short loc_18001D403
0x18001d3cd  add     rcx, 1154h; void *
0x18001d3d4  xor     edx, edx; Val
0x18001d3d6  mov     r8d, 202h; Size
0x18001d3dc  call    memset_0
0x18001d3e1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d3e7  cmp     ecx, r12d
0x18001d3ea  jz      short loc_18001D3FC
0x18001d3ec  lea     r8, aThereAreNoMode; "There are no modems configured. Skippin"...
0x18001d3f3  mov     edx, r13d; dwFlags
0x18001d3f6  call    cs:__imp_TracePrintfExA
0x18001d3fc  xor     eax, eax
0x18001d3fe  jmp     loc_18001D505
0x18001d403  test    sil, 22h
0x18001d407  jz      loc_18001D491
0x18001d40d  mov     esi, 68h ; 'h'
0x18001d412  mov     ecx, esi; cb
0x18001d414  call    cs:__imp_CoTaskMemAlloc
0x18001d41a  mov     rdi, rax
0x18001d41d  test    rax, rax
0x18001d420  jz      short loc_18001D478
0x18001d422  lea     rcx, [rax+8]; void *
0x18001d426  xor     edx, edx; Val
0x18001d428  lea     r8d, [rsi-8]; Size
0x18001d42c  call    memset_0
0x18001d431  mov     [rdi], esi
0x18001d433  mov     dword ptr [rdi+4], 1000h
0x18001d43a  mov     rcx, cs:hInst
0x18001d441  mov     [rdi+8], rcx
0x18001d445  mov     [rdi+30h], rbx
0x18001d449  mov     qword ptr [rdi+10h], 6Eh ; 'n'
0x18001d451  mov     ecx, [rbx+70h]
0x18001d454  neg     ecx
0x18001d456  sbb     rax, rax
0x18001d459  neg     rax
0x18001d45c  add     rax, 0BD1h
0x18001d462  mov     [rdi+48h], rax
0x18001d466  xor     ebx, ebx
0x18001d468  lea     rax, ?PageDlgProc@CDialupConnectionRetryPage@@CAHPEAUHWND__@@I_K_J@Z; CDialupConnectionRetryPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001d46f  mov     [rdi+28h], rax
0x18001d473  mov     [r14], rdi
0x18001d476  jmp     short loc_18001D4E1
0x18001d478  mov     ecx, cs:g_dwTraceId
0x18001d47e  mov     ebx, 8007000Eh
0x18001d483  cmp     ecx, r12d
0x18001d486  jz      short loc_18001D4E1
0x18001d488  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001d48f  jmp     short loc_18001D4D5
0x18001d491  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d497  mov     ebx, 80004001h
0x18001d49c  cmp     ecx, r12d
0x18001d49f  jz      short loc_18001D4E1
0x18001d4a1  mov     [rsp+78h+var_50], ebx
0x18001d4a5  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001d4ac  mov     r9d, esi
0x18001d4af  mov     dword ptr [rsp+78h+var_58], esi
0x18001d4b3  mov     edx, r13d; dwFlags
0x18001d4b6  call    cs:__imp_TracePrintfExA
0x18001d4bc  jmp     short loc_18001D4E1
0x18001d4be  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d4c4  mov     ebx, 80004005h
0x18001d4c9  cmp     ecx, r12d
0x18001d4cc  jz      short loc_18001D4E1
0x18001d4ce  lea     r8, aUnableToGetRas_0; "Unable to get RasNcwInfo handle. hr = %"...
0x18001d4d5  mov     r9d, ebx
0x18001d4d8  mov     edx, r13d; dwFlags
0x18001d4db  call    cs:__imp_TracePrintfExA
0x18001d4e1  mov     eax, ebx
0x18001d4e3  jmp     short loc_18001D505
0x18001d4e5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d4eb  cmp     ecx, r12d
0x18001d4ee  jz      short loc_18001D503
0x18001d4f0  lea     r8, aHrensureproper; "HrEnsurePropertyBagAccess failed. hr = "...
0x18001d4f7  mov     r9d, edi
0x18001d4fa  mov     edx, r13d; dwFlags
0x18001d4fd  call    cs:__imp_TracePrintfExA
0x18001d503  mov     eax, edi
0x18001d505  add     rsp, 38h
0x18001d509  pop     r15
0x18001d50b  pop     r14
0x18001d50d  pop     r13
0x18001d50f  pop     r12
0x18001d511  pop     rdi
0x18001d512  pop     rsi
0x18001d513  pop     rbp
0x18001d514  pop     rbx
0x18001d515  retn
```
