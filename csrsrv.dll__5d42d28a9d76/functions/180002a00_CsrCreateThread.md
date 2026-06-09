# CsrCreateThread

- ea: `0x180002a00`
- end: `0x180002c7c`
- name: `CsrCreateThread`
- size: `636`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180002540`
- `0x180002880`
- `0x1800058b0`

## callees

- `0x180002a00`
- `0x180002f60`
- `0x180002fd0`
- `0x1800035c0`
- `0x180003780`
- `0x180003930`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtClose` at `0x180002ade`
- `ntdll!NtClose` at `0x180002ade`
- `ntdll!RtlFreeHeap` at `0x180002c1a`
- `ntdll!RtlFreeHeap` at `0x180002c1a`
- `ntdll!RtlEnterCriticalSection` at `0x180002a4c`
- `ntdll!RtlEnterCriticalSection` at `0x180002c3c`
- `ntdll!RtlEnterCriticalSection` at `0x180002a4c`
- `ntdll!RtlEnterCriticalSection` at `0x180002c3c`
- `ntdll!NtQueryInformationThread` at `0x180002a73`
- `ntdll!NtQueryInformationThread` at `0x180002a73`
- `ntdll!RtlLeaveCriticalSection` at `0x180002acf`
- `ntdll!RtlLeaveCriticalSection` at `0x180002b4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180002b9a`
- `ntdll!RtlLeaveCriticalSection` at `0x180002bb4`
- `ntdll!RtlLeaveCriticalSection` at `0x180002bce`
- `ntdll!RtlLeaveCriticalSection` at `0x180002acf`
- `ntdll!RtlLeaveCriticalSection` at `0x180002b4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180002b9a`
- `ntdll!RtlLeaveCriticalSection` at `0x180002bb4`
- `ntdll!RtlLeaveCriticalSection` at `0x180002bce`
- `ntdll!NtRegisterThreadTerminatePort` at `0x180002be8`
- `ntdll!NtRegisterThreadTerminatePort` at `0x180002be8`

## string_xrefs

- `0x180002b81`: `CsrCreateThread`

## pseudocode

