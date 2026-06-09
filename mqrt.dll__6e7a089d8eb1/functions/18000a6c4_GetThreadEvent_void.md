# GetThreadEvent(void * &)

- ea: `0x18000a6c4`
- end: `0x18000a83e`
- name: `?GetThreadEvent@@YAJAEAPEAX@Z`
- size: `378`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180008550`
- `0x18000a8b8`
- `0x18000dc48`
- `0x18001ba48`
- `0x18001ce18`
- `0x18001d224`

## callees

- `0x1800087f8`
- `0x18000a6c4`
- `0x18000af74`
- `0x180013c74`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000a758`
- `KERNEL32!CreateEventW` at `0x18000a758`
- `KERNEL32!GetLastError` at `0x18000a6e9`
- `KERNEL32!GetLastError` at `0x18000a766`
- `KERNEL32!GetLastError` at `0x18000a7d5`
- `KERNEL32!GetLastError` at `0x18000a6e9`
- `KERNEL32!GetLastError` at `0x18000a766`
- `KERNEL32!GetLastError` at `0x18000a7d5`
- `KERNEL32!CloseHandle` at `0x18000a80b`
- `KERNEL32!CloseHandle` at `0x18000a80b`
- `KERNEL32!TlsGetValue` at `0x18000a6d7`
- `KERNEL32!TlsGetValue` at `0x18000a6d7`
- `KERNEL32!TlsSetValue` at `0x18000a7cb`
- `KERNEL32!TlsSetValue` at `0x18000a7cb`

## pseudocode

