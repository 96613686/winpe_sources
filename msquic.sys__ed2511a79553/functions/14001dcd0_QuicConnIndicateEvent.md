# QuicConnIndicateEvent

- ea: `0x14001dcd0`
- end: `0x14001dda6`
- name: `QuicConnIndicateEvent`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005aa4`
- `0x1400099b4`
- `0x14000edc0`
- `0x140010440`
- `0x1400108c0`
- `0x140013200`
- `0x14001cc0c`
- `0x14001cd20`
- `0x14001d88c`
- `0x14001dbf0`
- `0x14001ddac`
- `0x14001f0e0`
- `0x14002ae60`
- `0x140031440`
- `0x1400324c4`
- `0x14004572c`
- `0x14004587c`

## callees

- `0x14001dcd0`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001dd62`
- `ntoskrnl!_snprintf_s` at `0x14001dd62`

## string_xrefs

- `0x14001dd25`: `Connection->State.HandleClosed || Connection->State.ShutdownComplete || !Connection->State.ExternalOwner`

## pseudocode

```c
__int64 __fastcall QuicConnIndicateEvent(__int64 a1, __int64 a2)
{
  unsigned int (__fastcall *v2)(__int64, _QWORD, __int64); // rax
  unsigned int v4; // edi
  char v5; // al
  __int64 v6; // rcx
  char DstBuf[128]; // [rsp+20h] [rbp-98h] BYREF

  v2 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(a1 + 3608);
  if ( v2 )
  {
    return v2(a1, *(_QWORD *)(a1 + 8), a2);
  }
  else
  {
    if ( (*(_BYTE *)(a1 + 252) & 0x40) != 0 )
    {
      v5 = *(_BYTE *)(a1 + 249);
      if ( (v5 & 3) == 0 && (v5 & 0x20) != 0 )
      {
        CxPlatLogAssert(
          "C:\\__w\\1\\s\\msquic\\src\\core\\connection.c",
          705,
          "Connection->State.HandleClosed || Connection->State.ShutdownComplete || !Connection->State.ExternalOwner");
        __int2c();
      }
    }
    v4 = -1073741436;
    if ( (byte_14005C48B & 0x40) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Event silently discarded (no handler).");
      McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogWarning, a1, DstBuf);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001dcd0  mov     [rsp+arg_10], rbx
0x14001dcd5  push    rdi
0x14001dcd6  sub     rsp, 0B0h
0x14001dcdd  mov     rax, cs:__security_cookie
0x14001dce4  xor     rax, rsp
0x14001dce7  mov     [rsp+0B8h+var_18], rax
0x14001dcef  mov     rax, [rcx+0E18h]
0x14001dcf6  mov     rbx, rcx
0x14001dcf9  test    rax, rax
0x14001dcfc  jz      short loc_14001DD0E
0x14001dcfe  mov     r8, rdx
0x14001dd01  mov     rdx, [rcx+8]
0x14001dd05  call    _guard_dispatch_icall
0x14001dd0a  mov     edi, eax
0x14001dd0c  jmp     short loc_14001DD82
0x14001dd0e  test    byte ptr [rcx+0FCh], 40h
0x14001dd15  jz      short loc_14001DD3F
0x14001dd17  mov     al, [rcx+0F9h]
0x14001dd1d  test    al, 3
0x14001dd1f  jnz     short loc_14001DD3F
0x14001dd21  test    al, 20h
0x14001dd23  jz      short loc_14001DD3F
0x14001dd25  lea     r8, aConnectionStat_3; "Connection->State.HandleClosed || Conne"...
0x14001dd2c  mov     edx, 2C1h
0x14001dd31  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x14001dd38  call    CxPlatLogAssert
0x14001dd3d  int     2Ch; Windows NT - assertion failure
0x14001dd3f  test    cs:byte_14005C48B, 40h
0x14001dd46  mov     edi, 0C0000184h
0x14001dd4b  jz      short loc_14001DD82
0x14001dd4d  lea     r9, aEventSilentlyD; "Event silently discarded (no handler)."
0x14001dd54  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001dd58  mov     edx, 80h; SizeInBytes
0x14001dd5d  lea     rcx, [rsp+0B8h+DstBuf]; DstBuf
0x14001dd62  call    cs:__imp__snprintf_s
0x14001dd69  nop     dword ptr [rax+rax+00h]
0x14001dd6e  lea     r9, [rsp+0B8h+DstBuf]
0x14001dd73  mov     r8, rbx
0x14001dd76  lea     rdx, QuicConnLogWarning
0x14001dd7d  call    McTemplateU0ps_EtwWriteTransfer
0x14001dd82  mov     eax, edi
0x14001dd84  mov     rcx, [rsp+0B8h+var_18]
0x14001dd8c  xor     rcx, rsp; StackCookie
0x14001dd8f  call    __security_check_cookie
0x14001dd94  mov     rbx, [rsp+0B8h+arg_10]
0x14001dd9c  add     rsp, 0B0h
0x14001dda3  pop     rdi
0x14001dda4  retn
```
