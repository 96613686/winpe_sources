# Projection::ProjectionMarshaler::TransferOwnershipAndReadInterfaceFromClassName(IInspectable *,HSTRING__ *,int,Projection::ConstructorArguments *)

- ea: `0x180091978`
- end: `0x180091d04`
- name: `?TransferOwnershipAndReadInterfaceFromClassName@ProjectionMarshaler@Projection@@QEAAPEAXPEAUIInspectable@@PEAUHSTRING__@@HPEAUConstructorArguments@2@@Z`
- size: `908`
- prototype: `void *__fastcall(Projection::ProjectionMarshaler *__hidden this, struct IInspectable *, HSTRING, int, struct Projection::ConstructorArguments *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180091764`

## callees

- `0x180004014`
- `0x180004054`
- `0x180069aa0`
- `0x18008abf8`
- `0x18008ac88`
- `0x18008ad14`
- `0x18008ade4`
- `0x18008af9c`
- `0x18008c8dc`
- `0x180091978`
- `0x18029f6b0`
- `0x18038f438`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180091cad`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180091ce0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180091cad`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180091ce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void *__fastcall Projection::ProjectionMarshaler::TransferOwnershipAndReadInterfaceFromClassName(
        Projection::ProjectionMarshaler *this,
        struct IUnknown *a2,
        HSTRING a3,
        int a4,
        struct Projection::ConstructorArguments *a5)
{
  ThreadContext **v6; // r15
  ThreadContext *v7; // rdi
  char v8; // bl
  int v9; // esi
  struct IUnknown *v10; // rdi
  __int64 v11; // rbx
  char *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r10
  int i; // ecx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rbx
  ThreadContext *v19; // rsi
  char v20; // di
  int v21; // ebx
  void *PropertyValueVarFromRuntimeClassName; // rbx
  __int64 v24; // rax
  __int64 v25; // rbx
  struct Windows::Foundation::IPropertyValue *v26; // r9
  const WCHAR *v27; // rax
  const WCHAR *v28; // rax
  struct IUnknown *v29; // [rsp+58h] [rbp-41h] BYREF
  struct Windows::Foundation::IPropertyValue *v30[2]; // [rsp+60h] [rbp-39h] BYREF
  HSTRING v31; // [rsp+70h] [rbp-29h] BYREF
  _QWORD *v32; // [rsp+78h] [rbp-21h]
  ThreadContext *v33; // [rsp+80h] [rbp-19h]
  char v34; // [rsp+88h] [rbp-11h]
  _BYTE v35[88]; // [rsp+90h] [rbp-9h] BYREF
  void *retaddr; // [rsp+F0h] [rbp+57h]

