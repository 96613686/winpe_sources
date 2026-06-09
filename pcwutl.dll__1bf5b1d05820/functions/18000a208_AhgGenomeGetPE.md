# AhgGenomeGetPE

- ea: `0x18000a208`
- end: `0x18000a604`
- name: `AhgGenomeGetPE`
- size: `1020`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009cdc`

## callees

- `0x18000a208`
- `0x18000a8f0`
- `0x18000a96c`
- `0x18000e240`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000a35d`
- `KERNEL32!MapViewOfFile` at `0x18000a35d`
- `KERNEL32!CreateFileMappingW` at `0x18000a31c`
- `KERNEL32!CreateFileMappingW` at `0x18000a31c`
- `KERNEL32!GetLocalTime` at `0x18000a40a`
- `KERNEL32!GetLocalTime` at `0x18000a40a`
- `KERNEL32!UnmapViewOfFile` at `0x18000a5b6`
- `KERNEL32!UnmapViewOfFile` at `0x18000a5b6`
- `KERNEL32!GetLastError` at `0x18000a2d5`
- `KERNEL32!GetLastError` at `0x18000a332`
- `KERNEL32!GetLastError` at `0x18000a373`
- `KERNEL32!GetLastError` at `0x18000a2d5`
- `KERNEL32!GetLastError` at `0x18000a332`
- `KERNEL32!GetLastError` at `0x18000a373`
- `KERNEL32!CloseHandle` at `0x18000a5c4`
- `KERNEL32!CloseHandle` at `0x18000a5d3`
- `KERNEL32!CloseHandle` at `0x18000a5c4`
- `KERNEL32!CloseHandle` at `0x18000a5d3`
- `KERNEL32!CreateFileW` at `0x18000a2c1`
- `KERNEL32!CreateFileW` at `0x18000a2c1`

## string_xrefs

- `0x18000a2db`: `Failed to open file [%d]`
- `0x18000a3da`: `Failed to read PE [%d]`
- `0x18000a570`: `Exception while reading PE [%d]`
- `0x18000a54a`: `Failed to set data for attribute AHG_TAG_PE_NXCOMPAT`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetPE(const WCHAR *a1, void *a2)
{
  __int64 v3; // r14
  void *v4; // r12
  void *v5; // r15
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v8; // r9
  __int64 v9; // r8
  DWORD v10; // edi
  void *v11; // rax
  HANDLE FileMappingW; // rax
  DWORD PeHeaderInfo; // eax
  const char *v14; // r9
  __int64 v15; // r8
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-B8h]
  unsigned int v18; // [rsp+40h] [rbp-98h] BYREF
  void *v19; // [rsp+48h] [rbp-90h]
  int v20; // [rsp+50h] [rbp-88h] BYREF
  int v21; // [rsp+54h] [rbp-84h] BYREF
  int v22; // [rsp+58h] [rbp-80h] BYREF
  int v23; // [rsp+5Ch] [rbp-7Ch] BYREF
  __int64 v24; // [rsp+60h] [rbp-78h] BYREF
  DWORD v25; // [rsp+68h] [rbp-70h]
  __int64 v26; // [rsp+78h] [rbp-60h]
  HANDLE v27; // [rsp+80h] [rbp-58h]
  void *v28; // [rsp+88h] [rbp-50h]
  void *v29; // [rsp+90h] [rbp-48h]
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-40h] BYREF

  v19 = a2;
  v29 = a2;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v18 = 0;
  SystemTime = 0;
  v3 = -1;
  v26 = -1;
  v4 = a2;
  v28 = a2;
  v5 = 0;
  v27 = 0;
  LODWORD(v24) = 0;
  if ( a2 )
    goto LABEL_10;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = (__int64)FileW;
  v26 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 0x11000002u, 0, 0, 0);
    v5 = FileMappingW;
    v27 = FileMappingW;
    if ( !FileMappingW )
    {
      LastError = GetLastError();
      v8 = "Failed to map file [%d]";
      v9 = 425;
      goto LABEL_4;
    }
    v4 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v28 = v4;
    if ( !v4 )
    {
      v10 = GetLastError();
      AslLogCallPrintf(1, "AhgGenomeGetPE", 437, "Failed to map a view of file mapping [%d]", v10);
      goto LABEL_9;
    }
