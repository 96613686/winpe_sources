# EfsRpcDuplicateEncryptionInfoFile_Downlevel

- ea: `0x180007590`
- end: `0x180007744`
- name: `EfsRpcDuplicateEncryptionInfoFile_Downlevel`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007590`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000b424`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000770f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000770f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007700`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000771d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007700`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000771d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800076d4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800076d4`
- `RPCRT4!RpcImpersonateClient` at `0x180007641`
- `RPCRT4!RpcImpersonateClient` at `0x180007641`
- `RPCRT4!RpcRevertToSelf` at `0x1800076e7`
- `RPCRT4!RpcRevertToSelf` at `0x1800076e7`

## pseudocode

```c
__int64 __fastcall EfsRpcDuplicateEncryptionInfoFile_Downlevel(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        struct _EFS_RPC_BLOB *a6,
        int a7)
{
  unsigned int LocalFileName; // eax
  WCHAR *v10; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // esi
  unsigned int v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  HANDLE ProcessHeap; // rax
  void *v18; // rdi
  HANDLE v19; // rax
  int v21; // [rsp+44h] [rbp-2Ch] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-28h]
  LPVOID v23; // [rsp+50h] [rbp-20h]
  void **v24; // [rsp+58h] [rbp-18h] BYREF
  int v25; // [rsp+60h] [rbp-10h]

  v21 = 0;
  lpMem = 0;
  v23 = 0;
  if ( (unsigned int)EfsRpcpValidateClientCall(a1, &v21) || !v21 )
  {
    return 5;
  }
  else
  {
    LocalFileName = EfsGetLocalFileName(a2);
    v10 = (WCHAR *)lpMem;
    v11 = LocalFileName;
    if ( !LocalFileName )
    {
      v11 = EfsGetLocalFileName(a3);
      if ( !v11 )
      {
        v11 = RpcImpersonateClient(0);
        if ( !v11 )
        {
          v11 = EfsEnsureLocalPath(v10);
          if ( !v11 )
          {
            v12 = 0;
            v25 = 0;
            v24 = &CEfsClient::`vftable';
            do
            {
              v13 = CEfsClientBase::EfsDuplicateEncryptionInfoClient((CEfsClientBase *)&v24, a2, a3, a4, a5, a6, a7);
              v11 = v13;
              if ( !v13 )
                break;
              v14 = v13 - 1708;
              if ( (unsigned int)v14 > 0x2D || (v15 = 0x2000000CC201LL, !_bittest64(&v15, v14)) )
              {
                if ( v11 != 1460 )
                  break;
              }
              Sleep(0x12Cu);
              v16 = v12++;
            }
            while ( v16 < 3 );
            v10 = (WCHAR *)lpMem;
          }
          RpcRevertToSelf();
        }
      }
    }
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    v18 = v23;
    if ( v23 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180007590  mov     [rsp-38h+arg_0], rbx
0x180007595  mov     [rsp-38h+arg_18], r9d
0x18000759a  mov     [rsp-38h+arg_10], r8
0x18000759f  push    rbp
0x1800075a0  push    rsi
0x1800075a1  push    rdi
0x1800075a2  push    r12
0x1800075a4  push    r13
0x1800075a6  push    r14
0x1800075a8  push    r15
0x1800075aa  mov     rbp, rsp
0x1800075ad  sub     rsp, 70h
0x1800075b1  xor     r14d, r14d
0x1800075b4  mov     r13, rdx
0x1800075b7  lea     rdx, [rbp+var_2C]
0x1800075bb  mov     [rbp+var_2C], r14d
0x1800075bf  mov     [rbp+lpMem], r14
0x1800075c3  mov     rsi, r8
0x1800075c6  mov     [rbp+var_20], r14
0x1800075ca  mov     [rbp+var_30], r14w
0x1800075cf  call    EfsRpcpValidateClientCall
0x1800075d4  test    eax, eax
0x1800075d6  jnz     loc_180007725
0x1800075dc  cmp     [rbp+var_2C], r14d
0x1800075e0  jz      loc_180007725
0x1800075e6  lea     r9, [rbp+var_30]
0x1800075ea  mov     rcx, r13; unsigned __int16 *
0x1800075ed  lea     r8, [rbp+lpMem]
0x1800075f1  call    EfsGetLocalFileName
0x1800075f6  mov     rdi, [rbp+lpMem]
0x1800075fa  mov     ebx, eax
0x1800075fc  test    eax, eax
0x1800075fe  jnz     loc_1800076ED
0x180007604  lea     r15d, [r14+1]
0x180007608  cmp     [rbp+var_30], r15w
0x18000760d  jnz     short loc_180007619
0x18000760f  mov     ebx, 5
0x180007614  jmp     loc_1800076ED
0x180007619  lea     r9, [rbp+var_30]
0x18000761d  mov     [rbp+var_30], r14w
0x180007622  lea     r8, [rbp+var_20]
0x180007626  mov     rcx, rsi; unsigned __int16 *
0x180007629  call    EfsGetLocalFileName
0x18000762e  mov     ebx, eax
0x180007630  test    eax, eax
0x180007632  jnz     loc_1800076ED
0x180007638  cmp     [rbp+var_30], r15w
0x18000763d  jz      short loc_18000760F
0x18000763f  xor     ecx, ecx; BindingHandle
0x180007641  call    cs:__imp_RpcImpersonateClient
0x180007647  mov     ebx, eax
0x180007649  test    eax, eax
0x18000764b  jnz     loc_1800076ED
0x180007651  mov     rcx, rdi
0x180007654  call    EfsEnsureLocalPath
0x180007659  mov     ebx, eax
0x18000765b  test    eax, eax
0x18000765d  jnz     loc_1800076E7
0x180007663  mov     r15, [rbp+arg_28]
0x180007667  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x18000766e  mov     r12d, [rbp+arg_20]
0x180007672  mov     esi, r14d
0x180007675  mov     rdi, [rbp+arg_10]
0x180007679  mov     [rbp+var_10], r14d
0x18000767d  mov     r14d, [rbp+arg_30]
0x180007681  mov     [rbp+var_18], rax
0x180007685  mov     r9d, [rbp+arg_18]; unsigned int
0x180007689  lea     rcx, [rbp+var_18]; this
0x18000768d  mov     [rsp+70h+var_40], r14d; int
0x180007692  mov     r8, rdi; unsigned __int16 *
0x180007695  mov     [rsp+70h+var_48], r15; struct _EFS_RPC_BLOB *
0x18000769a  mov     rdx, r13; unsigned __int16 *
0x18000769d  mov     [rsp+70h+var_50], r12d; unsigned int
0x1800076a2  call    ?EfsDuplicateEncryptionInfoClient@CEfsClientBase@@QEAAKPEBG0KKPEAU_EFS_RPC_BLOB@@H@Z; CEfsClientBase::EfsDuplicateEncryptionInfoClient(ushort const *,ushort const *,ulong,ulong,_EFS_RPC_BLOB *,int)
0x1800076a7  mov     ebx, eax
0x1800076a9  test    eax, eax
0x1800076ab  jz      short loc_1800076E3
0x1800076ad  add     eax, 0FFFFF954h
0x1800076b2  cmp     eax, 2Dh ; '-'
0x1800076b5  ja      short loc_1800076C7
0x1800076b7  mov     rcx, 2000000CC201h
0x1800076c1  bt      rcx, rax
0x1800076c5  jb      short loc_1800076CF
0x1800076c7  cmp     ebx, 5B4h
0x1800076cd  jnz     short loc_1800076E3
0x1800076cf  mov     ecx, 12Ch; dwMilliseconds
0x1800076d4  call    cs:__imp_Sleep
0x1800076da  mov     eax, esi
0x1800076dc  inc     esi
0x1800076de  cmp     eax, 3
0x1800076e1  jb      short loc_180007685
0x1800076e3  mov     rdi, [rbp+lpMem]
0x1800076e7  call    cs:__imp_RpcRevertToSelf
0x1800076ed  test    rdi, rdi
0x1800076f0  jz      short loc_180007706
0x1800076f2  call    cs:__imp_GetProcessHeap
0x1800076f8  mov     r8, rdi; lpMem
0x1800076fb  xor     edx, edx; dwFlags
0x1800076fd  mov     rcx, rax; hHeap
0x180007700  call    cs:__imp_HeapFree
0x180007706  mov     rdi, [rbp+var_20]
0x18000770a  test    rdi, rdi
0x18000770d  jz      short loc_18000772A
0x18000770f  call    cs:__imp_GetProcessHeap
0x180007715  mov     r8, rdi; lpMem
0x180007718  xor     edx, edx; dwFlags
0x18000771a  mov     rcx, rax; hHeap
0x18000771d  call    cs:__imp_HeapFree
0x180007723  jmp     short loc_18000772A
0x180007725  mov     ebx, 5
0x18000772a  mov     eax, ebx
0x18000772c  mov     rbx, [rsp+70h+arg_0]
0x180007734  add     rsp, 70h
0x180007738  pop     r15
0x18000773a  pop     r14
0x18000773c  pop     r13
0x18000773e  pop     r12
0x180007740  pop     rdi
0x180007741  pop     rsi
0x180007742  pop     rbp
0x180007743  retn
```
