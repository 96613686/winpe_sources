# TDDOResHelper::GetIconPath(ushort const *,ushort * *)

- ea: `0x1800159e8`
- end: `0x180015b5c`
- name: `?GetIconPath@TDDOResHelper@@QEAAJPEBGPEAPEAG@Z`
- size: `372`
- prototype: `__int64 __fastcall(LPVOID *ppv, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c128`
- `0x180036e34`

## callees

- `0x180009250`
- `0x1800159e8`
- `0x180015b64`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015b0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015b0d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015aaf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015aaf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015b39`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015b39`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015ac6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015ac6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TDDOResHelper::GetIconPath(LPVOID *ppv, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v6; // ebx
  const unsigned __int16 *v7; // rbx
  __int64 v8; // rax
  size_t v9; // rdi
  unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  HRESULT Instance; // eax
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]
  _QWORD v16[4]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+38h] BYREF

  v17 = 0;
  *a3 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  v6 = 0;
  v17 = 0;
  if ( *((_BYTE *)ppv + 8) )
    goto LABEL_2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppv);
  Instance = CoCreateInstance(
               &GUID_d2e86c4f_ea06_4a89_bf00_b49706db46e6,
               0,
               1u,
               &GUID_03e05342_07f2_4dee_98f7_c4ec68370cf4,
               ppv);
  v6 = 0;
  if ( Instance != -2147221164 )
    v6 = Instance;
  if ( v6 >= 0 )
  {
    *((_BYTE *)ppv + 8) = 1;
LABEL_2:
    if ( *ppv )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 8LL))(*ppv);
      v17 = (__int64)*ppv;
    }
    if ( v17 )
    {
      v16[0] = 31;
      v16[2] = 0;
      *(_OWORD *)pvar = 0;
      v15 = 0;
      v16[1] = a2;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, PROPVARIANT *))(*(_QWORD *)v17 + 48LL))(v17, v16, pvar);
      if ( v6 >= 0 )
      {
        if ( LOWORD(pvar[0]) == 31 )
        {
          v7 = (const unsigned __int16 *)pvar[1];
          v8 = -1;
          do
            ++v8;
          while ( *((_WORD *)pvar[1] + v8) );
          v9 = 2 * v8 + 2;
          v10 = (unsigned __int16 *)malloc(v9);
          *a3 = v10;
          if ( v10 )
          {
            v6 = StringCbCopyW(v10, v9, v7);
            if ( v6 )
            {
              free(*a3);
              *a3 = 0;
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
        PropVariantClear(pvar);
      }
    }
  }
  v11 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800159e8  push    rbp
0x1800159ea  push    rbx
0x1800159eb  push    rsi
0x1800159ec  push    rdi
0x1800159ed  push    r14
0x1800159ef  push    r15
0x1800159f1  mov     rbp, rsp
0x1800159f4  sub     rsp, 68h
0x1800159f8  mov     rsi, r8
0x1800159fb  mov     r14, rdx
0x1800159fe  mov     rdi, rcx
0x180015a01  xor     r15d, r15d
0x180015a04  mov     [rbp+arg_0], r15
0x180015a08  mov     [r8], r15
0x180015a0b  lea     rcx, [rbp+arg_0]
0x180015a0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015a14  mov     ebx, r15d
0x180015a17  mov     [rbp+arg_0], r15
0x180015a1b  cmp     [rdi+8], r15b
0x180015a1f  jz      loc_180015B18
0x180015a25  mov     rcx, [rdi]
0x180015a28  test    rcx, rcx
0x180015a2b  jz      short loc_180015A41
0x180015a2d  mov     rax, [rcx]
0x180015a30  mov     rax, [rax+8]
0x180015a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a39  nop
0x180015a3a  mov     rax, [rdi]
0x180015a3d  mov     [rbp+arg_0], rax
0x180015a41  cmp     [rbp+arg_0], r15
0x180015a45  jz      loc_180015ACD
0x180015a4b  xorps   xmm0, xmm0
0x180015a4e  xor     eax, eax
0x180015a50  movups  [rbp+var_20], xmm0
0x180015a54  mov     [rbp+var_10], rax
0x180015a58  xorps   xmm1, xmm1
0x180015a5b  movups  xmmword ptr [rbp+pvar], xmm1
0x180015a5f  mov     [rbp+var_28], rax
0x180015a63  lea     edi, [rax+1Fh]
0x180015a66  mov     word ptr [rbp+var_20], di
0x180015a6a  mov     qword ptr [rbp+var_20+8], r14
0x180015a6e  mov     rcx, [rbp+arg_0]
0x180015a72  mov     rax, [rcx]
0x180015a75  lea     r8, [rbp+pvar]
0x180015a79  lea     rdx, [rbp+var_20]
0x180015a7d  mov     rax, [rax+30h]
0x180015a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a86  mov     ebx, eax
0x180015a88  test    eax, eax
0x180015a8a  js      short loc_180015ACD
0x180015a8c  cmp     word ptr [rbp+pvar], di
0x180015a90  jnz     short loc_180015AC2
0x180015a92  mov     rbx, [rbp+pvar+8]
0x180015a96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015a9a  inc     rax
0x180015a9d  cmp     [rbx+rax*2], r15w
0x180015aa2  jnz     short loc_180015A9A
0x180015aa4  lea     rdi, ds:2[rax*2]
0x180015aac  mov     rcx, rdi; Size
0x180015aaf  call    cs:__imp_malloc
0x180015ab5  mov     [rsi], rax
0x180015ab8  test    rax, rax
0x180015abb  jnz     short loc_180015AF6
0x180015abd  mov     ebx, 8007000Eh
0x180015ac2  lea     rcx, [rbp+pvar]; pvar
0x180015ac6  call    cs:__imp_PropVariantClear
0x180015acc  nop
0x180015acd  mov     rcx, [rbp+arg_0]
0x180015ad1  test    rcx, rcx
0x180015ad4  jz      short loc_180015AE7
0x180015ad6  mov     [rbp+arg_0], r15
0x180015ada  mov     rax, [rcx]
0x180015add  mov     rax, [rax+10h]
0x180015ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae6  nop
0x180015ae7  mov     eax, ebx
0x180015ae9  add     rsp, 68h
0x180015aed  pop     r15
0x180015aef  pop     r14
0x180015af1  pop     rdi
0x180015af2  pop     rsi
0x180015af3  pop     rbx
0x180015af4  pop     rbp
0x180015af5  retn
0x180015af6  mov     r8, rbx; unsigned __int16 *
0x180015af9  mov     rdx, rdi; unsigned __int64
0x180015afc  mov     rcx, rax; unsigned __int16 *
0x180015aff  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180015b04  mov     ebx, eax
0x180015b06  test    eax, eax
0x180015b08  jz      short loc_180015AC2
0x180015b0a  mov     rcx, [rsi]; Block
0x180015b0d  call    cs:__imp_free
0x180015b13  mov     [rsi], r15
0x180015b16  jmp     short loc_180015AC2
0x180015b18  mov     rcx, rdi
0x180015b1b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015b20  mov     [rsp+68h+ppv], rdi; ppv
0x180015b25  lea     r9, _GUID_03e05342_07f2_4dee_98f7_c4ec68370cf4; riid
0x180015b2c  xor     edx, edx; pUnkOuter
0x180015b2e  lea     r8d, [rdx+1]; dwClsContext
0x180015b32  lea     rcx, _GUID_d2e86c4f_ea06_4a89_bf00_b49706db46e6; rclsid
0x180015b39  call    cs:__imp_CoCreateInstance
0x180015b3f  mov     ebx, r15d
0x180015b42  cmp     eax, 80040154h
0x180015b47  cmovnz  ebx, eax
0x180015b4a  test    ebx, ebx
0x180015b4c  js      loc_180015ACD
0x180015b52  mov     byte ptr [rdi+8], 1
0x180015b56  jmp     loc_180015A25
```
