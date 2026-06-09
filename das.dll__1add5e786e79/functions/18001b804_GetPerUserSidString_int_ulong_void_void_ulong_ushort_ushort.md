# GetPerUserSidString(int,ulong,void *,void *,ulong *,ushort *,ushort * *)

- ea: `0x18001b804`
- end: `0x18001ba70`
- name: `?GetPerUserSidString@@YAJHKPEAX0PEAKPEAGPEAPEAG@Z`
- size: `620`
- prototype: `int(int, unsigned int, void *, void *, unsigned int *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bf50`

## callees

- `0x1800119b0`
- `0x1800186ac`
- `0x18001a760`
- `0x18001b0fc`
- `0x18001b804`
- `0x18001ba78`
- `0x180024d10`
- `0x180036504`
- `0x180044fe0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b88d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ba4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b88d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ba4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ba59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ba59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b8a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b8a4`
- `api-ms-win-core-handle-l1-1-0!CompareObjectHandles` at `0x18001b9f2`
- `api-ms-win-core-handle-l1-1-0!CompareObjectHandles` at `0x18001b9f2`

## string_xrefs

- `0x18001b9fc`: `RPC client's token on the calling thread`
- `0x18001ba05`: `process's token`

## pseudocode

```c
__int64 __fastcall GetPerUserSidString(
        int a1,
        int a2,
        void *a3,
        void *a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7)
{
  unsigned __int16 **v7; // r14
  int ProcessHandle; // edi
  HANDLE ProcessHeap; // rax
  unsigned __int16 **v13; // rdi
  unsigned __int16 *v14; // rax
  void *v15; // rbx
  int v16; // edx
  int v17; // r8d
  DWORD v18; // ecx
  int v19; // edx
  int v20; // r8d
  BOOL v21; // eax
  int v22; // r8d
  const wchar_t *v23; // rcx
  HANDLE v24; // rax
  __int64 v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h]
  HANDLE TokenHandle[2]; // [rsp+50h] [rbp-10h] BYREF

  v7 = a7;
  v26 = 0;
  TokenHandle[0] = 0;
  v25 = 0;
  if ( !a7 )
    return 2147500035LL;
  if ( a1 )
    goto LABEL_20;
  if ( !a6 )
  {
    if ( a5 )
    {
      v18 = *a5;
      if ( *a5 )
      {
        if ( v18 != a2 )
        {
          ProcessHandle = GetProcessHandle(v18);
          if ( ProcessHandle < 0 )
            return (unsigned int)ProcessHandle;
          ProcessHandle = GetProcessToken(v26, TokenHandle);
          if ( ProcessHandle < 0 )
            return (unsigned int)ProcessHandle;
          ProcessHandle = GetUserSidStringFromToken(TokenHandle[0], (wil::details **)&v25);
          if ( ProcessHandle < 0 )
          {
LABEL_27:
            v15 = (void *)v25;
            goto LABEL_28;
          }
          v15 = (void *)v25;
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              v19,
              v20,
              13,
              &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
              *a5,
              v25);
          goto LABEL_19;
        }
      }
    }
LABEL_20:
    ProcessHandle = GetUserSidStringFromToken(a4, (wil::details **)&v25);
    if ( ProcessHandle >= 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
        v15 = (void *)v25;
      }
      else
      {
        v21 = CompareObjectHandles(a3, a4);
        v15 = (void *)v25;
        v23 = L"process's token";
        if ( !v21 )
          v23 = (const wchar_t *)L"RPC client's token on the calling thread";
        WPP_RECORDER_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)L"RPC client's token on the calling thread",
          v22,
          14,
          &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
          v25,
          (__int64)v23);
      }
      goto LABEL_26;
    }
    goto LABEL_27;
  }
  a7 = 0;
  ProcessHandle = StringCchLengthW(a6, 0xB8u, (unsigned __int64 *)&a7);
  if ( ProcessHandle >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v13 = a7;
    v14 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2LL * (_QWORD)a7 + 2);
    v25 = (__int64)v14;
    v15 = v14;
    if ( !v14 )
    {
      ProcessHandle = -2147024882;
      goto LABEL_28;
    }
    ProcessHandle = StringCchCopyW(v14, (unsigned __int64)v13 + 1, a6);
    if ( ProcessHandle < 0 )
    {
LABEL_28:
      if ( v15 )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v15);
      }
      return (unsigned int)ProcessHandle;
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        12,
        &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
        (__int64)v15);
LABEL_19:
    if ( v15 )
    {
LABEL_26:
      *v7 = (unsigned __int16 *)v15;
      v15 = 0;
      goto LABEL_28;
    }
    goto LABEL_20;
  }
  return (unsigned int)ProcessHandle;
}

```

