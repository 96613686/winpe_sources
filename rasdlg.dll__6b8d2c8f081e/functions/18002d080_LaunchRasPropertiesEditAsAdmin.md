# LaunchRasPropertiesEditAsAdmin

- ea: `0x18002d080`
- end: `0x18002d27e`
- name: `LaunchRasPropertiesEditAsAdmin`
- size: `510`
- prototype: `void __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014b40`

## callees

- `0x18002ca9c`
- `0x18002ccf4`
- `0x18002d080`
- `0x18002d284`
- `0x18003bea0`
- `0x18003c860`
- `0x18003ce6c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d250`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d250`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d0c0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d0c0`
- `RASAPI32!ReadPhonebookFile` at `0x18002d1bf`
- `RASAPI32!ReadPhonebookFile` at `0x18002d1bf`
- `RASAPI32!ClosePhonebookFile` at `0x18002d1a3`
- `RASAPI32!ClosePhonebookFile` at `0x18002d1a3`
- `rtutils!TracePrintfExA` at `0x18002d15a`
- `rtutils!TracePrintfExA` at `0x18002d22b`
- `rtutils!TracePrintfExA` at `0x18002d15a`
- `rtutils!TracePrintfExA` at `0x18002d22b`

## pseudocode

```c
void __fastcall LaunchRasPropertiesEditAsAdmin(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v6; // esi
  HRESULT v9; // eax
  struct _GUID *v10; // rdx
  const struct _GUID *v11; // r8
  int v12; // ecx
  HRESULT v13; // r14d
  int v14; // eax
  DWORD v15; // edi
  int v16; // eax
  unsigned __int16 v17; // di
  __int64 v18; // rdi
  __int64 v19; // rbp
  DWORD PhonebookFile; // eax
  int v21[2]; // [rsp+20h] [rbp-2A8h]
  void *v22; // [rsp+40h] [rbp-288h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-278h] BYREF
  int v24; // [rsp+60h] [rbp-268h]
  wchar_t v25[258]; // [rsp+6Ch] [rbp-25Ch] BYREF
  int v26; // [rsp+270h] [rbp-58h]

  v22 = 0;
  v6 = 0;
  v9 = CoInitializeEx(0, 6u);
  v12 = 0;
  v13 = v9;
  if ( v9 != -2147417850 )
    v12 = v9;
  if ( v12 >= 0 )
  {
    v14 = NtlCoCreateInstanceAsNetConfigOpOrAdmin(*(HWND *)(a3 + 4), v10, v11, &v22);
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get IRasDlgAdminOrNCO interface. hr = %#x", v14);
      if ( v15 != -2147023673 )
      {
        v6 = (unsigned __int16)v15;
        ThrowErrorBox(*(HWND *)(a3 + 4), v15);
      }
    }
    else
    {
      memset_0(v23, 0, 0x228u);
      CopyRasEntryDlgStruct((__int64)v23, a3, 0);
      v24 &= ~0x40000000u;
      v16 = (*(__int64 (__fastcall **)(void *, __int64, __int64, _BYTE *, _DWORD *))(*(_QWORD *)v22 + 24LL))(
              v22,
              a1,
              a2,
              v23,
              a4);
      v17 = v16;
      if ( v16 >= 0 )
      {
        if ( *a4 )
        {
          StringCchCopyWrapW((wchar_t *)(a3 + 24), 0x101u, v25);
          v18 = *(_QWORD *)(a3 + 544);
          if ( v18 )
          {
            v19 = StrDup(**(STRSAFE_LPCWSTR **)(v18 + 8));
            ClosePhonebookFile(*(_QWORD *)(v18 + 8));
            *(_QWORD *)v21 = *(_QWORD *)(v18 + 8);
            PhonebookFile = ReadPhonebookFile(v19, *(_QWORD *)(v18 + 16), 0, 0);
            if ( PhonebookFile )
              ErrorDlgUtil(*(HWND *)(a3 + 4), 0x141u, PhonebookFile, v21[0], 0x169u, 0xFAu);
            Free0(v19);
          }
        }
        else
        {
          v6 = v26;
        }
      }
      else
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "Failed to make call LaunchRasPropertiesEditAsAdmin on IRasDlgAdminOrNCO interface. hr = %#x",
            v16);
        v6 = v17;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v13 != -2147417850 )
      CoUninitialize();
  }
  *(_DWORD *)(a3 + 540) = v6;
}

```

## disassembly

