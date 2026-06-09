# Pku2uMarshalTokenSecurityAttributesBuffer(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * const,ulong,uchar * *,ulong *)

- ea: `0x18003a688`
- end: `0x18003a990`
- name: `?Pku2uMarshalTokenSecurityAttributesBuffer@@YAJQEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@KPEAPEAEPEAK@Z`
- size: `776`
- prototype: `__int64 __fastcall(struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *const, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e7c`

## callees

- `0x1800057f0`
- `0x1800388c8`
- `0x180038914`
- `0x180038a70`
- `0x180038b10`
- `0x180038bf8`
- `0x18003a688`
- `0x180044d98`

## import_xrefs

- `RPCRT4!MesBufferHandleReset` at `0x18003a89c`
- `RPCRT4!MesBufferHandleReset` at `0x18003a89c`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18003a7e1`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18003a7e1`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003a7e9`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003a8a4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003a7e9`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003a8a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Pku2uMarshalTokenSecurityAttributesBuffer(
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *const a1,
        __int64 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  _DWORD *v7; // rbx
  unsigned int i; // r9d
  __int64 v9; // r8
  RPC_STATUS v11; // eax
  int v12; // edi
  void *v13; // rdi
  RPC_STATUS v14; // eax
  int v15; // esi
  handle_t pHandle; // [rsp+38h] [rbp-29h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-21h] BYREF
  _DWORD *v18; // [rsp+48h] [rbp-19h] BYREF
  void *p_pEncodedSize; // [rsp+50h] [rbp-11h] BYREF
  handle_t *p_pHandle; // [rsp+58h] [rbp-9h]
  int *v21; // [rsp+60h] [rbp-1h]
  int *v22; // [rsp+68h] [rbp+7h]
  void *v23; // [rsp+70h] [rbp+Fh] BYREF
  void *v24; // [rsp+78h] [rbp+17h] BYREF
  _DWORD v25[2]; // [rsp+80h] [rbp+1Fh] BYREF
  _DWORD *v26; // [rsp+88h] [rbp+27h]
  unsigned int pEncodedSize; // [rsp+C8h] [rbp+67h] BYREF
  int v28; // [rsp+D0h] [rbp+6Fh] BYREF

  v28 = 0;
  make_unique_pku2u<_PAC_TOKEN_SECURITY_ATTRIBUTE [0]>(&v23, *((unsigned int *)a1 + 1));
  v7 = v23;
  if ( !v23 )
    return 3221225495LL;
  for ( i = 0; i < *((_DWORD *)a1 + 1); ++i )
  {
    v9 = *((_QWORD *)a1 + 1);
    *(_OWORD *)&v7[10 * i] = *(_OWORD *)(v9 + 40LL * i);
    if ( *(_WORD *)(v9 + 40LL * i + 18) )
      goto LABEL_20;
    v7[10 * i + 5] = *(_DWORD *)(v9 + 40LL * i + 20);
    switch ( *(_WORD *)(v9 + 40LL * i + 16) )
    {
      case 1:
        v7[10 * i + 4] = 1;
        break;
      case 2:
        v7[10 * i + 4] = 2;
        break;
      case 3:
        v7[10 * i + 4] = 3;
        break;
      case 4:
        v7[10 * i + 4] = 4;
        break;
      case 5:
        v7[10 * i + 4] = 5;
        break;
      case 6:
        v7[10 * i + 4] = 6;
        break;
      case 0x10:
        v7[10 * i + 4] = 16;
        break;
      default:
LABEL_20:
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v7 )
          Pku2uFree(v7);
        return 3221225701LL;
    }
    v7[10 * i + 6] = *(_DWORD *)(v9 + 40LL * i + 24);
    *(_QWORD *)&v7[10 * i + 8] = *(_QWORD *)(v9 + 40LL * i + 32);
  }
  v25[0] = *((_DWORD *)a1 + 1);
  v25[1] = 0;
  v26 = v7;
  v18 = v25;
  pEncodedSize = 0;
  pBuffer = 0;
  pHandle = 0;
  v11 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
  v12 = I_RpcMapWin32Status(v11);
  v28 = v12;
  if ( v12 < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
    if ( v7 )
      Pku2uFree(v7);
    return (unsigned int)v12;
  }
  p_pEncodedSize = &pEncodedSize;
  p_pHandle = &pHandle;
  v21 = (int *)&v18;
  v22 = &v28;
  lambda_2f7cb48c4355b40bac1dc582e4b090a7_::operator()(&p_pEncodedSize);
  v12 = v28;
  if ( v28 < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
    if ( v7 )
      Pku2uFree(v7);
    return (unsigned int)v12;
  }
  make_unique_pku2u<char [0]>(&v24, pEncodedSize);
  v13 = v24;
  if ( !v24 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
    if ( v7 )
      Pku2uFree(v7);
    return 3221225495LL;
  }
  pBuffer = (char *)v24;
  v14 = MesBufferHandleReset(pHandle, 1u, MES_ENCODE, &pBuffer, pEncodedSize, &pEncodedSize);
  v15 = I_RpcMapWin32Status(v14);
  v28 = v15;
  if ( v15 < 0 )
  {
    if ( v13 )
      Pku2uFree(v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
    if ( v7 )
      Pku2uFree(v7);
    return (unsigned int)v15;
  }
  p_pEncodedSize = &pHandle;
  p_pHandle = (handle_t *)&v18;
  v21 = &v28;
  lambda_b5dffb671c75d4eb536ce70e93c58d17_::operator()(&p_pEncodedSize);
  v15 = v28;
  if ( v28 < 0 )
  {
    if ( v13 )
      Pku2uFree(v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
    if ( v7 )
      Pku2uFree(v7);
    return (unsigned int)v15;
  }
  *a3 = (unsigned __int8 *)v13;
  *a4 = pEncodedSize;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
  if ( v7 )
    Pku2uFree(v7);
  return 0;
}

```

## disassembly

```asm
0x18003a688  mov     rax, rsp
0x18003a68b  mov     [rax+18h], rbx
0x18003a68f  mov     [rax+20h], rsi
0x18003a693  mov     [rax+10h], edx
0x18003a696  push    rbp
0x18003a697  push    rdi
0x18003a698  push    r12
0x18003a69a  push    r14
0x18003a69c  push    r15
0x18003a69e  lea     rbp, [rax-5Fh]
0x18003a6a2  sub     rsp, 90h
0x18003a6a9  mov     r14, r9
0x18003a6ac  mov     r15, r8
0x18003a6af  mov     rdi, rcx
0x18003a6b2  xor     r12d, r12d
0x18003a6b5  mov     [rbp+57h+arg_8], r12d
0x18003a6b9  mov     edx, [rcx+4]
0x18003a6bc  lea     rcx, [rbp+57h+var_48]
0x18003a6c0  call    ??$make_unique_pku2u@$$BY0A@U_PAC_TOKEN_SECURITY_ATTRIBUTE@@@@YA?AV?$unique_ptr@$$BY0A@U_PAC_TOKEN_SECURITY_ATTRIBUTE@@U?$function_deleter@P6AXPEAX@Z$1?Pku2uFree@@YAX0@Z@wil@@@wistd@@_K@Z; make_unique_pku2u<_PAC_TOKEN_SECURITY_ATTRIBUTE [0]>(unsigned __int64)
0x18003a6c5  nop
0x18003a6c6  mov     rbx, [rbp+57h+var_48]
0x18003a6ca  test    rbx, rbx
0x18003a6cd  jz      loc_18003A96F
0x18003a6d3  mov     r9d, r12d
0x18003a6d6  lea     esi, [r12+1]
0x18003a6db  mov     eax, [rdi+4]
0x18003a6de  cmp     r9d, eax
0x18003a6e1  jnb     loc_18003A7B5
0x18003a6e7  mov     eax, r9d
0x18003a6ea  lea     rdx, [rax+rax*4]
0x18003a6ee  mov     r8, [rdi+8]
0x18003a6f2  movups  xmm0, xmmword ptr [r8+rdx*8]
0x18003a6f7  movdqu  xmmword ptr [rbx+rdx*8], xmm0
0x18003a6fc  cmp     [r8+rdx*8+12h], r12w
0x18003a702  jnz     loc_18003A797
0x18003a708  mov     eax, [r8+rdx*8+14h]
0x18003a70d  mov     [rbx+rdx*8+14h], eax
0x18003a711  movzx   ecx, word ptr [r8+rdx*8+10h]
0x18003a717  sub     ecx, esi
0x18003a719  jz      short loc_18003A770
0x18003a71b  sub     ecx, esi
0x18003a71d  jz      short loc_18003A766
0x18003a71f  sub     ecx, esi
0x18003a721  jz      short loc_18003A75C
0x18003a723  sub     ecx, esi
0x18003a725  jz      short loc_18003A752
0x18003a727  sub     ecx, esi
0x18003a729  jz      short loc_18003A748
0x18003a72b  sub     ecx, esi
0x18003a72d  jz      short loc_18003A73E
0x18003a72f  cmp     ecx, 0Ah
0x18003a732  jnz     short loc_18003A78F
0x18003a734  mov     dword ptr [rbx+rdx*8+10h], 10h
0x18003a73c  jmp     short loc_18003A774
0x18003a73e  mov     dword ptr [rbx+rdx*8+10h], 6
0x18003a746  jmp     short loc_18003A774
0x18003a748  mov     dword ptr [rbx+rdx*8+10h], 5
0x18003a750  jmp     short loc_18003A774
0x18003a752  mov     dword ptr [rbx+rdx*8+10h], 4
0x18003a75a  jmp     short loc_18003A774
0x18003a75c  mov     dword ptr [rbx+rdx*8+10h], 3
0x18003a764  jmp     short loc_18003A774
0x18003a766  mov     dword ptr [rbx+rdx*8+10h], 2
0x18003a76e  jmp     short loc_18003A774
0x18003a770  mov     [rbx+rdx*8+10h], esi
0x18003a774  mov     eax, [r8+rdx*8+18h]
0x18003a779  mov     [rbx+rdx*8+18h], eax
0x18003a77d  mov     rax, [r8+rdx*8+20h]
0x18003a782  mov     [rbx+rdx*8+20h], rax
0x18003a787  add     r9d, esi
0x18003a78a  jmp     loc_18003A6DB
0x18003a78f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a794  nop
0x18003a795  jmp     short loc_18003A79D
0x18003a797  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a79c  nop
0x18003a79d  test    rbx, rbx
0x18003a7a0  jz      short loc_18003A7AB
0x18003a7a2  mov     rcx, rbx; void *
0x18003a7a5  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a7aa  nop
0x18003a7ab  mov     eax, 0C00000E5h
0x18003a7b0  jmp     loc_18003A974
0x18003a7b5  mov     [rbp+57h+var_38], eax
0x18003a7b8  xor     eax, eax
0x18003a7ba  mov     [rbp+57h+var_34], eax
0x18003a7bd  mov     [rbp+57h+var_30], rbx
0x18003a7c1  lea     rax, [rbp+57h+var_38]
0x18003a7c5  mov     [rbp+57h+var_70], rax
0x18003a7c9  mov     [rbp+57h+pEncodedSize], r12d
0x18003a7cd  mov     [rbp+57h+pBuffer], r12
0x18003a7d1  mov     [rbp+57h+pHandle], r12
0x18003a7d5  lea     r8, [rbp+57h+pHandle]; pHandle
0x18003a7d9  lea     rdx, [rbp+57h+pEncodedSize]; pEncodedSize
0x18003a7dd  lea     rcx, [rbp+57h+pBuffer]; pBuffer
0x18003a7e1  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18003a7e7  mov     ecx, eax; Status
0x18003a7e9  call    cs:__imp_I_RpcMapWin32Status
0x18003a7ef  mov     edi, eax
0x18003a7f1  mov     [rbp+57h+arg_8], eax
0x18003a7f4  test    eax, eax
0x18003a7f6  jns     short loc_18003A817
0x18003a7f8  lea     rcx, [rbp+57h+pHandle]
0x18003a7fc  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a801  nop
0x18003a802  test    rbx, rbx
0x18003a805  jz      short loc_18003A810
0x18003a807  mov     rcx, rbx; void *
0x18003a80a  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a80f  nop
0x18003a810  mov     eax, edi
0x18003a812  jmp     loc_18003A974
0x18003a817  lea     rax, [rbp+57h+pEncodedSize]
0x18003a81b  mov     [rbp+57h+var_68], rax
0x18003a81f  lea     rax, [rbp+57h+pHandle]
0x18003a823  mov     [rbp+57h+var_60], rax
0x18003a827  lea     rax, [rbp+57h+var_70]
0x18003a82b  mov     [rbp+57h+var_58], rax
0x18003a82f  lea     rax, [rbp+57h+arg_8]
0x18003a833  mov     [rbp+57h+var_50], rax
0x18003a837  lea     rcx, [rbp+57h+var_68]
0x18003a83b  call    _lambda_2f7cb48c4355b40bac1dc582e4b090a7___operator__
0x18003a840  mov     edi, [rbp+57h+arg_8]
0x18003a843  test    edi, edi
0x18003a845  jns     short loc_18003A861
0x18003a847  lea     rcx, [rbp+57h+pHandle]
0x18003a84b  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a850  nop
0x18003a851  test    rbx, rbx
0x18003a854  jz      short loc_18003A85F
0x18003a856  mov     rcx, rbx; void *
0x18003a859  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a85e  nop
0x18003a85f  jmp     short loc_18003A810
0x18003a861  mov     edx, [rbp+57h+pEncodedSize]
0x18003a864  lea     rcx, [rbp+57h+var_40]
0x18003a868  call    ??$make_unique_pku2u@$$BY0A@D@@YA?AV?$unique_ptr@$$BY0A@DU?$function_deleter@P6AXPEAX@Z$1?Pku2uFree@@YAX0@Z@wil@@@wistd@@_K@Z; make_unique_pku2u<char [0]>(unsigned __int64)
0x18003a86d  nop
0x18003a86e  mov     rdi, [rbp+57h+var_40]
0x18003a872  test    rdi, rdi
0x18003a875  jz      loc_18003A955
0x18003a87b  mov     [rbp+57h+pBuffer], rdi
0x18003a87f  mov     eax, [rbp+57h+pEncodedSize]
0x18003a882  lea     rcx, [rbp+57h+pEncodedSize]
0x18003a886  mov     [rsp+0B0h+var_88], rcx; pEncodedSize
0x18003a88b  mov     [rsp+0B0h+BufferSize], eax; BufferSize
0x18003a88f  lea     r9, [rbp+57h+pBuffer]; pBuffer
0x18003a893  xor     r8d, r8d; Operation
0x18003a896  mov     edx, esi; HandleStyle
0x18003a898  mov     rcx, [rbp+57h+pHandle]; Handle
0x18003a89c  call    cs:__imp_MesBufferHandleReset
0x18003a8a2  mov     ecx, eax; Status
0x18003a8a4  call    cs:__imp_I_RpcMapWin32Status
0x18003a8aa  mov     esi, eax
0x18003a8ac  mov     [rbp+57h+arg_8], eax
0x18003a8af  test    eax, eax
0x18003a8b1  jns     short loc_18003A8E0
0x18003a8b3  test    rdi, rdi
0x18003a8b6  jz      short loc_18003A8C1
0x18003a8b8  mov     rcx, rdi; void *
0x18003a8bb  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a8c0  nop
0x18003a8c1  lea     rcx, [rbp+57h+pHandle]
0x18003a8c5  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a8ca  nop
0x18003a8cb  test    rbx, rbx
0x18003a8ce  jz      short loc_18003A8D9
0x18003a8d0  mov     rcx, rbx; void *
0x18003a8d3  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a8d8  nop
0x18003a8d9  mov     eax, esi
0x18003a8db  jmp     loc_18003A974
0x18003a8e0  lea     rax, [rbp+57h+pHandle]
0x18003a8e4  mov     [rbp+57h+var_68], rax
0x18003a8e8  lea     rax, [rbp+57h+var_70]
0x18003a8ec  mov     [rbp+57h+var_60], rax
0x18003a8f0  lea     rax, [rbp+57h+arg_8]
0x18003a8f4  mov     [rbp+57h+var_58], rax
0x18003a8f8  lea     rcx, [rbp+57h+var_68]
0x18003a8fc  call    _lambda_b5dffb671c75d4eb536ce70e93c58d17___operator__
0x18003a901  mov     esi, [rbp+57h+arg_8]
0x18003a904  test    esi, esi
0x18003a906  jns     short loc_18003A930
0x18003a908  test    rdi, rdi
0x18003a90b  jz      short loc_18003A916
0x18003a90d  mov     rcx, rdi; void *
0x18003a910  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a915  nop
0x18003a916  lea     rcx, [rbp+57h+pHandle]
0x18003a91a  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a91f  nop
0x18003a920  test    rbx, rbx
0x18003a923  jz      short loc_18003A92E
0x18003a925  mov     rcx, rbx; void *
0x18003a928  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a92d  nop
0x18003a92e  jmp     short loc_18003A8D9
0x18003a930  mov     [r15], rdi
0x18003a933  mov     eax, [rbp+57h+pEncodedSize]
0x18003a936  mov     [r14], eax
0x18003a939  lea     rcx, [rbp+57h+pHandle]
0x18003a93d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a942  nop
0x18003a943  test    rbx, rbx
0x18003a946  jz      short loc_18003A951
0x18003a948  mov     rcx, rbx; void *
0x18003a94b  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a950  nop
0x18003a951  xor     eax, eax
0x18003a953  jmp     short loc_18003A974
0x18003a955  lea     rcx, [rbp+57h+pHandle]
0x18003a959  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003a95e  nop
0x18003a95f  test    rbx, rbx
0x18003a962  jz      short loc_18003A96D
0x18003a964  mov     rcx, rbx; void *
0x18003a967  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a96c  nop
0x18003a96d  jmp     short $+2
0x18003a96f  mov     eax, 0C0000017h
0x18003a974  lea     r11, [rsp+0B0h+var_20]
0x18003a97c  mov     rbx, [r11+40h]
0x18003a980  mov     rsi, [r11+48h]
0x18003a984  mov     rsp, r11
0x18003a987  pop     r15
0x18003a989  pop     r14
0x18003a98b  pop     r12
0x18003a98d  pop     rdi
0x18003a98e  pop     rbp
0x18003a98f  retn
```
