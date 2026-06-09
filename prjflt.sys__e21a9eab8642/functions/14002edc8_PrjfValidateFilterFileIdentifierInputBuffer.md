# PrjfValidateFilterFileIdentifierInputBuffer

- ea: `0x14002edc8`
- end: `0x14002eef2`
- name: `PrjfValidateFilterFileIdentifierInputBuffer`
- size: `298`
- prototype: `__int64 __fastcall(__int64, unsigned int, USHORT *, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002d668`

## callees

- `0x14000d128`
- `0x14002edc8`

## import_xrefs

- `ntoskrnl!RtlCompareAltitudes` at `0x14002eeb1`
- `ntoskrnl!RtlCompareAltitudes` at `0x14002eeb1`
- `FLTMGR!FltGetInstanceContext` at `0x14002edf6`
- `FLTMGR!FltGetInstanceContext` at `0x14002edf6`
- `FLTMGR!FltReleaseContext` at `0x14002eeda`
- `FLTMGR!FltReleaseContext` at `0x14002eeda`

## pseudocode

```c
__int64 __fastcall PrjfValidateFilterFileIdentifierInputBuffer(__int64 a1, unsigned int a2, USHORT *a3, _BYTE *a4)
{
  struct _FLT_INSTANCE *v4; // rcx
  int v8; // edx
  NTSTATUS InstanceContext; // ebx
  int v10; // r8d
  int v11; // ecx
  UNICODE_STRING Altitude2; // [rsp+60h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+A0h] [rbp+8h] BYREF

  v4 = *(struct _FLT_INSTANCE **)(a1 + 24);
  Context = 0;
  *a4 = 0;
  Altitude2 = 0;
  InstanceContext = FltGetInstanceContext(v4, &Context);
  if ( InstanceContext >= 0 )
  {
    if ( a2 < 4 || (v11 = *a3, a2 < v11 + 2) )
    {
      InstanceContext = -1073741811;
    }
    else
    {
      Altitude2.MaximumLength = *a3;
      Altitude2.Length = v11;
      Altitude2.Buffer = a3 + 1;
      if ( !RtlCompareAltitudes((PCUNICODE_STRING)((char *)Context + 8), &Altitude2) )
      {
        InstanceContext = 0;
        *a4 = 1;
      }
    }
  }
  else if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = xmmword_14001A3D0 & 0x80;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      519,
      v8,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      7,
      41,
      (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
      130,
      InstanceContext);
  }
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x14002edc8  mov     rax, rsp
0x14002edcb  push    rbx
0x14002edcc  push    rbp
0x14002edcd  push    rsi
0x14002edce  push    rdi
0x14002edcf  sub     rsp, 78h
0x14002edd3  mov     rcx, [rcx+18h]; Instance
0x14002edd7  mov     edi, edx
0x14002edd9  xorps   xmm0, xmm0
0x14002eddc  mov     qword ptr [rax+8], 0
0x14002ede4  lea     rdx, [rax+8]; Context
0x14002ede8  mov     byte ptr [r9], 0
0x14002edec  movups  xmmword ptr [rax-38h], xmm0
0x14002edf0  mov     rsi, r9
0x14002edf3  mov     rbp, r8
0x14002edf6  call    cs:__imp_FltGetInstanceContext
0x14002edfd  nop     dword ptr [rax+rax+00h]
0x14002ee02  mov     ebx, eax
0x14002ee04  test    eax, eax
0x14002ee06  jns     short loc_14002EE7D
0x14002ee08  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002ee0e  lea     rax, WPP_RECORDER_INITIALIZED
0x14002ee15  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002ee1c  setnz   r8b
0x14002ee20  and     dl, 80h
0x14002ee23  jnz     short loc_14002EE2E
0x14002ee25  test    r8b, r8b
0x14002ee28  jz      loc_14002EECD
0x14002ee2e  mov     r9, cs:WPP_GLOBAL_Control
0x14002ee35  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002ee3c  mov     [rsp+98h+var_48], ebx
0x14002ee40  mov     ecx, 207h
0x14002ee45  mov     [rsp+98h+var_50], 382h
0x14002ee4d  mov     [rsp+98h+var_58], rax
0x14002ee52  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002ee59  mov     r9, [r9+40h]
0x14002ee5d  mov     [rsp+98h+var_60], rax
0x14002ee62  mov     [rsp+98h+var_68], 29h ; ')'
0x14002ee69  mov     [rsp+98h+var_70], 7
0x14002ee71  mov     [rsp+98h+var_78], 2
0x14002ee76  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002ee7b  jmp     short loc_14002EECD
0x14002ee7d  cmp     edi, 4
0x14002ee80  jb      short loc_14002EEC8
0x14002ee82  movzx   ecx, word ptr [rbp+0]
0x14002ee86  lea     eax, [rcx+2]
0x14002ee89  cmp     edi, eax
0x14002ee8b  jb      short loc_14002EEC8
0x14002ee8d  mov     [rsp+98h+Altitude2.MaximumLength], cx
0x14002ee92  lea     rax, [rbp+2]
0x14002ee96  mov     [rsp+98h+Altitude2.Length], cx
0x14002ee9b  lea     rdx, [rsp+98h+Altitude2]; Altitude2
0x14002eea0  mov     rcx, [rsp+98h+Context]
0x14002eea8  add     rcx, 8; Altitude1
0x14002eeac  mov     [rsp+98h+Altitude2.Buffer], rax
0x14002eeb1  call    cs:__imp_RtlCompareAltitudes
0x14002eeb8  nop     dword ptr [rax+rax+00h]
0x14002eebd  test    eax, eax
0x14002eebf  jnz     short loc_14002EECD
0x14002eec1  xor     ebx, ebx
0x14002eec3  mov     byte ptr [rsi], 1
0x14002eec6  jmp     short loc_14002EECD
0x14002eec8  mov     ebx, 0C000000Dh
0x14002eecd  mov     rcx, [rsp+98h+Context]; Context
0x14002eed5  test    rcx, rcx
0x14002eed8  jz      short loc_14002EEE6
0x14002eeda  call    cs:__imp_FltReleaseContext
0x14002eee1  nop     dword ptr [rax+rax+00h]
0x14002eee6  mov     eax, ebx
0x14002eee8  add     rsp, 78h
0x14002eeec  pop     rdi
0x14002eeed  pop     rsi
0x14002eeee  pop     rbp
0x14002eeef  pop     rbx
0x14002eef0  retn
```
