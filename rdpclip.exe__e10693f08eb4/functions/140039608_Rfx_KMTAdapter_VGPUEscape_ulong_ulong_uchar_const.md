# Rfx::KMTAdapter::VGPUEscape(ulong,ulong,uchar * const)

- ea: `0x140039608`
- end: `0x140039803`
- name: `?VGPUEscape@KMTAdapter@Rfx@@SAJKKQEAE@Z`
- size: `507`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140038a58`

## callees

- `0x14003769c`
- `0x140037844`
- `0x140038360`
- `0x140038520`
- `0x1400387a0`
- `0x140039608`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140039646`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140039646`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400396b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14003970e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400397d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400396b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14003970e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400397d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003969c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400396f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400397b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003969c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400396f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400397b7`

## string_xrefs

- `0x14003963a`: `gdi32.dll`

## pseudocode

```c
__int64 __fastcall Rfx::KMTAdapter::VGPUEscape(__int64 a1, int a2, unsigned __int8 *const a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  void **v11; // [rsp+20h] [rbp-59h] BYREF
  HMODULE Library; // [rsp+28h] [rbp-51h]
  unsigned int v13; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v14[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v15; // [rsp+40h] [rbp-39h]
  _QWORD *v16; // [rsp+48h] [rbp-31h]
  __int64 v17; // [rsp+50h] [rbp-29h]
  _DWORD v18[6]; // [rsp+58h] [rbp-21h] BYREF
  __int64 (__fastcall *v19)(_DWORD *); // [rsp+70h] [rbp-9h]
  _QWORD v20[2]; // [rsp+80h] [rbp+7h] BYREF
  int v21; // [rsp+90h] [rbp+17h]
  int v22; // [rsp+94h] [rbp+1Bh]
  unsigned __int8 *v23; // [rsp+98h] [rbp+1Fh]

  v13 = 0;
  Library = LoadLibraryExW(L"gdi32.dll", 0, 0);
  v11 = &Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::`vftable';
  if ( Library )
    goto LABEL_6;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_6:
    v6 = Rfx::KMTAdapter::OpenVGPUAdapterByEnumeration(&v11, &v13);
    if ( v6 >= 0 )
    {
      Rfx::KMTAdapter::KMTAdapter(v18, &v11, v13);
      v15 = 0x100000000LL;
      v20[0] = 0x617473696C6143LL;
      v14[0] = v18[0];
      v16 = v20;
      v20[1] = 5;
      v21 = 75264;
      v22 = a2;
      v23 = a3;
      v14[1] = 0;
      v17 = 32;
      HashEscape(1, 32, v20);
      v8 = v19(v14);
      Rfx::KMTAdapter::~KMTAdapter((Rfx::KMTAdapter *)v18);
      v11 = &Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::`vftable';
      if ( Library && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::InternalClose(&v11) )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        RaiseException(v9, 1u, 0, 0);
        __debugbreak();
      }
      return (unsigned int)(v8 | 0x10000000);
    }
    else
    {
      v11 = &Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::`vftable';
      if ( Library && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::InternalClose(&v11) )
      {
        v7 = GetLastError();
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        RaiseException(v7, 1u, 0, 0);
        __debugbreak();
      }
    }
  }
  else
  {
    v11 = &Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::`vftable';
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140039608  mov     [rsp-8+arg_0], rbx
0x14003960d  push    rbp
0x14003960e  push    rsi
0x14003960f  push    rdi
0x140039610  push    r12
0x140039612  push    r15
0x140039614  lea     rbp, [rsp-37h]
0x140039619  sub     rsp, 0B0h
0x140039620  mov     rax, cs:__security_cookie
0x140039627  xor     rax, rsp
0x14003962a  mov     [rbp+57h+var_30], rax
0x14003962e  mov     rsi, r8
0x140039631  mov     [rbp+57h+var_A0], 0
0x140039638  mov     edi, edx
0x14003963a  lea     rcx, aGdi32Dll_0; "gdi32.dll"
0x140039641  xor     r8d, r8d; dwFlags
0x140039644  xor     edx, edx; hFile
0x140039646  call    cs:__imp_LoadLibraryExW
0x14003964c  lea     r12, ??_7?$HandleT@UModuleTraits@Rfx@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::`vftable'
0x140039653  mov     [rbp+57h+var_A8], rax
0x140039657  mov     [rbp+57h+var_B0], r12
0x14003965b  mov     r15d, 80070000h
0x140039661  test    rax, rax
0x140039664  jnz     short loc_1400396BF
0x140039666  call    cs:__imp_GetLastError
0x14003966c  mov     ebx, eax
0x14003966e  test    eax, eax
0x140039670  jle     short loc_140039678
0x140039672  movzx   ebx, ax
0x140039675  or      ebx, r15d
0x140039678  test    ebx, ebx
0x14003967a  jns     short loc_1400396BF
0x14003967c  cmp     [rbp+57h+var_A8], 0
0x140039681  mov     [rbp+57h+var_B0], r12
0x140039685  jz      loc_1400397DE
0x14003968b  lea     rcx, [rbp+57h+var_B0]
0x14003968f  call    ?InternalClose@?$HandleT@UModuleTraits@Rfx@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::InternalClose(void)
0x140039694  test    al, al
0x140039696  jnz     loc_1400397DE
0x14003969c  call    cs:__imp_GetLastError
0x1400396a2  test    eax, eax
0x1400396a4  jle     short loc_1400396AC
0x1400396a6  movzx   eax, ax
0x1400396a9  or      eax, r15d
0x1400396ac  xor     r9d, r9d; lpArguments
0x1400396af  xor     r8d, r8d; nNumberOfArguments
0x1400396b2  mov     ecx, eax; dwExceptionCode
0x1400396b4  lea     edx, [r9+1]; dwExceptionFlags
0x1400396b8  call    cs:__imp_RaiseException
0x1400396be  int     3; Trap to Debugger
0x1400396bf  lea     rdx, [rbp+57h+var_A0]
0x1400396c3  lea     rcx, [rbp+57h+var_B0]
0x1400396c7  call    ?OpenVGPUAdapterByEnumeration@KMTAdapter@Rfx@@SAJAEBV?$HandleT@UModuleTraits@Rfx@@@Wrappers@WRL@Microsoft@@AEAI@Z; Rfx::KMTAdapter::OpenVGPUAdapterByEnumeration(Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits> const &,uint &)
0x1400396cc  mov     ebx, eax
0x1400396ce  test    eax, eax
0x1400396d0  jns     short loc_140039715
0x1400396d2  cmp     [rbp+57h+var_A8], 0
0x1400396d7  mov     [rbp+57h+var_B0], r12
0x1400396db  jz      loc_1400397DE
0x1400396e1  lea     rcx, [rbp+57h+var_B0]
0x1400396e5  call    ?InternalClose@?$HandleT@UModuleTraits@Rfx@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::InternalClose(void)
0x1400396ea  test    al, al
0x1400396ec  jnz     loc_1400397DE
0x1400396f2  call    cs:__imp_GetLastError
0x1400396f8  test    eax, eax
0x1400396fa  jle     short loc_140039702
0x1400396fc  movzx   eax, ax
0x1400396ff  or      eax, r15d
0x140039702  xor     r9d, r9d; lpArguments
0x140039705  xor     r8d, r8d; nNumberOfArguments
0x140039708  mov     ecx, eax; dwExceptionCode
0x14003970a  lea     edx, [r9+1]; dwExceptionFlags
0x14003970e  call    cs:__imp_RaiseException
0x140039714  int     3; Trap to Debugger
0x140039715  mov     r8d, [rbp+57h+var_A0]
0x140039719  lea     rdx, [rbp+57h+var_B0]
0x14003971d  lea     rcx, [rbp+57h+var_78]
0x140039721  call    ??0KMTAdapter@Rfx@@QEAA@AEAV?$HandleT@UModuleTraits@Rfx@@@Wrappers@WRL@Microsoft@@I@Z; Rfx::KMTAdapter::KMTAdapter(Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits> &,uint)
0x140039726  mov     rax, 617473696C6143h
0x140039730  mov     [rbp+57h+var_90], 0
0x140039738  mov     [rbp+57h+var_50], rax
0x14003973c  lea     r8, [rbp+57h+var_50]
0x140039740  mov     eax, [rbp+57h+var_78]
0x140039743  mov     edx, 20h ; ' '
0x140039748  mov     [rbp+57h+var_98], eax
0x14003974b  lea     rax, [rbp+57h+var_50]
0x14003974f  mov     [rbp+57h+var_88], rax
0x140039753  mov     [rbp+57h+var_48], 5
0x14003975b  lea     ecx, [rdx-1Fh]
0x14003975e  mov     [rbp+57h+var_40], 12600h
0x140039765  mov     [rbp+57h+var_3C], edi
0x140039768  mov     [rbp+57h+var_38], rsi
0x14003976c  mov     [rbp+57h+var_94], 0
0x140039773  mov     [rbp+57h+var_80], 20h ; ' '
0x14003977b  mov     dword ptr [rbp+57h+var_90+4], 1
0x140039782  call    ?HashEscape@@YAXU_D3DDDI_ESCAPEFLAGS@@IPEAX@Z; HashEscape(_D3DDDI_ESCAPEFLAGS,uint,void *)
0x140039787  mov     rax, [rbp+57h+var_60]
0x14003978b  lea     rcx, [rbp+57h+var_98]
0x14003978f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039794  lea     rcx, [rbp+57h+var_78]; this
0x140039798  mov     ebx, eax
0x14003979a  call    ??1KMTAdapter@Rfx@@QEAA@XZ; Rfx::KMTAdapter::~KMTAdapter(void)
0x14003979f  cmp     [rbp+57h+var_A8], 0
0x1400397a4  mov     [rbp+57h+var_B0], r12
0x1400397a8  jz      short loc_1400397DA
0x1400397aa  lea     rcx, [rbp+57h+var_B0]
0x1400397ae  call    ?InternalClose@?$HandleT@UModuleTraits@Rfx@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Rfx::ModuleTraits>::InternalClose(void)
0x1400397b3  test    al, al
0x1400397b5  jnz     short loc_1400397DA
0x1400397b7  call    cs:__imp_GetLastError
0x1400397bd  test    eax, eax
0x1400397bf  jle     short loc_1400397C7
0x1400397c1  movzx   eax, ax
0x1400397c4  or      eax, r15d
0x1400397c7  xor     r9d, r9d; lpArguments
0x1400397ca  xor     r8d, r8d; nNumberOfArguments
0x1400397cd  mov     ecx, eax; dwExceptionCode
0x1400397cf  lea     edx, [r9+1]; dwExceptionFlags
0x1400397d3  call    cs:__imp_RaiseException
0x1400397d9  int     3; Trap to Debugger
0x1400397da  bts     ebx, 1Ch
0x1400397de  mov     eax, ebx
0x1400397e0  mov     rcx, [rbp+57h+var_30]
0x1400397e4  xor     rcx, rsp; StackCookie
0x1400397e7  call    __security_check_cookie
0x1400397ec  mov     rbx, [rsp+0D0h+arg_0]
0x1400397f4  add     rsp, 0B0h
0x1400397fb  pop     r15
0x1400397fd  pop     r12
0x1400397ff  pop     rdi
0x140039800  pop     rsi
0x140039801  pop     rbp
0x140039802  retn
```
