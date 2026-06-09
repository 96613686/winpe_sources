# EfsRpcFileKeyInfo_Downlevel

- ea: `0x180007890`
- end: `0x1800079b8`
- name: `EfsRpcFileKeyInfo_Downlevel`
- size: `296`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned int, struct _EFS_RPC_BLOB **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007890`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000ba38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000798c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000798c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000799b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000799b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007970`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007970`
- `RPCRT4!RpcImpersonateClient` at `0x180007906`
- `RPCRT4!RpcImpersonateClient` at `0x180007906`
- `RPCRT4!RpcRevertToSelf` at `0x18000797f`
- `RPCRT4!RpcRevertToSelf` at `0x18000797f`

## pseudocode

```c
__int64 __fastcall EfsRpcFileKeyInfo_Downlevel(
        void *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        struct _EFS_RPC_BLOB **a4)
{
  __int64 v7; // rdx
  unsigned int LocalFileName; // ebx
  unsigned int v9; // esi
  unsigned int v10; // eax
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  HANDLE ProcessHeap; // rax
  _WORD v16[2]; // [rsp+20h] [rbp-28h] BYREF
  int v17; // [rsp+24h] [rbp-24h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-20h] BYREF
  void **v19; // [rsp+30h] [rbp-18h] BYREF
  int v20; // [rsp+38h] [rbp-10h]

  v17 = 0;
  lpMem = 0;
  v16[0] = 0;
  if ( (unsigned int)EfsRpcpValidateClientCall(a1, &v17) || !v17 )
  {
    return 5;
  }
  else
  {
    LocalFileName = EfsGetLocalFileName(a2, v7, (unsigned __int16 **)&lpMem, v16);
    if ( !LocalFileName )
    {
      if ( v16[0] == 1 )
      {
        LocalFileName = 5;
      }
      else
      {
        LocalFileName = RpcImpersonateClient(0);
        if ( !LocalFileName )
        {
          LocalFileName = EfsEnsureLocalPath((const WCHAR *)lpMem);
          if ( !LocalFileName )
          {
            v20 = 0;
            v19 = &CEfsClient::`vftable';
            v9 = 0;
            do
            {
              v10 = CEfsClientBase::EfsFileKeyInfoClient((CEfsClientBase *)&v19, a2, a3, a4);
              LocalFileName = v10;
              if ( !v10 )
                break;
              v11 = v10 - 1708;
              if ( (unsigned int)v11 > 0x2D || (v12 = 0x2000000CC201LL, !_bittest64(&v12, v11)) )
              {
                if ( LocalFileName != 1460 )
                  break;
              }
              Sleep(0x12Cu);
              v13 = v9++;
            }
            while ( v13 < 3 );
          }
          RpcRevertToSelf();
        }
      }
    }
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return LocalFileName;
}

```

## disassembly

```asm
0x180007890  push    rbp
0x180007892  push    rbx
0x180007893  push    rsi
0x180007894  push    r12
0x180007896  push    r14
0x180007898  push    r15
0x18000789a  mov     rbp, rsp
0x18000789d  sub     rsp, 48h
0x1800078a1  mov     r14, rdx
0x1800078a4  mov     [rbp+var_24], 0
0x1800078ab  xor     eax, eax
0x1800078ad  mov     [rbp+lpMem], 0
0x1800078b5  lea     rdx, [rbp+var_24]
0x1800078b9  mov     [rbp+var_28], ax
0x1800078bd  mov     r15, r9
0x1800078c0  mov     r12d, r8d
0x1800078c3  call    EfsRpcpValidateClientCall
0x1800078c8  test    eax, eax
0x1800078ca  jnz     loc_1800079A3
0x1800078d0  cmp     [rbp+var_24], eax
0x1800078d3  jz      loc_1800079A3
0x1800078d9  lea     r9, [rbp+var_28]
0x1800078dd  mov     rcx, r14; unsigned __int16 *
0x1800078e0  lea     r8, [rbp+lpMem]
0x1800078e4  call    EfsGetLocalFileName
0x1800078e9  mov     ebx, eax
0x1800078eb  test    eax, eax
0x1800078ed  jnz     loc_180007985
0x1800078f3  lea     eax, [rbx+1]
0x1800078f6  cmp     [rbp+var_28], ax
0x1800078fa  jnz     short loc_180007904
0x1800078fc  lea     ebx, [rax+4]
0x1800078ff  jmp     loc_180007985
0x180007904  xor     ecx, ecx; BindingHandle
0x180007906  call    cs:__imp_RpcImpersonateClient
0x18000790c  mov     ebx, eax
0x18000790e  test    eax, eax
0x180007910  jnz     short loc_180007985
0x180007912  mov     rcx, [rbp+lpMem]
0x180007916  call    EfsEnsureLocalPath
0x18000791b  mov     ebx, eax
0x18000791d  test    eax, eax
0x18000791f  jnz     short loc_18000797F
0x180007921  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x180007928  mov     [rbp+var_10], ebx
0x18000792b  mov     [rbp+var_18], rax
0x18000792f  xor     esi, esi
0x180007931  mov     r9, r15; struct _EFS_RPC_BLOB **
0x180007934  lea     rcx, [rbp+var_18]; this
0x180007938  mov     r8d, r12d; unsigned int
0x18000793b  mov     rdx, r14; unsigned __int16 *
0x18000793e  call    ?EfsFileKeyInfoClient@CEfsClientBase@@QEAAKPEBGKPEAPEAU_EFS_RPC_BLOB@@@Z; CEfsClientBase::EfsFileKeyInfoClient(ushort const *,ulong,_EFS_RPC_BLOB * *)
0x180007943  mov     ebx, eax
0x180007945  test    eax, eax
0x180007947  jz      short loc_18000797F
0x180007949  add     eax, 0FFFFF954h
0x18000794e  cmp     eax, 2Dh ; '-'
0x180007951  ja      short loc_180007963
0x180007953  mov     rcx, 2000000CC201h
0x18000795d  bt      rcx, rax
0x180007961  jb      short loc_18000796B
0x180007963  cmp     ebx, 5B4h
0x180007969  jnz     short loc_18000797F
0x18000796b  mov     ecx, 12Ch; dwMilliseconds
0x180007970  call    cs:__imp_Sleep
0x180007976  mov     eax, esi
0x180007978  inc     esi
0x18000797a  cmp     eax, 3
0x18000797d  jb      short loc_180007931
0x18000797f  call    cs:__imp_RpcRevertToSelf
0x180007985  cmp     [rbp+lpMem], 0
0x18000798a  jz      short loc_1800079A8
0x18000798c  call    cs:__imp_GetProcessHeap
0x180007992  mov     r8, [rbp+lpMem]; lpMem
0x180007996  xor     edx, edx; dwFlags
0x180007998  mov     rcx, rax; hHeap
0x18000799b  call    cs:__imp_HeapFree
0x1800079a1  jmp     short loc_1800079A8
0x1800079a3  mov     ebx, 5
0x1800079a8  mov     eax, ebx
0x1800079aa  add     rsp, 48h
0x1800079ae  pop     r15
0x1800079b0  pop     r14
0x1800079b2  pop     r12
0x1800079b4  pop     rsi
0x1800079b5  pop     rbx
0x1800079b6  pop     rbp
0x1800079b7  retn
```
