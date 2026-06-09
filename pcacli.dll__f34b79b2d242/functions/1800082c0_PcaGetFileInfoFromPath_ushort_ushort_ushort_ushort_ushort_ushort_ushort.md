# PcaGetFileInfoFromPath(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x1800082c0`
- end: `0x18000847a`
- name: `?PcaGetFileInfoFromPath@@YAKPEAG000000@Z`
- size: `442`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callees

- `0x180001870`
- `0x180002180`
- `0x180002bd0`
- `0x180002ca0`
- `0x180002ee8`
- `0x180007738`
- `0x1800082c0`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000c4b4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c4b4`
- `RPCRT4!NdrClientCall3` at `0x1800083c3`
- `RPCRT4!NdrClientCall3` at `0x1800083c3`

## string_xrefs

- `0x18000831e`: `PcaClient`
- `0x1800083ee`: `PcaClient`
- `0x180008345`: `Failed to create binding handle [%d]`
- `0x180008312`: `GetFileInfoFromPath ignored,PCA disabled`
- `0x180008352`: `PcaGetFileInfoFromPath`
- `0x1800083e2`: `GetFileInfoFromPath,Time,%llu`

## pseudocode

```c
__int64 __fastcall PcaGetFileInfoFromPath(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  unsigned __int64 v11; // r13
  unsigned int v12; // edi
  CLIENT_CALL_RETURN v13; // rbx
  int v14; // eax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  void *v19; // [rsp+68h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v20; // [rsp+70h] [rbp-48h]
  unsigned __int64 v21; // [rsp+78h] [rbp-40h]

  v11 = PcaTimeStart();
  v21 = v11;
  v12 = 0;
  v19 = 0;
  if ( (unsigned int)PcaIsPcaDisabled() )
  {
    PcaTracePrintf("PcaClient", 0, 0, "GetFileInfoFromPath ignored,PCA disabled");
    LODWORD(v13.Pointer) = 0;
  }
  else
  {
    v14 = PcapCreateBindingHandle(&v19);
    LODWORD(v13.Pointer) = v14;
    if ( !v14 )
      goto LABEL_5;
    AslLogCallPrintf(1, "PcaGetFileInfoFromPath", 1437, "Failed to create binding handle [%d]", v14);
  }
  while ( LODWORD(v13.Pointer) )
  {
    if ( v12 > 1 )
      break;
    v16 = (unsigned int)(LODWORD(v13.Pointer) - 1708);
    if ( (unsigned int)v16 > 0x2D )
      break;
    v17 = 0x200000004201LL;
    if ( !_bittest64(&v17, v16) )
      break;
    LODWORD(v13.Pointer) = PcacpStartPCAService();
    ++v12;
    if ( !LODWORD(v13.Pointer) )
    {
LABEL_5:
      v20.Simple = 0;
      v13.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, a2, a3, a4, a5, a6, a7, v19, a1).Pointer;
      v20.Pointer = v13.Pointer;
      v15 = PcaTimeStart();
      PcaTracePrintf("PcaClient", 0, 0, "GetFileInfoFromPath,Time,%llu", v15 - v11);
    }
  }
  return LODWORD(v13.Pointer);
}

