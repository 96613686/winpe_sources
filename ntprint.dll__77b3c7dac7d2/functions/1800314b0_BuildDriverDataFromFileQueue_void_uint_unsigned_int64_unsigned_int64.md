# BuildDriverDataFromFileQueue(void *,uint,unsigned __int64,unsigned __int64)

- ea: `0x1800314b0`
- end: `0x1800318cf`
- name: `?BuildDriverDataFromFileQueue@@YAIPEAXI_K1@Z`
- size: `1055`
- prototype: `UINT __stdcall(PVOID Context, UINT Notification, UINT_PTR Param1, UINT_PTR Param2)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180002300`
- `0x1800026e0`
- `0x180007944`
- `0x18000b200`
- `0x18000d290`
- `0x18000d57c`
- `0x18000d624`
- `0x18001c914`
- `0x180025d10`
- `0x1800314b0`
- `0x1800323c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031589`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031620`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031589`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031620`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800316ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800316ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317fa`
- `SETUPAPI!SetupQueueCopyW` at `0x1800317e5`
- `SETUPAPI!SetupQueueCopyW` at `0x1800317e5`

## string_xrefs

- `0x180031548`: `Error retrieving filename part of relative file path: '%ws'`
- `0x180031646`: `Found printer extension '%ws' in queue`
- `0x1800317a1`: `Adding color profile to queue (SourceRootPath: '%ws', SourceFileName: '%ws')`

## pseudocode

