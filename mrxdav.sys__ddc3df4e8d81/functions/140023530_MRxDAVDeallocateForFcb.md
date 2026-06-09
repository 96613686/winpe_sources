# MRxDAVDeallocateForFcb

- ea: `0x140023530`
- end: `0x14002393d`
- name: `MRxDAVDeallocateForFcb`
- size: `1037`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400018d4`
- `0x1400019bc`
- `0x140003f48`
- `0x140006c00`
- `0x140023530`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002358f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023670`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400236eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002377d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023817`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002389f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002358f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023670`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400236eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002377d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023817`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002389f`
- `ntoskrnl!ExAllocatePool2` at `0x140023636`
- `ntoskrnl!ExAllocatePool2` at `0x140023636`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400235d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400235ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002390a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400235d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400235ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002390a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002371a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002371a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400235c0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400235c0`
- `ntoskrnl!ZwDeleteFile` at `0x14002374c`
- `ntoskrnl!ZwDeleteFile` at `0x14002374c`
- `rdbss!RxCreateRxContext` at `0x1400237d7`
- `rdbss!RxCreateRxContext` at `0x1400237d7`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400238cf`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x1400238cf`

## pseudocode

```c
__int64 __fastcall MRxDAVDeallocateForFcb(PRX_CONTEXT RxContext, _QWORD *a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v4; // r12d
  _QWORD *v5; // r13
  wchar_t *v7; // r15
  __int64 v8; // rdi
  unsigned int CurrentThreadId; // eax
  struct _ERESOURCE *v10; // rcx
  void *v11; // rcx
  wchar_t *Pool2; // rax
  __int64 v13; // rbx
  HANDLE v14; // rax
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rbx
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rdx
  char v22; // r13
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // rbx
  HANDLE v26; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  NTSTATUS v31; // [rsp+C0h] [rbp+50h]

  v3 = a2[17];
  v4 = 0;
  v5 = a2;
  if ( v3 )
  {
    v7 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
      WPP_SF_qS(v8, 39, (unsigned int)WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId, v3 + 668);
    }
    v10 = *(struct _ERESOURCE **)(v3 + 32);
    if ( v10 )
    {
      ExDeleteResourceLite(v10);
      ExFreePoolWithTag(*(PVOID *)(v3 + 32), 0);
      *(_QWORD *)(v3 + 32) = 0;
    }
    v11 = *(void **)(v3 + 48);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0);
      *(_QWORD *)(v3 + 48) = 0;
      *(_DWORD *)(v3 + 40) = 0;
      *(_DWORD *)(v3 + 56) = 0;
    }
    if ( *(_DWORD *)(v3 + 68) )
    {
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      Pool2 = (wchar_t *)ExAllocatePool2(258, 542, 1850103364);
      v7 = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        {
          v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v14 = PsGetCurrentThreadId();
          WPP_SF_q(v13, 40, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v14);
        }
LABEL_38:
        memset((void *)v3, 0, 0x8B8u);
        ExFreePoolWithTag((PVOID)v3, 0);
        v5[17] = 0;
        return v4;
      }
      memset(Pool2, 0, 0x21Eu);
      StringCbCopyW(v7, 0x21Eu, L"\\GLOBAL??\\");
      StringCbCopyW(v7 + 10, 0x20Au, (STRSAFE_LPCWSTR)(v3 + 668));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v16 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qS(v15, 41, (unsigned int)WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v16, (__int64)v7);
      }
      RtlInitUnicodeString(&DestinationString, v7);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Attributes = 64;
      v31 = ZwDeleteFile(&ObjectAttributes);
      if ( v31 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v18 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qLS(v17, v19, v20, v18, v31, v3 + 668);
      }
    }
    if ( !*(_DWORD *)(v3 + 8) || (v21 = v5[15]) == 0 )
    {
LABEL_36:
      if ( v7 )
        ExFreePoolWithTag(v7, 0);
      goto LABEL_38;
    }
    v22 = 0;
    if ( !RxContext )
    {
      RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(v21 + 32) + 48LL), 0);
      if ( !RxContext )
      {
        v4 = -1073741670;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        {
          v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v24 = PsGetCurrentThreadId();
          WPP_SF_qD(v23, 43, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v24, -1073741670);
        }
LABEL_35:
        v5 = a2;
        goto LABEL_36;
      }
      v22 = 1;
      RxContext->MRxContext[3] = a2;
    }
    v4 = UMRxAsyncEngOuterWrapper(
           (__int64)RxContext,
           v21,
           a3,
           2u,
           (__int64 (__fastcall *)(__int64, __int64))MRxDAVDeallocateForFcbContinuation,
           (__int64)"MRxDAVDeallocateForFcb");
    if ( v4
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v25 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v26 = PsGetCurrentThreadId();
      WPP_SF_qD(v25, 44, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v26, v4);
    }
    if ( v22 )
      RxDereferenceAndDeleteRxContext_Real(RxContext);
    goto LABEL_35;
  }
  return v4;
}

