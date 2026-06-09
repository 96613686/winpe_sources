# OnFinalizeCompleteStub(int,ulong,_DEVPROPERTY * const,ulong,ushort const * *,ulong,long,void *)

- ea: `0x14000b5d4`
- end: `0x14000b7bc`
- name: `?OnFinalizeCompleteStub@@YAJHKQEAU_DEVPROPERTY@@KPEAPEBGKJPEAX@Z`
- size: `488`
- prototype: `__int64 __fastcall(int, unsigned int, struct _DEVPROPERTY *const, unsigned int, const unsigned __int16 **, unsigned int, unsigned int Reply, RTL_SRWLOCK *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000c840`
- `0x140017bf0`

## callees

- `0x1400020d0`
- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x140009090`
- `0x14000b5d4`
- `0x14000be64`
- `0x140019c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b70d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b70d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b748`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b748`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b73f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000b73f`

## pseudocode

```c
__int64 __fastcall OnFinalizeCompleteStub(
        int a1,
        unsigned int a2,
        struct _DEVPROPERTY *const a3,
        unsigned int a4,
        const unsigned __int16 **a5,
        unsigned int a6,
        unsigned int Reply,
        RTL_SRWLOCK *a8)
{
  unsigned int v8; // eax
  __int64 v11; // rsi
  _QWORD *v13; // rdi
  RTL_SRWLOCK *v14; // rbx
  _QWORD *v15; // rax
  __int64 v16; // rbp
  struct _RPC_ASYNC_STATE *Ptr; // rcx
  int v18; // edx
  int v19; // r8d
  __int64 i; // rbx
  void *v21; // rcx
  int v23; // [rsp+28h] [rbp-60h]

  v8 = Reply;
  v11 = a4;
  v13 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      49,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
    v8 = Reply;
  }
  v14 = a8;
  if ( !v8 )
  {
    *(_DWORD *)a8[16].Ptr = a1;
    if ( a2 )
    {
      *(_QWORD *)v14[14].Ptr = 0;
      Reply = MidlCopyDevProperties(a3, a2, (struct _DEVPROPERTY **)v14[14].Ptr);
      if ( Reply )
        goto LABEL_15;
      *(_DWORD *)v14[13].Ptr = a2;
    }
    if ( (_DWORD)v11 )
    {
      v15 = (_QWORD *)DAF_user_alloc(8 * v11);
      v13 = v15;
      if ( v15 )
      {
        memset_0(v15, 0, 8 * v11);
        v16 = 0;
        while ( 1 )
        {
          Reply = DafStringCopy((unsigned __int16 *)a5[v16]);
          if ( (Reply & 0x80000000) != 0 )
            break;
          v16 = (unsigned int)(v16 + 1);
          if ( (unsigned int)v16 >= (unsigned int)v11 )
          {
            *(_DWORD *)v14[17].Ptr = v11;
            *(_QWORD *)v14[18].Ptr = v13;
            goto LABEL_14;
          }
        }
      }
      else
      {
        Reply = -2147024882;
      }
    }
    else
    {
LABEL_14:
      v13 = 0;
      *(_DWORD *)v14[19].Ptr = a6;
    }
  }
LABEL_15:
  AcquireSRWLockExclusive(v14 + 21);
  if ( LODWORD(v14[20].Ptr) )
  {
    Reply = -2147418113;
  }
  else
  {
    Ptr = (struct _RPC_ASYNC_STATE *)v14[12].Ptr;
    LODWORD(v14[20].Ptr) = 1;
    RpcAsyncCompleteCall(Ptr, &Reply);
  }
  ReleaseSRWLockExclusive(v14 + 21);
  if ( v13 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v11; i = (unsigned int)(i + 1) )
    {
      v21 = (void *)v13[i];
      if ( v21 )
        MIDL_user_free(v21);
    }
    MIDL_user_free(v13);
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      50,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v23,
      Reply);
  return Reply;
}

