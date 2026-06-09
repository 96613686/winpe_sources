# _AttributesFromSignatureInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x180076b70`
- end: `0x1800771c2`
- name: `?_AttributesFromSignatureInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1618`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180005e40`
- `0x180006e94`
- `0x180006ec4`
- `0x180066c10`
- `0x180076b70`
- `0x180077b50`
- `0x180116010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180076ddc`
- `ntdll!RtlAllocateHeap` at `0x180076f27`
- `ntdll!RtlAllocateHeap` at `0x18007707b`
- `ntdll!RtlAllocateHeap` at `0x180076ddc`
- `ntdll!RtlAllocateHeap` at `0x180076f27`
- `ntdll!RtlAllocateHeap` at `0x18007707b`
- `ntdll!RtlFreeHeap` at `0x180076e7c`
- `ntdll!RtlFreeHeap` at `0x180076fca`
- `ntdll!RtlFreeHeap` at `0x18007711e`
- `ntdll!RtlFreeHeap` at `0x180076e7c`
- `ntdll!RtlFreeHeap` at `0x180076fca`
- `ntdll!RtlFreeHeap` at `0x18007711e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077186`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077194`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077186`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077194`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076caf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076d15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076caf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d20`

## string_xrefs

- `0x180076c09`: `wintrust.dll`
- `0x180076c53`: `_LoadSystemModule failed for wintrust.dll`
- `0x180076c44`: `_AttributesFromSignatureInfo`
- `0x180076c6b`: `shlwapi.dll`
- `0x180076c83`: `_LoadSystemModule failed for shlwapi.dll`
- `0x180076e03`: `_SetFileAttributeValue`
- `0x180076e53`: `_SetFileAttributeValue`
- `0x180076f4e`: `_SetFileAttributeValue`
- `0x180076fa1`: `_SetFileAttributeValue`
- `0x1800770a2`: `_SetFileAttributeValue`
- `0x1800770f5`: `_SetFileAttributeValue`
- `0x180076e3e`: `Failed to copy attribute value (index %d) [%x]`
- `0x180076f8c`: `Failed to copy attribute value (index %d) [%x]`
- `0x1800770e0`: `Failed to copy attribute value (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromSignatureInfo(_QWORD **a1, __int64 a2)
{
  unsigned int v4; // ebx
  HMODULE SystemModule; // rax
  HMODULE v6; // r12
  HMODULE v7; // rax
  HMODULE v8; // r14
  FARPROC ProcAddress; // rax
  int v10; // eax
  FARPROC v11; // rax
  signed int LastError; // eax
  int v13; // eax
  int v14; // ebx
  wchar_t *Heap; // rax
  int v16; // eax
  void *v17; // r8
  int v18; // ebx
  wchar_t *v19; // rax
  int v20; // eax
  void *v21; // r8
  int v22; // ebx
  wchar_t *v23; // rax
  int v24; // eax
  void *v25; // r8
  _DWORD v27[3]; // [rsp+40h] [rbp-C0h] BYREF
  char v28; // [rsp+4Ch] [rbp-B4h]
  wchar_t *v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  wchar_t *v31; // [rsp+68h] [rbp-98h]
  int v32; // [rsp+70h] [rbp-90h]
  wchar_t *v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  wchar_t S2[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v36[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t v37[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(v27, 0, 0x58u);
  memset_0(S2, 0, 0x208u);
  memset_0(v36, 0, 0x208u);
  memset_0(v37, 0, 0x208u);
  if ( a2 )
  {
    v27[0] = 88;
    v29 = S2;
    v30 = 260;
    v31 = v36;
    v33 = v37;
    v32 = 260;
    v34 = 260;
    SystemModule = _LoadSystemModule(L"wintrust.dll");
    v6 = SystemModule;
    if ( SystemModule )
    {
      ProcAddress = GetProcAddress(SystemModule, "WTGetSignatureInfo");
      if ( ProcAddress )
      {
        v8 = 0;
        v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _DWORD *, _QWORD, _QWORD))ProcAddress)(
                **a1,
                -1,
                4099,
                v27,
                0,
                0);
        v4 = v10;
        if ( v10 < 0 )
        {
          AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1530, "WTGetSignatureInfo failed [%x]", v10);
          goto LABEL_64;
        }
        goto LABEL_16;
      }
    }
    else
    {
      AslLogCallPrintf(2, "_AttributesFromSignatureInfo", 1506, "_LoadSystemModule failed for wintrust.dll");
    }
    v7 = _LoadSystemModule(L"shlwapi.dll");
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147467259;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1544, "_LoadSystemModule failed for shlwapi.dll");
      goto LABEL_63;
    }
    v11 = GetProcAddress(v7, (LPCSTR)0x22F);
    if ( !v11 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1552, "Failed to get function SHGetSignatureInfo [%x]", v4);
      goto LABEL_62;
    }
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64, _DWORD *))v11)(**a1, 4099, v27);
    v4 = v13;
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1565, "SHGetSignatureInfo failed [%x]", v13);
LABEL_62:
      FreeLibrary(v8);
