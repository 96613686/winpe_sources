# CreateColorSpaceInternalW

- ea: `0x1800708c0`
- end: `0x180070b55`
- name: `CreateColorSpaceInternalW`
- size: `661`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180032130`
- `0x180079cf0`
- `0x180087c50`
- `0x180089514`
- `0x18008fc60`

## callees

- `0x18003472c`
- `0x1800352b4`
- `0x1800708c0`
- `0x18007ac50`
- `0x18007ba24`
- `0x1800a5010`

## import_xrefs

- `GDI32!ghICM` at `0x1800709e5`
- `GDI32!ghICM` at `0x180070a57`
- `GDI32!GdiSetLastError` at `0x180070b2b`
- `GDI32!GdiSetLastError` at `0x180070b2b`
- `win32u!NtGdiCreateColorSpace` at `0x180070a2d`
- `win32u!NtGdiCreateColorSpace` at `0x180070a2d`

## pseudocode

```c
__int64 __fastcall CreateColorSpaceInternalW(__int64 a1, int a2)
{
  __int64 v4; // rcx
  unsigned int v5; // eax
  int v6; // ecx
  __int64 v7; // rdx
  _OWORD *v8; // rcx
  _OWORD *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int64 v22; // rax
  __int64 v23; // rbx
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+5Ch] [rbp-A4h]
  _BYTE v28[12]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 v30[260]; // [rsp+A4h] [rbp-5Ch] BYREF
  int v31; // [rsp+2ACh] [rbp+1ACh]

  memset_0(v28, 0, 0x250u);
  if ( !a1 )
    goto LABEL_2;
  if ( *(_DWORD *)a1 != 1347637059 )
    goto LABEL_28;
  if ( *(_DWORD *)(a1 + 4) != 1024 )
    goto LABEL_28;
  if ( *(_DWORD *)(a1 + 8) != 588 )
    goto LABEL_28;
  v5 = *(_DWORD *)(a1 + 16);
  if ( v5 > 8 )
    goto LABEL_28;
  v6 = 278;
  if ( !_bittest(&v6, v5) )
    goto LABEL_28;
  v7 = 4;
  v8 = v28;
  v9 = (_OWORD *)a1;
  do
  {
    v10 = v9[1];
    *v8 = *v9;
    v11 = v9[2];
    v8[1] = v10;
    v12 = v9[3];
    v8[2] = v11;
    v13 = v9[4];
    v8[3] = v12;
    v14 = v9[5];
    v8[4] = v13;
    v15 = v9[6];
    v8[5] = v14;
    v16 = v9[7];
    v9 += 8;
    v8[6] = v15;
    v8[7] = v16;
    v8 += 8;
    --v7;
  }
  while ( v7 );
  v17 = v9[1];
  *v8 = *v9;
  v18 = v9[2];
  v8[1] = v17;
  v19 = v9[3];
  v8[2] = v18;
  v20 = *(_OWORD *)((char *)v9 + 60);
  v8[3] = v19;
  *(_OWORD *)((char *)v8 + 60) = v20;
  v31 = a2;
  if ( *(_DWORD *)(a1 + 12) && *(_DWORD *)(a1 + 12) != 1279872587 )
  {
    v24 = 260;
    if ( !ghICM && !(unsigned int)IcmInitialize() )
      return 0;
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, unsigned __int16 *, int *))fpGetStandardColorSpaceProfileW)(
                         0,
                         *(unsigned int *)(a1 + 12),
                         v30,
                         &v24) )
      return NtGdiCreateColorSpace(v28);
LABEL_28:
    v4 = 2017;
    goto LABEL_29;
  }
  v29 = 0;
  if ( !*(_WORD *)(a1 + 68) )
    return NtGdiCreateColorSpace(v28);
  if ( BuildIcmProfilePath((unsigned __int16 *)(a1 + 68), v30) )
  {
    if ( !ghICM && !(unsigned int)IcmInitialize() )
      return 0;
    v25[0] = 1;
    v25[1] = v30;
    v22 = -1;
    v27 = 0;
    do
      ++v22;
    while ( v30[v22] );
    v26 = 2 * v22 + 2;
    v23 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, _QWORD))fpWcsOpenColorProfileW)(v25, 0, 0);
    if ( v23 )
    {
      v24 = 0;
      if ( (unsigned int)((__int64 (__fastcall *)(__int64, int *))fpIsColorProfileValid)(v23, &v24) && v24 )
      {
        ((void (__fastcall *)(__int64))fpCloseColorProfile)(v23);
        return NtGdiCreateColorSpace(v28);
      }
      ((void (__fastcall *)(__int64))fpCloseColorProfile)(v23);
    }
    v4 = 2016;
    goto LABEL_29;
  }
