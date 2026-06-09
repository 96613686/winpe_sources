# CCTIConnectionInfoPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180012c70`
- end: `0x180012ecb`
- name: `?CanRunPage@CCTIConnectionInfoPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `603`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, int, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x180012c70`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180012d95`
- `rtutils!TracePrintfExA` at `0x180012e73`
- `rtutils!TracePrintfExA` at `0x180012eb2`
- `rtutils!TracePrintfExA` at `0x180012d95`
- `rtutils!TracePrintfExA` at `0x180012e73`
- `rtutils!TracePrintfExA` at `0x180012eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012db7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012db7`

## string_xrefs

- `0x180012d8b`: `ReadSkipTestingFlag:c_szSkipConnectionTesting:SkipTesting:%d`
- `0x180012ea3`: `HrEnsurePropertyBagAccess failed. hr = %#x`

## pseudocode

```c
__int64 __fastcall CCTIConnectionInfoPage::CanRunPage(
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
  _QWORD *v12; // r15
  int v13; // ebx
  __int64 *v14; // rax
  __int64 v15; // rax
  char *v16; // rax
  char *v17; // rbx
  int v18; // eax

  *a9 = 0;
  v12 = (_QWORD *)(a1 + 40);
  *(_OWORD *)(a1 + 8) = *a2;
  *(_QWORD *)(a1 + 32) = a8;
  v13 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 40);
  if ( v13 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrEnsurePropertyBagAccess failed. hr = %#x", (unsigned int)v13);
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)*v12 + 48LL))(
            *v12,
            a1 + 8,
            L"RASConnectionDetails",
            a1 + 48,
            0);
    if ( v13 >= 0 )
    {
      v14 = *(__int64 **)(a1 + 48);
      if ( v14 && (v15 = *v14) != 0 )
      {
        *(_QWORD *)(a1 + 56) = v15;
        if ( (*(_BYTE *)(v15 + 4) & 4) == 0 )
        {
          if ( *(_DWORD *)v15 != 1 || *(_WORD *)(v15 + 4436) )
          {
            if ( !(*(unsigned int (__fastcall **)(_QWORD, _OWORD *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)*v12 + 48LL))(
                    *v12,
                    a2,
                    L"SkipConnectionTesting",
                    0,
                    0)
              && g_dwTraceId != -1 )
            {
              TracePrintfExA(g_dwTraceId, 0xCu, "ReadSkipTestingFlag:c_szSkipConnectionTesting:SkipTesting:%d", 0);
            }
            *(_DWORD *)(*(_QWORD *)(a1 + 56) + 1812LL) = 0;
          }
          else
          {
            *(_DWORD *)(v15 + 1812) = 1;
          }
        }
        if ( (a4 & 0x22) != 0 )
        {
          v16 = (char *)CoTaskMemAlloc(0x68u);
          v17 = v16;
          if ( v16 )
          {
            memset_0(v16 + 8, 0, 0x60u);
            *(_DWORD *)v17 = 104;
            *((_DWORD *)v17 + 1) = 4096;
            *((_QWORD *)v17 + 1) = hInst;
            *((_QWORD *)v17 + 6) = a1;
            v18 = *(_DWORD *)(a1 + 584);
            if ( v18 == 5 )
            {
              *((_QWORD *)v17 + 2) = 121;
              *((_QWORD *)v17 + 9) = 3028;
            }
            else if ( v18 == 1 )
            {
              *((_QWORD *)v17 + 2) = 111;
              *((_QWORD *)v17 + 9) = 3027;
            }
            *((_QWORD *)v17 + 5) = CCTIConnectionInfoPage::PageDlgProc;
            *a9 = v17;
            return 0;
          }
          else
          {
            v13 = -2147024882;
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
          v13 = -2147467263;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(
              g_dwTraceId,
              0xCu,
              "Unsupported wizard type %d [%#x] requested. hr = %#x",
              a4,
              a4,
              -2147467263);
        }
      }
      else
      {
        v13 = -2147467259;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Unable to get RasNcwInfo handle. hr = %#x", 2147500037LL);
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed to query property bag for rasncw. hr = %#x", (unsigned int)v13);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180012c70  push    rbx
0x180012c72  push    rbp
0x180012c73  push    rsi
0x180012c74  push    rdi
0x180012c75  push    r12
0x180012c77  push    r13
0x180012c79  push    r14
0x180012c7b  push    r15
0x180012c7d  sub     rsp, 38h
0x180012c81  mov     r12, [rsp+78h+arg_40]
0x180012c89  mov     rsi, rcx
0x180012c8c  mov     r13, rdx
0x180012c8f  mov     ebp, r9d
0x180012c92  mov     qword ptr [r12], 0
0x180012c9a  lea     r15, [rsi+28h]
0x180012c9e  movups  xmm0, xmmword ptr [rdx]
0x180012ca1  mov     r8, r15
0x180012ca4  lea     rdx, IID_IXWizardPropertyBag
0x180012cab  movdqu  xmmword ptr [rcx+8], xmm0
0x180012cb0  mov     rcx, [rsp+78h+arg_38]
0x180012cb8  mov     [rsi+20h], rcx
0x180012cbc  call    HrEnsureTearOffInterfaceLoaded
0x180012cc1  mov     ebx, eax
0x180012cc3  test    eax, eax
0x180012cc5  js      loc_180012E96
0x180012ccb  mov     rcx, [r15]
0x180012cce  lea     r9, [rsi+30h]
0x180012cd2  lea     r8, aRasconnectiond; "RASConnectionDetails"
0x180012cd9  mov     [rsp+78h+var_58], 0
0x180012ce2  lea     rdx, [rsi+8]
0x180012ce6  mov     rax, [rcx]
0x180012ce9  mov     rax, [rax+30h]
0x180012ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf2  xor     r14d, r14d
0x180012cf5  mov     ebx, eax
0x180012cf7  test    eax, eax
0x180012cf9  jns     short loc_180012D18
0x180012cfb  mov     ecx, cs:g_dwTraceId
0x180012d01  or      edi, 0FFFFFFFFh
0x180012d04  cmp     ecx, edi
0x180012d06  jz      loc_180012EB8
0x180012d0c  lea     r8, aFailedToQueryP; "Failed to query property bag for rasncw"...
0x180012d13  jmp     loc_180012EAA
0x180012d18  mov     rax, [rsi+30h]
0x180012d1c  test    rax, rax
0x180012d1f  jz      loc_180012E7B
0x180012d25  mov     rax, [rax]
0x180012d28  test    rax, rax
0x180012d2b  jz      loc_180012E7B
0x180012d31  or      edi, 0FFFFFFFFh
0x180012d34  mov     [rsi+38h], rax
0x180012d38  test    byte ptr [rax+4], 4
0x180012d3c  jnz     short loc_180012DA6
0x180012d3e  cmp     dword ptr [rax], 1
0x180012d41  jnz     short loc_180012D59
0x180012d43  cmp     [rax+1154h], r14w
0x180012d4b  jnz     short loc_180012D59
0x180012d4d  mov     dword ptr [rax+714h], 1
0x180012d57  jmp     short loc_180012DA6
0x180012d59  mov     rcx, [r15]
0x180012d5c  lea     r8, aSkipconnection_1; "SkipConnectionTesting"
0x180012d63  xor     r9d, r9d
0x180012d66  mov     [rsp+78h+var_58], r14
0x180012d6b  mov     rdx, r13
0x180012d6e  mov     rax, [rcx]
0x180012d71  mov     rax, [rax+30h]
0x180012d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d7a  test    eax, eax
0x180012d7c  jnz     short loc_180012D9B
0x180012d7e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012d84  cmp     ecx, edi
0x180012d86  jz      short loc_180012D9B
0x180012d88  xor     r9d, r9d
0x180012d8b  lea     r8, aReadskiptestin; "ReadSkipTestingFlag:c_szSkipConnectionT"...
0x180012d92  lea     edx, [rax+0Ch]; dwFlags
0x180012d95  call    cs:__imp_TracePrintfExA
0x180012d9b  mov     rax, [rsi+38h]
0x180012d9f  mov     [rax+714h], r14d
0x180012da6  test    bpl, 22h
0x180012daa  jz      loc_180012E4D
0x180012db0  mov     ebp, 68h ; 'h'
0x180012db5  mov     ecx, ebp; cb
0x180012db7  call    cs:__imp_CoTaskMemAlloc
0x180012dbd  mov     rbx, rax
0x180012dc0  test    rax, rax
0x180012dc3  jz      short loc_180012E35
0x180012dc5  lea     rcx, [rax+8]; void *
0x180012dc9  xor     edx, edx; Val
0x180012dcb  lea     r8d, [rbp-8]; Size
0x180012dcf  call    memset_0
0x180012dd4  mov     [rbx], ebp
0x180012dd6  mov     dword ptr [rbx+4], 1000h
0x180012ddd  mov     rcx, cs:hInst
0x180012de4  mov     [rbx+8], rcx
0x180012de8  mov     [rbx+30h], rsi
0x180012dec  mov     eax, [rsi+248h]
0x180012df2  cmp     eax, 5
0x180012df5  jnz     short loc_180012E09
0x180012df7  mov     qword ptr [rbx+10h], 79h ; 'y'
0x180012dff  mov     qword ptr [rbx+48h], 0BD4h
0x180012e07  jmp     short loc_180012E1E
0x180012e09  cmp     eax, 1
0x180012e0c  jnz     short loc_180012E1E
0x180012e0e  mov     qword ptr [rbx+10h], 6Fh ; 'o'
0x180012e16  mov     qword ptr [rbx+48h], 0BD3h
0x180012e1e  lea     rax, ?PageDlgProc@CCTIConnectionInfoPage@@CAHPEAUHWND__@@I_K_J@Z; CCTIConnectionInfoPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180012e25  mov     [rbx+28h], rax
0x180012e29  mov     [r12], rbx
0x180012e2d  mov     ebx, r14d
0x180012e30  jmp     loc_180012EB8
0x180012e35  mov     ecx, cs:g_dwTraceId
0x180012e3b  mov     ebx, 8007000Eh
0x180012e40  cmp     ecx, edi
0x180012e42  jz      short loc_180012EB8
0x180012e44  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x180012e4b  jmp     short loc_180012EAA
0x180012e4d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012e53  mov     ebx, 80004001h
0x180012e58  cmp     ecx, edi
0x180012e5a  jz      short loc_180012EB8
0x180012e5c  mov     [rsp+78h+var_50], ebx
0x180012e60  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x180012e67  mov     r9d, ebp
0x180012e6a  mov     dword ptr [rsp+78h+var_58], ebp
0x180012e6e  mov     edx, 0Ch; dwFlags
0x180012e73  call    cs:__imp_TracePrintfExA
0x180012e79  jmp     short loc_180012EB8
0x180012e7b  mov     ecx, cs:g_dwTraceId
0x180012e81  or      edi, 0FFFFFFFFh
0x180012e84  mov     ebx, 80004005h
0x180012e89  cmp     ecx, edi
0x180012e8b  jz      short loc_180012EB8
0x180012e8d  lea     r8, aUnableToGetRas_0; "Unable to get RasNcwInfo handle. hr = %"...
0x180012e94  jmp     short loc_180012EAA
0x180012e96  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012e9c  or      edi, 0FFFFFFFFh
0x180012e9f  cmp     ecx, edi
0x180012ea1  jz      short loc_180012EB8
0x180012ea3  lea     r8, aHrensureproper; "HrEnsurePropertyBagAccess failed. hr = "...
0x180012eaa  mov     r9d, ebx
0x180012ead  mov     edx, 0Ch; dwFlags
0x180012eb2  call    cs:__imp_TracePrintfExA
0x180012eb8  mov     eax, ebx
0x180012eba  add     rsp, 38h
0x180012ebe  pop     r15
0x180012ec0  pop     r14
0x180012ec2  pop     r13
0x180012ec4  pop     r12
0x180012ec6  pop     rdi
0x180012ec7  pop     rsi
0x180012ec8  pop     rbp
0x180012ec9  pop     rbx
0x180012eca  retn
```
