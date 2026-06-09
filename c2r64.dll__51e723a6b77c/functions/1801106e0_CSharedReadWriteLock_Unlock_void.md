# CSharedReadWriteLock::Unlock(void)

- ea: `0x1801106e0`
- end: `0x180110828`
- name: `?Unlock@CSharedReadWriteLock@@UEAAHXZ`
- size: `328`
- prototype: `__int64 __fastcall(CSharedReadWriteLock *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800264b4`
- `0x180110184`
- `0x1801106e0`
- `0x180110a34`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18011077c`
- `KERNEL32!ReleaseSemaphore` at `0x1801107c8`
- `KERNEL32!ReleaseSemaphore` at `0x18011077c`
- `KERNEL32!ReleaseSemaphore` at `0x1801107c8`
- `KERNEL32!GetCurrentThreadId` at `0x180110720`
- `KERNEL32!GetCurrentThreadId` at `0x180110720`

## pseudocode

```c
__int64 __fastcall CSharedReadWriteLock::Unlock(CSharedReadWriteLock *this)
{
  __int64 v1; // rax
  unsigned int v3; // esi
  volatile __int32 **v4; // r9
  int v5; // ebp
  volatile __int32 **v6; // rbx
  LONG v7; // edx
  volatile __int32 *v8; // rax
  int v9; // ecx
  int v10; // r9d
  int PreviousCount; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 1);
  PreviousCount = 0;
  v3 = 1;
  if ( *(_DWORD *)(v1 + 24) )
  {
    v4 = (volatile __int32 **)((char *)this + 8);
    goto LABEL_18;
  }
  v5 = *(_DWORD *)(v1 + 8);
  v6 = (volatile __int32 **)((char *)this + 8);
  if ( v5 >= 0 )
  {
    v4 = (volatile __int32 **)((char *)this + 8);
    if ( _InterlockedExchangeAdd(*v6 + 2, 0xFFFFFFFF) == 1 && (unsigned int)sub_180110184(*v6 + 1) )
    {
LABEL_16:
      v3 = ReleaseSemaphore(*((HANDLE *)this + 8), 1, &PreviousCount);
LABEL_17:
      v4 = v6;
    }
  }
  else
  {
    if ( *((_DWORD *)*v6 + 4) != GetCurrentThreadId() )
      MsoShipAssertTagProc(507553218);
    if ( v5 == -1 )
    {
      *((_DWORD *)*v6 + 4) = 0;
      *((_DWORD *)*v6 + 3) = 0;
    }
    v4 = v6;
    if ( !_InterlockedIncrement(*v6 + 2) )
    {
      if ( **v6 )
      {
        v7 = _InterlockedExchange(*v6, 0);
        if ( v7 )
          v3 = ReleaseSemaphore(*((HANDLE *)this + 7), v7, &PreviousCount);
      }
      if ( !(unsigned int)sub_180110184(*v6 + 1) )
        goto LABEL_17;
      goto LABEL_16;
    }
  }
LABEL_18:
  if ( !*((_DWORD *)*v4 + 6) )
    _InterlockedDecrement(*((volatile signed __int32 **)this + 2));
  if ( (byte_18021CCC1 & 1) != 0 )
  {
    v8 = *v4;
    v9 = *((_DWORD *)*v4 + 2);
    v10 = -v9;
    if ( v9 > 0 )
      v10 = v9;
    McTemplateU0pqq_EventWriteTransfer(
      v9,
      (unsigned int)ReaWriteLockRelease,
      (_DWORD)this - 16,
      v10,
      *((_DWORD *)v8 + 5));
  }
  return v3;
}

