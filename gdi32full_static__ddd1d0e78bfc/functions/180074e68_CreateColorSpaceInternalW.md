# CreateColorSpaceInternalW

- ea: `0x180074e68`
- end: `0x18007510a`
- name: `CreateColorSpaceInternalW`
- size: `674`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180037f34`
- `0x18007e9a0`
- `0x18008d110`
- `0x18008eb38`
- `0x180095690`

## callees

- `0x18003a76c`
- `0x18003b378`
- `0x180074e68`
- `0x18007f800`
- `0x180080604`
- `0x1800a8010`

## import_xrefs

- `GDI32!ghICM` at `0x180074f8d`
- `GDI32!ghICM` at `0x180075005`
- `GDI32!GdiSetLastError` at `0x1800750d9`
- `GDI32!GdiSetLastError` at `0x1800750d9`
- `win32u!NtGdiCreateColorSpace` at `0x180074fd5`
- `win32u!NtGdiCreateColorSpace` at `0x180074fd5`

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
0x180074e68  mov     [rsp-8+arg_10], rbx
0x180074e6d  push    rbp
0x180074e6e  push    rsi
0x180074e6f  push    rdi
0x180074e70  lea     rbp, [rsp-1C0h]
0x180074e78  sub     rsp, 2C0h
0x180074e7f  mov     rax, cs:__security_cookie
0x180074e86  xor     rax, rsp
0x180074e89  mov     [rbp+1D0h+var_20], rax
0x180074e90  mov     edi, edx
0x180074e92  mov     rbx, rcx
0x180074e95  xor     edx, edx; Val
0x180074e97  lea     rcx, [rsp+2D0h+var_270]; void *
0x180074e9c  mov     r8d, 250h; Size
0x180074ea2  call    memset_0
0x180074ea7  xor     esi, esi
0x180074ea9  test    rbx, rbx
0x180074eac  jnz     short loc_180074EB8
0x180074eae  mov     ecx, 57h ; 'W'
0x180074eb3  jmp     loc_1800750D9
0x180074eb8  cmp     dword ptr [rbx], 50534F43h
0x180074ebe  jnz     loc_1800750D4
0x180074ec4  cmp     dword ptr [rbx+4], 400h
0x180074ecb  jnz     loc_1800750D4
0x180074ed1  cmp     dword ptr [rbx+8], 24Ch
0x180074ed8  jnz     loc_1800750D4
0x180074ede  mov     eax, [rbx+10h]
0x180074ee1  cmp     eax, 8
0x180074ee4  ja      loc_1800750D4
0x180074eea  mov     ecx, 116h
0x180074eef  bt      ecx, eax
0x180074ef2  jnb     loc_1800750D4
0x180074ef8  mov     edx, 4
0x180074efd  lea     rcx, [rsp+2D0h+var_270]
0x180074f02  mov     rax, rbx
0x180074f05  lea     r8d, [rdx+7Ch]
0x180074f09  movups  xmm0, xmmword ptr [rax]
0x180074f0c  movups  xmm1, xmmword ptr [rax+10h]
0x180074f10  movups  xmmword ptr [rcx], xmm0
0x180074f13  movups  xmm0, xmmword ptr [rax+20h]
0x180074f17  movups  xmmword ptr [rcx+10h], xmm1
0x180074f1b  movups  xmm1, xmmword ptr [rax+30h]
0x180074f1f  movups  xmmword ptr [rcx+20h], xmm0
0x180074f23  movups  xmm0, xmmword ptr [rax+40h]
0x180074f27  movups  xmmword ptr [rcx+30h], xmm1
0x180074f2b  movups  xmm1, xmmword ptr [rax+50h]
0x180074f2f  movups  xmmword ptr [rcx+40h], xmm0
0x180074f33  movups  xmm0, xmmword ptr [rax+60h]
0x180074f37  movups  xmmword ptr [rcx+50h], xmm1
0x180074f3b  movups  xmm1, xmmword ptr [rax+70h]
0x180074f3f  add     rax, r8
0x180074f42  movups  xmmword ptr [rcx+60h], xmm0
0x180074f46  movups  xmmword ptr [rcx+70h], xmm1
0x180074f4a  add     rcx, r8
0x180074f4d  sub     rdx, 1
0x180074f51  jnz     short loc_180074F09
0x180074f53  movups  xmm0, xmmword ptr [rax]
0x180074f56  movups  xmm1, xmmword ptr [rax+10h]
0x180074f5a  movups  xmmword ptr [rcx], xmm0
0x180074f5d  movups  xmm0, xmmword ptr [rax+20h]
0x180074f61  movups  xmmword ptr [rcx+10h], xmm1
0x180074f65  movups  xmm1, xmmword ptr [rax+30h]
0x180074f69  movups  xmmword ptr [rcx+20h], xmm0
0x180074f6d  movups  xmm0, xmmword ptr [rax+3Ch]
0x180074f71  movups  xmmword ptr [rcx+30h], xmm1
0x180074f75  movups  xmmword ptr [rcx+3Ch], xmm0
0x180074f79  mov     [rbp+1D0h+var_24], edi
0x180074f7f  cmp     [rbx+0Ch], esi
0x180074f82  jz      short loc_180074FE6
0x180074f84  cmp     dword ptr [rbx+0Ch], 4C494E4Bh
0x180074f8b  jz      short loc_180074FE6
0x180074f8d  mov     rax, cs:__imp_ghICM
0x180074f94  mov     [rsp+2D0h+var_290], 104h
0x180074f9c  cmp     [rax], rsi
0x180074f9f  jnz     short loc_180074FAE
0x180074fa1  call    ?IcmInitialize@@YAHXZ; IcmInitialize(void)
0x180074fa6  test    eax, eax
0x180074fa8  jz      loc_1800750E5
0x180074fae  mov     edx, [rbx+0Ch]
0x180074fb1  lea     r9, [rsp+2D0h+var_290]
0x180074fb6  mov     rax, cs:fpGetStandardColorSpaceProfileW
0x180074fbd  lea     r8, [rbp+1D0h+var_22C]
0x180074fc1  xor     ecx, ecx
0x180074fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074fc8  test    eax, eax
0x180074fca  jz      loc_1800750D4
0x180074fd0  lea     rcx, [rsp+2D0h+var_270]
0x180074fd5  call    cs:__imp_NtGdiCreateColorSpace
0x180074fdc  nop     dword ptr [rax+rax+00h]
0x180074fe1  jmp     loc_1800750E7
0x180074fe6  lea     rcx, [rbx+44h]; unsigned __int16 *
0x180074fea  mov     [rsp+2D0h+var_264], esi
0x180074fee  cmp     [rcx], si
0x180074ff1  jz      short loc_180074FD0
0x180074ff3  lea     rdx, [rbp+1D0h+var_22C]; unsigned __int16 *
0x180074ff7  call    BuildIcmProfilePath
0x180074ffc  test    rax, rax
0x180074fff  jz      loc_180074EAE
0x180075005  mov     rax, cs:__imp_ghICM
0x18007500c  cmp     [rax], rsi
0x18007500f  jnz     short loc_18007501E
0x180075011  call    ?IcmInitialize@@YAHXZ; IcmInitialize(void)
0x180075016  test    eax, eax
0x180075018  jz      loc_1800750E5
0x18007501e  lea     rax, [rbp+1D0h+var_22C]
0x180075022  mov     [rsp+2D0h+var_288], 1
0x18007502b  mov     [rsp+2D0h+var_280], rax
0x180075030  lea     rcx, [rbp+1D0h+var_22C]
0x180075034  or      rax, 0FFFFFFFFFFFFFFFFh
0x180075038  mov     [rsp+2D0h+var_274], esi
0x18007503c  mov     r9d, 1
0x180075042  inc     rax
0x180075045  cmp     [rcx+rax*2], si
0x180075049  jnz     short loc_180075042
0x18007504b  lea     eax, ds:2[rax*2]
0x180075052  mov     [rsp+2D0h+var_2A0], r9d
0x180075057  mov     [rsp+2D0h+var_278], eax
0x18007505b  lea     rcx, [rsp+2D0h+var_288]
0x180075060  mov     rax, cs:fpWcsOpenColorProfileW
0x180075067  xor     r8d, r8d
0x18007506a  mov     [rsp+2D0h+var_2A8], 3
0x180075072  xor     edx, edx
0x180075074  mov     [rsp+2D0h+var_2B0], r9d
0x180075079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007507e  mov     rbx, rax
0x180075081  test    rax, rax
0x180075084  jnz     short loc_18007508D
0x180075086  mov     ecx, 7E0h
0x18007508b  jmp     short loc_1800750D9
0x18007508d  mov     rax, cs:fpIsColorProfileValid
0x180075094  lea     rdx, [rsp+2D0h+var_290]
0x180075099  mov     rcx, rbx
0x18007509c  mov     [rsp+2D0h+var_290], esi
0x1800750a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750a5  test    eax, eax
0x1800750a7  jz      short loc_1800750C3
0x1800750a9  cmp     [rsp+2D0h+var_290], esi
0x1800750ad  jz      short loc_1800750C3
0x1800750af  mov     rax, cs:fpCloseColorProfile
0x1800750b6  mov     rcx, rbx
0x1800750b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750be  jmp     loc_180074FD0
0x1800750c3  mov     rax, cs:fpCloseColorProfile
0x1800750ca  mov     rcx, rbx
0x1800750cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750d2  jmp     short loc_180075086
0x1800750d4  mov     ecx, 7E1h
0x1800750d9  call    cs:__imp_GdiSetLastError
0x1800750e0  nop     dword ptr [rax+rax+00h]
0x1800750e5  xor     eax, eax
0x1800750e7  mov     rcx, [rbp+1D0h+var_20]
0x1800750ee  xor     rcx, rsp; StackCookie
0x1800750f1  call    __security_check_cookie
0x1800750f6  mov     rbx, [rsp+2D0h+arg_10]
0x1800750fe  add     rsp, 2C0h
0x180075105  pop     rdi
0x180075106  pop     rsi
0x180075107  pop     rbp
0x180075108  retn
```
