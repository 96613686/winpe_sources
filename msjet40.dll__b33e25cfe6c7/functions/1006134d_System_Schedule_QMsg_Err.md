# System::Schedule(QMsg *,Err &)

- ea: `0x1006134d`
- end: `0x1006144f`
- name: `?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z`
- size: `258`
- prototype: `void __thiscall(struct QMsg *, struct Err *)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x100565d5`
- `0x100570f9`
- `0x10060d63`
- `0x10061460`
- `0x100749f5`

## callees

- `0x1006134d`
- `0x10061846`
- `0x10074bb1`
- `0x10077909`
- `0x10077b24`
- `0x10077b8f`
- `0x10122f60`
- `0x10123aaa`
- `0x10123ae2`
- `0x10123af8`
- `0x10123b03`
- `0x10123e98`
- `0x10123f5f`
- `0x10123f8e`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x100613d3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x100613d3`

## pseudocode

```c
void __thiscall System::Schedule(struct QMsg *this, struct Err *a2, struct Err *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  Thread *v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // eax
  void *v10; // ebx
  int (__stdcall *v11)(void *); // [esp-4h] [ebp-24h]
  Thread *Block; // [esp+10h] [ebp-10h]

  if ( *((_DWORD *)this + 6) )
    goto LABEL_9;
  v4 = 4 * *((_DWORD *)this + 5);
  if ( !is_mul_ok(4u, *((_DWORD *)this + 5)) )
    v4 = -1;
  v5 = 0;
  *((_DWORD *)this + 6) = operator new[](v4);
  if ( !*((_DWORD *)this + 5) )
  {
LABEL_9:
    if ( !*((_DWORD *)a2 + 2) || Collection::IsMember(*((_DWORD *)this + 21), *((_DWORD *)a2 + 2)) )
      Queue::AddMessage(*((Queue **)this + 7), a2, a3);
    else
      Err::SetError(a3, -1010, v8);
  }
  else
  {
    while ( 1 )
    {
      Block = (Thread *)operator new(4u);
      v6 = Thread::Thread(Block, v11, this, a3);
      v7 = *((_DWORD *)this + 6);
      *(_DWORD *)(v7 + 4 * v5) = v6;
      if ( !*(_DWORD *)(*((_DWORD *)this + 6) + 4 * v5) )
        Err::SetError(a3, -1011, v7);
      if ( (*(_BYTE *)a3 & 8) != 0 )
        break;
      _InterlockedIncrement((volatile signed __int32 *)this + 26);
      ResumeThread(**(HANDLE **)(*((_DWORD *)this + 6) + 4 * v5++));
      if ( v5 >= *((_DWORD *)this + 5) )
        goto LABEL_9;
    }
    v9 = *((_DWORD *)this + 6);
    v10 = *(void **)(v9 + 4 * v5);
    if ( v10 )
    {
      Thread::~Thread(*(Thread **)(v9 + 4 * v5));
      operator delete(v10, 4u);
    }
    *(_DWORD *)(*((_DWORD *)this + 6) + 4 * v5) = 0;
    if ( !v5 )
    {
      operator delete[](*((void **)this + 6));
      *((_DWORD *)this + 6) = 0;
    }
  }
}

