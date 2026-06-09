# CIssuanceLicense::CreateEvents(ulong)

- ea: `0x1800098e8`
- end: `0x1800099b5`
- name: `?CreateEvents@CIssuanceLicense@@QEAAJK@Z`
- size: `205`
- prototype: `int(CIssuanceLicense *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004970`

## callees

- `0x180001284`
- `0x180001290`
- `0x1800098e8`
- `0x180017358`
- `0x180037b58`
- `0x18005bd72`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000990b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000990b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009939`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009939`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::CreateEvents(CIssuanceLicense *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  signed int v7; // ebx
  DWORD CurrentProcessId; // eax
  struct _SECURITY_ATTRIBUTES *v9; // rdx
  HANDLE EventA; // rax
  signed int LastError; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = (unsigned __int16 *)operator new[](0x78u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x78u);
    CurrentProcessId = GetCurrentProcessId();
    v7 = StringCchPrintfW(v6, 0x3Cu, L"UDRMPublishingSignRL_%lu%lu", CurrentProcessId, a2);
    if ( v7 >= 0 )
    {
      EventA = DRMOS::CreateEventA(0, v9, 0, (DRMOS *)v6);
      *((_QWORD *)this + 90) = EventA;
      if ( !EventA )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147467259;
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  operator delete(v6);
  LeaveCriticalSection(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800098e8  push    rbx
0x1800098ea  push    rbp
0x1800098eb  push    rsi
0x1800098ec  push    rdi
0x1800098ed  sub     rsp, 48h
0x1800098f1  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800098fa  mov     ebx, edx
0x1800098fc  mov     rbp, rcx
0x1800098ff  lea     rsi, [rcx+58h]
0x180009903  mov     [rsp+68h+arg_0], rsi
0x180009908  mov     rcx, rsi; lpCriticalSection
0x18000990b  call    cs:__imp_EnterCriticalSection
0x180009911  nop
0x180009912  mov     ecx, 78h ; 'x'; unsigned __int64
0x180009917  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000991c  mov     rdi, rax
0x18000991f  test    rax, rax
0x180009922  jnz     short loc_18000992B
0x180009924  mov     ebx, 8007000Eh
0x180009929  jmp     short loc_180009998
0x18000992b  xor     edx, edx; Val
0x18000992d  lea     r8d, [rdx+78h]; Size
0x180009931  mov     rcx, rdi; void *
0x180009934  call    memset_0
0x180009939  call    cs:__imp_GetCurrentProcessId
0x18000993f  mov     r9d, eax
0x180009942  mov     dword ptr [rsp+68h+var_48], ebx; unsigned __int16 *
0x180009946  lea     r8, ?g_wszPUB_SignCancelEventName@@3QBGB; "UDRMPublishingSignRL_%lu%lu"
0x18000994d  mov     edx, 3Ch ; '<'; unsigned __int64
0x180009952  mov     rcx, rdi; unsigned __int16 *
0x180009955  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000995a  mov     ebx, eax
0x18000995c  test    eax, eax
0x18000995e  js      short loc_180009998
0x180009960  mov     r9, rdi; int
0x180009963  xor     r8d, r8d; int
0x180009966  xor     ecx, ecx; lpEventAttributes
0x180009968  call    ?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18000996d  mov     [rbp+2D0h], rax
0x180009974  test    rax, rax
0x180009977  jnz     short loc_180009998
0x180009979  call    cs:__imp_GetLastError
0x18000997f  mov     ebx, eax
0x180009981  test    eax, eax
0x180009983  jle     short loc_18000998E
0x180009985  movzx   ebx, ax
0x180009988  or      ebx, 80070000h
0x18000998e  mov     eax, 80004005h
0x180009993  test    ebx, ebx
0x180009995  cmovns  ebx, eax
0x180009998  mov     rcx, rdi; Block
0x18000999b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099a0  nop
0x1800099a1  mov     rcx, rsi; lpCriticalSection
0x1800099a4  call    cs:__imp_LeaveCriticalSection
0x1800099aa  mov     eax, ebx
0x1800099ac  add     rsp, 48h
0x1800099b0  pop     rdi
0x1800099b1  pop     rsi
0x1800099b2  pop     rbp
0x1800099b3  pop     rbx
0x1800099b4  retn
```
