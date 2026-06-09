# DeletePrinterHandle(_SPOOL *)

- ea: `0x1800381cc`
- end: `0x1800382f9`
- name: `?DeletePrinterHandle@@YAHPEAU_SPOOL@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(struct _SPOOL *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056dcc`

## callees

- `0x180008730`
- `0x18000910c`
- `0x18001af1c`
- `0x1800381cc`
- `0x18003e984`
- `0x1800a00b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038202`
- `api-ms-win-security-base-l1-1-0!ObjectCloseAuditAlarmW` at `0x1800382cc`
- `api-ms-win-security-base-l1-1-0!ObjectCloseAuditAlarmW` at `0x1800382cc`
- `SPOOLSS!DllFreeSplStr` at `0x180038277`
- `SPOOLSS!DllFreeSplStr` at `0x180038284`
- `SPOOLSS!DllFreeSplStr` at `0x18003828e`
- `SPOOLSS!DllFreeSplStr` at `0x1800382ab`
- `SPOOLSS!DllFreeSplStr` at `0x1800382b5`
- `SPOOLSS!DllFreeSplStr` at `0x180038277`
- `SPOOLSS!DllFreeSplStr` at `0x180038284`
- `SPOOLSS!DllFreeSplStr` at `0x18003828e`
- `SPOOLSS!DllFreeSplStr` at `0x1800382ab`
- `SPOOLSS!DllFreeSplStr` at `0x1800382b5`
- `SPOOLSS!DllFreeSplMem` at `0x1800381f0`
- `SPOOLSS!DllFreeSplMem` at `0x1800382e8`
- `SPOOLSS!DllFreeSplMem` at `0x1800381f0`
- `SPOOLSS!DllFreeSplMem` at `0x1800382e8`

## string_xrefs

- `0x180038219`: `DeletePrinterHandle`

## pseudocode

```c
__int64 __fastcall DeletePrinterHandle(struct _SPOOL *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx

  v2 = *((_QWORD *)a1 + 6);
  if ( v2 )
    SafeDecrementReference((unsigned int *)(v2 + 16));
  v3 = *((_QWORD *)a1 + 7);
  if ( v3 )
    DllFreeSplMem(v3);
  v4 = (void *)*((_QWORD *)a1 + 36);
  if ( v4 )
    CloseHandle(v4);
  if ( *((_QWORD *)a1 + 40) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo("DeletePrinterHandle", L"Releasing PrintDAM object");
    NCoreLibrary::TReferenceCount::Release(*((NCoreLibrary::TReferenceCount **)a1 + 40));
    *((_QWORD *)a1 + 40) = 0;
  }
  if ( geCollectUsersInfo == 4
    && (*(_DWORD *)(*((_QWORD *)a1 + 21) + 168LL) & 0x1000000) != 0
    && (*((_BYTE *)a1 + 88) & 0x11) != 0
    && *((_QWORD *)a1 + 37) )
  {
    DetachUserInformation(a1);
  }
  DllFreeSplStr(*((_QWORD *)a1 + 30));
  DllFreeSplStr(*((_QWORD *)a1 + 29));
  DllFreeSplStr(*((_QWORD *)a1 + 5));
  SetSpoolChange(a1, 0, 0, 0xDEADDEAD);
  DllFreeSplStr(*((_QWORD *)a1 + 3));
  DllFreeSplStr(*((_QWORD *)a1 + 4));
  ObjectCloseAuditAlarmW(L"Spooler", a1, *((_DWORD *)a1 + 46));
  if ( *((_QWORD *)a1 + 17) )
    *((_DWORD *)a1 + 40) |= 8u;
  else
    DllFreeSplMem(a1);
  return 1;
}

```

## disassembly

```asm
0x1800381cc  push    rbx
0x1800381ce  sub     rsp, 20h
0x1800381d2  mov     rbx, rcx
0x1800381d5  mov     rcx, [rcx+30h]
0x1800381d9  test    rcx, rcx
0x1800381dc  jz      short loc_1800381E7
0x1800381de  add     rcx, 10h; unsigned int *
0x1800381e2  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800381e7  mov     rcx, [rbx+38h]
0x1800381eb  test    rcx, rcx
0x1800381ee  jz      short loc_1800381F6
0x1800381f0  call    cs:__imp_DllFreeSplMem
0x1800381f6  mov     rcx, [rbx+120h]; hObject
0x1800381fd  test    rcx, rcx
0x180038200  jz      short loc_180038208
0x180038202  call    cs:__imp_CloseHandle
0x180038208  cmp     qword ptr [rbx+140h], 0
0x180038210  jz      short loc_18003823C
0x180038212  lea     rdx, aReleasingPrint; "Releasing PrintDAM object"
0x180038219  lea     rcx, aDeleteprinterh; "DeletePrinterHandle"
0x180038220  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180038225  mov     rcx, [rbx+140h]; this
0x18003822c  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x180038231  mov     qword ptr [rbx+140h], 0
0x18003823c  cmp     cs:geCollectUsersInfo, 4
0x180038243  jnz     short loc_180038270
0x180038245  mov     rax, [rbx+0A8h]
0x18003824c  test    dword ptr [rax+0A8h], 1000000h
0x180038256  jz      short loc_180038270
0x180038258  test    byte ptr [rbx+58h], 11h
0x18003825c  jz      short loc_180038270
0x18003825e  cmp     qword ptr [rbx+128h], 0
0x180038266  jz      short loc_180038270
0x180038268  mov     rcx, rbx; struct _SPOOL *
0x18003826b  call    ?DetachUserInformation@@YAJPEAU_SPOOL@@@Z; DetachUserInformation(_SPOOL *)
0x180038270  mov     rcx, [rbx+0F0h]
0x180038277  call    cs:__imp_DllFreeSplStr
0x18003827d  mov     rcx, [rbx+0E8h]
0x180038284  call    cs:__imp_DllFreeSplStr
0x18003828a  mov     rcx, [rbx+28h]
0x18003828e  call    cs:__imp_DllFreeSplStr
0x180038294  mov     r9d, 0DEADDEADh; unsigned int
0x18003829a  xor     r8d, r8d; unsigned int *
0x18003829d  xor     edx, edx; struct _NOTIFY_RAW_DATA *
0x18003829f  mov     rcx, rbx; struct _SPOOL *
0x1800382a2  call    ?SetSpoolChange@@YAHPEAU_SPOOL@@PEAU_NOTIFY_RAW_DATA@@PEAKK@Z; SetSpoolChange(_SPOOL *,_NOTIFY_RAW_DATA *,ulong *,ulong)
0x1800382a7  mov     rcx, [rbx+18h]
0x1800382ab  call    cs:__imp_DllFreeSplStr
0x1800382b1  mov     rcx, [rbx+20h]
0x1800382b5  call    cs:__imp_DllFreeSplStr
0x1800382bb  mov     r8d, [rbx+0B8h]; GenerateOnClose
0x1800382c2  lea     rcx, szSpooler; "Spooler"
0x1800382c9  mov     rdx, rbx; HandleId
0x1800382cc  call    cs:__imp_ObjectCloseAuditAlarmW
0x1800382d2  cmp     qword ptr [rbx+88h], 0
0x1800382da  jz      short loc_1800382E5
0x1800382dc  or      dword ptr [rbx+0A0h], 8
0x1800382e3  jmp     short loc_1800382EE
0x1800382e5  mov     rcx, rbx
0x1800382e8  call    cs:__imp_DllFreeSplMem
0x1800382ee  mov     eax, 1
0x1800382f3  add     rsp, 20h
0x1800382f7  pop     rbx
0x1800382f8  retn
```