LABEL_10:
    PeHeaderInfo = AhgGetPeHeaderInfo((int)&v20, (int)&v21, (int)&v22, (int)&v23, (__int64)&v24, v4);
    v10 = PeHeaderInfo;
    v25 = PeHeaderInfo;
    if ( PeHeaderInfo )
    {
      AslLogCallPrintf(2, "AhgGenomeGetPE", 451, "Failed to read PE [%d]", PeHeaderInfo);
      v11 = v19;
      goto LABEL_29;
    }
    GetLocalTime(&SystemTime);
    if ( (unsigned int)v20 < 0x7C8
      || v20 > (unsigned int)SystemTime.wYear
      || (unsigned int)AhgpSetAttribute(a1 + 340, 10, &v20) )
    {
      v18 = HIWORD(v21) + ((unsigned __int16)v21 << 16);
      if ( v18 <= 0x10000 || (unsigned int)AhgpSetAttribute(a1 + 348, 11, &v18) )
      {
        v18 = HIWORD(v22) + ((unsigned __int16)v22 << 16);
        if ( v18 <= 0x10000 || (unsigned int)AhgpSetAttribute(a1 + 356, 12, &v18) )
        {
          v18 = HIWORD(v23) + ((unsigned __int16)v23 << 16);
          if ( !v18 || (unsigned int)AhgpSetAttribute(a1 + 364, 13, &v18) )
          {
            if ( (unsigned int)AhgpSetAttribute(a1 + 372, 14, &v24) )
            {
              v10 = 0;
              goto LABEL_9;
            }
            v14 = "Failed to set data for attribute AHG_TAG_PE_NXCOMPAT";
            v15 = 521;
          }
          else
          {
            v14 = "Failed to set data for attribute AHG_TAG_PE_SUBSYSTEM_VERSION";
            v15 = 511;
          }
        }
        else
        {
          v14 = "Failed to set data for attribute AHG_TAG_PE_SUBSYSTEM_VERSION";
          v15 = 499;
        }
      }
      else
      {
        v14 = "Failed to set data for attribute AHG_TAG_PE_OS_VERSION";
        v15 = 487;
      }
    }
    else
    {
      v14 = "Failed to set data for attribute AHG_TAG_PE_TIME_DATE_STAMP_YEAR";
      v15 = 475;
    }
    v10 = 87;
    AslLogCallPrintf(1, "AhgGenomeGetPE", v15, v14);
LABEL_9:
    v11 = v19;
    goto LABEL_29;
  }
  LastError = GetLastError();
  v8 = "Failed to open file [%d]";
  v9 = 412;
LABEL_4:
  dwCreationDisposition[0] = LastError;
  v10 = LastError;
  AslLogCallPrintf(1, "AhgGenomeGetPE", v9, v8, *(_QWORD *)dwCreationDisposition);
  v11 = 0;
LABEL_29:
  if ( v4 && !v11 )
    UnmapViewOfFile(v4);
  if ( v5 )
    CloseHandle(v5);
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  return v10;
}

