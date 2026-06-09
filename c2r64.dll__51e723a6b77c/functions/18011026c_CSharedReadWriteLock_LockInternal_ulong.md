# CSharedReadWriteLock::LockInternal(ulong)

- ea: `0x18011026c`
- end: `0x1801103d7`
- name: `?LockInternal@CSharedReadWriteLock@@AEAAKK@Z`
- size: `363`
- prototype: `unsigned int __fastcall(CSharedReadWriteLock *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180110200`

## callees

- `0x180110184`
- `0x18011026c`
- `0x180110828`
- `0x1801108fc`
- `0x180110a34`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801102aa`
- `KERNEL32!GetCurrentThreadId` at `0x1801102e7`
- `KERNEL32!GetCurrentThreadId` at `0x1801102aa`
- `KERNEL32!GetCurrentThreadId` at `0x1801102e7`

## pseudocode

```c
__int64 __fastcall CSharedReadWriteLock::LockInternal(CSharedReadWriteLock *this, unsigned int a2)
{
  unsigned int v4; // edi
  int v5; // edi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // r9d
  unsigned int v11; // eax

  v4 = 128;
  if ( !*(_DWORD *)(*((_QWORD *)this + 3) + 24LL) )
  {
    _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
    v5 = *(_DWORD *)(*((_QWORD *)this + 3) + 8LL);
    if ( v5 < 0
      && (CurrentThreadId = GetCurrentThreadId(), v7 = *((_QWORD *)this + 3), *(_DWORD *)(v7 + 16) == CurrentThreadId) )
    {
      _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF);
LABEL_5:
      v4 = 0;
    }
    else
    {
      while ( 1 )
      {
        v8 = *((_QWORD *)this + 3);
        if ( *(_DWORD *)(v8 + 24) )
          break;
        if ( v5 )
        {
          if ( !a2 )
          {
            v4 = 258;
            goto LABEL_24;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 4));
          v5 = *(_DWORD *)(*((_QWORD *)this + 3) + 8LL);
          if ( v5 || !(unsigned int)sub_180110184(*((_QWORD *)this + 3) + 4LL) )
          {
            if ( (byte_18021CCC1 & 1) != 0 )
            {
              v9 = *((_QWORD *)this + 3);
              v10 = -*(_DWORD *)(v9 + 8);
              if ( *(int *)(v9 + 8) > 0 )
                v10 = *(_DWORD *)(v9 + 8);
              McTemplateU0pqq_EventWriteTransfer(
                *(_DWORD *)(v9 + 8),
                (unsigned int)ReaWriteLockWriteWait,
                (_DWORD)this,
                v10,
                *(_DWORD *)(v9 + 20));
            }
            v11 = CSharedReadWriteLock::WaitForHandle(this, *((void **)this + 10), a2);
            v4 = v11;
            if ( v11 == 258 )
            {
              sub_180110184(*((_QWORD *)this + 3) + 4LL);
              goto LABEL_24;
            }
            if ( v11 == 128 )
              goto LABEL_23;
            v5 = *(_DWORD *)(*((_QWORD *)this + 3) + 8LL);
          }
        }
        else
        {
          v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), -1, 0);
          if ( !v5 )
          {
            *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = GetCurrentThreadId();
            *(_DWORD *)(*((_QWORD *)this + 3) + 12LL) = *((_DWORD *)this + 16);
            goto LABEL_5;
          }
        }
      }
      v4 = 128;
LABEL_23:
      if ( v4 == 128 )
        goto LABEL_25;
LABEL_24:
      _InterlockedAdd(*((volatile signed __int32 **)this + 4), 0xFFFFFFFF);
    }
  }
LABEL_25:
  if ( *(_DWORD *)(*((_QWORD *)this + 3) + 24LL) )
    CSharedRWHeap::WaitForRootMutex(*((CSharedRWHeap **)this + 7));
  return v4;
}

