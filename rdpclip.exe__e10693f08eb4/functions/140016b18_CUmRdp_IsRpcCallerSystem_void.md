# CUmRdp::IsRpcCallerSystem(void)

- ea: `0x140016b18`
- end: `0x140016bc6`
- name: `?IsRpcCallerSystem@CUmRdp@@QEAAHXZ`
- size: `174`
- prototype: `__int64 __fastcall(CUmRdp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140017630`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140016b18`
- `0x140016bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016b70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140016b32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140016b32`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140016b47`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140016b47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016bb8`

## pseudocode

```c
__int64 __fastcall CUmRdp::IsRpcCallerSystem(CUmRdp *this)
{
  CUmRdp *v1; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int IsSystemToken; // ebx
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  v1 = g_pUmRdpRpc;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    IsSystemToken = CUmRdp::IsSystemToken(v1, TokenHandle);
    CloseHandle(TokenHandle);
    return IsSystemToken;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140016b18  mov     [rsp+TokenHandle], rcx
0x140016b1d  push    rbx
0x140016b1e  sub     rsp, 30h
0x140016b22  mov     rbx, cs:?g_pUmRdpRpc@@3PEAVCUmRdp@@EA; CUmRdp * g_pUmRdpRpc
0x140016b29  mov     [rsp+38h+TokenHandle], 0
0x140016b32  call    cs:__imp_GetCurrentThread
0x140016b38  xor     r8d, r8d; OpenAsSelf
0x140016b3b  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x140016b40  mov     rcx, rax; ThreadHandle
0x140016b43  lea     edx, [r8+8]; DesiredAccess
0x140016b47  call    cs:__imp_OpenThreadToken
0x140016b4d  test    eax, eax
0x140016b4f  jnz     short loc_140016BA4
0x140016b51  mov     rax, cs:WPP_GLOBAL_Control
0x140016b58  lea     rcx, WPP_GLOBAL_Control
0x140016b5f  cmp     rax, rcx
0x140016b62  jz      short loc_140016BA0
0x140016b64  test    byte ptr [rax+1Ch], 1
0x140016b68  jz      short loc_140016BA0
0x140016b6a  cmp     byte ptr [rax+19h], 2
0x140016b6e  jb      short loc_140016BA0
0x140016b70  call    cs:__imp_GetLastError
0x140016b76  mov     ebx, eax
0x140016b78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140016b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b84  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x140016b8b  mov     edx, 0Eh
0x140016b90  mov     [rsp+38h+var_18], ebx
0x140016b94  mov     r9d, eax
0x140016b97  mov     rcx, [rcx+10h]
0x140016b9b  call    WPP_SF_Dd
0x140016ba0  xor     eax, eax
0x140016ba2  jmp     short loc_140016BC0
0x140016ba4  mov     rdx, [rsp+38h+TokenHandle]; void *
0x140016ba9  mov     rcx, rbx; this
0x140016bac  call    ?IsSystemToken@CUmRdp@@IEAAHPEAX@Z; CUmRdp::IsSystemToken(void *)
0x140016bb1  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x140016bb6  mov     ebx, eax
0x140016bb8  call    cs:__imp_CloseHandle
0x140016bbe  mov     eax, ebx
0x140016bc0  add     rsp, 30h
0x140016bc4  pop     rbx
0x140016bc5  retn
```
