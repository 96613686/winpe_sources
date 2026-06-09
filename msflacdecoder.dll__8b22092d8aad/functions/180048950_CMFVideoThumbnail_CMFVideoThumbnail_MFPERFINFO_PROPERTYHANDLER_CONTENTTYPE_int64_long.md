# CMFVideoThumbnail::CMFVideoThumbnail(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,long *)

- ea: `0x180048950`
- end: `0x180048a80`
- name: `??0CMFVideoThumbnail@@QEAA@W4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAJ@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004b5f8`

## callees

- `0x180048950`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048a13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048a13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180048995`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180048995`
- `MFPlat!MFCreateTelemetrySession` at `0x180048a4d`
- `MFPlat!MFCreateTelemetrySession` at `0x180048a4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFVideoThumbnail::CMFVideoThumbnail(__int64 a1, int a2, __int64 a3, unsigned int *a4)
{
  HANDLE EventW; // rax
  unsigned int v7; // edi
  GUID v9; // [rsp+20h] [rbp-48h] BYREF
  GUID v10; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)a1 = &CBaseUnknown::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &CMFVideoThumbnail::`vftable'{for `CBaseUnknown'};
  *(_QWORD *)(a1 + 16) = &CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'};
  *(_DWORD *)(a1 + 28) = a2;
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
0x180048950  push    rbx
0x180048952  push    rsi
0x180048953  push    rdi
0x180048954  push    r14
0x180048956  sub     rsp, 48h
0x18004895a  mov     r14, r9
0x18004895d  mov     rbx, rcx
0x180048960  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180048967  mov     [rcx], rax
0x18004896a  mov     dword ptr [rcx+8], 1
0x180048971  lea     rax, ??_7CMFVideoThumbnail@@6BCBaseUnknown@@@; const CMFVideoThumbnail::`vftable'{for `CBaseUnknown'}
0x180048978  mov     [rcx], rax
0x18004897b  lea     rax, ??_7CMFVideoThumbnail@@6BIMFSourceReaderCallback@@@; const CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'}
0x180048982  mov     [rcx+10h], rax
0x180048986  mov     [rcx+1Ch], edx
0x180048989  mov     qword ptr [rcx+20h], 0
0x180048991  add     rcx, 28h ; '('; lpCriticalSection
0x180048995  call    cs:__imp_InitializeCriticalSection
0x18004899b  mov     qword ptr [rbx+150h], 0
0x1800489a6  mov     qword ptr [rbx+158h], 0
0x1800489b1  mov     qword ptr [rbx+160h], 2FAF080h
0x1800489bc  mov     qword ptr [rbx+168h], 1312D00h
0x1800489c7  mov     qword ptr [rbx+170h], 0
0x1800489d2  mov     qword ptr [rbx+178h], 0
0x1800489dd  mov     dword ptr [rbx+180h], 0C8h
0x1800489e7  mov     dword ptr [rbx+184h], 40800000h
0x1800489f1  mov     dword ptr [rbx+188h], 3E800000h
0x1800489fb  lea     rsi, [rbx+190h]
0x180048a02  mov     qword ptr [rsi], 0
0x180048a09  xor     r9d, r9d; lpName
0x180048a0c  xor     r8d, r8d; bInitialState
0x180048a0f  xor     edx, edx; bManualReset
0x180048a11  xor     ecx, ecx; lpEventAttributes
0x180048a13  call    cs:__imp_CreateEventW
0x180048a19  mov     [rbx+170h], rax
0x180048a20  neg     rax
0x180048a23  sbb     edi, edi
0x180048a25  not     edi
0x180048a27  and     edi, 8007000Eh
0x180048a2d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180048a34  movdqu  [rsp+68h+var_48], xmm0
0x180048a3a  movdqu  [rsp+68h+var_38], xmm0
0x180048a40  mov     r8, rsi
0x180048a43  lea     rdx, [rsp+68h+var_48]
0x180048a48  lea     rcx, [rsp+68h+var_38]
0x180048a4d  call    cs:__imp_MFCreateTelemetrySession
0x180048a53  test    eax, eax
0x180048a55  js      short loc_180048A70
0x180048a57  mov     rcx, [rsi]
0x180048a5a  mov     rax, [rcx]
0x180048a5d  lea     rdx, MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION
0x180048a64  mov     rax, [rax+130h]
0x180048a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a70  mov     [r14], edi
0x180048a73  mov     rax, rbx
0x180048a76  add     rsp, 48h
0x180048a7a  pop     r14
0x180048a7c  pop     rdi
0x180048a7d  pop     rsi
0x180048a7e  pop     rbx
0x180048a7f  retn
```
