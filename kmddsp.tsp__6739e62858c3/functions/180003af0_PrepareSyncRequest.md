# PrepareSyncRequest

- ea: `0x180003af0`
- end: `0x180003ba1`
- name: `PrepareSyncRequest`
- size: `177`
- prototype: `__int64 __fastcall(int, int, unsigned int, _QWORD *)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x180003488`
- `0x180003ba8`
- `0x180004520`
- `0x180004670`
- `0x180004880`
- `0x180004fe0`
- `0x1800051d0`
- `0x180005320`
- `0x180005440`
- `0x180005550`
- `0x1800058b0`
- `0x180005bc0`
- `0x180005d00`
- `0x180005db0`
- `0x180006140`
- `0x180006820`
- `0x180006a20`
- `0x180006e30`
- `0x1800070c0`
- `0x1800072e0`
- `0x1800073b0`
- `0x1800074c0`
- `0x1800075b0`

## callees

- `0x18000274c`
- `0x180003af0`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003b84`
- `KERNEL32!LeaveCriticalSection` at `0x180003b84`
- `KERNEL32!EnterCriticalSection` at `0x180003b4f`
- `KERNEL32!EnterCriticalSection` at `0x180003b4f`

## pseudocode

```c
__int64 __fastcall PrepareSyncRequest(int a1, int a2, unsigned int a3, _QWORD *a4)
{
  const char *v8; // rdx
  __int64 result; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  unsigned int v12; // eax

  if ( a3 + 20 < a3 )
  {
    v8 = "PrepareSyncRequest: Arithmatic Overflow error.Failed to alloc async req for oid(%x)";
LABEL_3:
    TspLog(1, v8);
    return 2147483716LL;
  }
  v10 = (_DWORD *)AllocRequest();
  v11 = v10;
  if ( !v10 )
  {
    v8 = "PrepareSyncRequest: failed to alloc sync req for oid(%x)";
    goto LABEL_3;
  }
  v10[1] = a1;
  v10[2] = a2;
  v10[3] = a3;
  EnterCriticalSection(&gRequestIDCritSec);
  v12 = gdwRequestID + 1;
  gdwRequestID = v12;
  v11[4] = v12;
  if ( v12 >= 0x7FFFFFFF )
    gdwRequestID = 1;
  LeaveCriticalSection(&gRequestIDCritSec);
  result = 0;
  *a4 = v11;
  return result;
}

```

## disassembly

```asm
0x180003af0  push    rbx
0x180003af2  push    rbp
0x180003af3  push    rsi
0x180003af4  push    rdi
0x180003af5  push    r14
0x180003af7  sub     rsp, 20h
0x180003afb  mov     edi, ecx
0x180003afd  mov     r14, r9
0x180003b00  lea     ecx, [r8+14h]
0x180003b04  mov     esi, r8d
0x180003b07  mov     ebp, edx
0x180003b09  cmp     ecx, r8d
0x180003b0c  jnb     short loc_180003B29
0x180003b0e  lea     rdx, aPreparesyncreq_0; "PrepareSyncRequest: Arithmatic Overflow"...
0x180003b15  mov     r8d, edi
0x180003b18  mov     ecx, 1
0x180003b1d  call    TspLog
0x180003b22  mov     eax, 80000044h
0x180003b27  jmp     short loc_180003B95
0x180003b29  call    AllocRequest
0x180003b2e  mov     rbx, rax
0x180003b31  test    rax, rax
0x180003b34  jnz     short loc_180003B3F
0x180003b36  lea     rdx, aPreparesyncreq; "PrepareSyncRequest: failed to alloc syn"...
0x180003b3d  jmp     short loc_180003B15
0x180003b3f  lea     rcx, gRequestIDCritSec; lpCriticalSection
0x180003b46  mov     [rax+4], edi
0x180003b49  mov     [rax+8], ebp
0x180003b4c  mov     [rax+0Ch], esi
0x180003b4f  call    cs:__imp_EnterCriticalSection
0x180003b56  nop     dword ptr [rax+rax+00h]
0x180003b5b  mov     eax, cs:gdwRequestID
0x180003b61  inc     eax
0x180003b63  mov     cs:gdwRequestID, eax
0x180003b69  mov     [rbx+10h], eax
0x180003b6c  cmp     eax, 7FFFFFFFh
0x180003b71  jb      short loc_180003B7D
0x180003b73  mov     cs:gdwRequestID, 1
0x180003b7d  lea     rcx, gRequestIDCritSec; lpCriticalSection
0x180003b84  call    cs:__imp_LeaveCriticalSection
0x180003b8b  nop     dword ptr [rax+rax+00h]
0x180003b90  xor     eax, eax
0x180003b92  mov     [r14], rbx
0x180003b95  add     rsp, 20h
0x180003b99  pop     r14
0x180003b9b  pop     rdi
0x180003b9c  pop     rsi
0x180003b9d  pop     rbp
0x180003b9e  pop     rbx
0x180003b9f  retn
```
