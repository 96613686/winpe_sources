# _lambda_dcbe6b748b466fb1e89a621af059244f_::operator()

- ea: `0x18002cc80`
- end: `0x18002cef9`
- name: `_lambda_dcbe6b748b466fb1e89a621af059244f_::operator()`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18002cab8`

## callees

- `0x180001b94`
- `0x18000270c`
- `0x180002a94`
- `0x180011b9c`
- `0x1800120b8`
- `0x18002424c`
- `0x1800246b4`
- `0x18002cad8`
- `0x18002cc80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cebf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002cd37`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002cd37`

## string_xrefs

- `0x18002cee7`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingnvramdatareader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall lambda_dcbe6b748b466fb1e89a621af059244f_::operator()(__int64 **a1)
{
  __int64 *v2; // rax
  __int64 v3; // rcx
  int v4; // edi
  char v5; // r13
  int *v6; // rax
  unsigned __int16 v7; // r15
  unsigned __int16 *v8; // r14
  signed int LastError; // eax
  const struct std::nothrow_t *v10; // rdx
  int v11; // r8d
  signed int *v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 *v14; // r15
  unsigned __int64 v15; // rcx
  __int64 v16; // r12
  unsigned __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 *v19; // r8
  __int64 v20; // xmm0_8
  char v21; // cl
  __int64 v22; // rax
  int result; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-50h]
  HANDLE *p_hDevice; // [rsp+50h] [rbp-20h] BYREF
  __int64 v26; // [rsp+58h] [rbp-18h] BYREF
  char v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD BytesReturned; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE hDevice; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 *v31; // [rsp+C0h] [rbp+50h]

  v2 = *a1;
  v3 = **a1;
  if ( v3 != v2[1] )
    v2[1] = v3;
  hDevice = (HANDLE)-1LL;
  p_hDevice = &hDevice;
  v4 = 0;
  v26 = 0;
  v5 = 1;
  v27 = 1;
  *(_DWORD *)a1[1] = BthDevnodeOpenInterfaceHandle(v3, 0, &v26);
  wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hDevice);
  v6 = (int *)a1[1];
  if ( *v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingnvramdatareader.cpp",
      (const char *)(unsigned int)*v6,
      lpOutBuffer);
  v7 = 4;
  while ( 1 )
  {
    v8 = (unsigned __int16 *)operator new[](25 * ((unsigned int)v7 - 1) + 27);
    v31 = v8;
    BytesReturned = 0;
    if ( DeviceIoControl(hDevice, 0x4111D0u, 0, 0, v8, 25 * (v7 - 1) + 27, &BytesReturned, 0) )
      break;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = (signed int *)a1[1];
    *v12 = LastError;
    if ( LastError != -2147024774 || *v8 <= v7 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        v5 = 0;
      v13 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = v5;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      goto LABEL_29;
    }
    v7 = *v8;
    *v12 = 0;
    operator delete(v8, v10);
    if ( *(int *)a1[1] < 0 )
      goto LABEL_30;
  }
  v14 = *a1;
  v15 = *v8;
  v16 = (*a1)[1];
  v13 = 0x8F5C28F5C28F5C29uLL * (v16 - **a1);
  if ( v15 >= v13 )
  {
    if ( v15 > v13 )
    {
      if ( v15 <= 0x8F5C28F5C28F5C29uLL * (v14[2] - *v14) )
      {
        v17 = v15 - v13;
        if ( v17 )
        {
          v18 = 25 * v17;
          memset_0((void *)(*a1)[1], 0, 25 * v17);
          v16 += v18;
        }
        v14[1] = v16;
      }
      else
      {
        std::vector<BTHLE_PREPAIRING_ENTRY>::_Resize_reallocate<std::_Value_init_tag>(*a1, *v8);
      }
    }
  }
  else
  {
    v14[1] = *v14 + 25 * v15;
  }
  if ( *v8 )
  {
    v19 = *a1;
    v13 = 0;
    do
    {
      v20 = *(_QWORD *)((char *)v8 + v13 + 18);
      v21 = *((_BYTE *)v8 + v13 + 26);
      v22 = *v19;
      *(_OWORD *)(v13 + v22) = *(_OWORD *)((char *)v8 + v13 + 2);
      *(_QWORD *)(v13 + v22 + 16) = v20;
      *(_BYTE *)(v13 + v22 + 24) = v21;
      ++v4;
      v13 += 25LL;
    }
    while ( v4 < *v8 );
  }
LABEL_29:
  operator delete(v8, (const struct std::nothrow_t *)v13);
LABEL_30:
  result = (_DWORD)hDevice - 1;
  if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hDevice);
  return result;
}