```

## disassembly

```asm
0x18000a208  mov     r11, rsp
0x18000a20b  mov     [r11+18h], rsi
0x18000a20f  push    rdi
0x18000a210  push    r12
0x18000a212  push    r13
0x18000a214  push    r14
0x18000a216  push    r15
0x18000a218  sub     rsp, 0B0h
0x18000a21f  mov     rax, cs:__security_cookie
0x18000a226  xor     rax, rsp
0x18000a229  mov     [rsp+0D8h+var_30], rax
0x18000a231  mov     [rsp+0D8h+var_90], rdx
0x18000a236  mov     r13, rcx
0x18000a239  mov     [rsp+0D8h+var_48], rdx
0x18000a241  mov     [rsp+0D8h+var_88], 0
0x18000a249  mov     [rsp+0D8h+var_84], 0
0x18000a251  mov     [rsp+0D8h+var_80], 0
0x18000a259  mov     [rsp+0D8h+var_7C], 0
0x18000a261  mov     [rsp+0D8h+var_98], 0
0x18000a269  xorps   xmm0, xmm0
0x18000a26c  movups  xmmword ptr [r11-40h], xmm0
0x18000a271  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a275  mov     [rsp+0D8h+var_60], r14
0x18000a27a  mov     r12, rdx
0x18000a27d  mov     [rsp+0D8h+var_50], rdx
0x18000a285  xor     r15d, r15d
0x18000a288  mov     [rsp+0D8h+var_58], r15
0x18000a290  mov     [r11-78h], r15d
0x18000a294  lea     esi, [r14+2]
0x18000a298  test    rdx, rdx
0x18000a29b  jnz     loc_18000A3A4
0x18000a2a1  mov     [rsp+0D8h+hTemplateFile], r15; hTemplateFile
0x18000a2a6  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000a2ae  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a2b6  xor     r9d, r9d; lpSecurityAttributes
0x18000a2b9  mov     r8d, esi; dwShareMode
0x18000a2bc  mov     edx, 80000000h; dwDesiredAccess
0x18000a2c1  call    cs:__imp_CreateFileW
0x18000a2c7  mov     r14, rax
0x18000a2ca  mov     [rsp+0D8h+var_60], rax
0x18000a2cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a2d3  jnz     short loc_18000A304
0x18000a2d5  call    cs:__imp_GetLastError
0x18000a2db  lea     r9, aFailedToOpenFi; "Failed to open file [%d]"
0x18000a2e2  mov     r8d, 19Ch
0x18000a2e8  mov     [rsp+0D8h+dwCreationDisposition], eax
0x18000a2ec  mov     edi, eax
0x18000a2ee  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x18000a2f5  mov     ecx, esi
0x18000a2f7  call    AslLogCallPrintf
0x18000a2fc  mov     rax, r12
0x18000a2ff  jmp     loc_18000A5A9
0x18000a304  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], r15; lpName
0x18000a309  mov     [rsp+0D8h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x18000a30e  xor     r9d, r9d; dwMaximumSizeHigh
0x18000a311  xor     edx, edx; lpFileMappingAttributes
0x18000a313  mov     r8d, 11000002h; flProtect
0x18000a319  mov     rcx, rax; hFile
0x18000a31c  call    cs:__imp_CreateFileMappingW
0x18000a322  mov     r15, rax
0x18000a325  mov     [rsp+0D8h+var_58], rax
0x18000a32d  test    rax, rax
0x18000a330  jnz     short loc_18000A347
0x18000a332  call    cs:__imp_GetLastError
0x18000a338  lea     r9, aFailedToMapFil; "Failed to map file [%d]"
0x18000a33f  mov     r8d, 1A9h
0x18000a345  jmp     short loc_18000A2E8
0x18000a347  mov     qword ptr [rsp+0D8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000a350  xor     r9d, r9d; dwFileOffsetLow
0x18000a353  xor     r8d, r8d; dwFileOffsetHigh
0x18000a356  lea     edx, [r9+4]; dwDesiredAccess
0x18000a35a  mov     rcx, rax; hFileMappingObject
0x18000a35d  call    cs:__imp_MapViewOfFile
0x18000a363  mov     r12, rax
0x18000a366  mov     [rsp+0D8h+var_50], rax
0x18000a36e  test    rax, rax
0x18000a371  jnz     short loc_18000A3A4
0x18000a373  call    cs:__imp_GetLastError
0x18000a379  mov     edi, eax
0x18000a37b  mov     [rsp+0D8h+dwCreationDisposition], eax
0x18000a37f  lea     r9, aFailedToMapAVi; "Failed to map a view of file mapping [%"...
0x18000a386  mov     r8d, 1B5h
0x18000a38c  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x18000a393  mov     ecx, esi
0x18000a395  call    AslLogCallPrintf
0x18000a39a  mov     rax, [rsp+0D8h+var_90]
0x18000a39f  jmp     loc_18000A5A9
0x18000a3a4  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], r12; BaseAddress
0x18000a3a9  lea     rax, [rsp+0D8h+var_78]
0x18000a3ae  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax; __int64
0x18000a3b3  lea     r9, [rsp+0D8h+var_7C]; int
0x18000a3b8  lea     r8, [rsp+0D8h+var_80]; int
0x18000a3bd  lea     rdx, [rsp+0D8h+var_84]; int
0x18000a3c2  lea     rcx, [rsp+0D8h+var_88]; int
0x18000a3c7  call    AhgGetPeHeaderInfo
0x18000a3cc  mov     edi, eax
0x18000a3ce  mov     [rsp+0D8h+var_70], eax
0x18000a3d2  test    eax, eax
0x18000a3d4  jz      short loc_18000A402
0x18000a3d6  mov     [rsp+0D8h+dwCreationDisposition], eax
0x18000a3da  lea     r9, aFailedToReadPe; "Failed to read PE [%d]"
0x18000a3e1  mov     r8d, 1C3h
0x18000a3e7  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x18000a3ee  mov     ecx, 2
0x18000a3f3  call    AslLogCallPrintf
0x18000a3f8  mov     rax, [rsp+0D8h+var_90]
0x18000a3fd  jmp     loc_18000A5A9
0x18000a402  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x18000a40a  call    cs:__imp_GetLocalTime
0x18000a410  cmp     [rsp+0D8h+var_88], 7C8h
0x18000a418  jb      short loc_18000A467
0x18000a41a  movzx   eax, [rsp+0D8h+SystemTime.wYear]
0x18000a422  cmp     [rsp+0D8h+var_88], eax
0x18000a426  ja      short loc_18000A467
0x18000a428  mov     edx, 0Ah
0x18000a42d  lea     rcx, [r13+2A8h]
0x18000a434  lea     r8, [rsp+0D8h+var_88]
0x18000a439  call    AhgpSetAttribute
0x18000a43e  test    eax, eax
0x18000a440  jnz     short loc_18000A467
0x18000a442  lea     r9, aFailedToSetDat_1; "Failed to set data for attribute AHG_TA"...
0x18000a449  mov     r8d, 1DBh
0x18000a44f  mov     edi, 57h ; 'W'
0x18000a454  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x18000a45b  mov     ecx, esi
0x18000a45d  call    AslLogCallPrintf
0x18000a462  jmp     loc_18000A39A
0x18000a467  movzx   ecx, word ptr [rsp+0D8h+var_84]
0x18000a46c  shl     ecx, 10h
0x18000a46f  movzx   eax, word ptr [rsp+0D8h+var_84+2]
0x18000a474  add     ecx, eax
0x18000a476  mov     [rsp+0D8h+var_98], ecx
0x18000a47a  mov     edi, 10000h
0x18000a47f  cmp     ecx, edi
0x18000a481  jbe     short loc_18000A4AC
0x18000a483  mov     edx, 0Bh
0x18000a488  lea     rcx, [r13+2B8h]
0x18000a48f  lea     r8, [rsp+0D8h+var_98]
0x18000a494  call    AhgpSetAttribute
0x18000a499  test    eax, eax
0x18000a49b  jnz     short loc_18000A4AC
0x18000a49d  lea     r9, aFailedToSetDat_3; "Failed to set data for attribute AHG_TA"...
0x18000a4a4  mov     r8d, 1E7h
0x18000a4aa  jmp     short loc_18000A44F
0x18000a4ac  movzx   ecx, word ptr [rsp+0D8h+var_80]
0x18000a4b1  shl     ecx, 10h
0x18000a4b4  movzx   eax, word ptr [rsp+0D8h+var_80+2]
0x18000a4b9  add     ecx, eax
0x18000a4bb  mov     [rsp+0D8h+var_98], ecx
0x18000a4bf  cmp     ecx, edi
0x18000a4c1  jbe     short loc_18000A4EF
0x18000a4c3  mov     edx, 0Ch
0x18000a4c8  lea     rcx, [r13+2C8h]
0x18000a4cf  lea     r8, [rsp+0D8h+var_98]
0x18000a4d4  call    AhgpSetAttribute
0x18000a4d9  test    eax, eax
0x18000a4db  jnz     short loc_18000A4EF
0x18000a4dd  lea     r9, aFailedToSetDat_2; "Failed to set data for attribute AHG_TA"...
0x18000a4e4  mov     r8d, 1F3h
0x18000a4ea  jmp     loc_18000A44F
0x18000a4ef  movzx   ecx, word ptr [rsp+0D8h+var_7C]
0x18000a4f4  shl     ecx, 10h
0x18000a4f7  movzx   eax, word ptr [rsp+0D8h+var_7C+2]
0x18000a4fc  add     ecx, eax
0x18000a4fe  mov     [rsp+0D8h+var_98], ecx
0x18000a502  jz      short loc_18000A530
0x18000a504  mov     edx, 0Dh
0x18000a509  lea     rcx, [r13+2D8h]
0x18000a510  lea     r8, [rsp+0D8h+var_98]
0x18000a515  call    AhgpSetAttribute
0x18000a51a  test    eax, eax
0x18000a51c  jnz     short loc_18000A530
0x18000a51e  lea     r9, aFailedToSetDat_2; "Failed to set data for attribute AHG_TA"...
0x18000a525  mov     r8d, 1FFh
0x18000a52b  jmp     loc_18000A44F
0x18000a530  mov     edx, 0Eh
0x18000a535  lea     rcx, [r13+2E8h]
0x18000a53c  lea     r8, [rsp+0D8h+var_78]
0x18000a541  call    AhgpSetAttribute
0x18000a546  test    eax, eax
0x18000a548  jnz     short loc_18000A55C
0x18000a54a  lea     r9, aFailedToSetDat_6; "Failed to set data for attribute AHG_TA"...
0x18000a551  mov     r8d, 209h
0x18000a557  jmp     loc_18000A44F
0x18000a55c  xor     edi, edi
0x18000a55e  jmp     loc_18000A39A
0x18000a563  mov     edi, 1Eh
0x18000a568  mov     [rsp+0D8h+var_70], edi
0x18000a56c  mov     [rsp+0D8h+dwCreationDisposition], edi
0x18000a570  lea     r9, aExceptionWhile_0; "Exception while reading PE [%d]"
0x18000a577  mov     r8d, 1C9h
0x18000a57d  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x18000a584  lea     ecx, [rdi-1Dh]
0x18000a587  call    AslLogCallPrintf
0x18000a58c  mov     r14, [rsp+0D8h+var_60]
0x18000a591  mov     r15, [rsp+0D8h+var_58]
0x18000a599  mov     r12, [rsp+0D8h+var_50]
0x18000a5a1  mov     rax, [rsp+0D8h+var_48]
0x18000a5a9  test    r12, r12
0x18000a5ac  jz      short loc_18000A5BC
0x18000a5ae  test    rax, rax
0x18000a5b1  jnz     short loc_18000A5BC
0x18000a5b3  mov     rcx, r12; lpBaseAddress
0x18000a5b6  call    cs:__imp_UnmapViewOfFile
0x18000a5bc  test    r15, r15
0x18000a5bf  jz      short loc_18000A5CA
0x18000a5c1  mov     rcx, r15; hObject
0x18000a5c4  call    cs:__imp_CloseHandle
0x18000a5ca  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000a5ce  jz      short loc_18000A5D9
0x18000a5d0  mov     rcx, r14; hObject
0x18000a5d3  call    cs:__imp_CloseHandle
0x18000a5d9  mov     eax, edi
0x18000a5db  mov     rcx, [rsp+0D8h+var_30]
0x18000a5e3  xor     rcx, rsp; StackCookie
0x18000a5e6  call    __security_check_cookie
0x18000a5eb  mov     rsi, [rsp+0D8h+arg_10]
0x18000a5f3  add     rsp, 0B0h
0x18000a5fa  pop     r15
0x18000a5fc  pop     r14
0x18000a5fe  pop     r13
0x18000a600  pop     r12
0x18000a602  pop     rdi
0x18000a603  retn
0x180019656  push    rbp
0x180019658  sub     rsp, 40h
0x18001965c  mov     rbp, rdx
0x18001965f  mov     [rbp+70h], rcx
0x180019663  mov     rax, [rbp+70h]
0x180019667  mov     rcx, [rax]
0x18001966a  cmp     dword ptr [rcx], 0C0000006h
0x180019670  jz      short loc_18001968A
0x180019672  mov     rax, [rbp+70h]
0x180019676  mov     rcx, [rax]
0x180019679  cmp     dword ptr [rcx], 0C0000005h
0x18001967f  jz      short loc_18001968A
0x180019681  mov     dword ptr [rbp+64h], 0
0x180019688  jmp     short loc_180019691
0x18001968a  mov     dword ptr [rbp+64h], 1
0x180019691  mov     eax, [rbp+64h]
0x180019694  add     rsp, 40h
0x180019698  pop     rbp
0x180019699  retn
```