```

## disassembly

```asm
0x1006134d  push    4
0x1006134f  mov     eax, offset loc_101262BC
0x10061354  call    __EH_prolog3
0x10061359  mov     esi, ecx
0x1006135b  cmp     dword ptr [esi+18h], 0
0x1006135f  mov     ebx, [ebp+arg_4]
0x10061362  jnz     short loc_100613DF
0x10061364  mov     eax, [esi+14h]
0x10061367  push    4
0x10061369  pop     ecx
0x1006136a  mul     ecx
0x1006136c  push    0FFFFFFFFh
0x1006136e  pop     ecx
0x1006136f  cmovb   eax, ecx
0x10061372  push    eax; unsigned int
0x10061373  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10061378  xor     edi, edi
0x1006137a  mov     [esi+18h], eax
0x1006137d  pop     ecx
0x1006137e  cmp     [esi+14h], edi
0x10061381  jbe     short loc_100613DF
0x10061383  push    4; Size
0x10061385  call    ??2@YAPAXI@Z; operator new(uint)
0x1006138a  pop     ecx
0x1006138b  mov     [ebp+Block], eax
0x1006138e  push    ebx; struct Err *
0x1006138f  push    esi; lpParameter
0x10061390  push    ecx; int (__stdcall *)(void *)
0x10061391  mov     ecx, eax; this
0x10061393  mov     [ebp+var_4], 0
0x1006139a  call    ??0Thread@@QAE@P6GHPAX@Z0AAVErr@@@Z; Thread::Thread(int (*)(void *),void *,Err &)
0x1006139f  mov     [ebp+var_4], 0FFFFFFFFh
0x100613a6  mov     ecx, [esi+18h]
0x100613a9  mov     [ecx+edi*4], eax
0x100613ac  mov     eax, [esi+18h]
0x100613af  cmp     dword ptr [eax+edi*4], 0
0x100613b3  jnz     short loc_100613C2
0x100613b5  push    ecx
0x100613b6  push    0FFFFFC0Dh
0x100613bb  mov     ecx, ebx
0x100613bd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100613c2  test    byte ptr [ebx], 8
0x100613c5  jnz     short loc_10061406
0x100613c7  lock inc dword ptr [esi+68h]
0x100613cb  mov     eax, [esi+18h]
0x100613ce  mov     eax, [eax+edi*4]
0x100613d1  push    dword ptr [eax]; hThread
0x100613d3  call    ds:__imp__ResumeThread@4; ResumeThread(x)
0x100613d9  inc     edi
0x100613da  cmp     edi, [esi+14h]
0x100613dd  jb      short loc_10061383
0x100613df  mov     edi, [ebp+arg_0]
0x100613e2  cmp     dword ptr [edi+8], 0
0x100613e6  jz      short loc_1006143D
0x100613e8  push    dword ptr [edi+8]
0x100613eb  mov     ecx, [esi+54h]
0x100613ee  call    ?IsMember@Collection@@QAE?AW4CollBool@@PBX@Z; Collection::IsMember(void const *)
0x100613f3  test    eax, eax
0x100613f5  jnz     short loc_1006143D
0x100613f7  push    ecx
0x100613f8  push    0FFFFFC0Eh
0x100613fd  mov     ecx, ebx
0x100613ff  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10061404  jmp     short loc_10061447
0x10061406  mov     eax, [esi+18h]
0x10061409  mov     ebx, [eax+edi*4]
0x1006140c  test    ebx, ebx
0x1006140e  jz      short loc_10061421
0x10061410  mov     ecx, ebx; this
0x10061412  call    ??1Thread@@QAE@XZ; Thread::~Thread(void)
0x10061417  push    4; unsigned int
0x10061419  push    ebx; Block
0x1006141a  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006141f  pop     ecx
0x10061420  pop     ecx
0x10061421  mov     eax, [esi+18h]
0x10061424  mov     dword ptr [eax+edi*4], 0
0x1006142b  test    edi, edi
0x1006142d  jnz     short loc_10061447
0x1006142f  push    dword ptr [esi+18h]; Block
0x10061432  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10061437  pop     ecx
0x10061438  mov     [esi+18h], edi
0x1006143b  jmp     short loc_10061447
0x1006143d  mov     ecx, [esi+1Ch]; this
0x10061440  push    ebx; struct Err *
0x10061441  push    edi; struct QMsg *
0x10061442  call    ?AddMessage@Queue@@QAEXPAVQMsg@@AAVErr@@@Z; Queue::AddMessage(QMsg *,Err &)
0x10061447  call    __EH_epilog3
0x1006144c  retn    8
0x101262aa  push    4; unsigned int
0x101262ac  push    [ebp+Block]; Block
0x101262af  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x101262b4  pop     ecx
0x101262b5  pop     ecx
0x101262b6  retn
0x101262bc  nop
0x101262bd  nop
0x101262be  mov     edx, [esp-4+arg_4]
0x101262c2  lea     eax, [edx+0Ch]
0x101262c5  mov     ecx, [edx-14h]
0x101262c8  xor     ecx, eax; StackCookie
0x101262ca  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101262cf  mov     eax, offset stru_10128A1C
0x101262d4  jmp     ___CxxFrameHandler3
```
