# DdmThreadPool::Uninitialize(void)

- ea: `0x1800489b0`
- end: `0x180048a90`
- name: `?Uninitialize@DdmThreadPool@@UEAAKXZ`
- size: `224`
- prototype: `unsigned int __fastcall(DdmThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f8e0`
- `0x180046184`

## callees

- `0x180007b7c`
- `0x1800489b0`
- `0x18008c630`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180048a5c`
- `KERNEL32!SetEvent` at `0x180048a5c`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180048a24`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180048a24`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180048a2e`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180048a2e`
- `KERNEL32!CloseThreadpool` at `0x180048a45`
- `KERNEL32!CloseThreadpool` at `0x180048a45`
- `KERNEL32!CloseHandle` at `0x180048a66`
- `KERNEL32!CloseHandle` at `0x180048a66`

## string_xrefs

- `0x1800489d9`: `DdmThreadPool::Uninitialize() called when helper is not initialized`

## pseudocode

```c
__int64 __fastcall DdmThreadPool::Uninitialize(DdmThreadPool *this, __int64 a2, __int64 a3)
{
  struct _TP_CLEANUP_GROUP *v5; // rcx
  struct _TP_POOL *v6; // rcx
  void *v7; // rcx
  _QWORD v8[4]; // [rsp+38h] [rbp-30h] BYREF

  if ( *((_DWORD *)this + 24) )
  {
    v5 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 2);
    if ( v5 )
    {
      CloseThreadpoolCleanupGroupMembers(v5, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 2));
      *((_QWORD *)this + 2) = 0;
    }
    v6 = (struct _TP_POOL *)*((_QWORD *)this + 1);
    if ( v6 )
    {
      CloseThreadpool(v6);
      *((_QWORD *)this + 1) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 13);
    if ( v7 )
    {
      SetEvent(v7);
      CloseHandle(*((HANDLE *)this + 13));
      *((_QWORD *)this + 13) = 0;
    }
    *((_DWORD *)this + 24) = 0;
    return 0;
  }
  else
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v8[3] = 136;
      v8[2] = L"DdmThreadPool::Uninitialize() called when helper is not initialized";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, a3, 2, v8);
    }
    return 4317;
  }
}

```

## disassembly

```asm
0x1800489b0  mov     r11, rsp
0x1800489b3  push    rbx
0x1800489b4  sub     rsp, 60h
0x1800489b8  mov     rax, cs:__security_cookie
0x1800489bf  xor     rax, rsp
0x1800489c2  mov     [rsp+68h+var_10], rax
0x1800489c7  cmp     dword ptr [rcx+60h], 0
0x1800489cb  mov     rbx, rcx
0x1800489ce  jnz     short loc_180048A14
0x1800489d0  test    cs:byte_1800C8404, 10h
0x1800489d7  jz      short loc_180048A0D
0x1800489d9  lea     rax, aDdmthreadpoolU; "DdmThreadPool::Uninitialize() called wh"...
0x1800489e0  mov     qword ptr [r11-18h], 88h
0x1800489e8  mov     [r11-20h], rax
0x1800489ec  lea     rdx, RasDdmTraceInfo
0x1800489f3  lea     rax, [r11-30h]
0x1800489f7  mov     r9d, 2
0x1800489fd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048a04  mov     [r11-48h], rax
0x180048a08  call    McGenEventWrite_EventWriteTransfer
0x180048a0d  mov     eax, 10DDh
0x180048a12  jmp     short loc_180048A7D
0x180048a14  mov     rcx, [rcx+10h]; ptpcg
0x180048a18  test    rcx, rcx
0x180048a1b  jz      short loc_180048A3C
0x180048a1d  xor     r8d, r8d; pvCleanupContext
0x180048a20  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180048a24  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180048a2a  mov     rcx, [rbx+10h]; ptpcg
0x180048a2e  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180048a34  mov     qword ptr [rbx+10h], 0
0x180048a3c  mov     rcx, [rbx+8]; ptpp
0x180048a40  test    rcx, rcx
0x180048a43  jz      short loc_180048A53
0x180048a45  call    cs:__imp_CloseThreadpool
0x180048a4b  mov     qword ptr [rbx+8], 0
0x180048a53  mov     rcx, [rbx+68h]; hEvent
0x180048a57  test    rcx, rcx
0x180048a5a  jz      short loc_180048A74
0x180048a5c  call    cs:__imp_SetEvent
0x180048a62  mov     rcx, [rbx+68h]; hObject
0x180048a66  call    cs:__imp_CloseHandle
0x180048a6c  mov     qword ptr [rbx+68h], 0
0x180048a74  mov     dword ptr [rbx+60h], 0
0x180048a7b  xor     eax, eax
0x180048a7d  mov     rcx, [rsp+68h+var_10]
0x180048a82  xor     rcx, rsp; StackCookie
0x180048a85  call    __security_check_cookie
0x180048a8a  add     rsp, 60h
0x180048a8e  pop     rbx
0x180048a8f  retn
```