```

## disassembly

```asm
0x1800082c0  mov     rax, rsp
0x1800082c3  mov     [rax+20h], r9
0x1800082c7  mov     [rax+18h], r8
0x1800082cb  mov     [rax+10h], rdx
0x1800082cf  mov     [rax+8], rcx
0x1800082d3  push    rbx
0x1800082d4  push    rsi
0x1800082d5  push    rdi
0x1800082d6  push    r12
0x1800082d8  push    r13
0x1800082da  push    r14
0x1800082dc  push    r15
0x1800082de  sub     rsp, 80h
0x1800082e5  mov     rsi, r9
0x1800082e8  mov     r14, r8
0x1800082eb  mov     r15, rdx
0x1800082ee  mov     r12, rcx
0x1800082f1  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x1800082f6  mov     r13, rax
0x1800082f9  mov     [rsp+0B8h+var_40], rax
0x1800082fe  xor     edi, edi
0x180008300  mov     [rsp+0B8h+var_58], edi
0x180008304  mov     [rsp+0B8h+var_50], rdi
0x180008309  call    ?PcaIsPcaDisabled@@YAHXZ; PcaIsPcaDisabled(void)
0x18000830e  test    eax, eax
0x180008310  jz      short loc_180008331
0x180008312  lea     r9, aGetfileinfofro; "GetFileInfoFromPath ignored,PCA disable"...
0x180008319  xor     r8d, r8d; unsigned int
0x18000831c  xor     edx, edx; unsigned int
0x18000831e  lea     rcx, aPcaclient; "PcaClient"
0x180008325  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x18000832a  xor     ebx, ebx
0x18000832c  jmp     loc_18000842B
0x180008331  lea     rcx, [rsp+0B8h+var_50]; void **
0x180008336  call    ?PcapCreateBindingHandle@@YAKPEAPEAX@Z; PcapCreateBindingHandle(void * *)
0x18000833b  mov     ebx, eax
0x18000833d  test    eax, eax
0x18000833f  jz      short loc_180008368
0x180008341  mov     dword ptr [rsp+0B8h+var_98], eax
0x180008345  lea     r9, aFailedToCreate_0; "Failed to create binding handle [%d]"
0x18000834c  mov     r8d, 59Dh
0x180008352  lea     rdx, aPcagetfileinfo_0; "PcaGetFileInfoFromPath"
0x180008359  mov     ecx, 1
0x18000835e  call    AslLogCallPrintf
0x180008363  jmp     loc_18000842B
0x180008368  nop
0x180008369  mov     [rsp+0B8h+var_48], 0
0x180008372  mov     [rsp+0B8h+var_68], r12
0x180008377  mov     rax, [rsp+0B8h+var_50]
0x18000837c  mov     [rsp+0B8h+var_70], rax
0x180008381  mov     rax, [rsp+0B8h+arg_30]
0x180008389  mov     [rsp+0B8h+var_78], rax
0x18000838e  mov     rax, [rsp+0B8h+arg_28]
0x180008396  mov     [rsp+0B8h+var_80], rax
0x18000839b  mov     rax, [rsp+0B8h+arg_20]
0x1800083a3  mov     [rsp+0B8h+var_88], rax
0x1800083a8  mov     [rsp+0B8h+var_90], rsi
0x1800083ad  mov     [rsp+0B8h+var_98], r14
0x1800083b2  mov     r9, r15
0x1800083b5  xor     r8d, r8d; pReturnValue
0x1800083b8  lea     edx, [r8+5]; nProcNum
0x1800083bc  lea     rcx, pProxyInfo; pProxyInfo
0x1800083c3  call    cs:__imp_NdrClientCall3
0x1800083c9  mov     rbx, rax
0x1800083cc  mov     [rsp+0B8h+var_48], rax
0x1800083d1  mov     [rsp+0B8h+var_54], eax
0x1800083d5  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x1800083da  sub     rax, r13
0x1800083dd  mov     [rsp+0B8h+var_98], rax
0x1800083e2  lea     r9, aGetfileinfofro_0; "GetFileInfoFromPath,Time,%llu"
0x1800083e9  xor     r8d, r8d; unsigned int
0x1800083ec  xor     edx, edx; unsigned int
0x1800083ee  lea     rcx, aPcaclient; "PcaClient"
0x1800083f5  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800083fa  jmp     short loc_18000842B
0x1800083fc  mov     ebx, eax
0x1800083fe  mov     [rsp+0B8h+var_54], eax
0x180008402  mov     rsi, [rsp+0B8h+arg_18]
0x18000840a  mov     r14, [rsp+0B8h+arg_10]
0x180008412  mov     r15, [rsp+0B8h+arg_8]
0x18000841a  mov     r12, [rsp+0B8h+arg_0]
0x180008422  mov     edi, [rsp+0B8h+var_58]
0x180008426  mov     r13, [rsp+0B8h+var_40]
0x18000842b  test    ebx, ebx
0x18000842d  jz      short loc_180008465
0x18000842f  cmp     edi, 1
0x180008432  ja      short loc_180008465
0x180008434  lea     eax, [rbx-6ACh]
0x18000843a  cmp     eax, 2Dh ; '-'
0x18000843d  ja      short loc_180008465
0x18000843f  mov     rcx, 200000004201h
0x180008449  bt      rcx, rax
0x18000844d  jnb     short loc_180008465
0x18000844f  call    ?PcacpStartPCAService@@YAKXZ; PcacpStartPCAService(void)
0x180008454  mov     ebx, eax
0x180008456  inc     edi
0x180008458  mov     [rsp+0B8h+var_58], edi
0x18000845c  test    eax, eax
0x18000845e  jnz     short loc_18000842B
0x180008460  jmp     loc_180008368
0x180008465  mov     eax, ebx
0x180008467  add     rsp, 80h
0x18000846e  pop     r15
0x180008470  pop     r14
0x180008472  pop     r13
0x180008474  pop     r12
0x180008476  pop     rdi
0x180008477  pop     rsi
0x180008478  pop     rbx
0x180008479  retn
0x18000c4a6  push    rbp
0x18000c4a8  sub     rsp, 60h
0x18000c4ac  mov     rbp, rdx
0x18000c4af  mov     rcx, [rcx]
0x18000c4b2  mov     ecx, [rcx]; ExceptionCode
0x18000c4b4  call    cs:__imp_I_RpcExceptionFilter
0x18000c4ba  nop
0x18000c4bb  add     rsp, 60h
0x18000c4bf  pop     rbp
0x18000c4c0  retn
```
