# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(ulong,IMFMediaType *,ulong,CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType_Flag)

- ea: `0x18000d2dc`
- end: `0x18000d679`
- name: `?MFTtoDMO_SetType@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJKPEAUIMFMediaType@@KW4MFTtoDMO_SetType_Flag@1@@Z`
- size: `925`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d2a0`
- `0x18000d2c0`

## callees

- `0x18000b334`
- `0x18000b4ec`
- `0x18000cab8`
- `0x18000d2dc`
- `0x18000e3a0`
- `0x18000f0d0`
- `0x1800114a5`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int a4,
        int a5)
{
  __int64 *v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rcx
  char IsTypeDMORGB; // r13
  __int64 v17; // rax
  __int64 v18; // r9
  int v19; // eax
  int v20; // ebx
  bool v21; // zf
  __int64 *v22; // rcx
  __int64 (__fastcall *v23)(__int64 *, GUID *, _QWORD *); // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64 *, GUID *, _QWORD *); // rax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  __int64 (__fastcall *v31)(__int64 *, GUID *, _QWORD *); // rax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  _QWORD v38[2]; // [rsp+30h] [rbp-41h] BYREF
  GUID v39; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v40; // [rsp+50h] [rbp-21h] BYREF
  unsigned int v41; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v42; // [rsp+58h] [rbp-19h]
  GUID Buf2; // [rsp+60h] [rbp-11h] BYREF

  v42 = a1;
  v38[0] = 0;
  Buf2 = GUID_NULL;
  if ( (a4 & 0xFFFFFFFE) != 0 )
    return 2147942487LL;
  v9 = (__int64 *)(a1 + 48);
  v41 = 0;
  v10 = *(_QWORD *)(a1 + 48);
  v40 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(v10 + 24))(a1 + 48, &v41, &v40);
  if ( v11 >= 0 )
  {
    v14 = v40;
    if ( !a5 )
      v14 = v41;
    if ( a2 >= v14 )
      return 3222091443LL;
    IsTypeDMORGB = CMFTtoDMOImpl<CMFTtoDMO>::IsTypeDMORGB(v12, a3);
    if ( !IsTypeDMORGB )
      CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(v15, a3);
    if ( !a3 )
    {
      v17 = *v9;
      v18 = a4 | 2;
      if ( a5 )
        v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(v17 + 72))(v9, a2, 0, v18);
      else
        v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(v17 + 64))(v9, a2, 0, v18);
      v20 = v19;
      goto LABEL_45;
    }
    (*(void (__fastcall **)(__int64 *, GUID *))(*a3 + 264))(a3, &Buf2);
    v21 = memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) != 0;
    v22 = a3;
    v23 = *(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD *))(*a3 + 288);
    if ( !v21 )
    {
      v39 = FORMAT_MFVideoFormat;
      v20 = v23(a3, &v39, v38);
      if ( v20 >= 0 )
      {
        v24 = *v9;
        v25 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v24 + 72))(v9, a2, v38[0], a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v24 + 64))(v9, a2, v38[0], a4);
        v20 = v25;
        v26 = *a3;
        v39 = FORMAT_MFVideoFormat;
        (*(void (__fastcall **)(__int64 *, GUID *, _QWORD))(v26 + 296))(a3, &v39, v38[0]);
        if ( v20 >= 0 )
          goto LABEL_41;
      }
      if ( v20 == -1072861834 )
        goto LABEL_45;
      v27 = *(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD *))(*a3 + 288);
      v39 = FORMAT_VideoInfo2;
      v20 = v27(a3, &v39, v38);
      if ( v20 >= 0 )
      {
        v28 = *v9;
        v29 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v28 + 72))(v9, a2, v38[0], a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v28 + 64))(v9, a2, v38[0], a4);
        v20 = v29;
        v30 = *a3;
        v39 = FORMAT_VideoInfo2;
        (*(void (__fastcall **)(__int64 *, GUID *, _QWORD))(v30 + 296))(a3, &v39, v38[0]);
        if ( v20 >= 0 )
          goto LABEL_41;
      }
      if ( v20 == -1072861834 )
        goto LABEL_45;
      v31 = *(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD *))(*a3 + 288);
      v39 = FORMAT_VideoInfo;
      v20 = v31(a3, &v39, v38);
      if ( v20 >= 0 )
      {
        v32 = *v9;
        v33 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v32 + 72))(v9, a2, v38[0], a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v32 + 64))(v9, a2, v38[0], a4);
        v20 = v33;
        v34 = *a3;
        v39 = FORMAT_VideoInfo;
        (*(void (__fastcall **)(__int64 *, GUID *, _QWORD))(v34 + 296))(a3, &v39, v38[0]);
        if ( v20 >= 0 )
          goto LABEL_41;
      }
      if ( v20 == -1072861834 )
      {
LABEL_45:
        if ( !IsTypeDMORGB )
          CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(v12, a3);
        if ( v20 == 1 )
          v20 = -1072875852;
        v13 = (unsigned int)v20;
        return CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(v12, v13);
      }
      v22 = a3;
      v23 = *(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD *))(*a3 + 288);
    }
    v39 = AM_MEDIA_TYPE_REPRESENTATION;
    v20 = v23(v22, &v39, v38);
    if ( v20 < 0 )
      goto LABEL_45;
    v35 = *v9;
    v36 = a5
        ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v35 + 72))(v9, a2, v38[0], a4)
        : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v35 + 64))(v9, a2, v38[0], a4);
    v20 = v36;
    v37 = *a3;
    v39 = AM_MEDIA_TYPE_REPRESENTATION;
    (*(void (__fastcall **)(__int64 *, GUID *, _QWORD))(v37 + 296))(a3, &v39, v38[0]);
    if ( v20 < 0 )
      goto LABEL_45;
LABEL_41:
    if ( (a4 & 1) == 0 )
    {
      if ( a5 )
        *(_BYTE *)(v42 + 41) = IsTypeDMORGB;
      else
        *(_BYTE *)(v42 + 40) = IsTypeDMORGB;
    }
    goto LABEL_45;
  }
  v13 = (unsigned int)v11;
  return CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(v12, v13);
}

```

