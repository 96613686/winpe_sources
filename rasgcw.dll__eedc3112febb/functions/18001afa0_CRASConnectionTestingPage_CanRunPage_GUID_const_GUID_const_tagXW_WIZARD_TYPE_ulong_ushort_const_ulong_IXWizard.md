# CRASConnectionTestingPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18001afa0`
- end: `0x18001b0dd`
- name: `?CanRunPage@CRASConnectionTestingPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x18001afa0`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001b0a9`
- `rtutils!TracePrintfExA` at `0x18001b0cb`
- `rtutils!TracePrintfExA` at `0x18001b0a9`
- `rtutils!TracePrintfExA` at `0x18001b0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b002`

## pseudocode

```c
__int64 __fastcall CRASConnectionTestingPage::CanRunPage(
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
  *(_DWORD *)(a1 + 40) = a4;
  *(_OWORD *)(a1 + 44) = *a2;
  *(_QWORD *)(a1 + 72) = a8;
  v11 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 80);
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
      *((_QWORD *)v14 + 2) = 126;
      *((_QWORD *)v14 + 9) = (*(_DWORD *)(a1 + 60) != 0) + 3037LL;
      *((_QWORD *)v14 + 5) = CRASConnectionTestingPage::PageDlgProc;
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
0x18001afa0  push    rbx
0x18001afa2  push    rsi
0x18001afa3  push    rdi
0x18001afa4  push    r14
0x18001afa6  sub     rsp, 38h
0x18001afaa  mov     r14, [rsp+58h+arg_40]
0x18001afb2  mov     rsi, rcx
0x18001afb5  mov     edi, r9d
0x18001afb8  mov     qword ptr [r14], 0
0x18001afbf  lea     r8, [rsi+50h]
0x18001afc3  mov     [rcx+28h], r9d
0x18001afc7  movups  xmm0, xmmword ptr [rdx]
0x18001afca  lea     rdx, IID_IXWizardPropertyBag
0x18001afd1  movdqu  xmmword ptr [rcx+2Ch], xmm0
0x18001afd6  mov     rcx, [rsp+58h+arg_38]
0x18001afde  mov     [rsi+48h], rcx
0x18001afe2  call    HrEnsureTearOffInterfaceLoaded
0x18001afe7  mov     ebx, eax
0x18001afe9  test    eax, eax
0x18001afeb  js      loc_18001B0B1
0x18001aff1  test    dil, 22h
0x18001aff5  jz      loc_18001B082
0x18001affb  mov     edi, 68h ; 'h'
0x18001b000  mov     ecx, edi; cb
0x18001b002  call    cs:__imp_CoTaskMemAlloc
0x18001b008  mov     rbx, rax
0x18001b00b  test    rax, rax
0x18001b00e  jz      short loc_18001B066
0x18001b010  lea     rcx, [rax+8]; void *
0x18001b014  xor     edx, edx; Val
0x18001b016  lea     r8d, [rdi-8]; Size
0x18001b01a  call    memset_0
0x18001b01f  mov     [rbx], edi
0x18001b021  mov     dword ptr [rbx+4], 1000h
0x18001b028  mov     rcx, cs:hInst
0x18001b02f  mov     [rbx+8], rcx
0x18001b033  mov     [rbx+30h], rsi
0x18001b037  mov     qword ptr [rbx+10h], 7Eh ; '~'
0x18001b03f  mov     ecx, [rsi+3Ch]
0x18001b042  neg     ecx
0x18001b044  sbb     rax, rax
0x18001b047  neg     rax
0x18001b04a  add     rax, 0BDDh
0x18001b050  mov     [rbx+48h], rax
0x18001b054  lea     rax, ?PageDlgProc@CRASConnectionTestingPage@@KAHPEAUHWND__@@I_K_J@Z; CRASConnectionTestingPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001b05b  mov     [rbx+28h], rax
0x18001b05f  mov     [r14], rbx
0x18001b062  xor     ebx, ebx
0x18001b064  jmp     short loc_18001B0D1
0x18001b066  mov     ecx, cs:g_dwTraceId
0x18001b06c  mov     ebx, 8007000Eh
0x18001b071  cmp     ecx, 0FFFFFFFFh
0x18001b074  jz      short loc_18001B0D1
0x18001b076  mov     r9d, ebx
0x18001b079  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001b080  jmp     short loc_18001B0C6
0x18001b082  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b088  mov     ebx, 80004001h
0x18001b08d  cmp     ecx, 0FFFFFFFFh
0x18001b090  jz      short loc_18001B0D1
0x18001b092  mov     [rsp+58h+var_30], ebx
0x18001b096  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001b09d  mov     r9d, edi
0x18001b0a0  mov     [rsp+58h+var_38], edi
0x18001b0a4  mov     edx, 0Ch; dwFlags
0x18001b0a9  call    cs:__imp_TracePrintfExA
0x18001b0af  jmp     short loc_18001B0D1
0x18001b0b1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b0b7  cmp     ecx, 0FFFFFFFFh
0x18001b0ba  jz      short loc_18001B0D1
0x18001b0bc  mov     r9d, eax
0x18001b0bf  lea     r8, aFailedToInitia_0; "Failed to initialize the page. hr = %#x"
0x18001b0c6  mov     edx, 0Ch; dwFlags
0x18001b0cb  call    cs:__imp_TracePrintfExA
0x18001b0d1  mov     eax, ebx
0x18001b0d3  add     rsp, 38h
0x18001b0d7  pop     r14
0x18001b0d9  pop     rdi
0x18001b0da  pop     rsi
0x18001b0db  pop     rbx
0x18001b0dc  retn
```
