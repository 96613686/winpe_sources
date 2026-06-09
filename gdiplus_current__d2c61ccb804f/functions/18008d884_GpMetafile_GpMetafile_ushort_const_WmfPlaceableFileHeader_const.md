# GpMetafile::GpMetafile(ushort const *,WmfPlaceableFileHeader const *)

- ea: `0x18008d884`
- end: `0x18008dae7`
- name: `??0GpMetafile@@QEAA@PEBGPEBUWmfPlaceableFileHeader@@@Z`
- size: `611`
- prototype: `GpMetafile *__fastcall(GpMetafile *__hidden this, const unsigned __int16 *, const struct WmfPlaceableFileHeader *)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18008dc64`
- `0x18008df80`
- `0x18008e230`
- `0x18008e710`
- `0x18010d960`

## callees

- `0x180085228`
- `0x180085d9c`
- `0x18008941c`
- `0x1800894b8`
- `0x18008cb48`
- `0x18008d884`
- `0x18008daf0`
- `0x18008db20`
- `0x18008ddb0`
- `0x180172010`

## import_xrefs

- `GDI32!GetEnhMetaFileW` at `0x18008d9de`
- `GDI32!GetEnhMetaFileW` at `0x18008d9de`
- `GDI32!GetMetaFileW` at `0x18008d97d`
- `GDI32!GetMetaFileW` at `0x18008d97d`
- `GDI32!GetMetaFileBitsEx` at `0x18008da96`
- `GDI32!GetMetaFileBitsEx` at `0x18008da96`
- `GDI32!DeleteMetaFile` at `0x18008dad6`
- `GDI32!DeleteMetaFile` at `0x18008dad6`

## pseudocode

```c
GpMetafile *__fastcall GpMetafile::GpMetafile(GpMetafile *this, GpRuntime *a2, const struct WmfPlaceableFileHeader *a3)
{
  const unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // rdx
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r10
  const wchar_t *v12; // r8
  unsigned __int16 *i; // r9
  wchar_t v14; // dx
  wchar_t v15; // cx
  int v16; // edi
  int v17; // ebp
  HMETAFILE MetaFileW; // rax
  HMETAFILE v19; // rsi
  struct IStream *StreamOnFile; // rax
  struct IStream *v21; // rsi
  HENHMETAFILE EnhMetaFileW; // rax
  const wchar_t *j; // r8
  wchar_t v25; // dx
  wchar_t v26; // cx

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
    v11 = v10;
    if ( !a3 )
    {
      if ( !v10 )
        goto LABEL_39;
      v12 = L".WMF";
      for ( i = v10; ; ++i )
      {
        v14 = *i;
        v15 = *v12;
        if ( !*i )
          break;
        if ( !v15 )
          goto LABEL_28;
        if ( (unsigned __int16)(v14 - 97) <= 0x19u )
          v14 -= 32;
        if ( (unsigned __int16)(v15 - 97) <= 0x19u )
          v15 -= 32;
        if ( v14 < v15 || v14 > v15 )
          goto LABEL_28;
        ++v12;
      }
      if ( !v15 )
        goto LABEL_15;
LABEL_28:
      for ( j = L".APM"; ; ++j )
      {
        v25 = *v11;
        v26 = *j;
        if ( !*v11 )
          break;
        if ( !v26 )
          goto LABEL_39;
        if ( (unsigned __int16)(v25 - 97) <= 0x19u )
          v25 -= 32;
        if ( (unsigned __int16)(v26 - 97) <= 0x19u )
          v26 -= 32;
        if ( v25 < v26 || v25 > v26 )
          goto LABEL_39;
        ++v11;
      }
      if ( v26 )
      {
LABEL_39:
        v16 = 0;
LABEL_16:
        v17 = 0;
        if ( !v16 )
          goto LABEL_23;
        while ( 1 )
        {
          MetaFileW = GetMetaFileW((LPCWSTR)a2);
          v19 = MetaFileW;
          if ( MetaFileW )
          {
            if ( GetMetaFileBitsEx(MetaFileW, 0, 0) )
            {
              GpMetafile::InitWmf(this, v19, a3, 1, 0);
              goto LABEL_20;
            }
            DeleteMetaFile(v19);
          }
          StreamOnFile = CreateStreamOnFile((const unsigned __int16 *)a2);
          v21 = StreamOnFile;
          if ( !StreamOnFile )
            goto LABEL_22;
          GpMetafile::InitStream(this, StreamOnFile, 1);
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_20:
          if ( (unsigned int)GpMetafile::IsValid(this) || *((_DWORD *)this + 44) == 1 )
            return this;
LABEL_22:
          if ( v17 )
            return this;
LABEL_23:
          EnhMetaFileW = GetEnhMetaFileW((LPCWSTR)a2);
          if ( EnhMetaFileW )
          {
            GpMetafile::InitEmf(this, EnhMetaFileW, 1);
            if ( (unsigned int)GpMetafile::IsValid(this) || *((_DWORD *)this + 44) == 1 )
              return this;
          }
          if ( v16 )
            return this;
          v17 = 1;
          v16 = 1;
        }
      }
    }
LABEL_15:
    v16 = 1;
    goto LABEL_16;
  }
  return this;
}

```

