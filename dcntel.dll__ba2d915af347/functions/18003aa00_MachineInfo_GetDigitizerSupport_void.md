# MachineInfo::GetDigitizerSupport(void)

- ea: `0x18003aa00`
- end: `0x18003ab58`
- name: `?GetDigitizerSupport@MachineInfo@@AEBAHXZ`
- size: `344`
- prototype: `__int64 __fastcall(MachineInfo *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180009260`
- `0x1800092e0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a690`
- `0x18003aa00`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003aa44`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003aa44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003aa6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003aa6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab3e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18003aa0e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18003aa0e`

## string_xrefs

- `0x18003aa3d`: `minuser.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MachineInfo::GetDigitizerSupport(MachineInfo *this)
{
  unsigned int SystemMetrics; // ebx
  unsigned __int16 v2; // r8
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v5)(_QWORD, _QWORD); // rdi
  _DWORD *v6; // rsi
  unsigned int i; // r8d
  signed int LastError; // eax
  int v10; // edx
  unsigned int v11; // r8d
  const int *v12; // [rsp+20h] [rbp-38h] BYREF
  HMODULE v13; // [rsp+28h] [rbp-30h]
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF

  SystemMetrics = GetSystemMetrics(94);
  if ( !SystemMetrics && IsWindowsVersionOrGreater(6u, 2u, v2) )
  {
    v14 = SystemMetrics;
    Library = LoadLibraryExW(L"minuser.dll", 0, 0x800u);
    v12 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    v13 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetPointerDevices");
      v5 = (unsigned int (__fastcall *)(_QWORD, _QWORD))ProcAddress;
      if ( ProcAddress )
      {
        if ( ((unsigned int (__fastcall *)(unsigned int *, _QWORD))ProcAddress)(&v14, 0) == 1 && v14 )
        {
          v6 = operator new[](saturated_mul(v14, 0x438u));
          if ( v5(&v14, v6) )
          {
            for ( i = 0; i < v14; ++i )
            {
              switch ( v6[270 * i + 4] )
              {
                case 1:
                  SystemMetrics |= 4u;
                  break;
                case 2:
                  SystemMetrics |= 8u;
                  break;
                case 3:
                  SystemMetrics |= 1u;
                  break;
              }
            }
          }
          operator delete(v6);
        }
      }
    }
    v12 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v13 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v12) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v10, v11);
      JUMPOUT(0x18003AB57LL);
    }
  }
  return SystemMetrics;
}

```

## disassembly

```asm
0x18003aa00  push    rbx
0x18003aa02  push    rbp
0x18003aa03  push    rsi
0x18003aa04  push    rdi
0x18003aa05  sub     rsp, 38h
0x18003aa09  mov     ecx, 5Eh ; '^'; nIndex
0x18003aa0e  call    cs:__imp_GetSystemMetrics
0x18003aa14  mov     ebx, eax
0x18003aa16  test    eax, eax
0x18003aa18  jnz     loc_18003AB33
0x18003aa1e  lea     edx, [rax+2]; unsigned __int16
0x18003aa21  lea     ecx, [rax+6]; unsigned __int16
0x18003aa24  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18003aa29  test    al, al
0x18003aa2b  jz      loc_18003AB33
0x18003aa31  mov     [rsp+58h+arg_8], ebx
0x18003aa35  xor     edx, edx; hFile
0x18003aa37  mov     r8d, 800h; dwFlags
0x18003aa3d  lea     rcx, aMinuserDll; "minuser.dll"
0x18003aa44  call    cs:__imp_LoadLibraryExW
0x18003aa4a  lea     rbp, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003aa51  mov     [rsp+58h+var_38], rbp
0x18003aa56  mov     [rsp+58h+var_30], rax
0x18003aa5b  test    rax, rax
0x18003aa5e  jz      loc_18003AB18
0x18003aa64  lea     rdx, aGetpointerdevi; "GetPointerDevices"
0x18003aa6b  mov     rcx, rax; hModule
0x18003aa6e  call    cs:__imp_GetProcAddress
0x18003aa74  mov     rdi, rax
0x18003aa77  test    rax, rax
0x18003aa7a  jz      loc_18003AB18
0x18003aa80  xor     edx, edx
0x18003aa82  lea     rcx, [rsp+58h+arg_8]
0x18003aa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa8c  cmp     eax, 1
0x18003aa8f  jnz     loc_18003AB18
0x18003aa95  mov     eax, [rsp+58h+arg_8]
0x18003aa99  test    eax, eax
0x18003aa9b  jz      short loc_18003AB18
0x18003aa9d  mov     ecx, eax
0x18003aa9f  mov     eax, 438h
0x18003aaa4  mul     rcx
0x18003aaa7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003aaae  cmovb   rax, rcx
0x18003aab2  mov     rcx, rax; unsigned __int64
0x18003aab5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003aaba  mov     rsi, rax
0x18003aabd  mov     rdx, rax
0x18003aac0  lea     rcx, [rsp+58h+arg_8]
0x18003aac5  mov     rax, rdi
0x18003aac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aacd  test    eax, eax
0x18003aacf  jz      short loc_18003AB0F
0x18003aad1  xor     r8d, r8d
0x18003aad4  mov     r9d, [rsp+58h+arg_8]
0x18003aad9  test    r9d, r9d
0x18003aadc  jz      short loc_18003AB0F
0x18003aade  mov     eax, r8d
0x18003aae1  imul    rcx, rax, 438h
0x18003aae8  mov     edx, [rcx+rsi+10h]
0x18003aaec  sub     edx, 1
0x18003aaef  jz      short loc_18003AB04
0x18003aaf1  sub     edx, 1
0x18003aaf4  jz      short loc_18003AAFF
0x18003aaf6  cmp     edx, 1
0x18003aaf9  jnz     short loc_18003AB07
0x18003aafb  or      ebx, edx
0x18003aafd  jmp     short loc_18003AB07
0x18003aaff  or      ebx, 8
0x18003ab02  jmp     short loc_18003AB07
0x18003ab04  or      ebx, 4
0x18003ab07  inc     r8d
0x18003ab0a  cmp     r8d, r9d
0x18003ab0d  jb      short loc_18003AADE
0x18003ab0f  mov     rcx, rsi; Block
0x18003ab12  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ab17  nop
0x18003ab18  mov     [rsp+58h+var_38], rbp
0x18003ab1d  cmp     [rsp+58h+var_30], 0
0x18003ab23  jz      short loc_18003AB33
0x18003ab25  lea     rcx, [rsp+58h+var_38]
0x18003ab2a  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003ab2f  test    al, al
0x18003ab31  jz      short loc_18003AB3E
0x18003ab33  mov     eax, ebx
0x18003ab35  add     rsp, 38h
0x18003ab39  pop     rdi
0x18003ab3a  pop     rsi
0x18003ab3b  pop     rbp
0x18003ab3c  pop     rbx
0x18003ab3d  retn
0x18003ab3e  call    cs:__imp_GetLastError
0x18003ab44  test    eax, eax
0x18003ab46  jle     short loc_18003AB50
0x18003ab48  movzx   eax, ax
0x18003ab4b  or      eax, 80070000h
0x18003ab50  mov     ecx, eax; this
0x18003ab52  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
