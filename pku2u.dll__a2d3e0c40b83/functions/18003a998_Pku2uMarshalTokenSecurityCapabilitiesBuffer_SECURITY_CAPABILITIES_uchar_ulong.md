# Pku2uMarshalTokenSecurityCapabilitiesBuffer(_SECURITY_CAPABILITIES *,uchar * *,ulong *)

- ea: `0x18003a998`
- end: `0x18003aafd`
- name: `?Pku2uMarshalTokenSecurityCapabilitiesBuffer@@YAJPEAU_SECURITY_CAPABILITIES@@PEAPEAEPEAK@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct _SECURITY_CAPABILITIES *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e7c`

## callees

- `0x1800057f0`
- `0x1800388c8`
- `0x180038a70`
- `0x180038aa8`
- `0x180038cd8`
- `0x18003a998`

## import_xrefs

- `RPCRT4!MesBufferHandleReset` at `0x18003aa74`
- `RPCRT4!MesBufferHandleReset` at `0x18003aa74`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18003a9e2`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18003a9e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003a9ea`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003aa7c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003a9ea`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003aa7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Pku2uMarshalTokenSecurityCapabilitiesBuffer(
        struct _SECURITY_CAPABILITIES *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  RPC_STATUS v5; // eax
  int v6; // ebx
  unsigned __int8 *v7; // rdi
  RPC_STATUS v8; // eax
  unsigned int pEncodedSize; // [rsp+30h] [rbp-40h] BYREF
  handle_t pHandle; // [rsp+38h] [rbp-38h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-30h] BYREF
  void *v13; // [rsp+48h] [rbp-28h] BYREF
  void *p_pEncodedSize; // [rsp+50h] [rbp-20h] BYREF
  handle_t *p_pHandle; // [rsp+58h] [rbp-18h]
  struct _SECURITY_CAPABILITIES **v16; // [rsp+60h] [rbp-10h]
  int *v17; // [rsp+68h] [rbp-8h]
  struct _SECURITY_CAPABILITIES *v18; // [rsp+90h] [rbp+20h] BYREF
  int v19; // [rsp+A8h] [rbp+38h] BYREF

  v18 = a1;
  v19 = 0;
  pEncodedSize = 0;
  pBuffer = 0;
  pHandle = 0;
  v5 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
  v6 = I_RpcMapWin32Status(v5);
  v19 = v6;
  if ( v6 >= 0 )
  {
    p_pEncodedSize = &pEncodedSize;
    p_pHandle = &pHandle;
    v16 = &v18;
    v17 = &v19;
    lambda_2dc99db9977d9e44bed069a90f529d96_::operator()(&p_pEncodedSize);
    v6 = v19;
    if ( v19 >= 0 )
    {
      make_unique_pku2u<char [0]>(&v13, pEncodedSize);
      v7 = (unsigned __int8 *)v13;
      if ( v13 )
      {
        pBuffer = (char *)v13;
        v8 = MesBufferHandleReset(pHandle, 1u, MES_ENCODE, &pBuffer, pEncodedSize, &pEncodedSize);
        v6 = I_RpcMapWin32Status(v8);
        v19 = v6;
        if ( v6 >= 0 )
        {
          p_pEncodedSize = &pHandle;
          p_pHandle = (handle_t *)&v18;
          v16 = (struct _SECURITY_CAPABILITIES **)&v19;
          lambda_bafa639ecd951a39cd4b103d2683520f_::operator()(&p_pEncodedSize);
          v6 = v19;
          if ( v19 >= 0 )
          {
            *a2 = v7;
            *a3 = pEncodedSize;
            v6 = 0;
          }
          else if ( v7 )
          {
            Pku2uFree(v7);
          }
        }
        else if ( v7 )
        {
          Pku2uFree(v7);
        }
      }
      else
      {
        v6 = -1073741801;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003a998  mov     [rsp-18h+arg_8], rbx
0x18003a99d  mov     [rsp-18h+arg_10], rsi
0x18003a9a2  mov     [rsp-18h+arg_0], rcx
0x18003a9a7  push    rbp
0x18003a9a8  push    rdi
0x18003a9a9  push    r14
0x18003a9ab  mov     rbp, rsp
0x18003a9ae  sub     rsp, 70h
0x18003a9b2  mov     rsi, r8
0x18003a9b5  mov     r14, rdx
0x18003a9b8  mov     [rbp+arg_18], 0
0x18003a9bf  mov     [rbp+pEncodedSize], 0
0x18003a9c6  mov     [rbp+pBuffer], 0
0x18003a9ce  mov     [rbp+pHandle], 0
0x18003a9d6  lea     r8, [rbp+pHandle]; pHandle
0x18003a9da  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x18003a9de  lea     rcx, [rbp+pBuffer]; pBuffer
0x18003a9e2  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18003a9e8  mov     ecx, eax; Status
0x18003a9ea  call    cs:__imp_I_RpcMapWin32Status
0x18003a9f0  mov     ebx, eax
0x18003a9f2  mov     [rbp+arg_18], eax
0x18003a9f5  test    eax, eax
0x18003a9f7  js      loc_18003AADD
0x18003a9fd  lea     rax, [rbp+pEncodedSize]
0x18003aa01  mov     [rbp+var_20], rax
0x18003aa05  lea     rax, [rbp+pHandle]
0x18003aa09  mov     [rbp+var_18], rax
0x18003aa0d  lea     rax, [rbp+arg_0]
0x18003aa11  mov     [rbp+var_10], rax
0x18003aa15  lea     rax, [rbp+arg_18]
0x18003aa19  mov     [rbp+var_8], rax
0x18003aa1d  lea     rcx, [rbp+var_20]
0x18003aa21  call    _lambda_2dc99db9977d9e44bed069a90f529d96___operator__
0x18003aa26  mov     ebx, [rbp+arg_18]
0x18003aa29  test    ebx, ebx
0x18003aa2b  js      loc_18003AADD
0x18003aa31  mov     edx, [rbp+pEncodedSize]
0x18003aa34  lea     rcx, [rbp+var_28]
0x18003aa38  call    ??$make_unique_pku2u@$$BY0A@D@@YA?AV?$unique_ptr@$$BY0A@DU?$function_deleter@P6AXPEAX@Z$1?Pku2uFree@@YAX0@Z@wil@@@wistd@@_K@Z; make_unique_pku2u<char [0]>(unsigned __int64)
0x18003aa3d  nop
0x18003aa3e  mov     rdi, [rbp+var_28]
0x18003aa42  test    rdi, rdi
0x18003aa45  jnz     short loc_18003AA51
0x18003aa47  mov     ebx, 0C0000017h
0x18003aa4c  jmp     loc_18003AADD
0x18003aa51  mov     [rbp+pBuffer], rdi
0x18003aa55  mov     eax, [rbp+pEncodedSize]
0x18003aa58  lea     rcx, [rbp+pEncodedSize]
0x18003aa5c  mov     [rsp+70h+var_48], rcx; pEncodedSize
0x18003aa61  mov     [rsp+70h+BufferSize], eax; BufferSize
0x18003aa65  lea     r9, [rbp+pBuffer]; pBuffer
0x18003aa69  xor     r8d, r8d; Operation
0x18003aa6c  lea     edx, [r8+1]; HandleStyle
0x18003aa70  mov     rcx, [rbp+pHandle]; Handle
0x18003aa74  call    cs:__imp_MesBufferHandleReset
0x18003aa7a  mov     ecx, eax; Status
0x18003aa7c  call    cs:__imp_I_RpcMapWin32Status
0x18003aa82  mov     ebx, eax
0x18003aa84  mov     [rbp+arg_18], eax
0x18003aa87  test    eax, eax
0x18003aa89  jns     short loc_18003AA9B
0x18003aa8b  test    rdi, rdi
0x18003aa8e  jz      short loc_18003AA99
0x18003aa90  mov     rcx, rdi; void *
0x18003aa93  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003aa98  nop
0x18003aa99  jmp     short loc_18003AADD
0x18003aa9b  lea     rax, [rbp+pHandle]
0x18003aa9f  mov     [rbp+var_20], rax
0x18003aaa3  lea     rax, [rbp+arg_0]
0x18003aaa7  mov     [rbp+var_18], rax
0x18003aaab  lea     rax, [rbp+arg_18]
0x18003aaaf  mov     [rbp+var_10], rax
0x18003aab3  lea     rcx, [rbp+var_20]
0x18003aab7  call    _lambda_bafa639ecd951a39cd4b103d2683520f___operator__
0x18003aabc  mov     ebx, [rbp+arg_18]
0x18003aabf  test    ebx, ebx
0x18003aac1  jns     short loc_18003AAD3
0x18003aac3  test    rdi, rdi
0x18003aac6  jz      short loc_18003AAD1
0x18003aac8  mov     rcx, rdi; void *
0x18003aacb  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003aad0  nop
0x18003aad1  jmp     short loc_18003AADD
0x18003aad3  mov     [r14], rdi
0x18003aad6  mov     eax, [rbp+pEncodedSize]
0x18003aad9  mov     [rsi], eax
0x18003aadb  xor     ebx, ebx
0x18003aadd  lea     rcx, [rbp+pHandle]
0x18003aae1  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?MesHandleFree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&MesHandleFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003aae6  mov     eax, ebx
0x18003aae8  lea     r11, [rsp+70h+var_s0]
0x18003aaed  mov     rbx, [r11+28h]
0x18003aaf1  mov     rsi, [r11+30h]
0x18003aaf5  mov     rsp, r11
0x18003aaf8  pop     r14
0x18003aafa  pop     rdi
0x18003aafb  pop     rbp
0x18003aafc  retn
```