```

## disassembly

```asm
0x14000b5d4  mov     r11, rsp
0x14000b5d7  push    rbx
0x14000b5d8  push    rbp
0x14000b5d9  push    rsi
0x14000b5da  push    rdi
0x14000b5db  push    r12
0x14000b5dd  push    r13
0x14000b5df  push    r14
0x14000b5e1  push    r15
0x14000b5e3  sub     rsp, 48h
0x14000b5e7  mov     eax, [rsp+88h+Reply]
0x14000b5ee  mov     r15, r8
0x14000b5f1  mov     [r11+38h], eax
0x14000b5f5  mov     ebp, edx
0x14000b5f7  mov     esi, r9d
0x14000b5fa  mov     r14d, ecx
0x14000b5fd  xor     edi, edi
0x14000b5ff  lea     r12, WPP_RECORDER_INITIALIZED
0x14000b606  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b60d  lea     r13, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000b614  jz      short loc_14000B635
0x14000b616  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b61d  lea     r9d, [rdi+31h]; int
0x14000b621  mov     [r11-68h], r13
0x14000b625  mov     rcx, [rcx+28h]; int
0x14000b629  call    WPP_RECORDER_SF_s
0x14000b62e  mov     eax, [rsp+88h+Reply]
0x14000b635  mov     rbx, [rsp+88h+arg_38]
0x14000b63d  test    eax, eax
0x14000b63f  jnz     loc_14000B703
0x14000b645  mov     rax, [rbx+80h]
0x14000b64c  mov     [rax], r14d
0x14000b64f  test    ebp, ebp
0x14000b651  jz      short loc_14000B67D
0x14000b653  mov     rax, [rbx+70h]
0x14000b657  mov     edx, ebp; unsigned int
0x14000b659  mov     rcx, r15; struct _DEVPROPERTY *
0x14000b65c  mov     [rax], rdi
0x14000b65f  mov     r8, [rbx+70h]; struct _DEVPROPERTY **
0x14000b663  call    ?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z; MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)
0x14000b668  mov     [rsp+88h+Reply], eax
0x14000b66f  test    eax, eax
0x14000b671  jnz     loc_14000B703
0x14000b677  mov     rax, [rbx+68h]
0x14000b67b  mov     [rax], ebp
0x14000b67d  test    esi, esi
0x14000b67f  jz      short loc_14000B6F1
0x14000b681  mov     rbp, rsi
0x14000b684  shl     rbp, 3
0x14000b688  mov     rcx, rbp
0x14000b68b  call    DAF_user_alloc
0x14000b690  mov     rdi, rax
0x14000b693  test    rax, rax
0x14000b696  jnz     short loc_14000B6A5
0x14000b698  mov     [rsp+88h+Reply], 8007000Eh
0x14000b6a3  jmp     short loc_14000B703
0x14000b6a5  mov     r14, [rsp+88h+arg_20]
0x14000b6ad  mov     r8, rbp; Size
0x14000b6b0  xor     edx, edx; Val
0x14000b6b2  mov     rcx, rdi; void *
0x14000b6b5  call    memset_0
0x14000b6ba  xor     ebp, ebp
0x14000b6bc  test    esi, esi
0x14000b6be  jz      short loc_14000B6DE
0x14000b6c0  mov     rcx, [r14+rbp*8]; unsigned __int16 *
0x14000b6c4  lea     rdx, [rdi+rbp*8]
0x14000b6c8  call    DafStringCopy
0x14000b6cd  mov     [rsp+88h+Reply], eax
0x14000b6d4  test    eax, eax
0x14000b6d6  js      short loc_14000B703
0x14000b6d8  inc     ebp
0x14000b6da  cmp     ebp, esi
0x14000b6dc  jb      short loc_14000B6C0
0x14000b6de  mov     rax, [rbx+88h]
0x14000b6e5  mov     [rax], esi
0x14000b6e7  mov     rax, [rbx+90h]
0x14000b6ee  mov     [rax], rdi
0x14000b6f1  mov     rcx, [rbx+98h]
0x14000b6f8  xor     edi, edi
0x14000b6fa  mov     eax, [rsp+88h+arg_28]
0x14000b701  mov     [rcx], eax
0x14000b703  lea     rbp, [rbx+0A8h]
0x14000b70a  mov     rcx, rbp; SRWLock
0x14000b70d  call    cs:__imp_AcquireSRWLockExclusive
0x14000b713  cmp     dword ptr [rbx+0A0h], 0
0x14000b71a  jz      short loc_14000B729
0x14000b71c  mov     [rsp+88h+Reply], 8000FFFFh
0x14000b727  jmp     short loc_14000B745
0x14000b729  mov     rcx, [rbx+60h]; pAsync
0x14000b72d  lea     rdx, [rsp+88h+Reply]; Reply
0x14000b735  mov     dword ptr [rbx+0A0h], 1
0x14000b73f  call    cs:__imp_RpcAsyncCompleteCall
0x14000b745  mov     rcx, rbp; SRWLock
0x14000b748  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b74e  test    rdi, rdi
0x14000b751  jz      short loc_14000B775
0x14000b753  xor     ebx, ebx
0x14000b755  test    esi, esi
0x14000b757  jz      short loc_14000B76D
0x14000b759  mov     rcx, [rdi+rbx*8]; void *
0x14000b75d  test    rcx, rcx
0x14000b760  jz      short loc_14000B767
0x14000b762  call    MIDL_user_free
0x14000b767  inc     ebx
0x14000b769  cmp     ebx, esi
0x14000b76b  jb      short loc_14000B759
0x14000b76d  mov     rcx, rdi; void *
0x14000b770  call    MIDL_user_free
0x14000b775  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000b77c  jz      short loc_14000B7A4
0x14000b77e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b785  mov     r9d, 32h ; '2'; int
0x14000b78b  mov     eax, [rsp+88h+Reply]
0x14000b792  mov     dword ptr [rsp+88h+var_58], eax; char
0x14000b796  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x14000b79b  mov     rcx, [rcx+28h]; int
0x14000b79f  call    WPP_RECORDER_SF_sd
0x14000b7a4  mov     eax, [rsp+88h+Reply]
0x14000b7ab  add     rsp, 48h
0x14000b7af  pop     r15
0x14000b7b1  pop     r14
0x14000b7b3  pop     r13
0x14000b7b5  pop     r12
0x14000b7b7  pop     rdi
0x14000b7b8  pop     rsi
0x14000b7b9  pop     rbp
0x14000b7ba  pop     rbx
0x14000b7bb  retn
```
