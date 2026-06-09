# NTDomain::getConnection(LDAPConnection * *)

- ea: `0x18001f9b0`
- end: `0x18001fa3d`
- name: `?getConnection@NTDomain@@QEAAKPEAPEAVLDAPConnection@@@Z`
- size: `141`
- prototype: `unsigned int __fastcall(NTDomain *__hidden this, struct LDAPConnection **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d04c`

## callees

- `0x18001f7b4`
- `0x18001f9b0`
- `0x18001fa44`
- `0x18001fb4c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001fa25`
- `KERNEL32!LeaveCriticalSection` at `0x18001fa25`
- `KERNEL32!EnterCriticalSection` at `0x18001f9e6`
- `KERNEL32!EnterCriticalSection` at `0x18001f9e6`
- `KERNEL32!TryEnterCriticalSection` at `0x18001f9ca`
- `KERNEL32!TryEnterCriticalSection` at `0x18001f9ca`
- `KERNEL32!SwitchToThread` at `0x18001f9db`
- `KERNEL32!SwitchToThread` at `0x18001f9db`

## pseudocode

```c
__int64 __fastcall NTDomain::getConnection(struct _RTL_CRITICAL_SECTION *this, struct LDAPConnection **a2)
{
  int v4; // ebx
  volatile signed __int32 *DebugInfo; // rax
  unsigned int LockCount; // ebx

  v4 = 0;
  while ( !TryEnterCriticalSection(this) )
  {
    if ( ++v4 >= 100 )
    {
      EnterCriticalSection(this);
      break;
    }
    SwitchToThread();
  }
  if ( !(unsigned int)NTDomain::isConnected((NTDomain *)this) && (unsigned int)NTDomain::isExpired((NTDomain *)this) )
    NTDomain::findServer((NTDomain *)this);
  DebugInfo = (volatile signed __int32 *)this[3].DebugInfo;
  *a2 = (struct LDAPConnection *)DebugInfo;
  if ( DebugInfo )
    _InterlockedIncrement(DebugInfo + 24);
  LockCount = this[3].LockCount;
  LeaveCriticalSection(this);
  return LockCount;
}

```

## disassembly

```asm
0x18001f9b0  mov     [rsp+arg_0], rbx
0x18001f9b5  mov     [rsp+arg_8], rsi
0x18001f9ba  push    rdi
0x18001f9bb  sub     rsp, 20h
0x18001f9bf  mov     rsi, rdx
0x18001f9c2  mov     rdi, rcx
0x18001f9c5  xor     ebx, ebx
0x18001f9c7  mov     rcx, rdi; lpCriticalSection
0x18001f9ca  call    cs:__imp_TryEnterCriticalSection
0x18001f9d0  test    eax, eax
0x18001f9d2  jnz     short loc_18001F9EC
0x18001f9d4  inc     ebx
0x18001f9d6  cmp     ebx, 64h ; 'd'
0x18001f9d9  jge     short loc_18001F9E3
0x18001f9db  call    cs:__imp_SwitchToThread
0x18001f9e1  jmp     short loc_18001F9C7
0x18001f9e3  mov     rcx, rdi; lpCriticalSection
0x18001f9e6  call    cs:__imp_EnterCriticalSection
0x18001f9ec  mov     rcx, rdi; this
0x18001f9ef  call    ?isConnected@NTDomain@@IEAAHXZ; NTDomain::isConnected(void)
0x18001f9f4  test    eax, eax
0x18001f9f6  jnz     short loc_18001FA0C
0x18001f9f8  mov     rcx, rdi; this
0x18001f9fb  call    ?isExpired@NTDomain@@IEAAHXZ; NTDomain::isExpired(void)
0x18001fa00  test    eax, eax
0x18001fa02  jz      short loc_18001FA0C
0x18001fa04  mov     rcx, rdi; this
0x18001fa07  call    ?findServer@NTDomain@@IEAAXXZ; NTDomain::findServer(void)
0x18001fa0c  mov     rax, [rdi+78h]
0x18001fa10  mov     [rsi], rax
0x18001fa13  test    rax, rax
0x18001fa16  jz      short loc_18001FA1C
0x18001fa18  lock inc dword ptr [rax+60h]
0x18001fa1c  mov     ebx, [rdi+80h]
0x18001fa22  mov     rcx, rdi; lpCriticalSection
0x18001fa25  call    cs:__imp_LeaveCriticalSection
0x18001fa2b  mov     rsi, [rsp+28h+arg_8]
0x18001fa30  mov     eax, ebx
0x18001fa32  mov     rbx, [rsp+28h+arg_0]
0x18001fa37  add     rsp, 20h
0x18001fa3b  pop     rdi
0x18001fa3c  retn
```
