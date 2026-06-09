# RemoteGuard::Client<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,&PKerbCredIsoRemoteInput_AlignSize(void *,_KerbCredIsoRemoteInput * *),&PKerbCredIsoRemoteInput_Encode(void *,_KerbCredIsoRemoteInput * *),&PKerbCredIsoRemoteOutput_Decode(void *,_KerbCredIsoRemoteOutput * *)>::CallServer(_KerbCredIsoRemoteInput const &,_KerbCredIsoRemoteOutput * *)

- ea: `0x1800c9434`
- end: `0x1800c97f7`
- name: `?CallServer@?$Client@U_KerbCredIsoRemoteInput@@U_KerbCredIsoRemoteOutput@@$1?PKerbCredIsoRemoteInput_AlignSize@@YA_KPEAXPEAPEAU1@@Z$1?PKerbCredIsoRemoteInput_Encode@@YAX01@Z$1?PKerbCredIsoRemoteOutput_Decode@@YAX0PEAPEAU2@@Z@RemoteGuard@@QEAAJAEBU_KerbCredIsoRemoteInput@@PEAPEAU_KerbCredIsoRemoteOutput@@@Z`
- size: `963`
- prototype: ``
- caller_count: `22`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800c91e0`
- `0x1800c92f0`
- `0x1800c9360`
- `0x1800c93d0`
- `0x1800c9800`
- `0x1800c9a10`
- `0x1800c9d00`
- `0x1800c9e10`
- `0x1800c9e80`
- `0x1800c9ef0`
- `0x1800c9ff0`
- `0x1800ca060`
- `0x1800ca0d0`
- `0x1800ca3c0`
- `0x1800ca524`
- `0x1800ca5b0`
- `0x1800ca7e0`
- `0x1800ca850`
- `0x1800caa50`
- `0x1800cab10`
- `0x1800cab80`
- `0x1800cabf0`

## callees

- `0x1800069a0`
- `0x180007e80`
- `0x180070680`
- `0x1800c9434`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800c94fd`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800c94fd`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800c963b`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800c963b`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800c96f8`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800c96f8`
- `RPCRT4!MesHandleFree` at `0x1800c976c`
- `RPCRT4!MesHandleFree` at `0x1800c976c`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c94c3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c9601`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c96c1`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c972d`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c9740`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c9753`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c94c3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c9601`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c96c1`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c972d`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c9740`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c9753`
- `RPCRT4!MesBufferHandleReset` at `0x1800c95f9`
- `RPCRT4!MesBufferHandleReset` at `0x1800c96b9`
- `RPCRT4!MesBufferHandleReset` at `0x1800c95f9`
- `RPCRT4!MesBufferHandleReset` at `0x1800c96b9`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800c94bb`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800c94bb`

## pseudocode

```c
__int64 __fastcall RemoteGuard::Client<_KerbCredIsoRemoteInput,_KerbCredIsoRemoteOutput,&unsigned __int64 PKerbCredIsoRemoteInput_AlignSize(void *,_KerbCredIsoRemoteInput * *),&void PKerbCredIsoRemoteInput_Encode(void *,_KerbCredIsoRemoteInput * *),&void PKerbCredIsoRemoteOutput_Decode(void *,_KerbCredIsoRemoteOutput * *)>::CallServer(
        __int64 a1,
        _DWORD *a2,
        __int64 a3)
{
  RPC_STATUS v5; // eax
  int v6; // edi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r14
  unsigned int *p_pEncodedSize; // rsi
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  unsigned int *v18; // rax
  RPC_STATUS v19; // eax
  RPC_STATUS v20; // eax
  unsigned int pEncodedSize; // [rsp+30h] [rbp+0h] BYREF
  char *pBuffer; // [rsp+38h] [rbp+8h] BYREF
  handle_t pHandle; // [rsp+40h] [rbp+10h] BYREF
  int v25; // [rsp+48h] [rbp+18h] BYREF
  __int64 v26; // [rsp+50h] [rbp+20h] BYREF
  _DWORD *v27; // [rsp+58h] [rbp+28h] BYREF
  _DWORD *pObject; // [rsp+60h] [rbp+30h] BYREF
  unsigned int *v29; // [rsp+68h] [rbp+38h]

  pObject = a2;
  pHandle = (handle_t)-1LL;
  pEncodedSize = 0;
  v29 = 0;
  v26 = 0;
  v25 = 0;
  pBuffer = 0;
  v27 = 0;
  v5 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
  v6 = I_RpcMapWin32Status(v5);
  if ( v6 < 0 )
    goto LABEL_28;
  v7 = NdrMesTypeAlignSize3(
         pHandle,
         &stru_180124818,
         &KerberosRemoteIso_ProxyInfo,
         (const unsigned int **)&off_180140160,
         0,
         &pObject);
  pEncodedSize = v7;
  if ( pBuffer )
  {
    KerbFree(pBuffer);
    pBuffer = 0;
    v7 = pEncodedSize;
  }
  v11 = v7 + 16;
  p_pEncodedSize = 0;
  if ( v7 != -16 && (unsigned int)v11 <= (unsigned __int64)g_ulMaxStackAllocSize )
  {
    v13 = (unsigned int)v11 + g_ulAdditionalProbeSize + 8;
    if ( v13 >= (unsigned int)v11 )
    {
      if ( (unsigned int)VerifyStackAvailable(v13, v8, v9, v10) )
      {
        v14 = v11 + 23;
        if ( v11 + 23 <= (unsigned __int64)(v11 + 8) )
          v14 = 0xFFFFFFFFFFFFFF0LL;
        v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
        v16 = alloca(v15);
        v17 = alloca(v15);
        p_pEncodedSize = &pEncodedSize;
      }
      if ( !p_pEncodedSize )
        goto LABEL_14;
      *p_pEncodedSize = 1801679955;
      p_pEncodedSize += 2;
    }
  }
  if ( !p_pEncodedSize )
  {
LABEL_14:
    if ( v11 + 8 >= (unsigned __int64)(unsigned int)v11 )
    {
      v18 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
      p_pEncodedSize = v18;
      if ( v18 )
      {
        *v18 = 1885431112;
        p_pEncodedSize = v18 + 2;
      }
    }
  }
  v29 = p_pEncodedSize;
  if ( p_pEncodedSize )
  {
    pBuffer = (char *)(p_pEncodedSize + 4);
    v19 = MesBufferHandleReset(pHandle, 1u, MES_ENCODE, &pBuffer, v11 - 16, &pEncodedSize);
    v6 = I_RpcMapWin32Status(v19);
    if ( v6 >= 0 )
    {
      NdrMesTypeEncode3(
        pHandle,
        &stru_180124818,
        &KerberosRemoteIso_ProxyInfo,
        (const unsigned int **)&off_180140160,
        0,
        &pObject);
      *(_OWORD *)p_pEncodedSize = 0;
      *(_WORD *)p_pEncodedSize = 1;
      v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD, __int64 *, int *))(a1 + 8))(
             *(_QWORD *)a1,
             p_pEncodedSize,
             (unsigned int)v11,
             &v26,
             &v25);
      if ( v6 >= 0 )
      {
        if ( *(_WORD *)v26 == 1 )
        {
          pBuffer = (char *)(v26 + 16);
          v20 = MesBufferHandleReset(pHandle, 1u, MES_DECODE, &pBuffer, v25 - 16, 0);
          v6 = I_RpcMapWin32Status(v20);
          if ( v6 >= 0 )
          {
            NdrMesTypeDecode3(
              pHandle,
              &stru_180124818,
              &KerberosRemoteIso_ProxyInfo,
              (const unsigned int **)&off_180140160,
              1u,
              &v27);
            if ( v27 && *a2 == *v27 )
            {
              *(_QWORD *)a3 = v27;
              v27 = 0;
            }
            else
            {
              v6 = -1073741595;
            }
          }
        }
        else
        {
          v6 = -1073700845;
        }
      }
    }
  }
  else
  {
    v6 = -1073741801;
  }
