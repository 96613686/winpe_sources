# OpenCoreDriverInfs(_CORE_DEPENDENCIES *,_HINF_ARRAY *)

- ea: `0x18001a1d8`
- end: `0x18001a44e`
- name: `?OpenCoreDriverInfs@@YAHPEAU_CORE_DEPENDENCIES@@PEAU_HINF_ARRAY@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(struct _CORE_DEPENDENCIES *, struct _HINF_ARRAY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001a914`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x18001a1d8`
- `0x180020b60`
- `0x180035208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a349`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a349`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a229`
- `SETUPAPI!SetupCloseInfFile` at `0x18001a332`
- `SETUPAPI!SetupCloseInfFile` at `0x18001a332`

## string_xrefs

- `0x18001a204`: `OpenCoreDriverInfs`
- `0x18001a2d0`: `OpenCoreDriverInfs`
- `0x18001a369`: `OpenCoreDriverInfs`
- `0x18001a3e2`: `OpenCoreDriverInfs`
- `0x18001a433`: `OpenCoreDriverInfs`
- `0x18001a30d`: `OpenCoreDriverInfs`
- `0x18001a37d`: `OpenCoreDriverInfs`
- `0x18001a410`: `OpenCoreDriverInfs`
- `0x18001a1fd`: `Opening all required core driver INFs`
- `0x18001a2c6`: `Array index out of bounds. Trying to access element %d of a %d element array.`
- `0x18001a362`: `Successfully opened all required core driver INFs`
- `0x18001a42c`: `Error opening required core driver INFs: %d`

## pseudocode

```c
__int64 __fastcall OpenCoreDriverInfs(struct _CORE_DEPENDENCIES *a1, struct _HINF_ARRAY *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  unsigned int i; // edi
  unsigned int v8; // ebp
  __int64 v9; // r15
  __int64 v10; // rax
  signed int v11; // ebp
  unsigned int v12; // ecx
  __int64 j; // rbp
  void *v14; // rcx
  signed int v15; // eax
  unsigned int v16; // ecx
  DWORD LastError; // eax

  if ( !a1 || !a2 )
  {
    i = 0;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "OpenCoreDriverInfs",
      L"Invalid Argument: pCoreDependencies=%p, phInfArray=%p",
      a1,
      a2);
    SplLogPrinterSetupGenericEvent(
      &SETUP_PRINTER_OPERATION_FAILED,
      L"OpenCoreDriverInfs",
      L"Invalid argument(s)",
      0,
      0,
      0x57u,
      0x80070057);
LABEL_32:
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "OpenCoreDriverInfs",
      L"Error opening required core driver INFs: %d",
      LastError);
    return i;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("OpenCoreDriverInfs", L"Opening all required core driver INFs");
  *(_DWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  v4 = LocalAlloc(0x40u, (unsigned int)(8 * *(_DWORD *)a1));
  v5 = v4;
  if ( !v4 )
  {
    i = 0;
    v15 = GetLastError();
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    else
      v16 = v15;
    SplLogPrinterSetupGenericEvent(
      &SETUP_PRINTER_OPERATION_FAILED,
      L"OpenCoreDriverInfs",
      L"LocalAllocMem failed",
      0,
      0,
      v15,
      v16);
    goto LABEL_32;
  }
  v6 = 0;
  for ( i = 1; (unsigned int)v6 < *(_DWORD *)a1; v6 = (unsigned int)(v6 + 1) )
    v4[v6] = -1;
  v8 = 0;
  while ( 1 )
  {
    if ( v8 >= *((_DWORD *)a1 + 4) )
    {
      *(_DWORD *)a2 = *(_DWORD *)a1;
      *((_QWORD *)a2 + 1) = v5;
      goto LABEL_25;
    }
    v9 = *(unsigned __int16 *)(((unsigned __int64)v8 << 9) + *((_QWORD *)a1 + 3) + 510);
    if ( (unsigned int)v9 >= *(_DWORD *)a1 )
      break;
    if ( v5[v9] == -1 )
    {
      v10 = OpenPrinterInfFile(
              (unsigned __int16 *)(*((_QWORD *)a1 + 1)
                                 + 96LL
                                 + 624LL
                                 * *(unsigned __int16 *)(((unsigned __int64)v8 << 9) + *((_QWORD *)a1 + 3) + 510)),
              0);
      v5[v9] = v10;
      if ( v10 == -1 )
      {
        i = 0;
        goto LABEL_18;
      }
      i = 1;
      ++v8;
    }
    else
    {
      ++v8;
      i = 1;
    }
  }
  i = 0;
  v11 = GetLastError();
  ClassInstallerTelemetry::WriteDbgTraceError(
    "OpenCoreDriverInfs",
    L"Array index out of bounds. Trying to access element %d of a %d element array.",
    (unsigned int)v9,
    *(unsigned int *)a1);
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  else
    v12 = v11;
  SplLogPrinterSetupGenericEvent(
    &SETUP_PRINTER_OPERATION_FAILED,
    L"OpenCoreDriverInfs",
    L"Array out of bounds",
    0,
    0,
    v11,
    v12);
LABEL_18:
  if ( !v5 )
    goto LABEL_32;
  for ( j = 0; (unsigned int)j < *(_DWORD *)a1; j = (unsigned int)(j + 1) )
  {
    v14 = (void *)v5[j];
    if ( v14 != (void *)-1LL )
    {
      SetupCloseInfFile(v14);
      v5[j] = -1;
    }
  }
  LocalFree(v5);
LABEL_25:
  if ( !i )
    goto LABEL_32;
  ClassInstallerTelemetry::WriteDbgTraceInfo("OpenCoreDriverInfs", L"Successfully opened all required core driver INFs");
  SplLogPrinterSetupGenericEvent(&SETUP_PRINTER_OPERATION_SUCCEEDED, L"OpenCoreDriverInfs", 0, 0, 0, 0, 0);
  return i;
}