```

## disassembly

```asm
0x1801106e0  mov     [rsp+arg_10], rbx
0x1801106e5  mov     [rsp+arg_18], rbp
0x1801106ea  push    rsi
0x1801106eb  push    rdi
0x1801106ec  push    r14
0x1801106ee  sub     rsp, 30h
0x1801106f2  mov     rax, [rcx+8]
0x1801106f6  mov     rdi, rcx
0x1801106f9  mov     [rsp+48h+PreviousCount], 0
0x180110701  mov     esi, 1
0x180110706  cmp     dword ptr [rax+18h], 0
0x18011070a  jz      short loc_180110715
0x18011070c  lea     r9, [rcx+8]
0x180110710  jmp     loc_1801107D3
0x180110715  mov     ebp, [rax+8]
0x180110718  lea     rbx, [rcx+8]
0x18011071c  test    ebp, ebp
0x18011071e  jns     short loc_18011079B
0x180110720  call    cs:__imp_GetCurrentThreadId
0x180110726  mov     ecx, eax
0x180110728  mov     rax, [rbx]
0x18011072b  cmp     [rax+10h], ecx
0x18011072e  jz      short loc_18011073A
0x180110730  mov     ecx, 1E40A5C2h
0x180110735  call    MsoShipAssertTagProc
0x18011073a  cmp     ebp, 0FFFFFFFFh
0x18011073d  jnz     short loc_180110753
0x18011073f  mov     rax, [rbx]
0x180110742  mov     dword ptr [rax+10h], 0
0x180110749  mov     rax, [rbx]
0x18011074c  mov     dword ptr [rax+0Ch], 0
0x180110753  mov     rcx, [rbx]
0x180110756  lock inc dword ptr [rcx+8]
0x18011075a  mov     r9, rbx
0x18011075d  jnz     short loc_1801107D3
0x18011075f  mov     rax, [rbx]
0x180110762  mov     ecx, [rax]
0x180110764  test    ecx, ecx
0x180110766  jz      short loc_180110784
0x180110768  mov     rax, [rbx]
0x18011076b  xor     edx, edx
0x18011076d  xchg    edx, [rax]; lReleaseCount
0x18011076f  test    edx, edx
0x180110771  jz      short loc_180110784
0x180110773  mov     rcx, [rdi+38h]; hSemaphore
0x180110777  lea     r8, [rsp+48h+PreviousCount]; lpPreviousCount
0x18011077c  call    cs:__imp_ReleaseSemaphore
0x180110782  mov     esi, eax
0x180110784  mov     rcx, [rbx]
0x180110787  add     rcx, 4
0x18011078b  call    sub_180110184
0x180110790  test    eax, eax
0x180110792  jz      short loc_1801107D0
0x180110794  mov     edx, 1
0x180110799  jmp     short loc_1801107BF
0x18011079b  mov     rcx, [rbx]
0x18011079e  or      eax, 0FFFFFFFFh
0x1801107a1  lock xadd [rcx+8], eax
0x1801107a6  mov     r9, rbx
0x1801107a9  cmp     eax, esi
0x1801107ab  jnz     short loc_1801107D3
0x1801107ad  mov     rcx, [rbx]
0x1801107b0  add     rcx, 4
0x1801107b4  call    sub_180110184
0x1801107b9  test    eax, eax
0x1801107bb  jz      short loc_1801107D3
0x1801107bd  mov     edx, esi; lReleaseCount
0x1801107bf  mov     rcx, [rdi+40h]; hSemaphore
0x1801107c3  lea     r8, [rsp+48h+PreviousCount]; lpPreviousCount
0x1801107c8  call    cs:__imp_ReleaseSemaphore
0x1801107ce  mov     esi, eax
0x1801107d0  mov     r9, rbx
0x1801107d3  mov     rax, [r9]
0x1801107d6  cmp     dword ptr [rax+18h], 0
0x1801107da  jnz     short loc_1801107E3
0x1801107dc  mov     rax, [rdi+10h]
0x1801107e0  lock dec dword ptr [rax]
0x1801107e3  test    cs:byte_18021CCC1, 1
0x1801107ea  jz      short loc_180110813
0x1801107ec  mov     rax, [r9]
0x1801107ef  lea     r8, [rdi-10h]
0x1801107f3  mov     ecx, [rax+8]
0x1801107f6  mov     r9d, ecx
0x1801107f9  mov     edx, [rax+14h]
0x1801107fc  neg     r9d
0x1801107ff  mov     [rsp+48h+var_28], edx
0x180110803  lea     rdx, ReaWriteLockRelease
0x18011080a  cmovs   r9d, ecx
0x18011080e  call    McTemplateU0pqq_EventWriteTransfer
0x180110813  mov     rbx, [rsp+48h+arg_10]
0x180110818  mov     eax, esi
0x18011081a  mov     rbp, [rsp+48h+arg_18]
0x18011081f  add     rsp, 30h
0x180110823  pop     r14
0x180110825  pop     rdi
0x180110826  pop     rsi
0x180110827  retn
```