LABEL_63:
      if ( !v6 )
        return v4;
LABEL_64:
      FreeLibrary(v6);
      return v4;
    }
LABEL_16:
    if ( (v28 & 1) == 0 )
      goto LABEL_31;
    v14 = dword_18015554C;
    if ( (unsigned int)dword_18015554C <= 2 )
    {
      *(_DWORD *)(a2 + 10336) = *(_DWORD *)S2;
    }
    else if ( dword_18015554C == 3 )
    {
      *(_QWORD *)(a2 + 10336) = *(_QWORD *)S2;
    }
    else
    {
      if ( dword_18015554C != 4 )
        goto LABEL_31;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
      *(_QWORD *)(a2 + 10872) = Heap;
      if ( !Heap )
      {
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", 19);
        goto LABEL_31;
      }
      v16 = o_wmemcpy_s_0(Heap, 0x105u, S2, 0x104u);
      if ( v16 )
      {
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        AslLogCallPrintf(1, "_SetFileAttributeValue", 3156, "Failed to copy attribute value (index %d) [%x]", 19, v16);
        v17 = *(void **)(a2 + 10872);
        if ( v17 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
          *(_QWORD *)(a2 + 10872) = 0;
        }
LABEL_31:
        if ( (v28 & 2) == 0 )
          goto LABEL_46;
        v18 = dword_180155564;
        if ( (unsigned int)dword_180155564 <= 2 )
        {
          *(_DWORD *)(a2 + 10880) = *(_DWORD *)v36;
        }
        else if ( dword_180155564 == 3 )
        {
          *(_QWORD *)(a2 + 10880) = *(_QWORD *)v36;
        }
        else
        {
          if ( dword_180155564 != 4 )
            goto LABEL_46;
          v19 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
          *(_QWORD *)(a2 + 11416) = v19;
          if ( !v19 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3144,
              "Failed to alloc memory for string value (index %d)",
              20);
            goto LABEL_46;
          }
          v20 = o_wmemcpy_s_0(v19, 0x105u, v36, 0x104u);
          if ( v20 )
          {
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3156,
              "Failed to copy attribute value (index %d) [%x]",
              20,
              v20);
            v21 = *(void **)(a2 + 11416);
            if ( v21 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
              *(_QWORD *)(a2 + 11416) = 0;
            }
LABEL_46:
            if ( (v28 & 4) == 0 )
              goto LABEL_61;
            v22 = dword_18015557C;
            if ( (unsigned int)dword_18015557C <= 2 )
            {
              *(_DWORD *)(a2 + 11424) = *(_DWORD *)v37;
            }
            else if ( dword_18015557C == 3 )
            {
              *(_QWORD *)(a2 + 11424) = *(_QWORD *)v37;
            }
            else
            {
              if ( dword_18015557C != 4 )
                goto LABEL_61;
              v23 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
              *(_QWORD *)(a2 + 11960) = v23;
              if ( !v23 )
              {
                AslLogCallPrintf(
                  1,
                  "_SetFileAttributeValue",
                  3144,
                  "Failed to alloc memory for string value (index %d)",
                  21);
                goto LABEL_61;
              }
              v24 = o_wmemcpy_s_0(v23, 0x105u, v37, 0x104u);
              if ( v24 )
              {
                if ( v24 > 0 )
                  v24 = (unsigned __int16)v24 | 0x80070000;
                AslLogCallPrintf(
                  1,
                  "_SetFileAttributeValue",
                  3156,
                  "Failed to copy attribute value (index %d) [%x]",
                  21,
                  v24);
                v25 = *(void **)(a2 + 11960);
                if ( v25 )
                {
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
                  *(_QWORD *)(a2 + 11960) = 0;
                }
LABEL_61:
                v4 = 0;
                if ( !v8 )
                  goto LABEL_63;
                goto LABEL_62;
              }
              *(_WORD *)(*(_QWORD *)(a2 + 11960) + 520LL) = 0;
              *(_WORD *)(a2 + 11424) = 0;
            }
            *(_DWORD *)(a2 + 11944) = 21;
            *(_DWORD *)(a2 + 11948) = v22;
            *(_DWORD *)(a2 + 11952) = 1;
            goto LABEL_61;
          }
          *(_WORD *)(*(_QWORD *)(a2 + 11416) + 520LL) = 0;
          *(_WORD *)(a2 + 10880) = 0;
        }
        *(_DWORD *)(a2 + 11400) = 20;
        *(_DWORD *)(a2 + 11404) = v18;
        *(_DWORD *)(a2 + 11408) = 1;
        goto LABEL_46;
      }
      *(_WORD *)(*(_QWORD *)(a2 + 10872) + 520LL) = 0;
      *(_WORD *)(a2 + 10336) = 0;
    }
    *(_DWORD *)(a2 + 10856) = 19;
    *(_DWORD *)(a2 + 10860) = v14;
    *(_DWORD *)(a2 + 10864) = 1;
    goto LABEL_31;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180076b70  mov     [rsp-8+arg_10], rbx
