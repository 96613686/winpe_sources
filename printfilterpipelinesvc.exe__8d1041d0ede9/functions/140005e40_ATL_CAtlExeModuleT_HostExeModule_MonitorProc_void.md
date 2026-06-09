# ATL::CAtlExeModuleT<HostExeModule>::MonitorProc(void *)

- ea: `0x140005e40`
- end: `0x140005ea8`
- name: `?MonitorProc@?$CAtlExeModuleT@VHostExeModule@@@ATL@@SAKPEAX@Z`
- size: `104`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005e40`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140005e50`
- `KERNEL32!WaitForSingleObject` at `0x140005e61`
- `KERNEL32!WaitForSingleObject` at `0x140005e50`
- `KERNEL32!WaitForSingleObject` at `0x140005e61`
- `KERNEL32!CloseHandle` at `0x140005e87`
- `KERNEL32!CloseHandle` at `0x140005e87`
- `USER32!PostThreadMessageW` at `0x140005e9a`
- `USER32!PostThreadMessageW` at `0x140005e9a`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140005e77`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x140005e77`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<HostExeModule>::MonitorProc(PVOID Parameter)
{
  DWORD v2; // edx
  void *v3; // rcx

  while ( 1 )
  {
    WaitForSingleObject(*((HANDLE *)Parameter + 10), 0xFFFFFFFF);
    do
    {
      v2 = *((_DWORD *)Parameter + 22);
      v3 = (void *)*((_QWORD *)Parameter + 10);
      *((_BYTE *)Parameter + 97) = 0;
    }
    while ( !WaitForSingleObject(v3, v2) );
    if ( !*((_BYTE *)Parameter + 97) && !*((_DWORD *)Parameter + 3) )
    {
      CoSuspendClassObjects();
      if ( !*((_DWORD *)Parameter + 3) )
        break;
    }
  }
  CloseHandle(*((HANDLE *)Parameter + 10));
  PostThreadMessageW(*((_DWORD *)Parameter + 18), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140005e40  push    rbx
0x140005e42  sub     rsp, 20h
0x140005e46  mov     rbx, rcx
0x140005e49  mov     rcx, [rbx+50h]; hHandle
0x140005e4d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005e50  call    cs:__imp_WaitForSingleObject
0x140005e56  mov     edx, [rbx+58h]; dwMilliseconds
0x140005e59  mov     rcx, [rbx+50h]; hHandle
0x140005e5d  mov     byte ptr [rbx+61h], 0
0x140005e61  call    cs:__imp_WaitForSingleObject
0x140005e67  test    eax, eax
0x140005e69  jz      short loc_140005E56
0x140005e6b  cmp     byte ptr [rbx+61h], 0
0x140005e6f  jnz     short loc_140005E49
0x140005e71  cmp     dword ptr [rbx+0Ch], 0
0x140005e75  jnz     short loc_140005E49
0x140005e77  call    cs:__imp_CoSuspendClassObjects
0x140005e7d  cmp     dword ptr [rbx+0Ch], 0
0x140005e81  jnz     short loc_140005E49
0x140005e83  mov     rcx, [rbx+50h]; hObject
0x140005e87  call    cs:__imp_CloseHandle
0x140005e8d  mov     ecx, [rbx+48h]; idThread
0x140005e90  xor     r9d, r9d; lParam
0x140005e93  xor     r8d, r8d; wParam
0x140005e96  lea     edx, [r9+12h]; Msg
0x140005e9a  call    cs:__imp_PostThreadMessageW
0x140005ea0  xor     eax, eax
0x140005ea2  add     rsp, 20h
0x140005ea6  pop     rbx
0x140005ea7  retn
```
