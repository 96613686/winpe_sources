# CDfMutex::Take(ulong)

- ea: `0x18002dbd0`
- end: `0x18002dc97`
- name: `?Take@CDfMutex@@QEAAJK@Z`
- size: `199`
- prototype: `int(CDfMutex *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b588`
- `0x1800405dc`

## callees

- `0x18002dbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dbe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dbe4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dc36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dc36`

## pseudocode

```c
int __fastcall CDfMutex::Take(CDfMutex *this, DWORD a2)
{
  DWORD CurrentThreadId; // eax
  DWORD v5; // edi
  signed __int32 v6; // et0
  volatile signed __int32 *v7; // rcx
  int result; // eax
  DWORD v9; // eax

  CurrentThreadId = GetCurrentThreadId();
  v5 = CurrentThreadId;
  v6 = _InterlockedIncrement(*(volatile signed __int32 **)this);
  v7 = *(volatile signed __int32 **)this;
  if ( !v6 )
  {
    *((_DWORD *)v7 + 1) = 1;
    *(_DWORD *)(*(_QWORD *)this + 8LL) = CurrentThreadId;
    return 0;
  }
  if ( *((_DWORD *)v7 + 2) == CurrentThreadId )
  {
    ++*((_DWORD *)v7 + 1);
    return 0;
  }
  v9 = WaitForSingleObject(*((HANDLE *)this + 1), a2);
  if ( !v9 || v9 == 128 )
  {
    *(_DWORD *)(*(_QWORD *)this + 4LL) = 1;
    *(_DWORD *)(*(_QWORD *)this + 8LL) = v5;
    return 0;
  }
  if ( v9 == 258 )
    return -2147286784;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002dbd0  mov     [rsp+arg_8], rbx
0x18002dbd5  mov     [rsp+arg_10], rsi
0x18002dbda  push    rdi
0x18002dbdb  sub     rsp, 20h
0x18002dbdf  mov     esi, edx
0x18002dbe1  mov     rbx, rcx
0x18002dbe4  call    cs:__imp_GetCurrentThreadId
0x18002dbea  mov     rcx, [rbx]
0x18002dbed  mov     edi, eax
0x18002dbef  lock inc dword ptr [rcx]
0x18002dbf2  mov     rcx, [rbx]
0x18002dbf5  jnz     short loc_18002DC16
0x18002dbf7  mov     dword ptr [rcx+4], 1
0x18002dbfe  mov     rcx, [rbx]
0x18002dc01  mov     [rcx+8], eax
0x18002dc04  xor     eax, eax
0x18002dc06  mov     rbx, [rsp+28h+arg_8]
0x18002dc0b  mov     rsi, [rsp+28h+arg_10]
0x18002dc10  add     rsp, 20h
0x18002dc14  pop     rdi
0x18002dc15  retn
0x18002dc16  cmp     [rcx+8], edi
0x18002dc19  jnz     short loc_18002DC30
0x18002dc1b  inc     dword ptr [rcx+4]
0x18002dc1e  xor     eax, eax
0x18002dc20  mov     rbx, [rsp+28h+arg_8]
0x18002dc25  mov     rsi, [rsp+28h+arg_10]
0x18002dc2a  add     rsp, 20h
0x18002dc2e  pop     rdi
0x18002dc2f  retn
0x18002dc30  mov     rcx, [rbx+8]; hHandle
0x18002dc34  mov     edx, esi; dwMilliseconds
0x18002dc36  call    cs:__imp_WaitForSingleObject
0x18002dc3c  test    eax, eax
0x18002dc3e  jz      short loc_18002DC63
0x18002dc40  cmp     eax, 80h
0x18002dc45  jz      short loc_18002DC63
0x18002dc47  cmp     eax, 102h
0x18002dc4c  jnz     short loc_18002DC75
0x18002dc4e  mov     eax, 80030100h
0x18002dc53  mov     rbx, [rsp+28h+arg_8]
0x18002dc58  mov     rsi, [rsp+28h+arg_10]
0x18002dc5d  add     rsp, 20h
0x18002dc61  pop     rdi
0x18002dc62  retn
0x18002dc63  mov     rax, [rbx]
0x18002dc66  mov     dword ptr [rax+4], 1
0x18002dc6d  mov     rax, [rbx]
0x18002dc70  mov     [rax+8], edi
0x18002dc73  jmp     short loc_18002DC04
0x18002dc75  call    cs:__imp_GetLastError
0x18002dc7b  test    eax, eax
0x18002dc7d  jle     short loc_18002DC06
0x18002dc7f  mov     rbx, [rsp+28h+arg_8]
0x18002dc84  mov     rsi, [rsp+28h+arg_10]
0x18002dc89  movzx   eax, ax
0x18002dc8c  or      eax, 80070000h
0x18002dc91  add     rsp, 20h
0x18002dc95  pop     rdi
0x18002dc96  retn
```
