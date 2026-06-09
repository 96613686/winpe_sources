# RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::ProcessSerializedCall(void const *,ulong,ulong,void * *,ulong *)

- ea: `0x180054b14`
- end: `0x180054d24`
- name: `?ProcessSerializedCall@?$Server@U_NtlmCredIsoRemoteInput@@U_NtlmCredIsoRemoteOutput@@VNtlmCredIsoRemoteServer@@$1?PNtlmCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PNtlmCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PNtlmCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@QEAAJPEBXKKPEAPEAXPEAK@Z`
- size: `528`
- prototype: `__int64 __fastcall(_QWORD *, char *, unsigned int, unsigned int, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180054a70`

## callees

- `0x180030844`
- `0x1800533e4`
- `0x180054894`
- `0x1800549d0`
- `0x180054a24`
- `0x180054b14`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054c31`
- `RPCRT4!I_RpcMapWin32Status` at `0x180054b9e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180054bfd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180054c91`
- `RPCRT4!I_RpcMapWin32Status` at `0x180054b9e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180054bfd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180054c91`
- `RPCRT4!MesBufferHandleReset` at `0x180054c89`
- `RPCRT4!MesBufferHandleReset` at `0x180054c89`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180054bf5`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180054bf5`
- `RPCRT4!MesHandleFree` at `0x180054cc3`
- `RPCRT4!MesHandleFree` at `0x180054cc3`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180054b96`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180054b96`

## pseudocode

```c
__int64 __fastcall RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&void PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&unsigned __int64 PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&void PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::ProcessSerializedCall(
        _QWORD *a1,
        char *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 *a5,
        unsigned int *a6)
{
  __int64 v9; // rsi
  __int64 *v10; // r12
  unsigned int *v11; // r15
  RPC_STATUS v12; // eax
  __int64 v13; // rcx
  int v14; // ebx
  RPC_STATUS v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // edi
  __int64 v18; // rax
  RPC_STATUS v19; // eax
  __int64 v20; // rcx
  handle_t pHandle; // [rsp+38h] [rbp-59h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-51h] BYREF
  int *v24; // [rsp+48h] [rbp-49h] BYREF
  int *v25; // [rsp+50h] [rbp-41h] BYREF
  void (__fastcall *v26[2])(_QWORD); // [rsp+58h] [rbp-39h] BYREF
  int v27; // [rsp+68h] [rbp-29h] BYREF
  char v28[76]; // [rsp+6Ch] [rbp-25h] BYREF
  unsigned int pEncodedSize; // [rsp+100h] [rbp+6Fh] BYREF

  pEncodedSize = a4;
  pHandle = (handle_t)-1LL;
  v25 = 0;
  v27 = 0xFFFF;
  memset_0(v28, 0, 0x44u);
  v24 = &v27;
  pEncodedSize = 0;
  v9 = 0;
  pBuffer = 0;
  v26[0] = 0;
  v10 = a5;
  *a5 = 0;
  v11 = a6;
  *a6 = 0;
  v12 = MesDecodeBufferHandleCreate(a2, a3, &pHandle);
  v14 = I_RpcMapWin32Status(v12);
  if ( v14 >= 0 )
  {
    v14 = RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&void PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&unsigned __int64 PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&void PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::InputTypeDecodeWrapper(
            v13,
            pHandle,
            &v25);
    if ( v14 >= 0 )
    {
      ((void (__fastcall *)(_QWORD, int *, int *, void (__fastcall **)(_QWORD)))a1[1])(*a1, v25, v24, v26);
      *v24 = *v25;
      v15 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
      v14 = I_RpcMapWin32Status(v15);
      if ( v14 >= 0 )
      {
        v14 = RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&void PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&unsigned __int64 PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&void PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::OutputTypeAlignSizeWrapper(
                v16,
                pHandle,
                &v24,
                &pEncodedSize);
        if ( v14 >= 0 )
        {
          if ( pBuffer )
          {
            LocalFree(pBuffer);
            pBuffer = 0;
          }
          v17 = pEncodedSize + 16;
          v18 = (*(__int64 (__fastcall **)(_QWORD))(a1[2] + 40LL))(pEncodedSize + 16);
          v9 = v18;
          if ( v18 )
          {
            pBuffer = (char *)(v18 + 16);
            v19 = MesBufferHandleReset(pHandle, 1u, MES_ENCODE, &pBuffer, *v11 - 16, &pEncodedSize);
            v14 = I_RpcMapWin32Status(v19);
            if ( v14 >= 0 )
            {
              v14 = RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&void PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&unsigned __int64 PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&void PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::OutputTypeEncodeWrapper(
                      v20,
                      pHandle,
                      &v24);
              if ( v14 >= 0 )
              {
                *v11 = v17;
                *v10 = v9;
                v9 = 0;
              }
            }
          }
          else
          {
            v14 = -1073741801;
          }
        }
      }
    }
  }
  if ( pHandle != (handle_t)-1LL )
    MesHandleFree(pHandle);
  if ( v26[0] && v24 )
    v26[0](*a1);
  if ( v14 < 0 && v9 )
    (*(void (__fastcall **)(__int64))(a1[2] + 48LL))(v9);
  RemoteGuard::AutoMidlPtr<_NtlmCredIsoRemoteOutput>::~AutoMidlPtr<_NtlmCredIsoRemoteOutput>(&v25);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180054b14  mov     rax, rsp
0x180054b17  mov     [rax+8], rbx
0x180054b1b  mov     [rax+10h], rsi
0x180054b1f  mov     [rax+20h], r9d
0x180054b23  push    rbp
0x180054b24  push    rdi
0x180054b25  push    r12
0x180054b27  push    r14
0x180054b29  push    r15
0x180054b2b  lea     rbp, [rax-4Fh]
0x180054b2f  sub     rsp, 0B0h
0x180054b36  mov     ebx, r8d
0x180054b39  mov     rdi, rdx
0x180054b3c  mov     r14, rcx
0x180054b3f  mov     [rbp+47h+pHandle], 0FFFFFFFFFFFFFFFFh
0x180054b47  mov     [rbp+47h+var_88], 0
0x180054b4f  mov     [rbp+47h+var_70], 0FFFFh
0x180054b56  xor     edx, edx; Val
0x180054b58  lea     r8d, [rdx+44h]; Size
0x180054b5c  lea     rcx, [rbp+47h+var_6C]; void *
0x180054b60  call    memset_0
0x180054b65  lea     rax, [rbp+47h+var_70]
0x180054b69  mov     [rbp+47h+var_90], rax
0x180054b6d  mov     [rbp+47h+pEncodedSize], 0
0x180054b74  xor     esi, esi
0x180054b76  mov     [rbp+47h+pBuffer], rsi
0x180054b7a  mov     [rbp+47h+var_80], rsi
0x180054b7e  mov     r12, [rbp+47h+arg_20]
0x180054b82  mov     [r12], rsi
0x180054b86  mov     r15, [rbp+47h+arg_28]
0x180054b8a  mov     [r15], esi
0x180054b8d  lea     r8, [rbp+47h+pHandle]; pHandle
0x180054b91  mov     edx, ebx; BufferSize
0x180054b93  mov     rcx, rdi; Buffer
0x180054b96  call    cs:__imp_MesDecodeBufferHandleCreate
0x180054b9c  mov     ecx, eax; Status
0x180054b9e  call    cs:__imp_I_RpcMapWin32Status
0x180054ba4  mov     ebx, eax
0x180054ba6  test    eax, eax
0x180054ba8  js      loc_180054CB9
0x180054bae  lea     r8, [rbp+47h+var_88]
0x180054bb2  mov     rdx, [rbp+47h+pHandle]
0x180054bb6  call    ?InputTypeDecodeWrapper@?$Server@U_NtlmCredIsoRemoteInput@@U_NtlmCredIsoRemoteOutput@@VNtlmCredIsoRemoteServer@@$1?PNtlmCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PNtlmCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PNtlmCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@AEAAJPEAXPEAPEAU_NtlmCredIsoRemoteInput@@@Z; RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::InputTypeDecodeWrapper(void *,_NtlmCredIsoRemoteInput * *)
0x180054bbb  mov     ebx, eax
0x180054bbd  test    eax, eax
0x180054bbf  js      loc_180054CB9
0x180054bc5  lea     r9, [rbp+47h+var_80]
0x180054bc9  mov     r8, [rbp+47h+var_90]
0x180054bcd  mov     rdx, [rbp+47h+var_88]
0x180054bd1  mov     rcx, [r14]
0x180054bd4  mov     rax, [r14+8]
0x180054bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bdd  mov     rax, [rbp+47h+var_88]
0x180054be1  mov     ecx, [rax]
0x180054be3  mov     rax, [rbp+47h+var_90]
0x180054be7  mov     [rax], ecx
0x180054be9  lea     r8, [rbp+47h+pHandle]; pHandle
0x180054bed  lea     rdx, [rbp+47h+pEncodedSize]; pEncodedSize
0x180054bf1  lea     rcx, [rbp+47h+pBuffer]; pBuffer
0x180054bf5  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180054bfb  mov     ecx, eax; Status
0x180054bfd  call    cs:__imp_I_RpcMapWin32Status
0x180054c03  mov     ebx, eax
0x180054c05  test    eax, eax
0x180054c07  js      loc_180054CB9
0x180054c0d  lea     r9, [rbp+47h+pEncodedSize]
0x180054c11  lea     r8, [rbp+47h+var_90]
0x180054c15  mov     rdx, [rbp+47h+pHandle]
0x180054c19  call    ?OutputTypeAlignSizeWrapper@?$Server@U_NtlmCredIsoRemoteInput@@U_NtlmCredIsoRemoteOutput@@VNtlmCredIsoRemoteServer@@$1?PNtlmCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PNtlmCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PNtlmCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@AEAAJPEAXPEAPEAU_NtlmCredIsoRemoteOutput@@PEAK@Z; RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::OutputTypeAlignSizeWrapper(void *,_NtlmCredIsoRemoteOutput * *,ulong *)
0x180054c1e  mov     ebx, eax
0x180054c20  test    eax, eax
0x180054c22  js      loc_180054CB9
0x180054c28  mov     rcx, [rbp+47h+pBuffer]; hMem
0x180054c2c  test    rcx, rcx
0x180054c2f  jz      short loc_180054C3B
0x180054c31  call    cs:__imp_LocalFree
0x180054c37  mov     [rbp+47h+pBuffer], rsi
0x180054c3b  mov     edi, [rbp+47h+pEncodedSize]
0x180054c3e  add     edi, 10h
0x180054c41  mov     rax, [r14+10h]
0x180054c45  mov     ecx, edi
0x180054c47  mov     rax, [rax+28h]
0x180054c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c50  mov     rsi, rax
0x180054c53  test    rax, rax
0x180054c56  jnz     short loc_180054C5F
0x180054c58  mov     ebx, 0C0000017h
0x180054c5d  jmp     short loc_180054CB9
0x180054c5f  add     rax, 10h
0x180054c63  mov     [rbp+47h+pBuffer], rax
0x180054c67  mov     eax, [r15]
0x180054c6a  sub     eax, 10h
0x180054c6d  lea     rcx, [rbp+47h+pEncodedSize]
0x180054c71  mov     [rsp+0D0h+var_A8], rcx; pEncodedSize
0x180054c76  mov     [rsp+0D0h+BufferSize], eax; BufferSize
0x180054c7a  lea     r9, [rbp+47h+pBuffer]; pBuffer
0x180054c7e  xor     r8d, r8d; Operation
0x180054c81  lea     edx, [r8+1]; HandleStyle
0x180054c85  mov     rcx, [rbp+47h+pHandle]; Handle
0x180054c89  call    cs:__imp_MesBufferHandleReset
0x180054c8f  mov     ecx, eax; Status
0x180054c91  call    cs:__imp_I_RpcMapWin32Status
0x180054c97  mov     ebx, eax
0x180054c99  test    eax, eax
0x180054c9b  js      short loc_180054CB9
0x180054c9d  lea     r8, [rbp+47h+var_90]
0x180054ca1  mov     rdx, [rbp+47h+pHandle]
0x180054ca5  call    ?OutputTypeEncodeWrapper@?$Server@U_NtlmCredIsoRemoteInput@@U_NtlmCredIsoRemoteOutput@@VNtlmCredIsoRemoteServer@@$1?PNtlmCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PNtlmCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PNtlmCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@AEAAJPEAXPEAPEAU_NtlmCredIsoRemoteOutput@@@Z; RemoteGuard::Server<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,NtlmCredIsoRemoteServer,&PNtlmCredIsoRemoteInput_Decode(void *,_NtlmCredIsoRemoteInput * *),&PNtlmCredIsoRemoteOutput_AlignSize(void *,_NtlmCredIsoRemoteOutput * *),&PNtlmCredIsoRemoteOutput_Encode(void *,_NtlmCredIsoRemoteOutput * *)>::OutputTypeEncodeWrapper(void *,_NtlmCredIsoRemoteOutput * *)
0x180054caa  mov     ebx, eax
0x180054cac  test    eax, eax
0x180054cae  js      short loc_180054CB9
0x180054cb0  mov     [r15], edi
0x180054cb3  mov     [r12], rsi
0x180054cb7  xor     esi, esi
0x180054cb9  mov     rcx, [rbp+47h+pHandle]; Handle
0x180054cbd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180054cc1  jz      short loc_180054CC9
0x180054cc3  call    cs:__imp_MesHandleFree
0x180054cc9  mov     rax, [rbp+47h+var_80]
0x180054ccd  test    rax, rax
0x180054cd0  jz      short loc_180054CE3
0x180054cd2  mov     rdx, [rbp+47h+var_90]
0x180054cd6  test    rdx, rdx
0x180054cd9  jz      short loc_180054CE3
0x180054cdb  mov     rcx, [r14]
0x180054cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ce3  test    ebx, ebx
0x180054ce5  jns     short loc_180054CFD
0x180054ce7  test    rsi, rsi
0x180054cea  jz      short loc_180054CFD
0x180054cec  mov     rax, [r14+10h]
0x180054cf0  mov     rcx, rsi
0x180054cf3  mov     rax, [rax+30h]
0x180054cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cfc  nop
0x180054cfd  lea     rcx, [rbp+47h+var_88]
0x180054d01  call    ??1?$AutoMidlPtr@U_NtlmCredIsoRemoteOutput@@@RemoteGuard@@QEAA@XZ; RemoteGuard::AutoMidlPtr<_NtlmCredIsoRemoteOutput>::~AutoMidlPtr<_NtlmCredIsoRemoteOutput>(void)
0x180054d06  mov     eax, ebx
0x180054d08  lea     r11, [rsp+0D0h+var_20]
0x180054d10  mov     rbx, [r11+30h]
0x180054d14  mov     rsi, [r11+38h]
0x180054d18  mov     rsp, r11
0x180054d1b  pop     r15
0x180054d1d  pop     r14
0x180054d1f  pop     r12
0x180054d21  pop     rdi
0x180054d22  pop     rbp
0x180054d23  retn
```