  v30[1] = (struct Windows::Foundation::IPropertyValue *)-2LL;
  v6 = *(ThreadContext ***)(*((_QWORD *)this + 2) + 112LL);
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v6);
  v29 = 0;
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v35, v6, retaddr);
  v7 = v6[110];
  v33 = v7;
  v34 = *((_BYTE *)v7 + 313);
  v8 = v34;
  *((_BYTE *)v7 + 313) = 1;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IUnknown,
         &v29);
  ThreadContext::DisposeOnLeaveScript(v6[110]);
  *((_BYTE *)v7 + 313) = v8;
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v35);
  if ( v9 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v6, v9);
  v10 = v29;
  if ( v29 )
  {
    v11 = *((_QWORD *)this + 4);
    v12 = Memory::ArenaAllocator::Alloc(*((Memory::ArenaAllocator **)this + 1), 0x10u);
    *(_QWORD *)v12 = v10;
    *((_QWORD *)v12 + 1) = v11;
    *((_QWORD *)this + 4) = v12;
  }
  v13 = *(_QWORD *)(*((_QWORD *)Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this
                                                                                   + 2))
                    + 17)
                  + 40LL);
  if ( *(_QWORD *)v13 )
  {
    v14 = *(_QWORD *)(v13 + 8);
    for ( i = *(_DWORD *)(*(_QWORD *)v13
                        + 4
                        * ((unsigned int)(*(_DWORD *)(v13 + 28) - 1)
                         & (((unsigned __int64)v29 >> 4)
                          & 0x7FFFFFFF
                          ^ ((((unsigned __int64)v29 >> 4) & 0x7FFFFFFF) >> 15)
                          ^ ((((unsigned __int64)v29 >> 4)
                            & 0x7FFFFFFF
                            ^ ((((unsigned __int64)v29 >> 4) & 0x7FFFFFFF) >> 15)) >> 7))));
          i >= 0;
          i = *(_DWORD *)(v14 + 24LL * i + 8) )
    {
      if ( *(struct IUnknown **)(v14 + 24LL * i + 16) == v29 )
      {
        _mm_lfence();
        v16 = **(_QWORD **)(*(_QWORD *)(v13 + 8) + 24LL * i);
        if ( !v16 )
          break;
        Projection::ProjectionContext::TypeInstanceCreated(*((Projection::ProjectionContext **)this + 2), a2);
        v24 = *((_QWORD *)this + 2);
        v25 = *(_QWORD *)(v24 + 96) + 7920LL;
        if ( !*(_BYTE *)(*(_QWORD *)(v24 + 96) + 7936LL) )
        {
          v27 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(*(_QWORD *)(v24 + 96) + 7920LL);
          *(_QWORD *)(v25 + 8) = LoadLibraryExW(v27, 0, 0x800u);
          *(_BYTE *)(v25 + 16) = 1;
        }
        (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v25 + 32LL))(v25, a3);
        return (void *)v16;
      }
    }
  }
  v17 = *((_QWORD *)this + 2);
  v18 = *(_QWORD *)(v17 + 96) + 7920LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v17 + 96) + 7936LL) )
  {
    v28 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(*(_QWORD *)(v17 + 96) + 7920LL);
    *(_QWORD *)(v18 + 8) = LoadLibraryExW(v28, 0, 0x800u);
    *(_BYTE *)(v18 + 16) = 1;
  }
  v32 = (_QWORD *)v18;
  v31 = a3;
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 32LL))(v18, 0);
  v30[0] = 0;
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v35, v6, retaddr);
  v19 = v6[110];
  v33 = v19;
  v34 = *((_BYTE *)v19 + 313);
  v20 = v34;
  *((_BYTE *)v19 + 313) = 1;
  v21 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct Windows::Foundation::IPropertyValue **))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
          v30);
  ThreadContext::DisposeOnLeaveScript(v6[110]);
  *((_BYTE *)v19 + 313) = v20;
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v35);
  if ( v21 >= 0 )
  {
    v26 = v30[0];
    if ( v30[0] )
    {
      *((_QWORD *)this + 4) = regex::ImmutableList<HSTRING__ *>::Prepend(
                                *((_QWORD *)this + 4),
                                v30[0],
                                *((_QWORD *)this + 1));
      v26 = v30[0];
    }
    PropertyValueVarFromRuntimeClassName = Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(
                                             this,
                                             (struct AutoHSTRING *)&v31,
                                             v29,
                                             v26,
                                             1,
                                             0,
                                             a4);
    if ( v31 )
      (*(void (__fastcall **)(_QWORD *))(*v32 + 32LL))(v32);
  }
  else
  {
    PropertyValueVarFromRuntimeClassName = Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(
                                             this,
                                             (struct AutoHSTRING *)&v31,
                                             v29,
                                             (struct IInspectable *)a2,
                                             1,
                                             0,
                                             0,
                                             a4,
                                             a5);
    if ( v31 )
      (*(void (__fastcall **)(_QWORD *, HSTRING, _QWORD))(*v32 + 32LL))(v32, v31, *v32);
  }
  return PropertyValueVarFromRuntimeClassName;
}

