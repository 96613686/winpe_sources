# CreateEncoderToStream(_GUID const *,IStream *,GdiplusAbort *,IImageEncoder * *)

- ea: `0x18008c34c`
- end: `0x18008c48d`
- name: `?CreateEncoderToStream@@YAJPEBU_GUID@@PEAUIStream@@PEAUGdiplusAbort@@PEAPEAUIImageEncoder@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IStream *, struct GdiplusAbort *, struct IImageEncoder **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18008c1b0`
- `0x180095c8c`

## callees

- `0x18008c34c`
- `0x18008c8bc`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c454`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c454`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c476`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c476`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c374`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c3ca`

## string_xrefs

- `0x18008c46c`: `CreateCodecInstance`

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
0x18008c34c  push    rbx
0x18008c34e  push    rbp
0x18008c34f  push    rsi
0x18008c350  push    rdi
0x18008c351  push    r12
0x18008c353  push    r14
0x18008c355  push    r15
0x18008c357  sub     rsp, 30h
0x18008c35b  mov     rbp, rcx
0x18008c35e  mov     r14, r9
0x18008c361  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008c368  mov     r15, r8
0x18008c36b  mov     r12, rdx
0x18008c36e  xor     edi, edi
0x18008c370  xor     esi, esi
0x18008c372  xor     ebx, ebx
0x18008c374  call    cs:__imp_EnterCriticalSection
0x18008c37b  nop     dword ptr [rax+rax+00h]
0x18008c380  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x18008c385  mov     rax, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x18008c38c  test    rax, rax
0x18008c38f  jz      short loc_18008C3C3
0x18008c391  test    byte ptr [rax+48h], 1
0x18008c395  jz      short loc_18008C3AD
0x18008c397  mov     rcx, [rax]
0x18008c39a  sub     rcx, [rbp+0]
0x18008c39e  jnz     short loc_18008C3A8
0x18008c3a0  mov     rcx, [rax+8]
0x18008c3a4  sub     rcx, [rbp+8]
0x18008c3a8  test    rcx, rcx
0x18008c3ab  jz      short loc_18008C3B3
0x18008c3ad  mov     rax, [rax+68h]
0x18008c3b1  jmp     short loc_18008C38C
0x18008c3b3  mov     rsi, [rax+28h]
0x18008c3b7  mov     edi, 1
0x18008c3bc  mov     rbx, [rax+80h]
0x18008c3c3  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008c3ca  call    cs:__imp_LeaveCriticalSection
0x18008c3d1  nop     dword ptr [rax+rax+00h]
0x18008c3d6  test    edi, edi
0x18008c3d8  jz      short loc_18008C437
0x18008c3da  mov     [rsp+68h+var_48], 0
0x18008c3e3  test    rbx, rbx
0x18008c3e6  jz      short loc_18008C44C
0x18008c3e8  mov     rax, rbx
0x18008c3eb  lea     rcx, IID_IImageEncoder
0x18008c3f2  lea     rdx, [rsp+68h+var_48]
0x18008c3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3fc  test    eax, eax
0x18008c3fe  js      short loc_18008C427
0x18008c400  mov     rcx, [rsp+68h+var_48]
0x18008c405  mov     r8, r12
0x18008c408  mov     rdx, r15
0x18008c40b  mov     rax, [rcx]
0x18008c40e  mov     rax, [rax+18h]
0x18008c412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c417  mov     rcx, [rsp+68h+var_48]
0x18008c41c  mov     ebx, eax
0x18008c41e  test    eax, eax
0x18008c420  js      short loc_18008C43E
0x18008c422  mov     [r14], rcx
0x18008c425  mov     eax, ebx
0x18008c427  add     rsp, 30h
0x18008c42b  pop     r15
0x18008c42d  pop     r14
0x18008c42f  pop     r12
0x18008c431  pop     rdi
0x18008c432  pop     rsi
0x18008c433  pop     rbp
0x18008c434  pop     rbx
0x18008c435  retn
0x18008c437  mov     eax, 887B0006h
0x18008c43c  jmp     short loc_18008C427
0x18008c43e  mov     rax, [rcx]
0x18008c441  mov     rax, [rax+10h]
0x18008c445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c44a  jmp     short loc_18008C425
0x18008c44c  xor     r8d, r8d; dwFlags
0x18008c44f  xor     edx, edx; hFile
0x18008c451  mov     rcx, rsi; lpLibFileName
0x18008c454  call    cs:__imp_LoadLibraryExW
0x18008c45b  nop     dword ptr [rax+rax+00h]
0x18008c460  test    rax, rax
0x18008c463  jnz     short loc_18008C46C
0x18008c465  mov     eax, 887B0009h
0x18008c46a  jmp     short loc_18008C3FC
0x18008c46c  lea     rdx, aCreatecodecins; "CreateCodecInstance"
0x18008c473  mov     rcx, rax; hModule
0x18008c476  call    cs:__imp_GetProcAddress
0x18008c47d  nop     dword ptr [rax+rax+00h]
0x18008c482  test    rax, rax
0x18008c485  jnz     loc_18008C3EB
0x18008c48b  jmp     short loc_18008C465
```
