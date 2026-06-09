# IsAdminToken(int *)

- ea: `0x14004175c`
- end: `0x14004189b`
- name: `?IsAdminToken@@YAJPEAH@Z`
- size: `319`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `16`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400148c8`
- `0x140016520`
- `0x140017af0`
- `0x1400184a0`
- `0x1400189b0`
- `0x14001af10`
- `0x14001c4f4`
- `0x140028cb0`
- `0x140029730`
- `0x1400409b8`
- `0x1400413ac`
- `0x140042bf8`
- `0x1400472d0`
- `0x14004a970`
- `0x14004c2ac`
- `0x14004e148`

## callees

- `0x140020420`
- `0x14004175c`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x140041831`
- `ADVAPI32!CheckTokenMembership` at `0x140041831`
- `ADVAPI32!CreateWellKnownSid` at `0x1400417d6`
- `ADVAPI32!CreateWellKnownSid` at `0x1400417d6`
- `KERNEL32!GetLastError` at `0x1400417e6`
- `KERNEL32!GetLastError` at `0x140041845`
- `KERNEL32!GetLastError` at `0x1400417e6`
- `KERNEL32!GetLastError` at `0x140041845`
- `KERNEL32!HeapAlloc` at `0x14004178b`
- `KERNEL32!HeapAlloc` at `0x14004178b`
- `KERNEL32!HeapFree` at `0x14004187c`
- `KERNEL32!HeapFree` at `0x14004187c`
- `KERNEL32!GetProcessHeap` at `0x140041777`
- `KERNEL32!GetProcessHeap` at `0x140041868`
- `KERNEL32!GetProcessHeap` at `0x140041777`
- `KERNEL32!GetProcessHeap` at `0x140041868`

## string_xrefs

- `0x1400417a4`: `IsAdminToken`
- `0x14004180f`: `IsAdminToken`

## pseudocode

```c
__int64 __fastcall IsAdminToken(PBOOL IsMember)
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
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IsAdminToken", 676, v5);
    }
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v4);
  }
  else
  {
    v5 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IsAdminToken", 670, -2147024882);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14004175c  mov     [rsp+arg_0], rbx
0x140041761  mov     [rsp+arg_10], rsi
0x140041766  push    rdi
0x140041767  sub     rsp, 30h
0x14004176b  mov     ebx, 44h ; 'D'
0x140041770  mov     rsi, rcx
0x140041773  mov     [rsp+38h+cbSid], ebx
0x140041777  call    cs:__imp_GetProcessHeap
0x14004177e  nop     dword ptr [rax+rax+00h]
0x140041783  mov     r8d, ebx; dwBytes
0x140041786  xor     edx, edx; dwFlags
0x140041788  mov     rcx, rax; hHeap
0x14004178b  call    cs:__imp_HeapAlloc
0x140041792  nop     dword ptr [rax+rax+00h]
0x140041797  mov     rdi, rax
0x14004179a  test    rax, rax
0x14004179d  jnz     short loc_1400417C9
0x14004179f  mov     ebx, 8007000Eh
0x1400417a4  lea     r8, aIsadmintoken; "IsAdminToken"
0x1400417ab  mov     r9d, 29Eh
0x1400417b1  mov     [rsp+38h+var_18], ebx
0x1400417b5  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400417bc  lea     ecx, [rax+1]; Level
0x1400417bf  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400417c4  jmp     loc_140041888
0x1400417c9  xor     edx, edx; DomainSid
0x1400417cb  lea     r9, [rsp+38h+cbSid]; cbSid
0x1400417d0  mov     r8, rdi; pSid
0x1400417d3  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1400417d6  call    cs:__imp_CreateWellKnownSid
0x1400417dd  nop     dword ptr [rax+rax+00h]
0x1400417e2  test    eax, eax
0x1400417e4  jnz     short loc_140041829
0x1400417e6  call    cs:__imp_GetLastError
0x1400417ed  nop     dword ptr [rax+rax+00h]
0x1400417f2  mov     ebx, eax
0x1400417f4  test    eax, eax
0x1400417f6  jle     short loc_140041801
0x1400417f8  movzx   ebx, ax
0x1400417fb  or      ebx, 80070000h
0x140041801  test    ebx, ebx
0x140041803  jns     short loc_140041829
0x140041805  mov     r9d, 2A4h
0x14004180b  mov     [rsp+38h+var_18], ebx
0x14004180f  lea     r8, aIsadmintoken; "IsAdminToken"
0x140041816  mov     ecx, 1; Level
0x14004181b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041822  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041827  jmp     short loc_140041868
0x140041829  mov     r8, rsi; IsMember
0x14004182c  mov     rdx, rdi; SidToCheck
0x14004182f  xor     ecx, ecx; TokenHandle
0x140041831  call    cs:__imp_CheckTokenMembership
0x140041838  nop     dword ptr [rax+rax+00h]
0x14004183d  test    eax, eax
0x14004183f  jz      short loc_140041845
0x140041841  xor     ebx, ebx
0x140041843  jmp     short loc_140041868
0x140041845  call    cs:__imp_GetLastError
0x14004184c  nop     dword ptr [rax+rax+00h]
0x140041851  mov     ebx, eax
0x140041853  test    eax, eax
0x140041855  jle     short loc_140041860
0x140041857  movzx   ebx, ax
0x14004185a  or      ebx, 80070000h
0x140041860  test    ebx, ebx
0x140041862  jns     short loc_140041868
0x140041864  xor     ebx, ebx
0x140041866  mov     [rsi], ebx
0x140041868  call    cs:__imp_GetProcessHeap
0x14004186f  nop     dword ptr [rax+rax+00h]
0x140041874  mov     r8, rdi; lpMem
0x140041877  xor     edx, edx; dwFlags
0x140041879  mov     rcx, rax; hHeap
0x14004187c  call    cs:__imp_HeapFree
0x140041883  nop     dword ptr [rax+rax+00h]
0x140041888  mov     rsi, [rsp+38h+arg_10]
0x14004188d  mov     eax, ebx
0x14004188f  mov     rbx, [rsp+38h+arg_0]
0x140041894  add     rsp, 30h
0x140041898  pop     rdi
0x140041899  retn
```
