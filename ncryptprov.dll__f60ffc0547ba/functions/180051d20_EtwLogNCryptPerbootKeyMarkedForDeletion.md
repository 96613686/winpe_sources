# EtwLogNCryptPerbootKeyMarkedForDeletion

- ea: `0x180051d20`
- end: `0x180051e83`
- name: `EtwLogNCryptPerbootKeyMarkedForDeletion`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180046eb0`

## callees

- `0x18000d3d0`
- `0x18001aea0`
- `0x1800206c8`
- `0x1800207dc`
- `0x180024260`
- `0x180038970`
- `0x180051d20`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051dd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051dd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051e4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051e4c`

## pseudocode

```c
__int64 __fastcall EtwLogNCryptPerbootKeyMarkedForDeletion(__int64 a1, __int64 a2, __int64 a3, char a4, char a5)
{
  int ProcessInfo; // eax
  char v10; // di
  __int64 v11; // rbx
  char CurrentThreadId; // al
  unsigned int v13; // edi
  unsigned int v15; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v18[528]; // [rsp+90h] [rbp-70h] BYREF

  v15 = 0;
  v17 = 0;
  hMem = 0;
  memset_0(v18, 0, 0x208u);
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  ProcessInfo = I_GetProcessInfo(&v15, &v17);
  v10 = v15;
  if ( !ProcessInfo )
    I_GetServiceTag(v15, 520, v18);
  I_GetUserId((LPWSTR *)&hMem);
  v11 = v17;
  if ( (byte_18007A101 & 0x10) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v13 = McTemplateU0zddzzzddzzd_EventWriteTransfer(
            (_DWORD)hMem,
            (unsigned int)"\x1B",
            a1,
            0,
            a4,
            a2,
            a3,
            v11,
            v10,
            CurrentThreadId,
            (__int64)hMem,
            (__int64)v18,
            a5);
  }
  else
  {
    v13 = 0;
  }
  if ( v11 )
    MSCryptFree(v11);
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x180051d20  push    rbp
0x180051d22  push    rbx
0x180051d23  push    rsi
0x180051d24  push    rdi
0x180051d25  push    r12
0x180051d27  push    r14
0x180051d29  push    r15
0x180051d2b  lea     rbp, [rsp-1B0h]
0x180051d33  sub     rsp, 2B0h
0x180051d3a  mov     rax, cs:__security_cookie
0x180051d41  xor     rax, rsp
0x180051d44  mov     [rbp+1E0h+var_40], rax
0x180051d4b  mov     r14, r8
0x180051d4e  mov     [rsp+2E0h+var_270], 0
0x180051d56  mov     rsi, rdx
0x180051d59  mov     [rbp+1E0h+var_260], 0
0x180051d61  mov     r15, rcx
0x180051d64  mov     [rsp+2E0h+hMem], 0
0x180051d6d  mov     ebx, 208h
0x180051d72  lea     rcx, [rbp+1E0h+var_250]; void *
0x180051d76  mov     r8d, ebx; Size
0x180051d79  xor     edx, edx; Val
0x180051d7b  mov     r12d, r9d
0x180051d7e  call    memset_0
0x180051d83  test    r15, r15
0x180051d86  jz      loc_180051E5C
0x180051d8c  test    rsi, rsi
0x180051d8f  jz      loc_180051E5C
0x180051d95  test    r14, r14
0x180051d98  jz      loc_180051E5C
0x180051d9e  lea     rdx, [rbp+1E0h+var_260]
0x180051da2  lea     rcx, [rsp+2E0h+var_270]
0x180051da7  call    I_GetProcessInfo
0x180051dac  mov     edi, [rsp+2E0h+var_270]
0x180051db0  test    eax, eax
0x180051db2  jnz     short loc_180051DC1
0x180051db4  mov     edx, ebx
0x180051db6  lea     r8, [rbp+1E0h+var_250]
0x180051dba  mov     ecx, edi
0x180051dbc  call    I_GetServiceTag
0x180051dc1  lea     rcx, [rsp+2E0h+hMem]; StringSid
0x180051dc6  call    I_GetUserId
0x180051dcb  test    cs:byte_18007A101, 10h
0x180051dd2  mov     rbx, [rbp+1E0h+var_260]
0x180051dd6  jz      short loc_180051E33
0x180051dd8  call    cs:__imp_GetCurrentThreadId
0x180051ddf  nop     dword ptr [rax+rax+00h]
0x180051de4  mov     ecx, [rbp+1E0h+arg_20]
0x180051dea  lea     rdx, ETW_LOG_NCRYPT_PERBOOT_KEY_MARKED_FOR_DELETION; "\x1B"
0x180051df1  mov     [rsp+2E0h+var_280], ecx
0x180051df5  xor     r9d, r9d
0x180051df8  lea     rcx, [rbp+1E0h+var_250]
0x180051dfc  mov     r8, r15
0x180051dff  mov     [rsp+2E0h+var_288], rcx
0x180051e04  mov     rcx, [rsp+2E0h+hMem]
0x180051e09  mov     [rsp+2E0h+var_290], rcx
0x180051e0e  mov     [rsp+2E0h+var_298], eax
0x180051e12  mov     [rsp+2E0h+var_2A0], edi
0x180051e16  mov     [rsp+2E0h+var_2A8], rbx
0x180051e1b  mov     [rsp+2E0h+var_2B0], r14
0x180051e20  mov     [rsp+2E0h+var_2B8], rsi
0x180051e25  mov     [rsp+2E0h+var_2C0], r12d
0x180051e2a  call    McTemplateU0zddzzzddzzd_EventWriteTransfer
0x180051e2f  mov     edi, eax
0x180051e31  jmp     short loc_180051E35
0x180051e33  xor     edi, edi
0x180051e35  test    rbx, rbx
0x180051e38  jz      short loc_180051E42
0x180051e3a  mov     rcx, rbx
0x180051e3d  call    MSCryptFree
0x180051e42  mov     rcx, [rsp+2E0h+hMem]; hMem
0x180051e47  test    rcx, rcx
0x180051e4a  jz      short loc_180051E58
0x180051e4c  call    cs:__imp_LocalFree
0x180051e53  nop     dword ptr [rax+rax+00h]
0x180051e58  mov     eax, edi
0x180051e5a  jmp     short loc_180051E61
0x180051e5c  mov     eax, 0C000000Dh
0x180051e61  mov     rcx, [rbp+1E0h+var_40]
0x180051e68  xor     rcx, rsp; StackCookie
0x180051e6b  call    __security_check_cookie
0x180051e70  add     rsp, 2B0h
0x180051e77  pop     r15
0x180051e79  pop     r14
0x180051e7b  pop     r12
0x180051e7d  pop     rdi
0x180051e7e  pop     rsi
0x180051e7f  pop     rbx
0x180051e80  pop     rbp
0x180051e81  retn
```
