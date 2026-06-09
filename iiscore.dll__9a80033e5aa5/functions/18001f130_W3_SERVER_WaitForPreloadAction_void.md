# W3_SERVER::WaitForPreloadAction(void)

- ea: `0x18001f130`
- end: `0x18001f19c`
- name: `?WaitForPreloadAction@W3_SERVER@@AEBAXXZ`
- size: `108`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e694`
- `0x18001e7f0`

## callees

- `0x18001f130`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f186`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f186`
- `iisutil!PuDbgPrint` at `0x18001f17b`
- `iisutil!PuDbgPrint` at `0x18001f17b`

## string_xrefs

- `0x18001f15e`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.h`

## pseudocode

```c
void __fastcall W3_SERVER::WaitForPreloadAction(W3_SERVER *this)
{
  int i; // eax

  for ( i = *((_DWORD *)this + 402); i > 0; i = *((_DWORD *)this + 402) )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.h",
        952,
        "W3_SERVER::WaitForPreloadAction",
        "Waiting for %d preload actions to finish.\r\n",
        *((_DWORD *)this + 402));
    Sleep(0x3E8u);
  }
}

```

## disassembly

```asm
0x18001f130  push    rbx
0x18001f132  sub     rsp, 30h
0x18001f136  mov     eax, [rcx+648h]
0x18001f13c  mov     rbx, rcx
0x18001f13f  jmp     short loc_18001F192
0x18001f141  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f148  jz      short loc_18001F181
0x18001f14a  mov     eax, [rbx+648h]
0x18001f150  lea     r9, aW3ServerWaitfo; "W3_SERVER::WaitForPreloadAction"
0x18001f157  mov     rcx, cs:g_pDebug
0x18001f15e  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001f165  mov     [rsp+38h+var_10], eax
0x18001f169  mov     r8d, 3B8h
0x18001f16f  lea     rax, aWaitingForDPre; "Waiting for %d preload actions to finis"...
0x18001f176  mov     [rsp+38h+var_18], rax
0x18001f17b  call    cs:__imp_PuDbgPrint
0x18001f181  mov     ecx, 3E8h; dwMilliseconds
0x18001f186  call    cs:__imp_Sleep
0x18001f18c  mov     eax, [rbx+648h]
0x18001f192  test    eax, eax
0x18001f194  jg      short loc_18001F141
0x18001f196  add     rsp, 30h
0x18001f19a  pop     rbx
0x18001f19b  retn
```
