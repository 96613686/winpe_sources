# AhgGenomeGetAll

- ea: `0x180009cdc`
- end: `0x180009fe0`
- name: `AhgGenomeGetAll`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18000a60c`

## callees

- `0x180009cdc`
- `0x180009fe8`
- `0x18000a208`
- `0x18000a8f0`
- `0x18000ac50`
- `0x18000ad2c`
- `0x18000e240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009d4f`
- `KERNEL32!GetLastError` at `0x180009d4f`
- `KERNEL32!CloseHandle` at `0x180009e99`
- `KERNEL32!CloseHandle` at `0x180009e99`
- `KERNEL32!CreateFileW` at `0x180009d40`
- `KERNEL32!CreateFileW` at `0x180009d40`

## string_xrefs

- `0x180009d55`: `Failed to open file [%d]`
- `0x180009faf`: `Cannot get manifest data [%d]`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetAll(const WCHAR *a1, void *a2, void *a3, __int64 a4)
{
  unsigned int v4; // edi
  HANDLE FileW; // rsi
  DWORD LastError; // ebx
  int v9; // r14d
  DWORD FileCreationTime; // eax
  const char *v11; // r9
  __int64 v12; // r8
  const char *v13; // r9
  __int64 v14; // r8
  int PE; // eax
  unsigned int Manifest; // eax
  __int64 v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+80h] [rbp+8h] BYREF
  __int64 v20; // [rsp+88h] [rbp+10h] BYREF
  int v21; // [rsp+98h] [rbp+20h] BYREF
  int v22; // [rsp+9Ch] [rbp+24h]

  v22 = HIDWORD(a4);
  v20 = 0;
  v4 = 87;
  v19 = 0;
  v21 = 0;
  FileW = a2;
  if ( a2 == (void *)-1LL )
  {
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "AhgGenomeGetFileAttributes", 278, "Failed to open file [%d]", LastError);
      goto LABEL_21;
    }
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  FileCreationTime = AhgGetFileCreationTime(&v20, FileW);
  LastError = FileCreationTime;
  if ( FileCreationTime )
  {
    v11 = "Failed to get the creation time [%d]";
    v12 = 291;
LABEL_8:
    LODWORD(v18) = FileCreationTime;
    AslLogCallPrintf(1, "AhgGenomeGetFileAttributes", v12, v11, v18);
    goto LABEL_19;
  }
  if ( (unsigned int)AhgpSetAttribute(a1 + 316, 7, &v20) )
  {
    FileCreationTime = AhgGetFileExeType(&v21, &v19, FileW);
    LastError = FileCreationTime;
    if ( FileCreationTime )
    {
      if ( FileCreationTime != 193 )
      {
        v11 = "Failed to get the exe type [%d]";
        v12 = 312;
        goto LABEL_8;
      }
    }
    else if ( (unsigned int)AhgpSetAttribute(a1 + 324, 8, &v21) )
    {
      if ( (unsigned int)AhgpSetAttribute(a1 + 332, 9, &v19) )
      {
        LastError = 0;
      }
      else
      {
        LastError = 87;
        LODWORD(v18) = 87;
        AslLogCallPrintf(
          1,
          "AhgGenomeGetFileAttributes",
          333,
          "Failed to set data for attribute AHG_TAG_FILE_EXE_ILONLY [%d]",
          v18);
      }
    }
    else
    {
      LastError = 87;
      LODWORD(v18) = 87;
      AslLogCallPrintf(
        1,
        "AhgGenomeGetFileAttributes",
        323,
        "Failed to set data for attribute AHG_TAG_FILE_EXE_TYPE [%d]",
        v18);
    }
  }
  else
  {
    LastError = 87;
    LODWORD(v18) = 87;
    AslLogCallPrintf(
      1,
      "AhgGenomeGetFileAttributes",
      301,
      "Failed to set data for attribute AHG_TAG_FILE_CREATION_TIME [%d]",
      v18);
  }
LABEL_19:
  if ( v9 )
    CloseHandle(FileW);
LABEL_21:
  if ( LastError == 30 )
  {
    v4 = 30;
    LODWORD(v18) = 30;
    v13 = "Bad image file [%d]";
    v14 = 745;
LABEL_23:
    AslLogCallPrintf(1, "AhgGenomeGetAll", v14, v13, v18);
    return v4;
  }
  if ( LastError )
    AslLogCallPrintf(3, "AhgGenomeGetAll", 750, "Cannot get file attribute [%d]", LastError);
  PE = AhgGenomeGetPE(a1, a3);
  if ( PE == 30 )
  {
    v21 = 1;
    if ( !(unsigned int)AhgpSetAttribute(a1 + 380, 15, &v21) )
    {
      AslLogCallPrintf(1, "AhgGenomeRecordBadImageOr16BitApp", 590, "Failed to set data for attribute AHG_TAG_NOT_PE");
      v13 = "Failed to set bad image or 16 bit app into genome [%d]";
      LODWORD(v18) = 87;
      v14 = 762;
      goto LABEL_23;
    }
  }
  else if ( PE )
  {
    AslLogCallPrintf(3, "AhgGenomeGetAll", 768, "Cannot get PE data [%d]", PE);
  }
  Manifest = AhgGenomeGetManifest(a1);
  v4 = Manifest;
  if ( Manifest == 30 )
  {
    LODWORD(v18) = 30;
    v13 = "Bad image file [%d]";
    v14 = 778;
    goto LABEL_23;
  }
  if ( Manifest )
    AslLogCallPrintf(3, "AhgGenomeGetAll", 783, "Cannot get manifest data [%d]", Manifest);
  return 0;
}

```

