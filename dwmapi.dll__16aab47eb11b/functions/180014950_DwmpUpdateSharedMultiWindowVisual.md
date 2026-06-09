# DwmpUpdateSharedMultiWindowVisual

- ea: `0x180014950`
- end: `0x180014ae9`
- name: `DwmpUpdateSharedMultiWindowVisual`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000352c`
- `0x18000b990`
- `0x18000d0a0`
- `0x1800117a4`
- `0x180011800`
- `0x180014950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014a1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014a1c`

## pseudocode

```c
__int64 __fastcall DwmpUpdateSharedMultiWindowVisual(
        int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        int a8)
{
  signed int v12; // edx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 i; // rdx
  __int64 j; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  DWORD CurrentProcessId; // eax
  __m128i v21; // xmm1
  __int128 *v22; // rax
  __int128 v23; // xmm0
  CApiPortClient *v24; // rcx
  int v25; // eax
  void *v27; // [rsp+28h] [rbp-61h]
  int v28[2]; // [rsp+30h] [rbp-59h] BYREF
  void **v29; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v30[2]; // [rsp+40h] [rbp-49h] BYREF
  int v31; // [rsp+50h] [rbp-39h] BYREF
  __int128 v32; // [rsp+54h] [rbp-35h]
  __int128 v33; // [rsp+64h] [rbp-25h]
  __int128 v34; // [rsp+74h] [rbp-15h]
  int v35; // [rsp+84h] [rbp-5h]

  *(_QWORD *)v28 = a6;
  v30[0] = 0;
  v29 = &CValidatedData::`vftable';
  v12 = 8 * (a3 + a5);
  v30[1] = 0;
  if ( v12 > 0 )
  {
    v13 = CValidatedData::Create((CValidatedData *)&v29, v12);
    v14 = v13;
    if ( v13 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A180, 2u, v13, 0x169u, v27);
      goto LABEL_11;
    }
    v15 = v30[0];
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
      *(_QWORD *)(v15 + 8 * i) = *(_QWORD *)(a2 + 8 * i);
    for ( j = 0; (unsigned int)j < a5; *(_QWORD *)(v15 + 8 * v19) = v18 )
    {
      v18 = *(_QWORD *)(a4 + 8 * j);
      v19 = a3 + (unsigned int)j;
      j = (unsigned int)(j + 1);
    }
  }
  v31 = 1073741905;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v21 = _mm_cvtsi32_si128(*(_DWORD *)a7);
  *(_QWORD *)((char *)&v32 + 4) = __PAIR64__(a3, CurrentProcessId);
  v22 = *(__int128 **)v28;
  LODWORD(v32) = a1;
  HIDWORD(v32) = a5;
  v28[0] = 0;
  v23 = *v22;
  v35 = a8;
  v33 = v23;
  *(float *)&v23 = (float)*(int *)(a7 + 4);
  DWORD2(v34) = _mm_cvtepi32_ps(v21).m128_u32[0];
  HIDWORD(v34) = v23;
  v25 = CApiPortClient::SendRequestValidate(v24, &v31, 0x38u, (const struct CExtraData *)&v29, v28);
  v14 = v25;
  if ( v25 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A180, 2u, v25, 0x182u, v27);
  else
    v14 = v28[0];
LABEL_11:
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>>(v30);
  return v14;
}

```

## disassembly

```asm
0x180014950  mov     [rsp-8+arg_8], rbx
0x180014955  push    rbp
0x180014956  push    rsi
0x180014957  push    rdi
0x180014958  push    r12
0x18001495a  push    r13
0x18001495c  push    r14
0x18001495e  push    r15
0x180014960  lea     rbp, [rsp-7]
0x180014965  sub     rsp, 90h
0x18001496c  mov     rax, cs:__security_cookie
0x180014973  xor     rax, rsp
0x180014976  mov     [rbp+37h+var_38], rax
0x18001497a  mov     rax, [rbp+37h+arg_28]
0x18001497e  mov     r14, rdx
0x180014981  mov     esi, [rbp+37h+arg_20]
0x180014984  mov     r15, r9
0x180014987  mov     r12, [rbp+37h+arg_30]
0x18001498b  mov     edi, r8d
0x18001498e  mov     qword ptr [rbp+37h+var_90], rax
0x180014992  mov     r13, rcx
0x180014995  lea     rax, ??_7CValidatedData@@6B@; const CValidatedData::`vftable'
0x18001499c  mov     [rbp+37h+var_80], 0
0x1800149a4  lea     edx, [r8+rsi]
0x1800149a8  mov     [rbp+37h+var_88], rax
0x1800149ac  shl     edx, 3; unsigned int
0x1800149af  mov     [rbp+37h+var_78], 0
0x1800149b7  test    edx, edx
0x1800149b9  jle     short loc_180014A01
0x1800149bb  lea     rcx, [rbp+37h+var_88]; this
0x1800149bf  call    ?Create@CValidatedData@@QEAAJI@Z; CValidatedData::Create(uint)
0x1800149c4  mov     ebx, eax
0x1800149c6  test    eax, eax
0x1800149c8  js      loc_180014A8C
0x1800149ce  mov     r9, [rbp+37h+var_80]
0x1800149d2  xor     edx, edx
0x1800149d4  test    edi, edi
0x1800149d6  jz      short loc_1800149E6
0x1800149d8  mov     rax, [r14+rdx*8]
0x1800149dc  mov     [r9+rdx*8], rax
0x1800149e0  inc     edx
0x1800149e2  cmp     edx, edi
0x1800149e4  jb      short loc_1800149D8
0x1800149e6  xor     r8d, r8d
0x1800149e9  test    esi, esi
0x1800149eb  jz      short loc_180014A01
0x1800149ed  mov     rax, [r15+r8*8]
0x1800149f1  lea     ecx, [rdi+r8]
0x1800149f5  inc     r8d
0x1800149f8  mov     [r9+rcx*8], rax
0x1800149fc  cmp     r8d, esi
0x1800149ff  jb      short loc_1800149ED
0x180014a01  xorps   xmm0, xmm0
0x180014a04  mov     [rbp+37h+var_70], 40000051h
0x180014a0b  xor     eax, eax
0x180014a0d  movups  [rbp+37h+var_6C], xmm0
0x180014a11  mov     [rbp+37h+var_3C], eax
0x180014a14  movups  [rbp+37h+var_5C], xmm0
0x180014a18  movups  [rbp+37h+var_4C], xmm0
0x180014a1c  call    cs:__imp_GetCurrentProcessId
0x180014a22  movd    xmm1, dword ptr [r12]
0x180014a28  lea     r9, [rbp+37h+var_88]; struct CExtraData *
0x180014a2c  mov     dword ptr [rbp+37h+var_6C+4], eax
0x180014a2f  lea     rdx, [rbp+37h+var_70]; void *
0x180014a33  mov     rax, qword ptr [rbp+37h+var_90]
0x180014a37  mov     r8d, 38h ; '8'; unsigned __int64
0x180014a3d  cvtdq2ps xmm1, xmm1
0x180014a40  mov     dword ptr [rbp+37h+var_6C], r13d
0x180014a44  mov     dword ptr [rbp+37h+var_6C+8], edi
0x180014a47  mov     dword ptr [rbp+37h+var_6C+0Ch], esi
0x180014a4a  mov     [rbp+37h+var_90], 0
0x180014a51  movups  xmm0, xmmword ptr [rax]
0x180014a54  mov     eax, [rbp+37h+arg_38]
0x180014a57  mov     [rbp+37h+var_3C], eax
0x180014a5a  lea     rax, [rbp+37h+var_90]
0x180014a5e  movdqu  [rbp+37h+var_5C], xmm0
0x180014a63  mov     [rsp+0C0h+var_A0], rax; int *
0x180014a68  movd    xmm0, dword ptr [r12+4]
0x180014a6f  cvtdq2ps xmm0, xmm0
0x180014a72  movss   dword ptr [rbp+37h+var_4C+8], xmm1
0x180014a77  movss   dword ptr [rbp+37h+var_4C+0Ch], xmm0
0x180014a7c  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KAEBVCExtraData@@PEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,CExtraData const &,long *)
0x180014a81  mov     ebx, eax
0x180014a83  test    eax, eax
0x180014a85  js      short loc_180014A96
0x180014a87  mov     ebx, [rbp+37h+var_90]
0x180014a8a  jmp     short loc_180014AB7
0x180014a8c  mov     dword ptr [rsp+0C0h+var_A0], 169h
0x180014a94  jmp     short loc_180014A9E
0x180014a96  mov     dword ptr [rsp+0C0h+var_A0], 182h; unsigned int
0x180014a9e  mov     r8d, 2; unsigned int
0x180014aa4  lea     rdx, qword_18001A180; int *
0x180014aab  mov     r9d, eax; int
0x180014aae  lea     ecx, [r8+2]; unsigned int
0x180014ab2  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180014ab7  lea     rcx, [rbp+37h+var_80]
0x180014abb  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCHideInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>>(void)
0x180014ac0  mov     eax, ebx
0x180014ac2  mov     rcx, [rbp+37h+var_38]
0x180014ac6  xor     rcx, rsp; StackCookie
0x180014ac9  call    __security_check_cookie
0x180014ace  mov     rbx, [rsp+0C0h+arg_8]
0x180014ad6  add     rsp, 90h
0x180014add  pop     r15
0x180014adf  pop     r14
0x180014ae1  pop     r13
0x180014ae3  pop     r12
0x180014ae5  pop     rdi
0x180014ae6  pop     rsi
0x180014ae7  pop     rbp
0x180014ae8  retn
```
