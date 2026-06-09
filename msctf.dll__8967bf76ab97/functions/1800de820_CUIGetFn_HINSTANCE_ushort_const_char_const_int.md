# CUIGetFn(HINSTANCE__ * *,ushort const *,char const *,int)

- ea: `0x1800de820`
- end: `0x1800de98a`
- name: `?CUIGetFn@@YAP6A_JXZPEAPEAUHINSTANCE__@@PEBGPEBDH@Z`
- size: `362`
- prototype: `__int64 (*(HINSTANCE *, const unsigned __int16 *, const char *, int))(void)`
- caller_count: `23`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180077270`
- `0x180094504`
- `0x1800de4d4`
- `0x1800de59c`
- `0x1800de604`
- `0x1800de6b8`
- `0x1800de760`
- `0x1800de990`
- `0x1800dea2c`
- `0x1800deac8`
- `0x1800deb64`
- `0x1800dec0c`
- `0x1800decb4`
- `0x1800ded74`
- `0x1800e2cd0`
- `0x1800e2e20`
- `0x1800e2ec0`
- `0x1800e3000`
- `0x1800e3070`
- `0x1800e3360`
- `0x1800e3630`
- `0x1800e3720`
- `0x180102eac`

## callees

- `0x1800de820`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800de967`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800de967`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800de90c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800de90c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800de899`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800de899`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de950`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800de950`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de875`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800de875`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800de93c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800de93c`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800de8fe`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800de8fe`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800de8e2`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800de8e2`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800de92d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800de92d`

## pseudocode

```c
FARPROC __fastcall CUIGetFn(HINSTANCE *a1, const unsigned __int16 *a2, const char *a3, int a4)
{
  __int64 v7; // rbx
  HANDLE v8; // rax
  ULONG_PTR Cookie[2]; // [rsp+28h] [rbp-2A0h] BYREF
  LPCSTR lpProcName; // [rsp+38h] [rbp-290h]
  ACTCTXW pActCtx; // [rsp+40h] [rbp-288h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-248h] BYREF

  Cookie[1] = (ULONG_PTR)a1;
  lpProcName = a3;
  if ( !*a1 )
  {
    v7 = -1;
    Cookie[0] = 0;
    EnterCriticalSection(&g_cs);
    if ( a4 > 0 )
    {
      GetModuleFileNameW(g_hInst, Filename, 0x104u);
      *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
      pActCtx.lpApplicationName = 0;
      pActCtx.hModule = 0;
      pActCtx.cbSize = 56;
      pActCtx.dwFlags = 8;
      pActCtx.lpResourceName = (LPCWSTR)(unsigned __int16)a4;
      pActCtx.lpSource = Filename;
      v8 = CreateActCtxW(&pActCtx);
      v7 = (__int64)v8;
      if ( v8 != (HANDLE)-1LL )
        ActivateActCtx(v8, Cookie);
    }
    *a1 = LoadLibraryExW(a2, 0, 0);
    if ( Cookie[0] )
      DeactivateActCtx(0, Cookie[0]);
    if ( v7 != -1 )
      ReleaseActCtx((HANDLE)v7);
    LeaveCriticalSection(&g_cs);
  }
  if ( *a1 )
    return GetProcAddress(*a1, lpProcName);
  else
    return 0;
}

