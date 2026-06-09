# SyncActionCopyUsingDiffTxf

- ea: `0x18007d6d8`
- end: `0x18007dd74`
- name: `SyncActionCopyUsingDiffTxf`
- size: `1692`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, HANDLE hHandle@<rdx>, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x180077bc0`

## callees

- `0x18001fb40`
- `0x180020f2c`
- `0x1800223c0`
- `0x18002d8ec`
- `0x180030aec`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18003e928`
- `0x18007291c`
- `0x180072b28`
- `0x1800730d4`
- `0x180073a00`
- `0x180076090`
- `0x180076cd8`
- `0x18007cc48`
- `0x18007d2b0`
- `0x18007d6d8`
- `0x18007de5c`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x18007d9bd`
- `KERNEL32!VirtualFree` at `0x18007dcf0`
- `KERNEL32!VirtualFree` at `0x18007d9bd`
- `KERNEL32!VirtualFree` at `0x18007dcf0`

## string_xrefs

- `0x18007d744`: `SyncActionCopyClientToServer: OpArgs 0x%p ClientHandle 0x%p ServerHandle 0x%p SyncActionCopyOption %u`
- `0x18007dc50`: `SyncActionCopyClientToServer: SyncStoreQueryDiffTransferOffsets failed with 0x%x`
- `0x18007daeb`: `SyncActionCopyClientToServer: SyncStoreQueryDiffTransferOffsets copy whole file`
- `0x18007dcae`: `SyncActionCopyClientToServer: SyncActionCopyToAlternateStream failed with 0x%x`
- `0x18007d8b5`: `Trying to sync using copy chunk FSCTL`
- `0x18007db47`: `SyncActionCopyClientToServer: SyncActionCopyFileFromOffset return error 0x%x`
- `0x18007da94`: `Error using copy chunk FSCTL to copy file , status = 0x%08x`
- `0x18007dd26`: `SyncActionCopyClientToServer: 0x%08x ( EE = %u )`

## pseudocode

```c
__int64 __fastcall SyncActionCopyUsingDiffTxf(__int64 a1, HANDLE hHandle, HANDLE *a3, unsigned __int8 a4, int a5)
{
  HANDLE v5; // r15
  HANDLE v6; // r12
  __int64 v9; // r14
  int v10; // ebx
  _BYTE *v11; // rsi
  __int64 v12; // r8
  __int64 v13; // rax
  int DiffTransferOffsets; // ebx
  int v15; // eax
  int FileSize; // ebx
  int ResumeKey; // ebx
  unsigned int v18; // edi
  unsigned int i; // r14d
  __int64 v20; // rcx
  LARGE_INTEGER v21; // r9
  bool v22; // zf
  int v23; // r14d
  __int64 v24; // r12
  int v25; // r14d
  LPOLESTR lpsz; // [rsp+28h] [rbp-58h]
  unsigned int lpsza; // [rsp+28h] [rbp-58h]
  char v29; // [rsp+40h] [rbp-40h]
  _BYTE v30[15]; // [rsp+41h] [rbp-3Fh] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h]
  int v32[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+60h] [rbp-20h] BYREF
  __int128 v34; // [rsp+68h] [rbp-18h] BYREF
  __int64 v35; // [rsp+78h] [rbp-8h]

  v5 = 0;
  v31 = 0;
  v6 = 0;
  *(_QWORD *)v32 = 0;
  v35 = 0;
  v30[0] = 0;
  v9 = a1;
  v34 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    v10 = a4;
    SyncTraceOutputInternal(
      L"SyncActionCopyClientToServer: OpArgs 0x%p ClientHandle 0x%p ServerHandle 0x%p SyncActionCopyOption %u",
      a1,
      hHandle,
      a3,
      a4);
    WPP_SF_qqqD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      56,
      WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
      v9,
      hHandle,
      a3,
      v10);
  }
  while ( 1 )
  {
    v11 = (_BYTE *)SyncLargeAlloc(1608);
    if ( !v11 )
      break;
    v13 = 0;
    v29 = 0;
    *(_QWORD *)&v30[7] = 0;
    while ( 2 )
    {
      DiffTransferOffsets = SyncStoreQueryDiffTransferOffsets(hHandle, v13, v12, v11);
      if ( DiffTransferOffsets < 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncActionCopyClientToServer: SyncStoreQueryDiffTransferOffsets failed with 0x%x",
            (unsigned int)DiffTransferOffsets);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            57,
            WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
            (unsigned int)DiffTransferOffsets);
        }
        goto LABEL_75;
      }
      if ( !*(_QWORD *)&v30[7] && *(_DWORD *)v11 == 1 && !v11[4] && !*((_QWORD *)v11 + 1) && !*((_DWORD *)v11 + 4) )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCopyClientToServer: SyncStoreQueryDiffTransferOffsets copy whole file");
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 58, WPP_6245c1b01f713a032f327efa2846a355_Traceguids);
        }
