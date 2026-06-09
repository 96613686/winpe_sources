# W3_SERVER::WaitForPreloadAction(void)

- ea: `0x180020ca4`
- end: `0x180020d1d`
- name: `?WaitForPreloadAction@W3_SERVER@@AEBAXXZ`
- size: `121`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020148`
- `0x1800202bc`

## callees

- `0x180020ca4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020d00`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020d00`
- `iisutil!PuDbgPrint` at `0x180020cef`
- `iisutil!PuDbgPrint` at `0x180020cef`

## string_xrefs

- `0x180020cd2`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.h`

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
0x180020ca4  push    rbx
0x180020ca6  sub     rsp, 30h
0x180020caa  mov     eax, [rcx+648h]
0x180020cb0  mov     rbx, rcx
0x180020cb3  jmp     short loc_180020D12
0x180020cb5  test    byte ptr cs:g_dwDebugFlags, 3
0x180020cbc  jz      short loc_180020CFB
0x180020cbe  mov     eax, [rbx+648h]
0x180020cc4  lea     r9, aW3ServerWaitfo; "W3_SERVER::WaitForPreloadAction"
0x180020ccb  mov     rcx, cs:g_pDebug
0x180020cd2  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180020cd9  mov     [rsp+38h+var_10], eax
0x180020cdd  mov     r8d, 3B8h
0x180020ce3  lea     rax, aWaitingForDPre; "Waiting for %d preload actions to finis"...
0x180020cea  mov     [rsp+38h+var_18], rax
0x180020cef  call    cs:__imp_PuDbgPrint
0x180020cf6  nop     dword ptr [rax+rax+00h]
0x180020cfb  mov     ecx, 3E8h; dwMilliseconds
0x180020d00  call    cs:__imp_Sleep
0x180020d07  nop     dword ptr [rax+rax+00h]
0x180020d0c  mov     eax, [rbx+648h]
0x180020d12  test    eax, eax
0x180020d14  jg      short loc_180020CB5
0x180020d16  add     rsp, 30h
0x180020d1a  pop     rbx
0x180020d1b  retn
```
