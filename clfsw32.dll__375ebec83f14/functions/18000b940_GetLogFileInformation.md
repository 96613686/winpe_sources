# GetLogFileInformation

- ea: `0x18000b940`
- end: `0x18000b9bb`
- name: `GetLogFileInformation`
- size: `123`
- prototype: `BOOL __stdcall(HANDLE hLog, PCLFS_INFORMATION pinfoBuffer, PULONG cbBuffer)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aec0`
- `0x18000be70`
- `0x18000d9b0`
- `0x180010bdc`
- `0x180013cc0`

## callees

- `0x180008bfc`
- `0x18000b940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9a6`

## pseudocode

```c
BOOL __stdcall GetLogFileInformation(HANDLE hLog, PCLFS_INFORMATION pinfoBuffer, PULONG cbBuffer)
{
  BOOL v3; // ebx
  DWORD v4; // ecx
  DWORD InformationLog; // eax
  struct _OVERLAPPED *v7; // [rsp+30h] [rbp-18h]

  v3 = 0;
  if ( !cbBuffer )
  {
    v4 = 87;
LABEL_12:
    SetLastError(v4);
    return 0;
  }
  if ( !*cbBuffer )
    goto LABEL_11;
  if ( *cbBuffer < 0x78 )
  {
    *cbBuffer = 120;
    v4 = 122;
    goto LABEL_12;
  }
  if ( !pinfoBuffer )
  {
LABEL_11:
    v4 = 1784;
    goto LABEL_12;
  }
  InformationLog = NtQueryInformationLog(hLog, 0, 0, pinfoBuffer, cbBuffer, ClfsLogBasicInformation, v7);
  if ( !InformationLog )
    return 1;
  SetLastError(InformationLog);
  return v3;
}

```

## disassembly

```asm
0x18000b940  push    rbx
0x18000b942  sub     rsp, 40h
0x18000b946  xor     ebx, ebx
0x18000b948  test    r8, r8
0x18000b94b  jnz     short loc_18000B952
0x18000b94d  lea     ecx, [rbx+57h]
0x18000b950  jmp     short loc_18000B9A6
0x18000b952  cmp     [r8], ebx
0x18000b955  jz      short loc_18000B9A1
0x18000b957  cmp     dword ptr [r8], 78h ; 'x'
0x18000b95b  jnb     short loc_18000B96B
0x18000b95d  mov     dword ptr [r8], 78h ; 'x'
0x18000b964  mov     ecx, 7Ah ; 'z'; void *
0x18000b969  jmp     short loc_18000B9A6
0x18000b96b  test    rdx, rdx
0x18000b96e  jz      short loc_18000B9A1
0x18000b970  mov     r9, rdx; void *
0x18000b973  mov     [rsp+48h+var_20], ebx; enum _CLS_LOG_INFORMATION_CLASS
0x18000b977  mov     [rsp+48h+var_28], r8; unsigned int *
0x18000b97c  xor     edx, edx; void *
0x18000b97e  xor     r8d, r8d; unsigned int
0x18000b981  call    ?NtQueryInformationLog@@YAKPEAX0K0PEAKW4_CLS_LOG_INFORMATION_CLASS@@PEAU_OVERLAPPED@@@Z; NtQueryInformationLog(void *,void *,ulong,void *,ulong *,_CLS_LOG_INFORMATION_CLASS,_OVERLAPPED *)
0x18000b986  test    eax, eax
0x18000b988  jnz     short loc_18000B98F
0x18000b98a  lea     ebx, [rax+1]
0x18000b98d  jmp     short loc_18000B99D
0x18000b98f  mov     ecx, eax; dwErrCode
0x18000b991  call    cs:__imp_SetLastError
0x18000b998  nop     dword ptr [rax+rax+00h]
0x18000b99d  mov     eax, ebx
0x18000b99f  jmp     short loc_18000B9B4
0x18000b9a1  mov     ecx, 6F8h; dwErrCode
0x18000b9a6  call    cs:__imp_SetLastError
0x18000b9ad  nop     dword ptr [rax+rax+00h]
0x18000b9b2  xor     eax, eax
0x18000b9b4  add     rsp, 40h
0x18000b9b8  pop     rbx
0x18000b9b9  retn
```
