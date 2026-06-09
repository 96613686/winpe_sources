# LDAPConnection::isDisabled(void)

- ea: `0x18001f19c`
- end: `0x18001f21a`
- name: `?isDisabled@LDAPConnection@@QEAAHXZ`
- size: `126`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fa44`

## callees

- `0x180018218`
- `0x18001f19c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f207`
- `KERNEL32!LeaveCriticalSection` at `0x18001f207`
- `KERNEL32!EnterCriticalSection` at `0x18001f1ca`
- `KERNEL32!EnterCriticalSection` at `0x18001f1ca`
- `KERNEL32!TryEnterCriticalSection` at `0x18001f1ae`
- `KERNEL32!TryEnterCriticalSection` at `0x18001f1ae`
- `KERNEL32!SwitchToThread` at `0x18001f1bf`
- `KERNEL32!SwitchToThread` at `0x18001f1bf`

## pseudocode

```c
_BOOL8 __fastcall LDAPConnection::isDisabled(LPCRITICAL_SECTION lpCriticalSection)
{
  int v2; // ebx
  struct _RTL_CRITICAL_SECTION_DEBUG *SystemTimeAsDWORDLONG; // rax
  LONG LockCount; // ecx
  unsigned __int64 v5; // rax
  BOOL v6; // ebx

  v2 = 0;
  while ( !TryEnterCriticalSection(lpCriticalSection) )
  {
    if ( ++v2 >= 100 )
    {
      EnterCriticalSection(lpCriticalSection);
      break;
    }
    SwitchToThread();
  }
  SystemTimeAsDWORDLONG = (struct _RTL_CRITICAL_SECTION_DEBUG *)GetSystemTimeAsDWORDLONG();
  if ( SystemTimeAsDWORDLONG > lpCriticalSection[1].DebugInfo )
  {
    LockCount = lpCriticalSection[1].LockCount;
    v5 = (unsigned __int64)((char *)SystemTimeAsDWORDLONG - (char *)lpCriticalSection[1].DebugInfo) / 0x430E23400LL;
    if ( (int)v5 >= LockCount )
      LODWORD(v5) = lpCriticalSection[1].LockCount;
    lpCriticalSection[1].LockCount = LockCount - v5;
  }
  v6 = lpCriticalSection[1].LockCount > 0xAu;
  LeaveCriticalSection(lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x18001f19c  mov     [rsp+arg_0], rbx
0x18001f1a1  push    rdi
0x18001f1a2  sub     rsp, 20h
0x18001f1a6  mov     rdi, rcx
0x18001f1a9  xor     ebx, ebx
0x18001f1ab  mov     rcx, rdi; lpCriticalSection
0x18001f1ae  call    cs:__imp_TryEnterCriticalSection
0x18001f1b4  test    eax, eax
0x18001f1b6  jnz     short loc_18001F1D0
0x18001f1b8  inc     ebx
0x18001f1ba  cmp     ebx, 64h ; 'd'
0x18001f1bd  jge     short loc_18001F1C7
0x18001f1bf  call    cs:__imp_SwitchToThread
0x18001f1c5  jmp     short loc_18001F1AB
0x18001f1c7  mov     rcx, rdi; lpCriticalSection
0x18001f1ca  call    cs:__imp_EnterCriticalSection
0x18001f1d0  call    GetSystemTimeAsDWORDLONG
0x18001f1d5  cmp     rax, [rdi+28h]
0x18001f1d9  jbe     short loc_18001F1FB
0x18001f1db  sub     rax, [rdi+28h]
0x18001f1df  xor     edx, edx
0x18001f1e1  mov     ecx, [rdi+30h]
0x18001f1e4  mov     r8, 430E23400h
0x18001f1ee  div     r8
0x18001f1f1  cmp     eax, ecx
0x18001f1f3  cmovge  eax, ecx
0x18001f1f6  sub     ecx, eax
0x18001f1f8  mov     [rdi+30h], ecx
0x18001f1fb  xor     ebx, ebx
0x18001f1fd  mov     rcx, rdi; lpCriticalSection
0x18001f200  cmp     dword ptr [rdi+30h], 0Ah
0x18001f204  setnbe  bl
0x18001f207  call    cs:__imp_LeaveCriticalSection
0x18001f20d  mov     eax, ebx
0x18001f20f  mov     rbx, [rsp+28h+arg_0]
0x18001f214  add     rsp, 20h
0x18001f218  pop     rdi
0x18001f219  retn
```