```asm
0x18002d080  push    rbx
0x18002d082  push    rbp
0x18002d083  push    rsi
0x18002d084  push    rdi
0x18002d085  push    r12
0x18002d087  push    r14
0x18002d089  push    r15
0x18002d08b  sub     rsp, 290h
0x18002d092  mov     rax, cs:__security_cookie
0x18002d099  xor     rax, rsp
0x18002d09c  mov     [rsp+2C8h+var_48], rax
0x18002d0a4  mov     r12, rdx
0x18002d0a7  mov     [rsp+2C8h+var_288], 0
0x18002d0b0  mov     r15, rcx
0x18002d0b3  xor     esi, esi
0x18002d0b5  xor     ecx, ecx; pvReserved
0x18002d0b7  mov     rbp, r9
0x18002d0ba  mov     rbx, r8
0x18002d0bd  lea     edx, [rsi+6]; dwCoInit
0x18002d0c0  call    cs:__imp_CoInitializeEx
0x18002d0c6  xor     ecx, ecx
0x18002d0c8  mov     r14d, eax
0x18002d0cb  cmp     eax, 80010106h
0x18002d0d0  cmovnz  ecx, eax
0x18002d0d3  test    ecx, ecx
0x18002d0d5  js      loc_18002D256
0x18002d0db  mov     rcx, [rbx+4]; HWND
0x18002d0df  lea     r9, [rsp+2C8h+var_288]; void **
0x18002d0e4  call    ?NtlCoCreateInstanceAsNetConfigOpOrAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; NtlCoCreateInstanceAsNetConfigOpOrAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18002d0e9  mov     edi, eax
0x18002d0eb  test    eax, eax
0x18002d0ed  js      loc_18002D211
0x18002d0f3  xor     edx, edx; Val
0x18002d0f5  lea     rcx, [rsp+2C8h+var_278]; void *
0x18002d0fa  mov     r8d, 228h; Size
0x18002d100  call    memset_0
0x18002d105  xor     r8d, r8d
0x18002d108  lea     rcx, [rsp+2C8h+var_278]
0x18002d10d  mov     rdx, rbx
0x18002d110  call    CopyRasEntryDlgStruct
0x18002d115  mov     rcx, [rsp+2C8h+var_288]
0x18002d11a  lea     r9, [rsp+2C8h+var_278]
0x18002d11f  btr     [rsp+2C8h+var_268], 1Eh
0x18002d125  mov     r8, r12
0x18002d128  mov     rdx, r15
0x18002d12b  mov     qword ptr [rsp+2C8h+var_2A8], rbp
0x18002d130  mov     rax, [rcx]
0x18002d133  mov     rax, [rax+18h]
0x18002d137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d13c  mov     edi, eax
0x18002d13e  test    eax, eax
0x18002d140  jns     short loc_18002D168
0x18002d142  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002d148  cmp     ecx, 0FFFFFFFFh
0x18002d14b  jz      short loc_18002D160
0x18002d14d  mov     r9d, eax
0x18002d150  lea     r8, aFailedToMakeCa; "Failed to make call LaunchRasProperties"...
0x18002d157  lea     edx, [rsi+0Ch]; dwFlags
0x18002d15a  call    cs:__imp_TracePrintfExA
0x18002d160  movzx   esi, di
0x18002d163  jmp     loc_18002D1FE
0x18002d168  cmp     [rbp+0], esi
0x18002d16b  jz      loc_18002D1F7
0x18002d171  lea     rcx, [rbx+18h]
0x18002d175  mov     edx, 101h
0x18002d17a  lea     r8, [rsp+2C8h+var_25C]
0x18002d17f  call    StringCchCopyWrapW
0x18002d184  mov     rdi, [rbx+220h]
0x18002d18b  test    rdi, rdi
0x18002d18e  jz      short loc_18002D1FE
0x18002d190  mov     rcx, [rdi+8]
0x18002d194  mov     rcx, [rcx]; pszSrc
0x18002d197  call    StrDup
0x18002d19c  mov     rcx, [rdi+8]
0x18002d1a0  mov     rbp, rax
0x18002d1a3  call    cs:__imp_ClosePhonebookFile
0x18002d1a9  mov     rcx, [rdi+8]
0x18002d1ad  xor     r9d, r9d
0x18002d1b0  mov     rdx, [rdi+10h]
0x18002d1b4  xor     r8d, r8d
0x18002d1b7  mov     qword ptr [rsp+2C8h+var_2A8], rcx; int
0x18002d1bc  mov     rcx, rbp
0x18002d1bf  call    cs:__imp_ReadPhonebookFile
0x18002d1c5  test    eax, eax
0x18002d1c7  jz      short loc_18002D1ED
0x18002d1c9  mov     rcx, [rbx+4]; hWnd
0x18002d1cd  xor     r9d, r9d
0x18002d1d0  mov     [rsp+2C8h+var_298], 0FAh; UINT
0x18002d1d8  mov     r8d, eax; dwMessageId
0x18002d1db  mov     edx, 141h; uID
0x18002d1e0  mov     [rsp+2C8h+var_2A0], 169h; UINT
0x18002d1e8  call    ErrorDlgUtil
0x18002d1ed  mov     rcx, rbp
0x18002d1f0  call    Free0
0x18002d1f5  jmp     short loc_18002D1FE
0x18002d1f7  mov     esi, [rsp+2C8h+var_58]
0x18002d1fe  mov     rcx, [rsp+2C8h+var_288]
0x18002d203  mov     rax, [rcx]
0x18002d206  mov     rax, [rax+10h]
0x18002d20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d20f  jmp     short loc_18002D247
0x18002d211  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002d217  cmp     ecx, 0FFFFFFFFh
0x18002d21a  jz      short loc_18002D231
0x18002d21c  mov     r9d, edi
0x18002d21f  lea     r8, aFailedToGetIra; "Failed to get IRasDlgAdminOrNCO interfa"...
0x18002d226  mov     edx, 0Ch; dwFlags
0x18002d22b  call    cs:__imp_TracePrintfExA
0x18002d231  cmp     edi, 800704C7h
0x18002d237  jz      short loc_18002D247
0x18002d239  mov     rcx, [rbx+4]; hwndOwner
0x18002d23d  mov     edx, edi; dwMessageId
0x18002d23f  movzx   esi, di
0x18002d242  call    ThrowErrorBox
0x18002d247  cmp     r14d, 80010106h
0x18002d24e  jz      short loc_18002D256
0x18002d250  call    cs:__imp_CoUninitialize
0x18002d256  mov     [rbx+21Ch], esi
0x18002d25c  mov     rcx, [rsp+2C8h+var_48]
0x18002d264  xor     rcx, rsp; StackCookie
0x18002d267  call    __security_check_cookie
0x18002d26c  add     rsp, 290h
0x18002d273  pop     r15
0x18002d275  pop     r14
0x18002d277  pop     r12
0x18002d279  pop     rdi
0x18002d27a  pop     rsi
0x18002d27b  pop     rbp
0x18002d27c  pop     rbx
0x18002d27d  retn
```
