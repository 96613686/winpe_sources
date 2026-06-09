# ProfileSelection::Select(IMVCellularV2 *,ushort const *,uchar const *,ulong)

- ea: `0x18002a4f8`
- end: `0x18002a7e8`
- name: `?Select@ProfileSelection@@SAXPEAUIMVCellularV2@@PEBGPEBEK@Z`
- size: `752`
- prototype: `static void(struct IMVCellularV2 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800269e0`
- `0x18002ac1c`
- `0x180031d90`

## callees

- `0x18000108c`
- `0x180004244`
- `0x180012d80`
- `0x18002a4f8`
- `0x180036b1c`
- `0x180036c7c`
- `0x18003b946`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002a6f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002a6f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a746`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ProfileSelection::Select(
        struct IMVCellularV2 *a1,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v4; // rsi
  __int64 v8; // rax
  __int64 v9; // rdx
  _WORD *v10; // r8
  __int16 v11; // cx
  _WORD *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx
  void *v15; // rax
  _QWORD *v16; // rdi
  __int64 v17; // r8
  void *v18; // rbx
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // ecx
  const char *v22; // r9
  unsigned int i; // ebx
  __int64 v24; // rcx
  void *v25; // rcx
  int v26; // eax
  unsigned int v27; // eax
  int v28; // [rsp+20h] [rbp-79h]
  int v29; // [rsp+30h] [rbp-69h] BYREF
  void *Buf2; // [rsp+38h] [rbp-61h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-59h] BYREF
  char v32; // [rsp+50h] [rbp-49h]
  _OWORD v33[3]; // [rsp+58h] [rbp-41h] BYREF
  __int128 v34; // [rsp+88h] [rbp-11h] BYREF
  __int64 v35; // [rsp+98h] [rbp-1h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]
  int v37; // [rsp+B0h] [rbp+17h]
  int v38; // [rsp+B4h] [rbp+1Bh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v4 = a4;
  memset(v33, 0, sizeof(v33));
  v8 = 2147483646;
  v9 = 21;
  v10 = v33;
  do
  {
    if ( !v8 )
      break;
    v11 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v10++ = v11;
    --v8;
    --v9;
  }
  while ( v9 );
  v12 = v10 - 1;
  if ( v9 )
    v12 = v10;
  *v12 = 0;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)0x8007007ALL,
      v28);
  if ( (unsigned int)dword_180052170 > 4 )
  {
    v29 = 0;
    Buf2 = 0;
    v13 = *(_QWORD *)a1;
    pv[0] = &Buf2;
    pv[1] = 0;
    v32 = 1;
    v14 = (*(__int64 (__fastcall **)(struct IMVCellularV2 *, _OWORD *, int *, LPVOID *))(v13 + 56))(
            a1,
            v33,
            &v29,
            &pv[1]);
    if ( v32 )
    {
      v15 = *(void **)pv[0];
      *(_QWORD *)pv[0] = pv[1];
      if ( v15 )
        CoTaskMemFree(v15);
    }
    if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2147024894 )
    {
      v27 = wil::verify_hresult<long>(v14);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)v27,
        v28);
    }
    if ( (_DWORD)v4 && (v29 != (_DWORD)v4 || memcmp_0(a3, Buf2, v4)) )
    {
      *(_OWORD *)pv = 0;
      MvInitializeKeysFromBytes(a3, v4, (struct IMVKey ***)pv, (unsigned int *)&pv[1]);
      v34 = 0;
      v35 = 0;
      v16 = pv[0];
      MvPackKeys((__int64)&v34, (__int64)pv[0], (unsigned int)pv[1]);
      v18 = (void *)v34;
      v19 = *((_QWORD *)&v34 + 1) - v34;
      v20 = 0xFFFFFFFFLL;
      v21 = DWORD2(v34) - v34;
      if ( *((_QWORD *)&v34 + 1) - (_QWORD)v34 > 0xFFFFFFFF )
        v21 = -1;
      v22 = v19 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v19 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
          v22,
          v28);
      if ( (unsigned int)dword_180052170 > 4 )
      {
        v36 = v34;
        v37 = v21;
        v38 = 0;
        tlgWriteTransfer_EventWriteTransfer(&dword_180052170, &byte_180049757, 0, 0, 3, &v34);
      }
      if ( v18 )
        operator delete(v18);
      if ( v16 )
      {
        for ( i = 0; i < LODWORD(pv[1]); ++i )
        {
          v24 = v16[i];
          if ( v24 )
          {
            (*(void (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v24 + 16LL))(
              v24,
              v20,
              v17,
              v22);
            v16[i] = 0;
          }
        }
        CoTaskMemFree(v16);
      }
    }
    v25 = Buf2;
    Buf2 = 0;
    if ( v25 )
      CoTaskMemFree(v25);
  }
  v26 = (*(__int64 (__fastcall **)(struct IMVCellularV2 *, _OWORD *, _QWORD, const unsigned __int8 *))(*(_QWORD *)a1 + 48LL))(
          a1,
          v33,
          (unsigned int)v4,
          a3);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)(unsigned int)v26,
      v28);
}

```