```

## disassembly

```asm
0x140023530  mov     [rsp-38h+arg_0], rbx
0x140023535  mov     [rsp-38h+arg_8], rdx
0x14002353a  push    rbp
0x14002353b  push    rsi
0x14002353c  push    rdi
0x14002353d  push    r12
0x14002353f  push    r13
0x140023541  push    r14
0x140023543  push    r15
0x140023545  mov     rbp, rsp
0x140023548  sub     rsp, 70h
0x14002354c  mov     rsi, [rdx+88h]
0x140023553  xor     r12d, r12d
0x140023556  mov     r13, rdx
0x140023559  mov     r14, rcx
0x14002355c  test    rsi, rsi
0x14002355f  jz      loc_140023921
0x140023565  xor     r15d, r15d
0x140023568  mov     rdi, cs:WPP_GLOBAL_Control
0x14002356f  lea     rax, WPP_GLOBAL_Control
0x140023576  cmp     rdi, rax
0x140023579  jz      short loc_1400235B7
0x14002357b  test    dword ptr [rdi+2Ch], 4000h
0x140023582  jz      short loc_1400235B7
0x140023584  mov     rdi, [rdi+18h]
0x140023588  lea     rbx, [rsi+29Ch]
0x14002358f  call    cs:__imp_PsGetCurrentThreadId
0x140023596  nop     dword ptr [rax+rax+00h]
0x14002359b  lea     edx, [r12+27h]
0x1400235a0  mov     [rsp+70h+var_50], rbx
0x1400235a5  mov     r9, rax
0x1400235a8  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x1400235af  mov     rcx, rdi
0x1400235b2  call    WPP_SF_qS
0x1400235b7  mov     rcx, [rsi+20h]; Resource
0x1400235bb  test    rcx, rcx
0x1400235be  jz      short loc_1400235E2
0x1400235c0  call    cs:__imp_ExDeleteResourceLite
0x1400235c7  nop     dword ptr [rax+rax+00h]
0x1400235cc  mov     rcx, [rsi+20h]; P
0x1400235d0  xor     edx, edx; Tag
0x1400235d2  call    cs:__imp_ExFreePoolWithTag
0x1400235d9  nop     dword ptr [rax+rax+00h]
0x1400235de  mov     [rsi+20h], r12
0x1400235e2  mov     rcx, [rsi+30h]; P
0x1400235e6  test    rcx, rcx
0x1400235e9  jz      short loc_140023605
0x1400235eb  xor     edx, edx; Tag
0x1400235ed  call    cs:__imp_ExFreePoolWithTag
0x1400235f4  nop     dword ptr [rax+rax+00h]
0x1400235f9  xor     eax, eax
0x1400235fb  mov     [rsi+30h], r12
0x1400235ff  mov     [rsi+28h], eax
0x140023602  mov     [rsi+38h], eax
0x140023605  cmp     [rsi+44h], r12d
0x140023609  jz      loc_1400237A7
0x14002360f  xorps   xmm0, xmm0
0x140023612  mov     ebx, 21Eh
0x140023617  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002361b  mov     edx, ebx
0x14002361d  xor     eax, eax
0x14002361f  mov     r8d, 6E465644h
0x140023625  mov     ecx, 102h
0x14002362a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14002362e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140023632  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140023636  call    cs:__imp_ExAllocatePool2
0x14002363d  nop     dword ptr [rax+rax+00h]
0x140023642  mov     r15, rax
0x140023645  test    rax, rax
0x140023648  jnz     short loc_140023697
0x14002364a  mov     rbx, cs:WPP_GLOBAL_Control
0x140023651  lea     rax, WPP_GLOBAL_Control
0x140023658  cmp     rbx, rax
0x14002365b  jz      loc_1400238F5
0x140023661  bt      dword ptr [rbx+2Ch], 0Dh
0x140023666  jnb     loc_1400238F5
0x14002366c  mov     rbx, [rbx+18h]
0x140023670  call    cs:__imp_PsGetCurrentThreadId
0x140023677  nop     dword ptr [rax+rax+00h]
0x14002367c  lea     edx, [r15+28h]
0x140023680  mov     rcx, rbx
0x140023683  mov     r9, rax
0x140023686  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x14002368d  call    WPP_SF_q
0x140023692  jmp     loc_1400238F5
0x140023697  mov     r8, rbx; Size
0x14002369a  xor     edx, edx; Val
0x14002369c  mov     rcx, r15; void *
0x14002369f  call    memset
0x1400236a4  lea     r8, aGlobal; "\\GLOBAL??\\"
0x1400236ab  mov     rdx, rbx; cbDest
0x1400236ae  mov     rcx, r15; pszDest
0x1400236b1  call    StringCbCopyW
0x1400236b6  lea     r8, [rsi+29Ch]; pszSrc
0x1400236bd  mov     edx, 20Ah; cbDest
0x1400236c2  lea     rcx, [r15+14h]; pszDest
0x1400236c6  call    StringCbCopyW
0x1400236cb  mov     rbx, cs:WPP_GLOBAL_Control
0x1400236d2  lea     rax, WPP_GLOBAL_Control
0x1400236d9  cmp     rbx, rax
0x1400236dc  jz      short loc_140023713
0x1400236de  test    dword ptr [rbx+2Ch], 4000h
0x1400236e5  jz      short loc_140023713
0x1400236e7  mov     rbx, [rbx+18h]
0x1400236eb  call    cs:__imp_PsGetCurrentThreadId
0x1400236f2  nop     dword ptr [rax+rax+00h]
0x1400236f7  mov     edx, 29h ; ')'
0x1400236fc  mov     [rsp+70h+var_50], r15
0x140023701  mov     r9, rax
0x140023704  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x14002370b  mov     rcx, rbx
0x14002370e  call    WPP_SF_qS
0x140023713  mov     rdx, r15; SourceString
0x140023716  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002371a  call    cs:__imp_RtlInitUnicodeString
0x140023721  nop     dword ptr [rax+rax+00h]
0x140023726  lea     rax, [rbp+DestinationString]
0x14002372a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140023731  xorps   xmm0, xmm0
0x140023734  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140023738  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x14002373c  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x140023740  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140023745  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14002374c  call    cs:__imp_ZwDeleteFile
0x140023753  nop     dword ptr [rax+rax+00h]
0x140023758  mov     [rbp+arg_10], eax
0x14002375b  test    eax, eax
0x14002375d  jns     short loc_1400237A7
0x14002375f  mov     rbx, cs:WPP_GLOBAL_Control
0x140023766  lea     rax, WPP_GLOBAL_Control
0x14002376d  cmp     rbx, rax
0x140023770  jz      short loc_1400237A7
0x140023772  bt      dword ptr [rbx+2Ch], 0Dh
0x140023777  jnb     short loc_1400237A7
0x140023779  mov     rbx, [rbx+18h]
0x14002377d  call    cs:__imp_PsGetCurrentThreadId
0x140023784  nop     dword ptr [rax+rax+00h]
0x140023789  mov     r9, rax
0x14002378c  mov     rcx, rbx
0x14002378f  lea     rax, [rsi+29Ch]
0x140023796  mov     [rsp+70h+var_48], rax
0x14002379b  mov     eax, [rbp+arg_10]
0x14002379e  mov     dword ptr [rsp+70h+var_50], eax
0x1400237a2  call    WPP_SF_qLS
0x1400237a7  cmp     [rsi+8], r12d
0x1400237ab  jz      loc_1400238DF
0x1400237b1  mov     rdx, [r13+78h]
0x1400237b5  test    rdx, rdx
0x1400237b8  jz      loc_1400238DF
0x1400237be  xor     r13b, r13b
0x1400237c1  test    r14, r14
0x1400237c4  jnz     loc_140023854
0x1400237ca  mov     rdx, [rdx+20h]
0x1400237ce  xor     r8d, r8d; InitialContextFlags
0x1400237d1  xor     ecx, ecx; Irp
0x1400237d3  mov     rdx, [rdx+30h]; RxDeviceObject
0x1400237d7  call    cs:__imp_RxCreateRxContext
0x1400237de  nop     dword ptr [rax+rax+00h]
0x1400237e3  mov     r14, rax
0x1400237e6  test    rax, rax
0x1400237e9  jnz     short loc_140023846
0x1400237eb  mov     r12d, 0C000009Ah
0x1400237f1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400237f8  lea     rax, WPP_GLOBAL_Control
0x1400237ff  cmp     rbx, rax
0x140023802  jz      loc_1400238DB
0x140023808  bt      dword ptr [rbx+2Ch], 0Dh
0x14002380d  jnb     loc_1400238DB
0x140023813  mov     rbx, [rbx+18h]
0x140023817  call    cs:__imp_PsGetCurrentThreadId
0x14002381e  nop     dword ptr [rax+rax+00h]
0x140023823  lea     edx, [r14+2Bh]
0x140023827  mov     dword ptr [rsp+70h+var_50], 0C000009Ah
0x14002382f  mov     r9, rax
0x140023832  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023839  mov     rcx, rbx
0x14002383c  call    WPP_SF_qD
0x140023841  jmp     loc_1400238DB
0x140023846  mov     rax, [rbp+arg_8]
0x14002384a  mov     r13b, 1
0x14002384d  mov     [r14+0D8h], rax
0x140023854  lea     rax, aMrxdavdealloca_0; "MRxDAVDeallocateForFcb"
0x14002385b  mov     r9d, 2
0x140023861  mov     [rsp+70h+var_48], rax
0x140023866  mov     rcx, r14
0x140023869  lea     rax, MRxDAVDeallocateForFcbContinuation
0x140023870  mov     [rsp+70h+var_50], rax
0x140023875  call    UMRxAsyncEngOuterWrapper
0x14002387a  mov     r12d, eax
0x14002387d  test    eax, eax
0x14002387f  jz      short loc_1400238C7
0x140023881  mov     rbx, cs:WPP_GLOBAL_Control
0x140023888  lea     rax, WPP_GLOBAL_Control
0x14002388f  cmp     rbx, rax
0x140023892  jz      short loc_1400238C7
0x140023894  bt      dword ptr [rbx+2Ch], 0Dh
0x140023899  jnb     short loc_1400238C7
0x14002389b  mov     rbx, [rbx+18h]
0x14002389f  call    cs:__imp_PsGetCurrentThreadId
0x1400238a6  nop     dword ptr [rax+rax+00h]
0x1400238ab  mov     edx, 2Ch ; ','
0x1400238b0  mov     dword ptr [rsp+70h+var_50], r12d
0x1400238b5  mov     r9, rax
0x1400238b8  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x1400238bf  mov     rcx, rbx
0x1400238c2  call    WPP_SF_qD
0x1400238c7  test    r13b, r13b
0x1400238ca  jz      short loc_1400238DB
0x1400238cc  mov     rcx, r14; RxContext
0x1400238cf  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x1400238d6  nop     dword ptr [rax+rax+00h]
0x1400238db  mov     r13, [rbp+arg_8]
0x1400238df  test    r15, r15
0x1400238e2  jz      short loc_1400238F5
0x1400238e4  xor     edx, edx; Tag
0x1400238e6  mov     rcx, r15; P
0x1400238e9  call    cs:__imp_ExFreePoolWithTag
0x1400238f0  nop     dword ptr [rax+rax+00h]
0x1400238f5  xor     edx, edx; Val
0x1400238f7  mov     r8d, 8B8h; Size
0x1400238fd  mov     rcx, rsi; void *
0x140023900  call    memset
0x140023905  xor     edx, edx; Tag
0x140023907  mov     rcx, rsi; P
0x14002390a  call    cs:__imp_ExFreePoolWithTag
0x140023911  nop     dword ptr [rax+rax+00h]
0x140023916  mov     qword ptr [r13+88h], 0
0x140023921  mov     rbx, [rsp+70h+arg_0]
0x140023929  mov     eax, r12d
0x14002392c  add     rsp, 70h
0x140023930  pop     r15
0x140023932  pop     r14
0x140023934  pop     r13
0x140023936  pop     r12
0x140023938  pop     rdi
0x140023939  pop     rsi
0x14002393a  pop     rbp
0x14002393b  retn
```
