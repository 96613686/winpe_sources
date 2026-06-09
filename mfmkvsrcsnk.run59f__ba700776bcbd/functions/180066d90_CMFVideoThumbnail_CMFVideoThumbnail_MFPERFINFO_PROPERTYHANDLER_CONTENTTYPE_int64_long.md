# CMFVideoThumbnail::CMFVideoThumbnail(MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE,__int64,long *)

- ea: `0x180066d90`
- end: `0x180066ed3`
- name: `??0CMFVideoThumbnail@@QEAA@W4MFPERFINFO_PROPERTYHANDLER_CONTENTTYPE@@_JPEAJ@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180069bfc`

## callees

- `0x180066d90`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066dd5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066dd5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066e59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066e59`
- `MFPlat!MFCreateTelemetrySession` at `0x180066e99`
- `MFPlat!MFCreateTelemetrySession` at `0x180066e99`

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
    (*(void (__fastcall **)(_QWORD, void *))(**(_QWORD **)(a1 + 400) + 304LL))(
      *(_QWORD *)(a1 + 400),
      &MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION);
  *a4 = v7;
  return a1;
}

```

## disassembly

```asm
0x180066d90  push    rbx
0x180066d92  push    rsi
0x180066d93  push    rdi
0x180066d94  push    r14
0x180066d96  sub     rsp, 48h
0x180066d9a  mov     [rcx+1Ch], edx
0x180066d9d  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180066da4  mov     [rcx], rax
0x180066da7  mov     rbx, rcx
0x180066daa  mov     dword ptr [rcx+8], 1
0x180066db1  lea     rax, ??_7CMFVideoThumbnail@@6BCBaseUnknown@@@; const CMFVideoThumbnail::`vftable'{for `CBaseUnknown'}
0x180066db8  mov     [rcx], rax
0x180066dbb  mov     r14, r9
0x180066dbe  lea     rax, ??_7CMFVideoThumbnail@@6BIMFSourceReaderCallback@@@; const CMFVideoThumbnail::`vftable'{for `IMFSourceReaderCallback'}
0x180066dc5  mov     [rcx+10h], rax
0x180066dc9  mov     qword ptr [rcx+20h], 0
0x180066dd1  add     rcx, 28h ; '('; lpCriticalSection
0x180066dd5  call    cs:__imp_InitializeCriticalSection
0x180066ddc  nop     dword ptr [rax+rax+00h]
0x180066de1  mov     qword ptr [rbx+150h], 0
0x180066dec  lea     rsi, [rbx+190h]
0x180066df3  mov     qword ptr [rbx+158h], 0
0x180066dfe  xor     r9d, r9d; lpName
0x180066e01  mov     qword ptr [rbx+160h], 2FAF080h
0x180066e0c  xor     r8d, r8d; bInitialState
0x180066e0f  mov     qword ptr [rbx+168h], 1312D00h
0x180066e1a  xor     edx, edx; bManualReset
0x180066e1c  mov     qword ptr [rbx+170h], 0
0x180066e27  xor     ecx, ecx; lpEventAttributes
0x180066e29  mov     qword ptr [rbx+178h], 0
0x180066e34  mov     dword ptr [rbx+180h], 0C8h
0x180066e3e  mov     dword ptr [rbx+184h], 40800000h
0x180066e48  mov     dword ptr [rbx+188h], 3E800000h
0x180066e52  mov     qword ptr [rsi], 0
0x180066e59  call    cs:__imp_CreateEventW
0x180066e60  nop     dword ptr [rax+rax+00h]
0x180066e65  mov     [rbx+170h], rax
0x180066e6c  mov     r8, rsi
0x180066e6f  neg     rax
0x180066e72  lea     rdx, [rsp+68h+var_48]
0x180066e77  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180066e7e  sbb     edi, edi
0x180066e80  lea     rcx, [rsp+68h+var_38]
0x180066e85  not     edi
0x180066e87  and     edi, 8007000Eh
0x180066e8d  movdqu  [rsp+68h+var_48], xmm0
0x180066e93  movdqu  [rsp+68h+var_38], xmm0
0x180066e99  call    cs:__imp_MFCreateTelemetrySession
0x180066ea0  nop     dword ptr [rax+rax+00h]
0x180066ea5  test    eax, eax
0x180066ea7  js      short loc_180066EC2
0x180066ea9  mov     rcx, [rsi]
0x180066eac  lea     rdx, MF_TELEMETRY_FLAG_THUMBNAIL_GENERATION
0x180066eb3  mov     rax, [rcx]
0x180066eb6  mov     rax, [rax+130h]
0x180066ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ec2  mov     [r14], edi
0x180066ec5  mov     rax, rbx
0x180066ec8  add     rsp, 48h
0x180066ecc  pop     r14
0x180066ece  pop     rdi
0x180066ecf  pop     rsi
0x180066ed0  pop     rbx
0x180066ed1  retn
```