LABEL_2:
  v4 = 87;
LABEL_29:
  GdiSetLastError(v4);
  return 0;
}

```

## disassembly

```asm
0x1800708c0  mov     [rsp-8+arg_10], rbx
0x1800708c5  push    rbp
0x1800708c6  push    rsi
0x1800708c7  push    rdi
0x1800708c8  lea     rbp, [rsp-1C0h]
0x1800708d0  sub     rsp, 2C0h
0x1800708d7  mov     rax, cs:__security_cookie
0x1800708de  xor     rax, rsp
0x1800708e1  mov     [rbp+1D0h+var_20], rax
0x1800708e8  mov     edi, edx
0x1800708ea  mov     rbx, rcx
0x1800708ed  xor     edx, edx; Val
0x1800708ef  lea     rcx, [rsp+2D0h+var_270]; void *
0x1800708f4  mov     r8d, 250h; Size
0x1800708fa  call    memset_0
0x1800708ff  xor     esi, esi
0x180070901  test    rbx, rbx
0x180070904  jnz     short loc_180070910
0x180070906  mov     ecx, 57h ; 'W'
0x18007090b  jmp     loc_180070B2B
0x180070910  cmp     dword ptr [rbx], 50534F43h
0x180070916  jnz     loc_180070B26
0x18007091c  cmp     dword ptr [rbx+4], 400h
0x180070923  jnz     loc_180070B26
0x180070929  cmp     dword ptr [rbx+8], 24Ch
0x180070930  jnz     loc_180070B26
0x180070936  mov     eax, [rbx+10h]
0x180070939  cmp     eax, 8
0x18007093c  ja      loc_180070B26
0x180070942  mov     ecx, 116h
0x180070947  bt      ecx, eax
0x18007094a  jnb     loc_180070B26
0x180070950  mov     edx, 4
0x180070955  lea     rcx, [rsp+2D0h+var_270]
0x18007095a  mov     rax, rbx
0x18007095d  lea     r8d, [rdx+7Ch]
0x180070961  movups  xmm0, xmmword ptr [rax]
0x180070964  movups  xmm1, xmmword ptr [rax+10h]
0x180070968  movups  xmmword ptr [rcx], xmm0
0x18007096b  movups  xmm0, xmmword ptr [rax+20h]
0x18007096f  movups  xmmword ptr [rcx+10h], xmm1
0x180070973  movups  xmm1, xmmword ptr [rax+30h]
0x180070977  movups  xmmword ptr [rcx+20h], xmm0
0x18007097b  movups  xmm0, xmmword ptr [rax+40h]
0x18007097f  movups  xmmword ptr [rcx+30h], xmm1
0x180070983  movups  xmm1, xmmword ptr [rax+50h]
0x180070987  movups  xmmword ptr [rcx+40h], xmm0
0x18007098b  movups  xmm0, xmmword ptr [rax+60h]
0x18007098f  movups  xmmword ptr [rcx+50h], xmm1
0x180070993  movups  xmm1, xmmword ptr [rax+70h]
0x180070997  add     rax, r8
0x18007099a  movups  xmmword ptr [rcx+60h], xmm0
0x18007099e  movups  xmmword ptr [rcx+70h], xmm1
0x1800709a2  add     rcx, r8
0x1800709a5  sub     rdx, 1
0x1800709a9  jnz     short loc_180070961
0x1800709ab  movups  xmm0, xmmword ptr [rax]
0x1800709ae  movups  xmm1, xmmword ptr [rax+10h]
0x1800709b2  movups  xmmword ptr [rcx], xmm0
0x1800709b5  movups  xmm0, xmmword ptr [rax+20h]
0x1800709b9  movups  xmmword ptr [rcx+10h], xmm1
0x1800709bd  movups  xmm1, xmmword ptr [rax+30h]
0x1800709c1  movups  xmmword ptr [rcx+20h], xmm0
0x1800709c5  movups  xmm0, xmmword ptr [rax+3Ch]
0x1800709c9  movups  xmmword ptr [rcx+30h], xmm1
0x1800709cd  movups  xmmword ptr [rcx+3Ch], xmm0
0x1800709d1  mov     [rbp+1D0h+var_24], edi
0x1800709d7  cmp     [rbx+0Ch], esi
0x1800709da  jz      short loc_180070A38
0x1800709dc  cmp     dword ptr [rbx+0Ch], 4C494E4Bh
0x1800709e3  jz      short loc_180070A38
0x1800709e5  mov     rax, cs:__imp_ghICM
0x1800709ec  mov     [rsp+2D0h+var_290], 104h
0x1800709f4  cmp     [rax], rsi
0x1800709f7  jnz     short loc_180070A06
0x1800709f9  call    ?IcmInitialize@@YAHXZ; IcmInitialize(void)
0x1800709fe  test    eax, eax
0x180070a00  jz      loc_180070B31
0x180070a06  mov     edx, [rbx+0Ch]
0x180070a09  lea     r9, [rsp+2D0h+var_290]
0x180070a0e  mov     rax, cs:fpGetStandardColorSpaceProfileW
0x180070a15  lea     r8, [rbp+1D0h+var_22C]
0x180070a19  xor     ecx, ecx
0x180070a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a20  test    eax, eax
0x180070a22  jz      loc_180070B26
0x180070a28  lea     rcx, [rsp+2D0h+var_270]
0x180070a2d  call    cs:__imp_NtGdiCreateColorSpace
0x180070a33  jmp     loc_180070B33
0x180070a38  lea     rcx, [rbx+44h]; unsigned __int16 *
0x180070a3c  mov     [rsp+2D0h+var_264], esi
0x180070a40  cmp     [rcx], si
0x180070a43  jz      short loc_180070A28
0x180070a45  lea     rdx, [rbp+1D0h+var_22C]; unsigned __int16 *
0x180070a49  call    BuildIcmProfilePath
0x180070a4e  test    rax, rax
0x180070a51  jz      loc_180070906
0x180070a57  mov     rax, cs:__imp_ghICM
0x180070a5e  cmp     [rax], rsi
0x180070a61  jnz     short loc_180070A70
0x180070a63  call    ?IcmInitialize@@YAHXZ; IcmInitialize(void)
0x180070a68  test    eax, eax
0x180070a6a  jz      loc_180070B31
0x180070a70  lea     rax, [rbp+1D0h+var_22C]
0x180070a74  mov     [rsp+2D0h+var_288], 1
0x180070a7d  mov     [rsp+2D0h+var_280], rax
0x180070a82  lea     rcx, [rbp+1D0h+var_22C]
0x180070a86  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070a8a  mov     [rsp+2D0h+var_274], esi
0x180070a8e  mov     r9d, 1
0x180070a94  inc     rax
0x180070a97  cmp     [rcx+rax*2], si
0x180070a9b  jnz     short loc_180070A94
0x180070a9d  lea     eax, ds:2[rax*2]
0x180070aa4  mov     [rsp+2D0h+var_2A0], r9d
0x180070aa9  mov     [rsp+2D0h+var_278], eax
0x180070aad  lea     rcx, [rsp+2D0h+var_288]
0x180070ab2  mov     rax, cs:fpWcsOpenColorProfileW
0x180070ab9  xor     r8d, r8d
0x180070abc  mov     [rsp+2D0h+var_2A8], 3
0x180070ac4  xor     edx, edx
0x180070ac6  mov     [rsp+2D0h+var_2B0], r9d
0x180070acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070ad0  mov     rbx, rax
0x180070ad3  test    rax, rax
0x180070ad6  jnz     short loc_180070ADF
0x180070ad8  mov     ecx, 7E0h
0x180070add  jmp     short loc_180070B2B
0x180070adf  mov     rax, cs:fpIsColorProfileValid
0x180070ae6  lea     rdx, [rsp+2D0h+var_290]
0x180070aeb  mov     rcx, rbx
0x180070aee  mov     [rsp+2D0h+var_290], esi
0x180070af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070af7  test    eax, eax
0x180070af9  jz      short loc_180070B15
0x180070afb  cmp     [rsp+2D0h+var_290], esi
0x180070aff  jz      short loc_180070B15
0x180070b01  mov     rax, cs:fpCloseColorProfile
0x180070b08  mov     rcx, rbx
0x180070b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b10  jmp     loc_180070A28
0x180070b15  mov     rax, cs:fpCloseColorProfile
0x180070b1c  mov     rcx, rbx
0x180070b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b24  jmp     short loc_180070AD8
0x180070b26  mov     ecx, 7E1h
0x180070b2b  call    cs:__imp_GdiSetLastError
0x180070b31  xor     eax, eax
0x180070b33  mov     rcx, [rbp+1D0h+var_20]
0x180070b3a  xor     rcx, rsp; StackCookie
0x180070b3d  call    __security_check_cookie
0x180070b42  mov     rbx, [rsp+2D0h+arg_10]
0x180070b4a  add     rsp, 2C0h
0x180070b51  pop     rdi
0x180070b52  pop     rsi
0x180070b53  pop     rbp
0x180070b54  retn
```