```

## disassembly

```asm
0x180091978  mov     rax, rsp
0x18009197b  mov     [rax+20h], r9d
0x18009197f  mov     [rax+18h], r8
0x180091983  mov     [rax+10h], rdx
0x180091987  mov     [rax+8], rcx
0x18009198b  push    rbp
0x18009198c  push    rbx
0x18009198d  push    rsi
0x18009198e  push    rdi
0x18009198f  push    r12
0x180091991  push    r14
0x180091993  push    r15
0x180091995  lea     rbp, [rax-57h]
0x180091999  sub     rsp, 0B0h
0x1800919a0  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFEh
0x1800919a8  mov     r14, [rbp+4Fh+arg_0]
0x1800919ac  mov     rax, [r14+10h]
0x1800919b0  mov     r15, [rax+70h]
0x1800919b4  mov     rcx, r15; struct Js::ScriptContext *
0x1800919b7  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1800919bc  mov     [rbp+4Fh+var_90], 0
0x1800919c4  mov     r8, [rbp+57h]
0x1800919c8  mov     rdx, r15
0x1800919cb  lea     rcx, [rbp+4Fh+var_58]
0x1800919cf  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1800919d4  nop
0x1800919d5  mov     rdi, [r15+370h]
0x1800919dc  mov     [rbp+4Fh+var_68], rdi
0x1800919e0  mov     bl, [rdi+139h]
0x1800919e6  mov     [rbp+4Fh+var_60], bl
0x1800919e9  mov     byte ptr [rdi+139h], 1
0x1800919f0  mov     r12, [rbp+4Fh+arg_8]
0x1800919f4  mov     rax, [r12]
0x1800919f8  lea     r8, [rbp+4Fh+var_90]
0x1800919fc  lea     rdx, IID_IUnknown
0x180091a03  mov     rcx, r12
0x180091a06  mov     rax, [rax]
0x180091a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a0e  mov     esi, eax
0x180091a10  mov     rcx, [r15+370h]; this
0x180091a17  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x180091a1c  nop
0x180091a1d  mov     [rdi+139h], bl
0x180091a23  lea     rcx, [rbp+4Fh+var_58]
0x180091a27  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x180091a2c  test    esi, esi
0x180091a2e  js      loc_180091CF9
0x180091a34  mov     rdi, [rbp+4Fh+var_90]
0x180091a38  test    rdi, rdi
0x180091a3b  jz      short loc_180091A5A
0x180091a3d  mov     rbx, [r14+20h]
0x180091a41  mov     edx, 10h; unsigned __int64
0x180091a46  mov     rcx, [r14+8]; this
0x180091a4a  call    ?Alloc@ArenaAllocator@Memory@@QEAAPEAD_K@Z; Memory::ArenaAllocator::Alloc(unsigned __int64)
0x180091a4f  mov     [rax], rdi
0x180091a52  mov     [rax+8], rbx
0x180091a56  mov     [r14+20h], rax
0x180091a5a  mov     rcx, [r14+10h]; this
0x180091a5e  call    ?GetProjectionWriter@ProjectionContext@Projection@@QEAAPEAVProjectionWriter@2@XZ; Projection::ProjectionContext::GetProjectionWriter(void)
0x180091a63  mov     rcx, [rax+88h]
0x180091a6a  mov     r8, [rcx+28h]
0x180091a6e  mov     r9, [r8]
0x180091a71  test    r9, r9
0x180091a74  jz      short loc_180091ADF
0x180091a76  mov     r11, [rbp+4Fh+var_90]
0x180091a7a  mov     rcx, r11
0x180091a7d  shr     rcx, 4
0x180091a81  btr     ecx, 1Fh
0x180091a85  mov     eax, ecx
0x180091a87  shr     eax, 0Fh
0x180091a8a  xor     eax, ecx
0x180091a8c  mov     ecx, eax
0x180091a8e  mov     r10, [r8+8]
0x180091a92  mov     edx, eax
0x180091a94  shr     rdx, 7
0x180091a98  xor     rdx, rcx
0x180091a9b  mov     ecx, [r8+1Ch]
0x180091a9f  dec     ecx
0x180091aa1  and     rdx, rcx
0x180091aa4  mov     ecx, [r9+rdx*4]
0x180091aa8  test    ecx, ecx
0x180091aaa  js      short loc_180091ADF
0x180091aac  movsxd  rax, ecx
0x180091aaf  lea     rdx, [rax+rax*2]
0x180091ab3  cmp     [r10+rdx*8+10h], r11
0x180091ab8  jz      short loc_180091AC1
0x180091aba  mov     ecx, [r10+rdx*8+8]
0x180091abf  jmp     short loc_180091AA8
0x180091ac1  lfence
0x180091ac4  movsxd  rax, ecx
0x180091ac7  lea     rcx, [rax+rax*2]
0x180091acb  mov     rax, [r8+8]
0x180091acf  mov     rcx, [rax+rcx*8]
0x180091ad3  mov     rdi, [rcx]
0x180091ad6  test    rdi, rdi
0x180091ad9  jnz     loc_180091BE1
0x180091adf  mov     rax, [r14+10h]
0x180091ae3  mov     rbx, [rax+60h]
0x180091ae7  add     rbx, 1EF0h
0x180091aee  cmp     byte ptr [rbx+10h], 0
0x180091af2  jz      loc_180091CC6
0x180091af8  mov     [rbp+4Fh+var_70], rbx
0x180091afc  mov     rax, [rbp+4Fh+arg_10]
0x180091b00  mov     [rbp+4Fh+var_78], rax
0x180091b04  mov     rax, [rbx]
0x180091b07  xor     edx, edx
0x180091b09  mov     rcx, rbx
0x180091b0c  mov     rax, [rax+20h]
0x180091b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b15  nop
0x180091b16  mov     [rbp+4Fh+var_88], 0
0x180091b1e  mov     r8, [rbp+57h]
0x180091b22  mov     rdx, r15
0x180091b25  lea     rcx, [rbp+4Fh+var_58]
0x180091b29  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x180091b2e  nop
0x180091b2f  mov     rsi, [r15+370h]
0x180091b36  mov     [rbp+4Fh+var_68], rsi
0x180091b3a  mov     dil, [rsi+139h]
0x180091b41  mov     [rbp+4Fh+var_60], dil
0x180091b45  mov     byte ptr [rsi+139h], 1
0x180091b4c  mov     rax, [r12]
0x180091b50  lea     r8, [rbp+4Fh+var_88]
0x180091b54  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180091b5b  mov     rcx, r12
0x180091b5e  mov     rax, [rax]
0x180091b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b66  mov     ebx, eax
0x180091b68  mov     rcx, [r15+370h]; this
0x180091b6f  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x180091b74  nop
0x180091b75  mov     [rsi+139h], dil
0x180091b7c  lea     rcx, [rbp+4Fh+var_58]
0x180091b80  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x180091b85  test    ebx, ebx
0x180091b87  jns     loc_180091C2F
0x180091b8d  mov     rax, [rbp+4Fh+arg_20]
0x180091b91  mov     [rsp+40h], rax; struct Projection::ConstructorArguments *
0x180091b96  mov     eax, [rbp+4Fh+arg_18]
0x180091b99  mov     [rsp+0E0h+var_A8], eax; int
0x180091b9d  mov     [rsp+0E0h+var_B0], 0; bool
0x180091ba2  mov     [rsp+0E0h+var_B8], 0; bool
0x180091ba7  mov     [rsp+0E0h+var_C0], 1; bool
0x180091bac  mov     r9, r12; struct IInspectable *
0x180091baf  mov     r8, [rbp+4Fh+var_90]; struct IUnknown *
0x180091bb3  lea     rdx, [rbp+4Fh+var_78]; struct AutoHSTRING *
0x180091bb7  mov     rcx, r14; this
0x180091bba  call    ?ReadVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIInspectable@@_N33HPEAUConstructorArguments@2@@Z; Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,IInspectable *,bool,bool,bool,int,Projection::ConstructorArguments *)
0x180091bbf  mov     rbx, rax
0x180091bc2  mov     rdx, [rbp+4Fh+var_78]
0x180091bc6  test    rdx, rdx
0x180091bc9  jz      short loc_180091BDC
0x180091bcb  mov     rcx, [rbp+4Fh+var_70]
0x180091bcf  mov     r8, [rcx]
0x180091bd2  mov     rax, [r8+20h]
0x180091bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091bdb  nop
0x180091bdc  mov     rax, rbx
0x180091bdf  jmp     short loc_180091C1C
0x180091be1  mov     rdx, r12; struct IUnknown *
0x180091be4  mov     rcx, [r14+10h]; this
0x180091be8  call    ?TypeInstanceCreated@ProjectionContext@Projection@@QEAAJPEAUIUnknown@@@Z; Projection::ProjectionContext::TypeInstanceCreated(IUnknown *)
0x180091bed  mov     rax, [r14+10h]
0x180091bf1  mov     rbx, [rax+60h]
0x180091bf5  add     rbx, 1EF0h
0x180091bfc  cmp     byte ptr [rbx+10h], 0
0x180091c00  jz      loc_180091C93
0x180091c06  mov     rcx, [rbx]
0x180091c09  mov     rax, [rcx+20h]
0x180091c0d  mov     rdx, [rbp+4Fh+arg_10]
0x180091c11  mov     rcx, rbx
0x180091c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091c19  mov     rax, rdi
0x180091c1c  add     rsp, 0B0h
0x180091c23  pop     r15
0x180091c25  pop     r14
0x180091c27  pop     r12
0x180091c29  pop     rdi
0x180091c2a  pop     rsi
0x180091c2b  pop     rbx
0x180091c2c  pop     rbp
0x180091c2d  retn
0x180091c2f  mov     r9, [rbp+4Fh+var_88]
0x180091c33  test    r9, r9
0x180091c36  jz      short loc_180091C50
0x180091c38  mov     r8, [r14+8]
0x180091c3c  mov     rdx, r9
0x180091c3f  mov     rcx, [r14+20h]
0x180091c43  call    ?Prepend@?$ImmutableList@PEAUHSTRING__@@@regex@@QEAAPEAV12@PEAUHSTRING__@@PEAVArenaAllocator@Memory@@@Z; regex::ImmutableList<HSTRING__ *>::Prepend(HSTRING__ *,Memory::ArenaAllocator *)
0x180091c48  mov     [r14+20h], rax
0x180091c4c  mov     r9, [rbp+4Fh+var_88]; struct Windows::Foundation::IPropertyValue *
0x180091c50  mov     eax, [rbp+4Fh+arg_18]
0x180091c53  mov     dword ptr [rsp+0E0h+var_B0], eax; int
0x180091c57  mov     [rsp+0E0h+var_B8], 0; bool
0x180091c5c  mov     [rsp+0E0h+var_C0], 1; bool
0x180091c61  mov     r8, [rbp+4Fh+var_90]; struct IUnknown *
0x180091c65  lea     rdx, [rbp+4Fh+var_78]; struct AutoHSTRING *
0x180091c69  mov     rcx, r14; this
0x180091c6c  call    ?ReadPropertyValueVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIPropertyValue@Foundation@Windows@@_N3H@Z; Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,Windows::Foundation::IPropertyValue *,bool,bool,int)
0x180091c71  mov     rbx, rax
0x180091c74  mov     rdx, [rbp+4Fh+var_78]
0x180091c78  test    rdx, rdx
0x180091c7b  jz      short loc_180091C8E
0x180091c7d  mov     rcx, [rbp+4Fh+var_70]
0x180091c81  mov     r8, [rcx]
0x180091c84  mov     rax, [r8+20h]
0x180091c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091c8d  nop
0x180091c8e  jmp     loc_180091BDC
0x180091c93  mov     rax, [rbx]
0x180091c96  mov     rcx, rbx
0x180091c99  mov     rax, [rax+8]
0x180091c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ca2  mov     rcx, rax; lpLibFileName
0x180091ca5  xor     edx, edx; hFile
0x180091ca7  mov     r8d, 800h; dwFlags
0x180091cad  call    cs:__imp_LoadLibraryExW
0x180091cb4  nop     dword ptr [rax+rax+00h]
0x180091cb9  mov     [rbx+8], rax
0x180091cbd  mov     byte ptr [rbx+10h], 1
0x180091cc1  jmp     loc_180091C06
0x180091cc6  mov     rax, [rbx]
0x180091cc9  mov     rcx, rbx
0x180091ccc  mov     rax, [rax+8]
0x180091cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091cd5  mov     rcx, rax; lpLibFileName
0x180091cd8  xor     edx, edx; hFile
0x180091cda  mov     r8d, 800h; dwFlags
0x180091ce0  call    cs:__imp_LoadLibraryExW
0x180091ce7  nop     dword ptr [rax+rax+00h]
0x180091cec  mov     [rbx+8], rax
0x180091cf0  mov     byte ptr [rbx+10h], 1
0x180091cf4  jmp     loc_180091AF8
0x180091cf9  mov     edx, esi; int
0x180091cfb  mov     rcx, r15; struct Js::ScriptContext *
0x180091cfe  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
```
