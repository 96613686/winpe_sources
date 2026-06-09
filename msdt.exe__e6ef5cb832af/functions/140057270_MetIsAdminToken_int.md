# MetIsAdminToken(int *)

- ea: `0x140057270`
- end: `0x1400573af`
- name: `?MetIsAdminToken@@YAJPEAH@Z`
- size: `319`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140056c70`

## callees

- `0x140020420`
- `0x140057270`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x140057345`
- `ADVAPI32!CheckTokenMembership` at `0x140057345`
- `ADVAPI32!CreateWellKnownSid` at `0x1400572ea`
- `ADVAPI32!CreateWellKnownSid` at `0x1400572ea`
- `KERNEL32!GetLastError` at `0x1400572fa`
- `KERNEL32!GetLastError` at `0x140057359`
- `KERNEL32!GetLastError` at `0x1400572fa`
- `KERNEL32!GetLastError` at `0x140057359`
- `KERNEL32!HeapAlloc` at `0x14005729f`
- `KERNEL32!HeapAlloc` at `0x14005729f`
- `KERNEL32!HeapFree` at `0x140057390`
- `KERNEL32!HeapFree` at `0x140057390`
- `KERNEL32!GetProcessHeap` at `0x14005728b`
- `KERNEL32!GetProcessHeap` at `0x14005737c`
- `KERNEL32!GetProcessHeap` at `0x14005728b`
- `KERNEL32!GetProcessHeap` at `0x14005737c`

## string_xrefs

- `0x1400572b8`: `MetIsAdminToken`
- `0x140057323`: `MetIsAdminToken`

## pseudocode

```c
__int64 __fastcall MetIsAdminToken(PBOOL IsMember)
{
  HANDLE ProcessHeap; // rax
  void *v3; // rax
  void *v4; // rdi
  signed int v5; // ebx
  signed int LastError; // eax
  signed int v7; // eax
  HANDLE v8; // rax
  DWORD cbSid; // [rsp+48h] [rbp+10h] BYREF

  cbSid = 68;
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x44u);
  v4 = v3;
  if ( v3 )
  {
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v3, &cbSid) )
      goto LABEL_18;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_18:
      if ( CheckTokenMembership(0, v4, IsMember) )
      {
        v5 = 0;
      }
      else
      {
        v7 = GetLastError();
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
        if ( v5 < 0 )
        {
          v5 = 0;
          *IsMember = 0;
        }
      }
    }
    else
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetIsAdminToken", 270, v5);
    }
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v4);
  }
  else
  {
    v5 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetIsAdminToken", 264, -2147024882);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140057270  mov     [rsp+arg_0], rbx
0x140057275  mov     [rsp+arg_10], rsi
0x14005727a  push    rdi
0x14005727b  sub     rsp, 30h
0x14005727f  mov     ebx, 44h ; 'D'
0x140057284  mov     rsi, rcx
0x140057287  mov     [rsp+38h+cbSid], ebx
0x14005728b  call    cs:__imp_GetProcessHeap
0x140057292  nop     dword ptr [rax+rax+00h]
0x140057297  mov     r8d, ebx; dwBytes
0x14005729a  xor     edx, edx; dwFlags
0x14005729c  mov     rcx, rax; hHeap
0x14005729f  call    cs:__imp_HeapAlloc
0x1400572a6  nop     dword ptr [rax+rax+00h]
0x1400572ab  mov     rdi, rax
0x1400572ae  test    rax, rax
0x1400572b1  jnz     short loc_1400572DD
0x1400572b3  mov     ebx, 8007000Eh
0x1400572b8  lea     r8, aMetisadmintoke; "MetIsAdminToken"
0x1400572bf  mov     r9d, 108h
0x1400572c5  mov     [rsp+38h+var_18], ebx
0x1400572c9  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400572d0  lea     ecx, [rax+1]; Level
0x1400572d3  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400572d8  jmp     loc_14005739C
0x1400572dd  xor     edx, edx; DomainSid
0x1400572df  lea     r9, [rsp+38h+cbSid]; cbSid
0x1400572e4  mov     r8, rdi; pSid
0x1400572e7  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1400572ea  call    cs:__imp_CreateWellKnownSid
0x1400572f1  nop     dword ptr [rax+rax+00h]
0x1400572f6  test    eax, eax
0x1400572f8  jnz     short loc_14005733D
0x1400572fa  call    cs:__imp_GetLastError
0x140057301  nop     dword ptr [rax+rax+00h]
0x140057306  mov     ebx, eax
0x140057308  test    eax, eax
0x14005730a  jle     short loc_140057315
0x14005730c  movzx   ebx, ax
0x14005730f  or      ebx, 80070000h
0x140057315  test    ebx, ebx
0x140057317  jns     short loc_14005733D
0x140057319  mov     r9d, 10Eh
0x14005731f  mov     [rsp+38h+var_18], ebx
0x140057323  lea     r8, aMetisadmintoke; "MetIsAdminToken"
0x14005732a  mov     ecx, 1; Level
0x14005732f  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140057336  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005733b  jmp     short loc_14005737C
0x14005733d  mov     r8, rsi; IsMember
0x140057340  mov     rdx, rdi; SidToCheck
0x140057343  xor     ecx, ecx; TokenHandle
0x140057345  call    cs:__imp_CheckTokenMembership
0x14005734c  nop     dword ptr [rax+rax+00h]
0x140057351  test    eax, eax
0x140057353  jz      short loc_140057359
0x140057355  xor     ebx, ebx
0x140057357  jmp     short loc_14005737C
0x140057359  call    cs:__imp_GetLastError
0x140057360  nop     dword ptr [rax+rax+00h]
0x140057365  mov     ebx, eax
0x140057367  test    eax, eax
0x140057369  jle     short loc_140057374
0x14005736b  movzx   ebx, ax
0x14005736e  or      ebx, 80070000h
0x140057374  test    ebx, ebx
0x140057376  jns     short loc_14005737C
0x140057378  xor     ebx, ebx
0x14005737a  mov     [rsi], ebx
0x14005737c  call    cs:__imp_GetProcessHeap
0x140057383  nop     dword ptr [rax+rax+00h]
0x140057388  mov     r8, rdi; lpMem
0x14005738b  xor     edx, edx; dwFlags
0x14005738d  mov     rcx, rax; hHeap
0x140057390  call    cs:__imp_HeapFree
0x140057397  nop     dword ptr [rax+rax+00h]
0x14005739c  mov     rsi, [rsp+38h+arg_10]
0x1400573a1  mov     eax, ebx
0x1400573a3  mov     rbx, [rsp+38h+arg_0]
0x1400573a8  add     rsp, 30h
0x1400573ac  pop     rdi
0x1400573ad  retn
```