LABEL_75:
        FileSize = SyncActionCopyFileToServer(v9, hHandle, a3, a4);
        if ( FileSize
          && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncActionCopyClientToServer: SyncActionCopyToAlternateStream failed with 0x%x",
            (unsigned int)FileSize);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            59,
            WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
            (unsigned int)FileSize);
        }
        v18 = 2234;
        goto LABEL_80;
      }
      if ( !v6 )
      {
        v15 = SyncActionpOpenTempFile(v9, *a3, (HANDLE *)v32, 0, 0, 0, 0);
        v5 = *(HANDLE *)v32;
        FileSize = v15;
        if ( v15 < 0 )
        {
          v18 = 2251;
          goto LABEL_80;
        }
        ResumeKey = SyncGetResumeKey(*(_QWORD *)v32, &v34);
        if ( ResumeKey >= 0 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(L"Trying to sync using copy chunk FSCTL");
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 61, WPP_6245c1b01f713a032f327efa2846a355_Traceguids);
          }
          v6 = v5;
          v29 = 1;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(L"Error obtaining resume key, status = 0x%08x", (unsigned int)ResumeKey);
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              60,
              WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
              (unsigned int)ResumeKey);
          }
          v6 = *a3;
          FileSize = SyncConvertBackoutHandle(v9 + 32, hHandle);
          if ( FileSize < 0 )
          {
            v18 = 2270;
            goto LABEL_80;
          }
        }
      }
      for ( i = 0; i < *(_DWORD *)v11; ++i )
      {
        *(_QWORD *)&v30[7] = *(_QWORD *)&v11[16 * i + 8];
        v20 = *(unsigned int *)&v11[16 * i + 16];
        if ( (_DWORD)v20 )
        {
          v21 = *(LARGE_INTEGER *)&v30[7];
        }
        else
        {
          FileSize = SyncGetFileSize(hHandle);
          if ( FileSize < 0 || !v31 )
          {
            v18 = 2295;
            goto LABEL_80;
          }
          v21 = *(LARGE_INTEGER *)&v30[7];
          v20 = v31 - *(_QWORD *)&v30[7];
        }
        v31 = v20;
        FileSize = SyncActionCopyFileFromOffset(a1, hHandle, v6, v21, v20, (__int64)lpsz, v29 == 0);
        if ( FileSize < 0 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(
              L"SyncActionCopyClientToServer: SyncActionCopyFileFromOffset return error 0x%x",
              (unsigned int)FileSize);
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              62,
              WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
              (unsigned int)FileSize);
          }
          v18 = 2320;
          goto LABEL_80;
        }
      }
      v13 = v31 + *(_QWORD *)&v30[7];
      v22 = v11[4] == 1;
      *(_QWORD *)&v30[7] += v31;
      if ( v22 )
      {
        v9 = a1;
        continue;
      }
      break;
    }
    if ( !v5 || v6 != v5 )
    {
      v25 = a5;
      v24 = a1;
LABEL_63:
      FileSize = SyncGetFileSize(hHandle);
      if ( FileSize >= 0 )
      {
        FileSize = SyncTruncateFile(*a3, v31);
        if ( FileSize >= 0 )
        {
          FileSize = SyncActionCopyAttributesWithAdjustment(
                       hHandle,
                       *a3,
                       (FILETIME *)(*(_QWORD *)(v24 + 16) + 104LL),
                       v25,
                       0,
                       0,
                       0,
                       0);
          if ( FileSize >= 0 )
          {
            v18 = 0;
            FileSize = 0;
          }
          else
          {
            v18 = 2440;
          }
        }
        else
        {
          v18 = 2428;
        }
      }
      else
      {
        v18 = 2425;
      }
      if ( !v11 )
        goto LABEL_82;
LABEL_80:
      ++NumLargeFree;
      VirtualFree(v11, 0, 0x8000u);
      goto LABEL_82;
    }
    v33 = 0;
    if ( a5 )
      v23 = 10000000 * a5;
    else
      v23 = 1;
    ++NumLargeFree;
    VirtualFree(v11, 0, 0x8000u);
    v24 = a1;
    FileSize = SyncConvertBackoutHandle(a1 + 32, hHandle);
    if ( FileSize < 0 )
    {
      v18 = 2342;
      goto LABEL_82;
    }
    lpsza = v23;
    v25 = a5;
    FileSize = SyncActionCopyAttributesWithAdjustment(
                 hHandle,
                 *a3,
                 (FILETIME *)(*(_QWORD *)(a1 + 16) + 104LL),
                 a5,
                 0,
                 lpsza,
                 0,
                 &v33);
    if ( FileSize < 0 )
    {
      v18 = 2361;
      goto LABEL_82;
    }
    FileSize = SyncActionSetOriginalTime(hHandle);
    if ( FileSize < 0 )
    {
      v18 = 2370;
      goto LABEL_82;
    }
    v11 = 0;
    FileSize = SyncActionCopyChunkFile(hHandle, (__int64)v30);
    SyncCloseFile(v5);
    v5 = 0;
    *(_QWORD *)v32 = 0;
    if ( FileSize >= 0 )
      goto LABEL_63;
    if ( !v30[0] )
    {
      v18 = 2413;
      goto LABEL_82;
    }
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"Error using copy chunk FSCTL to copy file , status = 0x%08x", (unsigned int)FileSize);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        63,
        WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
        (unsigned int)FileSize);
    }
    v6 = *a3;
    v9 = a1;
  }
  FileSize = -1073741670;
  v18 = 2166;
