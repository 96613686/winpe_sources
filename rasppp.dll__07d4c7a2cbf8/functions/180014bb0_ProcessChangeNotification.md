# ProcessChangeNotification

- ea: `0x180014bb0`
- end: `0x180014cf8`
- name: `ProcessChangeNotification`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017bc0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800054a8`
- `0x180012024`
- `0x180014bb0`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014cd6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014cd6`

## string_xrefs

- `0x180014c7a`: `ChangeNotification for Protocol 0x%x failed, error=%d`

## pseudocode

```c
int __fastcall ProcessChangeNotification(__int64 a1)
{
  __int64 (*v2)(void); // rax
  unsigned int v3; // ebp
  unsigned int i; // ebx
  __int64 v5; // rdi
  int v7; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v8[2044]; // [rsp+34h] [rbp-834h] BYREF

  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
      L"Processing change notification event");
  ReadPPPKeyValues(hKey);
  LODWORD(v2) = LoadParserDll(hKey);
  v3 = PppConfigInfo + HIDWORD(PppConfigInfo);
  for ( i = 0; i < v3; ++i )
  {
    v5 = 176LL * i;
    LODWORD(v2) = (_DWORD)CpTable;
    if ( (*((_BYTE *)CpTable + v5 + 168) & 2) != 0 )
    {
      v2 = *(__int64 (**)(void))((char *)CpTable + v5 + 152);
      if ( v2 )
      {
        LODWORD(v2) = v2();
        if ( (_DWORD)v2 )
        {
          if ( byte_18004CF33 < 0 )
          {
            LOWORD(v7) = 0;
            LODWORD(v2) = FormatRRASErrorString(
                            &v7,
                            L"ChangeNotification for Protocol 0x%x failed, error=%d",
                            *(unsigned int *)((char *)CpTable + v5),
                            (unsigned int)v2);
            if ( byte_18004CF33 < 0 )
              LODWORD(v2) = McTemplateU0z_EventWriteTransfer(
                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              (const EVENT_DESCRIPTOR *)RasPppTraceError,
                              (const wchar_t *)&v7);
          }
        }
      }
    }
  }
  if ( a1 && !_InterlockedDecrement((volatile signed __int32 *)&g_DdmMsgHandler) )
    LODWORD(v2) = SetEvent(*((HANDLE *)&g_DdmMsgHandler + 1));
  return (int)v2;
}

```

## disassembly

```asm
0x180014bb0  push    rbx
0x180014bb2  push    rbp
0x180014bb3  push    rsi
0x180014bb4  push    rdi
0x180014bb5  sub     rsp, 848h
0x180014bbc  mov     rax, cs:__security_cookie
0x180014bc3  xor     rax, rsp
0x180014bc6  mov     [rsp+868h+var_38], rax
0x180014bce  mov     rsi, rcx
0x180014bd1  xor     eax, eax
0x180014bd3  lea     rcx, [rsp+868h+var_834]; void *
0x180014bd8  mov     [rsp+868h+var_838], eax
0x180014bdc  xor     edx, edx; Val
0x180014bde  mov     r8d, 7FCh; Size
0x180014be4  call    memset_0
0x180014be9  test    cs:byte_18004CF34, 1
0x180014bf0  jz      short loc_180014C0C
0x180014bf2  lea     r8, aProcessingChan; "Processing change notification event"
0x180014bf9  lea     rdx, RasPppTraceInfo
0x180014c00  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014c07  call    McTemplateU0z_EventWriteTransfer
0x180014c0c  mov     rcx, cs:hKey; hKey
0x180014c13  call    ReadPPPKeyValues
0x180014c18  mov     rcx, cs:hKey; hKey
0x180014c1f  call    LoadParserDll
0x180014c24  mov     ebp, dword ptr cs:PppConfigInfo+4
0x180014c2a  add     ebp, dword ptr cs:PppConfigInfo
0x180014c30  xor     ebx, ebx
0x180014c32  cmp     ebx, ebp
0x180014c34  jnb     loc_180014CC1
0x180014c3a  mov     eax, ebx
0x180014c3c  imul    rdi, rax, 0B0h
0x180014c43  mov     rax, cs:CpTable
0x180014c4a  test    byte ptr [rdi+rax+0A8h], 2
0x180014c52  jz      short loc_180014CBA
0x180014c54  mov     rax, [rdi+rax+98h]
0x180014c5c  test    rax, rax
0x180014c5f  jz      short loc_180014CBA
0x180014c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c66  test    eax, eax
0x180014c68  jz      short loc_180014CBA
0x180014c6a  cmp     cs:byte_18004CF33, 0
0x180014c71  jge     short loc_180014CBA
0x180014c73  mov     r8, cs:CpTable
0x180014c7a  lea     rdx, aChangenotifica; "ChangeNotification for Protocol 0x%x fa"...
0x180014c81  xor     ecx, ecx
0x180014c83  mov     r9d, eax
0x180014c86  mov     word ptr [rsp+868h+var_838], cx
0x180014c8b  lea     rcx, [rsp+868h+var_838]
0x180014c90  mov     r8d, [rdi+r8]
0x180014c94  call    FormatRRASErrorString
0x180014c99  cmp     cs:byte_18004CF33, 0
0x180014ca0  jge     short loc_180014CBA
0x180014ca2  lea     r8, [rsp+868h+var_838]
0x180014ca7  lea     rdx, RasPppTraceError
0x180014cae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014cb5  call    McTemplateU0z_EventWriteTransfer
0x180014cba  inc     ebx
0x180014cbc  jmp     loc_180014C32
0x180014cc1  test    rsi, rsi
0x180014cc4  jz      short loc_180014CDC
0x180014cc6  lock dec dword ptr cs:g_DdmMsgHandler
0x180014ccd  jnz     short loc_180014CDC
0x180014ccf  mov     rcx, qword ptr cs:g_DdmMsgHandler+8; hEvent
0x180014cd6  call    cs:__imp_SetEvent
0x180014cdc  mov     rcx, [rsp+868h+var_38]
0x180014ce4  xor     rcx, rsp; StackCookie
0x180014ce7  call    __security_check_cookie
0x180014cec  add     rsp, 848h
0x180014cf3  pop     rdi
0x180014cf4  pop     rsi
0x180014cf5  pop     rbp
0x180014cf6  pop     rbx
0x180014cf7  retn
```
