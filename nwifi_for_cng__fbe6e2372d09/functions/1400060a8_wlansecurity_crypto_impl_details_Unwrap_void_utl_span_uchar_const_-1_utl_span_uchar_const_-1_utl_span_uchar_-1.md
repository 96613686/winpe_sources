# wlansecurity::crypto::impl::details::Unwrap(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x1400060a8`
- end: `0x140006401`
- name: `?Unwrap@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z`
- size: `857`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023f50`

## callees

- `0x14000599c`
- `0x1400060a8`
- `0x14000ccb4`
- `0x140020cd0`
- `0x140020d30`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006298`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400062f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000631f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000635f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006298`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400062f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000631f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000635f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006375`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006375`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063f0`
- `ksecdd!BCryptDecrypt` at `0x140006222`
- `ksecdd!BCryptDecrypt` at `0x140006222`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14000615e`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14000615e`
- `ksecdd!BCryptDestroyKey` at `0x14000638b`
- `ksecdd!BCryptDestroyKey` at `0x1400063c0`

## pseudocode

```c
__int64 __fastcall wlansecurity::crypto::impl::details::Unwrap(
        BCRYPT_ALG_HANDLE hAlgorithm,
        const struct std::nothrow_t *a2,
        unsigned __int64 **a3,
        __int64 a4)
{
  unsigned __int64 v4; // r15
  PNPAGED_LOOKASIDE_LIST *v9; // rax
  PNPAGED_LOOKASIDE_LIST *v10; // rbx
  unsigned __int64 *v11; // rdx
  size_t v12; // r15
  __int64 v13; // rdi
  NTSTATUS v14; // esi
  size_t v15; // r15
  int v16; // r14d
  int i; // esi
  __int64 v18; // r13
  int v19; // ecx
  NTSTATUS v20; // edi
  UCHAR *pbSecret; // [rsp+20h] [rbp-89h]
  ULONG cbSecret; // [rsp+28h] [rbp-81h]
  BCRYPT_KEY_HANDLE hKey[2]; // [rsp+50h] [rbp-59h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-49h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-39h] BYREF
  NTSTATUS (__stdcall *v27)(BCRYPT_KEY_HANDLE); // [rsp+78h] [rbp-31h] BYREF
  BCRYPT_KEY_HANDLE *v28; // [rsp+80h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+88h] [rbp-21h] BYREF
  char v30; // [rsp+90h] [rbp-19h]
  UCHAR pbOutput[16]; // [rsp+A0h] [rbp-9h] BYREF

  v4 = (unsigned __int64)a3[1];
  v9 = (PNPAGED_LOOKASIDE_LIST *)operator new(v4, a2);
  v10 = v9;
  if ( !v9 )
    return 3221225495LL;
  v11 = *a3;
  v12 = v4 - 8;
  *(_OWORD *)pbOutput = 0;
  v13 = *v11;
  Buf1 = *v11;
  memmove(v9, v11 + 1, v12);
  v28 = hKey;
  cbSecret = *((_DWORD *)a2 + 2);
  pbSecret = *(UCHAR **)a2;
  hKey[0] = 0;
  phKey = 0;
  v30 = 1;
  v14 = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v28);
  if ( v14 < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(hKey);
    if ( *(v10 - 2) )
      ExFreeToNPagedLookasideList(*(v10 - 2), v10 - 2);
    else
      ExFreePoolWithTag(v10 - 2, *((_DWORD *)v10 - 2));
    return (unsigned int)v14;
  }
  else
  {
    v15 = v12 >> 3;
    v16 = 5;
LABEL_4:
    if ( v16 < 0 )
    {
      if ( !memcmp(&Buf1, qword_1400A1B40, 8u) )
      {
        memmove(*(void **)a4, v10, *(_QWORD *)(a4 + 8));
        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(hKey);
        if ( *(v10 - 2) )
          ExFreeToNPagedLookasideList(*(v10 - 2), v10 - 2);
        else
          ExFreePoolWithTag(v10 - 2, *((_DWORD *)v10 - 2));
        return 0;
      }
      else
      {
        if ( hKey[0] )
        {
          *(BCRYPT_KEY_HANDLE *)&Buf1 = hKey[0];
          v27 = BCryptDestroyKey;
          wistd::invoke<long (*)(void *),void * &>(&v27, &Buf1);
        }
        if ( *(v10 - 2) )
          ExFreeToNPagedLookasideList(*(v10 - 2), v10 - 2);
        else
          ExFreePoolWithTag(v10 - 2, *((_DWORD *)v10 - 2));
        return 3221226123LL;
      }
    }
    else
    {
      for ( i = v15 - 1; ; --i )
      {
        if ( i < 0 )
        {
          --v16;
          goto LABEL_4;
        }
        v18 = i;
        *((_QWORD *)&Buf1 + 1) = v10[v18];
        v19 = i + v15 * v16 + 1;
        *(_OWORD *)pbOutput = Buf1;
        pbOutput[6] = ((unsigned __int16)(i + v15 * v16 + 1) >> 8) ^ BYTE6(Buf1);
        pbOutput[4] = HIBYTE(v19) ^ BYTE4(Buf1);
        pbOutput[5] = BYTE2(v19) ^ BYTE5(Buf1);
        pbOutput[7] = v19 ^ HIBYTE(v13);
        pcbResult = 16;
        v20 = BCryptDecrypt(hKey[0], pbOutput, 0x10u, 0, 0, 0, pbOutput, 0x10u, &pcbResult, 0);
        if ( v20 < 0 )
          break;
        HIBYTE(v13) = pbOutput[7];
        *(_QWORD *)&Buf1 = *(_QWORD *)pbOutput;
        v10[v18] = *(PNPAGED_LOOKASIDE_LIST *)&pbOutput[8];
      }
      if ( hKey[0] )
      {
        v27 = (NTSTATUS (__stdcall *)(BCRYPT_KEY_HANDLE))hKey[0];
        *(_QWORD *)&Buf1 = BCryptDestroyKey;
        wistd::invoke<long (*)(void *),void * &>(&Buf1, &v27);
      }
      if ( *(v10 - 2) )
        ExFreeToNPagedLookasideList(*(v10 - 2), v10 - 2);
      else
        ExFreePoolWithTag(v10 - 2, *((_DWORD *)v10 - 2));
      return (unsigned int)v20;
    }
  }
}

```