## disassembly

```asm
0x18008d884  push    rbx
0x18008d886  push    rbp
0x18008d887  push    rsi
0x18008d888  push    rdi
0x18008d889  push    r12
0x18008d88b  push    r13
0x18008d88d  push    r14
0x18008d88f  push    r15
0x18008d891  sub     rsp, 38h
0x18008d895  lea     rax, ??_7GpMetafile@@6B@; const GpMetafile::`vftable'
0x18008d89c  xor     r12d, r12d
0x18008d89f  mov     [rcx+10h], r12
0x18008d8a3  mov     r15, r8
0x18008d8a6  mov     dword ptr [rcx+1Ch], 0FFFFFFFFh
0x18008d8ad  mov     r14, rdx
0x18008d8b0  mov     dword ptr [rcx+18h], 2
0x18008d8b7  mov     rbx, rcx
0x18008d8ba  mov     dword ptr [rcx+8], 676D4931h
0x18008d8c1  mov     [rcx], rax
0x18008d8c4  call    ?InitDefaults@GpMetafile@@IEAAXXZ; GpMetafile::InitDefaults(void)
0x18008d8c9  mov     rcx, r14; this
0x18008d8cc  call    ?UnicodeStringDuplicate@GpRuntime@@YAPEAGPEBG@Z; GpRuntime::UnicodeStringDuplicate(ushort const *)
0x18008d8d1  mov     [rbx+0C0h], rax
0x18008d8d8  test    rax, rax
0x18008d8db  jz      loc_18008DA1C
0x18008d8e1  mov     rcx, r14; this
0x18008d8e4  call    ?UnicodeStringReverseSearch@GpRuntime@@YAPEAGPEBGG@Z; GpRuntime::UnicodeStringReverseSearch(ushort const *,ushort)
0x18008d8e9  lea     r13d, [r12+1]
0x18008d8ee  mov     r10, rax
0x18008d8f1  test    r15, r15
0x18008d8f4  jnz     short loc_18008D970
0x18008d8f6  test    rax, rax
0x18008d8f9  jz      loc_18008DA86
0x18008d8ff  lea     r8, aWmf_0; ".WMF"
0x18008d906  mov     r9, rax
0x18008d909  mov     r11w, 61h ; 'a'
0x18008d90e  mov     di, 19h
0x18008d912  mov     si, 20h ; ' '
0x18008d916  movzx   edx, word ptr [r9]
0x18008d91a  movzx   ecx, word ptr [r8]
0x18008d91e  test    dx, dx
0x18008d921  jz      short loc_18008D967
0x18008d923  test    cx, cx
0x18008d926  jz      loc_18008DA31
0x18008d92c  movzx   eax, dx
0x18008d92f  sub     ax, r11w
0x18008d933  cmp     ax, di
0x18008d936  jbe     short loc_18008D962
0x18008d938  movzx   eax, cx
0x18008d93b  sub     ax, r11w
0x18008d93f  cmp     ax, di
0x18008d942  jbe     short loc_18008D95D
0x18008d944  cmp     dx, cx
0x18008d947  jb      loc_18008DA31
0x18008d94d  ja      loc_18008DA31
0x18008d953  add     r9, 2
0x18008d957  add     r8, 2
0x18008d95b  jmp     short loc_18008D916
0x18008d95d  sub     cx, si
0x18008d960  jmp     short loc_18008D944
0x18008d962  sub     dx, si
0x18008d965  jmp     short loc_18008D938
0x18008d967  test    cx, cx
0x18008d96a  jnz     loc_18008DA31
0x18008d970  mov     edi, r13d
0x18008d973  mov     ebp, r12d
0x18008d976  test    edi, edi
0x18008d978  jz      short loc_18008D9DB
0x18008d97a  mov     rcx, r14; lpName
0x18008d97d  call    cs:__imp_GetMetaFileW
0x18008d984  nop     dword ptr [rax+rax+00h]
0x18008d989  mov     rsi, rax
0x18008d98c  test    rax, rax
0x18008d98f  jnz     loc_18008DA8E
0x18008d995  mov     rcx, r14; unsigned __int16 *
0x18008d998  call    ?CreateStreamOnFile@@YAPEAUIStream@@PEBGI@Z; CreateStreamOnFile(ushort const *,uint)
0x18008d99d  mov     rsi, rax
0x18008d9a0  test    rax, rax
0x18008d9a3  jz      short loc_18008D9D7
0x18008d9a5  mov     r8d, r13d; int
0x18008d9a8  mov     rdx, rax; struct IStream *
0x18008d9ab  mov     rcx, rbx; this
0x18008d9ae  call    ?InitStream@GpMetafile@@IEAAXPEAUIStream@@H@Z; GpMetafile::InitStream(IStream *,int)
0x18008d9b3  mov     rcx, [rsi]
0x18008d9b6  mov     rax, [rcx+10h]
0x18008d9ba  mov     rcx, rsi
0x18008d9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d9c2  mov     rcx, rbx; this
0x18008d9c5  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18008d9ca  test    eax, eax
0x18008d9cc  jnz     short loc_18008DA1C
0x18008d9ce  cmp     [rbx+0B0h], r13d
0x18008d9d5  jz      short loc_18008DA1C
0x18008d9d7  test    ebp, ebp
0x18008d9d9  jnz     short loc_18008DA1C
0x18008d9db  mov     rcx, r14; lpName
0x18008d9de  call    cs:__imp_GetEnhMetaFileW
0x18008d9e5  nop     dword ptr [rax+rax+00h]
0x18008d9ea  test    rax, rax
0x18008d9ed  jnz     short loc_18008D9FE
0x18008d9ef  test    edi, edi
0x18008d9f1  jnz     short loc_18008DA1C
0x18008d9f3  mov     ebp, r13d
0x18008d9f6  mov     edi, r13d
0x18008d9f9  jmp     loc_18008D97A
0x18008d9fe  mov     r8d, r13d; int
0x18008da01  mov     rdx, rax; HENHMETAFILE
0x18008da04  mov     rcx, rbx; this
0x18008da07  call    ?InitEmf@GpMetafile@@IEAAXPEAUHENHMETAFILE__@@H@Z; GpMetafile::InitEmf(HENHMETAFILE__ *,int)
0x18008da0c  mov     rcx, rbx; this
0x18008da0f  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18008da14  test    eax, eax
0x18008da16  jz      loc_18008DAC1
0x18008da1c  mov     rax, rbx
0x18008da1f  add     rsp, 38h
0x18008da23  pop     r15
0x18008da25  pop     r14
0x18008da27  pop     r13
0x18008da29  pop     r12
0x18008da2b  pop     rdi
0x18008da2c  pop     rsi
0x18008da2d  pop     rbp
0x18008da2e  pop     rbx
0x18008da2f  retn
0x18008da31  lea     r8, aApm; ".APM"
0x18008da38  movzx   edx, word ptr [r10]
0x18008da3c  movzx   ecx, word ptr [r8]
0x18008da40  test    dx, dx
0x18008da43  jz      short loc_18008DA7D
0x18008da45  test    cx, cx
0x18008da48  jz      short loc_18008DA86
0x18008da4a  movzx   eax, dx
0x18008da4d  sub     ax, r11w
0x18008da51  cmp     ax, di
0x18008da54  jbe     short loc_18008DA78
0x18008da56  movzx   eax, cx
0x18008da59  sub     ax, r11w
0x18008da5d  cmp     ax, di
0x18008da60  jbe     short loc_18008DA73
0x18008da62  cmp     dx, cx
0x18008da65  jb      short loc_18008DA86
0x18008da67  ja      short loc_18008DA86
0x18008da69  add     r10, 2
0x18008da6d  add     r8, 2
0x18008da71  jmp     short loc_18008DA38
0x18008da73  sub     cx, si
0x18008da76  jmp     short loc_18008DA62
0x18008da78  sub     dx, si
0x18008da7b  jmp     short loc_18008DA56
0x18008da7d  test    cx, cx
0x18008da80  jz      loc_18008D970
0x18008da86  mov     edi, r12d
0x18008da89  jmp     loc_18008D973
0x18008da8e  xor     r8d, r8d; lpData
0x18008da91  xor     edx, edx; cbBuffer
0x18008da93  mov     rcx, rsi; hMF
0x18008da96  call    cs:__imp_GetMetaFileBitsEx
0x18008da9d  nop     dword ptr [rax+rax+00h]
0x18008daa2  test    eax, eax
0x18008daa4  jz      short loc_18008DAD3
0x18008daa6  mov     r9d, r13d; int
0x18008daa9  mov     [rsp+78h+var_58], r12d; int
0x18008daae  mov     r8, r15; struct WmfPlaceableFileHeader *
0x18008dab1  mov     rdx, rsi; HMETAFILE
0x18008dab4  mov     rcx, rbx; this
0x18008dab7  call    ?InitWmf@GpMetafile@@IEAAXPEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z; GpMetafile::InitWmf(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)
0x18008dabc  jmp     loc_18008D9C2
0x18008dac1  cmp     [rbx+0B0h], r13d
0x18008dac8  jnz     loc_18008D9EF
0x18008dace  jmp     loc_18008DA1C
0x18008dad3  mov     rcx, rsi; hmf
0x18008dad6  call    cs:__imp_DeleteMetaFile
0x18008dadd  nop     dword ptr [rax+rax+00h]
0x18008dae2  jmp     loc_18008D995
```
