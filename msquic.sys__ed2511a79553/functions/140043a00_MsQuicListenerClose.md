# MsQuicListenerClose

- ea: `0x140043a00`
- end: `0x140043add`
- name: `MsQuicListenerClose`
- size: `221`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14002bc40`
- `0x14002be18`
- `0x1400337e4`
- `0x14003eb54`
- `0x140040c2c`
- `0x140043a00`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140043a7b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140043a7b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140043aad`
- `ntoskrnl!KeWaitForSingleObject` at `0x140043aad`

## pseudocode

```c
void __fastcall MsQuicListenerClose(char *P, __int64 a2)
{
  __int64 v3; // rcx

  if ( P )
  {
    if ( *(_DWORD *)P != 2 )
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\listener.c",
        159,
        "Handle == ((void *)0) || Handle->Type == QUIC_HANDLE_TYPE_LISTENER");
    if ( *(_DWORD *)P == 2 )
    {
      if ( (Microsoft_QuicEnableBits & 8) != 0 )
        McTemplateU0qp_EtwWriteTransfer(P, a2, 9, P);
      if ( (MsQuicLib & 0x20) != 0 && P[17] )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\listener.c", 173, "!Listener->AppClosed");
        __int2c();
      }
      P[17] = 1;
      if ( *((HANDLE *)P + 3) == PsGetCurrentThreadId() )
      {
        P[19] = 1;
      }
      else
      {
        QuicListenerStopAsync(P);
        KeWaitForSingleObject(P + 88, Executive, 0, 0, 0);
        QuicListenerFree(P);
      }
      if ( (Microsoft_QuicEnableBits & 8) != 0 )
        McTemplateU0_EtwWriteTransfer(v3, QuicApiExit);
    }
  }
}

```

## disassembly

```asm
0x140043a00  test    rcx, rcx
0x140043a03  jz      locret_140043ADB
0x140043a09  push    rbx
0x140043a0a  sub     rsp, 30h
0x140043a0e  cmp     dword ptr [rcx], 2
0x140043a11  mov     rbx, rcx
0x140043a14  jz      short loc_140043A2E
0x140043a16  lea     r8, aHandleVoid0Han; "Handle == ((void *)0) || Handle->Type ="...
0x140043a1d  mov     edx, 9Fh
0x140043a22  lea     rcx, aCW1SMsquicSrcC; "C:\\__w\\1\\s\\msquic\\src\\core\\liste"...
0x140043a29  call    CxPlatLogAssert
0x140043a2e  cmp     dword ptr [rbx], 2
0x140043a31  jnz     loc_140043AD6
0x140043a37  test    cs:Microsoft_QuicEnableBits, 8
0x140043a3e  jz      short loc_140043A4E
0x140043a40  mov     r9, rbx
0x140043a43  mov     r8d, 9
0x140043a49  call    McTemplateU0qp_EtwWriteTransfer
0x140043a4e  test    cs:MsQuicLib, 20h
0x140043a55  jz      short loc_140043A77
0x140043a57  cmp     byte ptr [rbx+11h], 0
0x140043a5b  jz      short loc_140043A77
0x140043a5d  lea     r8, aListenerAppclo; "!Listener->AppClosed"
0x140043a64  mov     edx, 0ADh
0x140043a69  lea     rcx, aCW1SMsquicSrcC; "C:\\__w\\1\\s\\msquic\\src\\core\\liste"...
0x140043a70  call    CxPlatLogAssert
0x140043a75  int     2Ch; Windows NT - assertion failure
0x140043a77  mov     byte ptr [rbx+11h], 1
0x140043a7b  call    cs:__imp_PsGetCurrentThreadId
0x140043a82  nop     dword ptr [rax+rax+00h]
0x140043a87  cmp     [rbx+18h], rax
0x140043a8b  jnz     short loc_140043A93
0x140043a8d  mov     byte ptr [rbx+13h], 1
0x140043a91  jmp     short loc_140043AC1
0x140043a93  mov     rcx, rbx
0x140043a96  call    QuicListenerStopAsync
0x140043a9b  and     [rsp+38h+var_18], 0
0x140043aa1  lea     rcx, [rbx+58h]; Object
0x140043aa5  xor     r9d, r9d; Alertable
0x140043aa8  xor     r8d, r8d; WaitMode
0x140043aab  xor     edx, edx; WaitReason
0x140043aad  call    cs:__imp_KeWaitForSingleObject
0x140043ab4  nop     dword ptr [rax+rax+00h]
0x140043ab9  mov     rcx, rbx; P
0x140043abc  call    QuicListenerFree
0x140043ac1  test    cs:Microsoft_QuicEnableBits, 8
0x140043ac8  jz      short loc_140043AD6
0x140043aca  lea     rdx, QuicApiExit
0x140043ad1  call    McTemplateU0_EtwWriteTransfer
0x140043ad6  add     rsp, 30h
0x140043ada  pop     rbx
0x140043adb  retn
```
