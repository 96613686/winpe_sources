# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180002b0c`
- end: `0x180002dc5`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(__int64, DWORD, int, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005844`

## callees

- `0x180001578`
- `0x180002b0c`
- `0x180002dcc`
- `0x180004638`
- `0x1800068d4`
- `0x1800078c4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180002cb6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180002cb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180002b6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180002b6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002baf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b9a`

## string_xrefs

- `0x180002c06`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180002c45`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180002c73`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180002ced`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        _BYTE *a4)
{
  void *v6; // rax
  unsigned int v7; // edi
  _QWORD *v8; // rbx
  wil::details *v9; // rcx
  HANDLE Event; // r14
  void *v11; // rdi
  DWORD LastError; // r12d
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int LastErrorFailHr; // eax
  HRESULT v18; // eax
  __int64 v19; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD dwindex; // [rsp+88h] [rbp+48h] BYREF
  int v25; // [rsp+90h] [rbp+50h] BYREF
  __int64 v26; // [rsp+98h] [rbp+58h] BYREF

  v25 = a3;
  dwindex = a2;
  if ( a4 )
    *a4 = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    v7 = -2147024882;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v7,
      lpdwindex);
    return v7;
  }
  v8 = (_QWORD *)`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>'::`2'::CompletionDelegate::CompletionDelegate(v6);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v11 = (void *)v8[7];
    if ( v11 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
      SetLastError(LastError);
    }
    v8[7] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v9);
    v7 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      if ( v8 )
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      goto LABEL_19;
    }
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
    (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 64LL))(a1, v8);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v15,
      lpdwindex);
    if ( v8 )
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    return v7;
  }
  pHandles = (HANDLE)v8[7];
  dwindex = 0;
  v18 = CoWaitForMultipleHandles(8u, 0x1D4C0u, 1u, &pHandles, &dwindex);
  v7 = v18;
  if ( a4 && v18 == -2147417835 )
  {
    *a4 = 1;
    (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  }
  else
  {
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x655,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)v18,
        lpdwindexa);
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      return v7;
    }
    if ( *((_DWORD *)v8 + 12) != 1 )
    {
      v26 = 0;
      v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
             a1,
             &GUID_00000036_0000_0000_c000_000000000046,
             &v26);
      if ( (v7 & 0x80000000) == 0 )
      {
        v25 = -2147418113;
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 64LL))(v26, &v25);
        if ( (v7 & 0x80000000) == 0 )
          v7 = v25;
      }
      v19 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      return v7;
    }
    (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180002b0c  mov     [rsp-38h+arg_10], r8d
0x180002b11  mov     [rsp-38h+dwindex], edx
0x180002b15  push    rbp
0x180002b16  push    rbx
0x180002b17  push    rsi
0x180002b18  push    rdi
0x180002b19  push    r12
0x180002b1b  push    r14
0x180002b1d  push    r15
0x180002b1f  mov     rbp, rsp
0x180002b22  sub     rsp, 40h
0x180002b26  mov     rsi, r9
0x180002b29  mov     r15, rcx
0x180002b2c  test    r9, r9
0x180002b2f  jz      short loc_180002B35
0x180002b31  mov     byte ptr [r9], 0
0x180002b35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002b3c  mov     ecx, 40h ; '@'; unsigned __int64
0x180002b41  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002b46  test    rax, rax
0x180002b49  jnz     short loc_180002B55
0x180002b4b  mov     edi, 8007000Eh
0x180002b50  jmp     loc_180002C6C
0x180002b55  mov     rcx, rax
0x180002b58  call    ??0CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@QEAA@XZ; `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::CompletionDelegate(void)
0x180002b5d  mov     rbx, rax
0x180002b60  mov     r9d, 1F0003h; dwDesiredAccess
0x180002b66  xor     r8d, r8d; dwFlags
0x180002b69  xor     edx, edx; lpName
0x180002b6b  xor     ecx, ecx; lpEventAttributes
0x180002b6d  call    cs:__imp_CreateEventExW
0x180002b73  mov     r14, rax
0x180002b76  test    rax, rax
0x180002b79  jz      loc_180002C2F
0x180002b7f  call    cs:__imp_GetLastError
0x180002b85  mov     rdi, [rbx+38h]
0x180002b89  test    rdi, rdi
0x180002b8c  jz      short loc_180002BB5
0x180002b8e  call    cs:__imp_GetLastError
0x180002b94  mov     r12d, eax
0x180002b97  mov     rcx, rdi; hObject
0x180002b9a  call    cs:__imp_CloseHandle
0x180002ba0  mov     rcx, [rbp+38h]; this
0x180002ba4  test    eax, eax
0x180002ba6  jz      loc_180002DBA
0x180002bac  mov     ecx, r12d; dwErrCode
0x180002baf  call    cs:__imp_SetLastError
0x180002bb5  mov     [rbx+38h], r14
0x180002bb9  test    rbx, rbx
0x180002bbc  jz      short loc_180002BCE
0x180002bbe  mov     rax, [rbx]
0x180002bc1  mov     rcx, rbx
0x180002bc4  mov     rax, [rax+8]
0x180002bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bcd  nop
0x180002bce  test    rbx, rbx
0x180002bd1  jz      short loc_180002BE3
0x180002bd3  mov     rax, [rbx]
0x180002bd6  mov     rcx, rbx
0x180002bd9  mov     rax, [rax+10h]
0x180002bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be2  nop
0x180002be3  mov     rax, [r15]
0x180002be6  mov     rdx, rbx
0x180002be9  mov     rcx, r15
0x180002bec  mov     rax, [rax+40h]
0x180002bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf5  mov     edi, eax
0x180002bf7  test    eax, eax
0x180002bf9  jns     loc_180002C8C
0x180002bff  mov     rcx, [rbp+38h]; this
0x180002c03  mov     r9d, eax; char *
0x180002c06  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c0d  mov     edx, 649h; void *
0x180002c12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c17  nop
0x180002c18  test    rbx, rbx
0x180002c1b  jz      short loc_180002C2D
0x180002c1d  mov     rcx, [rbx]
0x180002c20  mov     rax, [rcx+10h]
0x180002c24  mov     rcx, rbx
0x180002c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2c  nop
0x180002c2d  jmp     short loc_180002C85
0x180002c2f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002c34  mov     edi, eax
0x180002c36  test    eax, eax
0x180002c38  jns     loc_180002BB9
0x180002c3e  mov     rcx, [rbp+38h]; this
0x180002c42  mov     r9d, eax; char *
0x180002c45  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c4c  mov     edx, 62Bh; void *
0x180002c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c56  nop
0x180002c57  test    rbx, rbx
0x180002c5a  jz      short loc_180002C6C
0x180002c5c  mov     rax, [rbx]
0x180002c5f  mov     rcx, rbx
0x180002c62  mov     rax, [rax+10h]
0x180002c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6b  nop
0x180002c6c  mov     rcx, [rbp+38h]; this
0x180002c70  mov     r9d, edi; char *
0x180002c73  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c7a  mov     edx, 648h; void *
0x180002c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002c84  nop
0x180002c85  mov     eax, edi
0x180002c87  jmp     loc_180002DAB
0x180002c8c  mov     rax, [rbx+38h]
0x180002c90  mov     [rbp+pHandles], rax
0x180002c94  mov     [rbp+dwindex], 0
0x180002c9b  lea     rax, [rbp+dwindex]
0x180002c9f  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x180002ca4  lea     r9, [rbp+pHandles]; pHandles
0x180002ca8  mov     edx, 1D4C0h; dwTimeout
0x180002cad  mov     ecx, 8; dwFlags
0x180002cb2  lea     r8d, [rcx-7]; cHandles
0x180002cb6  call    cs:__imp_CoWaitForMultipleHandles
0x180002cbc  mov     edi, eax
0x180002cbe  test    rsi, rsi
0x180002cc1  jz      short loc_180002CE2
0x180002cc3  cmp     eax, 80010115h
0x180002cc8  jnz     short loc_180002CE2
0x180002cca  mov     byte ptr [rsi], 1
0x180002ccd  mov     rax, [rbx]
0x180002cd0  mov     rcx, rbx
0x180002cd3  mov     rax, [rax+10h]
0x180002cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cdc  nop
0x180002cdd  jmp     loc_180002DA9
0x180002ce2  test    edi, edi
0x180002ce4  jns     short loc_180002D14
0x180002ce6  mov     rcx, [rbp+38h]; this
0x180002cea  mov     r9d, edi; char *
0x180002ced  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002cf4  mov     edx, 655h; void *
0x180002cf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002cfe  nop
0x180002cff  mov     rax, [rbx]
0x180002d02  mov     rcx, rbx
0x180002d05  mov     rax, [rax+10h]
0x180002d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d0e  nop
0x180002d0f  jmp     loc_180002C85
0x180002d14  mov     eax, [rbx+30h]
0x180002d17  cmp     eax, 1
0x180002d1a  jz      short loc_180002D99
0x180002d1c  mov     [rbp+arg_18], 0
0x180002d24  mov     rax, [r15]
0x180002d27  lea     r8, [rbp+arg_18]
0x180002d2b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180002d32  mov     rcx, r15
0x180002d35  mov     rax, [rax]
0x180002d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3d  mov     edi, eax
0x180002d3f  test    eax, eax
0x180002d41  js      short loc_180002D66
0x180002d43  mov     [rbp+arg_10], 8000FFFFh
0x180002d4a  mov     rcx, [rbp+arg_18]
0x180002d4e  mov     rax, [rcx]
0x180002d51  lea     rdx, [rbp+arg_10]
0x180002d55  mov     rax, [rax+40h]
0x180002d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d5e  mov     edi, eax
0x180002d60  test    eax, eax
0x180002d62  cmovns  edi, [rbp+arg_10]
0x180002d66  mov     rcx, [rbp+arg_18]
0x180002d6a  test    rcx, rcx
0x180002d6d  jz      short loc_180002D84
0x180002d6f  mov     [rbp+arg_18], 0
0x180002d77  mov     rax, [rcx]
0x180002d7a  mov     rax, [rax+10h]
0x180002d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d83  nop
0x180002d84  mov     rax, [rbx]
0x180002d87  mov     rcx, rbx
0x180002d8a  mov     rax, [rax+10h]
0x180002d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d93  nop
0x180002d94  jmp     loc_180002C85
0x180002d99  mov     rax, [rbx]
0x180002d9c  mov     rcx, rbx
0x180002d9f  mov     rax, [rax+10h]
0x180002da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da8  nop
0x180002da9  xor     eax, eax
0x180002dab  add     rsp, 40h
0x180002daf  pop     r15
0x180002db1  pop     r14
0x180002db3  pop     r12
0x180002db5  pop     rdi
0x180002db6  pop     rsi
0x180002db7  pop     rbx
0x180002db8  pop     rbp
0x180002db9  retn
0x180002dba  mov     edx, 0A0Bh; void *
0x180002dbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
