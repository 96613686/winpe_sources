# ProcessChangeNotification

- ea: `0x1800152d0`
- end: `0x18001541f`
- name: `ProcessChangeNotification`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800183e0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180005698`
- `0x18001264c`
- `0x1800152d0`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800153f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800153f6`

## string_xrefs

- `0x18001539a`: `ChangeNotification for Protocol 0x%x failed, error=%d`

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
  if ( (byte_18004DF34 & 1) != 0 )
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
          if ( byte_18004DF33 < 0 )
          {
            LOWORD(v7) = 0;
            LODWORD(v2) = FormatRRASErrorString(
                            &v7,
                            L"ChangeNotification for Protocol 0x%x failed, error=%d",
                            *(unsigned int *)((char *)CpTable + v5),
                            (unsigned int)v2);
            if ( byte_18004DF33 < 0 )
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
0x1800152d0  push    rbx
0x1800152d2  push    rbp
0x1800152d3  push    rsi
0x1800152d4  push    rdi
0x1800152d5  sub     rsp, 848h
0x1800152dc  mov     rax, cs:__security_cookie
0x1800152e3  xor     rax, rsp
0x1800152e6  mov     [rsp+868h+var_38], rax
0x1800152ee  mov     rsi, rcx
0x1800152f1  xor     eax, eax
0x1800152f3  lea     rcx, [rsp+868h+var_834]; void *
0x1800152f8  mov     [rsp+868h+var_838], eax
0x1800152fc  xor     edx, edx; Val
0x1800152fe  mov     r8d, 7FCh; Size
0x180015304  call    memset_0
0x180015309  test    cs:byte_18004DF34, 1
0x180015310  jz      short loc_18001532C
0x180015312  lea     r8, aProcessingChan; "Processing change notification event"
0x180015319  lea     rdx, RasPppTraceInfo
0x180015320  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015327  call    McTemplateU0z_EventWriteTransfer
0x18001532c  mov     rcx, cs:hKey; hKey
0x180015333  call    ReadPPPKeyValues
0x180015338  mov     rcx, cs:hKey; hKey
0x18001533f  call    LoadParserDll
0x180015344  mov     ebp, dword ptr cs:PppConfigInfo+4
0x18001534a  add     ebp, dword ptr cs:PppConfigInfo
0x180015350  xor     ebx, ebx
0x180015352  cmp     ebx, ebp
0x180015354  jnb     loc_1800153E1
0x18001535a  mov     eax, ebx
0x18001535c  imul    rdi, rax, 0B0h
0x180015363  mov     rax, cs:CpTable
0x18001536a  test    byte ptr [rdi+rax+0A8h], 2
0x180015372  jz      short loc_1800153DA
0x180015374  mov     rax, [rdi+rax+98h]
0x18001537c  test    rax, rax
0x18001537f  jz      short loc_1800153DA
0x180015381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015386  test    eax, eax
0x180015388  jz      short loc_1800153DA
0x18001538a  cmp     cs:byte_18004DF33, 0
0x180015391  jge     short loc_1800153DA
0x180015393  mov     r8, cs:CpTable
0x18001539a  lea     rdx, aChangenotifica; "ChangeNotification for Protocol 0x%x fa"...
0x1800153a1  xor     ecx, ecx
0x1800153a3  mov     r9d, eax
0x1800153a6  mov     word ptr [rsp+868h+var_838], cx
0x1800153ab  lea     rcx, [rsp+868h+var_838]
0x1800153b0  mov     r8d, [rdi+r8]
0x1800153b4  call    FormatRRASErrorString
0x1800153b9  cmp     cs:byte_18004DF33, 0
0x1800153c0  jge     short loc_1800153DA
0x1800153c2  lea     r8, [rsp+868h+var_838]
0x1800153c7  lea     rdx, RasPppTraceError
0x1800153ce  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800153d5  call    McTemplateU0z_EventWriteTransfer
0x1800153da  inc     ebx
0x1800153dc  jmp     loc_180015352
0x1800153e1  test    rsi, rsi
0x1800153e4  jz      short loc_180015402
0x1800153e6  lock dec dword ptr cs:g_DdmMsgHandler
0x1800153ed  jnz     short loc_180015402
0x1800153ef  mov     rcx, qword ptr cs:g_DdmMsgHandler+8; hEvent
0x1800153f6  call    cs:__imp_SetEvent
0x1800153fd  nop     dword ptr [rax+rax+00h]
0x180015402  mov     rcx, [rsp+868h+var_38]
0x18001540a  xor     rcx, rsp; StackCookie
0x18001540d  call    __security_check_cookie
0x180015412  add     rsp, 848h
0x180015419  pop     rdi
0x18001541a  pop     rsi
0x18001541b  pop     rbp
0x18001541c  pop     rbx
0x18001541d  retn
```
