# GpMetafile::GpMetafile(ushort const *,WmfPlaceableFileHeader const *)

- ea: `0x18000adac`
- end: `0x18000b049`
- name: `??0GpMetafile@@QEAA@PEBGPEBUWmfPlaceableFileHeader@@@Z`
- size: `669`
- prototype: `GpMetafile *__fastcall(GpMetafile *__hidden this, const unsigned __int16 *, const struct WmfPlaceableFileHeader *)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18000acc8`
- `0x1800c0b00`
- `0x1800c0d10`
- `0x1800cff00`
- `0x1800f2240`

## callees

- `0x18000a380`
- `0x18000a3a8`
- `0x18000ab54`
- `0x18000adac`
- `0x18000b20c`
- `0x18000b78c`
- `0x18000b83c`
- `0x1800a6850`
- `0x1800a68e4`
- `0x180175010`

## import_xrefs

- `GDI32!GetEnhMetaFileW` at `0x18000aea5`
- `GDI32!GetEnhMetaFileW` at `0x18000aea5`
- `GDI32!GetMetaFileW` at `0x18000ae36`
- `GDI32!GetMetaFileW` at `0x18000ae36`
- `GDI32!GetMetaFileBitsEx` at `0x18000aece`
- `GDI32!GetMetaFileBitsEx` at `0x18000aece`
- `GDI32!DeleteMetaFile` at `0x18000b014`
- `GDI32!DeleteMetaFile` at `0x18000b014`

## pseudocode

```c
GpMetafile *__fastcall GpMetafile::GpMetafile(GpMetafile *this, GpRuntime *a2, const struct WmfPlaceableFileHeader *a3)
{
  const unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // rdx
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // rax
  int v11; // edi
  int v12; // esi
  HMETAFILE MetaFileW; // rax
  HMETAFILE v14; // rbp
  struct IStream *StreamOnFile; // rax
  struct IStream *v16; // r14
  HENHMETAFILE EnhMetaFileW; // rax
  const wchar_t *i; // r8
  wchar_t v20; // dx
  wchar_t v21; // cx
  const wchar_t *j; // r8
  wchar_t v23; // dx
  wchar_t v24; // cx

  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 7) = -1;
  *((_DWORD *)this + 6) = 2;
  *((_DWORD *)this + 2) = 1735215409;
  *(_QWORD *)this = &GpMetafile::`vftable';
  GpMetafile::InitDefaults(this);
  v7 = GpRuntime::UnicodeStringDuplicate(a2, v6);
  *((_QWORD *)this + 24) = v7;
  if ( v7 )
  {
    v10 = GpRuntime::UnicodeStringReverseSearch(a2, v8, v9);
    if ( !a3 )
    {
      if ( !v10 )
        goto LABEL_39;
      for ( i = L".WMF"; ; ++i )
      {
        v20 = *(const wchar_t *)((char *)i + (char *)v10 - (char *)L".WMF");
        v21 = *i;
        if ( !v20 )
          break;
        if ( !v21 )
          goto LABEL_28;
        if ( (unsigned __int16)(v20 - 97) <= 0x19u )
          v20 -= 32;
        if ( (unsigned __int16)(v21 - 97) <= 0x19u )
          v21 -= 32;
        if ( v20 < v21 || v20 > v21 )
          goto LABEL_28;
      }
      if ( !v21 )
        goto LABEL_3;
LABEL_28:
      for ( j = L".APM"; ; ++j )
      {
        v23 = *(const wchar_t *)((char *)j + (char *)v10 - (char *)L".APM");
        v24 = *j;
        if ( !v23 )
          break;
        if ( !v24 )
          goto LABEL_39;
        if ( (unsigned __int16)(v23 - 97) <= 0x19u )
          v23 -= 32;
        if ( (unsigned __int16)(v24 - 97) <= 0x19u )
          v24 -= 32;
        if ( v23 < v24 || v23 > v24 )
          goto LABEL_39;
      }
      if ( v24 )
      {
LABEL_39:
        v11 = 0;
LABEL_4:
        v12 = 0;
        if ( !v11 )
          goto LABEL_10;
        while ( 1 )
        {
          MetaFileW = GetMetaFileW((LPCWSTR)a2);
          v14 = MetaFileW;
          if ( MetaFileW )
          {
            if ( GetMetaFileBitsEx(MetaFileW, 0, 0) )
            {
              GpMetafile::InitWmf(this, v14, a3, 1, 0);
              if ( (unsigned int)GpMetafile::IsValid(this) )
                return this;
              goto LABEL_8;
            }
            DeleteMetaFile(v14);
          }
          StreamOnFile = CreateStreamOnFile((const unsigned __int16 *)a2);
          v16 = StreamOnFile;
          if ( !StreamOnFile )
            goto LABEL_9;
          GpMetafile::InitStream(this, StreamOnFile, 1);
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
          if ( (unsigned int)GpMetafile::IsValid(this) )
            return this;
LABEL_8:
          if ( *((_DWORD *)this + 44) == 1 )
            return this;
LABEL_9:
          if ( v12 )
            return this;
LABEL_10:
          v12 = 1;
          EnhMetaFileW = GetEnhMetaFileW((LPCWSTR)a2);
          if ( EnhMetaFileW )
          {
            GpMetafile::InitEmf(this, EnhMetaFileW, 1);
            if ( (unsigned int)GpMetafile::IsValid(this) || *((_DWORD *)this + 44) == 1 )
              return this;
          }
          if ( v11 )
            return this;
          v11 = 1;
        }
      }
    }
LABEL_3:
    v11 = 1;
    goto LABEL_4;
  }
  return this;
}

