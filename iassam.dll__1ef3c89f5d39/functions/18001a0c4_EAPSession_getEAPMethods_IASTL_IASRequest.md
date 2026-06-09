# EAPSession::getEAPMethods(IASTL::IASRequest &)

- ea: `0x18001a0c4`
- end: `0x18001a42c`
- name: `?getEAPMethods@EAPSession@@QEAAXAEAVIASRequest@IASTL@@@Z`
- size: `872`
- prototype: `void __fastcall(EAPSession *__hidden this, struct IASTL::IASRequest *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018fb0`

## callees

- `0x180001f0c`
- `0x180001f26`
- `0x18000b2a0`
- `0x18000bbf8`
- `0x18000c4a4`
- `0x18000c500`
- `0x180018b88`
- `0x18001a0c4`
- `0x1800254a0`
- `0x18002b472`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001a1e8`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001a3ca`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001a1e8`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001a3ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a329`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a329`

## string_xrefs

- `0x18001a37e`: `Not enough memory to eap method config data`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EAPSession::getEAPMethods(EAPSession *this, struct IAttributesRaw **a2)
{
  __int64 v4; // r12
  _OWORD *v5; // rax
  _OWORD *v6; // rsi
  _BYTE *v7; // rbx
  unsigned int v8; // r15d
  _BYTE *i; // rdi
  __int64 v10; // r15
  unsigned int j; // ecx
  __int64 v12; // rbx
  _QWORD *v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  void *v16; // rax
  unsigned int v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+60h] [rbp-A0h]
  char v22; // [rsp+64h] [rbp-9Ch]
  _BYTE v23[136]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v24; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v25; // [rsp+F8h] [rbp-8h]
  int v26; // [rsp+100h] [rbp+0h]
  char v27; // [rsp+104h] [rbp+4h]
  _BYTE v28[136]; // [rsp+108h] [rbp+8h] BYREF

  v19 = v23;
  v20 = v23;
  v21 = 8;
  v22 = 0;
  v17[0] = 4106;
  IASTL::IASAttributeVector::load((IASTL::IASAttributeVector *)&v19, a2[1], 1u, v17);
  FreeEAPMethods((EAPSession *)((char *)this + 280));
  v4 = (v20 - v19) >> 4;
  *((_DWORD *)this + 70) = v4;
  v5 = CoTaskMemAlloc(32LL * (unsigned int)v4);
  v6 = v5;
  *((_QWORD *)this + 36) = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Not enough memory to allocate array of EAP_HOST_AUTHENTICATOR_METHOD_DATA");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
    }
    *(_QWORD *)v17 = "bad allocation";
    exception::exception((exception *)pExceptionObject, (const char *const *)v17, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  memset_0(v5, 0, 32LL * (unsigned int)v4);
  v7 = v19;
  v8 = 0;
  while ( v7 != v20 )
  {
    v6[2 * v8] = *(_OWORD *)*(_QWORD *)(*((_QWORD *)v7 + 1) + 32LL);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Allowed EAP type: %d");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_69033002015f3c629418a4473ed337be_Traceguids);
    }
    v7 += 16;
    ++v8;
  }
  v24 = v28;
  v25 = v28;
  v26 = 8;
  v27 = 0;
  v17[0] = 8098;
  if ( IASTL::IASAttributeVector::load((IASTL::IASAttributeVector *)&v24, a2[1], 1u, v17) )
  {
    for ( i = v24; i != v25; i += 16 )
    {
      v10 = *((_QWORD *)i + 1);
      for ( j = 0; j < (unsigned int)v4; ++j )
      {
        v12 = 2LL * j;
        v13 = *(_QWORD **)(v10 + 32);
        v14 = *(_QWORD *)&v6[v12] - *v13;
        if ( !v14 )
          v14 = *((_QWORD *)&v6[v12] + 1) - v13[1];
        if ( !v14 )
        {
          v15 = *(_DWORD *)(v10 + 24) - 20;
          LODWORD(v6[v12 + 1]) = v15;
          v16 = CoTaskMemAlloc(v15);
          *((_QWORD *)&v6[v12 + 1] + 1) = v16;
          if ( !v16 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("Not enough memory to eap method config data");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_69033002015f3c629418a4473ed337be_Traceguids,
                "NPSSVC");
            }
            *(_QWORD *)v17 = "bad allocation";
            exception::exception((exception *)pExceptionObject, (const char *const *)v17, 1);
            pExceptionObject[0] = &std::bad_alloc::`vftable';
            throw (std::bad_alloc *)pExceptionObject;
          }
          memcpy_0(v16, (const void *)(*(_QWORD *)(v10 + 32) + 20LL), LODWORD(v6[v12 + 1]));
          if ( LOBYTE(v6[v12]) == 25 )
            *(_DWORD *)(*((_QWORD *)&v6[v12 + 1] + 1) + 8LL) &= ~2u;
          break;
        }
      }
    }
  }
  IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>((IASTL::IASAttributeVector *)&v24);
  IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>((IASTL::IASAttributeVector *)&v19);
}

