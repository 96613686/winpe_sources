# ATL::CAtlComModule::UnregisterServer(int,_GUID const *)

- ea: `0x180005824`
- end: `0x180005965`
- name: `?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(GUID *this, const unsigned __int16 *, struct ITypeLib *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005f70`

## callees

- `0x18000387c`
- `0x180003a50`
- `0x180005824`
- `0x18000f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005949`
- `OLEAUT32!__imp_SysFreeString` at `0x180005949`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18000590c`
- `OLEAUT32!__imp_UnRegisterTypeLib` at `0x18000590c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlComModule::UnregisterServer(GUID *this, const unsigned __int16 *a2, struct ITypeLib *a3)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v3; // rdi
  __int64 *v4; // rax
  __int64 v5; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  HRESULT v7; // ebx
  GUID *libID; // [rsp+50h] [rbp+20h] BYREF
  struct ITypeLib *v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = a3;
  libID = this;
  v3 = off_180017350;
  v4 = (__int64 *)off_180017358;
  if ( off_180017350 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_180017358 )
  {
    do
    {
      v5 = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v5 + 56))();
        v7 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v7 = (*(__int64 (__fastcall **)(_QWORD))(v5 + 8))(0);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v4 = (__int64 *)off_180017358;
      }
      v3 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v3 + 8);
    }
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v4 );
  }
  bstrString = 0;
  v10 = 0;
  v7 = ATL::AtlLoadTypeLib(off_180017348, a2, &bstrString, &v10);
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
0x180005824  mov     [rsp-18h+arg_8], rbx
0x180005829  mov     [rsp-18h+arg_10], r8
0x18000582e  mov     [rsp-18h+libID], rcx
0x180005833  push    rbp
0x180005834  push    rsi
0x180005835  push    rdi
0x180005836  mov     rbp, rsp
0x180005839  sub     rsp, 30h
0x18000583d  xor     ebx, ebx
0x18000583f  mov     rdi, cs:off_180017350
0x180005846  mov     rax, cs:off_180017358
0x18000584d  cmp     rdi, rax
0x180005850  jnb     short loc_1800058A8
0x180005852  mov     rsi, [rdi]
0x180005855  test    rsi, rsi
0x180005858  jz      short loc_180005897
0x18000585a  mov     rax, [rsi+38h]
0x18000585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005863  xor     r8d, r8d; int
0x180005866  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005869  mov     rcx, [rsi]; rguid
0x18000586c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005871  mov     ebx, eax
0x180005873  test    eax, eax
0x180005875  js      loc_180005955
0x18000587b  xor     ecx, ecx
0x18000587d  mov     rax, [rsi+8]
0x180005881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005886  mov     ebx, eax
0x180005888  test    eax, eax
0x18000588a  js      loc_180005955
0x180005890  mov     rax, cs:off_180017358
0x180005897  add     rdi, 8
0x18000589b  cmp     rdi, rax
0x18000589e  jb      short loc_180005852
0x1800058a0  test    ebx, ebx
0x1800058a2  js      loc_180005955
0x1800058a8  mov     [rbp+bstrString], 0
0x1800058b0  mov     [rbp+arg_10], 0
0x1800058b8  lea     r9, [rbp+arg_10]; struct ITypeLib **
0x1800058bc  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800058c0  mov     rcx, cs:off_180017348; HINSTANCE
0x1800058c7  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x1800058cc  mov     ebx, eax
0x1800058ce  test    eax, eax
0x1800058d0  js      short loc_18000592F
0x1800058d2  mov     [rbp+libID], 0
0x1800058da  mov     rcx, [rbp+arg_10]
0x1800058de  mov     rax, [rcx]
0x1800058e1  lea     rdx, [rbp+libID]
0x1800058e5  mov     rax, [rax+38h]
0x1800058e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ee  mov     ebx, eax
0x1800058f0  test    eax, eax
0x1800058f2  js      short loc_18000592F
0x1800058f4  mov     rcx, [rbp+libID]; libID
0x1800058f8  mov     eax, [rcx+14h]
0x1800058fb  mov     [rsp+30h+syskind], eax; syskind
0x1800058ff  mov     r9d, [rcx+10h]; lcid
0x180005903  movzx   r8d, word ptr [rcx+1Ah]; wVerMinor
0x180005908  movzx   edx, word ptr [rcx+18h]; wVerMajor
0x18000590c  call    cs:__imp_UnRegisterTypeLib
0x180005913  nop     dword ptr [rax+rax+00h]
0x180005918  mov     ebx, eax
0x18000591a  mov     rcx, [rbp+arg_10]
0x18000591e  mov     rax, [rcx]
0x180005921  mov     rdx, [rbp+libID]
0x180005925  mov     rax, [rax+60h]
0x180005929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000592e  nop
0x18000592f  mov     rcx, [rbp+arg_10]
0x180005933  test    rcx, rcx
0x180005936  jz      short loc_180005945
0x180005938  mov     rax, [rcx]
0x18000593b  mov     rax, [rax+10h]
0x18000593f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005944  nop
0x180005945  mov     rcx, [rbp+bstrString]; bstrString
0x180005949  call    cs:__imp_SysFreeString
0x180005950  nop     dword ptr [rax+rax+00h]
0x180005955  mov     eax, ebx
0x180005957  mov     rbx, [rsp+30h+arg_8]
0x18000595c  add     rsp, 30h
0x180005960  pop     rdi
0x180005961  pop     rsi
0x180005962  pop     rbp
0x180005963  retn
```
