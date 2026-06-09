# CuipAskUserForSwitch(HINSTANCE__ *,ushort *)

- ea: `0x14000f5b4`
- end: `0x14000f6de`
- name: `?CuipAskUserForSwitch@@YAHPEAUHINSTANCE__@@PEAG@Z`
- size: `298`
- prototype: `_BOOL8 __fastcall(HINSTANCE, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001adb0`

## callees

- `0x14000f5b4`
- `0x14000fbec`
- `0x140010ad3`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000f671`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000f671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f694`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000f61b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000f61b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f6bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f6bc`

## pseudocode

```c
_BOOL8 __fastcall CuipAskUserForSwitch(HINSTANCE a1, unsigned __int16 *a2)
{
  HANDLE v4; // rax
  void *v5; // rbx
  DWORD v6; // eax
  DWORD LastError; // eax
  _QWORD Parameter[11]; // [rsp+30h] [rbp-58h] BYREF
  DWORD ThreadId; // [rsp+90h] [rbp+8h] BYREF

  memset_0(Parameter, 0, 0x50u);
  ThreadId = 0;
  dword_140029BE0 = 0;
  Parameter[0] = a1;
  Parameter[6] = a2;
  v4 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CuipInterimDialogWindowThread, Parameter, 0, &ThreadId);
  v5 = v4;
  if ( v4 )
  {
    if ( WaitForSingleObject(v4, 0xFFFFFFFF)
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 63, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
    }
    CloseHandle(v5);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v6 = GetLastError();
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v6);
  }
  return dword_140029BE0 == 0;
}

```

## disassembly

```asm
0x14000f5b4  mov     [rsp+arg_8], rbx
0x14000f5b9  push    rdi
0x14000f5ba  sub     rsp, 80h
0x14000f5c1  mov     rdi, rdx
0x14000f5c4  mov     rbx, rcx
0x14000f5c7  xor     edx, edx; Val
0x14000f5c9  lea     rcx, [rsp+88h+Parameter]; void *
0x14000f5ce  lea     r8d, [rdx+50h]; Size
0x14000f5d2  call    memset_0
0x14000f5d7  lea     rax, [rsp+88h+ThreadId]
0x14000f5df  mov     [rsp+88h+ThreadId], 0
0x14000f5ea  mov     [rsp+88h+lpThreadId], rax; lpThreadId
0x14000f5ef  lea     r9, [rsp+88h+Parameter]; lpParameter
0x14000f5f4  lea     r8, ?CuipInterimDialogWindowThread@@YAKPEAX@Z; lpStartAddress
0x14000f5fb  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x14000f603  xor     edx, edx; dwStackSize
0x14000f605  mov     cs:dword_140029BE0, 0
0x14000f60f  xor     ecx, ecx; lpThreadAttributes
0x14000f611  mov     [rsp+88h+Parameter], rbx
0x14000f616  mov     [rsp+88h+var_28], rdi
0x14000f61b  call    cs:__imp_CreateThread
0x14000f621  mov     rbx, rax
0x14000f624  test    rax, rax
0x14000f627  jnz     short loc_14000F66B
0x14000f629  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f630  lea     rax, WPP_GLOBAL_Control
0x14000f637  cmp     rcx, rax
0x14000f63a  jz      loc_14000F6C2
0x14000f640  test    byte ptr [rcx+1Ch], 4
0x14000f644  jz      short loc_14000F6C2
0x14000f646  call    cs:__imp_GetLastError
0x14000f64c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f653  lea     edx, [rbx+3Eh]
0x14000f656  mov     r9d, eax
0x14000f659  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000f660  mov     rcx, [rcx+10h]
0x14000f664  call    WPP_SF_D
0x14000f669  jmp     short loc_14000F6C2
0x14000f66b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000f66e  mov     rcx, rbx; hHandle
0x14000f671  call    cs:__imp_WaitForSingleObject
0x14000f677  test    eax, eax
0x14000f679  jz      short loc_14000F6B9
0x14000f67b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f682  lea     rax, WPP_GLOBAL_Control
0x14000f689  cmp     rcx, rax
0x14000f68c  jz      short loc_14000F6B9
0x14000f68e  test    byte ptr [rcx+1Ch], 4
0x14000f692  jz      short loc_14000F6B9
0x14000f694  call    cs:__imp_GetLastError
0x14000f69a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f6a1  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000f6a8  mov     edx, 3Fh ; '?'
0x14000f6ad  mov     r9d, eax
0x14000f6b0  mov     rcx, [rcx+10h]
0x14000f6b4  call    WPP_SF_D
0x14000f6b9  mov     rcx, rbx; hObject
0x14000f6bc  call    cs:__imp_CloseHandle
0x14000f6c2  mov     rbx, [rsp+88h+arg_8]
0x14000f6ca  xor     eax, eax
0x14000f6cc  cmp     cs:dword_140029BE0, eax
0x14000f6d2  setz    al
0x14000f6d5  add     rsp, 80h
0x14000f6dc  pop     rdi
0x14000f6dd  retn
```
