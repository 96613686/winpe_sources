# SvcpSetServiceStatus(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)

- ea: `0x14001c700`
- end: `0x14001c76d`
- name: `?SvcpSetServiceStatus@@YAXPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z`
- size: `109`
- prototype: `void __fastcall(SERVICE_STATUS_HANDLE, struct _SERVICE_STATUS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140001cc6`
- `0x140007554`
- `0x140008034`
- `0x14001c700`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x14001c706`
- `ADVAPI32!SetServiceStatus` at `0x14001c706`
- `KERNEL32!GetLastError` at `0x14001c710`
- `KERNEL32!GetLastError` at `0x14001c710`

## pseudocode

```c
void __fastcall SvcpSetServiceStatus(SERVICE_STATUS_HANDLE a1, struct _SERVICE_STATUS *a2)
{
  DWORD LastError; // ebx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( !SetServiceStatus(a1, a2) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9df9884075d73472bc34f24e96197e6d_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, LastError);
    throw (bad_win32_error *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x14001c700  push    rbx
0x14001c702  sub     rsp, 40h
0x14001c706  call    cs:__imp_SetServiceStatus
0x14001c70c  test    eax, eax
0x14001c70e  jnz     short loc_14001C767
0x14001c710  call    cs:__imp_GetLastError
0x14001c716  mov     ebx, eax
0x14001c718  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c71f  lea     rax, WPP_GLOBAL_Control
0x14001c726  cmp     rcx, rax
0x14001c729  jz      short loc_14001C749
0x14001c72b  test    byte ptr [rcx+1Ch], 1
0x14001c72f  jz      short loc_14001C749
0x14001c731  mov     rcx, [rcx+10h]
0x14001c735  lea     r8, WPP_9df9884075d73472bc34f24e96197e6d_Traceguids
0x14001c73c  mov     edx, 0Ch
0x14001c741  mov     r9d, ebx
0x14001c744  call    WPP_SF_d
0x14001c749  mov     edx, ebx; unsigned int
0x14001c74b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14001c750  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14001c755  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x14001c75c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001c761  call    _CxxThrowException_0
0x14001c767  add     rsp, 40h
0x14001c76b  pop     rbx
0x14001c76c  retn
```
