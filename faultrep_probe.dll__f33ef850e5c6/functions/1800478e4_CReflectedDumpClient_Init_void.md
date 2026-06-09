# CReflectedDumpClient::Init(void)

- ea: `0x1800478e4`
- end: `0x180047985`
- name: `?Init@CReflectedDumpClient@@QEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(CReflectedDumpClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004752c`

## callees

- `0x180009f00`
- `0x180046eb8`
- `0x1800478e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047929`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800478fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800478fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047916`

## pseudocode

```c
__int64 __fastcall CReflectedDumpClient::Init(CReflectedDumpClient *this)
{
  HANDLE EventW; // rax
  void *v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ebx

  CReflectedDumpClient::Cleanup(this);
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = EventW;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  if ( *((_QWORD *)this + 1) == -1 || *((_QWORD *)this + 1) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
      v5 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v5);
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800478e4  push    rbx
0x1800478e6  sub     rsp, 20h
0x1800478ea  mov     rbx, rcx
0x1800478ed  call    ?Cleanup@CReflectedDumpClient@@QEAAXXZ; CReflectedDumpClient::Cleanup(void)
0x1800478f2  xor     r9d, r9d; lpName
0x1800478f5  xor     r8d, r8d; bInitialState
0x1800478f8  xor     ecx, ecx; lpEventAttributes
0x1800478fa  lea     edx, [r9+1]; bManualReset
0x1800478fe  call    cs:__imp_CreateEventW
0x180047904  mov     rcx, [rbx+8]; hObject
0x180047908  mov     [rbx+8], rax
0x18004790c  lea     rax, [rcx+1]
0x180047910  cmp     rax, 1
0x180047914  jbe     short loc_18004791C
0x180047916  call    cs:__imp_CloseHandle
0x18004791c  mov     rax, [rbx+8]
0x180047920  inc     rax
0x180047923  cmp     rax, 1
0x180047927  ja      short loc_18004797B
0x180047929  call    cs:__imp_GetLastError
0x18004792f  mov     ebx, eax
0x180047931  test    eax, eax
0x180047933  jle     short loc_18004793E
0x180047935  movzx   ebx, ax
0x180047938  or      ebx, 80070000h
0x18004793e  test    ebx, ebx
0x180047940  mov     eax, 80004005h
0x180047945  cmovns  ebx, eax
0x180047948  mov     rcx, cs:WPP_GLOBAL_Control
0x18004794f  lea     rax, WPP_GLOBAL_Control
0x180047956  cmp     rcx, rax
0x180047959  jz      short loc_18004797D
0x18004795b  test    byte ptr [rcx+1Ch], 1
0x18004795f  jz      short loc_18004797D
0x180047961  mov     rcx, [rcx+10h]
0x180047965  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x18004796c  mov     edx, 4Fh ; 'O'
0x180047971  mov     r9d, ebx
0x180047974  call    WPP_SF_d
0x180047979  jmp     short loc_18004797D
0x18004797b  xor     ebx, ebx
0x18004797d  mov     eax, ebx
0x18004797f  add     rsp, 20h
0x180047983  pop     rbx
0x180047984  retn
```
