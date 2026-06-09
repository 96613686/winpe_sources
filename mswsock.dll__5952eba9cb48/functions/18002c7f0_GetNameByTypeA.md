# GetNameByTypeA

- ea: `0x18002c7f0`
- end: `0x18002c8ff`
- name: `GetNameByTypeA`
- size: `271`
- prototype: `INT __stdcall(LPGUID lpServiceType, LPSTR lpServiceName, DWORD dwNameLength)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18002c7f0`
- `0x18002c910`
- `0x180053010`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18002c8ae`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18002c8ae`
- `ntdll!RtlInitUnicodeString` at `0x18002c886`
- `ntdll!RtlInitUnicodeString` at `0x18002c886`
- `ntdll!RtlFreeHeap` at `0x18002c870`
- `ntdll!RtlFreeHeap` at `0x18002c8c8`
- `ntdll!RtlFreeHeap` at `0x18002c870`
- `ntdll!RtlFreeHeap` at `0x18002c8c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c8e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c8e4`

## pseudocode

```c
INT __stdcall GetNameByTypeA(LPGUID lpServiceType, LPSTR lpServiceName, DWORD dwNameLength)
{
  unsigned __int64 v4; // rax
  USHORT v5; // bx
  DWORD v7; // esi
  WCHAR *HeapRoutine; // rax
  WCHAR *v9; // rdi
  DWORD v10; // ecx
  NTSTATUS v11; // ebx
  struct _STRING v13; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  v4 = 2LL * dwNameLength;
  v5 = dwNameLength;
  DestinationString = 0;
  v13 = 0;
  if ( v4 > 0xFFFFFFFF )
  {
    v10 = 87;
    goto LABEL_8;
  }
  v7 = 2 * dwNameLength;
  HeapRoutine = (WCHAR *)SockAllocateHeapRoutine(SockPrivateHeap, 0, (unsigned int)v4);
  v9 = HeapRoutine;
  if ( !HeapRoutine )
  {
    v10 = 8;
LABEL_8:
    SetLastError(v10);
    return -1;
  }
  if ( !GetNameByTypeW(lpServiceType, HeapRoutine, v7) )
  {
    RtlInitUnicodeString(&DestinationString, v9);
    v13.Length = v5;
    v13.MaximumLength = v5;
    v13.Buffer = lpServiceName;
    v11 = RtlUnicodeStringToAnsiString(&v13, &DestinationString, 0);
    RtlFreeHeap(SockPrivateHeap, 0, v9);
    return (v11 >= 0) - 1;
  }
  RtlFreeHeap(SockPrivateHeap, 0, v9);
  return -1;
}

```

## disassembly

```asm
0x18002c7f0  push    rbx
0x18002c7f2  push    rbp
0x18002c7f3  push    rsi
0x18002c7f4  push    rdi
0x18002c7f5  push    r14
0x18002c7f7  sub     rsp, 40h
0x18002c7fb  mov     eax, r8d
0x18002c7fe  mov     rbp, rcx
0x18002c801  add     rax, rax
0x18002c804  mov     ebx, r8d
0x18002c807  mov     ecx, 0FFFFFFFFh
0x18002c80c  xorps   xmm0, xmm0
0x18002c80f  xorps   xmm1, xmm1
0x18002c812  mov     r14, rdx
0x18002c815  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18002c81a  movups  xmmword ptr [rsp+68h+var_48.Length], xmm1
0x18002c81f  cmp     rax, rcx
0x18002c822  ja      loc_18002C8DF
0x18002c828  mov     rcx, cs:SockPrivateHeap
0x18002c82f  xor     edx, edx
0x18002c831  mov     esi, eax
0x18002c833  mov     r8d, eax
0x18002c836  mov     rax, cs:SockAllocateHeapRoutine
0x18002c83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c842  mov     rdi, rax
0x18002c845  test    rax, rax
0x18002c848  jnz     short loc_18002C852
0x18002c84a  lea     ecx, [rax+8]
0x18002c84d  jmp     loc_18002C8E4
0x18002c852  mov     r8d, esi; dwNameLength
0x18002c855  mov     rdx, rdi; lpServiceName
0x18002c858  mov     rcx, rbp; lpServiceType
0x18002c85b  call    GetNameByTypeW
0x18002c860  test    eax, eax
0x18002c862  jz      short loc_18002C87E
0x18002c864  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002c86b  mov     r8, rdi; P
0x18002c86e  xor     edx, edx; Flags
0x18002c870  call    cs:__imp_RtlFreeHeap
0x18002c877  nop     dword ptr [rax+rax+00h]
0x18002c87c  jmp     short loc_18002C8F0
0x18002c87e  mov     rdx, rdi; SourceString
0x18002c881  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002c886  call    cs:__imp_RtlInitUnicodeString
0x18002c88d  nop     dword ptr [rax+rax+00h]
0x18002c892  xor     r8d, r8d; AllocateDestinationString
0x18002c895  mov     [rsp+68h+var_48.Length], bx
0x18002c89a  lea     rdx, [rsp+68h+DestinationString]; SourceString
0x18002c89f  mov     [rsp+68h+var_48.MaximumLength], bx
0x18002c8a4  lea     rcx, [rsp+68h+var_48]; DestinationString
0x18002c8a9  mov     [rsp+68h+var_48.Buffer], r14
0x18002c8ae  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18002c8b5  nop     dword ptr [rax+rax+00h]
0x18002c8ba  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002c8c1  mov     r8, rdi; P
0x18002c8c4  xor     edx, edx; Flags
0x18002c8c6  mov     ebx, eax
0x18002c8c8  call    cs:__imp_RtlFreeHeap
0x18002c8cf  nop     dword ptr [rax+rax+00h]
0x18002c8d4  xor     eax, eax
0x18002c8d6  test    ebx, ebx
0x18002c8d8  setns   al
0x18002c8db  dec     eax
0x18002c8dd  jmp     short loc_18002C8F3
0x18002c8df  mov     ecx, 57h ; 'W'; dwErrCode
0x18002c8e4  call    cs:__imp_SetLastError
0x18002c8eb  nop     dword ptr [rax+rax+00h]
0x18002c8f0  or      eax, 0FFFFFFFFh
0x18002c8f3  add     rsp, 40h
0x18002c8f7  pop     r14
0x18002c8f9  pop     rdi
0x18002c8fa  pop     rsi
0x18002c8fb  pop     rbp
0x18002c8fc  pop     rbx
0x18002c8fd  retn
```
