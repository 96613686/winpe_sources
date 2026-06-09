# BthServSetState(ulong)

- ea: `0x18000e848`
- end: `0x18000e8ea`
- name: `?BthServSetState@@YAHK@Z`
- size: `162`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f0e0`
- `0x180010c40`
- `0x180010f60`

## callees

- `0x18000e848`
- `0x180012788`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e8d7`

## pseudocode

```c
int __fastcall BthServSetState(DWORD a1)
{
  SERVICE_STATUS_HANDLE v1; // rax
  _UNKNOWN **v3; // rdx
  _UNKNOWN **v4; // r8

  v1 = hServiceStatus;
  if ( hServiceStatus )
  {
    v3 = &WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
    v4 = &WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v3,
        (_DWORD)v4,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
      v1 = hServiceStatus;
    }
    ServiceStatus.dwCurrentState = a1;
    LODWORD(v1) = SetServiceStatus(v1, &ServiceStatus);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18000e848  push    rbx
0x18000e84a  sub     rsp, 60h
0x18000e84e  mov     rax, cs:hServiceStatus
0x18000e855  mov     ebx, ecx
0x18000e857  test    rax, rax
0x18000e85a  jz      loc_18000E8E3
0x18000e860  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e867  lea     rdx, WPP_GLOBAL_Control
0x18000e86e  cmp     rcx, rdx
0x18000e871  jz      short loc_18000E87D
0x18000e873  cmp     byte ptr [rcx+19h], 5
0x18000e877  jb      short loc_18000E87D
0x18000e879  mov     dl, 1
0x18000e87b  jmp     short loc_18000E87F
0x18000e87d  xor     dl, dl
0x18000e87f  lea     r8, WPP_RECORDER_INITIALIZED
0x18000e886  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18000e88d  setnz   r8b
0x18000e891  test    dl, dl
0x18000e893  jnz     short loc_18000E89A
0x18000e895  test    r8b, r8b
0x18000e898  jz      short loc_18000E8C2
0x18000e89a  lea     r9, off_18003B4B0; "<blank>"
0x18000e8a1  mov     rax, [r9+rbx*8]
0x18000e8a5  mov     r9, [rcx+28h]
0x18000e8a9  mov     rcx, [rcx+10h]
0x18000e8ad  mov     [rsp+68h+var_18], rax
0x18000e8b2  mov     [rsp+68h+var_20], ebx
0x18000e8b6  call    WPP_RECORDER_AND_TRACE_SF_sds
0x18000e8bb  mov     rax, cs:hServiceStatus
0x18000e8c2  lea     rdx, ServiceStatus
0x18000e8c9  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18000e8cf  mov     rcx, rax
0x18000e8d2  add     rsp, 60h
0x18000e8d6  pop     rbx
0x18000e8d7  jmp     cs:__imp_SetServiceStatus
0x18000e8e3  add     rsp, 60h
0x18000e8e7  pop     rbx
0x18000e8e8  retn
```
