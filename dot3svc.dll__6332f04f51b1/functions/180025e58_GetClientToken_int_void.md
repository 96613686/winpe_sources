# GetClientToken(int,void * *)

- ea: `0x180025e58`
- end: `0x180025fcc`
- name: `?GetClientToken@@YAKHPEAPEAX@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180014d90`
- `0x180027790`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180025e58`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180025ea7`
- `RPCRT4!RpcImpersonateClient` at `0x180025ea7`
- `RPCRT4!RpcRevertToSelf` at `0x180025f31`
- `RPCRT4!RpcRevertToSelf` at `0x180025f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025eff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025ede`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025ede`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025ef5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025ef5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025f7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025f7d`

## pseudocode

```c
__int64 __fastcall GetClientToken(__int64 a1, void **a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v9; // rax
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 29, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids);
  }
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v6 = 30;
LABEL_20:
      WPP_SF_d(v5[1].Flink, v6, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids, v3);
      v5 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 31, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids, LastError);
      }
    }
    v3 = RpcRevertToSelf();
    v4 = v3;
    if ( !v3 )
    {
      v9 = TokenHandle;
      v5 = WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v6 = 32;
      goto LABEL_20;
    }
  }
  v9 = TokenHandle;
  if ( !TokenHandle )
  {
LABEL_24:
    *a2 = v9;
    goto LABEL_25;
  }
  CloseHandle(TokenHandle);
  v5 = WPP_GLOBAL_Control;
LABEL_25:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v5[1].Blink) >= 4u && (BYTE4(v5[1].Blink) & 1) != 0 )
    WPP_SF_d(v5[1].Flink, 33, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180025e58  push    rbx
0x180025e5a  push    rbp
0x180025e5b  push    rdi
0x180025e5c  push    r14
0x180025e5e  sub     rsp, 28h
0x180025e62  mov     rdi, rdx
0x180025e65  mov     [rsp+48h+TokenHandle], 0
0x180025e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e75  lea     rbp, WPP_GLOBAL_Control
0x180025e7c  lea     r14, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids
0x180025e83  cmp     rcx, rbp
0x180025e86  jz      short loc_180025EA5
0x180025e88  cmp     byte ptr [rcx+19h], 4
0x180025e8c  jb      short loc_180025EA5
0x180025e8e  test    byte ptr [rcx+1Ch], 1
0x180025e92  jz      short loc_180025EA5
0x180025e94  mov     rcx, [rcx+10h]
0x180025e98  mov     edx, 1Dh
0x180025e9d  mov     r8, r14
0x180025ea0  call    WPP_SF_
0x180025ea5  xor     ecx, ecx; BindingHandle
0x180025ea7  call    cs:__imp_RpcImpersonateClient
0x180025ead  mov     ebx, eax
0x180025eaf  test    eax, eax
0x180025eb1  jz      short loc_180025EDE
0x180025eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180025eba  cmp     rcx, rbp
0x180025ebd  jz      loc_180025F70
0x180025ec3  cmp     byte ptr [rcx+19h], 1
0x180025ec7  jb      loc_180025F70
0x180025ecd  test    byte ptr [rcx+1Ch], 1
0x180025ed1  jz      loc_180025F70
0x180025ed7  mov     edx, 1Eh
0x180025edc  jmp     short loc_180025F5A
0x180025ede  call    cs:__imp_GetCurrentThread
0x180025ee4  mov     edx, 0Eh; DesiredAccess
0x180025ee9  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180025eee  mov     rcx, rax; ThreadHandle
0x180025ef1  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180025ef5  call    cs:__imp_OpenThreadToken
0x180025efb  test    eax, eax
0x180025efd  jnz     short loc_180025F31
0x180025eff  call    cs:__imp_GetLastError
0x180025f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f0c  cmp     rcx, rbp
0x180025f0f  jz      short loc_180025F31
0x180025f11  cmp     byte ptr [rcx+19h], 1
0x180025f15  jb      short loc_180025F31
0x180025f17  test    byte ptr [rcx+1Ch], 1
0x180025f1b  jz      short loc_180025F31
0x180025f1d  mov     rcx, [rcx+10h]
0x180025f21  mov     edx, 1Fh
0x180025f26  mov     r9d, eax
0x180025f29  mov     r8, r14
0x180025f2c  call    WPP_SF_d
0x180025f31  call    cs:__imp_RpcRevertToSelf
0x180025f37  mov     ebx, eax
0x180025f39  test    eax, eax
0x180025f3b  jz      short loc_180025F8C
0x180025f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f44  cmp     rcx, rbp
0x180025f47  jz      short loc_180025F70
0x180025f49  cmp     byte ptr [rcx+19h], 1
0x180025f4d  jb      short loc_180025F70
0x180025f4f  test    byte ptr [rcx+1Ch], 1
0x180025f53  jz      short loc_180025F70
0x180025f55  mov     edx, 20h ; ' '
0x180025f5a  mov     rcx, [rcx+10h]
0x180025f5e  mov     r9d, eax
0x180025f61  mov     r8, r14
0x180025f64  call    WPP_SF_d
0x180025f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f70  mov     rax, [rsp+48h+TokenHandle]
0x180025f75  test    rax, rax
0x180025f78  jz      short loc_180025F98
0x180025f7a  mov     rcx, rax; hObject
0x180025f7d  call    cs:__imp_CloseHandle
0x180025f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f8a  jmp     short loc_180025F9B
0x180025f8c  mov     rax, [rsp+48h+TokenHandle]
0x180025f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f98  mov     [rdi], rax
0x180025f9b  cmp     rcx, rbp
0x180025f9e  jz      short loc_180025FC0
0x180025fa0  cmp     byte ptr [rcx+19h], 4
0x180025fa4  jb      short loc_180025FC0
0x180025fa6  test    byte ptr [rcx+1Ch], 1
0x180025faa  jz      short loc_180025FC0
0x180025fac  mov     rcx, [rcx+10h]
0x180025fb0  mov     edx, 21h ; '!'
0x180025fb5  mov     r9d, ebx
0x180025fb8  mov     r8, r14
0x180025fbb  call    WPP_SF_d
0x180025fc0  mov     eax, ebx
0x180025fc2  add     rsp, 28h
0x180025fc6  pop     r14
0x180025fc8  pop     rdi
0x180025fc9  pop     rbp
0x180025fca  pop     rbx
0x180025fcb  retn
```
