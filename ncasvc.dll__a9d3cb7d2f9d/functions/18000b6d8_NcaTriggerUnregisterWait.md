# NcaTriggerUnregisterWait

- ea: `0x18000b6d8`
- end: `0x18000b7d7`
- name: `NcaTriggerUnregisterWait`
- size: `255`
- prototype: `__int64 __fastcall(PTP_WAIT *lpMem)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b3a8`
- `0x18000b51c`
- `0x18000b9f8`
- `0x18000f7c8`
- `0x180011bc0`
- `0x180015e80`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x18000b6d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b782`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000b75b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000b75b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000b76a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000b76a`

## pseudocode

```c
__int64 __fastcall NcaTriggerUnregisterWait(PTP_WAIT *lpMem)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi
  PTP_WAIT v4; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    v3 = 0;
    if ( *lpMem )
    {
      WaitForThreadpoolWaitCallbacks(*lpMem, 1);
      CloseThreadpoolWait(*lpMem);
      *lpMem = 0;
    }
    v4 = lpMem[1];
    if ( v4 )
    {
      CloseHandle(v4);
      lpMem[1] = 0;
    }
    NcaFree(lpMem);
    goto LABEL_13;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    WPP_SF_d(v2[2], 17, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 87);
LABEL_13:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(v2[2], 18, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18000b6d8  mov     [rsp+arg_0], rbx
0x18000b6dd  mov     [rsp+arg_8], rsi
0x18000b6e2  push    rdi
0x18000b6e3  sub     rsp, 20h
0x18000b6e7  mov     rbx, rcx
0x18000b6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6f1  lea     rsi, WPP_GLOBAL_Control
0x18000b6f8  cmp     rcx, rsi
0x18000b6fb  jz      short loc_18000B71F
0x18000b6fd  test    byte ptr [rcx+1Ch], 8
0x18000b701  jz      short loc_18000B71F
0x18000b703  mov     rcx, [rcx+10h]
0x18000b707  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b70e  mov     edx, 10h
0x18000b713  call    WPP_SF_
0x18000b718  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b71f  test    rbx, rbx
0x18000b722  jnz     short loc_18000B74E
0x18000b724  lea     edi, [rbx+57h]
0x18000b727  cmp     rcx, rsi
0x18000b72a  jz      loc_18000B7C4
0x18000b730  test    byte ptr [rcx+1Ch], 1
0x18000b734  jz      short loc_18000B7A1
0x18000b736  mov     rcx, [rcx+10h]
0x18000b73a  lea     edx, [rbx+11h]
0x18000b73d  mov     r9d, edi
0x18000b740  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b747  call    WPP_SF_d
0x18000b74c  jmp     short loc_18000B79A
0x18000b74e  mov     rcx, [rbx]; pwa
0x18000b751  xor     edi, edi
0x18000b753  test    rcx, rcx
0x18000b756  jz      short loc_18000B779
0x18000b758  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18000b75b  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000b762  nop     dword ptr [rax+rax+00h]
0x18000b767  mov     rcx, [rbx]; pwa
0x18000b76a  call    cs:__imp_CloseThreadpoolWait
0x18000b771  nop     dword ptr [rax+rax+00h]
0x18000b776  mov     [rbx], rdi
0x18000b779  mov     rcx, [rbx+8]; hObject
0x18000b77d  test    rcx, rcx
0x18000b780  jz      short loc_18000B792
0x18000b782  call    cs:__imp_CloseHandle
0x18000b789  nop     dword ptr [rax+rax+00h]
0x18000b78e  mov     [rbx+8], rdi
0x18000b792  mov     rcx, rbx; lpMem
0x18000b795  call    NcaFree
0x18000b79a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7a1  cmp     rcx, rsi
0x18000b7a4  jz      short loc_18000B7C4
0x18000b7a6  test    byte ptr [rcx+1Ch], 8
0x18000b7aa  jz      short loc_18000B7C4
0x18000b7ac  mov     rcx, [rcx+10h]
0x18000b7b0  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b7b7  mov     edx, 12h
0x18000b7bc  mov     r9d, edi
0x18000b7bf  call    WPP_SF_d
0x18000b7c4  mov     rbx, [rsp+28h+arg_0]
0x18000b7c9  mov     eax, edi
0x18000b7cb  mov     rsi, [rsp+28h+arg_8]
0x18000b7d0  add     rsp, 20h
0x18000b7d4  pop     rdi
0x18000b7d5  retn
```
