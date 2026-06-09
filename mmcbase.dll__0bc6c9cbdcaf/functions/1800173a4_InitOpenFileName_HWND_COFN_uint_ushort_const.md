# InitOpenFileName(HWND__ *,COFN *,uint,ushort const *)

- ea: `0x1800173a4`
- end: `0x1800174a0`
- name: `?InitOpenFileName@@YAXPEAUHWND__@@PEAUCOFN@@IPEBG@Z`
- size: `252`
- prototype: `void(HWND, struct COFN *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180017b5c`

## callees

- `0x180003c40`
- `0x1800041f0`
- `0x1800064b4`
- `0x1800173a4`
- `0x18001b522`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017427`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017427`
- `USER32!CharNextW` at `0x18001745b`
- `USER32!CharNextW` at `0x18001745b`

## string_xrefs

- `0x1800173bb`: `InitOpenFileName`

## pseudocode

```c
void __fastcall InitOpenFileName(HWND a1, WCHAR *a2, __int64 a3, const unsigned __int16 *a4)
{
  unsigned __int16 *v7; // rbp
  LPWSTR v8; // rbx
  int StringW; // eax
  WCHAR v10; // si
  WCHAR *v11; // rdi
  int v12; // eax
  _DWORD v13[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v14; // [rsp+28h] [rbp-40h]

  ++mmcerror::SC::s_CallDepth;
  v14 = 0;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v13, L"InitOpenFileName");
  memset_0(a2, 0, 0x98u);
  *((_QWORD *)a2 + 1) = a1;
  v7 = a2 + 76;
  v8 = a2 + 336;
  *(_DWORD *)a2 = 152;
  *((_QWORD *)a2 + 3) = a2 + 336;
  *((_QWORD *)a2 + 6) = a2 + 76;
  *((_DWORD *)a2 + 14) = 260;
  *((_DWORD *)a2 + 24) = 12;
  StringW = LoadStringW(mmcerror::SC::s_hInst, 0x3F0u, a2 + 336, 200);
  if ( StringW )
  {
    v10 = a2[StringW + 335];
    v11 = &a2[StringW + 336];
    while ( v8 < v11 )
    {
      if ( *v8 == v10 )
        *v8++ = 0;
      else
        v8 = CharNextW(v8);
    }
  }
  v13[0] = 3;
  v12 = StringCchCopyW(v7, 0x104u, a4);
  --mmcerror::SC::s_CallDepth;
  v13[1] = v12;
  mmcerror::SC::Trace_((mmcerror::SC *)v13);
}

```

## disassembly

```asm
0x1800173a4  push    rbx
0x1800173a6  push    rbp
0x1800173a7  push    rsi
0x1800173a8  push    rdi
0x1800173a9  push    r14
0x1800173ab  sub     rsp, 40h
0x1800173af  inc     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x1800173b5  mov     rdi, rdx
0x1800173b8  mov     rbx, rcx
0x1800173bb  lea     rdx, aInitopenfilena; "InitOpenFileName"
0x1800173c2  xorps   xmm0, xmm0
0x1800173c5  lea     rcx, [rsp+68h+var_48]; this
0x1800173ca  movdqu  [rsp+68h+var_40], xmm0
0x1800173d0  mov     r14, r9
0x1800173d3  call    ?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800173d8  mov     esi, 98h
0x1800173dd  xor     edx, edx; Val
0x1800173df  mov     r8d, esi; Size
0x1800173e2  mov     rcx, rdi; void *
0x1800173e5  call    memset_0
0x1800173ea  mov     [rdi+8], rbx
0x1800173ee  lea     rbp, [rdi+98h]
0x1800173f5  lea     rbx, [rdi+2A0h]
0x1800173fc  mov     [rdi], esi
0x1800173fe  mov     [rdi+18h], rbx
0x180017402  lea     r9d, [rsi+30h]; cchBufferMax
0x180017406  mov     [rdi+30h], rbp
0x18001740a  mov     r8, rbx; lpBuffer
0x18001740d  mov     dword ptr [rdi+38h], 104h
0x180017414  mov     edx, 3F0h; uID
0x180017419  mov     dword ptr [rdi+60h], 0Ch
0x180017420  mov     rcx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hInstance
0x180017427  call    cs:__imp_LoadStringW
0x18001742d  test    eax, eax
0x18001742f  jz      short loc_180017469
0x180017431  cdqe
0x180017433  movzx   esi, word ptr [rdi+rax*2+29Eh]
0x18001743b  lea     rdi, [rdi+rax*2]
0x18001743f  add     rdi, 2A0h
0x180017446  jmp     short loc_180017464
0x180017448  cmp     [rbx], si
0x18001744b  jnz     short loc_180017458
0x18001744d  xor     eax, eax
0x18001744f  mov     [rbx], ax
0x180017452  add     rbx, 2
0x180017456  jmp     short loc_180017464
0x180017458  mov     rcx, rbx; lpsz
0x18001745b  call    cs:__imp_CharNextW
0x180017461  mov     rbx, rax
0x180017464  cmp     rbx, rdi
0x180017467  jb      short loc_180017448
0x180017469  mov     r8, r14; unsigned __int16 *
0x18001746c  mov     [rsp+68h+var_48], 3
0x180017474  mov     edx, 104h; unsigned __int64
0x180017479  mov     rcx, rbp; unsigned __int16 *
0x18001747c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017481  dec     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180017487  lea     rcx, [rsp+68h+var_48]; this
0x18001748c  mov     [rsp+68h+var_44], eax
0x180017490  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x180017495  add     rsp, 40h
0x180017499  pop     r14
0x18001749b  pop     rdi
0x18001749c  pop     rsi
0x18001749d  pop     rbp
0x18001749e  pop     rbx
0x18001749f  retn
```
