# wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)

- ea: `0x140003cf0`
- end: `0x140003e33`
- name: `?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE hHandle, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005298`

## callees

- `0x140003cf0`
- `0x140004d34`
- `0x140004d54`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140003d02`
- `KERNEL32!WaitForSingleObject` at `0x140003de4`
- `KERNEL32!WaitForSingleObject` at `0x140003d02`
- `KERNEL32!WaitForSingleObject` at `0x140003de4`
- `KERNEL32!GetLastError` at `0x140003d78`
- `KERNEL32!GetLastError` at `0x140003dd2`
- `KERNEL32!GetLastError` at `0x140003d78`
- `KERNEL32!GetLastError` at `0x140003dd2`
- `KERNEL32!ReleaseSemaphore` at `0x140003d4f`
- `KERNEL32!ReleaseSemaphore` at `0x140003d6e`
- `KERNEL32!ReleaseSemaphore` at `0x140003d9c`
- `KERNEL32!ReleaseSemaphore` at `0x140003dc8`
- `KERNEL32!ReleaseSemaphore` at `0x140003d4f`
- `KERNEL32!ReleaseSemaphore` at `0x140003d6e`
- `KERNEL32!ReleaseSemaphore` at `0x140003d9c`
- `KERNEL32!ReleaseSemaphore` at `0x140003dc8`

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
0x140003cf0  mov     [rsp+arg_0], rsi
0x140003cf5  push    rdi; int
0x140003cf6  sub     rsp, 20h
0x140003cfa  mov     rsi, rdx
0x140003cfd  mov     rdi, rcx
0x140003d00  xor     edx, edx; dwMilliseconds
0x140003d02  call    cs:__imp_WaitForSingleObject
0x140003d08  cmp     eax, 0FFFFFFFFh
0x140003d0b  jnz     short loc_140003D21
0x140003d0d  mov     edx, 9Ch; void *
0x140003d12  mov     rcx, [rsp+28h]; this
0x140003d17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140003d1c  jmp     loc_140003E28
0x140003d21  test    eax, eax
0x140003d23  jz      short loc_140003D36
0x140003d25  cmp     eax, 102h
0x140003d2a  jz      short loc_140003D36
0x140003d2c  mov     edx, 9Dh
0x140003d31  jmp     loc_140003E13
0x140003d36  mov     [rsp+28h+PreviousCount], 0
0x140003d3e  mov     edx, 1; lReleaseCount
0x140003d43  mov     rcx, rdi; hSemaphore
0x140003d46  test    eax, eax
0x140003d48  jnz     short loc_140003D8F
0x140003d4a  lea     r8, [rsp+28h+PreviousCount]; lpPreviousCount
0x140003d4f  call    cs:__imp_ReleaseSemaphore
0x140003d55  test    eax, eax
0x140003d57  jnz     short loc_140003D60
0x140003d59  mov     edx, 0A5h
0x140003d5e  jmp     short loc_140003D12
0x140003d60  inc     [rsp+28h+PreviousCount]
0x140003d64  xor     r8d, r8d; lpPreviousCount
0x140003d67  mov     rcx, rdi; hSemaphore
0x140003d6a  lea     edx, [r8+1]; lReleaseCount
0x140003d6e  call    cs:__imp_ReleaseSemaphore
0x140003d74  test    eax, eax
0x140003d76  jnz     short loc_140003D85
0x140003d78  call    cs:__imp_GetLastError
0x140003d7e  cmp     eax, 12Ah
0x140003d83  jz      short loc_140003E04
0x140003d85  mov     edx, 0AAh
0x140003d8a  jmp     loc_140003E13
0x140003d8f  lea     r8, [rsp+28h+arg_18]; lpPreviousCount
0x140003d94  mov     [rsp+28h+arg_18], 0
0x140003d9c  call    cs:__imp_ReleaseSemaphore
0x140003da2  test    eax, eax
0x140003da4  jnz     short loc_140003DB0
0x140003da6  mov     edx, 0B4h
0x140003dab  jmp     loc_140003D12
0x140003db0  cmp     [rsp+28h+arg_18], 0
0x140003db5  jz      short loc_140003DBE
0x140003db7  mov     edx, 0B5h
0x140003dbc  jmp     short loc_140003E13
0x140003dbe  xor     r8d, r8d; lpPreviousCount
0x140003dc1  mov     rcx, rdi; hSemaphore
0x140003dc4  lea     edx, [r8+1]; lReleaseCount
0x140003dc8  call    cs:__imp_ReleaseSemaphore
0x140003dce  test    eax, eax
0x140003dd0  jnz     short loc_140003E0E
0x140003dd2  call    cs:__imp_GetLastError
0x140003dd8  cmp     eax, 12Ah
0x140003ddd  jnz     short loc_140003E0E
0x140003ddf  xor     edx, edx; dwMilliseconds
0x140003de1  mov     rcx, rdi; hHandle
0x140003de4  call    cs:__imp_WaitForSingleObject
0x140003dea  cmp     eax, 0FFFFFFFFh
0x140003ded  jnz     short loc_140003DF9
0x140003def  mov     edx, 0BBh
0x140003df4  jmp     loc_140003D12
0x140003df9  test    eax, eax
0x140003dfb  jz      short loc_140003E04
0x140003dfd  mov     edx, 0BCh
0x140003e02  jmp     short loc_140003E13
0x140003e04  mov     eax, [rsp+28h+PreviousCount]
0x140003e08  mov     [rsi], eax
0x140003e0a  xor     eax, eax
0x140003e0c  jmp     short loc_140003E28
0x140003e0e  mov     edx, 0B8h; void *
0x140003e13  mov     rcx, [rsp+28h]; this
0x140003e18  mov     r9d, 8000FFFFh; char *
0x140003e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e23  mov     eax, 8000FFFFh
0x140003e28  mov     rsi, [rsp+28h+arg_0]
0x140003e2d  add     rsp, 20h
0x140003e31  pop     rdi
0x140003e32  retn
```
