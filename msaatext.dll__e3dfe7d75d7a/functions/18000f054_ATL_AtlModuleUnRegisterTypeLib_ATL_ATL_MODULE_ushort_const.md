# ATL::AtlModuleUnRegisterTypeLib(ATL::_ATL_MODULE *,ushort const *)

- ea: `0x18000f054`
- end: `0x18000f147`
- name: `?AtlModuleUnRegisterTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBG@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800128a0`

## callees

- `0x18000ecfc`
- `0x18000f054`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f137`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f137`
- `KERNEL32!LoadLibraryExW` at `0x18000f0bd`
- `KERNEL32!LoadLibraryExW` at `0x18000f0bd`
- `KERNEL32!GetProcAddress` at `0x18000f0d5`
- `KERNEL32!GetProcAddress` at `0x18000f0d5`
- `KERNEL32!FreeLibrary` at `0x18000f102`
- `KERNEL32!FreeLibrary` at `0x18000f102`

## string_xrefs

- `0x18000f0b6`: `oleaut32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::AtlModuleUnRegisterTypeLib(struct ATL::_ATL_MODULE *a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  struct ATL::_ATL_MODULE *v7; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v8; // [rsp+58h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF

  v7 = a1;
  bstrString = 0;
  v8 = 0;
  v2 = ATL::AtlModuleLoadTypeLib(a1, a2, &bstrString, &v8);
  if ( v2 >= 0 )
  {
    v7 = 0;
    v2 = ((__int64 (__fastcall *)(struct ITypeLib *, struct ATL::_ATL_MODULE **))v8->lpVtbl->GetLibAttr)(v8, &v7);
    if ( v2 >= 0 )
    {
      Library = LoadLibraryExW(L"oleaut32.dll", 0, 0);
      v4 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "UnRegisterTypeLib");
        if ( ProcAddress )
          v2 = ((__int64 (__fastcall *)(struct ATL::_ATL_MODULE *, _QWORD, _QWORD, _QWORD, _DWORD))ProcAddress)(
                 v7,
                 *((unsigned __int16 *)v7 + 12),
                 *((unsigned __int16 *)v7 + 13),
                 *((unsigned int *)v7 + 4),
                 *((_DWORD *)v7 + 5));
        FreeLibrary(v4);
      }
      ((void (__fastcall *)(struct ITypeLib *, struct ATL::_ATL_MODULE *))v8->lpVtbl->ReleaseTLibAttr)(v8, v7);
    }
  }
  if ( v8 )
    ((void (__fastcall *)(struct ITypeLib *))v8->lpVtbl->Release)(v8);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f054  mov     [rsp-18h+arg_8], rdx
0x18000f059  mov     [rsp-18h+arg_0], rcx
0x18000f05e  push    rbp
0x18000f05f  push    rbx
0x18000f060  push    rdi
0x18000f061  mov     rbp, rsp
0x18000f064  sub     rsp, 30h
0x18000f068  mov     [rbp+bstrString], 0
0x18000f070  mov     [rbp+arg_8], 0
0x18000f078  lea     r9, [rbp+arg_8]; struct ITypeLib **
0x18000f07c  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000f080  call    ?AtlModuleLoadTypeLib@ATL@@YAJPEAU_ATL_MODULE@1@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlModuleLoadTypeLib(ATL::_ATL_MODULE *,ushort const *,ushort * *,ITypeLib * *)
0x18000f085  mov     ebx, eax
0x18000f087  test    eax, eax
0x18000f089  js      loc_18000F11D
0x18000f08f  mov     [rbp+arg_0], 0
0x18000f097  mov     rcx, [rbp+arg_8]
0x18000f09b  mov     rax, [rcx]
0x18000f09e  lea     rdx, [rbp+arg_0]
0x18000f0a2  mov     rax, [rax+38h]
0x18000f0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ab  mov     ebx, eax
0x18000f0ad  test    eax, eax
0x18000f0af  js      short loc_18000F11D
0x18000f0b1  xor     r8d, r8d; dwFlags
0x18000f0b4  xor     edx, edx; hFile
0x18000f0b6  lea     rcx, LibFileName; "oleaut32.dll"
0x18000f0bd  call    cs:__imp_LoadLibraryExW
0x18000f0c3  mov     rdi, rax
0x18000f0c6  test    rax, rax
0x18000f0c9  jz      short loc_18000F108
0x18000f0cb  lea     rdx, ProcName; "UnRegisterTypeLib"
0x18000f0d2  mov     rcx, rax; hModule
0x18000f0d5  call    cs:__imp_GetProcAddress
0x18000f0db  test    rax, rax
0x18000f0de  jz      short loc_18000F0FF
0x18000f0e0  mov     rcx, [rbp+arg_0]
0x18000f0e4  mov     edx, [rcx+14h]
0x18000f0e7  mov     [rsp+30h+var_10], edx
0x18000f0eb  mov     r9d, [rcx+10h]
0x18000f0ef  movzx   r8d, word ptr [rcx+1Ah]
0x18000f0f4  movzx   edx, word ptr [rcx+18h]
0x18000f0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0fd  mov     ebx, eax
0x18000f0ff  mov     rcx, rdi; hLibModule
0x18000f102  call    cs:__imp_FreeLibrary
0x18000f108  mov     rcx, [rbp+arg_8]
0x18000f10c  mov     rax, [rcx]
0x18000f10f  mov     rdx, [rbp+arg_0]
0x18000f113  mov     rax, [rax+60h]
0x18000f117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11c  nop
0x18000f11d  mov     rcx, [rbp+arg_8]
0x18000f121  test    rcx, rcx
0x18000f124  jz      short loc_18000F133
0x18000f126  mov     rax, [rcx]
0x18000f129  mov     rax, [rax+10h]
0x18000f12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f132  nop
0x18000f133  mov     rcx, [rbp+bstrString]; bstrString
0x18000f137  call    cs:__imp_SysFreeString
0x18000f13d  mov     eax, ebx
0x18000f13f  add     rsp, 30h
0x18000f143  pop     rdi
0x18000f144  pop     rbx
0x18000f145  pop     rbp
0x18000f146  retn
```