```

## disassembly

```asm
0x18001a0c4  mov     [rsp-8+arg_10], rbx
0x18001a0c9  push    rbp
0x18001a0ca  push    rsi
0x18001a0cb  push    rdi
0x18001a0cc  push    r12
0x18001a0ce  push    r13
0x18001a0d0  push    r14
0x18001a0d2  push    r15
0x18001a0d4  lea     rbp, [rsp-0A0h]
0x18001a0dc  sub     rsp, 1A0h
0x18001a0e3  mov     rax, cs:__security_cookie
0x18001a0ea  xor     rax, rsp
0x18001a0ed  mov     [rbp+0D0h+var_40], rax
0x18001a0f4  mov     r13, rdx
0x18001a0f7  mov     rdi, rcx
0x18001a0fa  lea     rax, [rsp+1D0h+var_168]
0x18001a0ff  mov     [rsp+1D0h+var_180], rax
0x18001a104  lea     rax, [rsp+1D0h+var_168]
0x18001a109  mov     [rsp+1D0h+var_178], rax
0x18001a10e  mov     [rsp+1D0h+var_170], 8
0x18001a116  mov     [rsp+1D0h+var_16C], 0
0x18001a11b  mov     [rsp+1D0h+var_1A0], 100Ah
0x18001a123  lea     r9, [rsp+1D0h+var_1A0]; unsigned int *
0x18001a128  mov     r15d, 1
0x18001a12e  mov     r8d, r15d; unsigned int
0x18001a131  mov     rdx, [rdx+8]; struct IAttributesRaw *
0x18001a135  lea     rcx, [rsp+1D0h+var_180]; this
0x18001a13a  call    ?load@IASAttributeVector@IASTL@@QEAAKPEAUIAttributesRaw@@KPEAK@Z; IASTL::IASAttributeVector::load(IAttributesRaw *,ulong,ulong *)
0x18001a13f  lea     rbx, [rdi+118h]
0x18001a146  mov     rcx, rbx; struct _EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY *
0x18001a149  call    ?FreeEAPMethods@@YAXAEAU_EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY@@@Z; FreeEAPMethods(_EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY &)
0x18001a14e  mov     r12, [rsp+1D0h+var_178]
0x18001a153  sub     r12, [rsp+1D0h+var_180]
0x18001a158  sar     r12, 4
0x18001a15c  mov     [rbx], r12d
0x18001a15f  mov     ebx, r12d
0x18001a162  shl     rbx, 5
0x18001a166  mov     rcx, rbx; cb
0x18001a169  call    cs:__imp_CoTaskMemAlloc
0x18001a16f  mov     rsi, rax
0x18001a172  mov     [rdi+120h], rax
0x18001a179  test    rax, rax
0x18001a17c  jnz     loc_18001A20C
0x18001a182  lea     r14, WPP_GLOBAL_Control
0x18001a189  mov     rax, cs:WPP_GLOBAL_Control
0x18001a190  cmp     rax, r14
0x18001a193  jz      short loc_18001A1CF
0x18001a195  cmp     byte ptr [rax+19h], 2
0x18001a199  jb      short loc_18001A1CF
0x18001a19b  test    byte ptr [rax+1Ch], 4
0x18001a19f  jz      short loc_18001A1CF
0x18001a1a1  lea     rcx, aNotEnoughMemor_1; "Not enough memory to allocate array of "...
0x18001a1a8  call    WppDbgPrint
0x18001a1ad  lea     edx, [rsi+10h]
0x18001a1b0  lea     r9, aNpssvc; "NPSSVC"
0x18001a1b7  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001a1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1c5  mov     rcx, [rcx+10h]
0x18001a1c9  call    WPP_SF_s
0x18001a1ce  nop
0x18001a1cf  lea     rax, aBadAllocation; "bad allocation"
0x18001a1d6  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x18001a1db  mov     r8d, r15d
0x18001a1de  lea     rdx, [rsp+1D0h+var_1A0]
0x18001a1e3  lea     rcx, [rsp+1D0h+pExceptionObject]
0x18001a1e8  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18001a1ee  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001a1f5  mov     [rsp+1D0h+pExceptionObject], rax
0x18001a1fa  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a201  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x18001a206  call    _CxxThrowException_0
0x18001a20c  mov     r8, rbx; Size
0x18001a20f  xor     edx, edx; Val
0x18001a211  mov     rcx, rsi; void *
0x18001a214  call    memset_0
0x18001a219  mov     rbx, [rsp+1D0h+var_180]
0x18001a21e  xor     r15d, r15d
0x18001a221  lea     r14, WPP_GLOBAL_Control
0x18001a228  jmp     short loc_18001A294
0x18001a22a  mov     edi, r15d
0x18001a22d  shl     rdi, 5
0x18001a231  mov     rax, [rbx+8]
0x18001a235  mov     rcx, [rax+20h]
0x18001a239  movups  xmm0, xmmword ptr [rcx]
0x18001a23c  movdqu  xmmword ptr [rdi+rsi], xmm0
0x18001a241  mov     rax, cs:WPP_GLOBAL_Control
0x18001a248  cmp     rax, r14
0x18001a24b  jz      short loc_18001A28D
0x18001a24d  cmp     byte ptr [rax+19h], 4
0x18001a251  jb      short loc_18001A28D
0x18001a253  test    byte ptr [rax+1Ch], 4
0x18001a257  jz      short loc_18001A28D
0x18001a259  movzx   edx, byte ptr [rdi+rsi]
0x18001a25d  lea     rcx, aAllowedEapType; "Allowed EAP type: %d"
0x18001a264  call    WppDbgPrint
0x18001a269  movzx   eax, byte ptr [rdi+rsi]
0x18001a26d  mov     edx, 11h
0x18001a272  mov     [rsp+1D0h+var_1B0], eax
0x18001a276  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001a27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a284  mov     rcx, [rcx+10h]
0x18001a288  call    WPP_SF_sd
0x18001a28d  add     rbx, 10h
0x18001a291  inc     r15d
0x18001a294  cmp     rbx, [rsp+1D0h+var_178]
0x18001a299  jnz     short loc_18001A22A
0x18001a29b  lea     rax, [rbp+0D0h+var_C8]
0x18001a29f  mov     [rbp+0D0h+var_E0], rax
0x18001a2a3  lea     rax, [rbp+0D0h+var_C8]
0x18001a2a7  mov     [rbp+0D0h+var_D8], rax
0x18001a2ab  mov     [rbp+0D0h+var_D0], 8
0x18001a2b2  mov     [rbp+0D0h+var_CC], 0
0x18001a2b6  mov     [rsp+1D0h+var_1A0], 1FA2h
0x18001a2be  lea     r9, [rsp+1D0h+var_1A0]; unsigned int *
0x18001a2c3  mov     r8d, 1; unsigned int
0x18001a2c9  mov     rdx, [r13+8]; struct IAttributesRaw *
0x18001a2cd  lea     rcx, [rbp+0D0h+var_E0]; this
0x18001a2d1  call    ?load@IASAttributeVector@IASTL@@QEAAKPEAUIAttributesRaw@@KPEAK@Z; IASTL::IASAttributeVector::load(IAttributesRaw *,ulong,ulong *)
0x18001a2d6  test    eax, eax
0x18001a2d8  jz      loc_18001A3EE
0x18001a2de  mov     rdi, [rbp+0D0h+var_E0]
0x18001a2e2  cmp     rdi, [rbp+0D0h+var_D8]
0x18001a2e6  jz      loc_18001A3EE
0x18001a2ec  mov     r15, [rdi+8]
0x18001a2f0  xor     ecx, ecx
0x18001a2f2  cmp     ecx, r12d
0x18001a2f5  jnb     short loc_18001A35D
0x18001a2f7  mov     ebx, ecx
0x18001a2f9  shl     rbx, 5
0x18001a2fd  mov     rdx, [r15+20h]
0x18001a301  mov     rax, [rbx+rsi]
0x18001a305  sub     rax, [rdx]
0x18001a308  jnz     short loc_18001A313
0x18001a30a  mov     rax, [rbx+rsi+8]
0x18001a30f  sub     rax, [rdx+8]
0x18001a313  test    rax, rax
0x18001a316  jz      short loc_18001A31C
0x18001a318  inc     ecx
0x18001a31a  jmp     short loc_18001A2F2
0x18001a31c  mov     eax, [r15+18h]
0x18001a320  add     eax, 0FFFFFFECh
0x18001a323  mov     [rbx+rsi+10h], eax
0x18001a327  mov     ecx, eax; cb
0x18001a329  call    cs:__imp_CoTaskMemAlloc
0x18001a32f  mov     [rbx+rsi+18h], rax
0x18001a334  test    rax, rax
0x18001a337  jz      short loc_18001A366
0x18001a339  mov     r8d, [rbx+rsi+10h]; Size
0x18001a33e  mov     rdx, [r15+20h]
0x18001a342  add     rdx, 14h; Src
0x18001a346  mov     rcx, rax; void *
0x18001a349  call    memcpy_0
0x18001a34e  cmp     byte ptr [rbx+rsi], 19h
0x18001a352  jnz     short loc_18001A35D
0x18001a354  mov     rax, [rbx+rsi+18h]
0x18001a359  and     dword ptr [rax+8], 0FFFFFFFDh
0x18001a35d  add     rdi, 10h
0x18001a361  jmp     loc_18001A2E2
0x18001a366  mov     rax, cs:WPP_GLOBAL_Control
0x18001a36d  cmp     rax, r14
0x18001a370  jz      short loc_18001A3AE
0x18001a372  cmp     byte ptr [rax+19h], 2
0x18001a376  jb      short loc_18001A3AE
0x18001a378  test    byte ptr [rax+1Ch], 4
0x18001a37c  jz      short loc_18001A3AE
0x18001a37e  lea     rcx, aNotEnoughMemor_3; "Not enough memory to eap method config "...
0x18001a385  call    WppDbgPrint
0x18001a38a  mov     edx, 12h
0x18001a38f  lea     r9, aNpssvc; "NPSSVC"
0x18001a396  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001a39d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3a4  mov     rcx, [rcx+10h]
0x18001a3a8  call    WPP_SF_s
0x18001a3ad  nop
0x18001a3ae  lea     rax, aBadAllocation; "bad allocation"
0x18001a3b5  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x18001a3ba  mov     r8d, 1
0x18001a3c0  lea     rdx, [rsp+1D0h+var_1A0]
0x18001a3c5  lea     rcx, [rsp+1D0h+pExceptionObject]
0x18001a3ca  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18001a3d0  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001a3d7  mov     [rsp+1D0h+pExceptionObject], rax
0x18001a3dc  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a3e3  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x18001a3e8  call    _CxxThrowException_0
0x18001a3ee  lea     rcx, [rbp+0D0h+var_E0]; this
0x18001a3f2  call    ??1?$IASAttributeVectorWithBuffer@$09@IASTL@@QEAA@XZ; IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>(void)
0x18001a3f7  nop
0x18001a3f8  lea     rcx, [rsp+1D0h+var_180]; this
0x18001a3fd  call    ??1?$IASAttributeVectorWithBuffer@$09@IASTL@@QEAA@XZ; IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>(void)
0x18001a402  mov     rcx, [rbp+0D0h+var_40]
0x18001a409  xor     rcx, rsp; StackCookie
0x18001a40c  call    __security_check_cookie
0x18001a411  mov     rbx, [rsp+1D0h+arg_10]
0x18001a419  add     rsp, 1A0h
0x18001a420  pop     r15
0x18001a422  pop     r14
0x18001a424  pop     r13
0x18001a426  pop     r12
0x18001a428  pop     rdi
0x18001a429  pop     rsi
0x18001a42a  pop     rbp
0x18001a42b  retn
```
