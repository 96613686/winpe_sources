# _ReadStandardProperties

- ea: `0x1800028d8`
- end: `0x180002c20`
- name: `_ReadStandardProperties`
- size: `840`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800026fc`

## callees

- `0x180002098`
- `0x1800028d8`
- `0x180002cf0`
- `0x1800cd010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002a68`
- `msvcrt!memcpy_s` at `0x180002a68`
- `ole32!CoTaskMemAlloc` at `0x180002a4d`
- `ole32!CoTaskMemAlloc` at `0x180002a4d`
- `ole32!CoTaskMemFree` at `0x180002aa5`
- `ole32!CoTaskMemFree` at `0x180002aa5`
- `ole32!PropVariantClear` at `0x180002b2c`
- `ole32!PropVariantClear` at `0x180002b2c`

## pseudocode

```c
__int64 __fastcall ReadStandardProperties(__int64 a1, __int64 a2)
{
  __int64 v3; // r13
  struct CMessageTree *Instance; // rax
  struct CMessageTree *v5; // rsi
  int v6; // r14d
  int v7; // esi
  char *v9; // rdi
  char *v10; // rbx
  unsigned int v11; // edi
  int v12; // r15d
  __int64 v13; // r12
  __int64 v14; // r8
  __int64 v15; // rdx
  void *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r13
  void *v19; // rax
  VARTYPE v20; // ax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // [rsp+30h] [rbp-20h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v28; // [rsp+A0h] [rbp+50h] BYREF
  void *Source; // [rsp+A8h] [rbp+58h] BYREF

  v3 = a2;
  Instance = CMessageTree::CreateInstance(0);
  v5 = Instance;
  if ( Instance )
  {
    v9 = (char *)Instance + 32;
    v10 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Instance + 4) + 64LL))((__int64)Instance + 32);
    if ( v6 >= 0 )
    {
      v10 = v9;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    (*(void (__fastcall **)(struct CMessageTree *))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v25 = 0;
    v7 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v10)(
           v10,
           &GUID_f90adfef_d01f_11d2_a004_00a0c90c9bb6,
           &v25);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 40LL))(v10, a1);
      if ( v7 >= 0 )
      {
        v11 = 0;
        v28 = 0;
        while ( 1 )
        {
          if ( v11 >= 0x1A )
            goto LABEL_32;
          v12 = 0;
          v13 = 32LL * v11;
          memset(&pvar, 0, sizeof(pvar));
          v14 = *(unsigned int *)((char *)&c_rgMsgProps + v13 + 16);
          if ( (_DWORD)v14 != -1 )
          {
            v15 = *(unsigned int *)((char *)&c_rgMsgProps + v13 + 20);
            Source = 0;
            v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, void **))(*(_QWORD *)v25 + 496LL))(
                    v25,
                    v15,
                    v14,
                    &Source);
            if ( v12 >= 0 )
              break;
          }
LABEL_25:
          if ( !pvar.vt )
          {
            if ( *(_DWORD *)((char *)&c_rgMsgProps + v13 + 12) == -1 )
            {
              v23 = *(__int64 *)((char *)&c_rgMsgProps + v13);
              if ( PKEY_Message_HasAttachments.pid == *(_DWORD *)(v23 + 16) )
              {
                v24 = *(_QWORD *)&PKEY_Message_HasAttachments.fmtid.Data1 - *(_QWORD *)v23;
                if ( *(_QWORD *)&PKEY_Message_HasAttachments.fmtid.Data1 == *(_QWORD *)v23 )
                  v24 = *(_QWORD *)PKEY_Message_HasAttachments.fmtid.Data4 - *(_QWORD *)(v23 + 8);
                if ( !v24 )
                {
                  Source = 0;
                  if ( (**(int (__fastcall ***)(char *, GUID *, void **))v10)(
                         v10,
                         &GUID_fd853cd4_7f86_11d0_8252_00c04fd85ab4,
                         &Source) >= 0 )
                  {
                    pvar.vt = 11;
                    v28 = 0;
                    if ( (*(int (__fastcall **)(void *, unsigned int *))(*(_QWORD *)Source + 104LL))(Source, &v28) >= 0
                      && (v28 & 1) != 0 )
                    {
                      pvar.iVal = -1;
                    }
                    else
                    {
                      pvar.iVal = 0;
                    }
                  }
                  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&Source);
LABEL_29:
                  if ( pvar.vt >= 2u )
                    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v3 + 48LL))(
                           v3,
                           *(const struct MsgPropStruct near *const *)((char *)&c_rgMsgProps + v13),
                           &pvar);
                  goto LABEL_31;
                }
              }
            }
            else
            {
              v21 = *(int *)((char *)&c_rgMsgProps + v13 + 12);
              pvar.vt = *(_WORD *)((char *)&c_rgMsgProps + v13 + 8);
              v12 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v10 + 312LL))(
                      v10,
                      v21,
                      0,
                      &pvar);
            }
          }
          if ( v12 >= 0 )
            goto LABEL_29;
