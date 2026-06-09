# PROTOCOL::BeginSendCommon(int *)

- ea: `0x180002f60`
- end: `0x1800030d3`
- name: `?BeginSendCommon@PROTOCOL@@AEAAJPEAH@Z`
- size: `371`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800030dc`
- `0x1800039a0`

## callees

- `0x180002f60`
- `0x180003414`
- `0x180009128`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000307e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000307e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000309d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000309d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002fef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003074`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002fef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002faf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002fc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002fc4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000306a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000306a`

## pseudocode

```c
__int64 __fastcall PROTOCOL::BeginSendCommon(PROTOCOL *this, int *a2)
{
  bool v2; // zf
  __int64 *v4; // rax
  __int64 v5; // r14
  signed int v6; // ebx
  int v7; // ebp
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // r9d
  __int64 (__fastcall *v13)(__int64, __int64, __int64, __int64, int); // rax
  void *TokenHandle; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 13) == 0;
  v4 = (__int64 *)*((_QWORD *)this + 18);
  *a2 = 0;
  v5 = *v4;
  TokenHandle = 0;
  if ( !v2 )
    goto LABEL_2;
  if ( *((_DWORD *)this + 14) )
  {
    *a2 = 1;
LABEL_2:
    v6 = -2147024883;
LABEL_25:
    FCGI_BUFFER::Free(*((FCGI_BUFFER **)this + 18));
    *((_QWORD *)this + 18) = 0;
    return (unsigned int)v6;
  }
  v7 = 0;
  if ( *((_QWORD *)this + 19) )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError != 1008 )
        goto LABEL_20;
      TokenHandle = 0;
    }
    if ( !SetThreadToken(0, *((HANDLE *)this + 19)) )
    {
LABEL_19:
      LastError = GetLastError();
      v6 = LastError;
LABEL_20:
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    v7 = 1;
  }
  v10 = v5 - 8;
  v11 = *((_QWORD *)this + 4);
  v12 = *(_DWORD *)(*((_QWORD *)this + 18) + 24LL);
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int))(*(_QWORD *)v11 + 48LL);
  if ( v12 )
  {
    v6 = v13(v11, 1, v10, (unsigned int)(v12 + 8), 1);
  }
  else
  {
    v6 = v13(v11, 1, v10, 8, 0);
    if ( v6 >= 0 )
      PROTOCOL::DispatchSendCompletion(this, 0, 0);
  }
  if ( v7 )
  {
    if ( !TokenHandle )
    {
      RevertToSelf();
      goto LABEL_22;
    }
    if ( !SetThreadToken(0, TokenHandle) )
      goto LABEL_19;
  }
LABEL_22:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v6 < 0 )
    goto LABEL_25;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002f60  push    rbx
0x180002f62  push    rbp
0x180002f63  push    rdi
0x180002f64  push    r14
0x180002f66  sub     rsp, 38h
0x180002f6a  cmp     dword ptr [rcx+34h], 0
0x180002f6e  mov     rdi, rcx
0x180002f71  mov     rax, [rcx+90h]
0x180002f78  mov     dword ptr [rdx], 0
0x180002f7e  mov     r14, [rax]
0x180002f81  mov     [rsp+58h+TokenHandle], 0
0x180002f8a  jz      short loc_180002F96
0x180002f8c  mov     ebx, 8007000Dh
0x180002f91  jmp     loc_1800030B0
0x180002f96  cmp     dword ptr [rcx+38h], 0
0x180002f9a  jz      short loc_180002FA4
0x180002f9c  mov     dword ptr [rdx], 1
0x180002fa2  jmp     short loc_180002F8C
0x180002fa4  xor     ebp, ebp
0x180002fa6  cmp     [rcx+98h], rbp
0x180002fad  jz      short loc_180003002
0x180002faf  call    cs:__imp_GetCurrentThread
0x180002fb5  mov     rcx, rax; ThreadHandle
0x180002fb8  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180002fbd  lea     edx, [rbp+4]; DesiredAccess
0x180002fc0  lea     r8d, [rbp+1]; OpenAsSelf
0x180002fc4  call    cs:__imp_OpenThreadToken
0x180002fca  test    eax, eax
0x180002fcc  jnz     short loc_180002FE6
0x180002fce  call    cs:__imp_GetLastError
0x180002fd4  mov     ebx, eax
0x180002fd6  cmp     eax, 3F0h
0x180002fdb  jnz     loc_180003086
0x180002fe1  mov     [rsp+58h+TokenHandle], rbp
0x180002fe6  mov     rdx, [rdi+98h]; Token
0x180002fed  xor     ecx, ecx; Thread
0x180002fef  call    cs:__imp_SetThreadToken
0x180002ff5  test    eax, eax
0x180002ff7  jz      loc_18000307E
0x180002ffd  mov     ebp, 1
0x180003002  mov     rax, [rdi+90h]
0x180003009  lea     r8, [r14-8]
0x18000300d  mov     rcx, [rdi+20h]
0x180003011  mov     edx, 1
0x180003016  mov     r9d, [rax+18h]
0x18000301a  mov     rax, [rcx]
0x18000301d  mov     rax, [rax+30h]
0x180003021  test    r9d, r9d
0x180003024  jnz     short loc_180003049
0x180003026  mov     [rsp+58h+var_38], r9d
0x18000302b  lea     r9d, [rdx+7]
0x18000302f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003034  mov     ebx, eax
0x180003036  test    eax, eax
0x180003038  js      short loc_18000305C
0x18000303a  xor     r8d, r8d; unsigned int
0x18000303d  xor     edx, edx; int
0x18000303f  mov     rcx, rdi; this
0x180003042  call    ?DispatchSendCompletion@PROTOCOL@@AEAAXJK@Z; PROTOCOL::DispatchSendCompletion(long,ulong)
0x180003047  jmp     short loc_18000305C
0x180003049  add     r9d, 8
0x18000304d  mov     [rsp+58h+var_38], 1
0x180003055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305a  mov     ebx, eax
0x18000305c  test    ebp, ebp
0x18000305e  jz      short loc_180003093
0x180003060  mov     rdx, [rsp+58h+TokenHandle]; Token
0x180003065  test    rdx, rdx
0x180003068  jnz     short loc_180003072
0x18000306a  call    cs:__imp_RevertToSelf
0x180003070  jmp     short loc_180003093
0x180003072  xor     ecx, ecx; Thread
0x180003074  call    cs:__imp_SetThreadToken
0x18000307a  test    eax, eax
0x18000307c  jnz     short loc_180003093
0x18000307e  call    cs:__imp_GetLastError
0x180003084  mov     ebx, eax
0x180003086  test    eax, eax
0x180003088  jle     short loc_180003093
0x18000308a  movzx   ebx, ax
0x18000308d  or      ebx, 80070000h
0x180003093  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180003098  test    rcx, rcx
0x18000309b  jz      short loc_1800030AC
0x18000309d  call    cs:__imp_CloseHandle
0x1800030a3  mov     [rsp+58h+TokenHandle], 0
0x1800030ac  test    ebx, ebx
0x1800030ae  jns     short loc_1800030C7
0x1800030b0  mov     rcx, [rdi+90h]; this
0x1800030b7  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x1800030bc  mov     qword ptr [rdi+90h], 0
0x1800030c7  mov     eax, ebx
0x1800030c9  add     rsp, 38h
0x1800030cd  pop     r14
0x1800030cf  pop     rdi
0x1800030d0  pop     rbp
0x1800030d1  pop     rbx
0x1800030d2  retn
```
