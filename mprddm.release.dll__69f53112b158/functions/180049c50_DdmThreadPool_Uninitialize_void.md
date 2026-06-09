# DdmThreadPool::Uninitialize(void)

- ea: `0x180049c50`
- end: `0x180049d5e`
- name: `?Uninitialize@DdmThreadPool@@UEAAKXZ`
- size: `270`
- prototype: `unsigned int __fastcall(DdmThreadPool *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800205b0`
- `0x180047258`

## callees

- `0x180007c0c`
- `0x180049c50`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180049d20`
- `KERNEL32!SetEvent` at `0x180049d20`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180049cde`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180049cde`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180049cee`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180049cee`
- `KERNEL32!CloseThreadpool` at `0x180049d07`
- `KERNEL32!CloseThreadpool` at `0x180049d07`
- `KERNEL32!CloseHandle` at `0x180049d30`
- `KERNEL32!CloseHandle` at `0x180049d30`

## string_xrefs

- `0x180049c7c`: `DdmThreadPool::Uninitialize() called when helper is not initialized`

## pseudocode

```c
__int64 __fastcall DdmThreadPool::Uninitialize(DdmThreadPool *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  struct _TP_CLEANUP_GROUP *v6; // rcx
  struct _TP_POOL *v7; // rcx
  void *v8; // rcx
  _BYTE v9[16]; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-28h]
  int v11; // [rsp+48h] [rbp-20h]
  int v12; // [rsp+4Ch] [rbp-1Ch]

  if ( *((_DWORD *)this + 24) )
  {
    v6 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 2);
    if ( v6 )
    {
      CloseThreadpoolCleanupGroupMembers(v6, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 2));
      *((_QWORD *)this + 2) = 0;
    }
    v7 = (struct _TP_POOL *)*((_QWORD *)this + 1);
    if ( v7 )
    {
      CloseThreadpool(v7);
      *((_QWORD *)this + 1) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 13);
    if ( v8 )
    {
      SetEvent(v8);
      CloseHandle(*((HANDLE *)this + 13));
      *((_QWORD *)this + 13) = 0;
    }
    *((_DWORD *)this + 24) = 0;
    return 0;
  }
  else
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( aDdmthreadpoolU[v4] );
      v10 = L"DdmThreadPool::Uninitialize() called when helper is not initialized";
      v11 = 2 * v4 + 2;
      v12 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, a3, 2, v9);
    }
    return 4317;
  }
}

```

## disassembly

```asm
0x180049c50  mov     [rsp+arg_8], rbx
0x180049c55  push    rdi
0x180049c56  sub     rsp, 60h
0x180049c5a  mov     rax, cs:__security_cookie
0x180049c61  xor     rax, rsp
0x180049c64  mov     [rsp+68h+var_18], rax
0x180049c69  xor     edi, edi
0x180049c6b  mov     rbx, rcx
0x180049c6e  cmp     [rcx+60h], edi
0x180049c71  jnz     short loc_180049CCE
0x180049c73  test    cs:byte_1800CF404, 10h
0x180049c7a  jz      short loc_180049CC7
0x180049c7c  lea     rcx, aDdmthreadpoolU; "DdmThreadPool::Uninitialize() called wh"...
0x180049c83  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049c87  inc     rax
0x180049c8a  cmp     [rcx+rax*2], di
0x180049c8e  jnz     short loc_180049C87
0x180049c90  lea     eax, ds:2[rax*2]
0x180049c97  mov     [rsp+68h+var_28], rcx
0x180049c9c  mov     [rsp+68h+var_20], eax
0x180049ca0  lea     rdx, RasDdmTraceInfo
0x180049ca7  lea     rax, [rsp+68h+var_38]
0x180049cac  mov     [rsp+68h+var_1C], edi
0x180049cb0  mov     r9d, 2
0x180049cb6  mov     [rsp+68h+var_48], rax
0x180049cbb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180049cc2  call    McGenEventWrite_EventWriteTransfer
0x180049cc7  mov     eax, 10DDh
0x180049ccc  jmp     short loc_180049D45
0x180049cce  mov     rcx, [rcx+10h]; ptpcg
0x180049cd2  test    rcx, rcx
0x180049cd5  jz      short loc_180049CFE
0x180049cd7  xor     r8d, r8d; pvCleanupContext
0x180049cda  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180049cde  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180049ce5  nop     dword ptr [rax+rax+00h]
0x180049cea  mov     rcx, [rbx+10h]; ptpcg
0x180049cee  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180049cf5  nop     dword ptr [rax+rax+00h]
0x180049cfa  mov     [rbx+10h], rdi
0x180049cfe  mov     rcx, [rbx+8]; ptpp
0x180049d02  test    rcx, rcx
0x180049d05  jz      short loc_180049D17
0x180049d07  call    cs:__imp_CloseThreadpool
0x180049d0e  nop     dword ptr [rax+rax+00h]
0x180049d13  mov     [rbx+8], rdi
0x180049d17  mov     rcx, [rbx+68h]; hEvent
0x180049d1b  test    rcx, rcx
0x180049d1e  jz      short loc_180049D40
0x180049d20  call    cs:__imp_SetEvent
0x180049d27  nop     dword ptr [rax+rax+00h]
0x180049d2c  mov     rcx, [rbx+68h]; hObject
0x180049d30  call    cs:__imp_CloseHandle
0x180049d37  nop     dword ptr [rax+rax+00h]
0x180049d3c  mov     [rbx+68h], rdi
0x180049d40  mov     [rbx+60h], edi
0x180049d43  xor     eax, eax
0x180049d45  mov     rcx, [rsp+68h+var_18]
0x180049d4a  xor     rcx, rsp; StackCookie
0x180049d4d  call    __security_check_cookie
0x180049d52  mov     rbx, [rsp+68h+arg_8]
0x180049d57  add     rsp, 60h
0x180049d5b  pop     rdi
0x180049d5c  retn
```