```

## disassembly

```asm
0x18000adac  mov     [rsp+arg_8], rbx
0x18000adb1  mov     [rsp+arg_10], rbp
0x18000adb6  mov     [rsp+arg_18], rsi
0x18000adbb  push    rdi
0x18000adbc  push    r12
0x18000adbe  push    r13
0x18000adc0  push    r14
0x18000adc2  push    r15
0x18000adc4  sub     rsp, 30h
0x18000adc8  lea     rax, ??_7GpMetafile@@6B@; const GpMetafile::`vftable'
0x18000adcf  xor     r13d, r13d
0x18000add2  mov     [rcx+10h], r13
0x18000add6  mov     r12, r8
0x18000add9  or      dword ptr [rcx+1Ch], 0FFFFFFFFh
0x18000addd  mov     r15, rdx
0x18000ade0  mov     dword ptr [rcx+18h], 2
0x18000ade7  mov     rbx, rcx
0x18000adea  mov     dword ptr [rcx+8], 676D4931h
0x18000adf1  mov     [rcx], rax
0x18000adf4  call    ?InitDefaults@GpMetafile@@IEAAXXZ; GpMetafile::InitDefaults(void)
0x18000adf9  mov     rcx, r15; this
0x18000adfc  call    ?UnicodeStringDuplicate@GpRuntime@@YAPEAGPEBG@Z; GpRuntime::UnicodeStringDuplicate(ushort const *)
0x18000ae01  mov     [rbx+0C0h], rax
0x18000ae08  test    rax, rax
0x18000ae0b  jz      loc_18000AF04
0x18000ae11  mov     rcx, r15; this
0x18000ae14  call    ?UnicodeStringReverseSearch@GpRuntime@@YAPEAGPEBGG@Z; GpRuntime::UnicodeStringReverseSearch(ushort const *,ushort)
0x18000ae19  lea     r14d, [r13+1]
0x18000ae1d  mov     r10, rax
0x18000ae20  test    r12, r12
0x18000ae23  jz      loc_18000AF25
0x18000ae29  mov     edi, r14d
0x18000ae2c  mov     esi, r13d
0x18000ae2f  test    edi, edi
0x18000ae31  jz      short loc_18000AE9F
0x18000ae33  mov     rcx, r15; lpName
0x18000ae36  call    cs:__imp_GetMetaFileW
0x18000ae3d  nop     dword ptr [rax+rax+00h]
0x18000ae42  mov     rbp, rax
0x18000ae45  test    rax, rax
0x18000ae48  jnz     short loc_18000AEC6
0x18000ae4a  mov     rcx, r15; unsigned __int16 *
0x18000ae4d  call    ?CreateStreamOnFile@@YAPEAUIStream@@PEBGI@Z; CreateStreamOnFile(ushort const *,uint)
0x18000ae52  mov     r14, rax
0x18000ae55  test    rax, rax
0x18000ae58  jz      short loc_18000AE95
0x18000ae5a  mov     r8d, 1; int
0x18000ae60  mov     rdx, rax; struct IStream *
0x18000ae63  mov     rcx, rbx; this
0x18000ae66  call    ?InitStream@GpMetafile@@IEAAXPEAUIStream@@H@Z; GpMetafile::InitStream(IStream *,int)
0x18000ae6b  mov     rcx, [r14]
0x18000ae6e  mov     rax, [rcx+10h]
0x18000ae72  mov     rcx, r14
0x18000ae75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7a  mov     rcx, rbx; this
0x18000ae7d  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18000ae82  test    eax, eax
0x18000ae84  jnz     short loc_18000AF04
0x18000ae86  lea     r14d, [rax+1]
0x18000ae8a  cmp     [rbx+0B0h], r14d
0x18000ae91  jnz     short loc_18000AE9B
0x18000ae93  jmp     short loc_18000AF04
0x18000ae95  mov     r14d, 1
0x18000ae9b  test    esi, esi
0x18000ae9d  jnz     short loc_18000AF04
0x18000ae9f  mov     rcx, r15; lpName
0x18000aea2  mov     esi, r14d
0x18000aea5  call    cs:__imp_GetEnhMetaFileW
0x18000aeac  nop     dword ptr [rax+rax+00h]
0x18000aeb1  test    rax, rax
0x18000aeb4  jnz     loc_18000AFE1
0x18000aeba  test    edi, edi
0x18000aebc  jnz     short loc_18000AF04
0x18000aebe  mov     edi, r14d
0x18000aec1  jmp     loc_18000AE33
0x18000aec6  xor     r8d, r8d; lpData
0x18000aec9  xor     edx, edx; cbBuffer
0x18000aecb  mov     rcx, rbp; hMF
0x18000aece  call    cs:__imp_GetMetaFileBitsEx
0x18000aed5  nop     dword ptr [rax+rax+00h]
0x18000aeda  test    eax, eax
0x18000aedc  jz      loc_18000B011
0x18000aee2  mov     r9d, r14d; int
0x18000aee5  mov     [rsp+58h+var_38], r13d; int
0x18000aeea  mov     r8, r12; struct WmfPlaceableFileHeader *
0x18000aeed  mov     rdx, rbp; HMETAFILE
0x18000aef0  mov     rcx, rbx; this
0x18000aef3  call    ?InitWmf@GpMetafile@@IEAAXPEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z; GpMetafile::InitWmf(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)
0x18000aef8  mov     rcx, rbx; this
0x18000aefb  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18000af00  test    eax, eax
0x18000af02  jz      short loc_18000AE8A
0x18000af04  mov     rbp, [rsp+58h+arg_10]
0x18000af09  mov     rax, rbx
0x18000af0c  mov     rbx, [rsp+58h+arg_8]
0x18000af11  mov     rsi, [rsp+58h+arg_18]
0x18000af16  add     rsp, 30h
0x18000af1a  pop     r15
0x18000af1c  pop     r14
0x18000af1e  pop     r13
0x18000af20  pop     r12
0x18000af22  pop     rdi
0x18000af23  retn
0x18000af25  test    r10, r10
0x18000af28  jz      loc_18000AFD9
0x18000af2e  lea     r8, aWmf_0; ".WMF"
0x18000af35  mov     r9, r10
0x18000af38  sub     r9, r8
0x18000af3b  mov     di, 61h ; 'a'
0x18000af3f  mov     si, 19h
0x18000af43  mov     r11d, 0FFE0h
0x18000af49  movzx   edx, word ptr [r9+r8]
0x18000af4e  movzx   ecx, word ptr [r8]
0x18000af52  test    dx, dx
0x18000af55  jz      short loc_18000AF87
0x18000af57  test    cx, cx
0x18000af5a  jz      short loc_18000AF90
0x18000af5c  movzx   eax, dx
0x18000af5f  sub     ax, di
0x18000af62  cmp     ax, si
0x18000af65  jbe     loc_18000B025
0x18000af6b  movzx   eax, cx
0x18000af6e  sub     ax, di
0x18000af71  cmp     ax, si
0x18000af74  jbe     loc_18000B02E
0x18000af7a  cmp     dx, cx
0x18000af7d  jb      short loc_18000AF90
0x18000af7f  ja      short loc_18000AF90
0x18000af81  add     r8, 2
0x18000af85  jmp     short loc_18000AF49
0x18000af87  test    cx, cx
0x18000af8a  jz      loc_18000AE29
0x18000af90  lea     r8, aApm; ".APM"
0x18000af97  sub     r10, r8
0x18000af9a  movzx   edx, word ptr [r10+r8]
0x18000af9f  movzx   ecx, word ptr [r8]
0x18000afa3  test    dx, dx
0x18000afa6  jz      short loc_18000AFD0
0x18000afa8  test    cx, cx
0x18000afab  jz      short loc_18000AFD9
0x18000afad  movzx   eax, dx
0x18000afb0  sub     ax, di
0x18000afb3  cmp     ax, si
0x18000afb6  jbe     short loc_18000B037
0x18000afb8  movzx   eax, cx
0x18000afbb  sub     ax, di
0x18000afbe  cmp     ax, si
0x18000afc1  jbe     short loc_18000B040
0x18000afc3  cmp     dx, cx
0x18000afc6  jb      short loc_18000AFD9
0x18000afc8  ja      short loc_18000AFD9
0x18000afca  add     r8, 2
0x18000afce  jmp     short loc_18000AF9A
0x18000afd0  test    cx, cx
0x18000afd3  jz      loc_18000AE29
0x18000afd9  mov     edi, r13d
0x18000afdc  jmp     loc_18000AE2C
0x18000afe1  mov     r8d, r14d; int
0x18000afe4  mov     rdx, rax; HENHMETAFILE
0x18000afe7  mov     rcx, rbx; this
0x18000afea  call    ?InitEmf@GpMetafile@@IEAAXPEAUHENHMETAFILE__@@H@Z; GpMetafile::InitEmf(HENHMETAFILE__ *,int)
0x18000afef  mov     rcx, rbx; this
0x18000aff2  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18000aff7  test    eax, eax
0x18000aff9  jnz     loc_18000AF04
0x18000afff  cmp     [rbx+0B0h], r14d
0x18000b006  jz      loc_18000AF04
0x18000b00c  jmp     loc_18000AEBA
0x18000b011  mov     rcx, rbp; hmf
0x18000b014  call    cs:__imp_DeleteMetaFile
0x18000b01b  nop     dword ptr [rax+rax+00h]
0x18000b020  jmp     loc_18000AE4A
0x18000b025  add     dx, r11w
0x18000b029  jmp     loc_18000AF6B
0x18000b02e  add     cx, r11w
0x18000b032  jmp     loc_18000AF7A
0x18000b037  add     dx, r11w
0x18000b03b  jmp     loc_18000AFB8
0x18000b040  add     cx, r11w
0x18000b044  jmp     loc_18000AFC3
```