## disassembly

```asm
0x18002a4f8  push    rbp
0x18002a4fa  push    rbx
0x18002a4fb  push    rsi
0x18002a4fc  push    rdi
0x18002a4fd  push    r12
0x18002a4ff  push    r13
0x18002a501  push    r14
0x18002a503  lea     rbp, [rsp-27h]
0x18002a508  sub     rsp, 0C0h
0x18002a50f  mov     rax, cs:__security_cookie
0x18002a516  xor     rax, rsp
0x18002a519  mov     [rbp+57h+var_38], rax
0x18002a51d  mov     esi, r9d
0x18002a520  mov     r13, r8
0x18002a523  mov     r9, rdx
0x18002a526  mov     r12, rcx
0x18002a529  xorps   xmm0, xmm0
0x18002a52c  movups  [rbp+57h+var_98], xmm0
0x18002a530  movups  [rbp+57h+var_88], xmm0
0x18002a534  movups  [rbp+57h+var_78], xmm0
0x18002a538  mov     eax, 7FFFFFFEh
0x18002a53d  mov     edx, 15h
0x18002a542  lea     r8, [rbp+57h+var_98]
0x18002a546  xor     r14d, r14d
0x18002a549  test    rax, rax
0x18002a54c  jz      short loc_18002A56C
0x18002a54e  movzx   ecx, word ptr [r9]
0x18002a552  test    cx, cx
0x18002a555  jz      short loc_18002A56C
0x18002a557  add     r9, 2
0x18002a55b  mov     [r8], cx
0x18002a55f  add     r8, 2
0x18002a563  dec     rax
0x18002a566  sub     rdx, 1
0x18002a56a  jnz     short loc_18002A549
0x18002a56c  mov     rax, rdx
0x18002a56f  neg     rax
0x18002a572  sbb     r9d, r9d
0x18002a575  not     r9d
0x18002a578  and     r9d, 8007007Ah; char *
0x18002a57f  lea     rcx, [r8-2]
0x18002a583  test    rdx, rdx
0x18002a586  cmovnz  rcx, r8
0x18002a58a  mov     [rcx], r14w
0x18002a58e  mov     rcx, [rbp+5Fh]; this
0x18002a592  jz      loc_18002A7A1
0x18002a598  mov     eax, cs:dword_180052170
0x18002a59e  cmp     eax, 4
0x18002a5a1  jbe     loc_18002A74C
0x18002a5a7  mov     [rbp+57h+var_C0], r14d
0x18002a5ab  mov     [rbp+57h+Buf2], r14
0x18002a5af  mov     rax, [r12]
0x18002a5b3  lea     rcx, [rbp+57h+Buf2]
0x18002a5b7  mov     [rbp+57h+pv], rcx
0x18002a5bb  mov     [rbp+57h+pv+8], r14
0x18002a5bf  mov     [rbp+57h+var_A0], 1
0x18002a5c3  lea     r9, [rbp+57h+pv+8]
0x18002a5c7  lea     r8, [rbp+57h+var_C0]
0x18002a5cb  lea     rdx, [rbp+57h+var_98]
0x18002a5cf  mov     rcx, r12
0x18002a5d2  mov     rax, [rax+38h]
0x18002a5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5db  mov     ebx, eax
0x18002a5dd  cmp     [rbp+57h+var_A0], r14b
0x18002a5e1  jz      short loc_18002A5FF
0x18002a5e3  mov     rdx, [rbp+57h+pv]
0x18002a5e7  mov     rax, [rdx]
0x18002a5ea  mov     rcx, [rbp+57h+pv+8]
0x18002a5ee  mov     [rdx], rcx
0x18002a5f1  test    rax, rax
0x18002a5f4  jz      short loc_18002A5FF
0x18002a5f6  mov     rcx, rax; pv
0x18002a5f9  call    cs:__imp_CoTaskMemFree
0x18002a5ff  mov     ecx, 80000000h
0x18002a604  lea     eax, [rbx+rcx]
0x18002a607  test    ecx, eax
0x18002a609  jnz     short loc_18002A617
0x18002a60b  cmp     ebx, 80070002h
0x18002a611  jnz     loc_18002A7B3
0x18002a617  test    esi, esi
0x18002a619  jz      loc_18002A739
0x18002a61f  cmp     [rbp+57h+var_C0], esi
0x18002a622  jnz     short loc_18002A63B
0x18002a624  mov     r8, rsi; Size
0x18002a627  mov     rdx, [rbp+57h+Buf2]; Buf2
0x18002a62b  mov     rcx, r13; Buf1
0x18002a62e  call    memcmp_0
0x18002a633  test    eax, eax
0x18002a635  jz      loc_18002A739
0x18002a63b  xorps   xmm0, xmm0
0x18002a63e  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18002a642  lea     r9, [rbp+57h+pv+8]; unsigned int *
0x18002a646  lea     r8, [rbp+57h+pv]; struct IMVKey ***
0x18002a64a  mov     edx, esi; unsigned int
0x18002a64c  mov     rcx, r13; unsigned __int8 *
0x18002a64f  call    ?MvInitializeKeysFromBytes@@YAJPEBEKPEAPEAPEAUIMVKey@@PEAKPEAUIClassFactory@@@Z; MvInitializeKeysFromBytes(uchar const *,ulong,IMVKey * * *,ulong *,IClassFactory *)
0x18002a654  xorps   xmm0, xmm0
0x18002a657  movdqu  [rbp+57h+var_68], xmm0
0x18002a65c  mov     [rbp+57h+var_58], r14
0x18002a660  mov     r8d, dword ptr [rbp+57h+pv+8]
0x18002a664  mov     rdi, [rbp+57h+pv]
0x18002a668  mov     rdx, rdi
0x18002a66b  lea     rcx, [rbp+57h+var_68]
0x18002a66f  call    ?MvPackKeys@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAUIMVKey@@K@Z; MvPackKeys(std::vector<uchar> &,IMVKey * *,ulong)
0x18002a674  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18002a678  mov     rbx, qword ptr [rbp+57h+var_68]
0x18002a67c  sub     rax, rbx
0x18002a67f  mov     edx, 0FFFFFFFFh
0x18002a684  cmp     rax, rdx
0x18002a687  mov     ecx, eax
0x18002a689  jbe     short loc_18002A68D
0x18002a68b  mov     ecx, edx
0x18002a68d  cmp     rdx, rax
0x18002a690  sbb     r9d, r9d
0x18002a693  and     r9d, 80070216h; char *
0x18002a69a  mov     r10, [rbp+5Fh]
0x18002a69e  cmp     rax, rdx
0x18002a6a1  ja      loc_18002A7D3
0x18002a6a7  mov     eax, cs:dword_180052170
0x18002a6ad  cmp     eax, 4
0x18002a6b0  jbe     short loc_18002A6E8
0x18002a6b2  mov     [rbp+57h+var_48], rbx
0x18002a6b6  mov     [rbp+57h+var_40], ecx
0x18002a6b9  mov     [rbp+57h+var_3C], r14d
0x18002a6bd  lea     rax, [rbp+57h+var_68]
0x18002a6c1  mov     [rsp+0F0h+var_C8], rax
0x18002a6c6  mov     [rsp+0F0h+var_D0], 3; int
0x18002a6ce  xor     r9d, r9d
0x18002a6d1  xor     r8d, r8d
0x18002a6d4  lea     rdx, byte_180049757
0x18002a6db  lea     rcx, dword_180052170
0x18002a6e2  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a6e7  nop
0x18002a6e8  test    rbx, rbx
0x18002a6eb  jz      short loc_18002A6F7
0x18002a6ed  mov     rcx, rbx
0x18002a6f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002a6f6  nop
0x18002a6f7  test    rdi, rdi
0x18002a6fa  jz      short loc_18002A739
0x18002a6fc  mov     ebx, r14d
0x18002a6ff  cmp     dword ptr [rbp+57h+pv+8], r14d
0x18002a703  jbe     short loc_18002A72F
0x18002a705  mov     r14d, ebx
0x18002a708  mov     rcx, [rdi+r14*8]
0x18002a70c  test    rcx, rcx
0x18002a70f  jz      short loc_18002A725
0x18002a711  mov     rax, [rcx]
0x18002a714  mov     rax, [rax+10h]
0x18002a718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a71d  mov     qword ptr [rdi+r14*8], 0
0x18002a725  inc     ebx
0x18002a727  cmp     ebx, dword ptr [rbp+57h+pv+8]
0x18002a72a  jb      short loc_18002A705
0x18002a72c  xor     r14d, r14d
0x18002a72f  mov     rcx, rdi; pv
0x18002a732  call    cs:__imp_CoTaskMemFree
0x18002a738  nop
0x18002a739  mov     rcx, [rbp+57h+Buf2]; pv
0x18002a73d  mov     [rbp+57h+Buf2], r14
0x18002a741  test    rcx, rcx
0x18002a744  jz      short loc_18002A74C
0x18002a746  call    cs:__imp_CoTaskMemFree
0x18002a74c  mov     rax, [r12]
0x18002a750  mov     r9, r13
0x18002a753  mov     r8d, esi
0x18002a756  lea     rdx, [rbp+57h+var_98]
0x18002a75a  mov     rcx, r12
0x18002a75d  mov     rax, [rax+30h]
0x18002a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a766  test    eax, eax
0x18002a768  js      short loc_18002A788
0x18002a76a  mov     rcx, [rbp+57h+var_38]
0x18002a76e  xor     rcx, rsp; StackCookie
0x18002a771  call    __security_check_cookie
0x18002a776  add     rsp, 0C0h
0x18002a77d  pop     r14
0x18002a77f  pop     r13
0x18002a781  pop     r12
0x18002a783  pop     rdi
0x18002a784  pop     rsi
0x18002a785  pop     rbx
0x18002a786  pop     rbp
0x18002a787  retn
0x18002a788  mov     rcx, [rbp+5Fh]; this
0x18002a78c  mov     r9d, eax; char *
0x18002a78f  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a796  mov     edx, 60h ; '`'; void *
0x18002a79b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a7a1  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a7a8  mov     edx, 44h ; 'D'; void *
0x18002a7ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a7b3  mov     ecx, ebx
0x18002a7b5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002a7ba  mov     r9d, eax; char *
0x18002a7bd  mov     rcx, [rbp+5Fh]; this
0x18002a7c1  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a7c8  mov     edx, 4Eh ; 'N'; void *
0x18002a7cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a7d3  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a7da  mov     edx, 57h ; 'W'; void *
0x18002a7df  mov     rcx, r10; this
0x18002a7e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
