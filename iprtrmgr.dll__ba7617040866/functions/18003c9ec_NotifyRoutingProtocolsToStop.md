# NotifyRoutingProtocolsToStop

- ea: `0x18003c9ec`
- end: `0x18003caba`
- name: `NotifyRoutingProtocolsToStop`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180050b74`

## callees

- `0x18000ac60`
- `0x18003c9ec`
- `0x18003d534`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003ca6d`
- `KERNEL32!FreeLibrary` at `0x18003ca6d`
- `KERNEL32!Sleep` at `0x18003ca63`
- `KERNEL32!Sleep` at `0x18003ca63`
- `KERNEL32!HeapFree` at `0x18003ca98`
- `KERNEL32!HeapFree` at `0x18003ca98`

## string_xrefs

- `0x18003ca01`: `NotifyRoutingProtocolsToStop`

## pseudocode

```c
int __fastcall NotifyRoutingProtocolsToStop(int a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rax
  __int64 *v4; // rsi
  HMODULE *v5; // rdi
  HMODULE v6; // rcx
  void **v7; // rax

  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"NotifyRoutingProtocolsToStop");
  v2 = (__int64 *)g_leProtoCbListV6;
  v3 = &g_leProtoCbListV6;
  v4 = (__int64 *)&g_leProtoCbListV4;
  if ( a1 )
    v2 = (__int64 *)g_leProtoCbListV4;
  else
    v4 = &g_leProtoCbListV6;
  while ( v2 != v4 )
  {
    while ( *((_DWORD *)v2 + 4) == 1 )
      ;
    if ( *((_DWORD *)v2 + 4) != 2 )
    {
      v5 = (HMODULE *)v2;
      LODWORD(v3) = StopRoutingProtocol((__int64)v2);
      v2 = (__int64 *)*v2;
      if ( !(_DWORD)v3 )
      {
        Sleep(0);
        FreeLibrary(v5[5]);
        v6 = *v5;
        if ( *((HMODULE **)*v5 + 1) != v5 || (v7 = (void **)v5[1], *v7 != v5) )
          __fastfail(3u);
        *v7 = v6;
        *((_QWORD *)v6 + 1) = v7;
        LODWORD(v3) = HeapFree(IPRouterHeap, 0, v5);
        --TotalRoutingProtocols;
      }
    }
  }
  return (int)v3;
}

```

## disassembly

```asm
0x18003c9ec  push    rbx
0x18003c9ee  push    rsi
0x18003c9ef  push    rdi
0x18003c9f0  push    r14
0x18003c9f2  sub     rsp, 28h
0x18003c9f6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003c9fd  mov     edi, ecx
0x18003c9ff  jz      short loc_18003CA1B
0x18003ca01  lea     r8, aNotifyroutingp; "NotifyRoutingProtocolsToStop"
0x18003ca08  lea     rdx, RasRtrmgrTraceInfo
0x18003ca0f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ca16  call    McTemplateU0z_EventWriteTransfer
0x18003ca1b  mov     rbx, cs:g_leProtoCbListV6
0x18003ca22  lea     rax, g_leProtoCbListV6
0x18003ca29  test    edi, edi
0x18003ca2b  lea     rsi, g_leProtoCbListV4
0x18003ca32  cmovnz  rbx, cs:g_leProtoCbListV4
0x18003ca3a  cmovz   rsi, rax
0x18003ca3e  jmp     short loc_18003CAA4
0x18003ca40  cmp     dword ptr [rbx+10h], 1
0x18003ca44  jz      short loc_18003CA40
0x18003ca46  cmp     dword ptr [rbx+10h], 2
0x18003ca4a  jz      short loc_18003CAA4
0x18003ca4c  mov     rcx, rbx
0x18003ca4f  mov     r14, rbx
0x18003ca52  mov     rdi, rbx
0x18003ca55  call    StopRoutingProtocol
0x18003ca5a  mov     rbx, [rbx]
0x18003ca5d  test    eax, eax
0x18003ca5f  jnz     short loc_18003CAA4
0x18003ca61  xor     ecx, ecx; dwMilliseconds
0x18003ca63  call    cs:__imp_Sleep
0x18003ca69  mov     rcx, [rdi+28h]; hLibModule
0x18003ca6d  call    cs:__imp_FreeLibrary
0x18003ca73  mov     rcx, [rdi]
0x18003ca76  cmp     [rcx+8], rdi
0x18003ca7a  jnz     short loc_18003CAB3
0x18003ca7c  mov     rax, [rdi+8]
0x18003ca80  cmp     [rax], rdi
0x18003ca83  jnz     short loc_18003CAB3
0x18003ca85  mov     [rax], rcx
0x18003ca88  mov     r8, rdi; lpMem
0x18003ca8b  mov     [rcx+8], rax
0x18003ca8f  xor     edx, edx; dwFlags
0x18003ca91  mov     rcx, cs:IPRouterHeap; hHeap
0x18003ca98  call    cs:__imp_HeapFree
0x18003ca9e  dec     cs:TotalRoutingProtocols
0x18003caa4  cmp     rbx, rsi
0x18003caa7  jnz     short loc_18003CA40
0x18003caa9  add     rsp, 28h
0x18003caad  pop     r14
0x18003caaf  pop     rdi
0x18003cab0  pop     rsi
0x18003cab1  pop     rbx
0x18003cab2  retn
0x18003cab3  mov     ecx, 3
0x18003cab8  int     29h; Win8: RtlFailFast(ecx)
```
