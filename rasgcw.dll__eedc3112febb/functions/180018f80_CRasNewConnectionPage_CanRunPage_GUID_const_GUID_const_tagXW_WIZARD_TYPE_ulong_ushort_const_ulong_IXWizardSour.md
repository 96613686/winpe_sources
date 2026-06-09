# CRasNewConnectionPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180018f80`
- end: `0x180019072`
- name: `?CanRunPage@CRasNewConnectionPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018f80`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180019033`
- `rtutils!TracePrintfExA` at `0x180019060`
- `rtutils!TracePrintfExA` at `0x180019033`
- `rtutils!TracePrintfExA` at `0x180019060`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018fbb`

## pseudocode

```c
__int64 __fastcall CRasNewConnectionPage::CanRunPage(
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
  unsigned int v9; // edi
  __int128 v11; // xmm0
  char *v12; // rax
  char *v13; // rbx

  v9 = 0;
  *a9 = 0;
  v11 = *a2;
  *(_QWORD *)(a1 + 80) = a8;
  *(_OWORD *)(a1 + 64) = v11;
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
      *((_QWORD *)v13 + 5) = CRasNewConnectionPage::PageDlgProc;
      *((_QWORD *)v13 + 6) = a1;
      *((_QWORD *)v13 + 2) = 140;
      *((_QWORD *)v13 + 9) = 3065;
      *a9 = v13;
    }
    else
    {
      v9 = -2147024882;
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
    v9 = -2147467263;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unsupported wizard type %d [%#x] requested. hr = %#x", a4, a4, -2147467263);
  }
  return v9;
}

```

## disassembly

```asm
0x180018f80  push    rbx
0x180018f82  push    rsi
0x180018f83  push    rdi
0x180018f84  push    r14
0x180018f86  sub     rsp, 38h
0x180018f8a  mov     r14, [rsp+58h+arg_40]
0x180018f92  xor     edi, edi
0x180018f94  mov     rax, [rsp+58h+arg_38]
0x180018f9c  mov     rsi, rcx
0x180018f9f  mov     [r14], rdi
0x180018fa2  movups  xmm0, xmmword ptr [rdx]
0x180018fa5  mov     [rcx+50h], rax
0x180018fa9  movdqu  xmmword ptr [rcx+40h], xmm0
0x180018fae  test    r9b, 22h
0x180018fb2  jz      loc_18001903B
0x180018fb8  lea     ecx, [rdi+68h]; cb
0x180018fbb  call    cs:__imp_CoTaskMemAlloc
0x180018fc1  mov     rbx, rax
0x180018fc4  test    rax, rax
0x180018fc7  jz      short loc_180019014
0x180018fc9  lea     rcx, [rax+8]; void *
0x180018fcd  xor     edx, edx; Val
0x180018fcf  lea     r8d, [rdi+60h]; Size
0x180018fd3  call    memset_0
0x180018fd8  mov     dword ptr [rbx], 68h ; 'h'
0x180018fde  lea     rax, ?PageDlgProc@CRasNewConnectionPage@@CAHPEAUHWND__@@I_K_J@Z; CRasNewConnectionPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180018fe5  mov     dword ptr [rbx+4], 1000h
0x180018fec  mov     rcx, cs:hInst
0x180018ff3  mov     [rbx+8], rcx
0x180018ff7  mov     [rbx+28h], rax
0x180018ffb  mov     [rbx+30h], rsi
0x180018fff  mov     qword ptr [rbx+10h], 8Ch
0x180019007  mov     qword ptr [rbx+48h], 0BF9h
0x18001900f  mov     [r14], rbx
0x180019012  jmp     short loc_180019066
0x180019014  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001901a  mov     edi, 8007000Eh
0x18001901f  cmp     ecx, 0FFFFFFFFh
0x180019022  jz      short loc_180019066
0x180019024  mov     r9d, edi
0x180019027  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001902e  mov     edx, 0Ch; dwFlags
0x180019033  call    cs:__imp_TracePrintfExA
0x180019039  jmp     short loc_180019066
0x18001903b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180019041  mov     edi, 80004001h
0x180019046  cmp     ecx, 0FFFFFFFFh
0x180019049  jz      short loc_180019066
0x18001904b  mov     [rsp+58h+var_30], edi
0x18001904f  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x180019056  mov     edx, 0Ch; dwFlags
0x18001905b  mov     [rsp+58h+var_38], r9d
0x180019060  call    cs:__imp_TracePrintfExA
0x180019066  mov     eax, edi
0x180019068  add     rsp, 38h
0x18001906c  pop     r14
0x18001906e  pop     rdi
0x18001906f  pop     rsi
0x180019070  pop     rbx
0x180019071  retn
```
