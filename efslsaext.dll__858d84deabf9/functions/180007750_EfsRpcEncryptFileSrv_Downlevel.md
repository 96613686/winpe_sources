# EfsRpcEncryptFileSrv_Downlevel

- ea: `0x180007750`
- end: `0x180007877`
- name: `EfsRpcEncryptFileSrv_Downlevel`
- size: `295`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007750`
- `0x180007d6c`
- `0x1800084e0`
- `0x180008544`
- `0x18000b808`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007845`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007845`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007854`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007854`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007828`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007828`
- `RPCRT4!RpcImpersonateClient` at `0x1800077c4`
- `RPCRT4!RpcImpersonateClient` at `0x1800077c4`
- `RPCRT4!RpcRevertToSelf` at `0x180007838`
- `RPCRT4!RpcRevertToSelf` at `0x180007838`

## pseudocode

```c
__int64 __fastcall EfsRpcEncryptFileSrv_Downlevel(void *a1, unsigned __int16 *a2)
{
  __int64 v3; // rdx
  unsigned int LocalFileName; // ebx
  unsigned int v5; // esi
  unsigned int v6; // eax
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-20h] BYREF
  void **v13; // [rsp+28h] [rbp-18h] BYREF
  int v14; // [rsp+30h] [rbp-10h]
  __int16 v15; // [rsp+70h] [rbp+30h] BYREF
  int v16; // [rsp+78h] [rbp+38h]

  v16 = 0;
  lpMem = 0;
  v15 = 0;
  if ( (unsigned int)EfsRpcpValidateClientCall(a1) || !v16 )
  {
    return 5;
  }
  else
  {
    LocalFileName = EfsGetLocalFileName(a2, v3, (unsigned __int16 **)&lpMem, &v15);
    if ( !LocalFileName )
    {
      if ( v15 == 1 )
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
            v14 = 0;
            v13 = &CEfsClient::`vftable';
            v5 = 0;
            do
            {
              v6 = CEfsClientBase::EfsEncryptFileClient((CEfsClientBase *)&v13, a2);
              LocalFileName = v6;
              if ( !v6 )
                break;
              v7 = v6 - 1708;
              if ( (unsigned int)v7 > 0x2D || (v8 = 0x2000000CC201LL, !_bittest64(&v8, v7)) )
              {
                if ( LocalFileName != 1460 )
                  break;
              }
              Sleep(0x12Cu);
              v9 = v5++;
            }
            while ( v9 < 3 );
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
0x180007750  mov     [rsp-18h+arg_0], rbx
0x180007755  mov     [rsp-18h+arg_8], rsi
0x18000775a  push    rbp
0x18000775b  push    r12
0x18000775d  push    r14
0x18000775f  mov     rbp, rsp
0x180007762  sub     rsp, 40h
0x180007766  mov     r14, rdx
0x180007769  mov     [rbp+arg_18], 0
0x180007770  xor     eax, eax
0x180007772  mov     [rbp+lpMem], 0
0x18000777a  lea     rdx, [rbp+arg_18]
0x18000777e  mov     [rbp+arg_10], ax
0x180007782  call    EfsRpcpValidateClientCall
0x180007787  test    eax, eax
0x180007789  jnz     loc_18000785C
0x18000778f  cmp     [rbp+arg_18], eax
0x180007792  jz      loc_18000785C
0x180007798  lea     r9, [rbp+arg_10]
0x18000779c  mov     rcx, r14; unsigned __int16 *
0x18000779f  lea     r8, [rbp+lpMem]
0x1800077a3  call    EfsGetLocalFileName
0x1800077a8  mov     ebx, eax
0x1800077aa  test    eax, eax
0x1800077ac  jnz     loc_18000783E
0x1800077b2  lea     r12d, [rax+1]
0x1800077b6  cmp     [rbp+arg_10], r12w
0x1800077bb  jnz     short loc_1800077C2
0x1800077bd  lea     ebx, [rax+5]
0x1800077c0  jmp     short loc_18000783E
0x1800077c2  xor     ecx, ecx; BindingHandle
0x1800077c4  call    cs:__imp_RpcImpersonateClient
0x1800077ca  mov     ebx, eax
0x1800077cc  test    eax, eax
0x1800077ce  jnz     short loc_18000783E
0x1800077d0  mov     rcx, [rbp+lpMem]
0x1800077d4  call    EfsEnsureLocalPath
0x1800077d9  mov     ebx, eax
0x1800077db  test    eax, eax
0x1800077dd  jnz     short loc_180007838
0x1800077df  lea     rax, ??_7CEfsClient@@6B@; const CEfsClient::`vftable'
0x1800077e6  mov     [rbp+var_10], ebx
0x1800077e9  mov     [rbp+var_18], rax
0x1800077ed  xor     esi, esi
0x1800077ef  mov     rdx, r14; unsigned __int16 *
0x1800077f2  lea     rcx, [rbp+var_18]; this
0x1800077f6  call    ?EfsEncryptFileClient@CEfsClientBase@@QEAAKPEBG@Z; CEfsClientBase::EfsEncryptFileClient(ushort const *)
0x1800077fb  mov     ebx, eax
0x1800077fd  test    eax, eax
0x1800077ff  jz      short loc_180007838
0x180007801  add     eax, 0FFFFF954h
0x180007806  cmp     eax, 2Dh ; '-'
0x180007809  ja      short loc_18000781B
0x18000780b  mov     rcx, 2000000CC201h
0x180007815  bt      rcx, rax
0x180007819  jb      short loc_180007823
0x18000781b  cmp     ebx, 5B4h
0x180007821  jnz     short loc_180007838
0x180007823  mov     ecx, 12Ch; dwMilliseconds
0x180007828  call    cs:__imp_Sleep
0x18000782e  mov     eax, esi
0x180007830  add     esi, r12d
0x180007833  cmp     eax, 3
0x180007836  jb      short loc_1800077EF
0x180007838  call    cs:__imp_RpcRevertToSelf
0x18000783e  cmp     [rbp+lpMem], 0
0x180007843  jz      short loc_180007861
0x180007845  call    cs:__imp_GetProcessHeap
0x18000784b  mov     r8, [rbp+lpMem]; lpMem
0x18000784f  xor     edx, edx; dwFlags
0x180007851  mov     rcx, rax; hHeap
0x180007854  call    cs:__imp_HeapFree
0x18000785a  jmp     short loc_180007861
0x18000785c  mov     ebx, 5
0x180007861  mov     rsi, [rsp+40h+arg_8]
0x180007866  mov     eax, ebx
0x180007868  mov     rbx, [rsp+40h+arg_0]
0x18000786d  add     rsp, 40h
0x180007871  pop     r14
0x180007873  pop     r12
0x180007875  pop     rbp
0x180007876  retn
```