```c
__int64 __fastcall CsrCreateThread(__int64 a1, void *a2, __int128 *a3, char a4)
{
  NTSTATUS InformationThread; // ebx
  __int64 *v8; // rdx
  __int64 *j; // rax
  char *Thread; // rbx
  __int128 v12; // xmm0
  NTSTATUS inserted; // esi
  _QWORD *v14; // rax
  __int64 v15; // r14
  __int64 v16; // rbx
  __int64 *v17; // rcx
  __int64 *i; // rax
  _OWORD ThreadInformation[2]; // [rsp+30h] [rbp-58h] BYREF

  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  if ( a4 )
  {
    v14 = KeGetPcr()->Unused1[1];
    v15 = v14[5];
    v16 = v14[6];
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    v17 = &CsrThreadHashTable[2 * (((unsigned int)v16 >> 2) & 0x3FF)];
    for ( i = (__int64 *)*v17; i != v17; i = (__int64 *)*i )
    {
      if ( i[3] == v16 && i[2] == v15 )
        goto LABEL_3;
    }
    goto LABEL_17;
  }
  RtlEnterCriticalSection(&CsrProcessStructureLock);
LABEL_3:
  InformationThread = NtQueryInformationThread(a2, ThreadTimes, ThreadInformation, 0x20u, 0);
  if ( InformationThread < 0 )
  {
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return (unsigned int)InformationThread;
  }
  v8 = &CsrThreadHashTable[2 * ((*((_DWORD *)a3 + 2) >> 2) & 0x3FF)];
  for ( j = (__int64 *)*v8; j != v8; j = (__int64 *)*j )
  {
    if ( j[3] == *((_QWORD *)a3 + 1) && j[2] == *(_QWORD *)a3 )
    {
      if ( *(j - 3) == *(_QWORD *)&ThreadInformation[0] )
      {
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
        NtClose(a2);
        return 0;
      }
      break;
    }
  }
  if ( (*(_BYTE *)(a1 + 92) & 8) != 0 )
  {
    CsrpLogFailure("CsrCreateThread");
LABEL_17:
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return 3221225547LL;
  }
  Thread = (char *)CsrAllocateThread(a1);
  if ( Thread )
  {
    *(_QWORD *)Thread = *(_QWORD *)&ThreadInformation[0];
    v12 = *a3;
    *((_QWORD *)Thread + 8) = a2;
    *((_DWORD *)Thread + 18) = 0;
    *(_OWORD *)(Thread + 40) = v12;
    inserted = CsrInsertThread(a1, Thread);
    if ( inserted >= 0 )
    {
      if ( a1 != CsrRootProcess )
        goto LABEL_15;
      inserted = NtRegisterThreadTerminatePort(CsrApiPort);
      if ( inserted >= 0 )
        goto LABEL_15;
      CsrRemoveThread(Thread);
    }
    CsrLockedDereferenceProcess(a1);
    RtlFreeHeap(CsrHeap, 0, Thread);
LABEL_15:
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return (unsigned int)inserted;
  }
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180002a00  mov     [rsp+arg_10], rbx
0x180002a05  push    rbp
0x180002a06  push    rsi
0x180002a07  push    rdi
0x180002a08  push    r14
0x180002a0a  push    r15
0x180002a0c  sub     rsp, 60h
0x180002a10  mov     rax, cs:__security_cookie
0x180002a17  xor     rax, rsp
0x180002a1a  mov     [rsp+88h+var_38], rax
0x180002a1f  lea     r15, CsrThreadHashTable
0x180002a26  xorps   xmm0, xmm0
0x180002a29  mov     rdi, rcx
0x180002a2c  mov     rsi, r8
0x180002a2f  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002a36  mov     rbp, rdx
0x180002a39  movups  [rsp+88h+ThreadInformation], xmm0
0x180002a3e  movups  [rsp+88h+var_48], xmm0
0x180002a43  test    r9b, r9b
0x180002a46  jnz     loc_180002C2B
0x180002a4c  call    cs:__imp_RtlEnterCriticalSection
0x180002a53  nop     dword ptr [rax+rax+00h]
0x180002a58  xor     r14d, r14d
0x180002a5b  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x180002a60  mov     r9d, 20h ; ' '; ThreadInformationLength
0x180002a66  mov     [rsp+88h+ReturnLength], r14; ReturnLength
0x180002a6b  mov     edx, 1; ThreadInformationClass
0x180002a70  mov     rcx, rbp; ThreadHandle
0x180002a73  call    cs:__imp_NtQueryInformationThread
0x180002a7a  nop     dword ptr [rax+rax+00h]
0x180002a7f  mov     ebx, eax
0x180002a81  test    eax, eax
0x180002a83  js      loc_180002BC7
0x180002a89  mov     edx, [rsi+8]
0x180002a8c  shr     rdx, 2
0x180002a90  and     edx, 3FFh
0x180002a96  shl     rdx, 4
0x180002a9a  add     rdx, r15
0x180002a9d  mov     rax, [rdx]
0x180002aa0  cmp     rax, rdx
0x180002aa3  jz      short loc_180002AEE
0x180002aa5  mov     rcx, [rsi+8]
0x180002aa9  cmp     [rax+18h], rcx
0x180002aad  jz      short loc_180002AB4
0x180002aaf  mov     rax, [rax]
0x180002ab2  jmp     short loc_180002AA0
0x180002ab4  mov     rcx, [rsi]
0x180002ab7  cmp     [rax+10h], rcx
0x180002abb  jnz     short loc_180002AAF
0x180002abd  mov     rcx, qword ptr [rsp+88h+ThreadInformation]
0x180002ac2  cmp     [rax-18h], rcx
0x180002ac6  jnz     short loc_180002AEE
0x180002ac8  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002acf  call    cs:__imp_RtlLeaveCriticalSection
0x180002ad6  nop     dword ptr [rax+rax+00h]
0x180002adb  mov     rcx, rbp; Handle
0x180002ade  call    cs:__imp_NtClose
0x180002ae5  nop     dword ptr [rax+rax+00h]
0x180002aea  xor     eax, eax
0x180002aec  jmp     short loc_180002B5A
0x180002aee  test    byte ptr [rdi+5Ch], 8
0x180002af2  jnz     loc_180002B7C
0x180002af8  mov     rcx, rdi
0x180002afb  call    CsrAllocateThread
0x180002b00  mov     rbx, rax
0x180002b03  test    rax, rax
0x180002b06  jz      loc_180002BAD
0x180002b0c  mov     rax, qword ptr [rsp+88h+ThreadInformation]
0x180002b11  mov     rdx, rbx
0x180002b14  mov     [rbx], rax
0x180002b17  mov     rcx, rdi
0x180002b1a  movups  xmm0, xmmword ptr [rsi]
0x180002b1d  mov     [rbx+40h], rbp
0x180002b21  mov     [rbx+48h], r14d
0x180002b25  movups  xmmword ptr [rbx+28h], xmm0
0x180002b29  call    CsrInsertThread
0x180002b2e  mov     esi, eax
0x180002b30  test    eax, eax
0x180002b32  js      loc_180002C06
0x180002b38  cmp     rdi, cs:CsrRootProcess
0x180002b3f  jz      loc_180002BE1
0x180002b45  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002b4c  call    cs:__imp_RtlLeaveCriticalSection
0x180002b53  nop     dword ptr [rax+rax+00h]
0x180002b58  mov     eax, esi
0x180002b5a  mov     rcx, [rsp+88h+var_38]
0x180002b5f  xor     rcx, rsp; StackCookie
0x180002b62  call    __security_check_cookie
0x180002b67  mov     rbx, [rsp+88h+arg_10]
0x180002b6f  add     rsp, 60h
0x180002b73  pop     r15
0x180002b75  pop     r14
0x180002b77  pop     rdi
0x180002b78  pop     rsi
0x180002b79  pop     rbp
0x180002b7a  retn
0x180002b7c  mov     edx, 4C5h
0x180002b81  lea     rcx, aCsrcreatethrea_0; "CsrCreateThread"
0x180002b88  mov     r8d, 0C000004Bh
0x180002b8e  call    CsrpLogFailure
0x180002b93  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002b9a  call    cs:__imp_RtlLeaveCriticalSection
0x180002ba1  nop     dword ptr [rax+rax+00h]
0x180002ba6  mov     eax, 0C000004Bh
0x180002bab  jmp     short loc_180002B5A
0x180002bad  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002bb4  call    cs:__imp_RtlLeaveCriticalSection
0x180002bbb  nop     dword ptr [rax+rax+00h]
0x180002bc0  mov     eax, 0C0000017h
0x180002bc5  jmp     short loc_180002B5A
0x180002bc7  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002bce  call    cs:__imp_RtlLeaveCriticalSection
0x180002bd5  nop     dword ptr [rax+rax+00h]
0x180002bda  mov     eax, ebx
0x180002bdc  jmp     loc_180002B5A
0x180002be1  mov     rcx, cs:CsrApiPort; TerminationPort
0x180002be8  call    cs:__imp_NtRegisterThreadTerminatePort
0x180002bef  nop     dword ptr [rax+rax+00h]
0x180002bf4  mov     esi, eax
0x180002bf6  test    eax, eax
0x180002bf8  jns     loc_180002B45
0x180002bfe  mov     rcx, rbx
0x180002c01  call    CsrRemoveThread
0x180002c06  mov     rcx, rdi
0x180002c09  call    CsrLockedDereferenceProcess
0x180002c0e  mov     rcx, cs:CsrHeap; HeapHandle
0x180002c15  mov     r8, rbx; BaseAddress
0x180002c18  xor     edx, edx; Flags
0x180002c1a  call    cs:__imp_RtlFreeHeap
0x180002c21  nop     dword ptr [rax+rax+00h]
0x180002c26  jmp     loc_180002B45
0x180002c2b  mov     rax, gs:70h
0x180002c34  mov     r14, [rax+28h]
0x180002c38  mov     rbx, [rax+30h]
0x180002c3c  call    cs:__imp_RtlEnterCriticalSection
0x180002c43  nop     dword ptr [rax+rax+00h]
0x180002c48  mov     ecx, ebx
0x180002c4a  shr     rcx, 2
0x180002c4e  and     ecx, 3FFh
0x180002c54  shl     rcx, 4
0x180002c58  add     rcx, r15
0x180002c5b  mov     rax, [rcx]
0x180002c5e  cmp     rax, rcx
0x180002c61  jz      loc_180002B93
0x180002c67  cmp     [rax+18h], rbx
0x180002c6b  jnz     short loc_180002C77
0x180002c6d  cmp     [rax+10h], r14
0x180002c71  jz      loc_180002A58
0x180002c77  mov     rax, [rax]
0x180002c7a  jmp     short loc_180002C5E
```
