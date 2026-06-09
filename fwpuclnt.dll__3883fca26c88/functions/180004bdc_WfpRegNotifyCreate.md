# WfpRegNotifyCreate

- ea: `0x180004bdc`
- end: `0x180004d36`
- name: `WfpRegNotifyCreate`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800045a0`
- `0x18001d5c0`

## callees

- `0x1800034e0`
- `0x180004a88`
- `0x180004bdc`
- `0x180005fc8`
- `0x180006230`
- `0x18003b4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004ca7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004ca7`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180004cd5`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180004cd5`

## string_xrefs

- `0x180004d12`: `CreateEventW`

## pseudocode

```c
__int64 __fastcall WfpRegNotifyCreate(
        __int64 a1,
        void *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  __int64 v10; // rdi
  HANDLE EventW; // rax
  __int64 v13; // rcx
  DWORD LastError; // eax
  __int64 v15; // rcx
  const char *v16; // rdx

  *a8 = 0;
  v10 = WfpMemAlloc(0x48u, 8u);
  if ( !v10 )
  {
    MEMORY[0] = -2147483646;
    v10 = WfpStringCopy(a2);
    if ( !v10 )
    {
      MEMORY[0x10] = 1;
      MEMORY[0x14] = a4;
      MEMORY[0x1C] = 0;
      MEMORY[0x20] = a6;
      MEMORY[0x28] = a7;
      EventW = CreateEventW(0, 0, 0, 0);
      MEMORY[0x38] = EventW;
      if ( EventW )
      {
        MEMORY[0x40] = RegisterWaitForSingleObjectEx(EventW, WfpRegNotifyOnChange, 0, 0xFFFFFFFFLL, 128);
        if ( MEMORY[0x40] )
        {
          v10 = WfpExecuteInPersistentThread(v13, 0);
          if ( !v10 )
          {
            *a8 = 0;
            return v10;
          }
          goto LABEL_2;
        }
        LastError = GetLastError();
        v16 = "RegisterWaitForSingleObjectEx";
      }
      else
      {
        LastError = GetLastError();
        v16 = "CreateEventW";
      }
      v10 = WfpReportSysErrorAsWinError(v15, v16, LastError);
      if ( !v10 )
        return v10;
    }
  }
LABEL_2:
  WfpRegNotifyDestroy(0);
  return v10;
}

```

## disassembly

```asm
0x180004bdc  mov     rax, rsp
0x180004bdf  mov     [rax+10h], rbx
0x180004be3  mov     [rax+18h], rbp
0x180004be7  mov     [rax+8], rcx
0x180004beb  push    rsi
0x180004bec  push    rdi
0x180004bed  push    r14
0x180004bef  sub     rsp, 30h
0x180004bf3  mov     rsi, [rsp+48h+arg_38]
0x180004bfb  lea     r8, [rax+8]
0x180004bff  mov     rbp, rdx
0x180004c02  mov     qword ptr [rax+8], 0
0x180004c0a  mov     edx, 8; dwFlags
0x180004c0f  mov     r14d, r9d
0x180004c12  mov     qword ptr [rsi], 0
0x180004c19  lea     ecx, [rdx+40h]; dwBytes
0x180004c1c  call    WfpMemAlloc
0x180004c21  mov     rbx, [rsp+48h+arg_0]
0x180004c26  mov     rdi, rax
0x180004c29  test    rax, rax
0x180004c2c  jz      short loc_180004C5F
0x180004c2e  mov     rcx, rbx
0x180004c31  call    WfpRegNotifyDestroy
0x180004c36  jmp     short loc_180004C48
0x180004c38  mov     r8d, eax
0x180004c3b  call    WfpReportSysErrorAsWinError
0x180004c40  mov     rdi, rax
0x180004c43  test    rax, rax
0x180004c46  jnz     short loc_180004C2E
0x180004c48  mov     rbx, [rsp+48h+arg_8]
0x180004c4d  mov     rax, rdi
0x180004c50  mov     rbp, [rsp+48h+arg_10]
0x180004c55  add     rsp, 30h
0x180004c59  pop     r14
0x180004c5b  pop     rdi
0x180004c5c  pop     rsi
0x180004c5d  retn
0x180004c5f  lea     r8, [rbx+8]
0x180004c63  mov     qword ptr [rbx], 0FFFFFFFF80000002h
0x180004c6a  mov     rcx, rbp; Src
0x180004c6d  call    WfpStringCopy
0x180004c72  mov     rdi, rax
0x180004c75  test    rax, rax
0x180004c78  jnz     short loc_180004C2E
0x180004c7a  mov     dword ptr [rbx+10h], 1
0x180004c81  xor     r9d, r9d; lpName
0x180004c84  mov     [rbx+14h], r14d
0x180004c88  xor     r8d, r8d; bInitialState
0x180004c8b  mov     [rbx+1Ch], eax
0x180004c8e  xor     edx, edx; bManualReset
0x180004c90  mov     rax, [rsp+48h+arg_28]
0x180004c95  xor     ecx, ecx; lpEventAttributes
0x180004c97  mov     [rbx+20h], rax
0x180004c9b  mov     rax, [rsp+48h+arg_30]
0x180004ca3  mov     [rbx+28h], rax
0x180004ca7  call    cs:__imp_CreateEventW
0x180004cae  nop     dword ptr [rax+rax+00h]
0x180004cb3  mov     [rbx+38h], rax
0x180004cb7  test    rax, rax
0x180004cba  jz      short loc_180004D06
0x180004cbc  or      r9d, 0FFFFFFFFh
0x180004cc0  mov     [rsp+48h+var_28], 80h
0x180004cc8  mov     r8, rbx
0x180004ccb  lea     rdx, WfpRegNotifyOnChange
0x180004cd2  mov     rcx, rax
0x180004cd5  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180004cdc  nop     dword ptr [rax+rax+00h]
0x180004ce1  mov     [rbx+40h], rax
0x180004ce5  test    rax, rax
0x180004ce8  jz      short loc_180004D1E
0x180004cea  mov     rdx, rbx
0x180004ced  call    WfpExecuteInPersistentThread
0x180004cf2  mov     rdi, rax
0x180004cf5  test    rax, rax
0x180004cf8  jnz     loc_180004C2E
0x180004cfe  mov     [rsi], rbx
0x180004d01  jmp     loc_180004C48
0x180004d06  call    cs:__imp_GetLastError
0x180004d0d  nop     dword ptr [rax+rax+00h]
0x180004d12  lea     rdx, aCreateeventw; "CreateEventW"
0x180004d19  jmp     loc_180004C38
0x180004d1e  call    cs:__imp_GetLastError
0x180004d25  nop     dword ptr [rax+rax+00h]
0x180004d2a  lea     rdx, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180004d31  jmp     loc_180004C38
```