LABEL_82:
  SyncCloseFile(v5);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionCopyClientToServer: 0x%08x ( EE = %u )", (unsigned int)FileSize, v18);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      64,
      WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
      (unsigned int)FileSize,
      v18);
  }
  return (unsigned int)FileSize;
}

```

## disassembly

```asm
0x18007d6d8  mov     [rsp-38h+arg_8], rbx
0x18007d6dd  mov     [rsp-38h+arg_18], r9b
0x18007d6e2  mov     [rsp-38h+arg_0], rcx
0x18007d6e7  push    rbp
0x18007d6e8  push    rsi
0x18007d6e9  push    rdi
0x18007d6ea  push    r12
0x18007d6ec  push    r13
0x18007d6ee  push    r14
0x18007d6f0  push    r15
0x18007d6f2  mov     rbp, rsp
0x18007d6f5  sub     rsp, 80h
0x18007d6fc  xor     r15d, r15d
0x18007d6ff  mov     [rbp+var_30], 0
0x18007d707  xor     r12d, r12d
0x18007d70a  mov     qword ptr [rbp+var_28], r15
0x18007d70e  xor     eax, eax
0x18007d710  xorps   xmm0, xmm0
0x18007d713  mov     [rbp+var_8], rax
0x18007d717  mov     r13, r8
0x18007d71a  mov     [rbp+var_3F], al
0x18007d71d  mov     rdi, rdx
0x18007d720  mov     r14, rcx
0x18007d723  movups  [rbp+var_18], xmm0
0x18007d727  mov     rax, cs:WPP_GLOBAL_Control
0x18007d72e  lea     rcx, WPP_GLOBAL_Control
0x18007d735  cmp     rax, rcx
0x18007d738  jz      short loc_18007D78A
0x18007d73a  test    byte ptr [rax+6Ch], 4
0x18007d73e  jz      short loc_18007D78A
0x18007d740  movzx   ebx, r9b
0x18007d744  lea     rcx, aSyncactioncopy_17; "SyncActionCopyClientToServer: OpArgs 0x"...
0x18007d74b  mov     r9, r8
0x18007d74e  mov     dword ptr [rsp+80h+var_60], ebx
0x18007d752  mov     r8, rdx
0x18007d755  mov     rdx, r14
0x18007d758  call    SyncTraceOutputInternal
0x18007d75d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d764  lea     edx, [r12+38h]
0x18007d769  mov     dword ptr [rsp+80h+var_50], ebx
0x18007d76d  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18007d774  mov     [rsp+80h+lpsz], r13
0x18007d779  mov     r9, r14
0x18007d77c  mov     qword ptr [rsp+80h+var_60], rdi
0x18007d781  mov     rcx, [rcx+60h]
0x18007d785  call    WPP_SF_qqqD
0x18007d78a  mov     ecx, 648h
0x18007d78f  call    SyncLargeAlloc
0x18007d794  mov     rsi, rax
0x18007d797  test    rax, rax
0x18007d79a  jz      loc_18007DCF8
0x18007d7a0  xor     eax, eax
0x18007d7a2  mov     [rbp+var_40], 0
0x18007d7a6  mov     qword ptr [rbp+var_3F+7], rax
0x18007d7aa  jmp     short loc_18007D7B0
0x18007d7ac  mov     r14, [rbp+arg_0]
0x18007d7b0  mov     r9, rsi
0x18007d7b3  mov     rdx, rax
0x18007d7b6  mov     rcx, rdi
0x18007d7b9  call    SyncStoreQueryDiffTransferOffsets
0x18007d7be  mov     ebx, eax
0x18007d7c0  test    eax, eax
0x18007d7c2  js      loc_18007DC35
0x18007d7c8  cmp     qword ptr [rbp+var_3F+7], 0
0x18007d7cd  jnz     short loc_18007D7EB
0x18007d7cf  cmp     dword ptr [rsi], 1
0x18007d7d2  jnz     short loc_18007D7EB
0x18007d7d4  cmp     byte ptr [rsi+4], 0
0x18007d7d8  jnz     short loc_18007D7EB
0x18007d7da  cmp     qword ptr [rsi+8], 0
0x18007d7df  jnz     short loc_18007D7EB
0x18007d7e1  cmp     dword ptr [rsi+10h], 0
0x18007d7e5  jz      loc_18007DACA
0x18007d7eb  test    r12, r12
0x18007d7ee  jnz     loc_18007D8E4
0x18007d7f4  mov     rdx, [r13+0]; int
0x18007d7f8  lea     r8, [rbp+var_28]; int
0x18007d7fc  mov     dword ptr [rsp+80h+var_50], r12d; int
0x18007d801  xor     r9d, r9d; int
0x18007d804  mov     [rsp+80h+lpsz], r12; lpsz
0x18007d809  mov     rcx, r14; int
0x18007d80c  mov     qword ptr [rsp+80h+var_60], r12; __int64
0x18007d811  call    SyncActionpOpenTempFile
0x18007d816  mov     r15, qword ptr [rbp+var_28]
0x18007d81a  mov     ebx, eax
0x18007d81c  test    eax, eax
0x18007d81e  js      loc_18007DB18
0x18007d824  lea     rdx, [rbp+var_18]
0x18007d828  mov     rcx, r15
0x18007d82b  call    SyncGetResumeKey
0x18007d830  mov     ebx, eax
0x18007d832  test    eax, eax
0x18007d834  jns     short loc_18007D89C
0x18007d836  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d83d  lea     rax, WPP_GLOBAL_Control
0x18007d844  cmp     rcx, rax
0x18007d847  jz      short loc_18007D87C
0x18007d849  test    byte ptr [rcx+6Ch], 1
0x18007d84d  jz      short loc_18007D87C
0x18007d84f  mov     edx, ebx
0x18007d851  lea     rcx, aErrorObtaining; "Error obtaining resume key, status = 0x"...
0x18007d858  call    SyncTraceOutputInternal
0x18007d85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d864  lea     edx, [r12+3Ch]
0x18007d869  mov     r9d, ebx
0x18007d86c  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18007d873  mov     rcx, [rcx+60h]
0x18007d877  call    WPP_SF_d
0x18007d87c  mov     r12, [r13+0]
0x18007d880  lea     rcx, [r14+20h]
0x18007d884  mov     rdx, rdi
0x18007d887  call    SyncConvertBackoutHandle
0x18007d88c  mov     ebx, eax
0x18007d88e  test    eax, eax
0x18007d890  jns     short loc_18007D8E4
0x18007d892  mov     edi, 8DEh
0x18007d897  jmp     loc_18007DCDE
0x18007d89c  mov     rax, cs:WPP_GLOBAL_Control
0x18007d8a3  lea     rcx, WPP_GLOBAL_Control
0x18007d8aa  cmp     rax, rcx
0x18007d8ad  jz      short loc_18007D8DD
0x18007d8af  test    byte ptr [rax+6Ch], 1
0x18007d8b3  jz      short loc_18007D8DD
0x18007d8b5  lea     rcx, aTryingToSyncUs; "Trying to sync using copy chunk FSCTL"
0x18007d8bc  call    SyncTraceOutputInternal
0x18007d8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d8c8  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18007d8cf  mov     edx, 3Dh ; '='
0x18007d8d4  mov     rcx, [rcx+60h]
0x18007d8d8  call    WPP_SF_
0x18007d8dd  mov     r12, r15
0x18007d8e0  mov     [rbp+var_40], 1
0x18007d8e4  xor     r14d, r14d
0x18007d8e7  cmp     r14d, [rsi]
0x18007d8ea  jnb     short loc_18007D965
0x18007d8ec  mov     eax, r14d
0x18007d8ef  add     rax, rax
0x18007d8f2  mov     rcx, [rsi+rax*8+8]
0x18007d8f7  mov     qword ptr [rbp+var_3F+7], rcx
0x18007d8fb  mov     ecx, [rsi+rax*8+10h]
0x18007d8ff  test    ecx, ecx
0x18007d901  jnz     short loc_18007D92F
0x18007d903  lea     rdx, [rbp+var_30]
0x18007d907  mov     rcx, rdi; hHandle
0x18007d90a  call    SyncGetFileSize
0x18007d90f  mov     ebx, eax
0x18007d911  test    eax, eax
0x18007d913  js      loc_18007DB22
0x18007d919  mov     rcx, [rbp+var_30]
0x18007d91d  test    rcx, rcx
0x18007d920  jz      loc_18007DB22
0x18007d926  mov     r9, qword ptr [rbp+var_3F+7]
0x18007d92a  sub     rcx, r9
0x18007d92d  jmp     short loc_18007D933
0x18007d92f  mov     r9, qword ptr [rbp+var_3F+7]
0x18007d933  cmp     [rbp+var_40], 0
0x18007d937  mov     r8, r12
0x18007d93a  mov     [rbp+var_30], rcx
0x18007d93e  mov     rdx, rdi
0x18007d941  setz    al
0x18007d944  mov     byte ptr [rsp+80h+var_50], al
0x18007d948  mov     qword ptr [rsp+80h+var_60], rcx
0x18007d94d  mov     rcx, [rbp+arg_0]
0x18007d951  call    SyncActionCopyFileFromOffset
0x18007d956  mov     ebx, eax
0x18007d958  test    eax, eax
0x18007d95a  js      loc_18007DB2C
0x18007d960  inc     r14d
0x18007d963  jmp     short loc_18007D8E7
0x18007d965  mov     rax, qword ptr [rbp+var_3F+7]
0x18007d969  add     rax, [rbp+var_30]
0x18007d96d  cmp     byte ptr [rsi+4], 1
0x18007d971  mov     qword ptr [rbp+var_3F+7], rax
0x18007d975  jz      loc_18007D7AC
0x18007d97b  test    r15, r15
0x18007d97e  jz      loc_18007DBA4
0x18007d984  cmp     r12, r15
0x18007d987  jnz     loc_18007DBA4
0x18007d98d  mov     eax, [rbp+arg_20]
0x18007d990  mov     [rbp+var_20], 0
0x18007d998  test    eax, eax
0x18007d99a  jz      short loc_18007D9A5
0x18007d99c  imul    r14d, eax, 989680h
0x18007d9a3  jmp     short loc_18007D9AB
0x18007d9a5  mov     r14d, 1
0x18007d9ab  inc     cs:NumLargeFree
0x18007d9b2  xor     edx, edx; dwSize
0x18007d9b4  mov     r8d, 8000h; dwFreeType
0x18007d9ba  mov     rcx, rsi; lpAddress
0x18007d9bd  call    cs:__imp_VirtualFree
0x18007d9c3  mov     r12, [rbp+arg_0]
0x18007d9c7  mov     rdx, rdi
0x18007d9ca  lea     rcx, [r12+20h]
0x18007d9cf  call    SyncConvertBackoutHandle
0x18007d9d4  mov     ebx, eax
0x18007d9d6  test    eax, eax
0x18007d9d8  js      loc_18007DB9A
0x18007d9de  mov     r8, [r12+10h]
0x18007d9e3  lea     rax, [rbp+var_20]
0x18007d9e7  mov     rdx, [r13+0]; FileHandle
0x18007d9eb  add     r8, 68h ; 'h'
0x18007d9ef  mov     [rsp+80h+var_48], rax; __int64
0x18007d9f4  mov     rcx, rdi; hHandle
0x18007d9f7  mov     [rsp+80h+var_50], 0; __int64
0x18007da00  mov     dword ptr [rsp+80h+lpsz], r14d; int
0x18007da05  mov     r14d, [rbp+arg_20]
0x18007da09  mov     r9d, r14d
0x18007da0c  mov     [rsp+80h+var_60], 0; char
0x18007da11  call    SyncActionCopyAttributesWithAdjustment
0x18007da16  mov     ebx, eax
0x18007da18  test    eax, eax
0x18007da1a  js      loc_18007DB90
0x18007da20  lea     r8, [rbp+var_20]
0x18007da24  xor     edx, edx
0x18007da26  mov     rcx, rdi; FileHandle
0x18007da29  call    SyncActionSetOriginalTime
0x18007da2e  mov     ebx, eax
0x18007da30  test    eax, eax
0x18007da32  js      loc_18007DB86
0x18007da38  mov     r9, [r13+0]
0x18007da3c  lea     rax, [rbp+var_3F]
0x18007da40  lea     r8, [rbp+var_18]
0x18007da44  mov     qword ptr [rsp+80h+var_60], rax; __int64
0x18007da49  mov     rdx, r15
0x18007da4c  mov     rcx, rdi; hHandle
0x18007da4f  xor     esi, esi
0x18007da51  call    SyncActionCopyChunkFile
0x18007da56  mov     rcx, r15; Handle
0x18007da59  mov     ebx, eax
0x18007da5b  call    SyncCloseFile
0x18007da60  xor     r15d, r15d
0x18007da63  mov     qword ptr [rbp+var_28], r15
0x18007da67  test    ebx, ebx
0x18007da69  jns     loc_18007DBAC
0x18007da6f  cmp     [rbp+var_3F], sil
0x18007da73  jz      loc_18007DB7C
0x18007da79  mov     rax, cs:WPP_GLOBAL_Control
0x18007da80  lea     rcx, WPP_GLOBAL_Control
0x18007da87  cmp     rax, rcx
0x18007da8a  jz      short loc_18007DABD
0x18007da8c  test    byte ptr [rax+6Ch], 1
0x18007da90  jz      short loc_18007DABD
0x18007da92  mov     edx, ebx
0x18007da94  lea     rcx, aErrorUsingCopy; "Error using copy chunk FSCTL to copy fi"...
0x18007da9b  call    SyncTraceOutputInternal
0x18007daa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007daa7  lea     edx, [rsi+3Fh]
0x18007daaa  mov     r9d, ebx
0x18007daad  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18007dab4  mov     rcx, [rcx+60h]
0x18007dab8  call    WPP_SF_d
0x18007dabd  mov     r12, [r13+0]
0x18007dac1  mov     r14, [rbp+arg_0]
0x18007dac5  jmp     loc_18007D78A
0x18007daca  mov     rax, cs:WPP_GLOBAL_Control
0x18007dad1  lea     r12, WPP_GLOBAL_Control
0x18007dad8  cmp     rax, r12
0x18007dadb  jz      loc_18007DC7B
0x18007dae1  test    byte ptr [rax+6Ch], 1
0x18007dae5  jz      loc_18007DC7B
0x18007daeb  lea     rcx, aSyncactioncopy_36; "SyncActionCopyClientToServer: SyncStore"...
0x18007daf2  call    SyncTraceOutputInternal
0x18007daf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dafe  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18007db05  mov     edx, 3Ah ; ':'
0x18007db0a  mov     rcx, [rcx+60h]
0x18007db0e  call    WPP_SF_
0x18007db13  jmp     loc_18007DC7B
0x18007db18  mov     edi, 8CBh
0x18007db1d  jmp     loc_18007DCDE
0x18007db22  mov     edi, 8F7h
0x18007db27  jmp     loc_18007DCDE
0x18007db2c  mov     rax, cs:WPP_GLOBAL_Control
0x18007db33  lea     rcx, WPP_GLOBAL_Control
0x18007db3a  cmp     rax, rcx
0x18007db3d  jz      short loc_18007DB72
0x18007db3f  test    byte ptr [rax+6Ch], 1
0x18007db43  jz      short loc_18007DB72
0x18007db45  mov     edx, ebx
0x18007db47  lea     rcx, aSyncactioncopy_27; "SyncActionCopyClientToServer: SyncActio"...
0x18007db4e  call    SyncTraceOutputInternal
0x18007db53  mov     rcx, cs:WPP_GLOBAL_Control
0x18007db5a  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18007db61  mov     edx, 3Eh ; '>'
0x18007db66  mov     r9d, ebx
0x18007db69  mov     rcx, [rcx+60h]
0x18007db6d  call    WPP_SF_d
0x18007db72  mov     edi, 910h
0x18007db77  jmp     loc_18007DCDE
0x18007db7c  mov     edi, 96Dh
0x18007db81  jmp     loc_18007DD02
0x18007db86  mov     edi, 942h
0x18007db8b  jmp     loc_18007DD02
0x18007db90  mov     edi, 939h
0x18007db95  jmp     loc_18007DD02
0x18007db9a  mov     edi, 926h
0x18007db9f  jmp     loc_18007DD02
0x18007dba4  mov     r14d, [rbp+arg_20]
0x18007dba8  mov     r12, [rbp+arg_0]
0x18007dbac  lea     rdx, [rbp+var_30]
  ... truncated ...
```
