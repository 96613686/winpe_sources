# AD_LOOKUP_MANAGER::StartShutdown(void)

- ea: `0x18002598c`
- end: `0x180025a51`
- name: `?StartShutdown@AD_LOOKUP_MANAGER@@QEAAXXZ`
- size: `197`
- prototype: `void __fastcall(AD_LOOKUP_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800047d0`

## callees

- `0x180001250`
- `0x180024f3c`
- `0x1800256f4`
- `0x18002598c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180025a4a`
- `KERNEL32!EnterCriticalSection` at `0x18002599f`
- `KERNEL32!EnterCriticalSection` at `0x18002599f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800259e0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800259e0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025a10`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180025a10`
- `WLDAP32!__imp_ldap_abandon` at `0x1800259fc`
- `WLDAP32!__imp_ldap_abandon` at `0x1800259fc`

## pseudocode

```c
void __fastcall AD_LOOKUP_MANAGER::StartShutdown(AD_LOOKUP_MANAGER *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  _QWORD **v3; // rdi
  _QWORD *v4; // rax
  _QWORD *v5; // rcx
  CReaderWriterLock3 *v6; // rbp
  _QWORD *v7; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_DWORD *)this + 25) = 1;
  v3 = (_QWORD **)((char *)this + 56);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *v3 = v5;
    v6 = (CReaderWriterLock3 *)(v4 + 2);
    v5[1] = v3;
    v7 = v4 - 37;
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v4 + 2));
    if ( *(_DWORD *)v7 == 1 )
    {
      ldap_abandon(*(LDAP **)(v7[1] + 816LL), *((_DWORD *)v7 + 71));
      v7[36] = 0;
    }
    CReaderWriterLock3::WriteUnlock(v6);
    AD_LOOKUP_WORK_ITEM::ProcessComplete((AD_LOOKUP_WORK_ITEM *)v7);
    if ( v7 )
    {
      AD_LOOKUP_WORK_ITEM::~AD_LOOKUP_WORK_ITEM((AD_LOOKUP_WORK_ITEM *)v7);
      operator delete(v7);
    }
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18002598c  push    rbx
0x18002598e  push    rbp
0x18002598f  push    rsi
0x180025990  push    rdi
0x180025991  sub     rsp, 28h
0x180025995  lea     rsi, [rcx+8]
0x180025999  mov     rbx, rcx
0x18002599c  mov     rcx, rsi; lpCriticalSection
0x18002599f  call    cs:__imp_EnterCriticalSection
0x1800259a5  mov     dword ptr [rbx+64h], 1
0x1800259ac  lea     rdi, [rbx+38h]
0x1800259b0  mov     rax, [rdi]
0x1800259b3  cmp     rax, rdi
0x1800259b6  jz      loc_180025A3F
0x1800259bc  cmp     [rax+8], rdi
0x1800259c0  jnz     short loc_180025A38
0x1800259c2  mov     rcx, [rax]
0x1800259c5  cmp     [rcx+8], rax
0x1800259c9  jnz     short loc_180025A38
0x1800259cb  mov     [rdi], rcx
0x1800259ce  lea     rbp, [rax+10h]
0x1800259d2  mov     [rcx+8], rdi
0x1800259d6  lea     rbx, [rax-128h]
0x1800259dd  mov     rcx, rbp
0x1800259e0  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800259e6  cmp     dword ptr [rbx], 1
0x1800259e9  jnz     short loc_180025A0D
0x1800259eb  mov     rcx, [rbx+8]
0x1800259ef  mov     edx, [rbx+11Ch]; msgid
0x1800259f5  mov     rcx, [rcx+330h]; ld
0x1800259fc  call    cs:__imp_ldap_abandon
0x180025a02  mov     qword ptr [rbx+120h], 0
0x180025a0d  mov     rcx, rbp
0x180025a10  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180025a16  mov     rcx, rbx; this
0x180025a19  call    ?ProcessComplete@AD_LOOKUP_WORK_ITEM@@QEAAXXZ; AD_LOOKUP_WORK_ITEM::ProcessComplete(void)
0x180025a1e  test    rbx, rbx
0x180025a21  jz      short loc_1800259B0
0x180025a23  mov     rcx, rbx; this
0x180025a26  call    ??1AD_LOOKUP_WORK_ITEM@@QEAA@XZ; AD_LOOKUP_WORK_ITEM::~AD_LOOKUP_WORK_ITEM(void)
0x180025a2b  mov     rcx, rbx; Block
0x180025a2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025a33  jmp     loc_1800259B0
0x180025a38  mov     ecx, 3
0x180025a3d  int     29h; Win8: RtlFailFast(ecx)
0x180025a3f  mov     rcx, rsi
0x180025a42  add     rsp, 28h
0x180025a46  pop     rdi
0x180025a47  pop     rsi
0x180025a48  pop     rbp
0x180025a49  pop     rbx
0x180025a4a  jmp     cs:__imp_LeaveCriticalSection
```
