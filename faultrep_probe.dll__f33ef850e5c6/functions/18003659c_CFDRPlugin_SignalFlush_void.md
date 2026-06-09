# CFDRPlugin::SignalFlush(void)

- ea: `0x18003659c`
- end: `0x180036743`
- name: `?SignalFlush@CFDRPlugin@@AEAAJXZ`
- size: `423`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180035c50`

## callees

- `0x1800028b4`
- `0x180006684`
- `0x180009ed8`
- `0x180024bc4`
- `0x18003659c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180036668`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180036668`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800366b2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800366b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800366e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800366e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036730`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::SignalFlush(CFDRPlugin *this)
{
  char *v2; // rbx
  const struct std::nothrow_t *v3; // rdx
  int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  LPCWSTR lpName; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  utl::make_unique_for_overwrite<wchar_t [0],0>(&lpName, 260);
  if ( !lpName )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    v4 = -2147024882;
    goto LABEL_25;
  }
  v4 = StringCchPrintfW((wchar_t *)lpName, 0x104u, L"%s-%d", L"FDR_FLUSH_MESSAGE", *((_DWORD *)this + 12));
  if ( v4 >= 0 )
  {
    v2 = (char *)OpenEventW(0x100002u, 0, lpName);
    if ( v2 == (char *)-1LL || v2 + 1 == (char *)1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v6 = 70;
    }
    else if ( SetEvent(v2) )
    {
      if ( WaitForSingleObject(v2, 0x1388u) != -1 )
      {
        v4 = 0;
        goto LABEL_25;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_15:
        v4 = -2147467259;
        goto LABEL_25;
      }
      v6 = 72;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v6 = 71;
    }
    WPP_SF_(v5[2], v6, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
LABEL_25:
  if ( lpName )
    operator delete((void *)lpName, v3);
  if ( (unsigned __int64)(v2 + 1) > 1 )
    CloseHandle(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003659c  mov     [rsp+arg_0], rbx
0x1800365a1  push    rdi
0x1800365a2  sub     rsp, 30h
0x1800365a6  mov     rdi, rcx
0x1800365a9  mov     edx, 104h
0x1800365ae  lea     rcx, [rsp+38h+lpName]
0x1800365b3  xor     ebx, ebx
0x1800365b5  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800365ba  cmp     [rsp+38h+lpName], rbx
0x1800365bf  jnz     short loc_1800365F7
0x1800365c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365c8  lea     rax, WPP_GLOBAL_Control
0x1800365cf  cmp     rcx, rax
0x1800365d2  jz      short loc_1800365ED
0x1800365d4  test    byte ptr [rcx+1Ch], 1
0x1800365d8  jz      short loc_1800365ED
0x1800365da  mov     rcx, [rcx+10h]
0x1800365de  lea     edx, [rbx+44h]
0x1800365e1  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1800365e8  call    WPP_SF_
0x1800365ed  mov     edi, 8007000Eh
0x1800365f2  jmp     loc_180036711
0x1800365f7  mov     eax, [rdi+30h]
0x1800365fa  lea     r9, aFdrFlushMessag; "FDR_FLUSH_MESSAGE"
0x180036601  mov     rcx, [rsp+38h+lpName]; wchar_t *
0x180036606  lea     r8, aSD; "%s-%d"
0x18003660d  mov     edx, 104h; unsigned __int64
0x180036612  mov     [rsp+38h+var_18], eax
0x180036616  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18003661b  mov     edi, eax
0x18003661d  test    eax, eax
0x18003661f  jns     short loc_18003665C
0x180036621  mov     rcx, cs:WPP_GLOBAL_Control
0x180036628  lea     rax, WPP_GLOBAL_Control
0x18003662f  cmp     rcx, rax
0x180036632  jz      loc_180036711
0x180036638  test    byte ptr [rcx+1Ch], 1
0x18003663c  jz      loc_180036711
0x180036642  mov     rcx, [rcx+10h]
0x180036646  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x18003664d  mov     edx, 45h ; 'E'
0x180036652  call    WPP_SF_
0x180036657  jmp     loc_180036711
0x18003665c  mov     r8, [rsp+38h+lpName]; lpName
0x180036661  xor     edx, edx; bInheritHandle
0x180036663  mov     ecx, 100002h; dwDesiredAccess
0x180036668  call    cs:__imp_OpenEventW
0x18003666e  mov     rbx, rax
0x180036671  inc     rax
0x180036674  cmp     rax, 1
0x180036678  ja      short loc_1800366AF
0x18003667a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036681  lea     rax, WPP_GLOBAL_Control
0x180036688  cmp     rcx, rax
0x18003668b  jz      short loc_1800366A8
0x18003668d  test    byte ptr [rcx+1Ch], 1
0x180036691  jz      short loc_1800366A8
0x180036693  mov     edx, 46h ; 'F'
0x180036698  mov     rcx, [rcx+10h]
0x18003669c  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1800366a3  call    WPP_SF_
0x1800366a8  mov     edi, 80004005h
0x1800366ad  jmp     short loc_180036711
0x1800366af  mov     rcx, rbx; hEvent
0x1800366b2  call    cs:__imp_SetEvent
0x1800366b8  test    eax, eax
0x1800366ba  jnz     short loc_1800366DC
0x1800366bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366c3  lea     rax, WPP_GLOBAL_Control
0x1800366ca  cmp     rcx, rax
0x1800366cd  jz      short loc_1800366A8
0x1800366cf  test    byte ptr [rcx+1Ch], 1
0x1800366d3  jz      short loc_1800366A8
0x1800366d5  mov     edx, 47h ; 'G'
0x1800366da  jmp     short loc_180036698
0x1800366dc  mov     edx, 1388h; dwMilliseconds
0x1800366e1  mov     rcx, rbx; hHandle
0x1800366e4  call    cs:__imp_WaitForSingleObject
0x1800366ea  cmp     eax, 0FFFFFFFFh
0x1800366ed  jnz     short loc_18003670F
0x1800366ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366f6  lea     rax, WPP_GLOBAL_Control
0x1800366fd  cmp     rcx, rax
0x180036700  jz      short loc_1800366A8
0x180036702  test    byte ptr [rcx+1Ch], 1
0x180036706  jz      short loc_1800366A8
0x180036708  mov     edx, 48h ; 'H'
0x18003670d  jmp     short loc_180036698
0x18003670f  xor     edi, edi
0x180036711  cmp     [rsp+38h+lpName], 0
0x180036717  jz      short loc_180036723
0x180036719  mov     rcx, [rsp+38h+lpName]; void *
0x18003671e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036723  lea     rax, [rbx+1]
0x180036727  cmp     rax, 1
0x18003672b  jbe     short loc_180036736
0x18003672d  mov     rcx, rbx; hObject
0x180036730  call    cs:__imp_CloseHandle
0x180036736  mov     rbx, [rsp+38h+arg_0]
0x18003673b  mov     eax, edi
0x18003673d  add     rsp, 30h
0x180036741  pop     rdi
0x180036742  retn
```
