# SpinCallWinVerityTrust(HWND__ *,_GUID const *,_WINTRUST_DATA * const)

- ea: `0x14000c02c`
- end: `0x14000c0f3`
- name: `?SpinCallWinVerityTrust@@YAJPEAUHWND__@@PEBU_GUID@@QEAU_WINTRUST_DATA@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(HWND, const struct _GUID *, struct _WINTRUST_DATA *const)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c0fc`

## callees

- `0x14000c02c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000c0c2`
- `KERNEL32!CloseHandle` at `0x14000c0c2`
- `KERNEL32!CreateThread` at `0x14000c065`
- `KERNEL32!CreateThread` at `0x14000c065`
- `KERNEL32!GetExitCodeThread` at `0x14000c093`
- `KERNEL32!GetExitCodeThread` at `0x14000c093`
- `KERNEL32!GetLastError` at `0x14000c0a3`
- `KERNEL32!GetLastError` at `0x14000c0d4`
- `KERNEL32!GetLastError` at `0x14000c0a3`
- `KERNEL32!GetLastError` at `0x14000c0d4`
- `KERNEL32!WaitForSingleObject` at `0x14000c07f`
- `KERNEL32!WaitForSingleObject` at `0x14000c07f`

## pseudocode

```c
signed int __fastcall SpinCallWinVerityTrust(HWND a1, const struct _GUID *a2, struct _WINTRUST_DATA *const a3)
{
  HANDLE Thread; // rax
  void *v4; // rbx
  int LastError; // eax
  signed int result; // eax
  _QWORD v7[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD ExitCode; // [rsp+60h] [rbp+8h] BYREF

  v7[0] = a1;
  v7[1] = a2;
  v7[2] = a3;
  ExitCode = 0;
  Thread = CreateThread(0, 0, WinVerifyTrustThreadProc, v7, 0, 0);
  v4 = Thread;
  if ( Thread )
  {
    WaitForSingleObject(Thread, 0xFFFFFFFF);
    if ( !GetExitCodeThread(v4, &ExitCode) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ExitCode = LastError;
    }
    CloseHandle(v4);
    return ExitCode;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x14000c02c  mov     rax, rsp
0x14000c02f  push    rbx
0x14000c030  sub     rsp, 50h
0x14000c034  mov     [rax-28h], rcx
0x14000c038  lea     r9, [rax-28h]; lpParameter
0x14000c03c  mov     [rax-20h], rdx
0x14000c040  xor     ecx, ecx; lpThreadAttributes
0x14000c042  mov     [rax-18h], r8
0x14000c046  xor     edx, edx; dwStackSize
0x14000c048  mov     qword ptr [rax-30h], 0
0x14000c050  lea     r8, ?WinVerifyTrustThreadProc@@YAKPEAU_WINVERIFYTRUST_PARAMS@@@Z; lpStartAddress
0x14000c057  mov     dword ptr [rax+8], 0
0x14000c05e  mov     dword ptr [rax-38h], 0
0x14000c065  call    cs:__imp_CreateThread
0x14000c06c  nop     dword ptr [rax+rax+00h]
0x14000c071  mov     rbx, rax
0x14000c074  test    rax, rax
0x14000c077  jz      short loc_14000C0D4
0x14000c079  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000c07c  mov     rcx, rax; hHandle
0x14000c07f  call    cs:__imp_WaitForSingleObject
0x14000c086  nop     dword ptr [rax+rax+00h]
0x14000c08b  lea     rdx, [rsp+58h+ExitCode]; lpExitCode
0x14000c090  mov     rcx, rbx; hThread
0x14000c093  call    cs:__imp_GetExitCodeThread
0x14000c09a  nop     dword ptr [rax+rax+00h]
0x14000c09f  test    eax, eax
0x14000c0a1  jnz     short loc_14000C0BF
0x14000c0a3  call    cs:__imp_GetLastError
0x14000c0aa  nop     dword ptr [rax+rax+00h]
0x14000c0af  test    eax, eax
0x14000c0b1  jle     short loc_14000C0BB
0x14000c0b3  movzx   eax, ax
0x14000c0b6  or      eax, 80070000h
0x14000c0bb  mov     [rsp+58h+ExitCode], eax
0x14000c0bf  mov     rcx, rbx; hObject
0x14000c0c2  call    cs:__imp_CloseHandle
0x14000c0c9  nop     dword ptr [rax+rax+00h]
0x14000c0ce  mov     eax, [rsp+58h+ExitCode]
0x14000c0d2  jmp     short loc_14000C0EC
0x14000c0d4  call    cs:__imp_GetLastError
0x14000c0db  nop     dword ptr [rax+rax+00h]
0x14000c0e0  test    eax, eax
0x14000c0e2  jle     short loc_14000C0EC
0x14000c0e4  movzx   eax, ax
0x14000c0e7  or      eax, 80070000h
0x14000c0ec  add     rsp, 50h
0x14000c0f0  pop     rbx
0x14000c0f1  retn
```
