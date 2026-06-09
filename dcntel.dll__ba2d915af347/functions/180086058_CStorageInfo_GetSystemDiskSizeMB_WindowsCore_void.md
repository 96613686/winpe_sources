# CStorageInfo::GetSystemDiskSizeMB_WindowsCore(void)

- ea: `0x180086058`
- end: `0x1800861af`
- name: `?GetSystemDiskSizeMB_WindowsCore@CStorageInfo@@CA_JXZ`
- size: `343`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180085d68`
- `0x1800cc788`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x180086058`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008607e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008607e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800860a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800860c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800860e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800860a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800860c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800860e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086195`

## string_xrefs

- `0x180086077`: `storageusage.dll`
- `0x18008609c`: `OpenStorageTypeSearch`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CStorageInfo::GetSystemDiskSizeMB_WindowsCore(void)
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  FARPROC v3; // r14
  FARPROC v4; // rsi
  signed int LastError; // eax
  int v7; // edx
  unsigned int v8; // r8d
  const int *v9; // [rsp+50h] [rbp-10h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp-8h]
  __int64 v11; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int64 v12; // [rsp+98h] [rbp+38h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+40h] BYREF

  v0 = -1;
  Library = LoadLibraryExW(L"storageusage.dll", 0, 0x800u);
  v9 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "OpenStorageTypeSearch");
    if ( ProcAddress )
    {
      v3 = GetProcAddress(hModule, "SelectStorageVolumeEx");
      if ( v3 )
      {
        v4 = GetProcAddress(hModule, "CloseFindStorageSearch");
        if ( v4 )
        {
          v11 = 0;
          if ( ((int (__fastcall *)(__int64 *))ProcAddress)(&v11) >= 0 )
          {
            v12 = 0;
            v13 = 0;
            if ( ((int (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, unsigned __int64 *, __int64 *))v3)(
                   v11,
                   0,
                   0,
                   0,
                   0,
                   0,
                   &v12,
                   &v13) >= 0 )
              v0 = v12 >> 20;
            ((void (__fastcall *)(__int64 *))v4)(&v11);
          }
        }
      }
    }
  }
  v9 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v9) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v7, v8);
    JUMPOUT(0x1800861AELL);
  }
  return v0;
}

```

## disassembly

```asm
0x180086058  mov     [rsp-28h+arg_18], rbx
0x18008605d  push    rbp
0x18008605e  push    rsi
0x18008605f  push    rdi
0x180086060  push    r12
0x180086062  push    r14
0x180086064  mov     rbp, rsp
0x180086067  sub     rsp, 60h
0x18008606b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008606f  xor     edx, edx; hFile
0x180086071  mov     r8d, 800h; dwFlags
0x180086077  lea     rcx, aStorageusageDl; "storageusage.dll"
0x18008607e  call    cs:__imp_LoadLibraryExW
0x180086084  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18008608b  mov     [rbp+var_10], r12
0x18008608f  mov     [rbp+hModule], rax
0x180086093  test    rax, rax
0x180086096  jz      loc_180086166
0x18008609c  lea     rdx, aOpenstoragetyp; "OpenStorageTypeSearch"
0x1800860a3  mov     rcx, rax; hModule
0x1800860a6  call    cs:__imp_GetProcAddress
0x1800860ac  mov     rdi, rax
0x1800860af  test    rax, rax
0x1800860b2  jz      loc_180086166
0x1800860b8  lea     rdx, aSelectstoragev; "SelectStorageVolumeEx"
0x1800860bf  mov     rcx, [rbp+hModule]; hModule
0x1800860c3  call    cs:__imp_GetProcAddress
0x1800860c9  mov     r14, rax
0x1800860cc  test    rax, rax
0x1800860cf  jz      loc_180086166
0x1800860d5  lea     rdx, aClosefindstora; "CloseFindStorageSearch"
0x1800860dc  mov     rcx, [rbp+hModule]; hModule
0x1800860e0  call    cs:__imp_GetProcAddress
0x1800860e6  mov     rsi, rax
0x1800860e9  test    rax, rax
0x1800860ec  jz      short loc_180086166
0x1800860ee  mov     [rbp+arg_0], 0
0x1800860f6  lea     rcx, [rbp+arg_0]
0x1800860fa  mov     rax, rdi
0x1800860fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086102  test    eax, eax
0x180086104  js      short loc_180086166
0x180086106  mov     [rbp+arg_8], 0
0x18008610e  mov     [rbp+arg_10], 0
0x180086116  lea     rax, [rbp+arg_10]
0x18008611a  mov     [rsp+60h+var_28], rax
0x18008611f  lea     rax, [rbp+arg_8]
0x180086123  mov     [rsp+60h+var_30], rax
0x180086128  mov     [rsp+60h+var_38], 0
0x180086130  mov     [rsp+60h+var_40], 0
0x180086139  xor     r9d, r9d
0x18008613c  xor     r8d, r8d
0x18008613f  xor     edx, edx
0x180086141  mov     rcx, [rbp+arg_0]
0x180086145  mov     rax, r14
0x180086148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008614d  test    eax, eax
0x18008614f  js      short loc_180086159
0x180086151  mov     rbx, [rbp+arg_8]
0x180086155  shr     rbx, 14h
0x180086159  lea     rcx, [rbp+arg_0]
0x18008615d  mov     rax, rsi
0x180086160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086165  nop
0x180086166  mov     [rbp+var_10], r12
0x18008616a  cmp     [rbp+hModule], 0
0x18008616f  jz      short loc_18008617E
0x180086171  lea     rcx, [rbp+var_10]
0x180086175  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18008617a  test    al, al
0x18008617c  jz      short loc_180086195
0x18008617e  mov     rax, rbx
0x180086181  mov     rbx, [rsp+60h+arg_18]
0x180086189  add     rsp, 60h
0x18008618d  pop     r14
0x18008618f  pop     r12
0x180086191  pop     rdi
0x180086192  pop     rsi
0x180086193  pop     rbp
0x180086194  retn
0x180086195  call    cs:__imp_GetLastError
0x18008619b  test    eax, eax
0x18008619d  jle     short loc_1800861A7
0x18008619f  movzx   eax, ax
0x1800861a2  or      eax, 80070000h
0x1800861a7  mov     ecx, eax; this
0x1800861a9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
