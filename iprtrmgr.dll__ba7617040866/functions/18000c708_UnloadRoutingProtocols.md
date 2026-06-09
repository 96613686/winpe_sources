# UnloadRoutingProtocols

- ea: `0x18000c708`
- end: `0x18000c86b`
- name: `UnloadRoutingProtocols`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c054`

## callees

- `0x18000ac60`
- `0x18000c708`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000c806`
- `KERNEL32!FreeLibrary` at `0x18000c806`
- `KERNEL32!Sleep` at `0x18000c7fc`
- `KERNEL32!Sleep` at `0x18000c7fc`
- `KERNEL32!HeapFree` at `0x18000c818`
- `KERNEL32!HeapFree` at `0x18000c818`

## string_xrefs

- `0x18000c749`: `UnloadRoutingProtocols`
- `0x18000c796`: `Unloading routing protocols for transport %d`
- `0x18000c830`: `Leaving: UnloadRoutingProtocols`

## pseudocode

```c
int __fastcall UnloadRoutingProtocols(unsigned int a1)
{
  __int64 *v2; // rax
  void **v3; // rbx
  void *v4; // rdi
  void **v5; // rax
  int v7; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+34h] [rbp-814h] BYREF

  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString(&v7, L"Entered: %ws", L"UnloadRoutingProtocols");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v7);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString(&v7, L"Unloading routing protocols for transport %d", a1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v7);
      }
    }
  }
  v2 = &g_leProtoCbListV6;
  v3 = &g_leProtoCbListV4;
  if ( a1 != 33 )
    v3 = (void **)&g_leProtoCbListV6;
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( *((void ***)v4 + 1) != v3 || (v5 = *(void ***)v4, *(void **)(*(_QWORD *)v4 + 8LL) != v4) )
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    Sleep(0);
    FreeLibrary(*((HMODULE *)v4 + 5));
    LODWORD(v2) = HeapFree(IPRouterHeap, 0, v4);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    LODWORD(v2) = McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasRtrmgrTraceInfo,
                    L"Leaving: UnloadRoutingProtocols");
  return (int)v2;
}

```

## disassembly

```asm
0x18000c708  mov     [rsp+arg_8], rbx
0x18000c70d  push    rdi
0x18000c70e  sub     rsp, 840h
0x18000c715  mov     rax, cs:__security_cookie
0x18000c71c  xor     rax, rsp
0x18000c71f  mov     [rsp+848h+var_18], rax
0x18000c727  mov     edi, ecx
0x18000c729  xor     ebx, ebx
0x18000c72b  lea     rcx, [rsp+848h+var_814]; void *
0x18000c730  mov     [rsp+848h+var_818], ebx
0x18000c734  xor     edx, edx; Val
0x18000c736  mov     r8d, 7FCh; Size
0x18000c73c  call    memset_0
0x18000c741  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18000c747  jge     short loc_18000C7C7
0x18000c749  lea     r8, aUnloadroutingp; "UnloadRoutingProtocols"
0x18000c750  mov     word ptr [rsp+848h+var_818], bx
0x18000c755  lea     rdx, aEnteredWs; "Entered: %ws"
0x18000c75c  lea     rcx, [rsp+848h+var_818]
0x18000c761  call    FormatRRASErrorString
0x18000c766  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18000c76c  jge     short loc_18000C7C7
0x18000c76e  lea     r8, [rsp+848h+var_818]
0x18000c773  lea     rdx, RasRtrmgrTraceInfo
0x18000c77a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c781  call    McTemplateU0z_EventWriteTransfer
0x18000c786  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18000c78c  jge     short loc_18000C7C7
0x18000c78e  mov     r8d, edi
0x18000c791  mov     word ptr [rsp+848h+var_818], bx
0x18000c796  lea     rdx, aUnloadingRouti; "Unloading routing protocols for transpo"...
0x18000c79d  lea     rcx, [rsp+848h+var_818]
0x18000c7a2  call    FormatRRASErrorString
0x18000c7a7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18000c7ad  jge     short loc_18000C7C7
0x18000c7af  lea     r8, [rsp+848h+var_818]
0x18000c7b4  lea     rdx, RasRtrmgrTraceInfo
0x18000c7bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c7c2  call    McTemplateU0z_EventWriteTransfer
0x18000c7c7  cmp     edi, 21h ; '!'
0x18000c7ca  lea     rax, g_leProtoCbListV6
0x18000c7d1  lea     rbx, g_leProtoCbListV4
0x18000c7d8  cmovnz  rbx, rax
0x18000c7dc  mov     rdi, [rbx]
0x18000c7df  cmp     rdi, rbx
0x18000c7e2  jz      short loc_18000C827
0x18000c7e4  cmp     [rdi+8], rbx
0x18000c7e8  jnz     short loc_18000C820
0x18000c7ea  mov     rax, [rdi]
0x18000c7ed  cmp     [rax+8], rdi
0x18000c7f1  jnz     short loc_18000C820
0x18000c7f3  mov     [rbx], rax
0x18000c7f6  xor     ecx, ecx; dwMilliseconds
0x18000c7f8  mov     [rax+8], rbx
0x18000c7fc  call    cs:__imp_Sleep
0x18000c802  mov     rcx, [rdi+28h]; hLibModule
0x18000c806  call    cs:__imp_FreeLibrary
0x18000c80c  mov     rcx, cs:IPRouterHeap; hHeap
0x18000c813  mov     r8, rdi; lpMem
0x18000c816  xor     edx, edx; dwFlags
0x18000c818  call    cs:__imp_HeapFree
0x18000c81e  jmp     short loc_18000C7DC
0x18000c820  mov     ecx, 3
0x18000c825  int     29h; Win8: RtlFailFast(ecx)
0x18000c827  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000c82e  jz      short loc_18000C84A
0x18000c830  lea     r8, aLeavingUnloadr; "Leaving: UnloadRoutingProtocols"
0x18000c837  lea     rdx, RasRtrmgrTraceInfo
0x18000c83e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c845  call    McTemplateU0z_EventWriteTransfer
0x18000c84a  mov     rcx, [rsp+848h+var_18]
0x18000c852  xor     rcx, rsp; StackCookie
0x18000c855  call    __security_check_cookie
0x18000c85a  mov     rbx, [rsp+848h+arg_8]
0x18000c862  add     rsp, 840h
0x18000c869  pop     rdi
0x18000c86a  retn
```
