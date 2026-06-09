# OSInfo::GetOSSubscriptionInfo(void)

- ea: `0x180060fd8`
- end: `0x1800610d8`
- name: `?GetOSSubscriptionInfo@OSInfo@@CA?AU_SubscriptionInfo_2@@XZ`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800610e0`
- `0x1800c08a0`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x180060fd8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180061004`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180061004`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006102a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006102a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061077`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061077`

## string_xrefs

- `0x180060ffd`: `clipc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 OSInfo::GetOSSubscriptionInfo()
{
  int v0; // ebx
  int v1; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v4; // eax
  HLOCAL v5; // rcx
  signed int LastError; // eax
  int v8; // edx
  unsigned int v9; // r8d
  const int *v10; // [rsp+20h] [rbp-18h] BYREF
  HMODULE v11; // [rsp+28h] [rbp-10h]
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  v0 = -1;
  v1 = -1;
  hMem = 0;
  Library = LoadLibraryExW(L"clipc.dll", 0, 0x800u);
  v10 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v11 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "ClipGetSubscriptionStatus")) != 0 )
  {
    v4 = ((__int64 (__fastcall *)(HLOCAL *))ProcAddress)(&hMem);
    v5 = hMem;
    if ( v4 >= 0 && hMem )
    {
      if ( *(_DWORD *)hMem )
      {
        v1 = *((_DWORD *)hMem + 2);
        if ( *(_DWORD *)hMem <= 1u )
          v0 = *((_DWORD *)hMem + 1);
        else
          v0 = -3;
      }
    }
    else
    {
      v0 = -2;
    }
  }
  else
  {
    v5 = hMem;
  }
  if ( v5 )
  {
    LocalFree(v5);
    hMem = 0;
  }
  v10 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v11 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v10) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v8, v9);
    JUMPOUT(0x1800610D7LL);
  }
  hMem = (HLOCAL)__PAIR64__(v1, v0);
  return __PAIR64__(v1, v0);
}

```

## disassembly

```asm
0x180060fd8  mov     [rsp+arg_8], rbx
0x180060fdd  mov     [rsp+arg_10], rbp
0x180060fe2  push    rdi
0x180060fe3  sub     rsp, 30h
0x180060fe7  or      ebx, 0FFFFFFFFh
0x180060fea  mov     edi, ebx
0x180060fec  mov     [rsp+38h+hMem], 0
0x180060ff5  xor     edx, edx; hFile
0x180060ff7  mov     r8d, 800h; dwFlags
0x180060ffd  lea     rcx, aClipcDll; "clipc.dll"
0x180061004  call    cs:__imp_LoadLibraryExW
0x18006100a  lea     rbp, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180061011  mov     [rsp+38h+var_18], rbp
0x180061016  mov     [rsp+38h+var_10], rax
0x18006101b  test    rax, rax
0x18006101e  jz      short loc_18006106D
0x180061020  lea     rdx, aClipgetsubscri; "ClipGetSubscriptionStatus"
0x180061027  mov     rcx, rax; hModule
0x18006102a  call    cs:__imp_GetProcAddress
0x180061030  test    rax, rax
0x180061033  jz      short loc_18006106D
0x180061035  lea     rcx, [rsp+38h+hMem]
0x18006103a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006103f  mov     rcx, [rsp+38h+hMem]
0x180061044  test    eax, eax
0x180061046  js      short loc_180061066
0x180061048  test    rcx, rcx
0x18006104b  jz      short loc_180061066
0x18006104d  cmp     dword ptr [rcx], 0
0x180061050  jbe     short loc_180061072
0x180061052  mov     edi, [rcx+8]
0x180061055  cmp     dword ptr [rcx], 1
0x180061058  jbe     short loc_180061061
0x18006105a  mov     ebx, 0FFFFFFFDh
0x18006105f  jmp     short loc_180061072
0x180061061  mov     ebx, [rcx+4]
0x180061064  jmp     short loc_180061072
0x180061066  mov     ebx, 0FFFFFFFEh
0x18006106b  jmp     short loc_180061072
0x18006106d  mov     rcx, [rsp+38h+hMem]; hMem
0x180061072  test    rcx, rcx
0x180061075  jz      short loc_180061086
0x180061077  call    cs:__imp_LocalFree
0x18006107d  mov     [rsp+38h+hMem], 0
0x180061086  mov     [rsp+38h+var_18], rbp
0x18006108b  cmp     [rsp+38h+var_10], 0
0x180061091  jz      short loc_1800610A1
0x180061093  lea     rcx, [rsp+38h+var_18]
0x180061098  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18006109d  test    al, al
0x18006109f  jz      short loc_1800610BE
0x1800610a1  mov     dword ptr [rsp+38h+hMem], ebx
0x1800610a5  mov     dword ptr [rsp+38h+hMem+4], edi
0x1800610a9  mov     rax, [rsp+38h+hMem]
0x1800610ae  mov     rbx, [rsp+38h+arg_8]
0x1800610b3  mov     rbp, [rsp+38h+arg_10]
0x1800610b8  add     rsp, 30h
0x1800610bc  pop     rdi
0x1800610bd  retn
0x1800610be  call    cs:__imp_GetLastError
0x1800610c4  test    eax, eax
0x1800610c6  jle     short loc_1800610D0
0x1800610c8  movzx   eax, ax
0x1800610cb  or      eax, 80070000h
0x1800610d0  mov     ecx, eax; this
0x1800610d2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