LABEL_31:
          PropVariantClear(&pvar);
          v28 = ++v11;
          if ( v7 < 0 )
            goto LABEL_32;
        }
        v16 = Source;
        v12 = 0;
        if ( Source )
        {
          v17 = -1;
          do
            ++v17;
          while ( *((_WORD *)Source + v17) );
          v18 = 2 * v17 + 2;
          v19 = CoTaskMemAlloc(v18);
          pvar.hVal.QuadPart = (LONGLONG)v19;
          if ( v19 )
          {
            memcpy_s(v19, v18, v16, v18);
            v16 = Source;
            v20 = 31;
LABEL_22:
            pvar.vt = v20;
            if ( v16 )
              CoTaskMemFree(v16);
            v11 = v28;
            v3 = a2;
            goto LABEL_25;
          }
          v16 = Source;
          v12 = -2147024882;
        }
        else
        {
          v12 = -2147024809;
        }
        v20 = _mm_cvtsi128_si32((__m128i)0LL);
        memset(&pvar, 0, sizeof(pvar));
        goto LABEL_22;
      }
LABEL_32:
      v22 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v7;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800028d8  mov     [rsp-38h+arg_0], rbx
0x1800028dd  mov     [rsp-38h+arg_8], rdx
0x1800028e2  push    rbp
0x1800028e3  push    rsi
0x1800028e4  push    rdi
0x1800028e5  push    r12
0x1800028e7  push    r13
0x1800028e9  push    r14
0x1800028eb  push    r15
0x1800028ed  mov     rbp, rsp
0x1800028f0  sub     rsp, 50h
0x1800028f4  mov     r15, rcx
0x1800028f7  mov     r13, rdx
0x1800028fa  xor     ecx, ecx; struct IUnknown *
0x1800028fc  call    ?CreateInstance@CMessageTree@@SAPEAV1@PEAUIUnknown@@@Z; CMessageTree::CreateInstance(IUnknown *)
0x180002901  xor     r12d, r12d
0x180002904  mov     rsi, rax
0x180002907  test    rax, rax
0x18000290a  jnz     short loc_18000292F
0x18000290c  mov     r14d, 8007000Eh
0x180002912  mov     esi, r14d
0x180002915  mov     rbx, [rsp+50h+arg_0]
0x18000291d  mov     eax, esi
0x18000291f  add     rsp, 50h
0x180002923  pop     r15
0x180002925  pop     r14
0x180002927  pop     r13
0x180002929  pop     r12
0x18000292b  pop     rdi
0x18000292c  pop     rsi
0x18000292d  pop     rbp
0x18000292e  retn
0x18000292f  lea     rdi, [rax+20h]
0x180002933  mov     rbx, r12
0x180002936  mov     rax, [rdi]
0x180002939  mov     rcx, rdi
0x18000293c  mov     rax, [rax+40h]
0x180002940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002945  mov     r14d, eax
0x180002948  test    eax, eax
0x18000294a  js      short loc_18000295E
0x18000294c  mov     rdx, [rdi]
0x18000294f  mov     rcx, rdi
0x180002952  mov     rbx, rdi
0x180002955  mov     rax, [rdx+8]
0x180002959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295e  mov     rcx, [rsi]
0x180002961  mov     rax, [rcx+10h]
0x180002965  mov     rcx, rsi
0x180002968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296d  test    r14d, r14d
0x180002970  js      short loc_180002912
0x180002972  mov     [rbp+var_20], r12
0x180002976  lea     r8, [rbp+var_20]
0x18000297a  mov     rax, [rbx]
0x18000297d  lea     rdx, _GUID_f90adfef_d01f_11d2_a004_00a0c90c9bb6
0x180002984  mov     rcx, rbx
0x180002987  mov     rax, [rax]
0x18000298a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298f  mov     esi, eax
0x180002991  test    eax, eax
0x180002993  js      loc_180002B67
0x180002999  mov     rax, [rbx]
0x18000299c  mov     rdx, r15
0x18000299f  mov     rcx, rbx
0x1800029a2  mov     rax, [rax+28h]
0x1800029a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ab  mov     esi, eax
0x1800029ad  test    eax, eax
0x1800029af  js      loc_180002B4E
0x1800029b5  mov     edi, r12d
0x1800029b8  mov     [rbp+arg_10], r12d
0x1800029bc  mov     r14d, 8007000Eh
0x1800029c2  lea     r10, ?c_rgMsgProps@@3QBUMsgPropStruct@@B; MsgPropStruct const near * const c_rgMsgProps
0x1800029c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800029cd  cmp     edi, 1Ah
0x1800029d0  jnb     loc_180002B4E
0x1800029d6  mov     r15d, r12d
0x1800029d9  xor     eax, eax
0x1800029db  mov     r12d, edi
0x1800029de  xorps   xmm0, xmm0
0x1800029e1  shl     r12, 5
0x1800029e5  movups  xmmword ptr [rbp+pvar], xmm0
0x1800029e9  mov     qword ptr [rbp+pvar+10h], rax
0x1800029ed  mov     r8d, [r12+r10+10h]
0x1800029f2  cmp     r8d, ecx
0x1800029f5  jz      loc_180002B7B
0x1800029fb  mov     rcx, [rbp+var_20]
0x1800029ff  lea     r9, [rbp+Source]
0x180002a03  mov     edx, [r12+r10+14h]
0x180002a08  mov     [rbp+Source], rax
0x180002a0c  mov     rax, [rcx]
0x180002a0f  mov     rax, [rax+1F0h]
0x180002a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1b  xor     edx, edx
0x180002a1d  mov     r15d, eax
0x180002a20  test    eax, eax
0x180002a22  js      loc_180002AB4
0x180002a28  mov     rdi, [rbp+Source]
0x180002a2c  xor     r15d, r15d
0x180002a2f  test    rdi, rdi
0x180002a32  jz      short loc_180002A82
0x180002a34  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002a38  inc     rax
0x180002a3b  cmp     [rdi+rax*2], r15w
0x180002a40  jnz     short loc_180002A38
0x180002a42  lea     r13, ds:2[rax*2]
0x180002a4a  mov     rcx, r13; cb
0x180002a4d  call    cs:__imp_CoTaskMemAlloc
0x180002a53  mov     qword ptr [rbp+pvar+8], rax
0x180002a57  test    rax, rax
0x180002a5a  jz      short loc_180002A79
0x180002a5c  mov     r9, r13; SourceSize
0x180002a5f  mov     r8, rdi; Source
0x180002a62  mov     rdx, r13; DestinationSize
0x180002a65  mov     rcx, rax; Destination
0x180002a68  call    cs:__imp_memcpy_s
0x180002a6e  mov     rdi, [rbp+Source]
0x180002a72  mov     eax, 1Fh
0x180002a77  jmp     short loc_180002A99
0x180002a79  mov     rdi, [rbp+Source]
0x180002a7d  mov     r15d, r14d
0x180002a80  jmp     short loc_180002A88
0x180002a82  mov     r15d, 80070057h
0x180002a88  xor     eax, eax
0x180002a8a  xorps   xmm0, xmm0
0x180002a8d  mov     qword ptr [rbp+pvar+10h], rax
0x180002a91  movd    eax, xmm0
0x180002a95  movups  xmmword ptr [rbp+pvar], xmm0
0x180002a99  mov     word ptr [rbp+pvar], ax
0x180002a9d  test    rdi, rdi
0x180002aa0  jz      short loc_180002AAB
0x180002aa2  mov     rcx, rdi; pv
0x180002aa5  call    cs:__imp_CoTaskMemFree
0x180002aab  mov     edi, [rbp+arg_10]
0x180002aae  xor     edx, edx
0x180002ab0  mov     r13, [rbp+arg_8]
0x180002ab4  lea     r10, ?c_rgMsgProps@@3QBUMsgPropStruct@@B; MsgPropStruct const near * const c_rgMsgProps
0x180002abb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002abf  cmp     word ptr [rbp+pvar], dx
0x180002ac3  jnz     short loc_180002AFB
0x180002ac5  cmp     [r12+r10+0Ch], ecx
0x180002aca  jz      loc_180002B82
0x180002ad0  movzx   eax, word ptr [r12+r10+8]
0x180002ad6  lea     r9, [rbp+pvar]
0x180002ada  movsxd  rdx, dword ptr [r12+r10+0Ch]
0x180002adf  xor     r8d, r8d
0x180002ae2  mov     word ptr [rbp+pvar], ax
0x180002ae6  mov     rcx, rbx
0x180002ae9  mov     rax, [rbx]
0x180002aec  mov     rax, [rax+138h]
0x180002af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af8  mov     r15d, eax
0x180002afb  test    r15d, r15d
0x180002afe  js      short loc_180002B28
0x180002b00  cmp     word ptr [rbp+pvar], 2
0x180002b05  jb      short loc_180002B28
0x180002b07  mov     rax, [r13+0]
0x180002b0b  lea     rdx, ?c_rgMsgProps@@3QBUMsgPropStruct@@B; MsgPropStruct const near * const c_rgMsgProps
0x180002b12  mov     rdx, [r12+rdx]
0x180002b16  lea     r8, [rbp+pvar]
0x180002b1a  mov     rcx, r13
0x180002b1d  mov     rax, [rax+30h]
0x180002b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b26  mov     esi, eax
0x180002b28  lea     rcx, [rbp+pvar]; pvar
0x180002b2c  call    cs:__imp_PropVariantClear
0x180002b32  xor     r12d, r12d
0x180002b35  lea     r10, ?c_rgMsgProps@@3QBUMsgPropStruct@@B; MsgPropStruct const near * const c_rgMsgProps
0x180002b3c  inc     edi
0x180002b3e  mov     [rbp+arg_10], edi
0x180002b41  lea     rcx, [r12-1]
0x180002b46  test    esi, esi
0x180002b48  jns     loc_1800029CD
0x180002b4e  mov     rcx, [rbp+var_20]
0x180002b52  test    rcx, rcx
0x180002b55  jz      short loc_180002B67
0x180002b57  mov     [rbp+var_20], r12
0x180002b5b  mov     rax, [rcx]
0x180002b5e  mov     rax, [rax+10h]
0x180002b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b67  mov     rax, [rbx]
0x180002b6a  mov     rcx, rbx
0x180002b6d  mov     rax, [rax+10h]
0x180002b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b76  jmp     loc_180002915
0x180002b7b  xor     edx, edx
0x180002b7d  jmp     loc_180002ABF
0x180002b82  mov     rcx, [r12+r10]
0x180002b86  mov     eax, cs:PKEY_Message_HasAttachments.pid
0x180002b8c  cmp     eax, [rcx+10h]
0x180002b8f  jnz     loc_180002AFB
0x180002b95  mov     rax, qword ptr cs:PKEY_Message_HasAttachments.fmtid.Data1
0x180002b9c  sub     rax, [rcx]
0x180002b9f  jnz     short loc_180002BAC
0x180002ba1  mov     rax, qword ptr cs:PKEY_Message_HasAttachments.fmtid.Data4
0x180002ba8  sub     rax, [rcx+8]
0x180002bac  test    rax, rax
0x180002baf  jnz     loc_180002AFB
0x180002bb5  xor     r15d, r15d
0x180002bb8  lea     r8, [rbp+Source]
0x180002bbc  mov     [rbp+Source], r15
0x180002bc0  lea     rdx, _GUID_fd853cd4_7f86_11d0_8252_00c04fd85ab4
0x180002bc7  mov     rax, [rbx]
0x180002bca  mov     rcx, rbx
0x180002bcd  mov     rax, [rax]
0x180002bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd5  test    eax, eax
0x180002bd7  js      short loc_180002C12
0x180002bd9  mov     rcx, [rbp+Source]
0x180002bdd  lea     eax, [r15+0Bh]
0x180002be1  mov     word ptr [rbp+pvar], ax
0x180002be5  lea     rdx, [rbp+arg_10]
0x180002be9  mov     [rbp+arg_10], r15d
0x180002bed  mov     rax, [rcx]
0x180002bf0  mov     rax, [rax+68h]
0x180002bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf9  test    eax, eax
0x180002bfb  js      short loc_180002C0D
0x180002bfd  test    byte ptr [rbp+arg_10], 1
0x180002c01  jz      short loc_180002C0D
0x180002c03  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c07  mov     word ptr [rbp+pvar+8], ax
0x180002c0b  jmp     short loc_180002C12
0x180002c0d  mov     word ptr [rbp+pvar+8], r15w
0x180002c12  lea     rcx, [rbp+Source]
0x180002c16  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180002c1b  jmp     loc_180002B00
```
