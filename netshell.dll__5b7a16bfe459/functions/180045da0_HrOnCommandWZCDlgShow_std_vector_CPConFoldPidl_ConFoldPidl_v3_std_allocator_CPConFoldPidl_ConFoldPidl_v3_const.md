# HrOnCommandWZCDlgShow(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x180045da0`
- end: `0x180045dff`
- name: `?HrOnCommandWZCDlgShow@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180045da0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180045ddc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180045ddc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045dea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045dea`

## pseudocode

```c
__int64 __fastcall HrOnCommandWZCDlgShow(_QWORD *a1)
{
  unsigned int v2; // ebx
  HANDLE v3; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 == a1[1] )
    return 0;
  if ( *(_QWORD *)*a1 )
  {
    v2 = 0;
    ThreadId = 0;
    v3 = CreateThread(0, 0, LaunchVANThreadProc, (LPVOID)1, 0, &ThreadId);
    if ( v3 )
      CloseHandle(v3);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180045da0  push    rbx
0x180045da2  sub     rsp, 30h
0x180045da6  mov     rax, [rcx]
0x180045da9  cmp     rax, [rcx+8]
0x180045dad  jnz     short loc_180045DB3
0x180045daf  xor     eax, eax
0x180045db1  jmp     short loc_180045DF9
0x180045db3  cmp     qword ptr [rax], 0
0x180045db7  jz      short loc_180045DF2
0x180045db9  xor     ebx, ebx
0x180045dbb  lea     rax, [rsp+38h+ThreadId]
0x180045dc0  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180045dc5  lea     r8, ?LaunchVANThreadProc@@YAKPEAX@Z; lpStartAddress
0x180045dcc  xor     edx, edx; dwStackSize
0x180045dce  mov     [rsp+38h+ThreadId], ebx
0x180045dd2  xor     ecx, ecx; lpThreadAttributes
0x180045dd4  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180045dd8  lea     r9d, [rbx+1]; lpParameter
0x180045ddc  call    cs:__imp_CreateThread
0x180045de2  test    rax, rax
0x180045de5  jz      short loc_180045DF7
0x180045de7  mov     rcx, rax; hObject
0x180045dea  call    cs:__imp_CloseHandle
0x180045df0  jmp     short loc_180045DF7
0x180045df2  mov     ebx, 80070057h
0x180045df7  mov     eax, ebx
0x180045df9  add     rsp, 30h
0x180045dfd  pop     rbx
0x180045dfe  retn
```
