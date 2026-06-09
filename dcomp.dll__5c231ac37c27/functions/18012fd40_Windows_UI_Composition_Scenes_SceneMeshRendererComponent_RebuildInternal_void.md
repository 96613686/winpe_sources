# Windows::UI::Composition::Scenes::SceneMeshRendererComponent::RebuildInternal(void)

- ea: `0x18012fd40`
- end: `0x18012ffd9`
- name: `?RebuildInternal@SceneMeshRendererComponent@Scenes@Composition@UI@Windows@@UEAAJXZ`
- size: `665`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Scenes::SceneMeshRendererComponent *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800093f4`
- `0x18001358c`
- `0x1800311c8`
- `0x18005143c`
- `0x1800e10e8`
- `0x18012fd40`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012fe59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012fe59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012fe7a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012fe98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012febf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012fee2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012ff08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012fe7a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012fe98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012febf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012fee2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012ff08`

## string_xrefs

- `0x18012fd9a`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtscenemeshrenderercomponent.cpp`
- `0x18012ff7d`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtscenemeshrenderercomponent.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Scenes::SceneMeshRendererComponent::RebuildInternal(
        Windows::UI::Composition::Scenes::SceneMeshRendererComponent *this)
{
  char *v1; // r14
  __int64 v2; // rax
  __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int i; // eax
  __int64 v8; // rsi
  int (__fastcall *v9)(__int64, __int64 *); // rdi
  int v10; // edi
  const WCHAR *StringRawBuffer; // rdi
  int v12; // esi
  _QWORD *v13; // rdx
  __int64 v14; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  __int64 v17; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+38h] [rbp-20h] BYREF
  HSTRING string[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  char v21; // [rsp+A0h] [rbp+48h] BYREF
  UINT32 length; // [rsp+A8h] [rbp+50h] BYREF
  int v23; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+60h] BYREF

  v1 = (char *)this + 72;
  v2 = *((_QWORD *)this + 9);
  v24 = 0;
  v17 = 0;
  if ( v2 != *((_QWORD *)this + 10) )
    *((_QWORD *)this + 10) = v2;
  v4 = *((_QWORD *)this + 8);
  v21 = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v24);
  v5 = Windows::UI::Composition::Scenes::SceneMeshMaterialAttributeMap::First(v4, &v24);
  v6 = v5;
  if ( v5 >= 0 )
  {
    for ( i = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 56LL))(v24, &v21);
          i >= 0;
          i = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 64LL))(v24, &v21) )
    {
      if ( !v21 )
        break;
      v8 = v24;
      v9 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v17);
      if ( v9(v8, &v17) < 0 )
        break;
      string[0] = 0;
      v23 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 48LL))(v17, string);
      if ( v10 < 0 )
      {
        v14 = 93;
        goto LABEL_23;
      }
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 56LL))(v17, &v23);
      if ( v10 < 0 )
      {
        v14 = 94;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtscenemeshrenderercomponent.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
        v6 = v10;
        goto LABEL_25;
      }
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], &length);
      CompareStringOrdinal(StringRawBuffer, length, L"EmissiveInput", 13, 0);
      v12 = CompareStringOrdinal(StringRawBuffer, length, L"NormalInput", 11, 0) == 2;
      if ( CompareStringOrdinal(StringRawBuffer, length, L"OcclusionInput", 14, 0) == 2 )
        v12 = 2;
      if ( CompareStringOrdinal(StringRawBuffer, length, L"BaseColorInput", 14, 0) == 2 )
        v12 = 3;
      if ( CompareStringOrdinal(StringRawBuffer, length, L"MetallicRoughnessInput", 22, 0) == 2 )
        v12 = 4;
      v13 = (_QWORD *)*((_QWORD *)this + 10);
      LODWORD(v18) = v12;
      HIDWORD(v18) = v23 == 4;
      if ( v13 == *((_QWORD **)this + 11) )
      {
        std::vector<DirectComposition::CCompositionTextureBinding *>::_Emplace_reallocate<DirectComposition::CCompositionTextureBinding *>(
          v1,
          v13,
          &v18);
      }
      else
      {
        *v13 = v18;
        *((_QWORD *)v1 + 1) += 8LL;
      }
    }
    Windows::UI::Composition::ProxyObject::SetBufferProperty(
      (__int64)this - 200,
      2,
      *(const void **)v1,
      (*((_QWORD *)v1 + 1) - *(_QWORD *)v1) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_BYTE *)this + 16) &= ~1u;
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtscenemeshrenderercomponent.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  }
LABEL_25:
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v24);
  return v6;
}

```

## disassembly