```

## disassembly

```asm
0x18001a1d8  push    rbx
0x18001a1da  push    rbp
0x18001a1db  push    rsi
0x18001a1dc  push    rdi
0x18001a1dd  push    r14
0x18001a1df  push    r15
0x18001a1e1  sub     rsp, 48h
0x18001a1e5  mov     r14, rdx
0x18001a1e8  mov     rbx, rcx
0x18001a1eb  test    rcx, rcx
0x18001a1ee  jz      loc_18001A3D6
0x18001a1f4  test    rdx, rdx
0x18001a1f7  jz      loc_18001A3D6
0x18001a1fd  lea     rdx, aOpeningAllRequ; "Opening all required core driver INFs"
0x18001a204  lea     rcx, aOpencoredriver_0; "OpenCoreDriverInfs"
0x18001a20b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001a210  mov     dword ptr [r14], 0
0x18001a217  mov     ecx, 40h ; '@'; uFlags
0x18001a21c  mov     qword ptr [r14+8], 0
0x18001a224  mov     edx, [rbx]
0x18001a226  shl     edx, 3; uBytes
0x18001a229  call    cs:__imp_LocalAlloc
0x18001a22f  mov     rsi, rax
0x18001a232  test    rax, rax
0x18001a235  jz      loc_18001A3AC
0x18001a23b  xor     ecx, ecx
0x18001a23d  mov     edx, 1
0x18001a242  mov     edi, edx
0x18001a244  cmp     [rbx], ecx
0x18001a246  jbe     short loc_18001A256
0x18001a248  mov     qword ptr [rax+rcx*8], 0FFFFFFFFFFFFFFFFh
0x18001a250  add     ecx, edx
0x18001a252  cmp     ecx, [rbx]
0x18001a254  jb      short loc_18001A248
0x18001a256  xor     ebp, ebp
0x18001a258  cmp     ebp, [rbx+10h]
0x18001a25b  jnb     loc_18001A351
0x18001a261  mov     rax, [rbx+18h]
0x18001a265  mov     ecx, ebp
0x18001a267  shl     rcx, 9
0x18001a26b  movzx   r15d, word ptr [rcx+rax+1FEh]
0x18001a274  cmp     r15d, [rbx]
0x18001a277  jnb     short loc_18001A2BB
0x18001a279  cmp     qword ptr [rsi+r15*8], 0FFFFFFFFFFFFFFFFh
0x18001a27e  mov     edi, r15d
0x18001a281  jnz     short loc_18001A2B1
0x18001a283  mov     rax, [rbx+8]
0x18001a287  xor     edx, edx
0x18001a289  add     rax, 60h ; '`'
0x18001a28d  imul    rcx, rdi, 270h
0x18001a294  add     rcx, rax; unsigned __int16 *
0x18001a297  call    OpenPrinterInfFile
0x18001a29c  mov     [rsi+r15*8], rax
0x18001a2a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a2a4  jz      short loc_18001A2B7
0x18001a2a6  mov     edx, 1
0x18001a2ab  mov     edi, edx
0x18001a2ad  add     ebp, edx
0x18001a2af  jmp     short loc_18001A258
0x18001a2b1  add     ebp, edx
0x18001a2b3  mov     edi, edx
0x18001a2b5  jmp     short loc_18001A258
0x18001a2b7  xor     edi, edi
0x18001a2b9  jmp     short loc_18001A319
0x18001a2bb  xor     edi, edi
0x18001a2bd  call    cs:__imp_GetLastError
0x18001a2c3  mov     r9d, [rbx]
0x18001a2c6  lea     rdx, aArrayIndexOutO; "Array index out of bounds. Trying to ac"...
0x18001a2cd  mov     r8d, r15d
0x18001a2d0  lea     rcx, aOpencoredriver_0; "OpenCoreDriverInfs"
0x18001a2d7  mov     ebp, eax
0x18001a2d9  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001a2de  test    ebp, ebp
0x18001a2e0  jg      short loc_18001A2E6
0x18001a2e2  mov     ecx, ebp
0x18001a2e4  jmp     short loc_18001A2EF
0x18001a2e6  movzx   ecx, bp
0x18001a2e9  or      ecx, 80070000h
0x18001a2ef  mov     [rsp+78h+var_48], ecx; unsigned int
0x18001a2f3  lea     r8, aArrayOutOfBoun; "Array out of bounds"
0x18001a2fa  mov     [rsp+78h+var_50], ebp; unsigned int
0x18001a2fe  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18001a305  xor     r9d, r9d; unsigned __int16 *
0x18001a308  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18001a30d  lea     rdx, aOpencoredriver_1; "OpenCoreDriverInfs"
0x18001a314  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001a319  test    rsi, rsi
0x18001a31c  jz      loc_18001A423
0x18001a322  xor     ebp, ebp
0x18001a324  cmp     [rbx], ebp
0x18001a326  jbe     short loc_18001A346
0x18001a328  mov     rcx, [rsi+rbp*8]; InfHandle
0x18001a32c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a330  jz      short loc_18001A340
0x18001a332  call    cs:__imp_SetupCloseInfFile
0x18001a338  mov     qword ptr [rsi+rbp*8], 0FFFFFFFFFFFFFFFFh
0x18001a340  inc     ebp
0x18001a342  cmp     ebp, [rbx]
0x18001a344  jb      short loc_18001A328
0x18001a346  mov     rcx, rsi; hMem
0x18001a349  call    cs:__imp_LocalFree
0x18001a34f  jmp     short loc_18001A35A
0x18001a351  mov     eax, [rbx]
0x18001a353  mov     [r14], eax
0x18001a356  mov     [r14+8], rsi
0x18001a35a  test    edi, edi
0x18001a35c  jz      loc_18001A423
0x18001a362  lea     rdx, aSuccessfullyOp; "Successfully opened all required core d"...
0x18001a369  lea     rcx, aOpencoredriver_0; "OpenCoreDriverInfs"
0x18001a370  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001a375  mov     [rsp+78h+var_48], 0; unsigned int
0x18001a37d  lea     rdx, aOpencoredriver_1; "OpenCoreDriverInfs"
0x18001a384  mov     [rsp+78h+var_50], 0; unsigned int
0x18001a38c  lea     rcx, SETUP_PRINTER_OPERATION_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18001a393  xor     r9d, r9d; unsigned __int16 *
0x18001a396  mov     [rsp+78h+var_58], 0; unsigned __int16 *
0x18001a39f  xor     r8d, r8d; unsigned __int16 *
0x18001a3a2  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001a3a7  jmp     loc_18001A43F
0x18001a3ac  xor     edi, edi
0x18001a3ae  call    cs:__imp_GetLastError
0x18001a3b4  test    eax, eax
0x18001a3b6  jg      short loc_18001A3BC
0x18001a3b8  mov     ecx, eax
0x18001a3ba  jmp     short loc_18001A3C5
0x18001a3bc  movzx   ecx, ax
0x18001a3bf  or      ecx, 80070000h
0x18001a3c5  mov     [rsp+78h+var_48], ecx
0x18001a3c9  lea     r8, aLocalallocmemF; "LocalAllocMem failed"
0x18001a3d0  mov     [rsp+78h+var_50], eax
0x18001a3d4  jmp     short loc_18001A408
0x18001a3d6  xor     edi, edi
0x18001a3d8  lea     rdx, aInvalidArgumen_2; "Invalid Argument: pCoreDependencies=%p,"...
0x18001a3df  mov     r9, r14
0x18001a3e2  lea     rcx, aOpencoredriver_0; "OpenCoreDriverInfs"
0x18001a3e9  mov     r8, rbx
0x18001a3ec  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001a3f1  mov     [rsp+78h+var_48], 80070057h; unsigned int
0x18001a3f9  lea     r8, aInvalidArgumen_10; "Invalid argument(s)"
0x18001a400  mov     [rsp+78h+var_50], 57h ; 'W'; unsigned int
0x18001a408  xor     r9d, r9d; unsigned __int16 *
0x18001a40b  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18001a410  lea     rdx, aOpencoredriver_1; "OpenCoreDriverInfs"
0x18001a417  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18001a41e  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001a423  call    cs:__imp_GetLastError
0x18001a429  mov     r8d, eax
0x18001a42c  lea     rdx, aErrorOpeningRe; "Error opening required core driver INFs"...
0x18001a433  lea     rcx, aOpencoredriver_0; "OpenCoreDriverInfs"
0x18001a43a  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001a43f  mov     eax, edi
0x18001a441  add     rsp, 48h
0x18001a445  pop     r15
0x18001a447  pop     r14
0x18001a449  pop     rdi
0x18001a44a  pop     rsi
0x18001a44b  pop     rbp
0x18001a44c  pop     rbx
0x18001a44d  retn
```