LABEL_28:
  if ( pHandle != (handle_t)-1LL )
    MesHandleFree(pHandle);
  if ( v29 && *(v29 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v26 )
    (*(void (**)(void))(*(_QWORD *)(a1 + 16) + 48LL))();
  if ( v27 )
    KerbFree(v27);
  if ( v6 >= 0 && *(_QWORD *)a3 )
    return *(unsigned int *)(*(_QWORD *)a3 + 4LL);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c9434  mov     [rsp-8+arg_10], r8
0x1800c9439  mov     [rsp-8+arg_0], rcx
0x1800c943e  push    rbp
0x1800c943f  push    r12
0x1800c9441  push    r13
0x1800c9443  push    r14
0x1800c9445  push    r15
0x1800c9447  sub     rsp, 80h
0x1800c944e  lea     rbp, [rsp+30h]
0x1800c9453  mov     [rbp+70h+arg_8], rsi
0x1800c945a  mov     [rbp+70h+arg_18], rdi
0x1800c9461  mov     rax, cs:__security_cookie
0x1800c9468  xor     rax, rbp
0x1800c946b  mov     [rbp+70h+var_30], rax
0x1800c946f  mov     r12, rdx
0x1800c9472  mov     r15, rcx
0x1800c9475  mov     [rbp+70h+var_40], rdx
0x1800c9479  mov     [rbp+70h+pHandle], 0FFFFFFFFFFFFFFFFh
0x1800c9481  mov     [rbp+70h+pEncodedSize], 0
0x1800c9488  mov     [rbp+70h+var_38], 0
0x1800c9490  mov     [rbp+70h+var_50], 0
0x1800c9498  mov     [rbp+70h+var_58], 0
0x1800c949f  mov     [rbp+70h+pBuffer], 0
0x1800c94a7  mov     [rbp+70h+var_48], 0
0x1800c94af  lea     r8, [rbp+70h+pHandle]; pHandle
0x1800c94b3  lea     rdx, [rbp+70h+pEncodedSize]; pEncodedSize
0x1800c94b7  lea     rcx, [rbp+70h+pBuffer]; pBuffer
0x1800c94bb  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1800c94c1  mov     ecx, eax; Status
0x1800c94c3  call    cs:__imp_I_RpcMapWin32Status
0x1800c94c9  mov     edi, eax
0x1800c94cb  test    eax, eax
0x1800c94cd  js      loc_1800C9762
0x1800c94d3  lea     rax, [rbp+70h+var_40]
0x1800c94d7  mov     [rsp+0A0h+pObject], rax; pObject
0x1800c94dc  mov     [rsp+0A0h+nTypeIndex], 0; nTypeIndex
0x1800c94e4  lea     r9, off_180140160; ArrTypeOffset
0x1800c94eb  lea     r8, ?KerberosRemoteIso_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800c94f2  lea     rdx, stru_180124818; pPicklingInfo
0x1800c94f9  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800c94fd  call    cs:__imp_NdrMesTypeAlignSize3
0x1800c9503  mov     [rbp+70h+pEncodedSize], eax
0x1800c9506  mov     rcx, [rbp+70h+pBuffer]
0x1800c950a  test    rcx, rcx
0x1800c950d  jz      short loc_1800C951F
0x1800c950f  call    KerbFree
0x1800c9514  mov     [rbp+70h+pBuffer], 0
0x1800c951c  mov     eax, [rbp+70h+pEncodedSize]
0x1800c951f  lea     r14d, [rax+10h]
0x1800c9523  xor     esi, esi
0x1800c9525  test    r14d, r14d
0x1800c9528  jz      short loc_1800C958C
0x1800c952a  mov     edi, r14d
0x1800c952d  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800c9534  ja      short loc_1800C958C
0x1800c9536  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800c953d  add     rcx, 8
0x1800c9541  add     rcx, rdi
0x1800c9544  cmp     rcx, rdi
0x1800c9547  jb      short loc_1800C958C
0x1800c9549  call    VerifyStackAvailable
0x1800c954e  test    eax, eax
0x1800c9550  jz      short loc_1800C957D
0x1800c9552  lea     rax, [r14+8]
0x1800c9556  lea     rcx, [rax+0Fh]
0x1800c955a  cmp     rcx, rax
0x1800c955d  ja      short loc_1800C9569
0x1800c955f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c9569  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c956d  mov     rax, rcx
0x1800c9570  call    _alloca_probe
0x1800c9575  sub     rsp, rcx
0x1800c9578  lea     rsi, [rsp+0A0h+pEncodedSize]
0x1800c957d  test    rsi, rsi
0x1800c9580  jz      short loc_1800C9591
0x1800c9582  mov     dword ptr [rsi], 6B637453h
0x1800c9588  add     rsi, 8
0x1800c958c  test    rsi, rsi
0x1800c958f  jnz     short loc_1800C95BB
0x1800c9591  mov     eax, r14d
0x1800c9594  lea     rcx, [r14+8]
0x1800c9598  cmp     rcx, rax
0x1800c959b  jb      short loc_1800C95BB
0x1800c959d  mov     rax, cs:g_pfnAllocate
0x1800c95a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c95a9  mov     rsi, rax
0x1800c95ac  test    rax, rax
0x1800c95af  jz      short loc_1800C95BB
0x1800c95b1  mov     dword ptr [rax], 70616548h
0x1800c95b7  add     rsi, 8
0x1800c95bb  mov     [rbp+70h+var_38], rsi
0x1800c95bf  test    rsi, rsi
0x1800c95c2  jnz     short loc_1800C95CE
0x1800c95c4  mov     edi, 0C0000017h
0x1800c95c9  jmp     loc_1800C9762
0x1800c95ce  lea     rax, [rsi+10h]
0x1800c95d2  mov     [rbp+70h+pBuffer], rax
0x1800c95d6  lea     eax, [r14-10h]
0x1800c95da  lea     rcx, [rbp+70h+pEncodedSize]
0x1800c95de  mov     [rsp+0A0h+pObject], rcx; pEncodedSize
0x1800c95e3  mov     [rsp+0A0h+nTypeIndex], eax; BufferSize
0x1800c95e7  lea     r9, [rbp+70h+pBuffer]; pBuffer
0x1800c95eb  xor     r8d, r8d; Operation
0x1800c95ee  lea     r13d, [r8+1]
0x1800c95f2  mov     edx, r13d; HandleStyle
0x1800c95f5  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800c95f9  call    cs:__imp_MesBufferHandleReset
0x1800c95ff  mov     ecx, eax; Status
0x1800c9601  call    cs:__imp_I_RpcMapWin32Status
0x1800c9607  mov     edi, eax
0x1800c9609  test    eax, eax
0x1800c960b  js      loc_1800C9762
0x1800c9611  lea     rax, [rbp+70h+var_40]
0x1800c9615  mov     [rsp+0A0h+pObject], rax; pObject
0x1800c961a  mov     [rsp+0A0h+nTypeIndex], 0; nTypeIndex
0x1800c9622  lea     r9, off_180140160; ArrTypeOffset
0x1800c9629  lea     r8, ?KerberosRemoteIso_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800c9630  lea     rdx, stru_180124818; pPicklingInfo
0x1800c9637  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800c963b  call    cs:__imp_NdrMesTypeEncode3
0x1800c9641  nop
0x1800c9642  xorps   xmm0, xmm0
0x1800c9645  movdqu  xmmword ptr [rsi], xmm0
0x1800c9649  mov     [rsi], r13w
0x1800c964d  lea     rax, [rbp+70h+var_58]
0x1800c9651  mov     qword ptr [rsp+0A0h+nTypeIndex], rax
0x1800c9656  lea     r9, [rbp+70h+var_50]
0x1800c965a  mov     r8d, r14d
0x1800c965d  mov     rdx, rsi
0x1800c9660  mov     rcx, [r15]
0x1800c9663  mov     rax, [r15+8]
0x1800c9667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c966c  mov     edi, eax
0x1800c966e  test    eax, eax
0x1800c9670  js      loc_1800C9762
0x1800c9676  mov     rax, [rbp+70h+var_50]
0x1800c967a  movzx   ecx, word ptr [rax]
0x1800c967d  cmp     ecx, r13d
0x1800c9680  jz      short loc_1800C968C
0x1800c9682  mov     edi, 0C000A013h
0x1800c9687  jmp     loc_1800C9762
0x1800c968c  mov     rax, [rbp+70h+var_50]
0x1800c9690  add     rax, 10h
0x1800c9694  mov     [rbp+70h+pBuffer], rax
0x1800c9698  mov     eax, [rbp+70h+var_58]
0x1800c969b  add     eax, 0FFFFFFF0h
0x1800c969e  mov     [rsp+0A0h+pObject], 0; pEncodedSize
0x1800c96a7  mov     [rsp+0A0h+nTypeIndex], eax; BufferSize
0x1800c96ab  lea     r9, [rbp+70h+pBuffer]; pBuffer
0x1800c96af  mov     r8d, r13d; Operation
0x1800c96b2  mov     edx, r13d; HandleStyle
0x1800c96b5  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800c96b9  call    cs:__imp_MesBufferHandleReset
0x1800c96bf  mov     ecx, eax; Status
0x1800c96c1  call    cs:__imp_I_RpcMapWin32Status
0x1800c96c7  mov     edi, eax
0x1800c96c9  test    eax, eax
0x1800c96cb  js      loc_1800C9762
0x1800c96d1  lea     rax, [rbp+70h+var_48]
0x1800c96d5  mov     [rsp+0A0h+pObject], rax; pObject
0x1800c96da  mov     [rsp+0A0h+nTypeIndex], r13d; nTypeIndex
0x1800c96df  lea     r9, off_180140160; ArrTypeOffset
0x1800c96e6  lea     r8, ?KerberosRemoteIso_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800c96ed  lea     rdx, stru_180124818; pPicklingInfo
0x1800c96f4  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800c96f8  call    cs:__imp_NdrMesTypeDecode3
0x1800c96fe  nop
0x1800c96ff  mov     rcx, [rbp+70h+var_48]
0x1800c9703  test    rcx, rcx
0x1800c9706  jz      short loc_1800C9724
0x1800c9708  mov     eax, [rcx]
0x1800c970a  cmp     [r12], eax
0x1800c970e  jnz     short loc_1800C9724
0x1800c9710  mov     rax, [rbp+70h+arg_10]
0x1800c9717  mov     [rax], rcx
0x1800c971a  mov     [rbp+70h+var_48], 0
0x1800c9722  jmp     short loc_1800C9762
0x1800c9724  mov     edi, 0C00000E5h
0x1800c9729  jmp     short loc_1800C9762
0x1800c972b  mov     ecx, eax; Status
0x1800c972d  call    cs:__imp_I_RpcMapWin32Status
0x1800c9733  mov     edi, eax
0x1800c9735  mov     r15, [rbp+70h+arg_0]
0x1800c973c  jmp     short loc_1800C9762
0x1800c973e  mov     ecx, eax; Status
0x1800c9740  call    cs:__imp_I_RpcMapWin32Status
0x1800c9746  mov     edi, eax
0x1800c9748  mov     r15, [rbp+70h+arg_0]
0x1800c974f  jmp     short loc_1800C9762
0x1800c9751  mov     ecx, eax; Status
0x1800c9753  call    cs:__imp_I_RpcMapWin32Status
0x1800c9759  mov     edi, eax
0x1800c975b  mov     r15, [rbp+70h+arg_0]
0x1800c9762  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800c9766  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c976a  jz      short loc_1800C9772
0x1800c976c  call    cs:__imp_MesHandleFree
0x1800c9772  mov     rax, [rbp+70h+var_38]
0x1800c9776  test    rax, rax
0x1800c9779  jz      short loc_1800C9793
0x1800c977b  lea     rcx, [rax-8]
0x1800c977f  cmp     dword ptr [rcx], 70616548h
0x1800c9785  jnz     short loc_1800C9793
0x1800c9787  mov     rax, cs:g_pfnFree
0x1800c978e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9793  mov     rcx, [rbp+70h+var_50]
0x1800c9797  test    rcx, rcx
0x1800c979a  jz      short loc_1800C97A9
0x1800c979c  mov     rax, [r15+10h]
0x1800c97a0  mov     rax, [rax+30h]
0x1800c97a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c97a9  mov     rcx, [rbp+70h+var_48]
0x1800c97ad  test    rcx, rcx
0x1800c97b0  jz      short loc_1800C97B7
0x1800c97b2  call    KerbFree
0x1800c97b7  test    edi, edi
0x1800c97b9  js      short loc_1800C97CD
0x1800c97bb  mov     rax, [rbp+70h+arg_10]
0x1800c97c2  mov     rcx, [rax]
0x1800c97c5  test    rcx, rcx
0x1800c97c8  jz      short loc_1800C97CD
0x1800c97ca  mov     edi, [rcx+4]
0x1800c97cd  mov     eax, edi
0x1800c97cf  mov     rcx, [rbp+70h+var_30]
0x1800c97d3  xor     rcx, rbp; StackCookie
0x1800c97d6  call    __security_check_cookie
0x1800c97db  mov     rsi, [rbp+70h+arg_8]
0x1800c97e2  mov     rdi, [rbp+70h+arg_18]
0x1800c97e9  lea     rsp, [rbp+50h]
0x1800c97ed  pop     r15
0x1800c97ef  pop     r14
0x1800c97f1  pop     r13
0x1800c97f3  pop     r12
0x1800c97f5  pop     rbp
0x1800c97f6  retn
```