## disassembly

```asm
0x18001b804  push    rbp
0x18001b806  push    rbx
0x18001b807  push    rsi
0x18001b808  push    rdi
0x18001b809  push    r12
0x18001b80b  push    r14
0x18001b80d  push    r15
0x18001b80f  mov     rbp, rsp
0x18001b812  sub     rsp, 60h
0x18001b816  mov     r14, [rbp+arg_30]
0x18001b81a  mov     r15, r9
0x18001b81d  mov     [rbp+var_18], 0
0x18001b825  mov     r12, r8
0x18001b828  mov     [rbp+TokenHandle], 0
0x18001b830  mov     [rbp+var_20], 0
0x18001b838  test    r14, r14
0x18001b83b  jnz     short loc_18001B847
0x18001b83d  mov     eax, 80004003h
0x18001b842  jmp     loc_18001BA61
0x18001b847  lea     rbx, WPP_RECORDER_INITIALIZED
0x18001b84e  lea     rsi, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001b855  test    ecx, ecx
0x18001b857  jnz     loc_18001B9D1
0x18001b85d  mov     rsi, [rbp+arg_28]
0x18001b861  test    rsi, rsi
0x18001b864  jz      loc_18001B919
0x18001b86a  lea     r8, [rbp+arg_30]; unsigned __int64 *
0x18001b86e  mov     [rbp+arg_30], 0
0x18001b876  mov     edx, 0B8h; unsigned __int64
0x18001b87b  mov     rcx, rsi; unsigned __int16 *
0x18001b87e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001b883  mov     edi, eax
0x18001b885  test    eax, eax
0x18001b887  js      loc_18001BA5F
0x18001b88d  call    cs:__imp_GetProcessHeap
0x18001b893  mov     rdi, [rbp+arg_30]
0x18001b897  xor     edx, edx; dwFlags
0x18001b899  mov     rcx, rax; hHeap
0x18001b89c  lea     r8, ds:2[rdi*2]; dwBytes
0x18001b8a4  call    cs:__imp_HeapAlloc
0x18001b8aa  mov     [rbp+var_20], rax
0x18001b8ae  mov     rbx, rax
0x18001b8b1  test    rax, rax
0x18001b8b4  jnz     short loc_18001B8C0
0x18001b8b6  mov     edi, 8007000Eh
0x18001b8bb  jmp     loc_18001BA46
0x18001b8c0  lea     rdx, [rdi+1]; unsigned __int64
0x18001b8c4  mov     r8, rsi; unsigned __int16 *
0x18001b8c7  mov     rcx, rbx; unsigned __int16 *
0x18001b8ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b8cf  mov     edi, eax
0x18001b8d1  test    eax, eax
0x18001b8d3  js      loc_18001BA46
0x18001b8d9  lea     rax, WPP_RECORDER_INITIALIZED
0x18001b8e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001b8e7  lea     rsi, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001b8ee  jz      loc_18001B9BC
0x18001b8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8fb  mov     r9d, 0Ch; int
0x18001b901  mov     qword ptr [rsp+60h+var_38], rbx; __int64
0x18001b906  mov     [rsp+60h+MessageGuid], rsi; MessageGuid
0x18001b90b  mov     rcx, [rcx+28h]; int
0x18001b90f  call    WPP_RECORDER_SF_S
0x18001b914  jmp     loc_18001B9BC
0x18001b919  mov     rsi, [rbp+arg_20]
0x18001b91d  test    rsi, rsi
0x18001b920  jz      loc_18001B9CA
0x18001b926  mov     ecx, [rsi]; dwProcessId
0x18001b928  test    ecx, ecx
0x18001b92a  jz      loc_18001B9CA
0x18001b930  cmp     ecx, edx
0x18001b932  jz      loc_18001B9CA
0x18001b938  lea     rdx, [rbp+var_18]
0x18001b93c  call    GetProcessHandle
0x18001b941  mov     edi, eax
0x18001b943  test    eax, eax
0x18001b945  js      loc_18001BA5F
0x18001b94b  mov     rcx, [rbp+var_18]
0x18001b94f  lea     rdx, [rbp+TokenHandle]
0x18001b953  call    GetProcessToken
0x18001b958  mov     edi, eax
0x18001b95a  test    eax, eax
0x18001b95c  js      loc_18001BA5F
0x18001b962  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001b966  lea     rdx, [rbp+var_20]
0x18001b96a  call    GetUserSidStringFromToken
0x18001b96f  mov     edi, eax
0x18001b971  test    eax, eax
0x18001b973  js      loc_18001BA42
0x18001b979  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18001b980  mov     rbx, [rbp+var_20]
0x18001b984  jz      short loc_18001B9B5
0x18001b986  mov     eax, [rsi]
0x18001b988  mov     r9d, 0Dh; int
0x18001b98e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b995  lea     rsi, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001b99c  mov     [rsp+60h+var_30], rbx; __int64
0x18001b9a1  mov     dword ptr [rsp+60h+var_38], eax; char
0x18001b9a5  mov     [rsp+60h+MessageGuid], rsi; MessageGuid
0x18001b9aa  mov     rcx, [rcx+28h]; int
0x18001b9ae  call    WPP_RECORDER_SF_dS
0x18001b9b3  jmp     short loc_18001B9BC
0x18001b9b5  lea     rsi, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001b9bc  test    rbx, rbx
0x18001b9bf  jnz     short loc_18001BA3B
0x18001b9c1  lea     rbx, WPP_RECORDER_INITIALIZED
0x18001b9c8  jmp     short loc_18001B9D1
0x18001b9ca  lea     rsi, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001b9d1  lea     rdx, [rbp+var_20]
0x18001b9d5  mov     rcx, r15; TokenHandle
0x18001b9d8  call    GetUserSidStringFromToken
0x18001b9dd  mov     edi, eax
0x18001b9df  test    eax, eax
0x18001b9e1  js      short loc_18001BA42
0x18001b9e3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18001b9ea  jz      short loc_18001BA37
0x18001b9ec  mov     rdx, r15; hSecondObjectHandle
0x18001b9ef  mov     rcx, r12; hFirstObjectHandle
0x18001b9f2  call    cs:__imp_CompareObjectHandles
0x18001b9f8  mov     rbx, [rbp+var_20]
0x18001b9fc  lea     rdx, aRpcClientSToke; "RPC client's token on the calling threa"...
0x18001ba03  test    eax, eax
0x18001ba05  lea     rcx, aProcessSToken; "process's token"
0x18001ba0c  mov     r9d, 0Eh; int
0x18001ba12  cmovz   rcx, rdx
0x18001ba16  mov     [rsp+60h+var_30], rcx; __int64
0x18001ba1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba22  mov     qword ptr [rsp+60h+var_38], rbx; __int64
0x18001ba27  mov     [rsp+60h+MessageGuid], rsi; MessageGuid
0x18001ba2c  mov     rcx, [rcx+28h]; int
0x18001ba30  call    WPP_RECORDER_SF_SS
0x18001ba35  jmp     short loc_18001BA3B
0x18001ba37  mov     rbx, [rbp+var_20]
0x18001ba3b  mov     [r14], rbx
0x18001ba3e  xor     ebx, ebx
0x18001ba40  jmp     short loc_18001BA46
0x18001ba42  mov     rbx, [rbp+var_20]
0x18001ba46  test    rbx, rbx
0x18001ba49  jz      short loc_18001BA5F
0x18001ba4b  call    cs:__imp_GetProcessHeap
0x18001ba51  mov     r8, rbx; lpMem
0x18001ba54  xor     edx, edx; dwFlags
0x18001ba56  mov     rcx, rax; hHeap
0x18001ba59  call    cs:__imp_HeapFree
0x18001ba5f  mov     eax, edi
0x18001ba61  add     rsp, 60h
0x18001ba65  pop     r15
0x18001ba67  pop     r14
0x18001ba69  pop     r12
0x18001ba6b  pop     rdi
0x18001ba6c  pop     rsi
0x18001ba6d  pop     rbx
0x18001ba6e  pop     rbp
0x18001ba6f  retn
```
