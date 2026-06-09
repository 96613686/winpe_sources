# GetCatalogPathFromFilePath(ushort const *,int)

- ea: `0x1800c8948`
- end: `0x1800c8bde`
- name: `?GetCatalogPathFromFilePath@@YAPEAGPEBGH@Z`
- size: `662`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18006f388`
- `0x1800b81d0`

## callees

- `0x180034748`
- `0x180046650`
- `0x180047330`
- `0x1800c8908`
- `0x1800c8948`
- `0x1800c954c`
- `0x1800c9854`
- `0x1800c9978`
- `0x1800c9a20`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800c8b03`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800c8b03`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800c8a36`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800c8a36`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800c8b91`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800c8b91`
- `SPOOLSS!DllFreeSplMem` at `0x1800c8b13`
- `SPOOLSS!DllFreeSplMem` at `0x1800c8b5c`
- `SPOOLSS!DllFreeSplMem` at `0x1800c8bb2`
- `SPOOLSS!DllFreeSplMem` at `0x1800c8b13`
- `SPOOLSS!DllFreeSplMem` at `0x1800c8b5c`
- `SPOOLSS!DllFreeSplMem` at `0x1800c8bb2`
- `SPOOLSS!DllAllocSplMem` at `0x1800c89b0`
- `SPOOLSS!DllAllocSplMem` at `0x1800c8a7d`
- `SPOOLSS!DllAllocSplMem` at `0x1800c89b0`
- `SPOOLSS!DllAllocSplMem` at `0x1800c8a7d`

## string_xrefs

- `0x1800c8b2c`: `GetCatalogPathFromFilePath`
- `0x1800c8b4d`: `GetCatalogPathFromFilePath`
- `0x1800c8b82`: `GetCatalogPathFromFilePath`
- `0x1800c8ba3`: `GetCatalogPathFromFilePath`
- `0x1800c8b46`: `Error creating catalog path %ws, %ws.`
- `0x1800c8b7b`: `Error allocating memory for catalog path %ws, %ws.`

## pseudocode

```c
unsigned __int16 *__fastcall GetCatalogPathFromFilePath(const unsigned __int16 *a1, int a2)
{
  unsigned __int16 *v2; // rbx
  const unsigned __int16 *FileName; // rax
  const unsigned __int16 *v5; // r15
  unsigned __int64 v6; // rdi
  WCHAR *v7; // r12
  HANDLE FirstFileW; // r13
  unsigned int v9; // r14d
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  int v13; // eax
  unsigned int v15; // [rsp+28h] [rbp-D8h]
  unsigned int v16; // [rsp+28h] [rbp-D8h]
  unsigned int v17; // [rsp+30h] [rbp-D0h]
  unsigned int v18; // [rsp+30h] [rbp-D0h]
  unsigned int v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+50h] [rbp-B0h]
  unsigned int v22[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v21 = a2;
  v2 = 0;
  v20 = 0;
  FileName = FindFileName(a1);
  v5 = FileName;
  if ( FileName )
  {
    v6 = 2 * (FileName - a1);
    *(_QWORD *)v19 = v6 + 12;
    v7 = (WCHAR *)DllAllocSplMem((unsigned int)(v6 + 12));
    if ( v7
      && StringCbCopyNExW(v7, v6 + 12, a1, v6, &v20, (unsigned __int64 *)v19, v17) >= 0
      && StringCbCopyExW(v20, *(unsigned __int64 *)v19, L"*.cat", &v20, (unsigned __int64 *)v19, v15) >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(v7, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        SplLibTelemetry::WriteDbgTraceError("GetCatalogPathFromFilePath", L"No catalog file found for %ws.", v5);
      }
      else
      {
        v9 = 1;
        v19[0] = 1;
        while ( v9 )
        {
          v10 = -1;
          do
            ++v10;
          while ( FindFileData.cFileName[v10] );
          v11 = v10 + 1;
          v12 = v6 + 2 * v11;
          *(_QWORD *)v22 = v12;
          v2 = (unsigned __int16 *)DllAllocSplMem((unsigned int)(v6 + 2 * v11));
          if ( !v2 )
          {
            SplLibTelemetry::WriteDbgTraceError(
              "GetCatalogPathFromFilePath",
              L"Error allocating memory for catalog path %ws, %ws.",
              a1,
              FindFileData.cFileName);
            break;
          }
          v13 = StringCbCopyNExW(v2, v12, a1, v6, &v20, (unsigned __int64 *)v22, v18);
          v9 = 0;
          if ( v13 < 0
            || StringCbCopyExW(
                 v20,
                 *(unsigned __int64 *)v22,
                 FindFileData.cFileName,
                 &v20,
                 (unsigned __int64 *)v22,
                 v16) < 0 )
          {
            SplLibTelemetry::WriteDbgTraceError(
              "GetCatalogPathFromFilePath",
              L"Error creating catalog path %ws, %ws.",
              a1,
              FindFileData.cFileName);
            DllFreeSplMem(v2);
            v2 = 0;
            v19[0] = 0;
          }
          else if ( v21 != 1 || LegacyVerifyFileSignature(a1, v2) )
          {
            SplLibTelemetry::WriteDbgTraceInfo("GetCatalogPathFromFilePath", L"Using catalog file %ws for  %ws", v2, v5);
            v9 = v19[0];
          }
          else
          {
            v19[0] = FindNextFileW(FirstFileW, &FindFileData);
            v9 = v19[0];
            DllFreeSplMem(v2);
            v2 = 0;
          }
          if ( v2 )
            break;
        }
        FindClose(FirstFileW);
      }
    }
    DllFreeSplMem(v7);
  }
  return v2;
}

