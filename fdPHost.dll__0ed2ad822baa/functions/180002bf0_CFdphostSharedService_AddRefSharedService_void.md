# CFdphostSharedService::AddRefSharedService(void)

- ea: `0x180002bf0`
- end: `0x180002c86`
- name: `?AddRefSharedService@CFdphostSharedService@@UEAAKXZ`
- size: `150`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002bf0`
- `0x180002f84`
- `0x180002fd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002c4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002c4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c2c`
- `combase!__imp_CoAddRefSharedService` at `0x180002c41`
- `combase!__imp_CoAddRefSharedService` at `0x180002c41`

## pseudocode

```c
__int64 __fastcall CFdphostSharedService::AddRefSharedService(RTL_SRWLOCK *this)
{
  unsigned int v2; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19);
  AcquireSRWLockExclusive(this + 2);
  v2 = ++HIDWORD(this[1].Ptr);
  if ( v2 == 1 )
    CoAddRefSharedService(LODWORD(this[3].Ptr));
  ReleaseSRWLockExclusive(this + 2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sqP(*((_QWORD *)WPP_GLOBAL_Control + 2), 20);
  return v2;
}

```

## disassembly

```asm
0x180002bf0  push    rbx
0x180002bf2  push    rbp
0x180002bf3  push    rsi
0x180002bf4  push    rdi
0x180002bf5  sub     rsp, 38h
0x180002bf9  mov     rbx, rcx
0x180002bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c03  lea     rbp, WPP_GLOBAL_Control
0x180002c0a  cmp     rcx, rbp
0x180002c0d  jz      short loc_180002C28
0x180002c0f  cmp     byte ptr [rcx+19h], 4
0x180002c13  jb      short loc_180002C28
0x180002c15  mov     rcx, [rcx+10h]
0x180002c19  mov     edx, 13h
0x180002c1e  mov     [rsp+58h+var_38], rbx
0x180002c23  call    WPP_SF_sq
0x180002c28  lea     rcx, [rbx+10h]; SRWLock
0x180002c2c  call    cs:__imp_AcquireSRWLockExclusive
0x180002c32  inc     dword ptr [rbx+0Ch]
0x180002c35  movsxd  rdi, dword ptr [rbx+0Ch]
0x180002c39  cmp     edi, 1
0x180002c3c  jnz     short loc_180002C47
0x180002c3e  mov     ecx, [rbx+18h]
0x180002c41  call    cs:__imp_CoAddRefSharedService
0x180002c47  lea     rcx, [rbx+10h]; SRWLock
0x180002c4b  call    cs:__imp_ReleaseSRWLockExclusive
0x180002c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c58  cmp     rcx, rbp
0x180002c5b  jz      short loc_180002C7B
0x180002c5d  cmp     byte ptr [rcx+19h], 4
0x180002c61  jb      short loc_180002C7B
0x180002c63  mov     rcx, [rcx+10h]
0x180002c67  mov     edx, 14h
0x180002c6c  mov     [rsp+58h+var_30], rdi
0x180002c71  mov     [rsp+58h+var_38], rbx
0x180002c76  call    WPP_SF_sqP
0x180002c7b  mov     eax, edi
0x180002c7d  add     rsp, 38h
0x180002c81  pop     rdi
0x180002c82  pop     rsi
0x180002c83  pop     rbp
0x180002c84  pop     rbx
0x180002c85  retn
```