```c
__int64 __fastcall GetThreadEvent(void **a1)
{
  void *Value; // rax
  signed int LastError; // ebx
  bool v4; // sf
  unsigned __int16 v5; // r8
  unsigned __int64 EventW; // rax
  bool v8; // sf
  DWORD v9; // ecx
  bool v10; // sf

  Value = TlsGetValue(g_dwThreadEventIndex);
  *a1 = Value;
  if ( !Value )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
      v4 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v4 = LastError < 0;
      }
      if ( !v4 )
        return (unsigned int)LastError;
      v5 = 1707;
LABEL_10:
      LogMsgHR(LastError, (wchar_t *)L"rt/message", v5);
      return (unsigned int)LastError;
    }
    EventW = (unsigned __int64)CreateEventW(0, 1, 1, 0);
    *a1 = (void *)EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_28971d9379eb322275615c28286c7903_Traceguids,
          (unsigned int)LastError);
      v8 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = LastError < 0;
      }
      if ( !v8 )
        return (unsigned int)LastError;
      v5 = 1705;
      goto LABEL_10;
    }
    v9 = g_dwThreadEventIndex;
    *a1 = (void *)(EventW | 1);
    if ( !TlsSetValue(v9, (LPVOID)(EventW | 1)) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12);
      CloseHandle(*a1);
      v10 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v10 = LastError < 0;
      }
      if ( !v10 )
        return (unsigned int)LastError;
      v5 = 1709;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a6c4  mov     [rsp+arg_0], rbx
0x18000a6c9  push    rdi
0x18000a6ca  sub     rsp, 30h
0x18000a6ce  mov     rdi, rcx
0x18000a6d1  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x18000a6d7  call    cs:__imp_TlsGetValue
0x18000a6dd  mov     [rdi], rax
0x18000a6e0  test    rax, rax
0x18000a6e3  jnz     loc_18000A831
0x18000a6e9  call    cs:__imp_GetLastError
0x18000a6ef  mov     ebx, eax
0x18000a6f1  test    eax, eax
0x18000a6f3  jz      short loc_18000A74C
0x18000a6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6fc  lea     rax, WPP_GLOBAL_Control
0x18000a703  cmp     rcx, rax
0x18000a706  jz      short loc_18000A720
0x18000a708  test    byte ptr [rcx+1Ch], 1
0x18000a70c  jz      short loc_18000A720
0x18000a70e  mov     rcx, [rcx+10h]
0x18000a712  mov     edx, 0Ah
0x18000a717  mov     [rsp+38h+var_18], ebx
0x18000a71b  call    WPP_SF_dD
0x18000a720  test    ebx, ebx
0x18000a722  jle     short loc_18000A72F
0x18000a724  movzx   ebx, bx
0x18000a727  or      ebx, 80070000h
0x18000a72d  test    ebx, ebx
0x18000a72f  jns     short loc_18000A745
0x18000a731  mov     r8d, 6ABh; unsigned __int16
0x18000a737  lea     rdx, aRtMessage; "rt/message"
0x18000a73e  mov     ecx, ebx; int
0x18000a740  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000a745  mov     eax, ebx
0x18000a747  jmp     loc_18000A833
0x18000a74c  xor     r9d, r9d; lpName
0x18000a74f  xor     ecx, ecx; lpEventAttributes
0x18000a751  lea     edx, [r9+1]; bManualReset
0x18000a755  mov     r8d, edx; bInitialState
0x18000a758  call    cs:__imp_CreateEventW
0x18000a75e  mov     [rdi], rax
0x18000a761  test    rax, rax
0x18000a764  jnz     short loc_18000A7BB
0x18000a766  call    cs:__imp_GetLastError
0x18000a76c  mov     ebx, eax
0x18000a76e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a775  lea     rax, WPP_GLOBAL_Control
0x18000a77c  cmp     rcx, rax
0x18000a77f  jz      short loc_18000A79F
0x18000a781  test    byte ptr [rcx+1Ch], 1
0x18000a785  jz      short loc_18000A79F
0x18000a787  mov     rcx, [rcx+10h]
0x18000a78b  lea     r8, WPP_28971d9379eb322275615c28286c7903_Traceguids
0x18000a792  mov     edx, 0Bh
0x18000a797  mov     r9d, ebx
0x18000a79a  call    WPP_SF_d
0x18000a79f  test    ebx, ebx
0x18000a7a1  jle     short loc_18000A7AE
0x18000a7a3  movzx   ebx, bx
0x18000a7a6  or      ebx, 80070000h
0x18000a7ac  test    ebx, ebx
0x18000a7ae  jns     short loc_18000A745
0x18000a7b0  mov     r8d, 6A9h
0x18000a7b6  jmp     loc_18000A737
0x18000a7bb  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x18000a7c1  or      rax, 1
0x18000a7c5  mov     rdx, rax; lpTlsValue
0x18000a7c8  mov     [rdi], rax
0x18000a7cb  call    cs:__imp_TlsSetValue
0x18000a7d1  test    eax, eax
0x18000a7d3  jnz     short loc_18000A831
0x18000a7d5  call    cs:__imp_GetLastError
0x18000a7db  mov     ebx, eax
0x18000a7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7e4  lea     rax, WPP_GLOBAL_Control
0x18000a7eb  cmp     rcx, rax
0x18000a7ee  jz      short loc_18000A808
0x18000a7f0  test    byte ptr [rcx+1Ch], 1
0x18000a7f4  jz      short loc_18000A808
0x18000a7f6  mov     rcx, [rcx+10h]
0x18000a7fa  mov     edx, 0Ch
0x18000a7ff  mov     [rsp+38h+var_18], ebx
0x18000a803  call    WPP_SF_dD
0x18000a808  mov     rcx, [rdi]; hObject
0x18000a80b  call    cs:__imp_CloseHandle
0x18000a811  test    ebx, ebx
0x18000a813  jle     short loc_18000A820
0x18000a815  movzx   ebx, bx
0x18000a818  or      ebx, 80070000h
0x18000a81e  test    ebx, ebx
0x18000a820  jns     loc_18000A745
0x18000a826  mov     r8d, 6ADh
0x18000a82c  jmp     loc_18000A737
0x18000a831  xor     eax, eax
0x18000a833  mov     rbx, [rsp+38h+arg_0]
0x18000a838  add     rsp, 30h
0x18000a83c  pop     rdi
0x18000a83d  retn
```
