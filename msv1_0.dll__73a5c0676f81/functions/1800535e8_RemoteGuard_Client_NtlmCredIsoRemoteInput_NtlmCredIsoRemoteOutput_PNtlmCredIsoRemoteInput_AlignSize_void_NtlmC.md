# RemoteGuard::Client<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,&PNtlmCredIsoRemoteInput_AlignSize(void *,_NtlmCredIsoRemoteInput * *),&PNtlmCredIsoRemoteInput_Encode(void *,_NtlmCredIsoRemoteInput * *),&PNtlmCredIsoRemoteOutput_Decode(void *,_NtlmCredIsoRemoteOutput * *)>::CallServer(_NtlmCredIsoRemoteInput const &,_NtlmCredIsoRemoteOutput * *)

- ea: `0x1800535e8`
- end: `0x1800539ad`
- name: `?CallServer@?$Client@U_NtlmCredIsoRemoteInput@@U_NtlmCredIsoRemoteOutput@@$1?PNtlmCredIsoRemoteInput_AlignSize@@YA_KPEAXPEAPEAU1@@Z$1?PNtlmCredIsoRemoteInput_Encode@@YAX01@Z$1?PNtlmCredIsoRemoteOutput_Decode@@YAX0PEAPEAU2@@Z@RemoteGuard@@QEAAJAEBU_NtlmCredIsoRemoteInput@@PEAPEAU_NtlmCredIsoRemoteOutput@@@Z`
- size: `965`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180053440`
- `0x180053520`
- `0x1800539e0`
- `0x180053ba0`
- `0x180053f00`
- `0x180054070`

## callees

- `0x180010b14`
- `0x18002fb50`
- `0x1800535e8`
- `0x18006bcf0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800536c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053967`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800536c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053967`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800538ad`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800538ad`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800537f0`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800537f0`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800536b1`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800536b1`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053677`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800537b6`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053876`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800538e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800538f5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053908`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053677`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800537b6`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053876`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800538e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800538f5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180053908`
- `RPCRT4!MesBufferHandleReset` at `0x1800537ae`
- `RPCRT4!MesBufferHandleReset` at `0x18005386e`
- `RPCRT4!MesBufferHandleReset` at `0x1800537ae`
- `RPCRT4!MesBufferHandleReset` at `0x18005386e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18005366f`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18005366f`
- `RPCRT4!MesHandleFree` at `0x180053921`
- `RPCRT4!MesHandleFree` at `0x180053921`

## pseudocode

```c
__int64 __fastcall RemoteGuard::Client<_NtlmCredIsoRemoteInput,_NtlmCredIsoRemoteOutput,&unsigned __int64 PNtlmCredIsoRemoteInput_AlignSize(void *,_NtlmCredIsoRemoteInput * *),&void PNtlmCredIsoRemoteInput_Encode(void *,_NtlmCredIsoRemoteInput * *),&void PNtlmCredIsoRemoteOutput_Decode(void *,_NtlmCredIsoRemoteOutput * *)>::CallServer(
        __int64 a1,
        _DWORD *a2,
        __int64 a3)
{
  RPC_STATUS v5; // eax
  int v6; // edi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned int *p_pEncodedSize; // rsi
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  unsigned int *v17; // rax
  RPC_STATUS v18; // eax
  RPC_STATUS v19; // eax
  unsigned int pEncodedSize; // [rsp+30h] [rbp+0h] BYREF
  char *pBuffer; // [rsp+38h] [rbp+8h] BYREF
  handle_t pHandle; // [rsp+40h] [rbp+10h] BYREF
  int v24; // [rsp+48h] [rbp+18h] BYREF
  __int64 v25; // [rsp+50h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+28h] BYREF
  _DWORD *pObject; // [rsp+60h] [rbp+30h] BYREF
  unsigned int *v28; // [rsp+68h] [rbp+38h]

  pObject = a2;
  pHandle = (handle_t)-1LL;
  pEncodedSize = 0;
  v28 = 0;
  v25 = 0;
  v24 = 0;
  pBuffer = 0;
  hMem = 0;
  v5 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
  v6 = I_RpcMapWin32Status(v5);
  if ( v6 < 0 )
    goto LABEL_28;
  v7 = NdrMesTypeAlignSize3(
         pHandle,
         &pPicklingInfo,
         &NtlmRemoteIso_ProxyInfo,
         (const unsigned int **)&ArrTypeOffset,
         0,
         &pObject);
  pEncodedSize = v7;
  if ( pBuffer )
  {
    LocalFree(pBuffer);
    pBuffer = 0;
    v7 = pEncodedSize;
  }
  v10 = v7 + 16;
  p_pEncodedSize = 0;
  if ( v7 != -16 && (unsigned int)v10 <= (unsigned __int64)g_ulMaxStackAllocSize )
  {
    v12 = (unsigned int)v10 + g_ulAdditionalProbeSize + 8;
    if ( v12 >= (unsigned int)v10 )
    {
      if ( (unsigned int)VerifyStackAvailable(v12, v8, v9) )
      {
        v13 = v10 + 23;
        if ( v10 + 23 <= (unsigned __int64)(v10 + 8) )
          v13 = 0xFFFFFFFFFFFFFF0LL;
        v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
        v15 = alloca(v14);
        v16 = alloca(v14);
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
    if ( v10 + 8 >= (unsigned __int64)(unsigned int)v10 )
    {
      v17 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
      p_pEncodedSize = v17;
      if ( v17 )
      {
        *v17 = 1885431112;
        p_pEncodedSize = v17 + 2;
      }
    }
  }
  v28 = p_pEncodedSize;
  if ( p_pEncodedSize )
  {
    pBuffer = (char *)(p_pEncodedSize + 4);
    v18 = MesBufferHandleReset(pHandle, 1u, MES_ENCODE, &pBuffer, v10 - 16, &pEncodedSize);
    v6 = I_RpcMapWin32Status(v18);
    if ( v6 >= 0 )
    {
      NdrMesTypeEncode3(
        pHandle,
        &pPicklingInfo,
        &NtlmRemoteIso_ProxyInfo,
        (const unsigned int **)&ArrTypeOffset,
        0,
        &pObject);
      *(_OWORD *)p_pEncodedSize = 0;
      *(_WORD *)p_pEncodedSize = 1;
      v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD, __int64 *, int *))(a1 + 8))(
             *(_QWORD *)a1,
             p_pEncodedSize,
             (unsigned int)v10,
             &v25,
             &v24);
      if ( v6 >= 0 )
      {
        if ( *(_WORD *)v25 == 1 )
        {
          pBuffer = (char *)(v25 + 16);
          v19 = MesBufferHandleReset(pHandle, 1u, MES_DECODE, &pBuffer, v24 - 16, 0);
          v6 = I_RpcMapWin32Status(v19);
          if ( v6 >= 0 )
          {
            NdrMesTypeDecode3(
              pHandle,
              &pPicklingInfo,
              &NtlmRemoteIso_ProxyInfo,
              (const unsigned int **)&ArrTypeOffset,
              1u,
              &hMem);
            if ( hMem && *a2 == *(_DWORD *)hMem )
            {
              *(_QWORD *)a3 = hMem;
              hMem = 0;
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
  if ( v28 && *(v28 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v25 )
    (*(void (**)(void))(*(_QWORD *)(a1 + 16) + 48LL))();
  if ( hMem )
    LocalFree(hMem);
  if ( v6 >= 0 && *(_QWORD *)a3 )
    return *(unsigned int *)(*(_QWORD *)a3 + 4LL);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800535e8  mov     [rsp-8+arg_10], r8
0x1800535ed  mov     [rsp-8+arg_0], rcx
0x1800535f2  push    rbp
0x1800535f3  push    r12
0x1800535f5  push    r13
0x1800535f7  push    r14
0x1800535f9  push    r15
0x1800535fb  sub     rsp, 80h
0x180053602  lea     rbp, [rsp+30h]
0x180053607  mov     [rbp+70h+arg_8], rsi
0x18005360e  mov     [rbp+70h+arg_18], rdi
0x180053615  mov     rax, cs:__security_cookie
0x18005361c  xor     rax, rbp
0x18005361f  mov     [rbp+70h+var_30], rax
0x180053623  mov     r12, rdx
0x180053626  mov     r15, rcx
0x180053629  mov     [rbp+70h+var_40], rdx
0x18005362d  mov     [rbp+70h+pHandle], 0FFFFFFFFFFFFFFFFh
0x180053635  mov     [rbp+70h+pEncodedSize], 0
0x18005363c  mov     [rbp+70h+var_38], 0
0x180053644  mov     [rbp+70h+var_50], 0
0x18005364c  mov     [rbp+70h+var_58], 0
0x180053653  mov     [rbp+70h+pBuffer], 0
0x18005365b  mov     [rbp+70h+hMem], 0
0x180053663  lea     r8, [rbp+70h+pHandle]; pHandle
0x180053667  lea     rdx, [rbp+70h+pEncodedSize]; pEncodedSize
0x18005366b  lea     rcx, [rbp+70h+pBuffer]; pBuffer
0x18005366f  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180053675  mov     ecx, eax; Status
0x180053677  call    cs:__imp_I_RpcMapWin32Status
0x18005367d  mov     edi, eax
0x18005367f  test    eax, eax
0x180053681  js      loc_180053917
0x180053687  lea     rax, [rbp+70h+var_40]
0x18005368b  mov     [rsp+0A0h+pObject], rax; pObject
0x180053690  mov     [rsp+0A0h+nTypeIndex], 0; nTypeIndex
0x180053698  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18005369f  lea     r8, NtlmRemoteIso_ProxyInfo; pProxyInfo
0x1800536a6  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800536ad  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800536b1  call    cs:__imp_NdrMesTypeAlignSize3
0x1800536b7  mov     [rbp+70h+pEncodedSize], eax
0x1800536ba  mov     rcx, [rbp+70h+pBuffer]; hMem
0x1800536be  test    rcx, rcx
0x1800536c1  jz      short loc_1800536D4
0x1800536c3  call    cs:__imp_LocalFree
0x1800536c9  mov     [rbp+70h+pBuffer], 0
0x1800536d1  mov     eax, [rbp+70h+pEncodedSize]
0x1800536d4  lea     r14d, [rax+10h]
0x1800536d8  xor     esi, esi
0x1800536da  test    r14d, r14d
0x1800536dd  jz      short loc_180053741
0x1800536df  mov     edi, r14d
0x1800536e2  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800536e9  ja      short loc_180053741
0x1800536eb  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800536f2  add     rcx, 8
0x1800536f6  add     rcx, rdi
0x1800536f9  cmp     rcx, rdi
0x1800536fc  jb      short loc_180053741
0x1800536fe  call    VerifyStackAvailable
0x180053703  test    eax, eax
0x180053705  jz      short loc_180053732
0x180053707  lea     rax, [r14+8]
0x18005370b  lea     rcx, [rax+0Fh]
0x18005370f  cmp     rcx, rax
0x180053712  ja      short loc_18005371E
0x180053714  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005371e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180053722  mov     rax, rcx
0x180053725  call    _alloca_probe
0x18005372a  sub     rsp, rcx
0x18005372d  lea     rsi, [rsp+0A0h+pEncodedSize]
0x180053732  test    rsi, rsi
0x180053735  jz      short loc_180053746
0x180053737  mov     dword ptr [rsi], 6B637453h
0x18005373d  add     rsi, 8
0x180053741  test    rsi, rsi
0x180053744  jnz     short loc_180053770
0x180053746  mov     eax, r14d
0x180053749  lea     rcx, [r14+8]
0x18005374d  cmp     rcx, rax
0x180053750  jb      short loc_180053770
0x180053752  mov     rax, cs:g_pfnAllocate
0x180053759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005375e  mov     rsi, rax
0x180053761  test    rax, rax
0x180053764  jz      short loc_180053770
0x180053766  mov     dword ptr [rax], 70616548h
0x18005376c  add     rsi, 8
0x180053770  mov     [rbp+70h+var_38], rsi
0x180053774  test    rsi, rsi
0x180053777  jnz     short loc_180053783
0x180053779  mov     edi, 0C0000017h
0x18005377e  jmp     loc_180053917
0x180053783  lea     rax, [rsi+10h]
0x180053787  mov     [rbp+70h+pBuffer], rax
0x18005378b  lea     eax, [r14-10h]
0x18005378f  lea     rcx, [rbp+70h+pEncodedSize]
0x180053793  mov     [rsp+0A0h+pObject], rcx; pEncodedSize
0x180053798  mov     [rsp+0A0h+nTypeIndex], eax; BufferSize
0x18005379c  lea     r9, [rbp+70h+pBuffer]; pBuffer
0x1800537a0  xor     r8d, r8d; Operation
0x1800537a3  lea     r13d, [r8+1]
0x1800537a7  mov     edx, r13d; HandleStyle
0x1800537aa  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800537ae  call    cs:__imp_MesBufferHandleReset
0x1800537b4  mov     ecx, eax; Status
0x1800537b6  call    cs:__imp_I_RpcMapWin32Status
0x1800537bc  mov     edi, eax
0x1800537be  test    eax, eax
0x1800537c0  js      loc_180053917
0x1800537c6  lea     rax, [rbp+70h+var_40]
0x1800537ca  mov     [rsp+0A0h+pObject], rax; pObject
0x1800537cf  mov     [rsp+0A0h+nTypeIndex], 0; nTypeIndex
0x1800537d7  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800537de  lea     r8, NtlmRemoteIso_ProxyInfo; pProxyInfo
0x1800537e5  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800537ec  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800537f0  call    cs:__imp_NdrMesTypeEncode3
0x1800537f6  nop
0x1800537f7  xorps   xmm0, xmm0
0x1800537fa  movdqu  xmmword ptr [rsi], xmm0
0x1800537fe  mov     [rsi], r13w
0x180053802  lea     rax, [rbp+70h+var_58]
0x180053806  mov     qword ptr [rsp+0A0h+nTypeIndex], rax
0x18005380b  lea     r9, [rbp+70h+var_50]
0x18005380f  mov     r8d, r14d
0x180053812  mov     rdx, rsi
0x180053815  mov     rcx, [r15]
0x180053818  mov     rax, [r15+8]
0x18005381c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053821  mov     edi, eax
0x180053823  test    eax, eax
0x180053825  js      loc_180053917
0x18005382b  mov     rax, [rbp+70h+var_50]
0x18005382f  movzx   ecx, word ptr [rax]
0x180053832  cmp     ecx, r13d
0x180053835  jz      short loc_180053841
0x180053837  mov     edi, 0C000A013h
0x18005383c  jmp     loc_180053917
0x180053841  mov     rax, [rbp+70h+var_50]
0x180053845  add     rax, 10h
0x180053849  mov     [rbp+70h+pBuffer], rax
0x18005384d  mov     eax, [rbp+70h+var_58]
0x180053850  add     eax, 0FFFFFFF0h
0x180053853  mov     [rsp+0A0h+pObject], 0; pEncodedSize
0x18005385c  mov     [rsp+0A0h+nTypeIndex], eax; BufferSize
0x180053860  lea     r9, [rbp+70h+pBuffer]; pBuffer
0x180053864  mov     r8d, r13d; Operation
0x180053867  mov     edx, r13d; HandleStyle
0x18005386a  mov     rcx, [rbp+70h+pHandle]; Handle
0x18005386e  call    cs:__imp_MesBufferHandleReset
0x180053874  mov     ecx, eax; Status
0x180053876  call    cs:__imp_I_RpcMapWin32Status
0x18005387c  mov     edi, eax
0x18005387e  test    eax, eax
0x180053880  js      loc_180053917
0x180053886  lea     rax, [rbp+70h+hMem]
0x18005388a  mov     [rsp+0A0h+pObject], rax; pObject
0x18005388f  mov     [rsp+0A0h+nTypeIndex], r13d; nTypeIndex
0x180053894  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18005389b  lea     r8, NtlmRemoteIso_ProxyInfo; pProxyInfo
0x1800538a2  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800538a9  mov     rcx, [rbp+70h+pHandle]; Handle
0x1800538ad  call    cs:__imp_NdrMesTypeDecode3
0x1800538b3  nop
0x1800538b4  mov     rcx, [rbp+70h+hMem]
0x1800538b8  test    rcx, rcx
0x1800538bb  jz      short loc_1800538D9
0x1800538bd  mov     eax, [rcx]
0x1800538bf  cmp     [r12], eax
0x1800538c3  jnz     short loc_1800538D9
0x1800538c5  mov     rax, [rbp+70h+arg_10]
0x1800538cc  mov     [rax], rcx
0x1800538cf  mov     [rbp+70h+hMem], 0
0x1800538d7  jmp     short loc_180053917
0x1800538d9  mov     edi, 0C00000E5h
0x1800538de  jmp     short loc_180053917
0x1800538e0  mov     ecx, eax; Status
0x1800538e2  call    cs:__imp_I_RpcMapWin32Status
0x1800538e8  mov     edi, eax
0x1800538ea  mov     r15, [rbp+70h+arg_0]
0x1800538f1  jmp     short loc_180053917
0x1800538f3  mov     ecx, eax; Status
0x1800538f5  call    cs:__imp_I_RpcMapWin32Status
0x1800538fb  mov     edi, eax
0x1800538fd  mov     r15, [rbp+70h+arg_0]
0x180053904  jmp     short loc_180053917
0x180053906  mov     ecx, eax; Status
0x180053908  call    cs:__imp_I_RpcMapWin32Status
0x18005390e  mov     edi, eax
0x180053910  mov     r15, [rbp+70h+arg_0]
0x180053917  mov     rcx, [rbp+70h+pHandle]; Handle
0x18005391b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005391f  jz      short loc_180053927
0x180053921  call    cs:__imp_MesHandleFree
0x180053927  mov     rax, [rbp+70h+var_38]
0x18005392b  test    rax, rax
0x18005392e  jz      short loc_180053948
0x180053930  lea     rcx, [rax-8]
0x180053934  cmp     dword ptr [rcx], 70616548h
0x18005393a  jnz     short loc_180053948
0x18005393c  mov     rax, cs:g_pfnFree
0x180053943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053948  mov     rcx, [rbp+70h+var_50]
0x18005394c  test    rcx, rcx
0x18005394f  jz      short loc_18005395E
0x180053951  mov     rax, [r15+10h]
0x180053955  mov     rax, [rax+30h]
0x180053959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005395e  mov     rcx, [rbp+70h+hMem]; hMem
0x180053962  test    rcx, rcx
0x180053965  jz      short loc_18005396D
0x180053967  call    cs:__imp_LocalFree
0x18005396d  test    edi, edi
0x18005396f  js      short loc_180053983
0x180053971  mov     rax, [rbp+70h+arg_10]
0x180053978  mov     rcx, [rax]
0x18005397b  test    rcx, rcx
0x18005397e  jz      short loc_180053983
0x180053980  mov     edi, [rcx+4]
0x180053983  mov     eax, edi
0x180053985  mov     rcx, [rbp+70h+var_30]
0x180053989  xor     rcx, rbp; StackCookie
0x18005398c  call    __security_check_cookie
0x180053991  mov     rsi, [rbp+70h+arg_8]
0x180053998  mov     rdi, [rbp+70h+arg_18]
0x18005399f  lea     rsp, [rbp+50h]
0x1800539a3  pop     r15
0x1800539a5  pop     r14
0x1800539a7  pop     r13
0x1800539a9  pop     r12
0x1800539ab  pop     rbp
0x1800539ac  retn
```