```

## disassembly

```asm
0x18002cc80  mov     [rsp-38h+arg_18], rbx
0x18002cc85  push    rbp
0x18002cc86  push    rsi
0x18002cc87  push    rdi
0x18002cc88  push    r12
0x18002cc8a  push    r13
0x18002cc8c  push    r14
0x18002cc8e  push    r15
0x18002cc90  mov     rbp, rsp
0x18002cc93  sub     rsp, 70h
0x18002cc97  mov     rsi, rcx
0x18002cc9a  mov     rax, [rcx]
0x18002cc9d  mov     rcx, [rax]
0x18002cca0  cmp     rcx, [rax+8]
0x18002cca4  jz      short loc_18002CCAA
0x18002cca6  mov     [rax+8], rcx
0x18002ccaa  or      [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x18002ccaf  lea     rax, [rbp+hDevice]
0x18002ccb3  mov     [rbp+var_20], rax
0x18002ccb7  xor     edi, edi
0x18002ccb9  mov     [rbp+var_18], rdi
0x18002ccbd  lea     r13d, [rdi+1]
0x18002ccc1  mov     [rbp+var_10], r13b
0x18002ccc5  lea     r8, [rbp+var_18]
0x18002ccc9  xor     edx, edx
0x18002cccb  call    BthDevnodeOpenInterfaceHandle
0x18002ccd0  mov     rcx, [rsi+8]
0x18002ccd4  mov     [rcx], eax
0x18002ccd6  lea     rcx, [rbp+var_20]
0x18002ccda  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002ccdf  mov     rax, [rsi+8]
0x18002cce3  mov     rcx, [rbp+38h]; this
0x18002cce7  cmp     [rax], edi
0x18002cce9  jl      loc_18002CEE4
0x18002ccef  lea     r15d, [rdi+4]
0x18002ccf3  movzx   eax, r15w
0x18002ccf7  sub     eax, r13d
0x18002ccfa  imul    ebx, eax, 19h
0x18002ccfd  add     ebx, 1Bh
0x18002cd00  mov     ecx, ebx; unsigned __int64
0x18002cd02  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002cd07  mov     r14, rax
0x18002cd0a  mov     [rbp+arg_10], rax
0x18002cd0e  mov     [rbp+BytesReturned], edi
0x18002cd11  mov     [rsp+70h+lpOverlapped], rdi; lpOverlapped
0x18002cd16  lea     rax, [rbp+BytesReturned]
0x18002cd1a  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x18002cd1f  mov     [rsp+70h+nOutBufferSize], ebx; nOutBufferSize
0x18002cd23  mov     [rsp+70h+lpOutBuffer], r14; lpOutBuffer
0x18002cd28  xor     r9d, r9d; nInBufferSize
0x18002cd2b  xor     r8d, r8d; lpInBuffer
0x18002cd2e  mov     edx, 4111D0h; dwIoControlCode
0x18002cd33  mov     rcx, [rbp+hDevice]; hDevice
0x18002cd37  call    cs:__imp_DeviceIoControl
0x18002cd3e  nop     dword ptr [rax+rax+00h]
0x18002cd43  test    eax, eax
0x18002cd45  jnz     loc_18002CDFD
0x18002cd4b  call    cs:__imp_GetLastError
0x18002cd52  nop     dword ptr [rax+rax+00h]
0x18002cd57  test    eax, eax
0x18002cd59  jle     short loc_18002CD63
0x18002cd5b  movzx   eax, ax
0x18002cd5e  or      eax, 80070000h
0x18002cd63  mov     rcx, [rsi+8]
0x18002cd67  mov     [rcx], eax
0x18002cd69  cmp     eax, 8007007Ah
0x18002cd6e  jnz     short loc_18002CD95
0x18002cd70  cmp     [r14], r15w
0x18002cd74  jbe     short loc_18002CD95
0x18002cd76  movzx   r15d, word ptr [r14]
0x18002cd7a  mov     [rcx], edi
0x18002cd7c  mov     rcx, r14; void *
0x18002cd7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cd84  mov     rax, [rsi+8]
0x18002cd88  cmp     [rax], edi
0x18002cd8a  jge     loc_18002CCF3
0x18002cd90  jmp     loc_18002CEB1
0x18002cd95  lea     rdx, WPP_GLOBAL_Control
0x18002cd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cda3  cmp     rcx, rdx
0x18002cda6  jz      short loc_18002CDAE
0x18002cda8  cmp     byte ptr [rcx+19h], 2
0x18002cdac  jnb     short loc_18002CDB1
0x18002cdae  mov     r13b, dil
0x18002cdb1  lea     rdx, WPP_RECORDER_INITIALIZED
0x18002cdb8  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18002cdbf  setnz   r8b
0x18002cdc3  test    r13b, r13b
0x18002cdc6  jnz     short loc_18002CDD1
0x18002cdc8  test    r8b, r8b
0x18002cdcb  jz      loc_18002CEA8
0x18002cdd1  mov     [rsp+70h+var_28], eax
0x18002cdd5  lea     rax, WPP_26b232c2825f3d06e75e37d988803d66_Traceguids
0x18002cddc  mov     [rsp+70h+lpOverlapped], rax
0x18002cde1  mov     word ptr [rsp+70h+lpBytesReturned], 0Bh
0x18002cde8  mov     r9, [rcx+28h]
0x18002cdec  mov     dl, r13b
0x18002cdef  mov     rcx, [rcx+10h]
0x18002cdf3  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002cdf8  jmp     loc_18002CEA8
0x18002cdfd  mov     r15, [rsi]
0x18002ce00  movzx   ecx, word ptr [r14]
0x18002ce04  mov     r12, [r15+8]
0x18002ce08  mov     rdx, r12
0x18002ce0b  sub     rdx, [r15]
0x18002ce0e  mov     r8, 8F5C28F5C28F5C29h
0x18002ce18  imul    rdx, r8
0x18002ce1c  cmp     rcx, rdx
0x18002ce1f  jnb     short loc_18002CE2E
0x18002ce21  imul    rax, rcx, 19h
0x18002ce25  add     rax, [r15]
0x18002ce28  mov     [r15+8], rax
0x18002ce2c  jmp     short loc_18002CE6A
0x18002ce2e  jbe     short loc_18002CE6A
0x18002ce30  mov     rax, [r15+10h]
0x18002ce34  sub     rax, [r15]
0x18002ce37  imul    rax, r8
0x18002ce3b  cmp     rcx, rax
0x18002ce3e  jbe     short loc_18002CE4D
0x18002ce40  mov     rdx, rcx
0x18002ce43  mov     rcx, r15
0x18002ce46  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UBTHLE_PREPAIRING_ENTRY@@V?$allocator@UBTHLE_PREPAIRING_ENTRY@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<BTHLE_PREPAIRING_ENTRY>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002ce4b  jmp     short loc_18002CE6A
0x18002ce4d  sub     rcx, rdx
0x18002ce50  jz      short loc_18002CE66
0x18002ce52  imul    rbx, rcx, 19h
0x18002ce56  mov     r8, rbx; Size
0x18002ce59  xor     edx, edx; Val
0x18002ce5b  mov     rcx, r12; void *
0x18002ce5e  call    memset_0
0x18002ce63  add     r12, rbx
0x18002ce66  mov     [r15+8], r12
0x18002ce6a  cmp     di, [r14]
0x18002ce6e  jnb     short loc_18002CEA8
0x18002ce70  mov     r8, [rsi]
0x18002ce73  mov     rdx, rdi
0x18002ce76  movups  xmm1, xmmword ptr [rdx+r14+2]
0x18002ce7c  movsd   xmm0, qword ptr [rdx+r14+12h]
0x18002ce83  mov     cl, [rdx+r14+1Ah]
0x18002ce88  mov     rax, [r8]
0x18002ce8b  movups  xmmword ptr [rdx+rax], xmm1
0x18002ce8f  movsd   qword ptr [rdx+rax+10h], xmm0
0x18002ce95  mov     [rdx+rax+18h], cl
0x18002ce99  add     edi, r13d
0x18002ce9c  lea     rdx, [rdx+19h]; struct std::nothrow_t *
0x18002cea0  movzx   eax, word ptr [r14]
0x18002cea4  cmp     edi, eax
0x18002cea6  jl      short loc_18002CE76
0x18002cea8  mov     rcx, r14; void *
0x18002ceab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ceb0  nop
0x18002ceb1  mov     rcx, [rbp+hDevice]; hObject
0x18002ceb5  lea     rax, [rcx-1]
0x18002ceb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002cebd  ja      short loc_18002CECB
0x18002cebf  call    cs:__imp_CloseHandle
0x18002cec6  nop     dword ptr [rax+rax+00h]
0x18002cecb  mov     rbx, [rsp+70h+arg_18]
0x18002ced3  add     rsp, 70h
0x18002ced7  pop     r15
0x18002ced9  pop     r14
0x18002cedb  pop     r13
0x18002cedd  pop     r12
0x18002cedf  pop     rdi
0x18002cee0  pop     rsi
0x18002cee1  pop     rbp
0x18002cee2  retn
0x18002cee4  mov     r9d, [rax]; char *
0x18002cee7  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002ceee  mov     edx, 1Ah; void *
0x18002cef3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
