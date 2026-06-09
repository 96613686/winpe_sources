# CreateDecoderForStream(IStream *,IImageDecoder * *,DecoderInitFlag)

- ea: `0x18008c568`
- end: `0x18008c8b5`
- name: `?CreateDecoderForStream@@YAJPEAUIStream@@PEAPEAUIImageDecoder@@W4DecoderInitFlag@@@Z`
- size: `845`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002e950`
- `0x18002edac`
- `0x18008bc14`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x18008c568`
- `0x18008c8bc`
- `0x18008c984`
- `0x180105d40`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c7f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008c7f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c889`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c889`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c5a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c69b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c5a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008c69b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c5c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c6e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c5c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008c6e0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c67b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c7b3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c67b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008c7b3`

## string_xrefs

- `0x18008c87f`: `CreateCodecInstance`

## pseudocode

```c
__int64 __fastcall CreateDecoderForStream(__int64 *a1, _QWORD *a2, unsigned int a3)
{
  __int64 v5; // rbx
  char *v6; // rdi
  int v7; // esi
  int v8; // ebp
  char *v9; // r15
  unsigned int v10; // r14d
  __int64 v11; // rax
  int v12; // ebp
  const WCHAR *v13; // r15
  INT_PTR (__stdcall *v14)(); // rbp
  struct CachedCodecInfo *DecoderWithHeader; // rbx
  FARPROC ProcAddress; // rax
  int v17; // ebx
  HMODULE Library; // rax
  __int64 v20; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-98h]
  char v23; // [rsp+50h] [rbp-88h] BYREF

  v22 = a2;
  EnterCriticalSection(&ImagingCritSec::critSec);
  ReloadCachedCodecInfo();
  v5 = (unsigned int)dword_1801AE1E4;
  LeaveCriticalSection(&ImagingCritSec::critSec);
  if ( !(_DWORD)v5 )
    return 2289762310LL;
  if ( (unsigned int)v5 > 0x40 )
  {
    v6 = (char *)GpMallocEx(v5, 0);
    if ( !v6 )
    {
      GpFree(0);
      return 2147942414LL;
    }
    v7 = 1;
  }
  else
  {
    v6 = &v23;
    v7 = 0;
  }
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(*a1 + 40))(a1, 0, 0, 0);
  if ( v8 >= 0 )
  {
    v9 = v6;
    v10 = 0;
    do
    {
      v11 = *a1;
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, char *, _QWORD, unsigned int *))(v11 + 24))(
              a1,
              v9,
              (unsigned int)v5,
              &v21);
      v10 += v21;
      if ( v12 != -2147483638 )
        break;
      LODWORD(v5) = v5 - v21;
      v9 += v21;
      Sleep(0);
    }
    while ( (_DWORD)v5 );
    if ( !v10 )
    {
      v17 = -2147467259;
      if ( v12 < 0 )
        v17 = v12;
      goto LABEL_22;
    }
    while ( 1 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*a1 + 40))(a1, -v10, 1);
      if ( v8 != -2147483638 )
        break;
      Sleep(0);
    }
    if ( v8 >= 0 )
    {
      v13 = 0;
      EnterCriticalSection(&ImagingCritSec::critSec);
      if ( (a3 & 2) != 0 && (DecoderWithHeader = FindDecoderWithHeader(v6, v10, 0x10000u)) != 0
        || (v14 = 0, (DecoderWithHeader = FindDecoderWithHeader(v6, v10, 0)) != 0) )
      {
        v14 = (INT_PTR (__stdcall *)())*((_QWORD *)DecoderWithHeader + 16);
        if ( !v14 )
          v13 = (const WCHAR *)*((_QWORD *)DecoderWithHeader + 5);
      }
      LeaveCriticalSection(&ImagingCritSec::critSec);
      if ( DecoderWithHeader )
      {
        v20 = 0;
        if ( v14 )
        {
          ProcAddress = v14;
        }
        else
        {
          Library = LoadLibraryExW(v13, 0, 0);
          if ( !Library || (ProcAddress = GetProcAddress(Library, "CreateCodecInstance")) == 0 )
          {
            v17 = -2005204983;
LABEL_19:
            if ( v17 >= 0 )
            {
              v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v20 + 24LL))(v20, a1, a3);
              if ( v17 < 0 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              }
              else
              {
                *v22 = v20;
              }
            }
LABEL_22:
            if ( v7 )
              GpFree(v6);
            return (unsigned int)v17;
          }
        }
        v17 = ((__int64 (__fastcall *)(GUID *, __int64 *))ProcAddress)(&IID_IImageDecoder, &v20);
        goto LABEL_19;
      }
      if ( v7 )
        GpFree(v6);
      return 2289762310LL;
    }
  }
  if ( v7 )
    GpFree(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008c568  mov     [rsp+arg_18], rbx
0x18008c56d  push    rbp
0x18008c56e  push    rsi
0x18008c56f  push    rdi
0x18008c570  push    r12
0x18008c572  push    r13
0x18008c574  push    r14
0x18008c576  push    r15
0x18008c578  sub     rsp, 0A0h
0x18008c57f  mov     rax, cs:__security_cookie
0x18008c586  xor     rax, rsp
0x18008c589  mov     [rsp+0D8h+var_48], rax
0x18008c591  mov     r12, rcx
0x18008c594  mov     [rsp+0D8h+var_98], rdx
0x18008c599  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008c5a0  mov     r13d, r8d
0x18008c5a3  call    cs:__imp_EnterCriticalSection
0x18008c5aa  nop     dword ptr [rax+rax+00h]
0x18008c5af  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x18008c5b4  mov     ebx, cs:dword_1801AE1E4
0x18008c5ba  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008c5c1  call    cs:__imp_LeaveCriticalSection
0x18008c5c8  nop     dword ptr [rax+rax+00h]
0x18008c5cd  test    ebx, ebx
0x18008c5cf  jz      loc_18008C7A5
0x18008c5d5  cmp     ebx, 40h ; '@'
0x18008c5d8  ja      loc_18008C833
0x18008c5de  lea     rdi, [rsp+0D8h+var_88]
0x18008c5e3  xor     esi, esi
0x18008c5e5  mov     rax, [r12]
0x18008c5e9  xor     edx, edx
0x18008c5eb  xor     r9d, r9d
0x18008c5ee  xor     r8d, r8d
0x18008c5f1  mov     rcx, r12
0x18008c5f4  mov     rax, [rax+28h]
0x18008c5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c5fd  mov     ebp, eax
0x18008c5ff  test    eax, eax
0x18008c601  js      loc_18008C791
0x18008c607  mov     r15, rdi
0x18008c60a  xor     r14d, r14d
0x18008c60d  mov     rax, [r12]
0x18008c611  lea     r9, [rsp+0D8h+var_A0]
0x18008c616  mov     r8d, ebx
0x18008c619  mov     [rsp+0D8h+var_A0], 0
0x18008c621  mov     rdx, r15
0x18008c624  mov     rcx, r12
0x18008c627  mov     rax, [rax+18h]
0x18008c62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c630  mov     ebp, eax
0x18008c632  mov     eax, [rsp+0D8h+var_A0]
0x18008c636  add     r14d, eax
0x18008c639  cmp     ebp, 8000000Ah
0x18008c63f  jz      loc_18008C7AC
0x18008c645  test    r14d, r14d
0x18008c648  jz      loc_18008C785
0x18008c64e  mov     eax, r14d
0x18008c651  neg     eax
0x18008c653  movsxd  rbx, eax
0x18008c656  mov     rax, [r12]
0x18008c65a  xor     r9d, r9d
0x18008c65d  mov     rdx, rbx
0x18008c660  mov     rcx, r12
0x18008c663  mov     rax, [rax+28h]
0x18008c667  lea     r8d, [r9+1]
0x18008c66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c670  mov     ebp, eax
0x18008c672  cmp     eax, 8000000Ah
0x18008c677  jnz     short loc_18008C689
0x18008c679  xor     ecx, ecx; dwMilliseconds
0x18008c67b  call    cs:__imp_Sleep
0x18008c682  nop     dword ptr [rax+rax+00h]
0x18008c687  jmp     short loc_18008C656
0x18008c689  test    ebp, ebp
0x18008c68b  js      loc_18008C791
0x18008c691  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008c698  xor     r15d, r15d
0x18008c69b  call    cs:__imp_EnterCriticalSection
0x18008c6a2  nop     dword ptr [rax+rax+00h]
0x18008c6a7  test    r13b, 2
0x18008c6ab  jnz     loc_18008C811
0x18008c6b1  xor     r8d, r8d; unsigned int
0x18008c6b4  mov     edx, r14d; unsigned int
0x18008c6b7  mov     rcx, rdi; void *
0x18008c6ba  xor     ebp, ebp
0x18008c6bc  call    ?FindDecoderWithHeader@@YAPEAUCachedCodecInfo@@PEBXII@Z; FindDecoderWithHeader(void const *,uint,uint)
0x18008c6c1  mov     rbx, rax
0x18008c6c4  test    rax, rax
0x18008c6c7  jz      short loc_18008C6D9
0x18008c6c9  mov     rbp, [rbx+80h]
0x18008c6d0  test    rbp, rbp
0x18008c6d3  jz      loc_18008C869
0x18008c6d9  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008c6e0  call    cs:__imp_LeaveCriticalSection
0x18008c6e7  nop     dword ptr [rax+rax+00h]
0x18008c6ec  test    rbx, rbx
0x18008c6ef  jz      loc_18008C79D
0x18008c6f5  mov     [rsp+0D8h+var_A8], 0
0x18008c6fe  test    rbp, rbp
0x18008c701  jz      loc_18008C7EE
0x18008c707  mov     rax, rbp
0x18008c70a  lea     rcx, IID_IImageDecoder
0x18008c711  lea     rdx, [rsp+0D8h+var_A8]
0x18008c716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c71b  mov     ebx, eax
0x18008c71d  test    ebx, ebx
0x18008c71f  js      short loc_18008C74F
0x18008c721  mov     rcx, [rsp+0D8h+var_A8]
0x18008c726  mov     r8d, r13d
0x18008c729  mov     rdx, r12
0x18008c72c  mov     rax, [rcx]
0x18008c72f  mov     rax, [rax+18h]
0x18008c733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c738  mov     rcx, [rsp+0D8h+var_A8]
0x18008c73d  mov     ebx, eax
0x18008c73f  test    eax, eax
0x18008c741  js      loc_18008C7CC
0x18008c747  mov     rax, [rsp+0D8h+var_98]
0x18008c74c  mov     [rax], rcx
0x18008c74f  test    esi, esi
0x18008c751  jnz     loc_18008C85C
0x18008c757  mov     eax, ebx
0x18008c759  mov     rcx, [rsp+0D8h+var_48]
0x18008c761  xor     rcx, rsp; StackCookie
0x18008c764  call    __security_check_cookie
0x18008c769  mov     rbx, [rsp+0D8h+arg_18]
0x18008c771  add     rsp, 0A0h
0x18008c778  pop     r15
0x18008c77a  pop     r14
0x18008c77c  pop     r13
0x18008c77e  pop     r12
0x18008c780  pop     rdi
0x18008c781  pop     rsi
0x18008c782  pop     rbp
0x18008c783  retn
0x18008c785  test    ebp, ebp
0x18008c787  mov     ebx, 80004005h
0x18008c78c  cmovs   ebx, ebp
0x18008c78f  jmp     short loc_18008C74F
0x18008c791  test    esi, esi
0x18008c793  jnz     loc_18008C84F
0x18008c799  mov     eax, ebp
0x18008c79b  jmp     short loc_18008C759
0x18008c79d  test    esi, esi
0x18008c79f  jnz     loc_18008C872
0x18008c7a5  mov     eax, 887B0006h
0x18008c7aa  jmp     short loc_18008C759
0x18008c7ac  xor     ecx, ecx; dwMilliseconds
0x18008c7ae  sub     ebx, eax
0x18008c7b0  add     r15, rax
0x18008c7b3  call    cs:__imp_Sleep
0x18008c7ba  nop     dword ptr [rax+rax+00h]
0x18008c7bf  test    ebx, ebx
0x18008c7c1  jz      loc_18008C645
0x18008c7c7  jmp     loc_18008C60D
0x18008c7cc  mov     rax, [rcx]
0x18008c7cf  mov     rax, [rax+20h]
0x18008c7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c7d8  mov     rcx, [rsp+0D8h+var_A8]
0x18008c7dd  mov     rax, [rcx]
0x18008c7e0  mov     rax, [rax+10h]
0x18008c7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c7e9  jmp     loc_18008C74F
0x18008c7ee  xor     r8d, r8d; dwFlags
0x18008c7f1  xor     edx, edx; hFile
0x18008c7f3  mov     rcx, r15; lpLibFileName
0x18008c7f6  call    cs:__imp_LoadLibraryExW
0x18008c7fd  nop     dword ptr [rax+rax+00h]
0x18008c802  test    rax, rax
0x18008c805  jnz     short loc_18008C87F
0x18008c807  mov     ebx, 887B0009h
0x18008c80c  jmp     loc_18008C71D
0x18008c811  mov     r8d, 10000h; unsigned int
0x18008c817  mov     edx, r14d; unsigned int
0x18008c81a  mov     rcx, rdi; void *
0x18008c81d  call    ?FindDecoderWithHeader@@YAPEAUCachedCodecInfo@@PEBXII@Z; FindDecoderWithHeader(void const *,uint,uint)
0x18008c822  mov     rbx, rax
0x18008c825  test    rax, rax
0x18008c828  jnz     loc_18008C6C9
0x18008c82e  jmp     loc_18008C6B1
0x18008c833  mov     rcx, rbx
0x18008c836  xor     edx, edx
0x18008c838  call    GpMallocEx
0x18008c83d  mov     rdi, rax
0x18008c840  test    rax, rax
0x18008c843  jz      short loc_18008C8A3
0x18008c845  mov     esi, 1
0x18008c84a  jmp     loc_18008C5E5
0x18008c84f  mov     rcx, rdi
0x18008c852  call    GpFree
0x18008c857  jmp     loc_18008C799
0x18008c85c  mov     rcx, rdi
0x18008c85f  call    GpFree
0x18008c864  jmp     loc_18008C757
0x18008c869  mov     r15, [rbx+28h]
0x18008c86d  jmp     loc_18008C6D9
0x18008c872  mov     rcx, rdi
0x18008c875  call    GpFree
0x18008c87a  jmp     loc_18008C7A5
0x18008c87f  lea     rdx, aCreatecodecins; "CreateCodecInstance"
0x18008c886  mov     rcx, rax; hModule
0x18008c889  call    cs:__imp_GetProcAddress
0x18008c890  nop     dword ptr [rax+rax+00h]
0x18008c895  test    rax, rax
0x18008c898  jnz     loc_18008C70A
0x18008c89e  jmp     loc_18008C807
0x18008c8a3  mov     rcx, rax
0x18008c8a6  call    GpFree
0x18008c8ab  mov     eax, 8007000Eh
0x18008c8b0  jmp     loc_18008C759
```
