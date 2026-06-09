# NcaNlmTriggerConnectionPointInitialize(void)

- ea: `0x18000bca4`
- end: `0x18000be1a`
- name: `?NcaNlmTriggerConnectionPointInitialize@@YAJXZ`
- size: `374`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ce40`

## callees

- `0x180004f34`
- `0x18000bca4`
- `0x18000bfe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bd12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bd12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bda6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bda6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000bcb8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000bcb8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bdfc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bdfc`

## pseudocode

```c
__int64 NcaNlmTriggerConnectionPointInitialize(void)
{
  int v0; // ebx
  signed int v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  HANDLE Thread; // rax
  signed int LastError; // eax

  dword_180028CE8 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids,
        (unsigned int)v0);
    goto LABEL_20;
  }
  qword_180028CD8 = CreateEventW(0, 0, 0, 0);
  if ( qword_180028CD8 )
  {
    Thread = CreateThread(0, 0, NcaNlmTriggerNotifySinkProc, gNcaNlmTriggerComp, 0, &ThreadId);
    if ( Thread )
    {
      qword_180028CC8 = Thread;
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 19;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v1 = GetLastError();
    v0 = v1;
    if ( v1 > 0 )
      v0 = (unsigned __int16)v1 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 18;
LABEL_11:
      WPP_SF_d(v2[2], v3, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids, (unsigned int)v0);
    }
  }
  CoUninitialize();
  if ( v0 < 0 )
LABEL_20:
    NcaNlmTriggerConnectionPointShutdown();
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000bca4  push    rbx
0x18000bca6  sub     rsp, 30h
0x18000bcaa  xor     edx, edx; dwCoInit
0x18000bcac  mov     cs:dword_180028CE8, 0
0x18000bcb6  xor     ecx, ecx; pvReserved
0x18000bcb8  call    cs:__imp_CoInitializeEx
0x18000bcbf  nop     dword ptr [rax+rax+00h]
0x18000bcc4  mov     ebx, eax
0x18000bcc6  test    eax, eax
0x18000bcc8  jns     short loc_18000BD08
0x18000bcca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcd1  lea     rax, WPP_GLOBAL_Control
0x18000bcd8  cmp     rcx, rax
0x18000bcdb  jz      loc_18000BE0C
0x18000bce1  test    byte ptr [rcx+1Ch], 1
0x18000bce5  jz      loc_18000BE0C
0x18000bceb  mov     rcx, [rcx+10h]
0x18000bcef  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000bcf6  mov     edx, 11h
0x18000bcfb  mov     r9d, ebx
0x18000bcfe  call    WPP_SF_d
0x18000bd03  jmp     loc_18000BE0C
0x18000bd08  xor     r9d, r9d; lpName
0x18000bd0b  xor     r8d, r8d; bInitialState
0x18000bd0e  xor     edx, edx; bManualReset
0x18000bd10  xor     ecx, ecx; lpEventAttributes
0x18000bd12  call    cs:__imp_CreateEventW
0x18000bd19  nop     dword ptr [rax+rax+00h]
0x18000bd1e  mov     cs:qword_180028CD8, rax
0x18000bd25  test    rax, rax
0x18000bd28  jnz     short loc_18000BD80
0x18000bd2a  call    cs:__imp_GetLastError
0x18000bd31  nop     dword ptr [rax+rax+00h]
0x18000bd36  mov     ebx, eax
0x18000bd38  test    eax, eax
0x18000bd3a  jle     short loc_18000BD45
0x18000bd3c  movzx   ebx, ax
0x18000bd3f  or      ebx, 80070000h
0x18000bd45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd4c  lea     rax, WPP_GLOBAL_Control
0x18000bd53  cmp     rcx, rax
0x18000bd56  jz      loc_18000BDFC
0x18000bd5c  test    byte ptr [rcx+1Ch], 1
0x18000bd60  jz      loc_18000BDFC
0x18000bd66  mov     edx, 12h
0x18000bd6b  mov     rcx, [rcx+10h]
0x18000bd6f  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000bd76  mov     r9d, ebx
0x18000bd79  call    WPP_SF_d
0x18000bd7e  jmp     short loc_18000BDFC
0x18000bd80  mov     r9, cs:?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A; lpParameter
0x18000bd87  lea     rax, ThreadId
0x18000bd8e  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000bd93  lea     r8, ?NcaNlmTriggerNotifySinkProc@@YAKPEAX@Z; lpStartAddress
0x18000bd9a  xor     edx, edx; dwStackSize
0x18000bd9c  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000bda4  xor     ecx, ecx; lpThreadAttributes
0x18000bda6  call    cs:__imp_CreateThread
0x18000bdad  nop     dword ptr [rax+rax+00h]
0x18000bdb2  test    rax, rax
0x18000bdb5  jnz     short loc_18000BDF5
0x18000bdb7  call    cs:__imp_GetLastError
0x18000bdbe  nop     dword ptr [rax+rax+00h]
0x18000bdc3  mov     ebx, eax
0x18000bdc5  test    eax, eax
0x18000bdc7  jle     short loc_18000BDD2
0x18000bdc9  movzx   ebx, ax
0x18000bdcc  or      ebx, 80070000h
0x18000bdd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdd9  lea     rax, WPP_GLOBAL_Control
0x18000bde0  cmp     rcx, rax
0x18000bde3  jz      short loc_18000BDFC
0x18000bde5  test    byte ptr [rcx+1Ch], 1
0x18000bde9  jz      short loc_18000BDFC
0x18000bdeb  mov     edx, 13h
0x18000bdf0  jmp     loc_18000BD6B
0x18000bdf5  mov     cs:qword_180028CC8, rax
0x18000bdfc  call    cs:__imp_CoUninitialize
0x18000be03  nop     dword ptr [rax+rax+00h]
0x18000be08  test    ebx, ebx
0x18000be0a  jns     short loc_18000BE11
0x18000be0c  call    ?NcaNlmTriggerConnectionPointShutdown@@YAXXZ; NcaNlmTriggerConnectionPointShutdown(void)
0x18000be11  mov     eax, ebx
0x18000be13  add     rsp, 30h
0x18000be17  pop     rbx
0x18000be18  retn
```
