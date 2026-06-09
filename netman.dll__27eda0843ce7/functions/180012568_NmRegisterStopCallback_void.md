# NmRegisterStopCallback(void)

- ea: `0x180012568`
- end: `0x180012684`
- name: `?NmRegisterStopCallback@@YAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180016688`

## callees

- `0x18000538c`
- `0x180012568`
- `0x180036010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012596`
- `KERNEL32!GetLastError` at `0x180012596`
- `KERNEL32!CreateEventW` at `0x180012581`
- `KERNEL32!CreateEventW` at `0x180012581`
- `KERNEL32!CloseHandle` at `0x18001266b`
- `KERNEL32!CloseHandle` at `0x18001266b`

## pseudocode

```c
__int64 NmRegisterStopCallback(void)
{
  HANDLE v0; // r8
  signed int LastError; // eax
  unsigned int v2; // ebx
  int v3; // eax

  v0 = hObject;
  if ( hObject || (hObject = CreateEventW(0, 0, 0, 0), (v0 = hObject) != 0) )
  {
    v2 = 0;
    v3 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(qword_180045050 + 192))(
           &WaitHandle,
           L"netman",
           v0,
           NmStopService,
           0,
           24);
    if ( v3 )
    {
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
      else
        v2 = v3;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, v2);
      CloseHandle(hObject);
      hObject = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180012568  push    rbx
0x18001256a  sub     rsp, 40h
0x18001256e  mov     r8, cs:hObject; bInitialState
0x180012575  test    r8, r8
0x180012578  jnz     short loc_1800125E9
0x18001257a  xor     r9d, r9d; lpName
0x18001257d  xor     edx, edx; bManualReset
0x18001257f  xor     ecx, ecx; lpEventAttributes
0x180012581  call    cs:__imp_CreateEventW
0x180012587  mov     cs:hObject, rax
0x18001258e  mov     r8, rax
0x180012591  test    rax, rax
0x180012594  jnz     short loc_1800125E9
0x180012596  call    cs:__imp_GetLastError
0x18001259c  mov     ebx, eax
0x18001259e  test    eax, eax
0x1800125a0  jle     short loc_1800125AB
0x1800125a2  movzx   ebx, ax
0x1800125a5  or      ebx, 80070000h
0x1800125ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125b2  lea     rax, WPP_GLOBAL_Control
0x1800125b9  cmp     rcx, rax
0x1800125bc  jz      loc_18001267C
0x1800125c2  test    byte ptr [rcx+1Ch], 8
0x1800125c6  jz      loc_18001267C
0x1800125cc  mov     rcx, [rcx+10h]
0x1800125d0  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x1800125d7  mov     edx, 16h
0x1800125dc  mov     r9d, ebx
0x1800125df  call    WPP_SF_d
0x1800125e4  jmp     loc_18001267C
0x1800125e9  mov     rax, cs:qword_180045050
0x1800125f0  lea     r9, ?NmStopService@@YAXPEAXE@Z; NmStopService(void *,uchar)
0x1800125f7  xor     ebx, ebx
0x1800125f9  mov     [rsp+48h+var_20], 18h
0x180012601  lea     rdx, ServiceName; "netman"
0x180012608  mov     [rsp+48h+var_28], rbx
0x18001260d  lea     rcx, WaitHandle
0x180012614  mov     rax, [rax+0C0h]
0x18001261b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012620  test    eax, eax
0x180012622  jz      short loc_18001267C
0x180012624  jg      short loc_18001262A
0x180012626  mov     ebx, eax
0x180012628  jmp     short loc_180012633
0x18001262a  movzx   ebx, ax
0x18001262d  or      ebx, 80070000h
0x180012633  mov     rcx, cs:WPP_GLOBAL_Control
0x18001263a  lea     rax, WPP_GLOBAL_Control
0x180012641  cmp     rcx, rax
0x180012644  jz      short loc_180012664
0x180012646  test    byte ptr [rcx+1Ch], 8
0x18001264a  jz      short loc_180012664
0x18001264c  mov     rcx, [rcx+10h]
0x180012650  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x180012657  mov     edx, 17h
0x18001265c  mov     r9d, ebx
0x18001265f  call    WPP_SF_d
0x180012664  mov     rcx, cs:hObject; hObject
0x18001266b  call    cs:__imp_CloseHandle
0x180012671  mov     cs:hObject, 0
0x18001267c  mov     eax, ebx
0x18001267e  add     rsp, 40h
0x180012682  pop     rbx
0x180012683  retn
```
