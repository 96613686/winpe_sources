# OnEnumCeremoniesCompleteStub(ulong,_CEREMONY const *,long,void *)

- ea: `0x14000b494`
- end: `0x14000b5cb`
- name: `?OnEnumCeremoniesCompleteStub@@YAJKPEBU_CEREMONY@@JPEAX@Z`
- size: `311`
- prototype: `__int64 __fastcall(unsigned int, const struct _CEREMONY *, int, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c760`
- `0x140017ad0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x14000b494`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b54c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b54c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b581`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b581`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b578`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b578`

## pseudocode

```c
__int64 __fastcall OnEnumCeremoniesCompleteStub(unsigned int a1, const struct _CEREMONY *a2, int a3, void *a4)
{
  __int64 v5; // rdi
  size_t v7; // rdi
  void *v8; // rcx
  _DWORD *v9; // rax
  struct _RPC_ASYNC_STATE *v10; // rcx
  int v11; // edx
  int v12; // r8d
  int v14; // [rsp+28h] [rbp-30h]
  unsigned int Reply; // [rsp+70h] [rbp+18h] BYREF

  v5 = a1;
  Reply = a3;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      43,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
    a3 = Reply;
  }
  if ( !a3 && (_DWORD)v5 )
  {
    **((_QWORD **)a4 + 14) = 0;
    **((_DWORD **)a4 + 13) = v5;
    v7 = 20 * v5;
    **((_QWORD **)a4 + 14) = DAF_user_alloc(v7);
    v8 = (void *)**((_QWORD **)a4 + 14);
    if ( v8 )
    {
      memcpy_0(v8, a2, v7);
    }
    else
    {
      v9 = (_DWORD *)*((_QWORD *)a4 + 13);
      Reply = -2147024882;
      *v9 = 0;
    }
  }
  AcquireSRWLockExclusive((PSRWLOCK)a4 + 21);
  if ( *((_DWORD *)a4 + 40) )
  {
    Reply = -2147418113;
  }
  else
  {
    v10 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a4 + 12);
    *((_DWORD *)a4 + 40) = 1;
    RpcAsyncCompleteCall(v10, &Reply);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)a4 + 21);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v11,
      v12,
      44,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v14,
      Reply);
  return Reply;
}

```

## disassembly

```asm
0x14000b494  mov     rax, rsp
0x14000b497  mov     [rax+8], rbx
0x14000b49b  mov     [rax+10h], rsi
0x14000b49f  push    rdi
0x14000b4a0  push    r14
0x14000b4a2  push    r15
0x14000b4a4  sub     rsp, 40h
0x14000b4a8  mov     rbx, r9
0x14000b4ab  mov     edi, ecx
0x14000b4ad  mov     rsi, rdx
0x14000b4b0  mov     [rax+18h], r8d
0x14000b4b4  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b4bb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b4c2  lea     r15, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000b4c9  jz      short loc_14000B4EA
0x14000b4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4d2  mov     r9d, 2Bh ; '+'; int
0x14000b4d8  mov     [rax-38h], r15
0x14000b4dc  mov     rcx, [rcx+28h]; int
0x14000b4e0  call    WPP_RECORDER_SF_s
0x14000b4e5  mov     r8d, [rsp+58h+Reply]
0x14000b4ea  test    r8d, r8d
0x14000b4ed  jnz     short loc_14000B542
0x14000b4ef  test    edi, edi
0x14000b4f1  jz      short loc_14000B542
0x14000b4f3  mov     rax, [rbx+70h]
0x14000b4f7  mov     qword ptr [rax], 0
0x14000b4fe  mov     rax, [rbx+68h]
0x14000b502  mov     [rax], edi
0x14000b504  lea     rdi, [rdi+rdi*4]
0x14000b508  shl     rdi, 2
0x14000b50c  mov     rcx, rdi
0x14000b50f  call    DAF_user_alloc
0x14000b514  mov     rcx, [rbx+70h]
0x14000b518  mov     [rcx], rax
0x14000b51b  mov     rax, [rbx+70h]
0x14000b51f  mov     rcx, [rax]; void *
0x14000b522  test    rcx, rcx
0x14000b525  jnz     short loc_14000B537
0x14000b527  mov     rax, [rbx+68h]
0x14000b52b  mov     [rsp+58h+Reply], 8007000Eh
0x14000b533  mov     [rax], ecx
0x14000b535  jmp     short loc_14000B542
0x14000b537  mov     r8, rdi; Size
0x14000b53a  mov     rdx, rsi; Src
0x14000b53d  call    memcpy_0
0x14000b542  lea     rdi, [rbx+0A8h]
0x14000b549  mov     rcx, rdi; SRWLock
0x14000b54c  call    cs:__imp_AcquireSRWLockExclusive
0x14000b552  cmp     dword ptr [rbx+0A0h], 0
0x14000b559  jz      short loc_14000B565
0x14000b55b  mov     [rsp+58h+Reply], 8000FFFFh
0x14000b563  jmp     short loc_14000B57E
0x14000b565  mov     rcx, [rbx+60h]; pAsync
0x14000b569  lea     rdx, [rsp+58h+Reply]; Reply
0x14000b56e  mov     dword ptr [rbx+0A0h], 1
0x14000b578  call    cs:__imp_RpcAsyncCompleteCall
0x14000b57e  mov     rcx, rdi; SRWLock
0x14000b581  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b587  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b58e  jz      short loc_14000B5B3
0x14000b590  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b597  mov     r9d, 2Ch ; ','; int
0x14000b59d  mov     eax, [rsp+58h+Reply]
0x14000b5a1  mov     dword ptr [rsp+58h+var_28], eax; char
0x14000b5a5  mov     [rsp+58h+MessageGuid], r15; MessageGuid
0x14000b5aa  mov     rcx, [rcx+28h]; int
0x14000b5ae  call    WPP_RECORDER_SF_sd
0x14000b5b3  mov     eax, [rsp+58h+Reply]
0x14000b5b7  mov     rbx, [rsp+58h+arg_0]
0x14000b5bc  mov     rsi, [rsp+58h+arg_8]
0x14000b5c1  add     rsp, 40h
0x14000b5c5  pop     r15
0x14000b5c7  pop     r14
0x14000b5c9  pop     rdi
0x14000b5ca  retn
```