## disassembly

```asm
0x180009cdc  mov     rax, rsp
0x180009cdf  mov     [rax+20h], r9
0x180009ce3  push    rbx
0x180009ce4  push    rbp
0x180009ce5  push    rsi
0x180009ce6  push    rdi
0x180009ce7  push    r13
0x180009ce9  push    r14
0x180009ceb  push    r15
0x180009ced  sub     rsp, 40h
0x180009cf1  mov     qword ptr [rax+10h], 0
0x180009cf9  mov     edi, 57h ; 'W'
0x180009cfe  mov     dword ptr [rax+8], 0
0x180009d05  mov     r15, r8
0x180009d08  mov     dword ptr [rax+20h], 0
0x180009d0f  mov     rsi, rdx
0x180009d12  mov     rbp, rcx
0x180009d15  lea     r13d, [rdi-56h]
0x180009d19  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180009d1d  jnz     short loc_180009D81
0x180009d1f  mov     qword ptr [rax-48h], 0
0x180009d27  xor     r9d, r9d; lpSecurityAttributes
0x180009d2a  mov     dword ptr [rax-50h], 80h
0x180009d31  mov     r8d, r13d; dwShareMode
0x180009d34  mov     edx, 80000000h; dwDesiredAccess
0x180009d39  mov     dword ptr [rax-58h], 3
0x180009d40  call    cs:__imp_CreateFileW
0x180009d46  mov     rsi, rax
0x180009d49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009d4d  jnz     short loc_180009D7C
0x180009d4f  call    cs:__imp_GetLastError
0x180009d55  lea     r9, aFailedToOpenFi; "Failed to open file [%d]"
0x180009d5c  mov     r8d, 116h
0x180009d62  lea     rdx, aAhggenomegetfi; "AhgGenomeGetFileAttributes"
0x180009d69  mov     dword ptr [rsp+78h+var_58], eax
0x180009d6d  mov     ecx, r13d
0x180009d70  mov     ebx, eax
0x180009d72  call    AslLogCallPrintf
0x180009d77  jmp     loc_180009E9F
0x180009d7c  mov     r14d, r13d
0x180009d7f  jmp     short loc_180009D84
0x180009d81  xor     r14d, r14d
0x180009d84  mov     rdx, rsi
0x180009d87  lea     rcx, [rsp+78h+arg_8]
0x180009d8f  call    AhgGetFileCreationTime
0x180009d94  mov     ebx, eax
0x180009d96  test    eax, eax
0x180009d98  jz      short loc_180009DBF
0x180009d9a  lea     r9, aFailedToGetThe_0; "Failed to get the creation time [%d]"
0x180009da1  mov     r8d, 123h
0x180009da7  mov     dword ptr [rsp+78h+var_58], eax
0x180009dab  lea     rdx, aAhggenomegetfi; "AhgGenomeGetFileAttributes"
0x180009db2  mov     ecx, r13d
0x180009db5  call    AslLogCallPrintf
0x180009dba  jmp     loc_180009E91
0x180009dbf  mov     edx, 7
0x180009dc4  lea     rcx, [rbp+278h]
0x180009dcb  lea     r8, [rsp+78h+arg_8]
0x180009dd3  call    AhgpSetAttribute
0x180009dd8  test    eax, eax
0x180009dda  jnz     short loc_180009DF1
0x180009ddc  mov     ebx, edi
0x180009dde  mov     dword ptr [rsp+78h+var_58], edi
0x180009de2  lea     r9, aFailedToSetDat_7; "Failed to set data for attribute AHG_TA"...
0x180009de9  mov     r8d, 12Dh
0x180009def  jmp     short loc_180009DAB
0x180009df1  mov     r8, rsi
0x180009df4  lea     rdx, [rsp+78h+arg_0]
0x180009dfc  lea     rcx, [rsp+78h+arg_18]
0x180009e04  call    AhgGetFileExeType
0x180009e09  mov     ebx, eax
0x180009e0b  test    eax, eax
0x180009e0d  jz      short loc_180009E25
0x180009e0f  cmp     eax, 0C1h
0x180009e14  jz      short loc_180009E91
0x180009e16  lea     r9, aFailedToGetThe; "Failed to get the exe type [%d]"
0x180009e1d  mov     r8d, 138h
0x180009e23  jmp     short loc_180009DA7
0x180009e25  mov     edx, 8
0x180009e2a  lea     rcx, [rbp+288h]
0x180009e31  lea     r8, [rsp+78h+arg_18]
0x180009e39  call    AhgpSetAttribute
0x180009e3e  test    eax, eax
0x180009e40  jnz     short loc_180009E5A
0x180009e42  mov     ebx, edi
0x180009e44  mov     dword ptr [rsp+78h+var_58], edi
0x180009e48  lea     r9, aFailedToSetDat_8; "Failed to set data for attribute AHG_TA"...
0x180009e4f  mov     r8d, 143h
0x180009e55  jmp     loc_180009DAB
0x180009e5a  mov     edx, 9
0x180009e5f  lea     rcx, [rbp+298h]
0x180009e66  lea     r8, [rsp+78h+arg_0]
0x180009e6e  call    AhgpSetAttribute
0x180009e73  test    eax, eax
0x180009e75  jnz     short loc_180009E8F
0x180009e77  mov     ebx, edi
0x180009e79  mov     dword ptr [rsp+78h+var_58], edi
0x180009e7d  lea     r9, aFailedToSetDat_4; "Failed to set data for attribute AHG_TA"...
0x180009e84  mov     r8d, 14Dh
0x180009e8a  jmp     loc_180009DAB
0x180009e8f  xor     ebx, ebx
0x180009e91  test    r14d, r14d
0x180009e94  jz      short loc_180009E9F
0x180009e96  mov     rcx, rsi; hObject
0x180009e99  call    cs:__imp_CloseHandle
0x180009e9f  mov     r14d, 1Eh
0x180009ea5  cmp     ebx, r14d
0x180009ea8  jnz     short loc_180009ED3
0x180009eaa  mov     edi, r14d
0x180009ead  mov     dword ptr [rsp+78h+var_58], r14d
0x180009eb2  lea     r9, aBadImageFileD; "Bad image file [%d]"
0x180009eb9  mov     r8d, 2E9h
0x180009ebf  lea     rdx, aAhggenomegetal; "AhgGenomeGetAll"
0x180009ec6  mov     ecx, r13d
0x180009ec9  call    AslLogCallPrintf
0x180009ece  jmp     loc_180009FCF
0x180009ed3  lea     rsi, aAhggenomegetal; "AhgGenomeGetAll"
0x180009eda  test    ebx, ebx
0x180009edc  jz      short loc_180009EFC
0x180009ede  lea     r9, aCannotGetFileA; "Cannot get file attribute [%d]"
0x180009ee5  mov     dword ptr [rsp+78h+var_58], ebx
0x180009ee9  mov     r8d, 2EEh
0x180009eef  mov     rdx, rsi
0x180009ef2  mov     ecx, 3
0x180009ef7  call    AslLogCallPrintf
0x180009efc  mov     rdx, r15
0x180009eff  mov     rcx, rbp
0x180009f02  call    AhgGenomeGetPE
0x180009f07  cmp     eax, r14d
0x180009f0a  jnz     short loc_180009F66
0x180009f0c  mov     edx, 0Fh
0x180009f11  mov     [rsp+78h+arg_18], r13d
0x180009f19  lea     rcx, [rbp+2F8h]
0x180009f20  lea     r8, [rsp+78h+arg_18]
0x180009f28  call    AhgpSetAttribute
0x180009f2d  test    eax, eax
0x180009f2f  jnz     short loc_180009F88
0x180009f31  lea     r9, aFailedToSetDat_5; "Failed to set data for attribute AHG_TA"...
0x180009f38  mov     r8d, 24Eh
0x180009f3e  lea     rdx, aAhggenomerecor; "AhgGenomeRecordBadImageOr16BitApp"
0x180009f45  mov     ecx, r13d
0x180009f48  call    AslLogCallPrintf
0x180009f4d  lea     r9, aFailedToSetBad; "Failed to set bad image or 16 bit app i"...
0x180009f54  mov     dword ptr [rsp+78h+var_58], edi
0x180009f58  mov     r8d, 2FAh
0x180009f5e  mov     rdx, rsi
0x180009f61  jmp     loc_180009EC6
0x180009f66  test    eax, eax
0x180009f68  jz      short loc_180009F88
0x180009f6a  lea     r9, aCannotGetPeDat; "Cannot get PE data [%d]"
0x180009f71  mov     dword ptr [rsp+78h+var_58], eax
0x180009f75  mov     r8d, 300h
0x180009f7b  mov     rdx, rsi
0x180009f7e  mov     ecx, 3
0x180009f83  call    AslLogCallPrintf
0x180009f88  mov     rcx, rbp
0x180009f8b  call    AhgGenomeGetManifest
0x180009f90  mov     edi, eax
0x180009f92  cmp     eax, r14d
0x180009f95  jnz     short loc_180009FAB
0x180009f97  mov     dword ptr [rsp+78h+var_58], r14d
0x180009f9c  lea     r9, aBadImageFileD; "Bad image file [%d]"
0x180009fa3  mov     r8d, 30Ah
0x180009fa9  jmp     short loc_180009F5E
0x180009fab  test    eax, eax
0x180009fad  jz      short loc_180009FCD
0x180009faf  lea     r9, aCannotGetManif; "Cannot get manifest data [%d]"
0x180009fb6  mov     dword ptr [rsp+78h+var_58], eax
0x180009fba  mov     r8d, 30Fh
0x180009fc0  mov     rdx, rsi
0x180009fc3  mov     ecx, 3
0x180009fc8  call    AslLogCallPrintf
0x180009fcd  xor     edi, edi
0x180009fcf  mov     eax, edi
0x180009fd1  add     rsp, 40h
0x180009fd5  pop     r15
0x180009fd7  pop     r14
0x180009fd9  pop     r13
0x180009fdb  pop     rdi
0x180009fdc  pop     rsi
0x180009fdd  pop     rbp
0x180009fde  pop     rbx
0x180009fdf  retn
```
