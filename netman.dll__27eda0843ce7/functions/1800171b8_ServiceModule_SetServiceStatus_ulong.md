# ServiceModule::SetServiceStatus(ulong)

- ea: `0x1800171b8`
- end: `0x180017246`
- name: `?SetServiceStatus@ServiceModule@@QEAAXK@Z`
- size: `142`
- prototype: `void __fastcall(ServiceModule *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f21c`
- `0x180016688`
- `0x1800169b4`
- `0x180016a9c`
- `0x180016e1c`

## callees

- `0x18000538c`
- `0x1800171b8`
- `0x18003060c`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x1800171fa`
- `ADVAPI32!SetServiceStatus` at `0x1800171fa`

## pseudocode

```c
void __fastcall ServiceModule::SetServiceStatus(ServiceModule *this, DWORD a2)
{
  unsigned int Win32Error; // eax

  ServiceStatus.dwCurrentState = a2;
  if ( a2 == 2 )
  {
    ServiceStatus.dwControlsAccepted = 0;
  }
  else if ( a2 == 4 )
  {
    ServiceStatus.dwControlsAccepted |= 0x81u;
  }
  ServiceStatus.dwCheckPoint = 0;
  if ( !SetServiceStatus(hRecipient, &ServiceStatus)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    Win32Error = HrFromLastWin32Error();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, Win32Error);
  }
}

```

## disassembly

```asm
0x1800171b8  sub     rsp, 28h
0x1800171bc  mov     cs:ServiceStatus.dwCurrentState, edx
0x1800171c2  cmp     edx, 2
0x1800171c5  jz      short loc_1800171D8
0x1800171c7  cmp     edx, 4
0x1800171ca  jnz     short loc_1800171E2
0x1800171cc  or      cs:ServiceStatus.dwControlsAccepted, 81h
0x1800171d6  jmp     short loc_1800171E2
0x1800171d8  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x1800171e2  mov     rcx, cs:hRecipient; hServiceStatus
0x1800171e9  lea     rdx, ServiceStatus; lpServiceStatus
0x1800171f0  mov     cs:ServiceStatus.dwCheckPoint, 0
0x1800171fa  call    cs:__imp_SetServiceStatus
0x180017200  test    eax, eax
0x180017202  jnz     short loc_180017241
0x180017204  mov     rax, cs:WPP_GLOBAL_Control
0x18001720b  lea     rcx, WPP_GLOBAL_Control
0x180017212  cmp     rax, rcx
0x180017215  jz      short loc_180017241
0x180017217  test    byte ptr [rax+1Ch], 8
0x18001721b  jz      short loc_180017241
0x18001721d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180017222  mov     rcx, cs:WPP_GLOBAL_Control
0x180017229  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x180017230  mov     edx, 13h
0x180017235  mov     r9d, eax
0x180017238  mov     rcx, [rcx+10h]
0x18001723c  call    WPP_SF_d
0x180017241  add     rsp, 28h
0x180017245  retn
```