```

## disassembly

```asm
0x1800de820  push    rbx
0x1800de822  push    rsi
0x1800de823  push    rdi
0x1800de824  push    r14
0x1800de826  sub     rsp, 2A8h
0x1800de82d  mov     rax, cs:__security_cookie
0x1800de834  xor     rax, rsp
0x1800de837  mov     [rsp+2C8h+var_38], rax
0x1800de83f  mov     esi, r9d
0x1800de842  mov     r14, rdx
0x1800de845  mov     rdi, rcx
0x1800de848  mov     [rsp+2C8h+var_298], rcx
0x1800de84d  mov     [rsp+2C8h+lpProcName], r8
0x1800de852  cmp     qword ptr [rcx], 0
0x1800de856  jnz     loc_1800DE956
0x1800de85c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800de860  mov     [rsp+2C8h+var_2A8], rbx
0x1800de865  mov     [rsp+2C8h+Cookie], 0
0x1800de86e  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x1800de875  call    cs:__imp_EnterCriticalSection
0x1800de87b  nop
0x1800de87c  test    esi, esi
0x1800de87e  jle     loc_1800DE904
0x1800de884  mov     r8d, 104h; nSize
0x1800de88a  lea     rdx, [rsp+2C8h+Filename]; lpFilename
0x1800de892  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800de899  call    cs:__imp_GetModuleFileNameW
0x1800de89f  xorps   xmm0, xmm0
0x1800de8a2  xor     eax, eax
0x1800de8a4  movups  xmmword ptr [rsp+2C8h+pActCtx.cbSize], xmm0
0x1800de8a9  movups  xmmword ptr [rsp+2C8h+pActCtx.wProcessorArchitecture], xmm0
0x1800de8ae  movups  xmmword ptr [rsp+2C8h+pActCtx.lpResourceName], xmm0
0x1800de8b3  mov     [rsp+2C8h+pActCtx.hModule], rax
0x1800de8b8  mov     [rsp+2C8h+pActCtx.cbSize], 38h ; '8'
0x1800de8c0  mov     [rsp+2C8h+pActCtx.dwFlags], 8
0x1800de8c8  movzx   eax, si
0x1800de8cb  mov     [rsp+2C8h+pActCtx.lpResourceName], rax
0x1800de8d0  lea     rax, [rsp+2C8h+Filename]
0x1800de8d8  mov     [rsp+2C8h+pActCtx.lpSource], rax
0x1800de8dd  lea     rcx, [rsp+2C8h+pActCtx]; pActCtx
0x1800de8e2  call    cs:__imp_CreateActCtxW
0x1800de8e8  mov     rbx, rax
0x1800de8eb  mov     [rsp+2C8h+var_2A8], rax
0x1800de8f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800de8f4  jz      short loc_1800DE904
0x1800de8f6  lea     rdx, [rsp+2C8h+Cookie]; lpCookie
0x1800de8fb  mov     rcx, rax; hActCtx
0x1800de8fe  call    cs:__imp_ActivateActCtx
0x1800de904  xor     r8d, r8d; dwFlags
0x1800de907  xor     edx, edx; hFile
0x1800de909  mov     rcx, r14; lpLibFileName
0x1800de90c  call    cs:__imp_LoadLibraryExW
0x1800de912  mov     [rdi], rax
0x1800de915  jmp     short loc_1800DE921
0x1800de917  mov     rbx, [rsp+2C8h+var_2A8]
0x1800de91c  mov     rdi, [rsp+2C8h+var_298]
0x1800de921  mov     rdx, [rsp+2C8h+Cookie]; ulCookie
0x1800de926  test    rdx, rdx
0x1800de929  jz      short loc_1800DE933
0x1800de92b  xor     ecx, ecx; dwFlags
0x1800de92d  call    cs:__imp_DeactivateActCtx
0x1800de933  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800de937  jz      short loc_1800DE942
0x1800de939  mov     rcx, rbx; hActCtx
0x1800de93c  call    cs:__imp_ReleaseActCtx
0x1800de942  jmp     short loc_1800DE949
0x1800de944  mov     rdi, [rsp+2C8h+var_298]
0x1800de949  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x1800de950  call    cs:__imp_LeaveCriticalSection
0x1800de956  mov     rcx, [rdi]; hModule
0x1800de959  test    rcx, rcx
0x1800de95c  jnz     short loc_1800DE962
0x1800de95e  xor     eax, eax
0x1800de960  jmp     short loc_1800DE96D
0x1800de962  mov     rdx, [rsp+2C8h+lpProcName]; lpProcName
0x1800de967  call    cs:__imp_GetProcAddress
0x1800de96d  mov     rcx, [rsp+2C8h+var_38]
0x1800de975  xor     rcx, rsp; StackCookie
0x1800de978  call    __security_check_cookie
0x1800de97d  add     rsp, 2A8h
0x1800de984  pop     r14
0x1800de986  pop     rdi
0x1800de987  pop     rsi
0x1800de988  pop     rbx
0x1800de989  retn
```
