# CsrCreateRemoteThread

- ea: `0x18000a070`
- end: `0x18000a1e1`
- name: `CsrCreateRemoteThread`
- size: `369`
- prototype: `int __fastcall(HANDLE SourceHandle, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180002f60`
- `0x180002fd0`
- `0x180003670`
- `0x180003930`
- `0x1800069e0`
- `0x18000a070`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtClose` at `0x18000a18f`
- `ntdll!NtClose` at `0x18000a18f`
- `ntdll!RtlFreeHeap` at `0x18000a1b0`
- `ntdll!RtlFreeHeap` at `0x18000a1b0`
- `ntdll!NtQueryInformationThread` at `0x18000a0c8`
- `ntdll!NtQueryInformationThread` at `0x18000a0c8`
- `ntdll!NtDuplicateObject` at `0x18000a142`
- `ntdll!NtDuplicateObject` at `0x18000a142`

## pseudocode

```c
int __fastcall CsrCreateRemoteThread(HANDLE SourceHandle, __int64 *a2)
{
  int result; // eax
  NTSTATUS inserted; // edi
  _DWORD *Thread; // rbx
  volatile signed __int32 *v7; // rcx
  HANDLE v8; // rcx
  volatile signed __int32 *v9; // [rsp+40h] [rbp-9h] BYREF
  void *TargetHandle; // [rsp+48h] [rbp-1h] BYREF
  _OWORD ThreadInformation[2]; // [rsp+50h] [rbp+7h] BYREF

  v9 = 0;
  TargetHandle = 0;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  result = NtQueryInformationThread(SourceHandle, ThreadTimes, ThreadInformation, 0x20u, 0);
  if ( result >= 0 )
  {
    result = CsrLockProcessByClientId(*a2, &v9);
    if ( result >= 0 )
    {
      if ( *((_QWORD *)&ThreadInformation[0] + 1) )
      {
        inserted = -1073741749;
      }
      else
      {
        Thread = CsrAllocateThread((__int64)v9);
        if ( Thread )
        {
          if ( NtDuplicateObject(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 SourceHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &TargetHandle,
                 0,
                 0,
                 2u) < 0 )
            TargetHandle = SourceHandle;
          v7 = v9;
          *(_QWORD *)Thread = *(_QWORD *)&ThreadInformation[0];
          *(_OWORD *)(Thread + 10) = *(_OWORD *)a2;
          *((_QWORD *)Thread + 8) = TargetHandle;
          Thread[18] = 0;
          inserted = CsrInsertThread((__int64)v7, (__int64)Thread);
          if ( inserted < 0 )
          {
            v8 = (HANDLE)*((_QWORD *)Thread + 8);
            if ( v8 != SourceHandle )
              NtClose(v8);
            CsrLockedDereferenceProcess((__int64)v9);
            RtlFreeHeap(CsrHeap, 0, Thread);
          }
        }
        else
        {
          inserted = -1073741801;
        }
      }
      CsrUnlockProcess((__int64)v9);
      return inserted;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a070  push    rbp
0x18000a072  push    rbx
0x18000a073  push    rdi
0x18000a074  push    r14
0x18000a076  lea     rbp, [rsp-3Fh]
0x18000a07b  sub     rsp, 88h
0x18000a082  mov     rax, cs:__security_cookie
0x18000a089  xor     rax, rsp
0x18000a08c  mov     [rbp+57h+var_30], rax
0x18000a090  xorps   xmm0, xmm0
0x18000a093  mov     [rbp+57h+var_60], 0
0x18000a09b  mov     r9d, 20h ; ' '; ThreadInformationLength
0x18000a0a1  mov     [rbp+57h+TargetHandle], 0
0x18000a0a9  mov     rdi, rdx
0x18000a0ac  mov     [rsp+0A0h+ReturnLength], 0; ReturnLength
0x18000a0b5  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18000a0b9  mov     r14, rcx
0x18000a0bc  movups  [rbp+57h+ThreadInformation], xmm0
0x18000a0c0  lea     edx, [r9-1Fh]; ThreadInformationClass
0x18000a0c4  movups  [rbp+57h+var_40], xmm0
0x18000a0c8  call    cs:__imp_NtQueryInformationThread
0x18000a0cf  nop     dword ptr [rax+rax+00h]
0x18000a0d4  test    eax, eax
0x18000a0d6  js      loc_18000A1C7
0x18000a0dc  mov     rcx, [rdi]
0x18000a0df  lea     rdx, [rbp+57h+var_60]
0x18000a0e3  call    CsrLockProcessByClientId
0x18000a0e8  test    eax, eax
0x18000a0ea  js      loc_18000A1C7
0x18000a0f0  cmp     qword ptr [rbp+57h+ThreadInformation+8], 0
0x18000a0f5  jz      short loc_18000A101
0x18000a0f7  mov     edi, 0C000004Bh
0x18000a0fc  jmp     loc_18000A1BC
0x18000a101  mov     rcx, [rbp+57h+var_60]
0x18000a105  call    CsrAllocateThread
0x18000a10a  mov     rbx, rax
0x18000a10d  test    rax, rax
0x18000a110  jnz     short loc_18000A11C
0x18000a112  mov     edi, 0C0000017h
0x18000a117  jmp     loc_18000A1BC
0x18000a11c  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18000a120  mov     [rsp+0A0h+Options], 2; Options
0x18000a128  mov     r8, rcx; TargetProcessHandle
0x18000a12b  mov     [rsp+0A0h+HandleAttributes], 0; HandleAttributes
0x18000a133  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x18000a137  mov     dword ptr [rsp+0A0h+ReturnLength], 0; DesiredAccess
0x18000a13f  mov     rdx, r14; SourceHandle
0x18000a142  call    cs:__imp_NtDuplicateObject
0x18000a149  nop     dword ptr [rax+rax+00h]
0x18000a14e  test    eax, eax
0x18000a150  jns     short loc_18000A156
0x18000a152  mov     [rbp+57h+TargetHandle], r14
0x18000a156  mov     rax, qword ptr [rbp+57h+ThreadInformation]
0x18000a15a  mov     rdx, rbx
0x18000a15d  mov     rcx, [rbp+57h+var_60]
0x18000a161  mov     [rbx], rax
0x18000a164  movups  xmm0, xmmword ptr [rdi]
0x18000a167  movdqu  xmmword ptr [rbx+28h], xmm0
0x18000a16c  mov     rax, [rbp+57h+TargetHandle]
0x18000a170  mov     [rbx+40h], rax
0x18000a174  mov     dword ptr [rbx+48h], 0
0x18000a17b  call    CsrInsertThread
0x18000a180  mov     edi, eax
0x18000a182  test    eax, eax
0x18000a184  jns     short loc_18000A1BC
0x18000a186  mov     rcx, [rbx+40h]; Handle
0x18000a18a  cmp     rcx, r14
0x18000a18d  jz      short loc_18000A19B
0x18000a18f  call    cs:__imp_NtClose
0x18000a196  nop     dword ptr [rax+rax+00h]
0x18000a19b  mov     rcx, [rbp+57h+var_60]
0x18000a19f  call    CsrLockedDereferenceProcess
0x18000a1a4  mov     rcx, cs:CsrHeap; HeapHandle
0x18000a1ab  mov     r8, rbx; BaseAddress
0x18000a1ae  xor     edx, edx; Flags
0x18000a1b0  call    cs:__imp_RtlFreeHeap
0x18000a1b7  nop     dword ptr [rax+rax+00h]
0x18000a1bc  mov     rcx, [rbp+57h+var_60]
0x18000a1c0  call    CsrUnlockProcess
0x18000a1c5  mov     eax, edi
0x18000a1c7  mov     rcx, [rbp+57h+var_30]
0x18000a1cb  xor     rcx, rsp; StackCookie
0x18000a1ce  call    __security_check_cookie
0x18000a1d3  add     rsp, 88h
0x18000a1da  pop     r14
0x18000a1dc  pop     rdi
0x18000a1dd  pop     rbx
0x18000a1de  pop     rbp
0x18000a1df  retn
```