## disassembly

```asm
0x18000d2dc  push    rbp
0x18000d2de  push    rbx
0x18000d2df  push    rsi
0x18000d2e0  push    rdi
0x18000d2e1  push    r12
0x18000d2e3  push    r13
0x18000d2e5  push    r14
0x18000d2e7  push    r15
0x18000d2e9  lea     rbp, [rsp-17h]
0x18000d2ee  sub     rsp, 88h
0x18000d2f5  mov     rax, cs:__security_cookie
0x18000d2fc  xor     rax, rsp
0x18000d2ff  mov     [rbp+4Fh+var_50], rax
0x18000d303  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d30a  xor     ebx, ebx
0x18000d30c  mov     [rbp+4Fh+var_68], rcx
0x18000d310  mov     [rbp+4Fh+var_90], rbx
0x18000d314  mov     r14d, r9d
0x18000d317  mov     rsi, r8
0x18000d31a  mov     r12d, edx
0x18000d31d  movdqu  [rbp+4Fh+Buf2], xmm0
0x18000d322  test    r9d, 0FFFFFFFEh
0x18000d329  jz      short loc_18000D335
0x18000d32b  mov     eax, 80070057h
0x18000d330  jmp     loc_18000D659
0x18000d335  lea     rdi, [rcx+30h]
0x18000d339  mov     [rbp+4Fh+var_6C], ebx
0x18000d33c  mov     rax, [rdi]
0x18000d33f  lea     r8, [rbp+4Fh+var_70]
0x18000d343  lea     rdx, [rbp+4Fh+var_6C]
0x18000d347  mov     [rbp+4Fh+var_70], ebx
0x18000d34a  mov     rcx, rdi
0x18000d34d  mov     rax, [rax+18h]
0x18000d351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d356  test    eax, eax
0x18000d358  jns     short loc_18000D361
0x18000d35a  mov     edx, eax
0x18000d35c  jmp     loc_18000D654
0x18000d361  mov     r15d, [rbp+4Fh+arg_20]
0x18000d365  test    r15d, r15d
0x18000d368  mov     eax, [rbp+4Fh+var_70]
0x18000d36b  cmovz   eax, [rbp+4Fh+var_6C]
0x18000d36f  cmp     r12d, eax
0x18000d372  jb      short loc_18000D37E
0x18000d374  mov     eax, 0C00D36B3h
0x18000d379  jmp     loc_18000D659
0x18000d37e  mov     rdx, rsi
0x18000d381  call    ?IsTypeDMORGB@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAA_NPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::IsTypeDMORGB(IMFMediaType *)
0x18000d386  mov     r13b, al
0x18000d389  test    al, al
0x18000d38b  jnz     short loc_18000D395
0x18000d38d  mov     rdx, rsi
0x18000d390  call    ?ConvertMFRGBFormatToDMORGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(IMFMediaType *)
0x18000d395  test    rsi, rsi
0x18000d398  jnz     short loc_18000D3C8
0x18000d39a  mov     rax, [rdi]
0x18000d39d  or      r14d, 2
0x18000d3a1  xor     r8d, r8d
0x18000d3a4  mov     r9d, r14d
0x18000d3a7  mov     edx, r12d
0x18000d3aa  mov     rcx, rdi
0x18000d3ad  test    r15d, r15d
0x18000d3b0  jnz     short loc_18000D3B8
0x18000d3b2  mov     rax, [rax+40h]
0x18000d3b6  jmp     short loc_18000D3BC
0x18000d3b8  mov     rax, [rax+48h]
0x18000d3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c1  mov     ebx, eax
0x18000d3c3  jmp     loc_18000D63A
0x18000d3c8  mov     rax, [rsi]
0x18000d3cb  lea     rdx, [rbp+4Fh+Buf2]
0x18000d3cf  mov     rcx, rsi
0x18000d3d2  mov     rax, [rax+108h]
0x18000d3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3de  mov     r8d, 10h; Size
0x18000d3e4  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x18000d3e8  lea     rcx, MEDIATYPE_Video; Buf1
0x18000d3ef  call    memcmp_0
0x18000d3f4  test    eax, eax
0x18000d3f6  lea     r8, [rbp+4Fh+var_90]
0x18000d3fa  mov     rax, [rsi]
0x18000d3fd  lea     rdx, [rbp+4Fh+var_80]
0x18000d401  setz    cl
0x18000d404  test    cl, cl
0x18000d406  mov     rcx, rsi
0x18000d409  mov     rax, [rax+120h]
0x18000d410  jz      loc_18000D5BA
0x18000d416  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000d41d  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d427  mov     ebx, eax
0x18000d429  test    eax, eax
0x18000d42b  js      short loc_18000D481
0x18000d42d  mov     rax, [rdi]
0x18000d430  mov     r9d, r14d
0x18000d433  mov     r8, [rbp+4Fh+var_90]
0x18000d437  mov     edx, r12d
0x18000d43a  mov     rcx, rdi
0x18000d43d  test    r15d, r15d
0x18000d440  jnz     short loc_18000D448
0x18000d442  mov     rax, [rax+40h]
0x18000d446  jmp     short loc_18000D44C
0x18000d448  mov     rax, [rax+48h]
0x18000d44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d451  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000d458  mov     r8, [rbp+4Fh+var_90]
0x18000d45c  lea     rdx, [rbp+4Fh+var_80]
0x18000d460  mov     ebx, eax
0x18000d462  mov     rcx, rsi
0x18000d465  mov     rax, [rsi]
0x18000d468  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d46d  mov     rax, [rax+128h]
0x18000d474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d479  test    ebx, ebx
0x18000d47b  jns     loc_18000D621
0x18000d481  cmp     ebx, 0C00D6D76h
0x18000d487  jz      loc_18000D63A
0x18000d48d  mov     rax, [rsi]
0x18000d490  lea     r8, [rbp+4Fh+var_90]
0x18000d494  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x18000d49b  lea     rdx, [rbp+4Fh+var_80]
0x18000d49f  mov     rcx, rsi
0x18000d4a2  mov     rax, [rax+120h]
0x18000d4a9  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4b3  mov     ebx, eax
0x18000d4b5  test    eax, eax
0x18000d4b7  js      short loc_18000D50D
0x18000d4b9  mov     rax, [rdi]
0x18000d4bc  mov     r9d, r14d
0x18000d4bf  mov     r8, [rbp+4Fh+var_90]
0x18000d4c3  mov     edx, r12d
0x18000d4c6  mov     rcx, rdi
0x18000d4c9  test    r15d, r15d
0x18000d4cc  jnz     short loc_18000D4D4
0x18000d4ce  mov     rax, [rax+40h]
0x18000d4d2  jmp     short loc_18000D4D8
0x18000d4d4  mov     rax, [rax+48h]
0x18000d4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4dd  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x18000d4e4  mov     r8, [rbp+4Fh+var_90]
0x18000d4e8  lea     rdx, [rbp+4Fh+var_80]
0x18000d4ec  mov     ebx, eax
0x18000d4ee  mov     rcx, rsi
0x18000d4f1  mov     rax, [rsi]
0x18000d4f4  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d4f9  mov     rax, [rax+128h]
0x18000d500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d505  test    ebx, ebx
0x18000d507  jns     loc_18000D621
0x18000d50d  cmp     ebx, 0C00D6D76h
0x18000d513  jz      loc_18000D63A
0x18000d519  mov     rax, [rsi]
0x18000d51c  lea     r8, [rbp+4Fh+var_90]
0x18000d520  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x18000d527  lea     rdx, [rbp+4Fh+var_80]
0x18000d52b  mov     rcx, rsi
0x18000d52e  mov     rax, [rax+120h]
0x18000d535  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53f  mov     ebx, eax
0x18000d541  test    eax, eax
0x18000d543  js      short loc_18000D599
0x18000d545  mov     rax, [rdi]
0x18000d548  mov     r9d, r14d
0x18000d54b  mov     r8, [rbp+4Fh+var_90]
0x18000d54f  mov     edx, r12d
0x18000d552  mov     rcx, rdi
0x18000d555  test    r15d, r15d
0x18000d558  jnz     short loc_18000D560
0x18000d55a  mov     rax, [rax+40h]
0x18000d55e  jmp     short loc_18000D564
0x18000d560  mov     rax, [rax+48h]
0x18000d564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d569  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x18000d570  mov     r8, [rbp+4Fh+var_90]
0x18000d574  lea     rdx, [rbp+4Fh+var_80]
0x18000d578  mov     ebx, eax
0x18000d57a  mov     rcx, rsi
0x18000d57d  mov     rax, [rsi]
0x18000d580  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d585  mov     rax, [rax+128h]
0x18000d58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d591  test    ebx, ebx
0x18000d593  jns     loc_18000D621
0x18000d599  cmp     ebx, 0C00D6D76h
0x18000d59f  jz      loc_18000D63A
0x18000d5a5  mov     rax, [rsi]
0x18000d5a8  lea     r8, [rbp+4Fh+var_90]
0x18000d5ac  lea     rdx, [rbp+4Fh+var_80]
0x18000d5b0  mov     rcx, rsi
0x18000d5b3  mov     rax, [rax+120h]
0x18000d5ba  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x18000d5c1  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5cb  mov     ebx, eax
0x18000d5cd  test    eax, eax
0x18000d5cf  js      short loc_18000D63A
0x18000d5d1  mov     rax, [rdi]
0x18000d5d4  mov     r9d, r14d
0x18000d5d7  mov     r8, [rbp+4Fh+var_90]
0x18000d5db  mov     edx, r12d
0x18000d5de  mov     rcx, rdi
0x18000d5e1  test    r15d, r15d
0x18000d5e4  jnz     short loc_18000D5EC
0x18000d5e6  mov     rax, [rax+40h]
0x18000d5ea  jmp     short loc_18000D5F0
0x18000d5ec  mov     rax, [rax+48h]
0x18000d5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f5  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x18000d5fc  mov     r8, [rbp+4Fh+var_90]
0x18000d600  lea     rdx, [rbp+4Fh+var_80]
0x18000d604  mov     ebx, eax
0x18000d606  mov     rcx, rsi
0x18000d609  mov     rax, [rsi]
0x18000d60c  movdqu  [rbp+4Fh+var_80], xmm0
0x18000d611  mov     rax, [rax+128h]
0x18000d618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61d  test    ebx, ebx
0x18000d61f  js      short loc_18000D63A
0x18000d621  test    r14b, 1
0x18000d625  jnz     short loc_18000D63A
0x18000d627  mov     rax, [rbp+4Fh+var_68]
0x18000d62b  test    r15d, r15d
0x18000d62e  jnz     short loc_18000D636
0x18000d630  mov     [rax+28h], r13b
0x18000d634  jmp     short loc_18000D63A
0x18000d636  mov     [rax+29h], r13b
0x18000d63a  test    r13b, r13b
0x18000d63d  jnz     short loc_18000D647
0x18000d63f  mov     rdx, rsi
0x18000d642  call    ?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)
0x18000d647  cmp     ebx, 1
0x18000d64a  mov     eax, 0C00D36B4h
0x18000d64f  cmovz   ebx, eax
0x18000d652  mov     edx, ebx
0x18000d654  call    ?DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z; CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)
0x18000d659  mov     rcx, [rbp+4Fh+var_50]
0x18000d65d  xor     rcx, rsp; StackCookie
0x18000d660  call    __security_check_cookie
0x18000d665  add     rsp, 88h
0x18000d66c  pop     r15
0x18000d66e  pop     r14
0x18000d670  pop     r13
0x18000d672  pop     r12
0x18000d674  pop     rdi
0x18000d675  pop     rsi
0x18000d676  pop     rbx
0x18000d677  pop     rbp
0x18000d678  retn
```
