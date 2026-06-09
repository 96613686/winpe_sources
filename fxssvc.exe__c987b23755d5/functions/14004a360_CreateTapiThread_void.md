# CreateTapiThread(void)

- ea: `0x14004a360`
- end: `0x14004a42c`
- name: `?CreateTapiThread@@YAHXZ`
- size: `204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400472a0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14004a360`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004a3d6`
- `KERNEL32!GetLastError` at `0x14004a3d6`
- `KERNEL32!SetLastError` at `0x14004a414`
- `KERNEL32!SetLastError` at `0x14004a414`
- `KERNEL32!CreateThread` at `0x14004a3c4`
- `KERNEL32!CreateThread` at `0x14004a3c4`

## pseudocode

```c
_BOOL8 CreateTapiThread(void)
{
  DWORD v0; // ebx
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  v0 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  g_hTapiWorkerThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)TapiWorkerThread, 0, 0, &ThreadId);
  if ( !g_hTapiWorkerThread )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, LastError);
    }
    if ( v0 )
      SetLastError(v0);
  }
  return v0 == 0;
}

```

## disassembly

```asm
0x14004a360  mov     [rsp+arg_8], rbx
0x14004a365  push    rdi
0x14004a366  sub     rsp, 30h
0x14004a36a  mov     [rsp+38h+ThreadId], 0
0x14004a372  xor     ebx, ebx
0x14004a374  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a37b  lea     rdi, WPP_GLOBAL_Control
0x14004a382  cmp     rcx, rdi
0x14004a385  jz      short loc_14004A3A8
0x14004a387  test    byte ptr [rcx+1Ch], 4
0x14004a38b  jz      short loc_14004A3A8
0x14004a38d  cmp     byte ptr [rcx+19h], 5
0x14004a391  jb      short loc_14004A3A8
0x14004a393  mov     rcx, [rcx+10h]
0x14004a397  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004a39e  mov     edx, 8Fh
0x14004a3a3  call    WPP_SF_
0x14004a3a8  lea     rax, [rsp+38h+ThreadId]
0x14004a3ad  xor     r9d, r9d; lpParameter
0x14004a3b0  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14004a3b5  lea     r8, ?TapiWorkerThread@@YAKPEAX@Z; lpStartAddress
0x14004a3bc  xor     edx, edx; dwStackSize
0x14004a3be  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x14004a3c2  xor     ecx, ecx; lpThreadAttributes
0x14004a3c4  call    cs:__imp_CreateThread
0x14004a3ca  mov     cs:?g_hTapiWorkerThread@@3PEAXEA, rax; void * g_hTapiWorkerThread
0x14004a3d1  test    rax, rax
0x14004a3d4  jnz     short loc_14004A41A
0x14004a3d6  call    cs:__imp_GetLastError
0x14004a3dc  mov     ebx, eax
0x14004a3de  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3e5  cmp     rcx, rdi
0x14004a3e8  jz      short loc_14004A40E
0x14004a3ea  test    byte ptr [rcx+1Ch], 4
0x14004a3ee  jz      short loc_14004A40E
0x14004a3f0  cmp     byte ptr [rcx+19h], 2
0x14004a3f4  jb      short loc_14004A40E
0x14004a3f6  mov     rcx, [rcx+10h]
0x14004a3fa  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004a401  mov     edx, 90h
0x14004a406  mov     r9d, eax
0x14004a409  call    WPP_SF_d
0x14004a40e  test    ebx, ebx
0x14004a410  jz      short loc_14004A41A
0x14004a412  mov     ecx, ebx; dwErrCode
0x14004a414  call    cs:__imp_SetLastError
0x14004a41a  xor     eax, eax
0x14004a41c  test    ebx, ebx
0x14004a41e  mov     rbx, [rsp+38h+arg_8]
0x14004a423  setz    al
0x14004a426  add     rsp, 30h
0x14004a42a  pop     rdi
0x14004a42b  retn
```
