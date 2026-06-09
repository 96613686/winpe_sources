# CCTWConnectionInfoPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180019ef0`
- end: `0x18001a12c`
- name: `?CanRunPage@CCTWConnectionInfoPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `572`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, int, int, __int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800114d8`
- `0x180019ef0`
- `0x18001a950`
- `0x18002f382`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001a0da`
- `rtutils!TracePrintfExA` at `0x18001a115`
- `rtutils!TracePrintfExA` at `0x18001a0da`
- `rtutils!TracePrintfExA` at `0x18001a115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a012`

## string_xrefs

- `0x18001a106`: `HrEnsurePropertyBagAccess failed. hr = %#x`

## pseudocode

```c
__int64 __fastcall CCTWConnectionInfoPage::CanRunPage(
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
  __int128 v11; // xmm0
  int v12; // ebx
  __int64 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // rax
  char *v17; // rbx

  *a9 = 0;
  v11 = *a2;
  *(_DWORD *)(a1 + 24) = a5;
  *(_OWORD *)(a1 + 8) = v11;
  *(_QWORD *)(a1 + 56) = a8;
  v12 = HrEnsureTearOffInterfaceLoaded(a8, &IID_IXWizardPropertyBag, a1 + 64);
  if ( v12 < 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "HrEnsurePropertyBagAccess failed. hr = %#x", (unsigned int)v12);
  }
  else
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, __int64, _QWORD))(**(_QWORD **)(a1 + 64) + 48LL))(
            *(_QWORD *)(a1 + 64),
            a1 + 8,
            L"RASConnectionDetails",
            a1 + 48,
            0);
    if ( v12 >= 0 )
    {
      v13 = *(__int64 **)(a1 + 48);
      if ( v13 && (v14 = *v13) != 0 )
      {
        *(_QWORD *)(a1 + 40) = v14;
        if ( (*(_BYTE *)(v14 + 4) & 4) == 0 )
        {
          if ( !*(_DWORD *)(a1 + 596) && *(_DWORD *)(v14 + 1812) )
            *(_DWORD *)(v14 + 1812) = 0;
          v15 = *(_QWORD *)(a1 + 40);
          *(_DWORD *)(a1 + 596) = 1;
          if ( *(_DWORD *)v15 == 2 )
          {
            CCTWConnectionInfoPage::ReadVPNInternetChkInfo((CCTWConnectionInfoPage *)a1);
          }
          else if ( !*(_WORD *)(v15 + 4436) )
          {
            *(_DWORD *)(a1 + 596) = 0;
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
            if ( *(_DWORD *)(a1 + 24) == 1 )
            {
              *((_QWORD *)v17 + 2) = 104;
              *((_QWORD *)v17 + 9) = 3126;
            }
            else if ( *(_DWORD *)(a1 + 24) == 2 )
            {
              *((_QWORD *)v17 + 2) = 100;
              *((_QWORD *)v17 + 9) = 3127;
              *(_DWORD *)(*(_QWORD *)(a1 + 40) + 2888LL) = 1;
              *(_DWORD *)(*(_QWORD *)(a1 + 40) + 4952LL) = 1;
            }
            *((_QWORD *)v17 + 5) = CCTWConnectionInfoPage::PageDlgProc;
            *a9 = v17;
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
        v12 = -2147467259;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Unable to get RasNcwInfo handle. hr = %#x", 2147500037LL);
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed to query property bag for rasncw. hr = %#x", (unsigned int)v12);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180019ef0  push    rbx
0x180019ef2  push    rbp
0x180019ef3  push    rsi
0x180019ef4  push    rdi
0x180019ef5  push    r12
0x180019ef7  push    r14
0x180019ef9  push    r15
0x180019efb  sub     rsp, 30h
0x180019eff  mov     eax, [rsp+68h+arg_20]
0x180019f06  mov     rdi, rcx
0x180019f09  mov     r15, [rsp+68h+arg_40]
0x180019f11  xor     r12d, r12d
0x180019f14  mov     esi, r9d
0x180019f17  lea     r8, [rdi+40h]
0x180019f1b  mov     [r15], r12
0x180019f1e  movups  xmm0, xmmword ptr [rdx]
0x180019f21  lea     rdx, IID_IXWizardPropertyBag
0x180019f28  mov     [rdi+18h], eax
0x180019f2b  movdqu  xmmword ptr [rcx+8], xmm0
0x180019f30  mov     rcx, [rsp+68h+arg_38]
0x180019f38  mov     [rdi+38h], rcx
0x180019f3c  call    HrEnsureTearOffInterfaceLoaded
0x180019f41  mov     ebx, eax
0x180019f43  test    eax, eax
0x180019f45  js      loc_18001A0FB
0x180019f4b  mov     rcx, [rdi+40h]
0x180019f4f  lea     r9, [rdi+30h]
0x180019f53  lea     r8, aRasconnectiond_2; "RASConnectionDetails"
0x180019f5a  mov     [rsp+68h+var_48], r12
0x180019f5f  lea     rdx, [rdi+8]
0x180019f63  mov     rax, [rcx]
0x180019f66  mov     rax, [rax+30h]
0x180019f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f6f  mov     ebx, eax
0x180019f71  test    eax, eax
0x180019f73  jns     short loc_180019F90
0x180019f75  mov     ecx, cs:g_dwTraceId
0x180019f7b  cmp     ecx, 0FFFFFFFFh
0x180019f7e  jz      loc_18001A11B
0x180019f84  lea     r8, aFailedToQueryP; "Failed to query property bag for rasncw"...
0x180019f8b  jmp     loc_18001A10D
0x180019f90  mov     rax, [rdi+30h]
0x180019f94  test    rax, rax
0x180019f97  jz      loc_18001A0E2
0x180019f9d  mov     rax, [rax]
0x180019fa0  test    rax, rax
0x180019fa3  jz      loc_18001A0E2
0x180019fa9  mov     [rdi+28h], rax
0x180019fad  mov     ebp, 1
0x180019fb2  test    byte ptr [rax+4], 4
0x180019fb6  jnz     short loc_18001A001
0x180019fb8  cmp     [rdi+254h], r12d
0x180019fbf  jnz     short loc_180019FD1
0x180019fc1  cmp     [rax+714h], r12d
0x180019fc8  jz      short loc_180019FD1
0x180019fca  mov     [rax+714h], r12d
0x180019fd1  mov     rax, [rdi+28h]
0x180019fd5  mov     [rdi+254h], ebp
0x180019fdb  cmp     dword ptr [rax], 2
0x180019fde  jnz     short loc_180019FEA
0x180019fe0  mov     rcx, rdi; this
0x180019fe3  call    ?ReadVPNInternetChkInfo@CCTWConnectionInfoPage@@AEAAXXZ; CCTWConnectionInfoPage::ReadVPNInternetChkInfo(void)
0x180019fe8  jmp     short loc_18001A001
0x180019fea  cmp     [rax+1154h], r12w
0x180019ff2  jnz     short loc_18001A001
0x180019ff4  mov     [rdi+254h], r12d
0x180019ffb  mov     [rax+714h], ebp
0x18001a001  test    sil, 22h
0x18001a005  jz      loc_18001A0B3
0x18001a00b  mov     esi, 68h ; 'h'
0x18001a010  mov     ecx, esi; cb
0x18001a012  call    cs:__imp_CoTaskMemAlloc
0x18001a018  mov     rbx, rax
0x18001a01b  test    rax, rax
0x18001a01e  jz      short loc_18001A09A
0x18001a020  lea     rcx, [rax+8]; void *
0x18001a024  xor     edx, edx; Val
0x18001a026  lea     r8d, [rsi-8]; Size
0x18001a02a  call    memset_0
0x18001a02f  mov     [rbx], esi
0x18001a031  mov     dword ptr [rbx+4], 1000h
0x18001a038  mov     rcx, cs:hInst
0x18001a03f  mov     [rbx+8], rcx
0x18001a043  mov     [rbx+30h], rdi
0x18001a047  cmp     [rdi+18h], ebp
0x18001a04a  jnz     short loc_18001A05A
0x18001a04c  mov     [rbx+10h], rsi
0x18001a050  mov     qword ptr [rbx+48h], 0C36h
0x18001a058  jmp     short loc_18001A084
0x18001a05a  cmp     dword ptr [rdi+18h], 2
0x18001a05e  jnz     short loc_18001A084
0x18001a060  mov     qword ptr [rbx+10h], 64h ; 'd'
0x18001a068  mov     qword ptr [rbx+48h], 0C37h
0x18001a070  mov     rax, [rdi+28h]
0x18001a074  mov     [rax+0B48h], ebp
0x18001a07a  mov     rax, [rdi+28h]
0x18001a07e  mov     [rax+1358h], ebp
0x18001a084  lea     rax, ?PageDlgProc@CCTWConnectionInfoPage@@CAHPEAUHWND__@@I_K_J@Z; CCTWConnectionInfoPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001a08b  mov     [rbx+28h], rax
0x18001a08f  mov     [r15], rbx
0x18001a092  mov     ebx, r12d
0x18001a095  jmp     loc_18001A11B
0x18001a09a  mov     ecx, cs:g_dwTraceId
0x18001a0a0  mov     ebx, 8007000Eh
0x18001a0a5  cmp     ecx, 0FFFFFFFFh
0x18001a0a8  jz      short loc_18001A11B
0x18001a0aa  lea     r8, aUnableToAlloca; "Unable to allocate memory for PROPSHEET"...
0x18001a0b1  jmp     short loc_18001A10D
0x18001a0b3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001a0b9  mov     ebx, 80004001h
0x18001a0be  cmp     ecx, 0FFFFFFFFh
0x18001a0c1  jz      short loc_18001A11B
0x18001a0c3  mov     [rsp+68h+var_40], ebx
0x18001a0c7  lea     r8, aUnsupportedWiz; "Unsupported wizard type %d [%#x] reques"...
0x18001a0ce  mov     r9d, esi
0x18001a0d1  mov     dword ptr [rsp+68h+var_48], esi
0x18001a0d5  mov     edx, 0Ch; dwFlags
0x18001a0da  call    cs:__imp_TracePrintfExA
0x18001a0e0  jmp     short loc_18001A11B
0x18001a0e2  mov     ecx, cs:g_dwTraceId
0x18001a0e8  mov     ebx, 80004005h
0x18001a0ed  cmp     ecx, 0FFFFFFFFh
0x18001a0f0  jz      short loc_18001A11B
0x18001a0f2  lea     r8, aUnableToGetRas_0; "Unable to get RasNcwInfo handle. hr = %"...
0x18001a0f9  jmp     short loc_18001A10D
0x18001a0fb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001a101  cmp     ecx, 0FFFFFFFFh
0x18001a104  jz      short loc_18001A11B
0x18001a106  lea     r8, aHrensureproper; "HrEnsurePropertyBagAccess failed. hr = "...
0x18001a10d  mov     r9d, ebx
0x18001a110  mov     edx, 0Ch; dwFlags
0x18001a115  call    cs:__imp_TracePrintfExA
0x18001a11b  mov     eax, ebx
0x18001a11d  add     rsp, 30h
0x18001a121  pop     r15
0x18001a123  pop     r14
0x18001a125  pop     r12
0x18001a127  pop     rdi
0x18001a128  pop     rsi
0x18001a129  pop     rbp
0x18001a12a  pop     rbx
0x18001a12b  retn
```
