# CMVEngine::InitializeProvisioningSession(void)

- ea: `0x180016f5c`
- end: `0x1800171d3`
- name: `?InitializeProvisioningSession@CMVEngine@@AEAAJXZ`
- size: `631`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018f74`
- `0x18001a6fc`
- `0x18001b700`
- `0x1800203a0`

## callees

- `0x1800010c8`
- `0x1800026c8`
- `0x1800071b0`
- `0x1800098dc`
- `0x180009b84`
- `0x18000a978`
- `0x180016f5c`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180017189`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800171b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017189`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800171b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016fe3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016fe3`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CMVEngine::InitializeProvisioningSession(CMVEngine *this)
{
  _QWORD *v2; // rdi
  HRESULT Instance; // esi
  __int64 v4; // rdx
  bool v6; // dl
  __int64 v7; // rax
  TraceLoggingCorrelationVector *v8; // rax
  void *v9; // rcx
  struct TraceLoggingCorrelationVector *v10; // rax
  void *v11; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  _BYTE v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  TraceLoggingCorrelationVector *v14; // [rsp+38h] [rbp-C8h]
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  char *v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+68h] [rbp-98h]
  int v18; // [rsp+6Ch] [rbp-94h]
  char Source[144]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v2 = (_QWORD *)((char *)this + 192);
  if ( *((_QWORD *)this + 24) )
  {
    if ( (unsigned int)dword_18005A000 > 4 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004F992, 0, 0, 2, v15);
    return 0;
  }
  Instance = CoCreateInstance(
               &GUID_e7a8b38f_ae80_4753_b520_433d402e6379,
               0,
               1u,
               &GUID_4ebf49ca_8a92_4057_93ee_237fc110897d,
               (LPVOID *)this + 24);
  if ( Instance < 0 )
  {
    v4 = 3556;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return (unsigned int)Instance;
  }
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004EFE2, 0, 0, 2, v15);
  v13[0] = 0;
  Instance = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v2 + 40LL))(*v2, v13);
  if ( Instance < 0 )
  {
    v4 = 3564;
    goto LABEL_6;
  }
  if ( !v13[0] )
  {
    if ( (unsigned int)dword_18005A000 > 4 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, qword_18004F128, 0, 0, 2, v15);
    Instance = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 32LL))(*v2);
    if ( Instance < 0 )
    {
      v4 = 3571;
      goto LABEL_6;
    }
  }
  (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v2 + 48LL))(*v2, 129, Source);
  if ( (unsigned __int8)TraceLoggingCorrelationVector::ValidateImpl(Source, 0) )
  {
    v10 = TraceLoggingCorrelationVector::Set(Source, v6);
    v11 = (void *)*((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = v10;
    if ( v11 )
      operator delete(v11);
    return 0;
  }
  if ( (unsigned int)dword_18005A000 > 4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( Source[v7] );
    v16 = Source;
    v17 = v7 + 1;
    v18 = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &byte_18004EBC7, 0, 0, 3, v15);
  }
  v8 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v8;
  if ( v8 )
    v8 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
  v9 = (void *)*((_QWORD *)this + 25);
  *((_QWORD *)this + 25) = v8;
  if ( v9 )
    operator delete(v9);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180016f5c  push    rbp
0x180016f5e  push    rbx
0x180016f5f  push    rsi
0x180016f60  push    rdi
0x180016f61  lea     rbp, [rsp-18h]
0x180016f66  sub     rsp, 118h
0x180016f6d  mov     rax, cs:__security_cookie
0x180016f74  xor     rax, rsp
0x180016f77  mov     [rbp+30h+var_30], rax
0x180016f7b  mov     rbx, rcx
0x180016f7e  lea     rdi, [rcx+0C0h]
0x180016f85  cmp     qword ptr [rdi], 0
0x180016f89  jz      short loc_180016FCA
0x180016f8b  mov     eax, cs:dword_18005A000
0x180016f91  cmp     eax, 4
0x180016f94  jbe     loc_1800171B9
0x180016f9a  lea     rax, [rsp+130h+var_F0]
0x180016f9f  mov     [rsp+130h+var_108], rax
0x180016fa4  mov     dword ptr [rsp+130h+ppv], 2
0x180016fac  xor     r9d, r9d
0x180016faf  xor     r8d, r8d
0x180016fb2  lea     rdx, word_18004F992
0x180016fb9  lea     rcx, dword_18005A000
0x180016fc0  call    _tlgWriteTransfer_EventWriteTransfer
0x180016fc5  jmp     loc_1800171B9
0x180016fca  mov     [rsp+130h+ppv], rdi; int
0x180016fcf  lea     r9, _GUID_4ebf49ca_8a92_4057_93ee_237fc110897d; riid
0x180016fd6  xor     edx, edx; pUnkOuter
0x180016fd8  lea     r8d, [rdx+1]; dwClsContext
0x180016fdc  lea     rcx, _GUID_e7a8b38f_ae80_4753_b520_433d402e6379; rclsid
0x180016fe3  call    cs:__imp_CoCreateInstance
0x180016fe9  mov     esi, eax
0x180016feb  test    eax, eax
0x180016fed  jns     short loc_18001700E
0x180016fef  mov     edx, 0DE4h; void *
0x180016ff4  mov     rcx, [rbp+38h]; this
0x180016ff8  mov     r9d, esi; char *
0x180016ffb  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180017002  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017007  mov     eax, esi
0x180017009  jmp     loc_1800171BB
0x18001700e  mov     eax, cs:dword_18005A000
0x180017014  cmp     eax, 4
0x180017017  jbe     short loc_180017044
0x180017019  lea     rax, [rsp+130h+var_F0]
0x18001701e  mov     [rsp+130h+var_108], rax
0x180017023  mov     dword ptr [rsp+130h+ppv], 2
0x18001702b  xor     r9d, r9d
0x18001702e  xor     r8d, r8d
0x180017031  lea     rdx, word_18004EFE2
0x180017038  lea     rcx, dword_18005A000
0x18001703f  call    _tlgWriteTransfer_EventWriteTransfer
0x180017044  mov     [rsp+130h+var_100], 0
0x180017049  mov     rcx, [rdi]
0x18001704c  mov     rax, [rcx]
0x18001704f  lea     rdx, [rsp+130h+var_100]
0x180017054  mov     rax, [rax+28h]
0x180017058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001705d  mov     esi, eax
0x18001705f  test    eax, eax
0x180017061  jns     short loc_18001706A
0x180017063  mov     edx, 0DECh
0x180017068  jmp     short loc_180016FF4
0x18001706a  cmp     [rsp+130h+var_100], 0
0x18001706f  jnz     short loc_1800170C6
0x180017071  mov     eax, cs:dword_18005A000
0x180017077  cmp     eax, 4
0x18001707a  jbe     short loc_1800170A7
0x18001707c  lea     rax, [rsp+130h+var_F0]
0x180017081  mov     [rsp+130h+var_108], rax
0x180017086  mov     dword ptr [rsp+130h+ppv], 2
0x18001708e  xor     r9d, r9d
0x180017091  xor     r8d, r8d
0x180017094  lea     rdx, qword_18004F128
0x18001709b  lea     rcx, dword_18005A000
0x1800170a2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800170a7  mov     rcx, [rdi]
0x1800170aa  mov     rax, [rcx]
0x1800170ad  mov     rax, [rax+20h]
0x1800170b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b6  mov     esi, eax
0x1800170b8  test    eax, eax
0x1800170ba  jns     short loc_1800170C6
0x1800170bc  mov     edx, 0DF3h
0x1800170c1  jmp     loc_180016FF4
0x1800170c6  mov     rcx, [rdi]
0x1800170c9  mov     rax, [rcx]
0x1800170cc  lea     r8, [rsp+130h+Source]
0x1800170d1  mov     edx, 81h
0x1800170d6  mov     rax, [rax+30h]
0x1800170da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170df  xor     edx, edx
0x1800170e1  lea     rcx, [rsp+130h+Source]
0x1800170e6  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x1800170eb  test    al, al
0x1800170ed  jnz     loc_180017196
0x1800170f3  mov     eax, cs:dword_18005A000
0x1800170f9  cmp     eax, 4
0x1800170fc  jbe     short loc_180017153
0x1800170fe  lea     rcx, [rsp+130h+Source]
0x180017103  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017107  inc     rax
0x18001710a  cmp     byte ptr [rcx+rax], 0
0x18001710e  jnz     short loc_180017107
0x180017110  lea     rcx, [rsp+130h+Source]
0x180017115  mov     [rsp+130h+var_D0], rcx
0x18001711a  inc     eax
0x18001711c  mov     [rsp+130h+var_C8], eax
0x180017120  mov     [rsp+130h+var_C4], 0
0x180017128  lea     rax, [rsp+130h+var_F0]
0x18001712d  mov     [rsp+130h+var_108], rax
0x180017132  mov     dword ptr [rsp+130h+ppv], 3
0x18001713a  xor     r9d, r9d
0x18001713d  xor     r8d, r8d
0x180017140  lea     rdx, byte_18004EBC7
0x180017147  lea     rcx, dword_18005A000
0x18001714e  call    _tlgWriteTransfer_EventWriteTransfer
0x180017153  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001715a  mov     ecx, 90h; unsigned __int64
0x18001715f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017164  mov     [rsp+130h+var_F8], rax
0x180017169  test    rax, rax
0x18001716c  jz      short loc_180017176
0x18001716e  mov     rcx, rax; this
0x180017171  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180017176  mov     rcx, [rbx+0C8h]
0x18001717d  mov     [rbx+0C8h], rax
0x180017184  test    rcx, rcx
0x180017187  jz      short loc_18001718F
0x180017189  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001718f  mov     eax, 80004005h
0x180017194  jmp     short loc_1800171BB
0x180017196  lea     rcx, [rsp+130h+Source]; Source
0x18001719b  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x1800171a0  mov     rcx, [rbx+0C8h]
0x1800171a7  mov     [rbx+0C8h], rax
0x1800171ae  test    rcx, rcx
0x1800171b1  jz      short loc_1800171B9
0x1800171b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800171b9  xor     eax, eax
0x1800171bb  mov     rcx, [rbp+30h+var_30]
0x1800171bf  xor     rcx, rsp; StackCookie
0x1800171c2  call    __security_check_cookie
0x1800171c7  add     rsp, 118h
0x1800171ce  pop     rdi
0x1800171cf  pop     rsi
0x1800171d0  pop     rbx
0x1800171d1  pop     rbp
0x1800171d2  retn
```
