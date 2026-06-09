# wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)

- ea: `0x1400039f0`
- end: `0x140003b33`
- name: `?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE hHandle, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004840`

## callees

- `0x1400039f0`
- `0x140004434`
- `0x140004454`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003a78`
- `KERNEL32!GetLastError` at `0x140003ad2`
- `KERNEL32!GetLastError` at `0x140003a78`
- `KERNEL32!GetLastError` at `0x140003ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003a4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003a6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003a9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003ac8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003a4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003a6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003a9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140003ac8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003a02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003ae4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003a02`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003ae4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::GetValueFromSemaphore(HANDLE hHandle, int *a2)
{
  DWORD v4; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rdx
  __int64 v9; // rdx
  DWORD v10; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int PreviousCount; // [rsp+40h] [rbp+18h] BYREF
  int v14; // [rsp+48h] [rbp+20h] BYREF

  v4 = WaitForSingleObject(hHandle, 0);
  if ( v4 == -1 )
  {
    v7 = 156;
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
  }
  if ( !v4 || v4 == 258 )
  {
    PreviousCount = 0;
    if ( v4 )
    {
      v14 = 0;
      if ( !ReleaseSemaphore(hHandle, 1, &v14) )
      {
        v7 = 180;
        return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
      }
      if ( v14 )
      {
        v9 = 181;
        goto LABEL_25;
      }
      if ( ReleaseSemaphore(hHandle, 1, 0) || GetLastError() != 298 )
      {
        v9 = 184;
        goto LABEL_25;
      }
      v10 = WaitForSingleObject(hHandle, 0);
      if ( v10 == -1 )
      {
        v7 = 187;
        return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
      }
      if ( v10 )
      {
        v9 = 188;
        goto LABEL_25;
      }
    }
    else
    {
      if ( !ReleaseSemaphore(hHandle, 1, &PreviousCount) )
      {
        v7 = 165;
        return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
      }
      ++PreviousCount;
      if ( ReleaseSemaphore(hHandle, 1, 0) || GetLastError() != 298 )
      {
        v9 = 170;
        goto LABEL_25;
      }
    }
    *a2 = PreviousCount;
    return 0;
  }
  v9 = 157;
LABEL_25:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v5, (const char *)0x8000FFFFLL, v11);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1400039f0  mov     [rsp+arg_0], rsi
0x1400039f5  push    rdi; int
0x1400039f6  sub     rsp, 20h
0x1400039fa  mov     rsi, rdx
0x1400039fd  mov     rdi, rcx
0x140003a00  xor     edx, edx; dwMilliseconds
0x140003a02  call    cs:__imp_WaitForSingleObject
0x140003a08  cmp     eax, 0FFFFFFFFh
0x140003a0b  jnz     short loc_140003A21
0x140003a0d  mov     edx, 9Ch; void *
0x140003a12  mov     rcx, [rsp+28h]; this
0x140003a17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140003a1c  jmp     loc_140003B28
0x140003a21  test    eax, eax
0x140003a23  jz      short loc_140003A36
0x140003a25  cmp     eax, 102h
0x140003a2a  jz      short loc_140003A36
0x140003a2c  mov     edx, 9Dh
0x140003a31  jmp     loc_140003B13
0x140003a36  mov     [rsp+28h+PreviousCount], 0
0x140003a3e  mov     edx, 1; lReleaseCount
0x140003a43  mov     rcx, rdi; hSemaphore
0x140003a46  test    eax, eax
0x140003a48  jnz     short loc_140003A8F
0x140003a4a  lea     r8, [rsp+28h+PreviousCount]; lpPreviousCount
0x140003a4f  call    cs:__imp_ReleaseSemaphore
0x140003a55  test    eax, eax
0x140003a57  jnz     short loc_140003A60
0x140003a59  mov     edx, 0A5h
0x140003a5e  jmp     short loc_140003A12
0x140003a60  inc     [rsp+28h+PreviousCount]
0x140003a64  xor     r8d, r8d; lpPreviousCount
0x140003a67  mov     rcx, rdi; hSemaphore
0x140003a6a  lea     edx, [r8+1]; lReleaseCount
0x140003a6e  call    cs:__imp_ReleaseSemaphore
0x140003a74  test    eax, eax
0x140003a76  jnz     short loc_140003A85
0x140003a78  call    cs:__imp_GetLastError
0x140003a7e  cmp     eax, 12Ah
0x140003a83  jz      short loc_140003B04
0x140003a85  mov     edx, 0AAh
0x140003a8a  jmp     loc_140003B13
0x140003a8f  lea     r8, [rsp+28h+arg_18]; lpPreviousCount
0x140003a94  mov     [rsp+28h+arg_18], 0
0x140003a9c  call    cs:__imp_ReleaseSemaphore
0x140003aa2  test    eax, eax
0x140003aa4  jnz     short loc_140003AB0
0x140003aa6  mov     edx, 0B4h
0x140003aab  jmp     loc_140003A12
0x140003ab0  cmp     [rsp+28h+arg_18], 0
0x140003ab5  jz      short loc_140003ABE
0x140003ab7  mov     edx, 0B5h
0x140003abc  jmp     short loc_140003B13
0x140003abe  xor     r8d, r8d; lpPreviousCount
0x140003ac1  mov     rcx, rdi; hSemaphore
0x140003ac4  lea     edx, [r8+1]; lReleaseCount
0x140003ac8  call    cs:__imp_ReleaseSemaphore
0x140003ace  test    eax, eax
0x140003ad0  jnz     short loc_140003B0E
0x140003ad2  call    cs:__imp_GetLastError
0x140003ad8  cmp     eax, 12Ah
0x140003add  jnz     short loc_140003B0E
0x140003adf  xor     edx, edx; dwMilliseconds
0x140003ae1  mov     rcx, rdi; hHandle
0x140003ae4  call    cs:__imp_WaitForSingleObject
0x140003aea  cmp     eax, 0FFFFFFFFh
0x140003aed  jnz     short loc_140003AF9
0x140003aef  mov     edx, 0BBh
0x140003af4  jmp     loc_140003A12
0x140003af9  test    eax, eax
0x140003afb  jz      short loc_140003B04
0x140003afd  mov     edx, 0BCh
0x140003b02  jmp     short loc_140003B13
0x140003b04  mov     eax, [rsp+28h+PreviousCount]
0x140003b08  mov     [rsi], eax
0x140003b0a  xor     eax, eax
0x140003b0c  jmp     short loc_140003B28
0x140003b0e  mov     edx, 0B8h; void *
0x140003b13  mov     rcx, [rsp+28h]; this
0x140003b18  mov     r9d, 8000FFFFh; char *
0x140003b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b23  mov     eax, 8000FFFFh
0x140003b28  mov     rsi, [rsp+28h+arg_0]
0x140003b2d  add     rsp, 20h
0x140003b31  pop     rdi
0x140003b32  retn
```
