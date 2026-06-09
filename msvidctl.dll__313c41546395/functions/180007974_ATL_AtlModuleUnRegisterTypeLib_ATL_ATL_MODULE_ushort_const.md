# ATL::AtlModuleUnRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)

- ea: `0x180007974`
- end: `0x180007a56`
- name: `?AtlModuleUnRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cea0`

## callees

- `0x180006b38`
- `0x1800073b0`
- `0x180007974`
- `0x1800f8010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a46`
- `KERNEL32!FreeLibrary` at `0x180007a1d`
- `KERNEL32!FreeLibrary` at `0x180007a1d`
- `KERNEL32!LoadLibraryExW` at `0x1800079d8`
- `KERNEL32!LoadLibraryExW` at `0x1800079d8`
- `KERNEL32!GetProcAddress` at `0x1800079f0`
- `KERNEL32!GetProcAddress` at `0x1800079f0`

## string_xrefs

- `0x1800079d1`: `oleaut32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::AtlModuleUnRegisterTypeLib(struct ATL::_ATL_MODULE *a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  struct ITypeLib *v7; // [rsp+50h] [rbp+20h] BYREF
  __int64 v8; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  bstrString = 0;
  v7 = 0;
  v2 = ATL::AtlModuleLoadTypeLib(a1, a2, &bstrString, &v7);
  if ( v2 >= 0 )
  {
    v8 = 0;
    v2 = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))v7->lpVtbl->GetLibAttr)(v7, &v8);
    if ( v2 >= 0 )
    {
      Library = LoadLibraryExW(L"oleaut32.dll", 0, 0);
      v4 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "UnRegisterTypeLib");
        if ( ProcAddress )
          v2 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
                 v8,
                 *(unsigned __int16 *)(v8 + 24),
                 *(unsigned __int16 *)(v8 + 26),
                 *(unsigned int *)(v8 + 16),
                 *(_DWORD *)(v8 + 20));
        FreeLibrary(v4);
      }
      ((void (__fastcall *)(struct ITypeLib *, __int64))v7->lpVtbl->ReleaseTLibAttr)(v7, v8);
    }
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v7);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007974  mov     [rsp-18h+arg_0], rcx
0x180007979  push    rbp
0x18000797a  push    rbx
0x18000797b  push    rdi
0x18000797c  mov     rbp, rsp
0x18000797f  sub     rsp, 30h
0x180007983  mov     [rbp+bstrString], 0
0x18000798b  mov     [rbp+arg_0], 0
0x180007993  lea     r9, [rbp+arg_0]; struct ITypeLib **
0x180007997  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000799b  call    ?AtlModuleLoadTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlModuleLoadTypeLib(ATL::_ATL_MODULE *,ushort const *,ushort * *,ITypeLib * *)
0x1800079a0  mov     ebx, eax
0x1800079a2  test    eax, eax
0x1800079a4  js      loc_180007A38
0x1800079aa  mov     [rbp+arg_10], 0
0x1800079b2  mov     rcx, [rbp+arg_0]
0x1800079b6  mov     rax, [rcx]
0x1800079b9  lea     rdx, [rbp+arg_10]
0x1800079bd  mov     rax, [rax+38h]
0x1800079c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c6  mov     ebx, eax
0x1800079c8  test    eax, eax
0x1800079ca  js      short loc_180007A38
0x1800079cc  xor     r8d, r8d; dwFlags
0x1800079cf  xor     edx, edx; hFile
0x1800079d1  lea     rcx, aOleaut32Dll_0; "oleaut32.dll"
0x1800079d8  call    cs:__imp_LoadLibraryExW
0x1800079de  mov     rdi, rax
0x1800079e1  test    rax, rax
0x1800079e4  jz      short loc_180007A23
0x1800079e6  lea     rdx, aUnregistertype; "UnRegisterTypeLib"
0x1800079ed  mov     rcx, rax; hModule
0x1800079f0  call    cs:__imp_GetProcAddress
0x1800079f6  test    rax, rax
0x1800079f9  jz      short loc_180007A1A
0x1800079fb  mov     rcx, [rbp+arg_10]
0x1800079ff  mov     edx, [rcx+14h]
0x180007a02  mov     [rsp+30h+var_10], edx
0x180007a06  mov     r9d, [rcx+10h]
0x180007a0a  movzx   r8d, word ptr [rcx+1Ah]
0x180007a0f  movzx   edx, word ptr [rcx+18h]
0x180007a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a18  mov     ebx, eax
0x180007a1a  mov     rcx, rdi; hLibModule
0x180007a1d  call    cs:__imp_FreeLibrary
0x180007a23  mov     rcx, [rbp+arg_0]
0x180007a27  mov     rax, [rcx]
0x180007a2a  mov     rdx, [rbp+arg_10]
0x180007a2e  mov     rax, [rax+60h]
0x180007a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a37  nop
0x180007a38  lea     rcx, [rbp+arg_0]
0x180007a3c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180007a41  nop
0x180007a42  mov     rcx, [rbp+bstrString]; bstrString
0x180007a46  call    cs:__imp_SysFreeString
0x180007a4c  mov     eax, ebx
0x180007a4e  add     rsp, 30h
0x180007a52  pop     rdi
0x180007a53  pop     rbx
0x180007a54  pop     rbp
0x180007a55  retn
```