```c
__int64 __fastcall BuildDriverDataFromFileQueue(char *Context, UINT Notification, UINT_PTR Param1, UINT_PTR Param2)
{
  signed int LastErrorAsFailHR; // ebx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  const unsigned __int16 *v10; // r15
  bool v11; // sf
  __int64 v12; // rax
  const unsigned __int16 *v13; // r12
  char *v14; // rcx
  __int64 v15; // rsi
  char *v16; // r14
  __int64 v17; // rdx
  int v18; // eax
  bool v19; // r11
  unsigned __int64 v20; // rsi
  signed int v21; // eax
  char v22; // r11
  unsigned __int64 v23; // r14
  int v24; // eax
  int v25; // edx
  __int64 v26; // rcx
  int v27; // edx
  unsigned int v28; // eax
  bool v29; // cf
  unsigned __int16 *v30; // rdx
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  NCoreLibrary *v33; // rcx
  DWORD LastError; // eax
  unsigned int v35; // ecx
  int v36; // edx
  unsigned int v37; // eax
  bool v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  UINT_PTR v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  WCHAR SourceRootPath[264]; // [rsp+80h] [rbp-80h] BYREF

  LastErrorAsFailHR = 0;
  v41 = Param1;
  if ( Notification != 24 )
    return (unsigned int)LastErrorAsFailHR;
  v6 = *((_QWORD *)Context + 13);
  v39 = 0;
  LastErrorAsFailHR = *(_DWORD *)(Param1 + 16);
  v7 = *(_QWORD *)(v6 + 152);
  v42 = *(_QWORD *)(v6 + 24);
  v8 = *(_QWORD *)(Param1 + 8);
  v43 = v7;
  v9 = *((_QWORD *)Context + 11);
  v10 = (const unsigned __int16 *)(v8 + 2 * v9);
  v11 = LastErrorAsFailHR < 0;
  if ( LastErrorAsFailHR > 0 )
  {
    LastErrorAsFailHR = (unsigned __int16)LastErrorAsFailHR | 0x80070000;
    v11 = LastErrorAsFailHR < 0;
  }
  if ( v11 )
  {
    v13 = 0;
    goto LABEL_15;
  }
  v12 = FileNamePart((wchar_t *)(v8 + 2 * v9));
  v13 = (const unsigned __int16 *)v12;
  if ( !v12 )
  {
    LastErrorAsFailHR = -2147418113;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "BuildDriverDataFromFileQueue",
      L"Error retrieving filename part of relative file path: '%ws'",
      v10);
    v14 = Context + 8;
    v15 = 0;
    v16 = Context + 8;
    goto LABEL_17;
  }
  if ( Context[40] )
    goto LABEL_15;
  v17 = (__int64)v10;
  if ( !*((_DWORD *)Context + 18) )
    v17 = v12;
  if ( (unsigned int)_o__wcsicmp(Context + 632, v17)
    || !*((_DWORD *)Context + 18)
    && (LastErrorAsFailHR = StringCchCopyW((unsigned __int16 *)Context + 316, 0x104u, v10),
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "BuildDriverDataFromFileQueue",
          L"Found data file in queue: '%ws'",
          v10),
        LastErrorAsFailHR < 0) )
  {
LABEL_15:
    v15 = 0;
    v14 = Context + 8;
    v16 = Context + 8;
    if ( LastErrorAsFailHR < 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v14 = Context + 8;
  v39 = 1;
  v16 = Context + 8;
  Context[40] = 1;
  v15 = 0;
LABEL_16:
  LastErrorAsFailHR = v14 == 0 ? 0x80004005 : 0;
LABEL_17:
  if ( v14 )
    v15 = *((_QWORD *)v16 + 2);
  while ( LastErrorAsFailHR >= 0 && !*((_DWORD *)Context + 18) && v16 && (char *)v15 != v16 )
  {
    if ( !*(_BYTE *)(v15 + 64) && !(unsigned int)_o__wcsicmp(*(_QWORD *)(v15 + 72), v13) )
    {
      v18 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)(v15 + 72), v10);
      *(_DWORD *)(v15 + 80) = v18;
      LastErrorAsFailHR = v18;
      if ( v18 >= 0 )
      {
        *(_BYTE *)(v15 + 64) = 1;
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "BuildDriverDataFromFileQueue",
          L"Found printer extension '%ws' in queue",
          v10);
      }
    }
    if ( v15 )
      v15 = *(_QWORD *)(v15 + 16);
  }
  v19 = v39;
  v20 = 0;
  v40 = 0;
  if ( LastErrorAsFailHR >= 0 && !v39 )
  {
    v21 = StringCchLengthW(v10, 0x7FFFFFFFu, &v40);
    v20 = v40;
    LastErrorAsFailHR = v21;
  }
  v40 = 0;
  if ( LastErrorAsFailHR >= 0 && !v19 )
  {
    LastErrorAsFailHR = StringCchLengthW(v13, 0x7FFFFFFFu, &v40);
    if ( LastErrorAsFailHR >= 0 )
    {
      v23 = v40;
      if ( !v22 )
      {
        v24 = _o__wcsnicmp(*(_QWORD *)v41, Context + 112);
        v25 = *((_DWORD *)Context + 18);
        if ( v24 )
        {
          if ( !v25 )
          {
            v35 = *((_DWORD *)Context + 12);
            v36 = -1;
            v37 = v20 + v35 + 1;
            v29 = v37 < v35;
            if ( v37 >= v35 )
              v36 = v20 + v35 + 1;
            *((_DWORD *)Context + 12) = v36;
            v30 = L"Found dependent file in queue: '%ws'";
            goto LABEL_52;
          }
          v39 = 0;
          LastErrorAsFailHR = IsManifestFile(v13, &v39);
          if ( LastErrorAsFailHR >= 0 && !v39 )
          {
            LastErrorAsFailHR = StringCchCopyW(
                                  (unsigned __int16 *)(v43 + 2LL * *((_QWORD *)Context + 8)),
                                  *((unsigned int *)Context + 12) - *((_QWORD *)Context + 8),
                                  v10);
            *((_QWORD *)Context + 8) += v20 + 1;
          }
        }
        else
        {
          v26 = *((unsigned int *)Context + 13);
          if ( !v25 )
          {
            v27 = -1;
            v28 = v23 + v26 + 1;
            v29 = v28 < (unsigned int)v26;
            if ( v28 >= (unsigned int)v26 )
              v27 = v23 + v26 + 1;
            *((_DWORD *)Context + 13) = v27;
            v30 = L"Found color profile in queue: '%ws'";
LABEL_52:
            LastErrorAsFailHR = v29 ? 0x80070216 : 0;
            ClassInstallerTelemetry::WriteDbgTraceInfo("BuildDriverDataFromFileQueue", v30, v10);
            return (unsigned int)LastErrorAsFailHR;
          }
          LastErrorAsFailHR = StringCchCopyW(
                                (unsigned __int16 *)(v42 + 2LL * *((_QWORD *)Context + 10)),
                                v26 - *((_QWORD *)Context + 10),
                                v13);
          *((_QWORD *)Context + 10) += v23 + 1;
          if ( LastErrorAsFailHR >= 0 )
          {
            LastErrorAsFailHR = StringCchCopyW(SourceRootPath, 0x104u, *(const unsigned __int16 **)(v41 + 8));
            if ( LastErrorAsFailHR >= 0 )
            {
              v31 = v20 - v23 + *((_QWORD *)Context + 11);
              if ( v31 >= 0x104 )
              {
                return (unsigned int)-2147483637;
              }
              else
              {
                v32 = v31;
                if ( v32 >= 260 )
                  _report_rangecheckfailure();
                SourceRootPath[v32] = 0;
                LastErrorAsFailHR = 0;
                ClassInstallerTelemetry::WriteDbgTraceInfo(
                  "BuildDriverDataFromFileQueue",
                  L"Adding color profile to queue (SourceRootPath: '%ws', SourceFileName: '%ws')",
                  SourceRootPath,
                  v13);
                if ( !SetupQueueCopyW(
                        *((HSPFILEQ *)Context + 7),
                        SourceRootPath,
                        0,
                        v13,
                        0,
                        0,
                        (PCWSTR)Context + 56,
                        0,
                        0x10000u) )
                {
                  LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v33);
                  LastError = GetLastError();
                  ClassInstallerTelemetry::WriteDbgTraceError(
                    "BuildDriverDataFromFileQueue",
                    L"Failed to add color profile to queue: %d",
                    LastError);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x1800314b0  mov     [rsp-8+arg_8], rbx
0x1800314b5  push    rbp
0x1800314b6  push    rsi
0x1800314b7  push    rdi
0x1800314b8  push    r12
0x1800314ba  push    r13
0x1800314bc  push    r14
0x1800314be  push    r15
0x1800314c0  lea     rbp, [rsp-1A0h]
0x1800314c8  sub     rsp, 2A0h
0x1800314cf  mov     rax, cs:__security_cookie
0x1800314d6  xor     rax, rsp
0x1800314d9  mov     [rbp+1D0h+var_40], rax
0x1800314e0  xor     ebx, ebx
0x1800314e2  mov     [rsp+2D0h+var_270], r8
0x1800314e7  mov     rdi, rcx
0x1800314ea  cmp     edx, 18h
0x1800314ed  jnz     loc_18003189D
0x1800314f3  mov     rax, [rcx+68h]
0x1800314f7  mov     [rsp+2D0h+var_280], bl
0x1800314fb  mov     ebx, [r8+10h]
0x1800314ff  mov     rcx, [rax+98h]
0x180031506  mov     rax, [rax+18h]
0x18003150a  mov     [rsp+2D0h+var_268], rax
0x18003150f  mov     rax, [r8+8]
0x180031513  mov     [rsp+2D0h+var_260], rcx
0x180031518  mov     rcx, [rdi+58h]
0x18003151c  lea     r15, [rax+rcx*2]
0x180031520  test    ebx, ebx
0x180031522  jle     short loc_18003152F
0x180031524  movzx   ebx, bx
0x180031527  or      ebx, 80070000h
0x18003152d  test    ebx, ebx
0x18003152f  js      loc_1800315D8
0x180031535  mov     rcx, r15; Str
0x180031538  call    FileNamePart
0x18003153d  mov     r12, rax
0x180031540  test    rax, rax
0x180031543  jnz     short loc_18003156E
0x180031545  mov     r8, r15
0x180031548  lea     rdx, aErrorRetrievin_8; "Error retrieving filename part of relat"...
0x18003154f  lea     rcx, aBuilddriverdat; "BuildDriverDataFromFileQueue"
0x180031556  mov     ebx, 8000FFFFh
0x18003155b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180031560  lea     rcx, [rdi+8]
0x180031564  xor     esi, esi
0x180031566  mov     r14, rcx
0x180031569  jmp     loc_1800315F8
0x18003156e  cmp     byte ptr [rdi+28h], 0
0x180031572  jnz     short loc_1800315DB
0x180031574  cmp     dword ptr [rdi+48h], 0
0x180031578  lea     rsi, [rdi+278h]
0x18003157f  mov     rdx, r15
0x180031582  mov     rcx, rsi
0x180031585  cmovz   rdx, rax
0x180031589  call    cs:__imp__o__wcsicmp
0x18003158f  test    eax, eax
0x180031591  jnz     short loc_1800315DB
0x180031593  cmp     [rdi+48h], eax
0x180031596  jnz     short loc_1800315C4
0x180031598  mov     r8, r15; unsigned __int16 *
0x18003159b  mov     edx, 104h; unsigned __int64
0x1800315a0  mov     rcx, rsi; unsigned __int16 *
0x1800315a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800315a8  mov     r8, r15
0x1800315ab  lea     rdx, aFoundDataFileI; "Found data file in queue: '%ws'"
0x1800315b2  lea     rcx, aBuilddriverdat; "BuildDriverDataFromFileQueue"
0x1800315b9  mov     ebx, eax
0x1800315bb  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800315c0  test    ebx, ebx
0x1800315c2  js      short loc_1800315DB
0x1800315c4  lea     rcx, [rdi+8]
0x1800315c8  mov     [rsp+2D0h+var_280], 1
0x1800315cd  mov     r14, rcx
0x1800315d0  mov     byte ptr [rdi+28h], 1
0x1800315d4  xor     esi, esi
0x1800315d6  jmp     short loc_1800315E8
0x1800315d8  xor     r12d, r12d
0x1800315db  xor     esi, esi
0x1800315dd  lea     rcx, [rdi+8]
0x1800315e1  mov     r14, rcx
0x1800315e4  test    ebx, ebx
0x1800315e6  js      short loc_1800315F8
0x1800315e8  mov     rax, rcx
0x1800315eb  neg     rax
0x1800315ee  sbb     ebx, ebx
0x1800315f0  not     ebx
0x1800315f2  and     ebx, 80004005h
0x1800315f8  test    rcx, rcx
0x1800315fb  jz      short loc_180031662
0x1800315fd  mov     rsi, [r14+10h]
0x180031601  jmp     short loc_180031662
0x180031603  cmp     dword ptr [rdi+48h], 0
0x180031607  jnz     short loc_180031666
0x180031609  test    r14, r14
0x18003160c  jz      short loc_180031666
0x18003160e  cmp     rsi, r14
0x180031611  jz      short loc_180031666
0x180031613  cmp     byte ptr [rsi+40h], 0
0x180031617  jnz     short loc_180031659
0x180031619  mov     rcx, [rsi+48h]
0x18003161d  mov     rdx, r12
0x180031620  call    cs:__imp__o__wcsicmp
0x180031626  test    eax, eax
0x180031628  jnz     short loc_180031659
0x18003162a  mov     rdx, r15; unsigned __int16 *
0x18003162d  lea     rcx, [rsi+48h]; this
0x180031631  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x180031636  mov     [rsi+50h], eax
0x180031639  mov     ebx, eax
0x18003163b  test    eax, eax
0x18003163d  js      short loc_180031659
0x18003163f  mov     r8, r15
0x180031642  mov     byte ptr [rsi+40h], 1
0x180031646  lea     rdx, aFoundPrinterEx; "Found printer extension '%ws' in queue"
0x18003164d  lea     rcx, aBuilddriverdat; "BuildDriverDataFromFileQueue"
0x180031654  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180031659  test    rsi, rsi
0x18003165c  jz      short loc_180031662
0x18003165e  mov     rsi, [rsi+10h]
0x180031662  test    ebx, ebx
0x180031664  jns     short loc_180031603
0x180031666  mov     r11b, [rsp+2D0h+var_280]
0x18003166b  xor     esi, esi
0x18003166d  mov     [rsp+2D0h+var_278], rsi
0x180031672  mov     r13d, 7FFFFFFFh
0x180031678  test    ebx, ebx
0x18003167a  js      short loc_180031698
0x18003167c  test    r11b, r11b
0x18003167f  jnz     short loc_180031698
0x180031681  lea     r8, [rsp+2D0h+var_278]; unsigned __int64 *
0x180031686  mov     edx, r13d; unsigned __int64
0x180031689  mov     rcx, r15; unsigned __int16 *
0x18003168c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031691  mov     rsi, [rsp+2D0h+var_278]
0x180031696  mov     ebx, eax
0x180031698  xor     r14d, r14d
0x18003169b  mov     [rsp+2D0h+var_278], r14
0x1800316a0  test    ebx, ebx
0x1800316a2  js      loc_18003189D
0x1800316a8  test    r11b, r11b
0x1800316ab  jnz     loc_18003189D
0x1800316b1  lea     r8, [rsp+2D0h+var_278]; unsigned __int64 *
0x1800316b6  mov     rdx, r13; unsigned __int64
0x1800316b9  mov     rcx, r12; unsigned __int16 *
0x1800316bc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800316c1  mov     ebx, eax
0x1800316c3  test    eax, eax
0x1800316c5  js      loc_18003189D
0x1800316cb  mov     r14, [rsp+2D0h+var_278]
0x1800316d0  test    r11b, r11b
0x1800316d3  jnz     loc_18003189D
0x1800316d9  mov     rcx, [rsp+2D0h+var_270]
0x1800316de  lea     r13, [rdi+70h]
0x1800316e2  mov     r8d, [rdi+2Ch]
0x1800316e6  mov     rdx, r13
0x1800316e9  mov     rcx, [rcx]
0x1800316ec  call    cs:__imp__o__wcsnicmp
0x1800316f2  mov     edx, [rdi+48h]
0x1800316f5  test    eax, eax
0x1800316f7  jnz     loc_180031822
0x1800316fd  mov     ecx, [rdi+34h]
0x180031700  test    edx, edx
0x180031702  jnz     short loc_180031721
0x180031704  or      edx, 0FFFFFFFFh
0x180031707  lea     eax, [rcx+1]
0x18003170a  add     eax, r14d
0x18003170d  cmp     eax, ecx
0x18003170f  cmovnb  edx, eax
0x180031712  mov     [rdi+34h], edx
0x180031715  lea     rdx, aFoundColorProf; "Found color profile in queue: '%ws'"
0x18003171c  jmp     loc_180031840
0x180031721  mov     rax, [rdi+50h]
0x180031725  mov     rdx, rcx
0x180031728  mov     rcx, [rsp+2D0h+var_268]
0x18003172d  sub     rdx, rax; unsigned __int64
0x180031730  mov     r8, r12; unsigned __int16 *
0x180031733  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180031737  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003173c  mov     ebx, eax
0x18003173e  lea     rax, [r14+1]
0x180031742  add     [rdi+50h], rax
0x180031746  test    ebx, ebx
0x180031748  js      loc_18003189D
0x18003174e  mov     rax, [rsp+2D0h+var_270]
0x180031753  lea     rcx, [rbp+1D0h+SourceRootPath]; unsigned __int16 *
0x180031757  mov     edx, 104h; unsigned __int64
0x18003175c  mov     r8, [rax+8]; unsigned __int16 *
0x180031760  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031765  mov     ebx, eax
0x180031767  test    eax, eax
0x180031769  js      loc_18003189D
0x18003176f  mov     rcx, [rdi+58h]
0x180031773  sub     rsi, r14
0x180031776  add     rcx, rsi
0x180031779  cmp     rcx, 104h
0x180031780  jnb     loc_18003181B
0x180031786  add     rcx, rcx
0x180031789  cmp     rcx, 208h
0x180031790  jnb     loc_1800318C9
0x180031796  xor     eax, eax
0x180031798  lea     r8, [rbp+1D0h+SourceRootPath]
0x18003179c  mov     [rbp+rcx+1D0h+SourceRootPath], ax
0x1800317a1  lea     rdx, aAddingColorPro; "Adding color profile to queue (SourceRo"...
0x1800317a8  lea     rcx, aBuilddriverdat; "BuildDriverDataFromFileQueue"
0x1800317af  mov     r9, r12
0x1800317b2  xor     ebx, ebx
0x1800317b4  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800317b9  mov     rcx, [rdi+38h]; QueueHandle
0x1800317bd  lea     rdx, [rbp+1D0h+SourceRootPath]; SourceRootPath
0x1800317c1  mov     [rsp+2D0h+CopyStyle], 10000h; CopyStyle
0x1800317c9  xor     esi, esi
0x1800317cb  mov     [rsp+2D0h+TargetFilename], rsi; TargetFilename
0x1800317d0  mov     r9, r12; SourceFilename
0x1800317d3  mov     [rsp+2D0h+TargetDirectory], r13; TargetDirectory
0x1800317d8  xor     r8d, r8d; SourcePath
0x1800317db  mov     [rsp+2D0h+SourceTagfile], rsi; SourceTagfile
0x1800317e0  mov     [rsp+2D0h+SourceDescription], rsi; SourceDescription
0x1800317e5  call    cs:__imp_SetupQueueCopyW
0x1800317eb  test    eax, eax
0x1800317ed  jnz     loc_18003189D
0x1800317f3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800317f8  mov     ebx, eax
0x1800317fa  call    cs:__imp_GetLastError
0x180031800  mov     r8d, eax
0x180031803  lea     rdx, aFailedToAddCol; "Failed to add color profile to queue: %"...
0x18003180a  lea     rcx, aBuilddriverdat; "BuildDriverDataFromFileQueue"
0x180031811  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180031816  jmp     loc_18003189D
0x18003181b  mov     ebx, 8000000Bh
0x180031820  jmp     short loc_18003189D
0x180031822  test    edx, edx
0x180031824  jnz     short loc_180031859
0x180031826  mov     ecx, [rdi+30h]
0x180031829  or      edx, 0FFFFFFFFh
0x18003182c  lea     eax, [rcx+1]
0x18003182f  add     eax, esi
0x180031831  cmp     eax, ecx
0x180031833  cmovnb  edx, eax
0x180031836  mov     [rdi+30h], edx
0x180031839  lea     rdx, aFoundDependent; "Found dependent file in queue: '%ws'"
0x180031840  sbb     ebx, ebx
0x180031842  lea     rcx, aBuilddriverdat; "BuildDriverDataFromFileQueue"
0x180031849  and     ebx, 80070216h
0x18003184f  mov     r8, r15
0x180031852  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180031857  jmp     short loc_18003189D
0x180031859  lea     rdx, [rsp+2D0h+var_280]; bool *
0x18003185e  mov     [rsp+2D0h+var_280], 0
0x180031863  mov     rcx, r12; unsigned __int16 *
0x180031866  call    ?IsManifestFile@@YAJPEBGPEA_N@Z; IsManifestFile(ushort const *,bool *)
0x18003186b  mov     ebx, eax
0x18003186d  test    eax, eax
0x18003186f  js      short loc_18003189D
0x180031871  cmp     [rsp+2D0h+var_280], 0
0x180031876  jnz     short loc_18003189D
0x180031878  mov     rax, [rdi+40h]
0x18003187c  mov     r8, r15; unsigned __int16 *
0x18003187f  mov     edx, [rdi+30h]
0x180031882  mov     rcx, [rsp+2D0h+var_260]
0x180031887  sub     rdx, rax; unsigned __int64
0x18003188a  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18003188e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031893  mov     ebx, eax
0x180031895  lea     rax, [rsi+1]
0x180031899  add     [rdi+40h], rax
0x18003189d  mov     eax, ebx
0x18003189f  mov     rcx, [rbp+1D0h+var_40]
0x1800318a6  xor     rcx, rsp; StackCookie
0x1800318a9  call    __security_check_cookie
0x1800318ae  mov     rbx, [rsp+2D0h+arg_8]
0x1800318b6  add     rsp, 2A0h
0x1800318bd  pop     r15
0x1800318bf  pop     r14
0x1800318c1  pop     r13
0x1800318c3  pop     r12
0x1800318c5  pop     rdi
0x1800318c6  pop     rsi
0x1800318c7  pop     rbp
0x1800318c8  retn
0x1800318c9  call    __report_rangecheckfailure
```
