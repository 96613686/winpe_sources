# CPackage::OLE2SoundRecReadFromStream(IStream *)

- ea: `0x180009dd8`
- end: `0x180009f9a`
- name: `?OLE2SoundRecReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009370`

## callees

- `0x1800079ac`
- `0x1800095e0`
- `0x180009dd8`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000abf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009e65`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009e65`

## pseudocode

```c
__int64 __fastcall CPackage::OLE2SoundRecReadFromStream(CPackage *this, struct IStream *a2)
{
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v5; // rax
  const WCHAR *v6; // rcx
  _DWORD *v7; // rax
  _WORD *v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rcx
  _WORD *v13; // rax
  _WORD *v14; // rdx
  __int64 v15; // rax
  _WORD *v16; // rcx
  _WORD *v17; // rax
  _WORD *v18; // rcx
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  int v21; // [rsp+38h] [rbp-50h]
  _OWORD v22[2]; // [rsp+40h] [rbp-48h] BYREF
  int v23; // [rsp+60h] [rbp-28h]

  v22[0] = *(_OWORD *)L"OLE2EmbedStrm.wav";
  v20 = 0;
  v22[1] = *(_OWORD *)L"dStrm.wav";
  v23 = *(_DWORD *)L"v";
  *((_DWORD *)this + 26) = 3;
  lpVtbl = a2->lpVtbl;
  v21 = 0;
  if ( ((int (__fastcall *)(struct IStream *, __int64 *, __int64, _QWORD))lpVtbl->Read)(a2, &v20, 12, 0) >= 0 && v21 )
  {
    v5 = *((_QWORD *)this + 14);
    if ( v5 )
    {
      v6 = *(const WCHAR **)(v5 + 592);
      if ( v6 )
      {
        DeleteFileW(v6);
        operator delete(*(void **)(*((_QWORD *)this + 14) + 592LL));
      }
      operator delete(*((void **)this + 14));
    }
    v7 = operator new(0x270u);
    *((_QWORD *)this + 14) = v7;
    if ( v7 )
    {
      *v7 = 64;
      v8 = v22;
      v9 = 2147483646;
      v10 = 260;
      v11 = 260;
      *(_DWORD *)(*((_QWORD *)this + 14) + 68LL) = v21;
      v12 = 2147483646;
      *(_DWORD *)(*((_QWORD *)this + 14) + 64LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 14) + 616LL) = 0;
      v13 = (_WORD *)(*((_QWORD *)this + 14) + 72LL);
      do
      {
        if ( !v12 )
          break;
        if ( !*v8 )
          break;
        *v13++ = *v8++;
        --v12;
        --v11;
      }
      while ( v11 );
      v14 = v13 - 1;
      if ( v11 )
        v14 = v13;
      *v14 = 0;
      if ( (int)CPackage::CreateTempFileName(this) >= 0
        && (int)CopyStreamToFile(
                  a2,
                  *(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL),
                  *(_DWORD *)(*((_QWORD *)this + 14) + 68LL)) >= 0 )
      {
        v15 = *((_QWORD *)this + 14);
        v16 = *(_WORD **)(v15 + 592);
        v17 = (_WORD *)(v15 + 72);
        do
        {
          if ( !v9 )
            break;
          if ( !*v16 )
            break;
          *v17++ = *v16++;
          --v9;
          --v10;
        }
        while ( v10 );
        v18 = v17 - 1;
        if ( v10 )
          v18 = v17;
        *v18 = 0;
        MarkFileUnsafe(*(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL));
      }
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180009dd8  mov     rax, rsp
0x180009ddb  mov     [rax+18h], rbx
0x180009ddf  mov     [rax+20h], rbp
0x180009de3  push    rsi
0x180009de4  push    rdi
0x180009de5  push    r14
0x180009de7  sub     rsp, 70h
0x180009deb  movups  xmm0, xmmword ptr cs:aOle2embedstrmW; "OLE2EmbedStrm.wav"
0x180009df2  xor     ebp, ebp
0x180009df4  mov     r14, rdx
0x180009df7  movups  xmm1, xmmword ptr cs:aOle2embedstrmW+10h; "dStrm.wav"
0x180009dfe  mov     rbx, rcx
0x180009e01  xor     r9d, r9d
0x180009e04  movups  xmmword ptr [rax-48h], xmm0
0x180009e08  lea     r8d, [rbp+0Ch]
0x180009e0c  mov     [rsp+88h+var_58], rbp
0x180009e11  movups  xmmword ptr [rax-38h], xmm1
0x180009e15  mov     eax, dword ptr cs:aOle2embedstrmW+20h; "v"
0x180009e1b  mov     [rsp+88h+var_28], eax
0x180009e1f  mov     dword ptr [rcx+68h], 3
0x180009e26  mov     rcx, r14
0x180009e29  mov     rax, [rdx]
0x180009e2c  lea     rdx, [rsp+88h+var_58]
0x180009e31  mov     [rsp+88h+var_50], ebp
0x180009e35  mov     rax, [rax+18h]
0x180009e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e3e  test    eax, eax
0x180009e40  js      loc_180009F80
0x180009e46  cmp     [rsp+88h+var_50], ebp
0x180009e4a  jbe     loc_180009F80
0x180009e50  mov     rax, [rbx+70h]
0x180009e54  test    rax, rax
0x180009e57  jz      short loc_180009E84
0x180009e59  mov     rcx, [rax+250h]; lpFileName
0x180009e60  test    rcx, rcx
0x180009e63  jz      short loc_180009E7B
0x180009e65  call    cs:__imp_DeleteFileW
0x180009e6b  mov     rcx, [rbx+70h]
0x180009e6f  mov     rcx, [rcx+250h]; lpMem
0x180009e76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e7b  mov     rcx, [rbx+70h]; lpMem
0x180009e7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e84  mov     ecx, 270h; unsigned __int64
0x180009e89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e8e  mov     [rbx+70h], rax
0x180009e92  test    rax, rax
0x180009e95  jz      loc_180009F80
0x180009e9b  mov     dword ptr [rax], 40h ; '@'
0x180009ea1  lea     rdx, [rsp+88h+var_48]
0x180009ea6  mov     rcx, [rbx+70h]
0x180009eaa  mov     esi, 7FFFFFFEh
0x180009eaf  mov     eax, [rsp+88h+var_50]
0x180009eb3  mov     edi, 104h
0x180009eb8  mov     r8d, edi
0x180009ebb  mov     [rcx+44h], eax
0x180009ebe  mov     ecx, esi
0x180009ec0  mov     rax, [rbx+70h]
0x180009ec4  mov     [rax+40h], ebp
0x180009ec7  mov     rax, [rbx+70h]
0x180009ecb  mov     [rax+268h], ebp
0x180009ed1  mov     rax, [rbx+70h]
0x180009ed5  add     rax, 48h ; 'H'
0x180009ed9  test    rcx, rcx
0x180009edc  jz      short loc_180009EFD
0x180009ede  movzx   r9d, word ptr [rdx]
0x180009ee2  test    r9w, r9w
0x180009ee6  jz      short loc_180009EFD
0x180009ee8  mov     [rax], r9w
0x180009eec  add     rdx, 2
0x180009ef0  add     rax, 2
0x180009ef4  dec     rcx
0x180009ef7  sub     r8, 1
0x180009efb  jnz     short loc_180009ED9
0x180009efd  test    r8, r8
0x180009f00  lea     rdx, [rax-2]
0x180009f04  mov     rcx, rbx; this
0x180009f07  cmovnz  rdx, rax
0x180009f0b  mov     [rdx], bp
0x180009f0e  call    ?CreateTempFileName@CPackage@@IEAAJXZ; CPackage::CreateTempFileName(void)
0x180009f13  test    eax, eax
0x180009f15  js      short loc_180009F80
0x180009f17  mov     rdx, [rbx+70h]
0x180009f1b  mov     rcx, r14; struct IStream *
0x180009f1e  mov     r8d, [rdx+44h]; unsigned int
0x180009f22  mov     rdx, [rdx+250h]; unsigned __int16 *
0x180009f29  call    ?CopyStreamToFile@@YAJPEAUIStream@@PEBGK@Z; CopyStreamToFile(IStream *,ushort const *,ulong)
0x180009f2e  test    eax, eax
0x180009f30  js      short loc_180009F80
0x180009f32  mov     rax, [rbx+70h]
0x180009f36  mov     rcx, [rax+250h]
0x180009f3d  add     rax, 48h ; 'H'
0x180009f41  test    rsi, rsi
0x180009f44  jz      short loc_180009F62
0x180009f46  movzx   edx, word ptr [rcx]
0x180009f49  test    dx, dx
0x180009f4c  jz      short loc_180009F62
0x180009f4e  mov     [rax], dx
0x180009f51  add     rcx, 2
0x180009f55  add     rax, 2
0x180009f59  dec     rsi
0x180009f5c  sub     rdi, 1
0x180009f60  jnz     short loc_180009F41
0x180009f62  test    rdi, rdi
0x180009f65  lea     rcx, [rax-2]
0x180009f69  cmovnz  rcx, rax
0x180009f6d  mov     [rcx], bp
0x180009f70  mov     rcx, [rbx+70h]
0x180009f74  mov     rcx, [rcx+250h]; unsigned __int16 *
0x180009f7b  call    ?MarkFileUnsafe@@YAJPEBG@Z; MarkFileUnsafe(ushort const *)
0x180009f80  lea     r11, [rsp+88h+var_18]
0x180009f85  mov     eax, 80004005h
0x180009f8a  mov     rbx, [r11+30h]
0x180009f8e  mov     rbp, [r11+38h]
0x180009f92  mov     rsp, r11
0x180009f95  pop     r14
0x180009f97  pop     rdi
0x180009f98  pop     rsi
0x180009f99  retn
```