0x180076b75  push    rbp
0x180076b76  push    rsi
0x180076b77  push    rdi
0x180076b78  push    r12
0x180076b7a  push    r14
0x180076b7c  lea     rbp, [rsp-5E0h]
0x180076b84  sub     rsp, 6E0h
0x180076b8b  mov     rax, cs:__security_cookie
0x180076b92  xor     rax, rsp
0x180076b95  mov     [rbp+600h+var_30], rax
0x180076b9c  mov     rdi, rdx
0x180076b9f  mov     rbx, rcx
0x180076ba2  mov     r14d, 58h ; 'X'
0x180076ba8  lea     rcx, [rsp+700h+var_6C0]; void *
0x180076bad  mov     r8d, r14d; Size
0x180076bb0  xor     edx, edx; Val
0x180076bb2  call    memset_0
0x180076bb7  mov     esi, 208h
0x180076bbc  lea     rcx, [rbp+600h+S2]; void *
0x180076bc0  mov     r8d, esi; Size
0x180076bc3  xor     edx, edx; Val
0x180076bc5  call    memset_0
0x180076bca  mov     r8d, esi; Size
0x180076bcd  lea     rcx, [rbp+600h+var_450]; void *
0x180076bd4  xor     edx, edx; Val
0x180076bd6  call    memset_0
0x180076bdb  mov     r8d, esi; Size
0x180076bde  lea     rcx, [rbp+600h+var_240]; void *
0x180076be5  xor     edx, edx; Val
0x180076be7  call    memset_0
0x180076bec  test    rdi, rdi
0x180076bef  jnz     short loc_180076BFB
0x180076bf1  mov     ebx, 80070057h
0x180076bf6  jmp     loc_18007719A
0x180076bfb  lea     rax, [rbp+600h+S2]
0x180076bff  mov     [rsp+700h+var_6C0], r14d
0x180076c04  mov     [rsp+700h+var_6A8], rax
0x180076c09  lea     rcx, aWintrustDll_0; "wintrust.dll"
0x180076c10  lea     rax, [rbp+600h+var_450]
0x180076c17  mov     [rsp+700h+var_6A0], 104h
0x180076c1f  mov     [rsp+700h+var_698], rax
0x180076c24  lea     rax, [rbp+600h+var_240]
0x180076c2b  mov     [rsp+700h+var_688], rax
0x180076c30  mov     [rsp+700h+var_690], 104h
0x180076c38  mov     [rbp+600h+var_680], 104h
0x180076c3f  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x180076c44  lea     rsi, aAttributesfrom_2; "_AttributesFromSignatureInfo"
0x180076c4b  mov     r12, rax
0x180076c4e  test    rax, rax
0x180076c51  jnz     short loc_180076CA5
0x180076c53  lea     r9, aLoadsystemmodu_0; "_LoadSystemModule failed for wintrust.d"...
0x180076c5a  mov     r8d, 5E2h
0x180076c60  mov     rdx, rsi
0x180076c63  lea     ecx, [rax+2]
0x180076c66  call    AslLogCallPrintf
0x180076c6b  lea     rcx, aShlwapiDll; "shlwapi.dll"
0x180076c72  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x180076c77  mov     r14, rax
0x180076c7a  test    rax, rax
0x180076c7d  jnz     loc_180076D0D
0x180076c83  lea     r9, aLoadsystemmodu; "_LoadSystemModule failed for shlwapi.dl"...
0x180076c8a  mov     r8d, 608h
0x180076c90  mov     rdx, rsi
0x180076c93  lea     ecx, [rax+1]
0x180076c96  mov     ebx, 80004005h
0x180076c9b  call    AslLogCallPrintf
0x180076ca0  jmp     loc_18007718C
0x180076ca5  lea     rdx, aWtgetsignature_0; "WTGetSignatureInfo"
0x180076cac  mov     rcx, r12; hModule
0x180076caf  call    cs:__imp_GetProcAddress
0x180076cb5  test    rax, rax
0x180076cb8  jz      short loc_180076C6B
0x180076cba  mov     rcx, [rbx]
0x180076cbd  lea     r9, [rsp+700h+var_6C0]
0x180076cc2  xor     r14d, r14d
0x180076cc5  mov     r8d, 1003h
0x180076ccb  mov     [rsp+700h+var_6D8], r14
0x180076cd0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180076cd4  mov     [rsp+700h+var_6E0], r14
0x180076cd9  mov     rcx, [rcx]
0x180076cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ce1  mov     ebx, eax
0x180076ce3  test    eax, eax
0x180076ce5  jns     loc_180076D86
0x180076ceb  lea     r9, aWtgetsignature; "WTGetSignatureInfo failed [%x]"
0x180076cf2  mov     dword ptr [rsp+700h+var_6E0], eax
0x180076cf6  mov     r8d, 5FAh
0x180076cfc  lea     ecx, [r14+1]
0x180076d00  mov     rdx, rsi
0x180076d03  call    AslLogCallPrintf
0x180076d08  jmp     loc_180077191
0x180076d0d  mov     edx, 22Fh; lpProcName
0x180076d12  mov     rcx, rax; hModule
0x180076d15  call    cs:__imp_GetProcAddress
0x180076d1b  test    rax, rax
0x180076d1e  jnz     short loc_180076D58
0x180076d20  call    cs:__imp_GetLastError
0x180076d26  mov     ebx, eax
0x180076d28  test    eax, eax
0x180076d2a  jle     short loc_180076D35
0x180076d2c  movzx   ebx, ax
0x180076d2f  or      ebx, 80070000h
0x180076d35  mov     dword ptr [rsp+700h+var_6E0], ebx
0x180076d39  lea     r9, aFailedToGetFun; "Failed to get function SHGetSignatureIn"...
0x180076d40  mov     r8d, 610h
0x180076d46  mov     rdx, rsi
0x180076d49  mov     ecx, 1
0x180076d4e  call    AslLogCallPrintf
0x180076d53  jmp     loc_180077183
0x180076d58  mov     rcx, [rbx]
0x180076d5b  lea     r8, [rsp+700h+var_6C0]
0x180076d60  mov     edx, 1003h
0x180076d65  mov     rcx, [rcx]
0x180076d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d6d  mov     ebx, eax
0x180076d6f  test    eax, eax
0x180076d71  jns     short loc_180076D86
0x180076d73  mov     dword ptr [rsp+700h+var_6E0], eax
0x180076d77  lea     r9, aShgetsignature; "SHGetSignatureInfo failed [%x]"
0x180076d7e  mov     r8d, 61Dh
0x180076d84  jmp     short loc_180076D46
0x180076d86  mov     esi, 1
0x180076d8b  test    [rsp+700h+var_6B4], sil
0x180076d90  jz      loc_180076ED4
0x180076d96  mov     ebx, cs:dword_18015554C
0x180076d9c  mov     ecx, ebx
0x180076d9e  test    ebx, ebx
0x180076da0  jz      loc_180076EB5
0x180076da6  sub     ecx, esi
0x180076da8  jz      loc_180076EB5
0x180076dae  sub     ecx, esi
0x180076db0  jz      loc_180076EB5
0x180076db6  sub     ecx, esi
0x180076db8  jz      loc_180076EA8
0x180076dbe  cmp     ecx, esi
0x180076dc0  jnz     loc_180076ED4
0x180076dc6  mov     rcx, gs:60h
0x180076dcf  lea     edx, [rsi+7]; Flags
0x180076dd2  mov     r8d, 20Ah; Size
0x180076dd8  mov     rcx, [rcx+30h]; HeapHandle
0x180076ddc  call    cs:__imp_RtlAllocateHeap
0x180076de2  mov     [rdi+2A78h], rax
0x180076de9  test    rax, rax
0x180076dec  jnz     short loc_180076E16
0x180076dee  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x180076df5  mov     dword ptr [rsp+700h+var_6E0], 13h
0x180076dfd  mov     r8d, 0C48h
0x180076e03  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180076e0a  mov     ecx, esi
0x180076e0c  call    AslLogCallPrintf
0x180076e11  jmp     loc_180076ED4
0x180076e16  mov     r9d, 104h; N
0x180076e1c  lea     r8, [rbp+600h+S2]; S2
0x180076e20  mov     rcx, rax; S1
0x180076e23  lea     edx, [r9+1]; N1
0x180076e27  call    _o_wmemcpy_s_0
0x180076e2c  test    eax, eax
0x180076e2e  jz      short loc_180076E8F
0x180076e30  jle     short loc_180076E3A
0x180076e32  movzx   eax, ax
0x180076e35  or      eax, 80070000h
0x180076e3a  mov     dword ptr [rsp+700h+var_6D8], eax
0x180076e3e  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x180076e45  mov     r8d, 0C54h
0x180076e4b  mov     dword ptr [rsp+700h+var_6E0], 13h
0x180076e53  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180076e5a  mov     ecx, esi
0x180076e5c  call    AslLogCallPrintf
0x180076e61  mov     r8, [rdi+2A78h]; P
0x180076e68  test    r8, r8
0x180076e6b  jz      short loc_180076ED4
0x180076e6d  mov     rcx, gs:60h
0x180076e76  xor     edx, edx; Flags
0x180076e78  mov     rcx, [rcx+30h]; HeapHandle
0x180076e7c  call    cs:__imp_RtlFreeHeap
0x180076e82  mov     qword ptr [rdi+2A78h], 0
0x180076e8d  jmp     short loc_180076ED4
0x180076e8f  mov     rcx, [rdi+2A78h]
0x180076e96  xor     eax, eax
0x180076e98  mov     [rcx+208h], ax
0x180076e9f  mov     [rdi+2860h], ax
0x180076ea6  jmp     short loc_180076EBE
0x180076ea8  mov     rax, qword ptr [rbp+600h+S2]
0x180076eac  mov     [rdi+2860h], rax
0x180076eb3  jmp     short loc_180076EBE
0x180076eb5  mov     eax, dword ptr [rbp+600h+S2]
0x180076eb8  mov     [rdi+2860h], eax
0x180076ebe  mov     dword ptr [rdi+2A68h], 13h
0x180076ec8  mov     [rdi+2A6Ch], ebx
0x180076ece  mov     [rdi+2A70h], esi
0x180076ed4  test    [rsp+700h+var_6B4], 2
0x180076ed9  jz      loc_180077028
0x180076edf  mov     ebx, cs:dword_180155564
0x180076ee5  mov     ecx, ebx
0x180076ee7  test    ebx, ebx
0x180076ee9  jz      loc_180077006
0x180076eef  sub     ecx, esi
0x180076ef1  jz      loc_180077006
0x180076ef7  sub     ecx, esi
0x180076ef9  jz      loc_180077006
0x180076eff  sub     ecx, esi
0x180076f01  jz      loc_180076FF6
0x180076f07  cmp     ecx, esi
0x180076f09  jnz     loc_180077028
0x180076f0f  mov     rcx, gs:60h
0x180076f18  mov     edx, 8; Flags
0x180076f1d  mov     r8d, 20Ah; Size
0x180076f23  mov     rcx, [rcx+30h]; HeapHandle
0x180076f27  call    cs:__imp_RtlAllocateHeap
0x180076f2d  mov     [rdi+2C98h], rax
0x180076f34  test    rax, rax
0x180076f37  jnz     short loc_180076F61
0x180076f39  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x180076f40  mov     dword ptr [rsp+700h+var_6E0], 14h
0x180076f48  mov     r8d, 0C48h
0x180076f4e  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180076f55  mov     ecx, esi
0x180076f57  call    AslLogCallPrintf
0x180076f5c  jmp     loc_180077028
0x180076f61  mov     r9d, 104h; N
0x180076f67  lea     r8, [rbp+600h+var_450]; S2
0x180076f6e  mov     rcx, rax; S1
0x180076f71  lea     edx, [r9+1]; N1
0x180076f75  call    _o_wmemcpy_s_0
0x180076f7a  test    eax, eax
0x180076f7c  jz      short loc_180076FDD
0x180076f7e  jle     short loc_180076F88
0x180076f80  movzx   eax, ax
0x180076f83  or      eax, 80070000h
0x180076f88  mov     dword ptr [rsp+700h+var_6D8], eax
0x180076f8c  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x180076f93  mov     r8d, 0C54h
0x180076f99  mov     dword ptr [rsp+700h+var_6E0], 14h
0x180076fa1  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180076fa8  mov     ecx, esi
0x180076faa  call    AslLogCallPrintf
0x180076faf  mov     r8, [rdi+2C98h]; P
0x180076fb6  test    r8, r8
0x180076fb9  jz      short loc_180077028
0x180076fbb  mov     rcx, gs:60h
0x180076fc4  xor     edx, edx; Flags
0x180076fc6  mov     rcx, [rcx+30h]; HeapHandle
0x180076fca  call    cs:__imp_RtlFreeHeap
0x180076fd0  mov     qword ptr [rdi+2C98h], 0
0x180076fdb  jmp     short loc_180077028
0x180076fdd  mov     rcx, [rdi+2C98h]
0x180076fe4  xor     eax, eax
0x180076fe6  mov     [rcx+208h], ax
0x180076fed  mov     [rdi+2A80h], ax
0x180076ff4  jmp     short loc_180077012
0x180076ff6  mov     rax, qword ptr [rbp+600h+var_450]
0x180076ffd  mov     [rdi+2A80h], rax
0x180077004  jmp     short loc_180077012
0x180077006  mov     eax, dword ptr [rbp+600h+var_450]
0x18007700c  mov     [rdi+2A80h], eax
0x180077012  mov     dword ptr [rdi+2C88h], 14h
0x18007701c  mov     [rdi+2C8Ch], ebx
0x180077022  mov     [rdi+2C90h], esi
0x180077028  test    [rsp+700h+var_6B4], 4
0x18007702d  jz      loc_18007717C
0x180077033  mov     ebx, cs:dword_18015557C
0x180077039  mov     ecx, ebx
0x18007703b  test    ebx, ebx
0x18007703d  jz      loc_18007715A
0x180077043  sub     ecx, esi
0x180077045  jz      loc_18007715A
0x18007704b  sub     ecx, esi
0x18007704d  jz      loc_18007715A
0x180077053  sub     ecx, esi
0x180077055  jz      loc_18007714A
0x18007705b  cmp     ecx, esi
0x18007705d  jnz     loc_18007717C
0x180077063  mov     rcx, gs:60h
0x18007706c  mov     edx, 8; Flags
0x180077071  mov     r8d, 20Ah; Size
0x180077077  mov     rcx, [rcx+30h]; HeapHandle
0x18007707b  call    cs:__imp_RtlAllocateHeap
0x180077081  mov     [rdi+2EB8h], rax
0x180077088  test    rax, rax
0x18007708b  jnz     short loc_1800770B5
0x18007708d  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x180077094  mov     dword ptr [rsp+700h+var_6E0], 15h
0x18007709c  mov     r8d, 0C48h
0x1800770a2  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800770a9  mov     ecx, esi
0x1800770ab  call    AslLogCallPrintf
0x1800770b0  jmp     loc_18007717C
0x1800770b5  mov     r9d, 104h; N
0x1800770bb  lea     r8, [rbp+600h+var_240]; S2
0x1800770c2  mov     rcx, rax; S1
0x1800770c5  lea     edx, [r9+1]; N1
0x1800770c9  call    _o_wmemcpy_s_0
0x1800770ce  test    eax, eax
0x1800770d0  jz      short loc_180077131
0x1800770d2  jle     short loc_1800770DC
0x1800770d4  movzx   eax, ax
0x1800770d7  or      eax, 80070000h
0x1800770dc  mov     dword ptr [rsp+700h+var_6D8], eax
0x1800770e0  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
  ... truncated ...
```
