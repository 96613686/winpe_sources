# CreateEncoderToStream(_GUID const *,IStream *,GdiplusAbort *,IImageEncoder * *)

- ea: `0x1800388a0`
- end: `0x1800389c8`
- name: `?CreateEncoderToStream@@YAJPEBU_GUID@@PEAUIStream@@PEAUGdiplusAbort@@PEAPEAUIImageEncoder@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IStream *, struct GdiplusAbort *, struct IImageEncoder **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003870c`
- `0x1800914b4`

## callees

- `0x1800388a0`
- `0x180038d94`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003899b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003899b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800389b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800389b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800388c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800388c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038918`

## string_xrefs

- `0x1800389ad`: `CreateCodecInstance`

## pseudocode

```c
__int64 __fastcall CreateEncoderToStream(
        const struct _GUID *a1,
        struct IStream *a2,
        struct GdiplusAbort *a3,
        struct IImageEncoder **a4)
{
  int v8; // edi
  const WCHAR *v9; // rsi
  INT_PTR (__stdcall *v10)(); // rbx
  struct CachedCodecInfo *i; // rax
  __int64 v12; // rcx
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  int v15; // ebx
  HMODULE Library; // rax
  struct IImageEncoder *v17; // [rsp+20h] [rbp-48h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  EnterCriticalSection(&ImagingCritSec::critSec);
  ReloadCachedCodecInfo();
  for ( i = CachedCodecs; i; i = (struct CachedCodecInfo *)*((_QWORD *)i + 13) )
  {
    if ( (*((_BYTE *)i + 72) & 1) != 0 )
    {
      v12 = *(_QWORD *)i - *(_QWORD *)&a1->Data1;
      if ( *(_QWORD *)i == *(_QWORD *)&a1->Data1 )
        v12 = *((_QWORD *)i + 1) - *(_QWORD *)a1->Data4;
      if ( !v12 )
      {
        v9 = (const WCHAR *)*((_QWORD *)i + 5);
        v8 = 1;
        v10 = (INT_PTR (__stdcall *)())*((_QWORD *)i + 16);
        break;
      }
    }
  }
  LeaveCriticalSection(&ImagingCritSec::critSec);
  if ( !v8 )
    return 2289762310LL;
  v17 = 0;
  if ( v10 )
  {
    ProcAddress = v10;
LABEL_12:
    result = ((__int64 (__fastcall *)(GUID *, struct IImageEncoder **))ProcAddress)(&IID_IImageEncoder, &v17);
    goto LABEL_13;
  }
  Library = LoadLibraryExW(v9, 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CreateCodecInstance");
    if ( ProcAddress )
      goto LABEL_12;
  }
  result = 2289762313LL;
LABEL_13:
  if ( (int)result >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(struct IImageEncoder *, struct GdiplusAbort *, struct IStream *))(*(_QWORD *)v17 + 24LL))(
            v17,
            a3,
            a2);
    if ( v15 < 0 )
      (*(void (__fastcall **)(struct IImageEncoder *))(*(_QWORD *)v17 + 16LL))(v17);
    else
      *a4 = v17;
    return (unsigned int)v15;
  }
  return result;
}

```

## disassembly

```asm
0x1800388a0  push    rbx
0x1800388a2  push    rbp
0x1800388a3  push    rsi
0x1800388a4  push    rdi
0x1800388a5  push    r12
0x1800388a7  push    r14
0x1800388a9  push    r15
0x1800388ab  sub     rsp, 30h
0x1800388af  mov     rbp, rcx
0x1800388b2  mov     r14, r9
0x1800388b5  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800388bc  mov     r15, r8
0x1800388bf  mov     r12, rdx
0x1800388c2  xor     edi, edi
0x1800388c4  xor     esi, esi
0x1800388c6  xor     ebx, ebx
0x1800388c8  call    cs:__imp_EnterCriticalSection
0x1800388ce  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x1800388d3  mov     rax, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x1800388da  test    rax, rax
0x1800388dd  jz      short loc_180038911
0x1800388df  test    byte ptr [rax+48h], 1
0x1800388e3  jz      short loc_1800388FB
0x1800388e5  mov     rcx, [rax]
0x1800388e8  sub     rcx, [rbp+0]
0x1800388ec  jnz     short loc_1800388F6
0x1800388ee  mov     rcx, [rax+8]
0x1800388f2  sub     rcx, [rbp+8]
0x1800388f6  test    rcx, rcx
0x1800388f9  jz      short loc_180038901
0x1800388fb  mov     rax, [rax+68h]
0x1800388ff  jmp     short loc_1800388DA
0x180038901  mov     rsi, [rax+28h]
0x180038905  mov     edi, 1
0x18003890a  mov     rbx, [rax+80h]
0x180038911  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038918  call    cs:__imp_LeaveCriticalSection
0x18003891e  test    edi, edi
0x180038920  jz      short loc_18003897E
0x180038922  mov     [rsp+68h+var_48], 0
0x18003892b  test    rbx, rbx
0x18003892e  jz      short loc_180038993
0x180038930  mov     rax, rbx
0x180038933  lea     rcx, IID_IImageEncoder
0x18003893a  lea     rdx, [rsp+68h+var_48]
0x18003893f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038944  test    eax, eax
0x180038946  js      short loc_18003896F
0x180038948  mov     rcx, [rsp+68h+var_48]
0x18003894d  mov     r8, r12
0x180038950  mov     rdx, r15
0x180038953  mov     rax, [rcx]
0x180038956  mov     rax, [rax+18h]
0x18003895a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003895f  mov     rcx, [rsp+68h+var_48]
0x180038964  mov     ebx, eax
0x180038966  test    eax, eax
0x180038968  js      short loc_180038985
0x18003896a  mov     [r14], rcx
0x18003896d  mov     eax, ebx
0x18003896f  add     rsp, 30h
0x180038973  pop     r15
0x180038975  pop     r14
0x180038977  pop     r12
0x180038979  pop     rdi
0x18003897a  pop     rsi
0x18003897b  pop     rbp
0x18003897c  pop     rbx
0x18003897d  retn
0x18003897e  mov     eax, 887B0006h
0x180038983  jmp     short loc_18003896F
0x180038985  mov     rax, [rcx]
0x180038988  mov     rax, [rax+10h]
0x18003898c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038991  jmp     short loc_18003896D
0x180038993  xor     r8d, r8d; dwFlags
0x180038996  xor     edx, edx; hFile
0x180038998  mov     rcx, rsi; lpLibFileName
0x18003899b  call    cs:__imp_LoadLibraryExW
0x1800389a1  test    rax, rax
0x1800389a4  jnz     short loc_1800389AD
0x1800389a6  mov     eax, 887B0009h
0x1800389ab  jmp     short loc_180038944
0x1800389ad  lea     rdx, aCreatecodecins; "CreateCodecInstance"
0x1800389b4  mov     rcx, rax; hModule
0x1800389b7  call    cs:__imp_GetProcAddress
0x1800389bd  test    rax, rax
0x1800389c0  jnz     loc_180038933
0x1800389c6  jmp     short loc_1800389A6
```
