# CFveApiBase::VolumeNameToDevicePath(ushort const *,ushort * *)

- ea: `0x18000bb54`
- end: `0x18000bc42`
- name: `?VolumeNameToDevicePath@CFveApiBase@@SAJPEBGPEAPEAG@Z`
- size: `238`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ba70`
- `0x18007ccb8`
- `0x1800aaf90`

## callees

- `0x180005410`
- `0x18000bb54`
- `0x18000bc50`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000bb90`
- `ntdll!RtlSetThreadErrorMode` at `0x18000bc14`
- `ntdll!RtlSetThreadErrorMode` at `0x18011fa2e`
- `ntdll!RtlSetThreadErrorMode` at `0x18000bb90`
- `ntdll!RtlSetThreadErrorMode` at `0x18000bc14`
- `ntdll!RtlSetThreadErrorMode` at `0x18011fa2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fa15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fa15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bbc4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000bbc4`

## pseudocode

```c
__int64 __fastcall CFveApiBase::VolumeNameToDevicePath(LPCWSTR lpFileName, unsigned __int16 **a2)
{
  __int64 v4; // rbx
  HANDLE FileW; // rax
  unsigned int LastHresultError; // eax
  unsigned int v7; // edi
  ULONG NewMode; // [rsp+48h] [rbp-20h] BYREF

  v4 = -1;
  NewMode = 0;
  RtlSetThreadErrorMode(0x10u, &NewMode);
  if ( lpFileName )
  {
    FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
    v4 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
      LastHresultError = GetLastHresultError();
    else
      LastHresultError = CFveApiBase::VolumeHandleToDevicePath(FileW, a2);
    v7 = LastHresultError;
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  RtlSetThreadErrorMode(NewMode, 0);
  return v7;
}

```

## disassembly

```asm
0x18000bb54  mov     r11, rsp
0x18000bb57  mov     [r11+18h], rbx
0x18000bb5b  mov     [r11+20h], rsi
0x18000bb5f  push    rdi
0x18000bb60  sub     rsp, 60h
0x18000bb64  mov     rax, cs:__security_cookie
0x18000bb6b  xor     rax, rsp
0x18000bb6e  mov     [rsp+68h+var_18], rax
0x18000bb73  mov     rsi, rdx
0x18000bb76  mov     rdi, rcx
0x18000bb79  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bb7d  mov     [r11-28h], rbx
0x18000bb81  mov     [rsp+68h+NewMode], 0
0x18000bb89  lea     rdx, [r11-20h]; OldMode
0x18000bb8d  lea     ecx, [rbx+11h]; NewMode
0x18000bb90  call    cs:__imp_RtlSetThreadErrorMode
0x18000bb97  nop     dword ptr [rax+rax+00h]
0x18000bb9c  nop
0x18000bb9d  test    rdi, rdi
0x18000bba0  jz      short loc_18000BBF4
0x18000bba2  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000bbab  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000bbb3  lea     r8d, [rbx+4]; dwShareMode
0x18000bbb7  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000bbbc  xor     r9d, r9d; lpSecurityAttributes
0x18000bbbf  xor     edx, edx; dwDesiredAccess
0x18000bbc1  mov     rcx, rdi; lpFileName
0x18000bbc4  call    cs:__imp_CreateFileW
0x18000bbcb  nop     dword ptr [rax+rax+00h]
0x18000bbd0  mov     rbx, rax
0x18000bbd3  mov     [rsp+68h+var_28], rax
0x18000bbd8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bbdc  jz      short loc_18000BBED
0x18000bbde  mov     rdx, rsi; unsigned __int16 **
0x18000bbe1  mov     rcx, rax; hDevice
0x18000bbe4  call    ?VolumeHandleToDevicePath@CFveApiBase@@SAJPEAXPEAPEAG@Z; CFveApiBase::VolumeHandleToDevicePath(void *,ushort * *)
0x18000bbe9  mov     edi, eax
0x18000bbeb  jmp     short loc_18000BBF9
0x18000bbed  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000bbf2  jmp     short loc_18000BBE9
0x18000bbf4  mov     edi, 80070057h
0x18000bbf9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000bbfd  jz      short loc_18000BC0E
0x18000bbff  mov     rcx, rbx; hObject
0x18000bc02  call    cs:__imp_CloseHandle
0x18000bc09  nop     dword ptr [rax+rax+00h]
0x18000bc0e  xor     edx, edx; OldMode
0x18000bc10  mov     ecx, [rsp+68h+NewMode]; NewMode
0x18000bc14  call    cs:__imp_RtlSetThreadErrorMode
0x18000bc1b  nop     dword ptr [rax+rax+00h]
0x18000bc20  mov     eax, edi
0x18000bc22  mov     rcx, [rsp+68h+var_18]
0x18000bc27  xor     rcx, rsp; StackCookie
0x18000bc2a  call    __security_check_cookie
0x18000bc2f  lea     r11, [rsp+68h+var_8]
0x18000bc34  mov     rbx, [r11+20h]
0x18000bc38  mov     rsi, [r11+28h]
0x18000bc3c  mov     rsp, r11
0x18000bc3f  pop     rdi
0x18000bc40  retn
0x18011fa02  push    rbp
0x18011fa04  sub     rsp, 40h
0x18011fa08  mov     rbp, rdx
0x18011fa0b  mov     rcx, [rbp+40h]; hObject
0x18011fa0f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011fa13  jz      short loc_18011FA29
0x18011fa15  call    cs:__imp_CloseHandle
0x18011fa1c  nop     dword ptr [rax+rax+00h]
0x18011fa21  mov     qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x18011fa29  xor     edx, edx; OldMode
0x18011fa2b  mov     ecx, [rbp+48h]; NewMode
0x18011fa2e  call    cs:__imp_RtlSetThreadErrorMode
0x18011fa35  nop     dword ptr [rax+rax+00h]
0x18011fa3a  nop
0x18011fa3b  add     rsp, 40h
0x18011fa3f  pop     rbp
0x18011fa40  retn
```