## disassembly

```asm
0x1400060a8  push    rbp
0x1400060aa  push    rbx
0x1400060ab  push    rsi
0x1400060ac  push    rdi
0x1400060ad  push    r12
0x1400060af  push    r13
0x1400060b1  push    r14
0x1400060b3  push    r15
0x1400060b5  lea     rbp, [rsp-1Fh]
0x1400060ba  sub     rsp, 0C8h
0x1400060c1  mov     rax, cs:__security_cookie
0x1400060c8  xor     rax, rsp
0x1400060cb  mov     [rbp+57h+var_50], rax
0x1400060cf  mov     r15, [r8+8]
0x1400060d3  mov     r14, rcx
0x1400060d6  mov     rcx, r15; unsigned __int64
0x1400060d9  mov     r12, r9
0x1400060dc  mov     rdi, r8
0x1400060df  mov     rsi, rdx
0x1400060e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400060e7  mov     rbx, rax
0x1400060ea  test    rax, rax
0x1400060ed  jz      loc_1400062AB
0x1400060f3  mov     rdx, [rdi]
0x1400060f6  xorps   xmm1, xmm1
0x1400060f9  xorps   xmm0, xmm0
0x1400060fc  add     r15, 0FFFFFFFFFFFFFFF8h
0x140006100  movups  xmmword ptr [rbp+57h+pbOutput], xmm1
0x140006104  mov     r8, r15; Size
0x140006107  mov     rcx, rax; void *
0x14000610a  mov     rdi, [rdx]
0x14000610d  add     rdx, 8; Src
0x140006111  movups  [rbp+57h+Buf1], xmm0
0x140006115  mov     qword ptr [rbp+57h+Buf1], rdi
0x140006119  call    memmove
0x14000611e  lea     rax, [rbp+57h+hKey]
0x140006122  mov     [rsp+100h+dwFlags], 0; dwFlags
0x14000612a  mov     [rbp+57h+var_80], rax
0x14000612e  lea     rdx, [rbp+57h+phKey]; phKey
0x140006132  mov     eax, [rsi+8]
0x140006135  xor     r9d, r9d; cbKeyObject
0x140006138  mov     [rsp+100h+cbSecret], eax; cbSecret
0x14000613c  xor     r8d, r8d; pbKeyObject
0x14000613f  mov     rax, [rsi]
0x140006142  mov     rcx, r14; hAlgorithm
0x140006145  mov     [rsp+100h+pbSecret], rax; pbSecret
0x14000614a  mov     [rbp+57h+hKey], 0
0x140006152  mov     [rbp+57h+phKey], 0
0x14000615a  mov     [rbp+57h+var_70], 1
0x14000615e  call    cs:__imp_BCryptGenerateSymmetricKey
0x140006165  nop     dword ptr [rax+rax+00h]
0x14000616a  lea     rcx, [rbp+57h+var_80]
0x14000616e  mov     esi, eax
0x140006170  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x140006175  test    esi, esi
0x140006177  js      loc_140006304
0x14000617d  shr     r15, 3
0x140006181  mov     r14d, 5
0x140006187  test    r14d, r14d
0x14000618a  js      loc_140006257
0x140006190  lea     esi, [r15-1]
0x140006194  test    esi, esi
0x140006196  js      loc_14000624F
0x14000619c  mov     ecx, r14d
0x14000619f  shr     rdi, 38h
0x1400061a3  imul    ecx, r15d
0x1400061a7  lea     eax, ds:0[rsi*8]
0x1400061ae  movsxd  r13, eax
0x1400061b1  lea     rdx, [rbp+57h+pbOutput]; pbInput
0x1400061b5  xor     r9d, r9d; pPaddingInfo
0x1400061b8  mov     rax, [rbx+r13]
0x1400061bc  inc     ecx
0x1400061be  mov     qword ptr [rbp+57h+Buf1+8], rax
0x1400061c2  add     ecx, esi
0x1400061c4  movaps  xmm0, [rbp+57h+Buf1]
0x1400061c8  mov     eax, ecx
0x1400061ca  shr     eax, 8
0x1400061cd  xor     dil, cl
0x1400061d0  movdqa  xmmword ptr [rbp+57h+pbOutput], xmm0
0x1400061d5  xor     [rbp+57h+pbOutput+6], al
0x1400061d8  mov     eax, ecx
0x1400061da  shr     ecx, 18h
0x1400061dd  xor     [rbp+57h+pbOutput+4], cl
0x1400061e0  xor     ecx, ecx
0x1400061e2  mov     [rsp+100h+var_B8], ecx; dwFlags
0x1400061e6  shr     eax, 10h
0x1400061e9  xor     [rbp+57h+pbOutput+5], al
0x1400061ec  lea     rax, [rbp+57h+var_90]
0x1400061f0  mov     [rsp+100h+pcbResult], rax; pcbResult
0x1400061f5  lea     r8d, [rcx+10h]; cbInput
0x1400061f9  mov     [rsp+100h+cbOutput], 10h; cbOutput
0x140006201  lea     rax, [rbp+57h+pbOutput]
0x140006205  mov     qword ptr [rsp+100h+dwFlags], rax; pbOutput
0x14000620a  mov     [rsp+100h+cbSecret], ecx; cbIV
0x14000620e  mov     [rsp+100h+pbSecret], rcx; pbIV
0x140006213  mov     rcx, [rbp+57h+hKey]; hKey
0x140006217  mov     [rbp+57h+pbOutput+7], dil
0x14000621b  mov     [rbp+57h+var_90], 10h
0x140006222  call    cs:__imp_BCryptDecrypt
0x140006229  nop     dword ptr [rax+rax+00h]
0x14000622e  mov     edi, eax
0x140006230  test    eax, eax
0x140006232  js      loc_1400062D1
0x140006238  mov     rdi, qword ptr [rbp+57h+pbOutput]
0x14000623c  dec     esi
0x14000623e  mov     rax, qword ptr [rbp+57h+pbOutput+8]
0x140006242  mov     qword ptr [rbp+57h+Buf1], rdi
0x140006246  mov     [rbx+r13], rax
0x14000624a  jmp     loc_140006194
0x14000624f  dec     r14d
0x140006252  jmp     loc_140006187
0x140006257  mov     r8d, 8; Size
0x14000625d  lea     rdx, qword_1400A1B40; Buf2
0x140006264  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140006268  call    memcmp
0x14000626d  test    eax, eax
0x14000626f  jz      loc_14000632F
0x140006275  mov     rax, [rbp+57h+hKey]
0x140006279  test    rax, rax
0x14000627c  jnz     loc_1400063B8
0x140006282  lea     rcx, [rbx-10h]; P
0x140006286  mov     rax, [rcx]
0x140006289  test    rax, rax
0x14000628c  jz      loc_1400063D9
0x140006292  mov     rdx, rcx; Entry
0x140006295  mov     rcx, rax; Lookaside
0x140006298  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000629f  nop     dword ptr [rax+rax+00h]
0x1400062a4  mov     eax, 0C000028Bh
0x1400062a9  jmp     short loc_1400062B0
0x1400062ab  mov     eax, 0C0000017h
0x1400062b0  mov     rcx, [rbp+57h+var_50]
0x1400062b4  xor     rcx, rsp; StackCookie
0x1400062b7  call    __security_check_cookie
0x1400062bc  add     rsp, 0C8h
0x1400062c3  pop     r15
0x1400062c5  pop     r14
0x1400062c7  pop     r13
0x1400062c9  pop     r12
0x1400062cb  pop     rdi
0x1400062cc  pop     rsi
0x1400062cd  pop     rbx
0x1400062ce  pop     rbp
0x1400062cf  retn
0x1400062d1  mov     rax, [rbp+57h+hKey]
0x1400062d5  test    rax, rax
0x1400062d8  jnz     loc_140006383
0x1400062de  lea     rcx, [rbx-10h]; P
0x1400062e2  mov     rax, [rcx]
0x1400062e5  test    rax, rax
0x1400062e8  jz      loc_1400063A4
0x1400062ee  mov     rdx, rcx; Entry
0x1400062f1  mov     rcx, rax; Lookaside
0x1400062f4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400062fb  nop     dword ptr [rax+rax+00h]
0x140006300  mov     eax, edi
0x140006302  jmp     short loc_1400062B0
0x140006304  lea     rcx, [rbp+57h+hKey]
0x140006308  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000630d  lea     rcx, [rbx-10h]; P
0x140006311  mov     r8, [rcx]
0x140006314  test    r8, r8
0x140006317  jz      short loc_140006372
0x140006319  mov     rdx, rcx; Entry
0x14000631c  mov     rcx, r8; Lookaside
0x14000631f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006326  nop     dword ptr [rax+rax+00h]
0x14000632b  mov     eax, esi
0x14000632d  jmp     short loc_1400062B0
0x14000632f  mov     r8, [r12+8]; Size
0x140006334  mov     rdx, rbx; Src
0x140006337  mov     rcx, [r12]; void *
0x14000633b  call    memmove
0x140006340  lea     rcx, [rbp+57h+hKey]
0x140006344  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140006349  lea     rcx, [rbx-10h]; P
0x14000634d  mov     rax, [rcx]
0x140006350  test    rax, rax
0x140006353  jz      loc_1400063ED
0x140006359  mov     rdx, rcx; Entry
0x14000635c  mov     rcx, rax; Lookaside
0x14000635f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006366  nop     dword ptr [rax+rax+00h]
0x14000636b  xor     eax, eax
0x14000636d  jmp     loc_1400062B0
0x140006372  mov     edx, [rcx+8]; Tag
0x140006375  call    cs:__imp_ExFreePoolWithTag
0x14000637c  nop     dword ptr [rax+rax+00h]
0x140006381  jmp     short loc_14000632B
0x140006383  mov     [rbp+57h+var_88], rax
0x140006387  lea     rdx, [rbp+57h+var_88]
0x14000638b  mov     rax, cs:__imp_BCryptDestroyKey
0x140006392  lea     rcx, [rbp+57h+Buf1]
0x140006396  mov     qword ptr [rbp+57h+Buf1], rax
0x14000639a  call    ??$invoke@P6AJPEAX@ZAEAPEAX@wistd@@YAJ$$QEAP6AJPEAX@ZAEAPEAX@Z; wistd::invoke<long (*)(void *),void * &>(long (*&&)(void *),void * &)
0x14000639f  jmp     loc_1400062DE
0x1400063a4  mov     edx, [rcx+8]; Tag
0x1400063a7  call    cs:__imp_ExFreePoolWithTag
0x1400063ae  nop     dword ptr [rax+rax+00h]
0x1400063b3  jmp     loc_140006300
0x1400063b8  mov     qword ptr [rbp+57h+Buf1], rax
0x1400063bc  lea     rdx, [rbp+57h+Buf1]
0x1400063c0  mov     rax, cs:__imp_BCryptDestroyKey
0x1400063c7  lea     rcx, [rbp+57h+var_88]
0x1400063cb  mov     [rbp+57h+var_88], rax
0x1400063cf  call    ??$invoke@P6AJPEAX@ZAEAPEAX@wistd@@YAJ$$QEAP6AJPEAX@ZAEAPEAX@Z; wistd::invoke<long (*)(void *),void * &>(long (*&&)(void *),void * &)
0x1400063d4  jmp     loc_140006282
0x1400063d9  mov     edx, [rcx+8]; Tag
0x1400063dc  call    cs:__imp_ExFreePoolWithTag
0x1400063e3  nop     dword ptr [rax+rax+00h]
0x1400063e8  jmp     loc_1400062A4
0x1400063ed  mov     edx, [rcx+8]; Tag
0x1400063f0  call    cs:__imp_ExFreePoolWithTag
0x1400063f7  nop     dword ptr [rax+rax+00h]
0x1400063fc  jmp     loc_14000636B
```
