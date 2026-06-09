# CRASConnectionFinishPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180018170`
- end: `0x1800182b3`
- name: `?CanRunPage@CRASConnectionFinishPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `323`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x180018170`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001827f`
- `rtutils!TracePrintfExA` at `0x1800182a1`
- `rtutils!TracePrintfExA` at `0x18001827f`
- `rtutils!TracePrintfExA` at `0x1800182a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800181d8`

## pseudocode

```c
__int64 __fastcall CRASConnectionFinishPage::CanRunPage(
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
  int v11; // eax
  unsigned int v12; // ebx
  char *v13; // rax
  char *v14; // rbx

  *a9 = 0;
  *(_DWORD *)(a1 + 116) = a4;
  *(_OWORD *)(a1 + 120) = *a2;
  *(_QWORD *)(a1 + 152) = a8;
  v11 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 160);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed to initialize the page. hr = %#x", (unsigned int)v11);
  }
  else if ( (a4 & 0x22) != 0 )
  {
    v13 = (char *)CoTaskMemAlloc(0x68u);
    v14 = v13;
    if ( v13 )
    {
      memset_0(v13 + 8, 0, 0x60u);
      *(_DWORD *)v14 = 104;
      *((_DWORD *)v14 + 1) = 4096;
      *((_QWORD *)v14 + 1) = hInst;
      *((_QWORD *)v14 + 6) = a1;
      *((_QWORD *)v14 + 2) = 151;
      *((_QWORD *)v14 + 9) = 3229LL - (*(_DWORD *)(a1 + 136) != 0);
      *((_QWORD *)v14 + 5) = CRASConnectionFinishPage::PageDlgProc;
      *a9 = v14;
      return 0;
    }
    else
    {
      v12 = -2147024882;
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
    v12 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v12;
}

```

## disassembly

```asm
0x180018170  push    rbx
0x180018172  push    rsi
0x180018173  push    rdi
0x180018174  push    r14
0x180018176  sub     rsp, 38h
0x18001817a  mov     r14, [rsp+58h+arg_40]
0x180018182  mov     rsi, rcx
0x180018185  mov     edi, r9d
0x180018188  mov     qword ptr [r14], 0
0x18001818f  lea     r8, [rsi+0A0h]
0x180018196  mov     [rcx+74h], r9d
0x18001819a  movups  xmm0, xmmword ptr [rdx]
0x18001819d  lea     rdx, IID_IXWizardPropertyBag
0x1800181a4  movdqu  xmmword ptr [rcx+78h], xmm0
0x1800181a9  mov     rcx, [rsp+58h+arg_38]
0x1800181b1  mov     [rsi+98h], rcx
0x1800181b8  call    HrEnsureTearOffInterfaceLoaded
0x1800181bd  mov     ebx, eax
0x1800181bf  test    eax, eax
0x1800181c1  js      loc_180018287
0x1800181c7  test    dil, 22h
0x1800181cb  jz      loc_180018258
0x1800181d1  mov     edi, 68h ; 'h'
0x1800181d6  mov     ecx, edi; cb
0x1800181d8  call    cs:__imp_CoTaskMemAlloc
0x1800181de  mov     rbx, rax
0x1800181e1  test    rax, rax
0x1800181e4  jz      short loc_18001823C
0x1800181e6  lea     rcx, [rax+8]; void *
0x1800181ea  xor     edx, edx; Val
0x1800181ec  lea     r8d, [rdi-8]; Size
0x1800181f0  call    memset_0
0x1800181f5  mov     [rbx], edi
0x1800181f7  mov     dword ptr [rbx+4], 1000h
0x1800181fe  mov     rcx, cs:hInst
0x180018205  mov     [rbx+8], rcx
0x180018209  mov     [rbx+30h], rsi
0x18001820d  mov     qword ptr [rbx+10h], 97h
0x180018215  mov     ecx, [rsi+88h]
0x18001821b  neg     ecx
0x18001821d  sbb     rax, rax
0x180018220  add     rax, 0C9Dh
0x180018226  mov     [rbx+48h], rax
0x18001822a  lea     rax, ?PageDlgProc@CRASConnectionFinishPage@@KAHPEAUHWND__@@I_K_J@Z; CRASConnectionFinishPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180018231  mov     [rbx+28h], rax
0x180018235  mov     [r14], rbx
0x180018238  xor     ebx, ebx
0x18001823a  jmp     short loc_1800182A7
0x18001823c  mov     ecx, cs:g_dwTraceId
0x180018242  mov     ebx, 8007000Eh
0x180018247  cmp     ecx, 0FFFFFFFFh
0x18001824a  jz      short loc_1800182A7
0x18001824c  mov     r9d, ebx
0x18001824f  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x180018256  jmp     short loc_18001829C
0x180018258  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001825e  mov     ebx, 80004001h
0x180018263  cmp     ecx, 0FFFFFFFFh
0x180018266  jz      short loc_1800182A7
0x180018268  mov     [rsp+58h+var_30], ebx
0x18001826c  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x180018273  mov     r9d, edi
0x180018276  mov     [rsp+58h+var_38], edi
0x18001827a  mov     edx, 0Ch; dwFlags
0x18001827f  call    cs:__imp_TracePrintfExA
0x180018285  jmp     short loc_1800182A7
0x180018287  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001828d  cmp     ecx, 0FFFFFFFFh
0x180018290  jz      short loc_1800182A7
0x180018292  mov     r9d, eax
0x180018295  lea     r8, aFailedToInitia_0; "Failed to initialize the page. hr = %#x"
0x18001829c  mov     edx, 0Ch; dwFlags
0x1800182a1  call    cs:__imp_TracePrintfExA
0x1800182a7  mov     eax, ebx
0x1800182a9  add     rsp, 38h
0x1800182ad  pop     r14
0x1800182af  pop     rdi
0x1800182b0  pop     rsi
0x1800182b1  pop     rbx
0x1800182b2  retn
```
