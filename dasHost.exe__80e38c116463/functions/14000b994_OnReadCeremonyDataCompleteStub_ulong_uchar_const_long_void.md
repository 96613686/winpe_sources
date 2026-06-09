# OnReadCeremonyDataCompleteStub(ulong,uchar const *,long,void *)

- ea: `0x14000b994`
- end: `0x14000bac3`
- name: `?OnReadCeremonyDataCompleteStub@@YAJKPEBEJPEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(size_t Size, const unsigned __int8 *Src, int, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c970`
- `0x140018300`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x14000b994`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ba44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ba44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ba79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ba79`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000ba70`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000ba70`

## pseudocode

```c
__int64 __fastcall OnReadCeremonyDataCompleteStub(size_t Size, const unsigned __int8 *Src, int a3, void *a4)
{
  size_t v5; // rdi
  void *v7; // rcx
  _DWORD *v8; // rax
  struct _RPC_ASYNC_STATE *v9; // rcx
  int v10; // edx
  int v11; // r8d
  int v13; // [rsp+28h] [rbp-30h]
  unsigned int Reply; // [rsp+70h] [rbp+18h] BYREF

  v5 = (unsigned int)Size;
  Reply = a3;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)Src,
      a3,
      45,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
    a3 = Reply;
  }
  if ( !a3 && (_DWORD)v5 )
  {
    **((_DWORD **)a4 + 13) = v5;
    **((_QWORD **)a4 + 14) = 0;
    **((_QWORD **)a4 + 14) = DAF_user_alloc(v5);
    v7 = (void *)**((_QWORD **)a4 + 14);
    if ( v7 )
    {
      memcpy_0(v7, Src, v5);
    }
    else
    {
      v8 = (_DWORD *)*((_QWORD *)a4 + 13);
      Reply = -2147024882;
      *v8 = 0;
    }
  }
  AcquireSRWLockExclusive((PSRWLOCK)a4 + 21);
  if ( *((_DWORD *)a4 + 40) )
  {
    Reply = -2147418113;
  }
  else
  {
    v9 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a4 + 12);
    *((_DWORD *)a4 + 40) = 1;
    RpcAsyncCompleteCall(v9, &Reply);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)a4 + 21);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v10,
      v11,
      46,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v13,
      Reply);
  return Reply;
}

```

## disassembly

```asm
0x14000b994  mov     rax, rsp
0x14000b997  mov     [rax+8], rbx
0x14000b99b  mov     [rax+10h], rsi
0x14000b99f  push    rdi
0x14000b9a0  push    r14
0x14000b9a2  push    r15
0x14000b9a4  sub     rsp, 40h
0x14000b9a8  mov     rbx, r9
0x14000b9ab  mov     edi, ecx
0x14000b9ad  mov     rsi, rdx
0x14000b9b0  mov     [rax+18h], r8d
0x14000b9b4  lea     r14, WPP_RECORDER_INITIALIZED
0x14000b9bb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000b9c2  lea     r15, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000b9c9  jz      short loc_14000B9EA
0x14000b9cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9d2  mov     r9d, 2Dh ; '-'; int
0x14000b9d8  mov     [rax-38h], r15
0x14000b9dc  mov     rcx, [rcx+28h]; int
0x14000b9e0  call    WPP_RECORDER_SF_s
0x14000b9e5  mov     r8d, [rsp+58h+Reply]
0x14000b9ea  test    r8d, r8d
0x14000b9ed  jnz     short loc_14000BA3A
0x14000b9ef  test    edi, edi
0x14000b9f1  jz      short loc_14000BA3A
0x14000b9f3  mov     rax, [rbx+68h]
0x14000b9f7  mov     rcx, rdi
0x14000b9fa  mov     [rax], edi
0x14000b9fc  mov     rax, [rbx+70h]
0x14000ba00  mov     qword ptr [rax], 0
0x14000ba07  call    DAF_user_alloc
0x14000ba0c  mov     rcx, [rbx+70h]
0x14000ba10  mov     [rcx], rax
0x14000ba13  mov     rax, [rbx+70h]
0x14000ba17  mov     rcx, [rax]; void *
0x14000ba1a  test    rcx, rcx
0x14000ba1d  jnz     short loc_14000BA2F
0x14000ba1f  mov     rax, [rbx+68h]
0x14000ba23  mov     [rsp+58h+Reply], 8007000Eh
0x14000ba2b  mov     [rax], ecx
0x14000ba2d  jmp     short loc_14000BA3A
0x14000ba2f  mov     r8, rdi; Size
0x14000ba32  mov     rdx, rsi; Src
0x14000ba35  call    memcpy_0
0x14000ba3a  lea     rdi, [rbx+0A8h]
0x14000ba41  mov     rcx, rdi; SRWLock
0x14000ba44  call    cs:__imp_AcquireSRWLockExclusive
0x14000ba4a  cmp     dword ptr [rbx+0A0h], 0
0x14000ba51  jz      short loc_14000BA5D
0x14000ba53  mov     [rsp+58h+Reply], 8000FFFFh
0x14000ba5b  jmp     short loc_14000BA76
0x14000ba5d  mov     rcx, [rbx+60h]; pAsync
0x14000ba61  lea     rdx, [rsp+58h+Reply]; Reply
0x14000ba66  mov     dword ptr [rbx+0A0h], 1
0x14000ba70  call    cs:__imp_RpcAsyncCompleteCall
0x14000ba76  mov     rcx, rdi; SRWLock
0x14000ba79  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ba7f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000ba86  jz      short loc_14000BAAB
0x14000ba88  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ba8f  mov     r9d, 2Eh ; '.'; int
0x14000ba95  mov     eax, [rsp+58h+Reply]
0x14000ba99  mov     dword ptr [rsp+58h+var_28], eax; char
0x14000ba9d  mov     [rsp+58h+MessageGuid], r15; MessageGuid
0x14000baa2  mov     rcx, [rcx+28h]; int
0x14000baa6  call    WPP_RECORDER_SF_sd
0x14000baab  mov     eax, [rsp+58h+Reply]
0x14000baaf  mov     rbx, [rsp+58h+arg_0]
0x14000bab4  mov     rsi, [rsp+58h+arg_8]
0x14000bab9  add     rsp, 40h
0x14000babd  pop     r15
0x14000babf  pop     r14
0x14000bac1  pop     rdi
0x14000bac2  retn
```