```asm
0x18012fd40  push    rbp
0x18012fd42  push    rbx
0x18012fd43  push    rsi
0x18012fd44  push    rdi
0x18012fd45  push    r12
0x18012fd47  push    r13
0x18012fd49  push    r14
0x18012fd4b  push    r15
0x18012fd4d  mov     rbp, rsp
0x18012fd50  sub     rsp, 58h
0x18012fd54  xor     r12d, r12d
0x18012fd57  lea     r14, [rcx+48h]
0x18012fd5b  mov     rax, [r14]
0x18012fd5e  mov     r15, rcx
0x18012fd61  mov     [rbp+arg_18], r12
0x18012fd65  mov     [rbp+var_28], r12
0x18012fd69  cmp     rax, [r14+8]
0x18012fd6d  jz      short loc_18012FD73
0x18012fd6f  mov     [r14+8], rax
0x18012fd73  mov     rbx, [rcx+40h]
0x18012fd77  lea     rcx, [rbp+arg_18]
0x18012fd7b  mov     [rbp+arg_0], r12b
0x18012fd7f  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18012fd84  lea     rdx, [rbp+arg_18]
0x18012fd88  mov     rcx, rbx
0x18012fd8b  call    ?First@SceneMeshMaterialAttributeMap@Scenes@Composition@UI@Windows@@QEAAJPEAPEAU?$IIterator@PEAU?$IKeyValuePair@PEAUHSTRING__@@W4SceneAttributeSemantic@Scenes@Composition@UI@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@5@@Z; Windows::UI::Composition::Scenes::SceneMeshMaterialAttributeMap::First(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::UI::Composition::Scenes::SceneAttributeSemantic> *> * *)
0x18012fd90  mov     ebx, eax
0x18012fd92  test    eax, eax
0x18012fd94  jns     short loc_18012FDB3
0x18012fd96  mov     rcx, [rbp+40h]; this
0x18012fd9a  lea     r8, aOnecoreuapWind_146; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18012fda1  mov     r9d, eax; char *
0x18012fda4  mov     edx, 52h ; 'R'; void *
0x18012fda9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fdae  jmp     loc_18012FFB4
0x18012fdb3  mov     rcx, [rbp+arg_18]
0x18012fdb7  lea     rdx, [rbp+arg_0]
0x18012fdbb  mov     rax, [rcx]
0x18012fdbe  mov     rax, [rax+38h]
0x18012fdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fdc7  mov     ebx, 2
0x18012fdcc  test    eax, eax
0x18012fdce  js      loc_18012FF90
0x18012fdd4  cmp     [rbp+arg_0], r12b
0x18012fdd8  jz      loc_18012FF90
0x18012fdde  mov     rsi, [rbp+arg_18]
0x18012fde2  lea     rcx, [rbp+var_28]
0x18012fde6  mov     rax, [rsi]
0x18012fde9  mov     rdi, [rax+30h]
0x18012fded  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18012fdf2  lea     rdx, [rbp+var_28]
0x18012fdf6  mov     rcx, rsi
0x18012fdf9  mov     rax, rdi
0x18012fdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fe01  test    eax, eax
0x18012fe03  js      loc_18012FF90
0x18012fe09  mov     rcx, [rbp+var_28]
0x18012fe0d  lea     rdx, [rbp+string]
0x18012fe11  mov     [rbp+string], r12
0x18012fe15  mov     [rbp+arg_10], r12d
0x18012fe19  mov     rax, [rcx]
0x18012fe1c  mov     rax, [rax+30h]
0x18012fe20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fe25  mov     edi, eax
0x18012fe27  test    eax, eax
0x18012fe29  js      loc_18012FF74
0x18012fe2f  mov     rcx, [rbp+var_28]
0x18012fe33  lea     rdx, [rbp+arg_10]
0x18012fe37  mov     rax, [rcx]
0x18012fe3a  mov     rax, [rax+38h]
0x18012fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fe43  mov     edi, eax
0x18012fe45  test    eax, eax
0x18012fe47  js      loc_18012FF6D
0x18012fe4d  mov     rcx, [rbp+string]; string
0x18012fe51  lea     rdx, [rbp+length]; length
0x18012fe55  mov     [rbp+length], r12d
0x18012fe59  call    cs:__imp_WindowsGetStringRawBuffer
0x18012fe5f  mov     edx, [rbp+length]; cchCount1
0x18012fe62  lea     r8, aEmissiveinput; "EmissiveInput"
0x18012fe69  mov     rcx, rax; lpString1
0x18012fe6c  mov     [rsp+58h+bIgnoreCase], r12d; bIgnoreCase
0x18012fe71  mov     r9d, 0Dh; cchCount2
0x18012fe77  mov     rdi, rax
0x18012fe7a  call    cs:__imp_CompareStringOrdinal
0x18012fe80  mov     edx, [rbp+length]; cchCount1
0x18012fe83  lea     r8, aNormalinput; "NormalInput"
0x18012fe8a  mov     r9d, 0Bh; cchCount2
0x18012fe90  mov     [rsp+58h+bIgnoreCase], r12d; bIgnoreCase
0x18012fe95  mov     rcx, rdi; lpString1
0x18012fe98  call    cs:__imp_CompareStringOrdinal
0x18012fe9e  mov     edx, [rbp+length]; cchCount1
0x18012fea1  lea     r8, aOcclusioninput; "OcclusionInput"
0x18012fea8  cmp     eax, ebx
0x18012feaa  mov     [rsp+58h+bIgnoreCase], r12d; bIgnoreCase
0x18012feaf  mov     esi, r12d
0x18012feb2  mov     r9d, 0Eh; cchCount2
0x18012feb8  mov     rcx, rdi; lpString1
0x18012febb  setz    sil
0x18012febf  call    cs:__imp_CompareStringOrdinal
0x18012fec5  mov     edx, [rbp+length]; cchCount1
0x18012fec8  lea     r8, aBasecolorinput; "BaseColorInput"
0x18012fecf  cmp     eax, ebx
0x18012fed1  mov     [rsp+58h+bIgnoreCase], r12d; bIgnoreCase
0x18012fed6  mov     r9d, 0Eh; cchCount2
0x18012fedc  mov     rcx, rdi; lpString1
0x18012fedf  cmovz   esi, ebx
0x18012fee2  call    cs:__imp_CompareStringOrdinal
0x18012fee8  mov     edx, [rbp+length]; cchCount1
0x18012feeb  lea     r8, aMetallicroughn; "MetallicRoughnessInput"
0x18012fef2  cmp     eax, ebx
0x18012fef4  mov     [rsp+58h+bIgnoreCase], r12d; bIgnoreCase
0x18012fef9  mov     eax, 3
0x18012fefe  mov     rcx, rdi; lpString1
0x18012ff01  cmovz   esi, eax
0x18012ff04  lea     r9d, [rax+13h]; cchCount2
0x18012ff08  call    cs:__imp_CompareStringOrdinal
0x18012ff0e  mov     edx, [rbp+arg_10]
0x18012ff11  mov     ecx, 4
0x18012ff16  cmp     eax, ebx
0x18012ff18  cmovz   esi, ecx
0x18012ff1b  mov     ecx, r12d
0x18012ff1e  sub     edx, 3
0x18012ff21  jz      short loc_18012FF2A
0x18012ff23  cmp     edx, 1
0x18012ff26  jnz     short loc_18012FF2A
0x18012ff28  mov     ecx, edx
0x18012ff2a  mov     rdx, [r15+50h]
0x18012ff2e  mov     dword ptr [rbp+var_20], esi
0x18012ff31  mov     dword ptr [rbp+var_20+4], ecx
0x18012ff34  cmp     rdx, [r15+58h]
0x18012ff38  jz      short loc_18012FF48
0x18012ff3a  mov     rax, [rbp+var_20]
0x18012ff3e  mov     [rdx], rax
0x18012ff41  add     qword ptr [r14+8], 8
0x18012ff46  jmp     short loc_18012FF54
0x18012ff48  lea     r8, [rbp+var_20]
0x18012ff4c  mov     rcx, r14
0x18012ff4f  call    ??$_Emplace_reallocate@PEAVCCompositionTextureBinding@DirectComposition@@@?$vector@PEAVCCompositionTextureBinding@DirectComposition@@V?$allocator@PEAVCCompositionTextureBinding@DirectComposition@@@std@@@std@@AEAAPEAPEAVCCompositionTextureBinding@DirectComposition@@QEAPEAV23@$$QEAPEAV23@@Z; std::vector<DirectComposition::CCompositionTextureBinding *>::_Emplace_reallocate<DirectComposition::CCompositionTextureBinding *>(DirectComposition::CCompositionTextureBinding * * const,DirectComposition::CCompositionTextureBinding * &&)
0x18012ff54  mov     rcx, [rbp+arg_18]
0x18012ff58  lea     rdx, [rbp+arg_0]
0x18012ff5c  mov     rax, [rcx]
0x18012ff5f  mov     rax, [rax+40h]
0x18012ff63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ff68  jmp     loc_18012FDCC
0x18012ff6d  mov     edx, 5Eh ; '^'
0x18012ff72  jmp     short loc_18012FF79
0x18012ff74  mov     edx, 5Dh ; ']'; void *
0x18012ff79  mov     rcx, [rbp+40h]; this
0x18012ff7d  lea     r8, aOnecoreuapWind_146; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18012ff84  mov     r9d, edi; char *
0x18012ff87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ff8c  mov     ebx, edi
0x18012ff8e  jmp     short loc_18012FFB4
0x18012ff90  mov     r9, [r14+8]
0x18012ff94  lea     rcx, [r15-0C8h]
0x18012ff9b  sub     r9, [r14]
0x18012ff9e  mov     edx, ebx
0x18012ffa0  mov     r8, [r14]
0x18012ffa3  and     r9, 0FFFFFFFFFFFFFFF8h
0x18012ffa7  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x18012ffac  and     byte ptr [r15+10h], 0FEh
0x18012ffb1  mov     ebx, r12d
0x18012ffb4  lea     rcx, [rbp+var_28]
0x18012ffb8  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18012ffbd  lea     rcx, [rbp+arg_18]
0x18012ffc1  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18012ffc6  mov     eax, ebx
0x18012ffc8  add     rsp, 58h
0x18012ffcc  pop     r15
0x18012ffce  pop     r14
0x18012ffd0  pop     r13
0x18012ffd2  pop     r12
0x18012ffd4  pop     rdi
0x18012ffd5  pop     rsi
0x18012ffd6  pop     rbx
0x18012ffd7  pop     rbp
0x18012ffd8  retn
```
