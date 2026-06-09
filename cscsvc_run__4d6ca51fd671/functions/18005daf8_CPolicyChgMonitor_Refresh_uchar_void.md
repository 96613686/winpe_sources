# CPolicyChgMonitor::Refresh(uchar,void *)

- ea: `0x18005daf8`
- end: `0x18005dc9a`
- name: `?Refresh@CPolicyChgMonitor@@QEAAJEPEAX@Z`
- size: `418`
- prototype: `int(CPolicyChgMonitor *__hidden this, unsigned __int8, void *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e320`
- `0x180061e10`
- `0x180061e40`

## callees

- `0x18000d640`
- `0x18001b150`
- `0x18001be00`
- `0x180029dd0`
- `0x18003e928`
- `0x18005daf8`
- `0x18005e948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005db62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005dbab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005db62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005dbab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005db82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dc54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005db82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dc54`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005dc1f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005dc1f`

## pseudocode

```c
__int64 __fastcall CPolicyChgMonitor::Refresh(CPolicyChgMonitor *this, unsigned __int8 a2, void *a3)
{
  int v5; // esi
  CWaitableOperation *v6; // rbx
  __int64 v7; // r14
  _QWORD *v8; // rdi
  void *v9; // r9
  int v10; // eax
  unsigned int i; // ebx
  __int64 v12; // rcx
  void *v13; // rdx
  __int64 j; // rbp
  SIZE_T dwBytes; // [rsp+60h] [rbp+8h] BYREF
  void *v17; // [rsp+78h] [rbp+20h] BYREF

  dwBytes = (SIZE_T)this;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids, a2, a3 != 0);
  }
  if ( a2 )
  {
    v7 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)&NumOfElements + 4));
    v8 = 0;
    v17 = 0;
    dwBytes = 0;
    v5 = ULongLongMult((unsigned int)dword_1800B6DC0, 8u, &dwBytes);
    if ( v5 >= 0 )
    {
      v10 = CscUtil_HeapAlloc(dwBytes, 1, &v17, v9);
      v8 = v17;
      v5 = v10;
    }
    if ( v5 >= 0 )
    {
      for ( i = 0; i < (unsigned int)dword_1800B6DC0; ++i )
      {
        if ( !a3 || EqualSid(*(PSID *)(*((_QWORD *)Base + 2 * i + 1) + 216LL), a3) )
        {
          v12 = *((_QWORD *)Base + 2 * i + 1);
          v8[v7] = v12;
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
          v7 = (unsigned int)(v7 + 1);
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)&NumOfElements + 4));
    if ( v8 )
    {
      for ( j = 0; (unsigned int)j < (unsigned int)v7; j = (unsigned int)(j + 1) )
      {
        CWaitableOperation::Signal((CWaitableOperation *)v8[j]);
        CRefCounted::ReleaseReference((CRefCounted *)v8[j]);
      }
      CscUtil_HeapFree(v8, v13);
    }
  }
  else
  {
    v5 = 0;
    v6 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)&NumOfElements + 4));
    if ( qword_1800B6DB0 )
    {
      v6 = (CWaitableOperation *)qword_1800B6DB0;
      _InterlockedIncrement((volatile signed __int32 *)(qword_1800B6DB0 + 8));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)&NumOfElements + 4));
    if ( v6 )
    {
      v5 = CWaitableOperation::Signal(v6);
      CRefCounted::ReleaseReference(v6);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005daf8  mov     [rsp+arg_8], rbx
0x18005dafd  mov     [rsp+dwBytes], rcx
0x18005db02  push    rbp
0x18005db03  push    rsi
0x18005db04  push    rdi
0x18005db05  push    r14
0x18005db07  push    r15
0x18005db09  sub     rsp, 30h
0x18005db0d  mov     r15, r8
0x18005db10  movzx   ebx, dl
0x18005db13  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db1a  lea     rax, WPP_GLOBAL_Control
0x18005db21  cmp     rcx, rax
0x18005db24  jz      short loc_18005DB53
0x18005db26  test    dword ptr [rcx+1Ch], 10000h
0x18005db2d  jz      short loc_18005DB53
0x18005db2f  mov     rcx, [rcx+10h]
0x18005db33  xor     eax, eax
0x18005db35  test    r8, r8
0x18005db38  mov     r9d, ebx
0x18005db3b  mov     edx, 35h ; '5'
0x18005db40  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005db47  setnz   al
0x18005db4a  mov     [rsp+58h+var_38], eax
0x18005db4e  call    WPP_SF_dd
0x18005db53  lea     rcx, NumOfElements+4; lpCriticalSection
0x18005db5a  test    bl, bl
0x18005db5c  jnz     short loc_18005DBA8
0x18005db5e  xor     esi, esi
0x18005db60  xor     ebx, ebx
0x18005db62  call    cs:__imp_EnterCriticalSection
0x18005db68  mov     rax, cs:qword_1800B6DB0
0x18005db6f  test    rax, rax
0x18005db72  jz      short loc_18005DB7B
0x18005db74  mov     rbx, rax
0x18005db77  lock inc dword ptr [rax+8]
0x18005db7b  lea     rcx, NumOfElements+4; lpCriticalSection
0x18005db82  call    cs:__imp_LeaveCriticalSection
0x18005db88  test    rbx, rbx
0x18005db8b  jz      loc_18005DC87
0x18005db91  mov     rcx, rbx; this
0x18005db94  call    ?Signal@CWaitableOperation@@QEAAJXZ; CWaitableOperation::Signal(void)
0x18005db99  mov     rcx, rbx; this
0x18005db9c  mov     esi, eax
0x18005db9e  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18005dba3  jmp     loc_18005DC87
0x18005dba8  xor     r14d, r14d
0x18005dbab  call    cs:__imp_EnterCriticalSection
0x18005dbb1  mov     ecx, cs:dword_1800B6DC0; unsigned __int64
0x18005dbb7  lea     r8, [rsp+58h+dwBytes]; unsigned __int64 *
0x18005dbbc  xor     edi, edi
0x18005dbbe  mov     [rsp+58h+arg_18], rdi
0x18005dbc3  mov     [rsp+58h+dwBytes], rdi
0x18005dbc8  lea     edx, [rdi+8]; unsigned __int64
0x18005dbcb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005dbd0  mov     esi, eax
0x18005dbd2  test    eax, eax
0x18005dbd4  js      short loc_18005DBEF
0x18005dbd6  mov     rcx, [rsp+58h+dwBytes]; dwBytes
0x18005dbdb  lea     r8, [rsp+58h+arg_18]; void **
0x18005dbe0  lea     edx, [rdi+1]; int
0x18005dbe3  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18005dbe8  mov     rdi, [rsp+58h+arg_18]
0x18005dbed  mov     esi, eax
0x18005dbef  test    esi, esi
0x18005dbf1  js      short loc_18005DC4D
0x18005dbf3  xor     ebx, ebx
0x18005dbf5  cmp     cs:dword_1800B6DC0, ebx
0x18005dbfb  jbe     short loc_18005DC4D
0x18005dbfd  mov     ebp, ebx
0x18005dbff  test    r15, r15
0x18005dc02  jz      short loc_18005DC29
0x18005dc04  mov     rax, cs:Base
0x18005dc0b  mov     ecx, ebp
0x18005dc0d  add     rcx, rcx
0x18005dc10  mov     rdx, r15; pSid2
0x18005dc13  mov     rcx, [rax+rcx*8+8]
0x18005dc18  mov     rcx, [rcx+0D8h]; pSid1
0x18005dc1f  call    cs:__imp_EqualSid
0x18005dc25  test    eax, eax
0x18005dc27  jz      short loc_18005DC43
0x18005dc29  mov     rax, cs:Base
0x18005dc30  add     rbp, rbp
0x18005dc33  mov     rcx, [rax+rbp*8+8]
0x18005dc38  mov     [rdi+r14*8], rcx
0x18005dc3c  lock inc dword ptr [rcx+8]
0x18005dc40  inc     r14d
0x18005dc43  inc     ebx
0x18005dc45  cmp     ebx, cs:dword_1800B6DC0
0x18005dc4b  jb      short loc_18005DBFD
0x18005dc4d  lea     rcx, NumOfElements+4; lpCriticalSection
0x18005dc54  call    cs:__imp_LeaveCriticalSection
0x18005dc5a  test    rdi, rdi
0x18005dc5d  jz      short loc_18005DC87
0x18005dc5f  xor     ebp, ebp
0x18005dc61  test    r14d, r14d
0x18005dc64  jz      short loc_18005DC7F
0x18005dc66  mov     rcx, [rdi+rbp*8]; this
0x18005dc6a  call    ?Signal@CWaitableOperation@@QEAAJXZ; CWaitableOperation::Signal(void)
0x18005dc6f  mov     rcx, [rdi+rbp*8]; this
0x18005dc73  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18005dc78  inc     ebp
0x18005dc7a  cmp     ebp, r14d
0x18005dc7d  jb      short loc_18005DC66
0x18005dc7f  mov     rcx, rdi; lpMem
0x18005dc82  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18005dc87  mov     rbx, [rsp+58h+arg_8]
0x18005dc8c  mov     eax, esi
0x18005dc8e  add     rsp, 30h
0x18005dc92  pop     r15
0x18005dc94  pop     r14
0x18005dc96  pop     rdi
0x18005dc97  pop     rsi
0x18005dc98  pop     rbp
0x18005dc99  retn
```
