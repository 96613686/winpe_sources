# RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::ProcessSerializedCall(void const *,ulong,ulong,void * *,ulong *)

- ea: `0x1800a7074`
- end: `0x1800a728a`
- name: `?ProcessSerializedCall@?$Server@U_KerbCredIsoRemoteInput@@U_KerbCredIsoRemoteOutput@@VKerbCredIsoRemoteServer@@$1?PKerbCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PKerbCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PKerbCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@QEAAJPEBXKKPEAPEAXPEAK@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800a6fd0`

## callees

- `0x1800069a0`
- `0x1800a02d8`
- `0x1800a03a4`
- `0x1800a6f24`
- `0x1800a6f78`
- `0x1800a7074`
- `0x1800f5010`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x1800a7229`
- `RPCRT4!MesHandleFree` at `0x1800a7229`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a7102`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a7161`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a71f7`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a7102`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a7161`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800a71f7`
- `RPCRT4!MesBufferHandleReset` at `0x1800a71ef`
- `RPCRT4!MesBufferHandleReset` at `0x1800a71ef`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800a7159`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800a7159`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800a70fa`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800a70fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&void PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&unsigned __int64 PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&void PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::ProcessSerializedCall(
        _QWORD *a1,
        char *a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5,
        unsigned int *a6)
{
  __int64 v7; // rdi
  __int64 *v8; // r12
  unsigned int *v9; // r15
  RPC_STATUS v10; // eax
  __int64 v11; // rcx
  int v12; // ebx
  RPC_STATUS v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // r14d
  __int64 v16; // rax
  RPC_STATUS v17; // eax
  __int64 v18; // rcx
  handle_t pHandle; // [rsp+38h] [rbp-49h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-41h] BYREF
  int *v22; // [rsp+48h] [rbp-39h] BYREF
  int *v23; // [rsp+50h] [rbp-31h] BYREF
  void (__fastcall *v24[2])(_QWORD); // [rsp+58h] [rbp-29h] BYREF
  int v25; // [rsp+68h] [rbp-19h] BYREF
  __int128 v26; // [rsp+6Ch] [rbp-15h]
  __int128 v27; // [rsp+7Ch] [rbp-5h]
  _BYTE v28[28]; // [rsp+8Ch] [rbp+Bh] BYREF
  unsigned int pEncodedSize; // [rsp+F0h] [rbp+6Fh] BYREF

  pHandle = (handle_t)-1LL;
  v23 = 0;
  v25 = 0xFFFF;
  v26 = 0;
  v27 = 0;
  memset(v28, 0, sizeof(v28));
  v22 = &v25;
  pEncodedSize = 0;
  v7 = 0;
  pBuffer = 0;
  v24[0] = 0;
  v8 = a5;
  *a5 = 0;
  v9 = a6;
  *a6 = 0;
  v10 = MesDecodeBufferHandleCreate(a2, a3, &pHandle);
  v12 = I_RpcMapWin32Status(v10);
  if ( v12 >= 0 )
  {
    v12 = RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&void PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&unsigned __int64 PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&void PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::InputTypeDecodeWrapper(
            v11,
            pHandle,
            &v23);
    if ( v12 >= 0 )
    {
      ((void (__fastcall *)(_QWORD, int *, int *, void (__fastcall **)(_QWORD)))a1[1])(*a1, v23, v22, v24);
      *v22 = *v23;
      v13 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
      v12 = I_RpcMapWin32Status(v13);
      if ( v12 >= 0 )
      {
        v12 = RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&void PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&unsigned __int64 PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&void PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::OutputTypeAlignSizeWrapper(
                v14,
                pHandle,
                &v22,
                &pEncodedSize);
        if ( v12 >= 0 )
        {
          if ( pBuffer )
          {
            KerbFree(pBuffer);
            pBuffer = 0;
          }
          v15 = pEncodedSize + 16;
          v16 = (*(__int64 (__fastcall **)(_QWORD))(a1[2] + 40LL))(pEncodedSize + 16);
          v7 = v16;
          if ( v16 )
          {
            pBuffer = (char *)(v16 + 16);
            v17 = MesBufferHandleReset(pHandle, 1u, MES_ENCODE, &pBuffer, *v9 - 16, &pEncodedSize);
            v12 = I_RpcMapWin32Status(v17);
            if ( v12 >= 0 )
            {
              v12 = RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&void PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&unsigned __int64 PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&void PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::OutputTypeEncodeWrapper(
                      v18,
                      pHandle,
                      &v22);
              if ( v12 >= 0 )
              {
                *v9 = v15;
                *v8 = v7;
                v7 = 0;
              }
            }
          }
          else
          {
            v12 = -1073741801;
          }
        }
      }
    }
  }
  if ( pHandle != (handle_t)-1LL )
    MesHandleFree(pHandle);
  if ( v24[0] && v22 )
    v24[0](*a1);
  if ( v12 < 0 && v7 )
    (*(void (__fastcall **)(__int64))(a1[2] + 48LL))(v7);
  RemoteGuard::AutoMidlPtr<_KerbCredIsoRemoteInput>::~AutoMidlPtr<_KerbCredIsoRemoteInput>(&v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800a7074  mov     rax, rsp
0x1800a7077  mov     [rax+8], rbx
0x1800a707b  mov     [rax+10h], rsi
0x1800a707f  mov     [rax+20h], r9d
0x1800a7083  push    rbp
0x1800a7084  push    rdi
0x1800a7085  push    r12
0x1800a7087  push    r14
0x1800a7089  push    r15
0x1800a708b  lea     rbp, [rax-4Fh]
0x1800a708f  sub     rsp, 0A0h
0x1800a7096  mov     eax, r8d
0x1800a7099  mov     r9, rdx
0x1800a709c  mov     rsi, rcx
0x1800a709f  mov     [rbp+47h+pHandle], 0FFFFFFFFFFFFFFFFh
0x1800a70a7  mov     [rbp+47h+var_78], 0
0x1800a70af  mov     [rbp+47h+var_60], 0FFFFh
0x1800a70b6  xorps   xmm0, xmm0
0x1800a70b9  movups  [rbp+47h+var_5C], xmm0
0x1800a70bd  movups  [rbp+47h+var_4C], xmm0
0x1800a70c1  movups  xmmword ptr [rbp+47h+var_3C], xmm0
0x1800a70c5  movups  xmmword ptr [rbp+47h+var_3C+0Ch], xmm0
0x1800a70c9  lea     rcx, [rbp+47h+var_60]
0x1800a70cd  mov     [rbp+47h+var_80], rcx
0x1800a70d1  mov     [rbp+47h+pEncodedSize], 0
0x1800a70d8  xor     edi, edi
0x1800a70da  mov     [rbp+47h+pBuffer], rdi
0x1800a70de  mov     [rbp+47h+var_70], rdi
0x1800a70e2  mov     r12, [rbp+47h+arg_20]
0x1800a70e6  mov     [r12], rdi
0x1800a70ea  mov     r15, [rbp+47h+arg_28]
0x1800a70ee  mov     [r15], edi
0x1800a70f1  lea     r8, [rbp+47h+pHandle]; pHandle
0x1800a70f5  mov     edx, eax; BufferSize
0x1800a70f7  mov     rcx, r9; Buffer
0x1800a70fa  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800a7100  mov     ecx, eax; Status
0x1800a7102  call    cs:__imp_I_RpcMapWin32Status
0x1800a7108  mov     ebx, eax
0x1800a710a  test    eax, eax
0x1800a710c  js      loc_1800A721F
0x1800a7112  lea     r8, [rbp+47h+var_78]
0x1800a7116  mov     rdx, [rbp+47h+pHandle]
0x1800a711a  call    ?InputTypeDecodeWrapper@?$Server@U_KerbCredIsoRemoteInput@@U_KerbCredIsoRemoteOutput@@VKerbCredIsoRemoteServer@@$1?PKerbCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PKerbCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PKerbCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@AEAAJPEAXPEAPEAU_KerbCredIsoRemoteInput@@@Z; RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::InputTypeDecodeWrapper(void *,_KerbCredIsoRemoteInput * *)
0x1800a711f  mov     ebx, eax
0x1800a7121  test    eax, eax
0x1800a7123  js      loc_1800A721F
0x1800a7129  lea     r9, [rbp+47h+var_70]
0x1800a712d  mov     r8, [rbp+47h+var_80]
0x1800a7131  mov     rdx, [rbp+47h+var_78]
0x1800a7135  mov     rcx, [rsi]
0x1800a7138  mov     rax, [rsi+8]
0x1800a713c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7141  mov     rax, [rbp+47h+var_78]
0x1800a7145  mov     ecx, [rax]
0x1800a7147  mov     rax, [rbp+47h+var_80]
0x1800a714b  mov     [rax], ecx
0x1800a714d  lea     r8, [rbp+47h+pHandle]; pHandle
0x1800a7151  lea     rdx, [rbp+47h+pEncodedSize]; pEncodedSize
0x1800a7155  lea     rcx, [rbp+47h+pBuffer]; pBuffer
0x1800a7159  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1800a715f  mov     ecx, eax; Status
0x1800a7161  call    cs:__imp_I_RpcMapWin32Status
0x1800a7167  mov     ebx, eax
0x1800a7169  test    eax, eax
0x1800a716b  js      loc_1800A721F
0x1800a7171  lea     r9, [rbp+47h+pEncodedSize]
0x1800a7175  lea     r8, [rbp+47h+var_80]
0x1800a7179  mov     rdx, [rbp+47h+pHandle]
0x1800a717d  call    ?OutputTypeAlignSizeWrapper@?$Server@U_KerbCredIsoRemoteInput@@U_KerbCredIsoRemoteOutput@@VKerbCredIsoRemoteServer@@$1?PKerbCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PKerbCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PKerbCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@AEAAJPEAXPEAPEAU_KerbCredIsoRemoteOutput@@PEAK@Z; RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::OutputTypeAlignSizeWrapper(void *,_KerbCredIsoRemoteOutput * *,ulong *)
0x1800a7182  mov     ebx, eax
0x1800a7184  test    eax, eax
0x1800a7186  js      loc_1800A721F
0x1800a718c  mov     rcx, [rbp+47h+pBuffer]
0x1800a7190  test    rcx, rcx
0x1800a7193  jz      short loc_1800A719E
0x1800a7195  call    KerbFree
0x1800a719a  mov     [rbp+47h+pBuffer], rdi
0x1800a719e  mov     r14d, [rbp+47h+pEncodedSize]
0x1800a71a2  add     r14d, 10h
0x1800a71a6  mov     rax, [rsi+10h]
0x1800a71aa  mov     ecx, r14d
0x1800a71ad  mov     rax, [rax+28h]
0x1800a71b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a71b6  mov     rdi, rax
0x1800a71b9  test    rax, rax
0x1800a71bc  jnz     short loc_1800A71C5
0x1800a71be  mov     ebx, 0C0000017h
0x1800a71c3  jmp     short loc_1800A721F
0x1800a71c5  add     rax, 10h
0x1800a71c9  mov     [rbp+47h+pBuffer], rax
0x1800a71cd  mov     eax, [r15]
0x1800a71d0  sub     eax, 10h
0x1800a71d3  lea     rcx, [rbp+47h+pEncodedSize]
0x1800a71d7  mov     [rsp+0C0h+var_98], rcx; pEncodedSize
0x1800a71dc  mov     [rsp+0C0h+BufferSize], eax; BufferSize
0x1800a71e0  lea     r9, [rbp+47h+pBuffer]; pBuffer
0x1800a71e4  xor     r8d, r8d; Operation
0x1800a71e7  lea     edx, [r8+1]; HandleStyle
0x1800a71eb  mov     rcx, [rbp+47h+pHandle]; Handle
0x1800a71ef  call    cs:__imp_MesBufferHandleReset
0x1800a71f5  mov     ecx, eax; Status
0x1800a71f7  call    cs:__imp_I_RpcMapWin32Status
0x1800a71fd  mov     ebx, eax
0x1800a71ff  test    eax, eax
0x1800a7201  js      short loc_1800A721F
0x1800a7203  lea     r8, [rbp+47h+var_80]
0x1800a7207  mov     rdx, [rbp+47h+pHandle]
0x1800a720b  call    ?OutputTypeEncodeWrapper@?$Server@U_KerbCredIsoRemoteInput@@U_KerbCredIsoRemoteOutput@@VKerbCredIsoRemoteServer@@$1?PKerbCredIsoRemoteInput_Decode@@YAXPEAXPEAPEAU1@@Z$1?PKerbCredIsoRemoteOutput_AlignSize@@YA_K0PEAPEAU2@@Z$1?PKerbCredIsoRemoteOutput_Encode@@YAX02@Z@RemoteGuard@@AEAAJPEAXPEAPEAU_KerbCredIsoRemoteOutput@@@Z; RemoteGuard::Server<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,KerbCredIsoRemoteServer,&PKerbCredIsoRemoteInput_Decode(void *,_KerbCredIsoRemoteInput * *),&PKerbCredIsoRemoteOutput_AlignSize(void *,_KerbCredIsoRemoteOutput * *),&PKerbCredIsoRemoteOutput_Encode(void *,_KerbCredIsoRemoteOutput * *)>::OutputTypeEncodeWrapper(void *,_KerbCredIsoRemoteOutput * *)
0x1800a7210  mov     ebx, eax
0x1800a7212  test    eax, eax
0x1800a7214  js      short loc_1800A721F
0x1800a7216  mov     [r15], r14d
0x1800a7219  mov     [r12], rdi
0x1800a721d  xor     edi, edi
0x1800a721f  mov     rcx, [rbp+47h+pHandle]; Handle
0x1800a7223  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a7227  jz      short loc_1800A722F
0x1800a7229  call    cs:__imp_MesHandleFree
0x1800a722f  mov     rax, [rbp+47h+var_70]
0x1800a7233  test    rax, rax
0x1800a7236  jz      short loc_1800A7249
0x1800a7238  mov     rdx, [rbp+47h+var_80]
0x1800a723c  test    rdx, rdx
0x1800a723f  jz      short loc_1800A7249
0x1800a7241  mov     rcx, [rsi]
0x1800a7244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7249  test    ebx, ebx
0x1800a724b  jns     short loc_1800A7263
0x1800a724d  test    rdi, rdi
0x1800a7250  jz      short loc_1800A7263
0x1800a7252  mov     rax, [rsi+10h]
0x1800a7256  mov     rcx, rdi
0x1800a7259  mov     rax, [rax+30h]
0x1800a725d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7262  nop
0x1800a7263  lea     rcx, [rbp+47h+var_78]
0x1800a7267  call    ??1?$AutoMidlPtr@U_KerbCredIsoRemoteInput@@@RemoteGuard@@QEAA@XZ; RemoteGuard::AutoMidlPtr<_KerbCredIsoRemoteInput>::~AutoMidlPtr<_KerbCredIsoRemoteInput>(void)
0x1800a726c  mov     eax, ebx
0x1800a726e  lea     r11, [rsp+0C0h+var_20]
0x1800a7276  mov     rbx, [r11+30h]
0x1800a727a  mov     rsi, [r11+38h]
0x1800a727e  mov     rsp, r11
0x1800a7281  pop     r15
0x1800a7283  pop     r14
0x1800a7285  pop     r12
0x1800a7287  pop     rdi
0x1800a7288  pop     rbp
0x1800a7289  retn
```
