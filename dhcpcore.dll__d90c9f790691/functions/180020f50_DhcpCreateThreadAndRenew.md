# DhcpCreateThreadAndRenew

- ea: `0x180020f50`
- end: `0x180021075`
- name: `DhcpCreateThreadAndRenew`
- size: `293`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800249ec`

## callees

- `0x180002534`
- `0x18001bdc0`
- `0x180020f50`
- `0x18004d4c0`
- `0x18004dbc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ff8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fb1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020fe6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020fe6`

## pseudocode

```c
__int64 __fastcall DhcpCreateThreadAndRenew(LPVOID lpParameter)
{
  DWORD v1; // esi
  __int64 v3; // rcx
  __int64 v4; // rbx
  HANDLE v5; // rax
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  ThreadId = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 121, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *((_QWORD *)lpParameter + 3));
  v3 = *((_QWORD *)lpParameter + 269);
  v4 = *((_QWORD *)lpParameter + 3);
  if ( v3 )
  {
    v1 = WaitForSingleObjectWin32Err(v3, 0);
    if ( v1 )
      goto LABEL_11;
    CloseHandle(*((HANDLE *)lpParameter + 269));
    *((_QWORD *)lpParameter + 269) = 0;
  }
  _InterlockedIncrement((volatile signed __int32 *)lpParameter + 4);
  v5 = CreateThread(0, 0, DhcpRenewThread, lpParameter, 0, &ThreadId);
  *((_QWORD *)lpParameter + 269) = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_dJ(1025, 122, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError, v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpParameter + 4, 0xFFFFFFFF) == 1 )
      DhcpDestroyContextEx(lpParameter);
  }
LABEL_11:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dJ(1028, 123, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v1, v4);
  return v1;
}

```

## disassembly

```asm
0x180020f50  mov     [rsp+arg_8], rbx
0x180020f55  mov     [rsp+arg_10], rsi
0x180020f5a  push    rdi
0x180020f5b  sub     rsp, 30h
0x180020f5f  xor     esi, esi
0x180020f61  mov     rdi, rcx
0x180020f64  mov     [rsp+38h+ThreadId], esi
0x180020f68  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020f6f  jz      short loc_180020F89
0x180020f71  mov     r9, [rdi+18h]
0x180020f75  lea     edx, [rsi+79h]
0x180020f78  mov     ecx, 404h
0x180020f7d  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180020f84  call    WPP_SF_q
0x180020f89  mov     rcx, [rdi+868h]
0x180020f90  mov     rbx, [rdi+18h]
0x180020f94  test    rcx, rcx
0x180020f97  jz      short loc_180020FC2
0x180020f99  xor     edx, edx
0x180020f9b  call    WaitForSingleObjectWin32Err
0x180020fa0  mov     esi, eax
0x180020fa2  test    eax, eax
0x180020fa4  jnz     loc_18002103C
0x180020faa  mov     rcx, [rdi+868h]; hObject
0x180020fb1  call    cs:__imp_CloseHandle
0x180020fb7  mov     qword ptr [rdi+868h], 0
0x180020fc2  lock inc dword ptr [rdi+10h]
0x180020fc6  lea     rax, [rsp+38h+ThreadId]
0x180020fcb  mov     r9, rdi; lpParameter
0x180020fce  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180020fd3  lea     r8, DhcpRenewThread; lpStartAddress
0x180020fda  xor     edx, edx; dwStackSize
0x180020fdc  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180020fe4  xor     ecx, ecx; lpThreadAttributes
0x180020fe6  call    cs:__imp_CreateThread
0x180020fec  mov     [rdi+868h], rax
0x180020ff3  test    rax, rax
0x180020ff6  jnz     short loc_18002103C
0x180020ff8  call    cs:__imp_GetLastError
0x180020ffe  mov     esi, eax
0x180021000  test    byte ptr cs:xmmword_1800616A0, 2
0x180021007  jz      short loc_180021027
0x180021009  mov     edx, 7Ah ; 'z'
0x18002100e  mov     qword ptr [rsp+38h+dwCreationFlags], rbx
0x180021013  mov     ecx, 401h
0x180021018  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002101f  mov     r9d, eax
0x180021022  call    WPP_SF_dJ
0x180021027  or      eax, 0FFFFFFFFh
0x18002102a  lock xadd [rdi+10h], eax
0x18002102f  cmp     eax, 1
0x180021032  jnz     short loc_18002103C
0x180021034  mov     rcx, rdi
0x180021037  call    DhcpDestroyContextEx
0x18002103c  test    byte ptr cs:xmmword_1800616A0, 10h
0x180021043  jz      short loc_180021063
0x180021045  mov     edx, 7Bh ; '{'
0x18002104a  mov     qword ptr [rsp+38h+dwCreationFlags], rbx
0x18002104f  mov     ecx, 404h
0x180021054  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002105b  mov     r9d, esi
0x18002105e  call    WPP_SF_dJ
0x180021063  mov     rbx, [rsp+38h+arg_8]
0x180021068  mov     eax, esi
0x18002106a  mov     rsi, [rsp+38h+arg_10]
0x18002106f  add     rsp, 30h
0x180021073  pop     rdi
0x180021074  retn
```
