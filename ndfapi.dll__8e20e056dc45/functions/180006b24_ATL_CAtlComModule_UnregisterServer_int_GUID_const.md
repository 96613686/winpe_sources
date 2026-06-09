# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x180006b24`
- end: `0x180006c58`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this, int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800078e0`

## callees

- `0x180004e34`
- `0x180004fdc`
- `0x180006b24`
- `0x180021010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c43`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180006c0c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x180006c0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_18002F450;
  for ( i = off_18002F458; v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v3 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
      v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
      if ( v7 < 0 )
        return (unsigned int)v7;
      i = off_18002F458;
    }
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_18002F448, a2, &bstrString, &v10);
  if ( v7 >= 0 )
  {
    libID = 0;
    v7 = ((__int64 (__fastcall *)(struct ITypeLib *, GUID **))v10->lpVtbl->GetLibAttr)(v10, &libID);
    if ( v7 >= 0 )
    {
      v7 = UnRegisterTypeLib(
             libID,
             *(_WORD *)libID[1].Data4,
             *(_WORD *)&libID[1].Data4[2],
             libID[1].Data1,
             *(SYSKIND *)&libID[1].Data2);
      ((void (__fastcall *)(struct ITypeLib *, GUID *))v10->lpVtbl->ReleaseTLibAttr)(v10, libID);
    }
  }
  if ( v10 )
    ((void (__fastcall *)(struct ITypeLib *))v10->lpVtbl->Release)(v10);
  SysFreeString(bstrString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006b24  mov     [rsp-18h+arg_8], rbx
0x180006b29  mov     [rsp-18h+arg_10], r8
0x180006b2e  mov     [rsp-18h+libID], rcx
0x180006b33  push    rbp
0x180006b34  push    rsi
0x180006b35  push    rdi
0x180006b36  mov     rbp, rsp
0x180006b39  sub     rsp, 30h
0x180006b3d  xor     ebx, ebx
0x180006b3f  mov     rdi, cs:off_18002F450
0x180006b46  mov     rax, cs:off_18002F458
0x180006b4d  cmp     rdi, rax
0x180006b50  jnb     short loc_180006BA8
0x180006b52  mov     rsi, [rdi]
0x180006b55  test    rsi, rsi
0x180006b58  jz      short loc_180006B97
0x180006b5a  mov     rax, [rsi+38h]
0x180006b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b63  xor     r8d, r8d; int
0x180006b66  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006b69  mov     rcx, [rsi]; rguid
0x180006b6c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006b71  mov     ebx, eax
0x180006b73  test    eax, eax
0x180006b75  js      loc_180006C49
0x180006b7b  xor     ecx, ecx
0x180006b7d  mov     rax, [rsi+8]
0x180006b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b86  mov     ebx, eax
0x180006b88  test    eax, eax
0x180006b8a  js      loc_180006C49
0x180006b90  mov     rax, cs:off_18002F458
0x180006b97  add     rdi, 8
0x180006b9b  cmp     rdi, rax
0x180006b9e  jb      short loc_180006B52
0x180006ba0  test    ebx, ebx
0x180006ba2  js      loc_180006C49
0x180006ba8  mov     [rbp+bstrString], 0
0x180006bb0  mov     [rbp+arg_10], 0
0x180006bb8  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x180006bbc  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180006bc0  mov     rcx, cs:off_18002F448; HINSTANCE
0x180006bc7  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x180006bcc  mov     ebx, eax
0x180006bce  test    eax, eax
0x180006bd0  js      short loc_180006C29
0x180006bd2  mov     [rbp+libID], 0
0x180006bda  mov     rcx, [rbp+arg_10]
0x180006bde  mov     rax, [rcx]
0x180006be1  lea     rdx, [rbp+libID]
0x180006be5  mov     rax, [rax+38h]
0x180006be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bee  mov     ebx, eax
0x180006bf0  test    eax, eax
0x180006bf2  js      short loc_180006C29
0x180006bf4  mov     rcx, [rbp+libID]; libID
0x180006bf8  mov     eax, [rcx+14h]
0x180006bfb  mov     [rsp+30h+syskind], eax; syskind
0x180006bff  mov     r9d, [rcx+10h]; lcid
0x180006c03  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180006c08  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x180006c0c  call    cs:__imp_UnRegisterTypeLib
0x180006c12  mov     ebx, eax
0x180006c14  mov     rcx, [rbp+arg_10]
0x180006c18  mov     rax, [rcx]
0x180006c1b  mov     rdx, [rbp+libID]
0x180006c1f  mov     rax, [rax+60h]
0x180006c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c28  nop
0x180006c29  mov     rcx, [rbp+arg_10]
0x180006c2d  test    rcx, rcx
0x180006c30  jz      short loc_180006C3F
0x180006c32  mov     rax, [rcx]
0x180006c35  mov     rax, [rax+10h]
0x180006c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c3e  nop
0x180006c3f  mov     rcx, [rbp+bstrString]; bstrString
0x180006c43  call    cs:__imp_SysFreeString
0x180006c49  mov     eax, ebx
0x180006c4b  mov     rbx, [rsp+30h+arg_8]
0x180006c50  add     rsp, 30h
0x180006c54  pop     rdi
0x180006c55  pop     rsi
0x180006c56  pop     rbp
0x180006c57  retn
```
