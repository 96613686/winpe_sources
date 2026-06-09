# CMFVideoThumbnail::CMFVideoThumbnail(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,long *)

- ea: `0x180064274`
- end: `0x1800643a4`
- name: `??0CMFVideoThumbnail@@QEAA@W4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAJ@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180066fe0`

## callees

- `0x180064274`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800642b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800642b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064337`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064337`
- `MFPlat!MFCreateTelemetrySession` at `0x180064371`
- `MFPlat!MFCreateTelemetrySession` at `0x180064371`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CMFVideoThumbnail(__int64 a1, int a2, __int64 a3, unsigned int *a4)
{
  HANDLE EventW; // rax
  unsigned int v7; // edi
  GUID v9; // [rsp+20h] [rbp-48h] BYREF
  GUID v10; // [rsp+30h] [rbp-38h] BYREF

  *(_DWORD *)(a1 + 28) = a2;
  *(_QWORD *)a1 = &CBaseUnknown::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &CMFVideoThumbnail::`vftable'{for `CBaseUnknown'};
  *(_QWORD *)(a1 + 16) = &CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'};
  *(_QWORD *)(a1 + 32) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  *(_QWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 50000000;
  *(_QWORD *)(a1 + 360) = 20000000;
  *(_QWORD *)(a1 + 368) = 0;
  *(_QWORD *)(a1 + 376) = 0;
  *(_DWORD *)(a1 + 384) = 200;
  *(_DWORD *)(a1 + 388) = 1082130432;
  *(_DWORD *)(a1 + 392) = 1048576000;
  *(_QWORD *)(a1 + 400) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 368) = EventW;
  v7 = EventW == 0 ? 0x8007000E : 0;
  v9 = GUID_00000000_0000_0000_0000_000000000000;
  v10 = GUID_00000000_0000_0000_0000_000000000000;
  if ( (int)MFCreateTelemetrySession(&v10, &v9, a1 + 400) >= 0 )
    (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 400) + 304LL))(
      *(_QWORD *)(a1 + 400),
      MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION);
  *a4 = v7;
  return a1;
}

```

## disassembly

```asm
0x180064274  push    rbx
0x180064276  push    rsi
0x180064277  push    rdi
0x180064278  push    r14
0x18006427a  sub     rsp, 48h
0x18006427e  mov     [rcx+1Ch], edx
0x180064281  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180064288  mov     [rcx], rax
0x18006428b  mov     rbx, rcx
0x18006428e  mov     dword ptr [rcx+8], 1
0x180064295  lea     rax, ??_7CMFVideoThumbnail@@6BCBaseUnknown@@@; const CMFVideoThumbnail::`vftable'{for `CBaseUnknown'}
0x18006429c  mov     [rcx], rax
0x18006429f  mov     r14, r9
0x1800642a2  lea     rax, ??_7CMFVideoThumbnail@@6BIMFSourceReaderCallback@@@; const CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'}
0x1800642a9  mov     [rcx+10h], rax
0x1800642ad  mov     qword ptr [rcx+20h], 0
0x1800642b5  add     rcx, 28h ; '('; lpCriticalSection
0x1800642b9  call    cs:__imp_InitializeCriticalSection
0x1800642bf  mov     qword ptr [rbx+150h], 0
0x1800642ca  lea     rsi, [rbx+190h]
0x1800642d1  mov     qword ptr [rbx+158h], 0
0x1800642dc  xor     r9d, r9d; lpName
0x1800642df  mov     qword ptr [rbx+160h], 2FAF080h
0x1800642ea  xor     r8d, r8d; bInitialState
0x1800642ed  mov     qword ptr [rbx+168h], 1312D00h
0x1800642f8  xor     edx, edx; bManualReset
0x1800642fa  mov     qword ptr [rbx+170h], 0
0x180064305  xor     ecx, ecx; lpEventAttributes
0x180064307  mov     qword ptr [rbx+178h], 0
0x180064312  mov     dword ptr [rbx+180h], 0C8h
0x18006431c  mov     dword ptr [rbx+184h], 40800000h
0x180064326  mov     dword ptr [rbx+188h], 3E800000h
0x180064330  mov     qword ptr [rsi], 0
0x180064337  call    cs:__imp_CreateEventW
0x18006433d  mov     [rbx+170h], rax
0x180064344  mov     r8, rsi
0x180064347  neg     rax
0x18006434a  lea     rdx, [rsp+68h+var_48]
0x18006434f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180064356  sbb     edi, edi
0x180064358  lea     rcx, [rsp+68h+var_38]
0x18006435d  not     edi
0x18006435f  and     edi, 8007000Eh
0x180064365  movdqu  [rsp+68h+var_48], xmm0
0x18006436b  movdqu  [rsp+68h+var_38], xmm0
0x180064371  call    cs:__imp_MFCreateTelemetrySession
0x180064377  test    eax, eax
0x180064379  js      short loc_180064394
0x18006437b  mov     rcx, [rsi]
0x18006437e  lea     rdx, MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION
0x180064385  mov     rax, [rcx]
0x180064388  mov     rax, [rax+130h]
0x18006438f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064394  mov     [r14], edi
0x180064397  mov     rax, rbx
0x18006439a  add     rsp, 48h
0x18006439e  pop     r14
0x1800643a0  pop     rdi
0x1800643a1  pop     rsi
0x1800643a2  pop     rbx
0x1800643a3  retn
```
