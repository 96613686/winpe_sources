# CDimRouterManager::CreateRMStateEvent(void)

- ea: `0x18002dccc`
- end: `0x18002dd91`
- name: `?CreateRMStateEvent@CDimRouterManager@@AEAAKXZ`
- size: `197`
- prototype: `__int64 __fastcall(CDimRouterManager *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002eb5c`

## callees

- `0x18000def0`
- `0x18002dccc`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dd12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dd12`

## string_xrefs

- `0x18002dd34`: `CreateRMStateEvent: CreateEvent failed with %d`

## pseudocode

```c
__int64 __fastcall CDimRouterManager::CreateRMStateEvent(CDimRouterManager *this)
{
  DWORD v2; // edi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  int v6; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+24h] [rbp-814h] BYREF

  v6 = 0;
  v2 = 0;
  memset_0(v7, 0, sizeof(v7));
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"CreateRMStateEvent: CreateEvent failed with %d", LastError);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v6);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002dccc  mov     [rsp+arg_8], rbx
0x18002dcd1  push    rdi
0x18002dcd2  sub     rsp, 830h
0x18002dcd9  mov     rax, cs:__security_cookie
0x18002dce0  xor     rax, rsp
0x18002dce3  mov     [rsp+838h+var_18], rax
0x18002dceb  mov     rbx, rcx
0x18002dcee  xor     eax, eax
0x18002dcf0  lea     rcx, [rsp+838h+var_814]; void *
0x18002dcf5  mov     [rsp+838h+var_818], eax
0x18002dcf9  xor     edx, edx; Val
0x18002dcfb  mov     r8d, 7FCh; Size
0x18002dd01  xor     edi, edi
0x18002dd03  call    memset_0
0x18002dd08  xor     r9d, r9d; lpName
0x18002dd0b  xor     r8d, r8d; bInitialState
0x18002dd0e  xor     edx, edx; bManualReset
0x18002dd10  xor     ecx, ecx; lpEventAttributes
0x18002dd12  call    cs:__imp_CreateEventW
0x18002dd18  mov     [rbx+10h], rax
0x18002dd1c  test    rax, rax
0x18002dd1f  jnz     short loc_18002DD6E
0x18002dd21  call    cs:__imp_GetLastError
0x18002dd27  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002dd2e  mov     edi, eax
0x18002dd30  jz      short loc_18002DD6E
0x18002dd32  xor     ecx, ecx
0x18002dd34  lea     rdx, aCreatermstatee; "CreateRMStateEvent: CreateEvent failed "...
0x18002dd3b  mov     word ptr [rsp+838h+var_818], cx
0x18002dd40  mov     r8d, eax
0x18002dd43  lea     rcx, [rsp+838h+var_818]
0x18002dd48  call    FormatRRASErrorString
0x18002dd4d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002dd54  jz      short loc_18002DD6E
0x18002dd56  lea     r8, [rsp+838h+var_818]
0x18002dd5b  lea     rdx, RasDimTraceError
0x18002dd62  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002dd69  call    McTemplateU0z_EventWriteTransfer
0x18002dd6e  mov     eax, edi
0x18002dd70  mov     rcx, [rsp+838h+var_18]
0x18002dd78  xor     rcx, rsp; StackCookie
0x18002dd7b  call    __security_check_cookie
0x18002dd80  mov     rbx, [rsp+838h+arg_8]
0x18002dd88  add     rsp, 830h
0x18002dd8f  pop     rdi
0x18002dd90  retn
```
