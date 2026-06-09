# QuicListenerClaimConnection

- ea: `0x140003198`
- end: `0x140003340`
- name: `QuicListenerClaimConnection`
- size: `424`
- prototype: `bool __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140003738`

## callees

- `0x140003198`
- `0x140003348`
- `0x14001c638`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003fdf8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000322a`
- `ntoskrnl!_snprintf_s` at `0x14000322a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000325f`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000325f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400031f4`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400031f4`

## pseudocode

```c
bool __fastcall QuicListenerClaimConnection(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rcx
  int v8; // ecx
  int v9; // esi
  char v11; // al
  _DWORD v12[2]; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C0h]
  __int64 v14; // [rsp+40h] [rbp-B8h]
  char DstBuf[128]; // [rsp+50h] [rbp-A8h] BYREF

  *(_BYTE *)(a2 + 250) |= 4u;
  *(_BYTE *)(a2 + 249) |= 0x20u;
  v12[0] = 0;
  v5 = a1[9];
  v12[1] = 0;
  v13 = a3;
  v14 = a2;
  if ( v5 )
    v6 = PsAttachSiloToCurrentThread();
  else
    v6 = -1;
  if ( byte_14005C48E < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[list][%p] Indicating NEW_CONNECTION %p", a1, (const void *)a2);
    McTemplateU0s_EtwWriteTransfer(v7, QuicLogVerbose, DstBuf);
  }
  v9 = QuicListenerIndicateEvent(a1, v12);
  if ( v6 != -1 )
    PsDetachSiloFromCurrentThread(v6);
  LOBYTE(v8) = *(_BYTE *)(a2 + 249) & 2;
  if ( v9 >= 0 )
  {
    if ( !(_BYTE)v8 && !*(_QWORD *)(a2 + 3608) )
    {
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\listener.c",
        699,
        "Connection->State.HandleClosed || Connection->ClientCallbackHandler != ((void *)0)");
      __int2c();
    }
    v11 = *(_BYTE *)(a2 + 249);
    if ( (v11 & 1) == 0 )
      *(_BYTE *)(a2 + 250) |= 0x40u;
    return (v11 & 2) == 0;
  }
  else
  {
    if ( (_BYTE)v8 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\listener.c", 679, "!Connection->State.HandleClosed");
      __int2c();
    }
    *(_BYTE *)(a2 + 249) &= ~0x20u;
    if ( (byte_14005C489 & 0x20) != 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        v8,
        (unsigned int)QuicListenerErrorStatus,
        (_DWORD)a1,
        v9,
        (__int64)"NEW_CONNECTION callback");
    QuicConnCloseLocally(a2, 2, 2);
    return 0;
  }
}