```

## disassembly

```asm
0x18011026c  mov     [rsp+arg_0], rbx
0x180110271  mov     [rsp+arg_8], rbp
0x180110276  mov     [rsp+arg_10], rsi
0x18011027b  push    rdi
0x18011027c  sub     rsp, 30h
0x180110280  mov     rax, [rcx+18h]
0x180110284  mov     ebp, edx
0x180110286  mov     rbx, rcx
0x180110289  mov     edi, 80h
0x18011028e  cmp     dword ptr [rax+18h], 0
0x180110292  jnz     loc_1801103AD
0x180110298  mov     rax, [rcx+20h]
0x18011029c  lock inc dword ptr [rax]
0x18011029f  mov     rax, [rcx+18h]
0x1801102a3  mov     edi, [rax+8]
0x1801102a6  test    edi, edi
0x1801102a8  jns     short loc_1801102C7
0x1801102aa  call    cs:__imp_GetCurrentThreadId
0x1801102b0  mov     rcx, [rbx+18h]
0x1801102b4  cmp     [rcx+10h], eax
0x1801102b7  jnz     short loc_1801102C7
0x1801102b9  or      esi, 0FFFFFFFFh
0x1801102bc  lock add [rcx+8], esi
0x1801102c0  xor     edi, edi
0x1801102c2  jmp     loc_1801103AD
0x1801102c7  or      esi, 0FFFFFFFFh
0x1801102ca  mov     rcx, [rbx+18h]
0x1801102ce  cmp     dword ptr [rcx+18h], 0
0x1801102d2  jnz     loc_180110399
0x1801102d8  test    edi, edi
0x1801102da  jnz     short loc_180110300
0x1801102dc  xor     eax, eax
0x1801102de  lock cmpxchg [rcx+8], esi
0x1801102e3  mov     edi, eax
0x1801102e5  jnz     short loc_1801102CA
0x1801102e7  call    cs:__imp_GetCurrentThreadId
0x1801102ed  mov     rcx, [rbx+18h]
0x1801102f1  mov     [rcx+10h], eax
0x1801102f4  mov     rax, [rbx+18h]
0x1801102f8  mov     ecx, [rbx+40h]
0x1801102fb  mov     [rax+0Ch], ecx
0x1801102fe  jmp     short loc_1801102C0
0x180110300  test    ebp, ebp
0x180110302  jz      loc_180110392
0x180110308  lock inc dword ptr [rcx+4]
0x18011030c  mov     rax, [rbx+18h]
0x180110310  mov     edi, [rax+8]
0x180110313  test    edi, edi
0x180110315  jnz     short loc_180110328
0x180110317  mov     rcx, [rbx+18h]
0x18011031b  add     rcx, 4
0x18011031f  call    sub_180110184
0x180110324  test    eax, eax
0x180110326  jnz     short loc_1801102CA
0x180110328  test    cs:byte_18021CCC1, 1
0x18011032f  jz      short loc_180110358
0x180110331  mov     rax, [rbx+18h]
0x180110335  mov     r8, rbx
0x180110338  mov     ecx, [rax+8]
0x18011033b  mov     r9d, ecx
0x18011033e  mov     edx, [rax+14h]
0x180110341  neg     r9d
0x180110344  mov     [rsp+38h+var_18], edx
0x180110348  lea     rdx, ReaWriteLockWriteWait
0x18011034f  cmovs   r9d, ecx
0x180110353  call    McTemplateU0pqq_EventWriteTransfer
0x180110358  mov     rdx, [rbx+50h]; void *
0x18011035c  mov     r8d, ebp; unsigned int
0x18011035f  mov     rcx, rbx; this
0x180110362  call    ?WaitForHandle@CSharedReadWriteLock@@AEAAKPEAXK@Z; CSharedReadWriteLock::WaitForHandle(void *,ulong)
0x180110367  mov     edi, eax
0x180110369  cmp     eax, 102h
0x18011036e  jz      short loc_180110383
0x180110370  cmp     eax, 80h
0x180110375  jz      short loc_18011039E
0x180110377  mov     rax, [rbx+18h]
0x18011037b  mov     edi, [rax+8]
0x18011037e  jmp     loc_1801102CA
0x180110383  mov     rcx, [rbx+18h]
0x180110387  add     rcx, 4
0x18011038b  call    sub_180110184
0x180110390  jmp     short loc_1801103A6
0x180110392  mov     edi, 102h
0x180110397  jmp     short loc_1801103A6
0x180110399  mov     edi, 80h
0x18011039e  cmp     edi, 80h
0x1801103a4  jz      short loc_1801103AD
0x1801103a6  mov     rax, [rbx+20h]
0x1801103aa  lock add [rax], esi
0x1801103ad  mov     rax, [rbx+18h]
0x1801103b1  cmp     dword ptr [rax+18h], 0
0x1801103b5  jz      short loc_1801103C0
0x1801103b7  mov     rcx, [rbx+38h]; this
0x1801103bb  call    ?WaitForRootMutex@CSharedRWHeap@@QEAAXXZ; CSharedRWHeap::WaitForRootMutex(void)
0x1801103c0  mov     rbx, [rsp+38h+arg_0]
0x1801103c5  mov     eax, edi
0x1801103c7  mov     rbp, [rsp+38h+arg_8]
0x1801103cc  mov     rsi, [rsp+38h+arg_10]
0x1801103d1  add     rsp, 30h
0x1801103d5  pop     rdi
0x1801103d6  retn
```