```

## disassembly

```asm
0x1800c8948  push    rbp
0x1800c894a  push    rbx
0x1800c894b  push    rsi
0x1800c894c  push    rdi
0x1800c894d  push    r12
0x1800c894f  push    r13
0x1800c8951  push    r14
0x1800c8953  push    r15
0x1800c8955  lea     rbp, [rsp-1C8h]
0x1800c895d  sub     rsp, 2C8h
0x1800c8964  mov     rax, cs:__security_cookie
0x1800c896b  xor     rax, rsp
0x1800c896e  mov     [rbp+200h+var_50], rax
0x1800c8975  xor     r13d, r13d
0x1800c8978  mov     [rsp+300h+var_2B0], edx
0x1800c897c  mov     ebx, r13d
0x1800c897f  mov     [rsp+300h+var_2B8], r13
0x1800c8984  mov     rsi, rcx
0x1800c8987  call    ?FindFileName@@YAPEBGPEBG@Z; FindFileName(ushort const *)
0x1800c898c  mov     r15, rax
0x1800c898f  test    rax, rax
0x1800c8992  jz      loc_1800C8BB8
0x1800c8998  mov     rdi, rax
0x1800c899b  sub     rdi, rsi
0x1800c899e  sar     rdi, 1
0x1800c89a1  add     rdi, rdi
0x1800c89a4  lea     r14, [rdi+0Ch]
0x1800c89a8  mov     ecx, r14d
0x1800c89ab  mov     qword ptr [rsp+300h+var_2C0], r14
0x1800c89b0  call    cs:__imp_DllAllocSplMem
0x1800c89b6  mov     r12, rax
0x1800c89b9  test    rax, rax
0x1800c89bc  jz      loc_1800C8BAF
0x1800c89c2  lea     rax, [rsp+300h+var_2C0]
0x1800c89c7  mov     r9, rdi; unsigned __int64
0x1800c89ca  mov     [rsp+300h+var_2D8], rax; unsigned int
0x1800c89cf  mov     r8, rsi; unsigned __int16 *
0x1800c89d2  lea     rax, [rsp+300h+var_2B8]
0x1800c89d7  mov     rdx, r14; unsigned __int64
0x1800c89da  mov     rcx, r12; unsigned __int16 *
0x1800c89dd  mov     [rsp+300h+var_2E0], rax; unsigned __int16 **
0x1800c89e2  call    ?StringCbCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCbCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800c89e7  test    eax, eax
0x1800c89e9  js      loc_1800C8BAF
0x1800c89ef  mov     rdx, qword ptr [rsp+300h+var_2C0]; unsigned __int64
0x1800c89f4  lea     rax, [rsp+300h+var_2C0]
0x1800c89f9  mov     rcx, [rsp+300h+var_2B8]; unsigned __int16 *
0x1800c89fe  lea     r9, [rsp+300h+var_2B8]; unsigned __int16 **
0x1800c8a03  lea     r8, aCat; "*.cat"
0x1800c8a0a  mov     [rsp+300h+var_2E0], rax; unsigned __int64 *
0x1800c8a0f  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800c8a14  test    eax, eax
0x1800c8a16  js      loc_1800C8BAF
0x1800c8a1c  xor     edx, edx; Val
0x1800c8a1e  lea     rcx, [rsp+300h+FindFileData]; void *
0x1800c8a23  mov     r8d, 250h; Size
0x1800c8a29  call    memset_0
0x1800c8a2e  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x1800c8a33  mov     rcx, r12; lpFileName
0x1800c8a36  call    cs:__imp_FindFirstFileW
0x1800c8a3c  mov     r13, rax
0x1800c8a3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c8a43  jz      loc_1800C8B99
0x1800c8a49  lea     r14d, [rbx+1]
0x1800c8a4d  xor     ecx, ecx
0x1800c8a4f  mov     [rsp+300h+var_2C0], r14d
0x1800c8a54  test    r14d, r14d
0x1800c8a57  jz      loc_1800C8B8E
0x1800c8a5d  lea     rdx, [rbp+200h+FindFileData.cFileName]
0x1800c8a61  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c8a65  inc     rax
0x1800c8a68  cmp     [rdx+rax*2], cx
0x1800c8a6c  jnz     short loc_1800C8A65
0x1800c8a6e  inc     rax
0x1800c8a71  lea     r14, [rdi+rax*2]
0x1800c8a75  mov     ecx, r14d
0x1800c8a78  mov     qword ptr [rsp+300h+var_2A8], r14
0x1800c8a7d  call    cs:__imp_DllAllocSplMem
0x1800c8a83  mov     rbx, rax
0x1800c8a86  mov     r8, rsi; unsigned __int16 *
0x1800c8a89  test    rax, rax
0x1800c8a8c  jz      loc_1800C8B77
0x1800c8a92  lea     rax, [rsp+300h+var_2A8]
0x1800c8a97  mov     r9, rdi; unsigned __int64
0x1800c8a9a  mov     [rsp+300h+var_2D8], rax; unsigned int
0x1800c8a9f  mov     rdx, r14; unsigned __int64
0x1800c8aa2  lea     rax, [rsp+300h+var_2B8]
0x1800c8aa7  mov     rcx, rbx; unsigned __int16 *
0x1800c8aaa  mov     [rsp+300h+var_2E0], rax; unsigned __int16 **
0x1800c8aaf  call    ?StringCbCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCbCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800c8ab4  xor     r14d, r14d
0x1800c8ab7  test    eax, eax
0x1800c8ab9  js      loc_1800C8B3F
0x1800c8abf  mov     rdx, qword ptr [rsp+300h+var_2A8]; unsigned __int64
0x1800c8ac4  lea     rax, [rsp+300h+var_2A8]
0x1800c8ac9  mov     rcx, [rsp+300h+var_2B8]; unsigned __int16 *
0x1800c8ace  lea     r9, [rsp+300h+var_2B8]; unsigned __int16 **
0x1800c8ad3  lea     r8, [rbp+200h+FindFileData.cFileName]; unsigned __int16 *
0x1800c8ad7  mov     [rsp+300h+var_2E0], rax; unsigned __int64 *
0x1800c8adc  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800c8ae1  test    eax, eax
0x1800c8ae3  js      short loc_1800C8B3F
0x1800c8ae5  cmp     [rsp+300h+var_2B0], 1
0x1800c8aea  jnz     short loc_1800C8B1F
0x1800c8aec  mov     rdx, rbx; unsigned __int16 *
0x1800c8aef  mov     rcx, rsi; unsigned __int16 *
0x1800c8af2  call    ?LegacyVerifyFileSignature@@YAHPEBG0@Z; LegacyVerifyFileSignature(ushort const *,ushort const *)
0x1800c8af7  test    eax, eax
0x1800c8af9  jnz     short loc_1800C8B1F
0x1800c8afb  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x1800c8b00  mov     rcx, r13; hFindFile
0x1800c8b03  call    cs:__imp_FindNextFileW
0x1800c8b09  mov     rcx, rbx
0x1800c8b0c  mov     [rsp+300h+var_2C0], eax
0x1800c8b10  mov     r14d, eax
0x1800c8b13  call    cs:__imp_DllFreeSplMem
0x1800c8b19  xor     ecx, ecx
0x1800c8b1b  mov     ebx, ecx
0x1800c8b1d  jmp     short loc_1800C8B6C
0x1800c8b1f  mov     r9, r15
0x1800c8b22  lea     rdx, aUsingCatalogFi; "Using catalog file %ws for  %ws"
0x1800c8b29  mov     r8, rbx
0x1800c8b2c  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x1800c8b33  call    ?WriteDbgTraceInfo@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c8b38  mov     r14d, [rsp+300h+var_2C0]
0x1800c8b3d  jmp     short loc_1800C8B6A
0x1800c8b3f  lea     r9, [rbp+200h+FindFileData.cFileName]
0x1800c8b43  mov     r8, rsi
0x1800c8b46  lea     rdx, aErrorCreatingC; "Error creating catalog path %ws, %ws."
0x1800c8b4d  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x1800c8b54  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c8b59  mov     rcx, rbx
0x1800c8b5c  call    cs:__imp_DllFreeSplMem
0x1800c8b62  mov     rbx, r14
0x1800c8b65  mov     [rsp+300h+var_2C0], r14d
0x1800c8b6a  xor     ecx, ecx
0x1800c8b6c  test    rbx, rbx
0x1800c8b6f  jz      loc_1800C8A54
0x1800c8b75  jmp     short loc_1800C8B8E
0x1800c8b77  lea     r9, [rbp+200h+FindFileData.cFileName]
0x1800c8b7b  lea     rdx, aErrorAllocatin; "Error allocating memory for catalog pat"...
0x1800c8b82  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x1800c8b89  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c8b8e  mov     rcx, r13; hFindFile
0x1800c8b91  call    cs:__imp_FindClose
0x1800c8b97  jmp     short loc_1800C8BAF
0x1800c8b99  mov     r8, r15
0x1800c8b9c  lea     rdx, aNoCatalogFileF; "No catalog file found for %ws."
0x1800c8ba3  lea     rcx, aGetcatalogpath; "GetCatalogPathFromFilePath"
0x1800c8baa  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c8baf  mov     rcx, r12
0x1800c8bb2  call    cs:__imp_DllFreeSplMem
0x1800c8bb8  mov     rax, rbx
0x1800c8bbb  mov     rcx, [rbp+200h+var_50]
0x1800c8bc2  xor     rcx, rsp; StackCookie
0x1800c8bc5  call    __security_check_cookie
0x1800c8bca  add     rsp, 2C8h
0x1800c8bd1  pop     r15
0x1800c8bd3  pop     r14
0x1800c8bd5  pop     r13
0x1800c8bd7  pop     r12
0x1800c8bd9  pop     rdi
0x1800c8bda  pop     rsi
0x1800c8bdb  pop     rbx
0x1800c8bdc  pop     rbp
0x1800c8bdd  retn
```