```

## disassembly

```asm
0x140003198  mov     [rsp+arg_18], rbx
0x14000319d  push    rbp
0x14000319e  push    rsi
0x14000319f  push    rdi
0x1400031a0  sub     rsp, 0E0h
0x1400031a7  mov     rax, cs:__security_cookie
0x1400031ae  xor     rax, rsp
0x1400031b1  mov     [rsp+0F8h+var_28], rax
0x1400031b9  or      byte ptr [rdx+0FAh], 4
0x1400031c0  xor     eax, eax
0x1400031c2  or      byte ptr [rdx+0F9h], 20h
0x1400031c9  mov     rbp, rcx
0x1400031cc  and     [rsp+0F8h+var_C8], eax
0x1400031d0  mov     rbx, rdx
0x1400031d3  mov     rcx, [rcx+48h]
0x1400031d7  mov     [rsp+0F8h+var_C4], eax
0x1400031db  and     [rsp+0F8h+var_C4], eax
0x1400031df  mov     [rsp+0F8h+var_C0], r8
0x1400031e4  mov     [rsp+0F8h+var_B8], rdx
0x1400031e9  test    rcx, rcx
0x1400031ec  jnz     short loc_1400031F4
0x1400031ee  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400031f2  jmp     short loc_140003203
0x1400031f4  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400031fb  nop     dword ptr [rax+rax+00h]
0x140003200  mov     rdi, rax
0x140003203  mov     edx, 80h; SizeInBytes
0x140003208  test    cs:byte_14005C48E, dl
0x14000320e  jz      short loc_140003247
0x140003210  mov     [rsp+0F8h+var_D0], rbx
0x140003215  lea     r9, aListPIndicatin; "[list][%p] Indicating NEW_CONNECTION %p"
0x14000321c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140003220  mov     [rsp+0F8h+var_D8], rbp
0x140003225  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14000322a  call    cs:__imp__snprintf_s
0x140003231  nop     dword ptr [rax+rax+00h]
0x140003236  lea     r8, [rsp+0F8h+DstBuf]
0x14000323b  lea     rdx, QuicLogVerbose
0x140003242  call    McTemplateU0s_EtwWriteTransfer
0x140003247  lea     rdx, [rsp+0F8h+var_C8]
0x14000324c  mov     rcx, rbp
0x14000324f  call    QuicListenerIndicateEvent
0x140003254  mov     esi, eax
0x140003256  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000325a  jz      short loc_14000326B
0x14000325c  mov     rcx, rdi
0x14000325f  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140003266  nop     dword ptr [rax+rax+00h]
0x14000326b  mov     cl, [rbx+0F9h]
0x140003271  mov     edi, 2
0x140003276  and     cl, dil
0x140003279  test    esi, esi
0x14000327b  jns     short loc_1400032DD
0x14000327d  test    cl, cl
0x14000327f  jz      short loc_14000329B
0x140003281  lea     r8, aConnectionStat_0; "!Connection->State.HandleClosed"
0x140003288  mov     edx, 2A7h
0x14000328d  lea     rcx, aCW1SMsquicSrcC; "C:\\__w\\1\\s\\msquic\\src\\core\\liste"...
0x140003294  call    CxPlatLogAssert
0x140003299  int     2Ch; Windows NT - assertion failure
0x14000329b  and     byte ptr [rbx+0F9h], 0DFh
0x1400032a2  test    cs:byte_14005C489, 20h
0x1400032a9  jz      short loc_1400032C9
0x1400032ab  lea     rax, aNewConnectionC; "NEW_CONNECTION callback"
0x1400032b2  mov     r9d, esi
0x1400032b5  mov     r8, rbp
0x1400032b8  mov     [rsp+0F8h+var_D8], rax
0x1400032bd  lea     rdx, QuicListenerErrorStatus
0x1400032c4  call    McTemplateU0pqs_EtwWriteTransfer
0x1400032c9  xor     r9d, r9d
0x1400032cc  mov     r8, rdi
0x1400032cf  mov     edx, edi
0x1400032d1  mov     rcx, rbx
0x1400032d4  call    QuicConnCloseLocally
0x1400032d9  xor     al, al
0x1400032db  jmp     short loc_14000331C
0x1400032dd  test    cl, cl
0x1400032df  jnz     short loc_140003305
0x1400032e1  cmp     qword ptr [rbx+0E18h], 0
0x1400032e9  jnz     short loc_140003305
0x1400032eb  lea     r8, aConnectionStat_5; "Connection->State.HandleClosed || Conne"...
0x1400032f2  mov     edx, 2BBh
0x1400032f7  lea     rcx, aCW1SMsquicSrcC; "C:\\__w\\1\\s\\msquic\\src\\core\\liste"...
0x1400032fe  call    CxPlatLogAssert
0x140003303  int     2Ch; Windows NT - assertion failure
0x140003305  mov     al, [rbx+0F9h]
0x14000330b  test    al, 1
0x14000330d  jnz     short loc_140003316
0x14000330f  or      byte ptr [rbx+0FAh], 40h
0x140003316  shr     al, 1
0x140003318  not     al
0x14000331a  and     al, 1
0x14000331c  mov     rcx, [rsp+0F8h+var_28]
0x140003324  xor     rcx, rsp; StackCookie
0x140003327  call    __security_check_cookie
0x14000332c  mov     rbx, [rsp+0F8h+arg_18]
0x140003334  add     rsp, 0E0h
0x14000333b  pop     rdi
0x14000333c  pop     rsi
0x14000333d  pop     rbp
0x14000333e  retn
```
