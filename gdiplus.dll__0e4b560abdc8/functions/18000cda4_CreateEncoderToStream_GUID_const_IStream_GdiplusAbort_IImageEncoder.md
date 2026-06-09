# CreateEncoderToStream(_GUID const *,IStream *,GdiplusAbort *,IImageEncoder * *)

- ea: `0x18000cda4`
- end: `0x18000ceff`
- name: `?CreateEncoderToStream@@YAJPEBU_GUID@@PEAUIStream@@PEAUGdiplusAbort@@PEAPEAUIImageEncoder@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IStream *, struct GdiplusAbort *, struct IImageEncoder **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000cc1c`
- `0x18008ba70`
- `0x1801519e0`

## callees

- `0x18000cda4`
- `0x18000d2f0`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cee9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cee9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ceb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ceb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce30`

## string_xrefs

- `0x18000cedf`: `CreateCodecInstance`

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
  struct IImageEncoder *v17; // [rsp+20h] [rbp-28h] BYREF

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
  }
  else
  {
    Library = LoadLibraryExW(v9, 0, 0);
    if ( !Library )
      return 2289762313LL;
    ProcAddress = GetProcAddress(Library, "CreateCodecInstance");
    if ( !ProcAddress )
      return 2289762313LL;
  }
  result = ((__int64 (__fastcall *)(GUID *, struct IImageEncoder **))ProcAddress)(&IID_IImageEncoder, &v17);
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
0x18000cda4  mov     rax, rsp
0x18000cda7  mov     [rax+8], rbx
0x18000cdab  mov     [rax+10h], rbp
0x18000cdaf  mov     [rax+18h], rsi
0x18000cdb3  mov     [rax+20h], rdi
0x18000cdb7  push    r12
0x18000cdb9  push    r14
0x18000cdbb  push    r15
0x18000cdbd  sub     rsp, 30h
0x18000cdc1  mov     rbp, rcx
0x18000cdc4  mov     r14, r9
0x18000cdc7  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000cdce  mov     r15, r8
0x18000cdd1  mov     r12, rdx
0x18000cdd4  xor     edi, edi
0x18000cdd6  xor     esi, esi
0x18000cdd8  xor     ebx, ebx
0x18000cdda  call    cs:__imp_EnterCriticalSection
0x18000cde1  nop     dword ptr [rax+rax+00h]
0x18000cde6  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x18000cdeb  mov     rax, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x18000cdf2  test    rax, rax
0x18000cdf5  jz      short loc_18000CE29
0x18000cdf7  test    byte ptr [rax+48h], 1
0x18000cdfb  jz      short loc_18000CE13
0x18000cdfd  mov     rcx, [rax]
0x18000ce00  sub     rcx, [rbp+0]
0x18000ce04  jnz     short loc_18000CE0E
0x18000ce06  mov     rcx, [rax+8]
0x18000ce0a  sub     rcx, [rbp+8]
0x18000ce0e  test    rcx, rcx
0x18000ce11  jz      short loc_18000CE19
0x18000ce13  mov     rax, [rax+68h]
0x18000ce17  jmp     short loc_18000CDF2
0x18000ce19  mov     rsi, [rax+28h]
0x18000ce1d  mov     edi, 1
0x18000ce22  mov     rbx, [rax+80h]
0x18000ce29  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ce30  call    cs:__imp_LeaveCriticalSection
0x18000ce37  nop     dword ptr [rax+rax+00h]
0x18000ce3c  test    edi, edi
0x18000ce3e  jz      short loc_18000CEAA
0x18000ce40  and     [rsp+48h+var_28], 0
0x18000ce46  test    rbx, rbx
0x18000ce49  jz      short loc_18000CEB1
0x18000ce4b  mov     rax, rbx
0x18000ce4e  lea     rdx, [rsp+48h+var_28]
0x18000ce53  lea     rcx, IID_IImageEncoder
0x18000ce5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce5f  test    eax, eax
0x18000ce61  js      short loc_18000CE8A
0x18000ce63  mov     rcx, [rsp+48h+var_28]
0x18000ce68  mov     r8, r12
0x18000ce6b  mov     rdx, r15
0x18000ce6e  mov     rax, [rcx]
0x18000ce71  mov     rax, [rax+18h]
0x18000ce75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce7a  mov     rcx, [rsp+48h+var_28]
0x18000ce7f  mov     ebx, eax
0x18000ce81  test    eax, eax
0x18000ce83  js      short loc_18000CED1
0x18000ce85  mov     [r14], rcx
0x18000ce88  mov     eax, ebx
0x18000ce8a  mov     rbx, [rsp+48h+arg_0]
0x18000ce8f  mov     rbp, [rsp+48h+arg_8]
0x18000ce94  mov     rsi, [rsp+48h+arg_10]
0x18000ce99  mov     rdi, [rsp+48h+arg_18]
0x18000ce9e  add     rsp, 30h
0x18000cea2  pop     r15
0x18000cea4  pop     r14
0x18000cea6  pop     r12
0x18000cea8  retn
0x18000ceaa  mov     eax, 887B0006h
0x18000ceaf  jmp     short loc_18000CE8A
0x18000ceb1  xor     r8d, r8d; dwFlags
0x18000ceb4  xor     edx, edx; hFile
0x18000ceb6  mov     rcx, rsi; lpLibFileName
0x18000ceb9  call    cs:__imp_LoadLibraryExW
0x18000cec0  nop     dword ptr [rax+rax+00h]
0x18000cec5  test    rax, rax
0x18000cec8  jnz     short loc_18000CEDF
0x18000ceca  mov     eax, 887B0009h
0x18000cecf  jmp     short loc_18000CE8A
0x18000ced1  mov     rax, [rcx]
0x18000ced4  mov     rax, [rax+10h]
0x18000ced8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cedd  jmp     short loc_18000CE88
0x18000cedf  lea     rdx, ProcName; "CreateCodecInstance"
0x18000cee6  mov     rcx, rax; hModule
0x18000cee9  call    cs:__imp_GetProcAddress
0x18000cef0  nop     dword ptr [rax+rax+00h]
0x18000cef5  test    rax, rax
0x18000cef8  jz      short loc_18000CECA
0x18000cefa  jmp     loc_18000CE4E
```
