# ATL::CAtlExeModuleT<CcttunesvrModule>::MonitorProc(void *)

- ea: `0x140005c80`
- end: `0x140005cdc`
- name: `?MonitorProc@?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@SAKPEAX@Z`
- size: `92`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005c80`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140005cbb`
- `KERNEL32!CloseHandle` at `0x140005cbb`
- `KERNEL32!WaitForSingleObject` at `0x140005c90`
- `KERNEL32!WaitForSingleObject` at `0x140005ca1`
- `KERNEL32!WaitForSingleObject` at `0x140005c90`
- `KERNEL32!WaitForSingleObject` at `0x140005ca1`
- `USER32!PostThreadMessageW` at `0x140005cce`
- `USER32!PostThreadMessageW` at `0x140005cce`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CcttunesvrModule>::MonitorProc(LPVOID lpThreadParameter)
{
  DWORD v2; // edx
  void *v3; // rcx

  do
  {
    WaitForSingleObject(*((HANDLE *)lpThreadParameter + 10), 0xFFFFFFFF);
    do
    {
      v2 = *((_DWORD *)lpThreadParameter + 22);
      v3 = (void *)*((_QWORD *)lpThreadParameter + 10);
      *((_BYTE *)lpThreadParameter + 97) = 0;
    }
    while ( !WaitForSingleObject(v3, v2) );
  }
  while ( *((_BYTE *)lpThreadParameter + 97) || *((_DWORD *)lpThreadParameter + 3) );
  CloseHandle(*((HANDLE *)lpThreadParameter + 10));
  PostThreadMessageW(*((_DWORD *)lpThreadParameter + 18), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140005c80  push    rbx
0x140005c82  sub     rsp, 20h
0x140005c86  mov     rbx, rcx
0x140005c89  mov     rcx, [rbx+50h]; hHandle
0x140005c8d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005c90  call    cs:__imp_WaitForSingleObject
0x140005c96  mov     edx, [rbx+58h]; dwMilliseconds
0x140005c99  mov     rcx, [rbx+50h]; hHandle
0x140005c9d  mov     byte ptr [rbx+61h], 0
0x140005ca1  call    cs:__imp_WaitForSingleObject
0x140005ca7  test    eax, eax
0x140005ca9  jz      short loc_140005C96
0x140005cab  cmp     byte ptr [rbx+61h], 0
0x140005caf  jnz     short loc_140005C89
0x140005cb1  cmp     dword ptr [rbx+0Ch], 0
0x140005cb5  jnz     short loc_140005C89
0x140005cb7  mov     rcx, [rbx+50h]; hObject
0x140005cbb  call    cs:__imp_CloseHandle
0x140005cc1  mov     ecx, [rbx+48h]; idThread
0x140005cc4  xor     r9d, r9d; lParam
0x140005cc7  xor     r8d, r8d; wParam
0x140005cca  lea     edx, [r9+12h]; Msg
0x140005cce  call    cs:__imp_PostThreadMessageW
0x140005cd4  xor     eax, eax
0x140005cd6  add     rsp, 20h
0x140005cda  pop     rbx
0x140005cdb  retn
```
