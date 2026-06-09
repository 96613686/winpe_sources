# LRPC_SCALL::SaveClientToken(void * *)

- ea: `0x18007200c`
- end: `0x18007211f`
- name: `?SaveClientToken@LRPC_SCALL@@QEAAJPEAPEAX@Z`
- size: `275`
- prototype: `int(LRPC_SCALL *__hidden this, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800714f8`
- `0x180085440`
- `0x1800a77e8`

## callees

- `0x1800281b0`
- `0x1800283bc`
- `0x18007200c`
- `0x1800729f8`
- `0x180072e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072084`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007206f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007206f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007205c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007205c`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::SaveClientToken(LRPC_SCALL *this, void **a2)
{
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned __int16 v7; // r8
  void *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  v4 = CaptureThreadToken(&v9, 0);
  if ( !v4 )
  {
    v4 = LRPC_SASSOCIATION::ImpersonateClient(*((LRPC_SASSOCIATION **)this + 38), *((struct _PORT_MESSAGE **)this + 55));
    if ( v4 )
    {
      v4 = 1749;
      v7 = 1232;
      goto LABEL_13;
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, a2) )
      goto LABEL_14;
    *a2 = 0;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 1347 )
      goto LABEL_14;
    RpcpErrorAddRecord(2u, LastError, 0x4CEu, 0, 0);
    if ( v4 != 8 )
    {
      if ( v4 == 1008 )
      {
        v4 = 5;
        goto LABEL_10;
      }
      if ( v4 != 1450 && v4 != 1816 )
        goto LABEL_10;
    }
    v4 = 14;
LABEL_10:
    v7 = 1231;
LABEL_13:
    RpcpErrorAddRecord(2u, v4, v7, 0, 0);
LABEL_14:
    RestoreOldThreadToken(v9);
  }
  return v4;
}

```

## disassembly

```asm
0x18007200c  mov     rax, rsp
0x18007200f  mov     [rax+8], rbx
0x180072013  mov     [rax+10h], rsi
0x180072017  push    rdi
0x180072018  sub     rsp, 30h
0x18007201c  mov     rsi, rdx
0x18007201f  mov     qword ptr [rax+18h], 0
0x180072027  mov     rdi, rcx
0x18007202a  xor     edx, edx; int
0x18007202c  lea     rcx, [rax+18h]; TokenHandle
0x180072030  call    ?CaptureThreadToken@@YAJPEAPEAXH@Z; CaptureThreadToken(void * *,int)
0x180072035  mov     ebx, eax
0x180072037  test    eax, eax
0x180072039  jnz     loc_18007210D
0x18007203f  mov     rdx, [rdi+1B8h]; struct _PORT_MESSAGE *
0x180072046  mov     rcx, [rdi+130h]; this
0x18007204d  call    ?ImpersonateClient@LRPC_SASSOCIATION@@QEAAJPEAU_PORT_MESSAGE@@@Z; LRPC_SASSOCIATION::ImpersonateClient(_PORT_MESSAGE *)
0x180072052  mov     ebx, eax
0x180072054  test    eax, eax
0x180072056  jnz     loc_1800720E1
0x18007205c  call    cs:__imp_GetCurrentThread
0x180072062  mov     r9, rsi; TokenHandle
0x180072065  lea     edx, [rbx+0Ch]; DesiredAccess
0x180072068  mov     rcx, rax; ThreadHandle
0x18007206b  lea     r8d, [rbx+1]; OpenAsSelf
0x18007206f  call    cs:__imp_OpenThreadToken
0x180072075  test    eax, eax
0x180072077  jnz     loc_180072103
0x18007207d  mov     qword ptr [rsi], 0
0x180072084  call    cs:__imp_GetLastError
0x18007208a  mov     ebx, eax
0x18007208c  cmp     eax, 543h
0x180072091  jz      short loc_180072103
0x180072093  xor     r9d, r9d; int
0x180072096  mov     [rsp+38h+var_18], 0; struct tagParam *
0x18007209f  mov     r8d, 4CEh; unsigned __int16
0x1800720a5  mov     edx, eax; int
0x1800720a7  lea     ecx, [r9+2]; unsigned int
0x1800720ab  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800720b0  cmp     ebx, 8
0x1800720b3  jz      short loc_1800720CD
0x1800720b5  cmp     ebx, 3F0h
0x1800720bb  jz      short loc_1800720DA
0x1800720bd  cmp     ebx, 5AAh
0x1800720c3  jz      short loc_1800720CD
0x1800720c5  cmp     ebx, 718h
0x1800720cb  jnz     short loc_1800720D2
0x1800720cd  mov     ebx, 0Eh
0x1800720d2  mov     r8d, 4CFh
0x1800720d8  jmp     short loc_1800720EC
0x1800720da  mov     ebx, 5
0x1800720df  jmp     short loc_1800720D2
0x1800720e1  mov     ebx, 6D5h
0x1800720e6  mov     r8d, 4D0h; unsigned __int16
0x1800720ec  xor     r9d, r9d; int
0x1800720ef  mov     [rsp+38h+var_18], 0; struct tagParam *
0x1800720f8  mov     edx, ebx; int
0x1800720fa  lea     ecx, [r9+2]; unsigned int
0x1800720fe  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180072103  mov     rcx, [rsp+38h+arg_10]; void *
0x180072108  call    ?RestoreOldThreadToken@@YAXPEAX@Z; RestoreOldThreadToken(void *)
0x18007210d  mov     rsi, [rsp+38h+arg_8]
0x180072112  mov     eax, ebx
0x180072114  mov     rbx, [rsp+38h+arg_0]
0x180072119  add     rsp, 30h
0x18007211d  pop     rdi
0x18007211e  retn
```
