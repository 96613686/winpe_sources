# CValAttributes::Validate(CPacketRadius *)

- ea: `0x180019ff4`
- end: `0x18001a178`
- name: `?Validate@CValAttributes@@QEAAJPEAVCPacketRadius@@@Z`
- size: `388`
- prototype: `int(CValAttributes *__hidden this, struct CPacketRadius *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019900`
- `0x180019fb0`
- `0x18001a1b0`

## callees

- `0x1800094e4`
- `0x180013cd0`
- `0x180019ff4`
- `0x18001d31c`
- `0x18002819c`
- `0x1800283c0`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `iassvcs!IASReportEvent` at `0x18001a126`
- `iassvcs!IASReportEvent` at `0x18001a126`

## string_xrefs

- `0x18001a099`: `Message Authenticator must accompany EAP-Message.`

## pseudocode

```c
__int64 __fastcall CValAttributes::Validate(CValAttributes *this, struct CPacketRadius *a2)
{
  __int64 v3; // rcx
  int v4; // r9d
  int v5; // r8d
  __int64 v6; // rdx
  __int64 v7; // rax
  const unsigned __int16 *ClientName; // rax
  __int64 v9; // rcx
  __int64 v11; // [rsp+28h] [rbp-D0h]
  const unsigned __int16 *v12; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE v13[144]; // [rsp+50h] [rbp-A8h] BYREF

  if ( **((_BYTE **)a2 + 3) != 1 )
    return 0;
  v3 = *((_QWORD *)a2 + 2);
  v4 = 0;
  v5 = 0;
  v6 = v3 + 16LL * *((unsigned int *)a2 + 22);
  if ( v3 == v6 )
    return 0;
  do
  {
    v7 = *(_QWORD *)(v3 + 8);
    if ( *(_DWORD *)(v7 + 8) == 80 )
    {
      v4 = 1;
    }
    else if ( *(_DWORD *)(v7 + 8) == 79 )
    {
      v5 = 1;
    }
    v3 += 16;
  }
  while ( v3 != v6 );
  if ( !v5 || v4 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Message Authenticator must accompany EAP-Message.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bd6b7d6a399730ce2a6e408bbd3e4a28_Traceguids, "NPSRAD");
  }
  memset_0(v13, 0, 0x82u);
  if ( (int)ias_inet_htow(*((SOCKADDR **)a2 + 10), v13) >= 0 )
    ClientName = (const unsigned __int16 *)v13;
  else
    ClientName = CPacketRadius::GetClientName(a2);
  v12 = ClientName;
  IASReportEvent(3221225491LL, 1, 0, &v12, 0);
  CReportEvent::Process(
    v9,
    1,
    **((unsigned __int8 **)a2 + 3),
    *((unsigned __int16 *)a2 + 16),
    *((SOCKADDR **)a2 + 10),
    v11,
    *((_QWORD *)a2 + 3));
  return 3221225495LL;
}

```

## disassembly

```asm
0x180019ff4  mov     [rsp+arg_0], rbx
0x180019ff9  push    rdi
0x180019ffa  sub     rsp, 0F0h
0x18001a001  mov     rax, cs:__security_cookie
0x18001a008  xor     rax, rsp
0x18001a00b  mov     [rsp+0F8h+var_18], rax
0x18001a013  mov     rax, [rdx+18h]
0x18001a017  mov     edi, 1
0x18001a01c  mov     rbx, rdx
0x18001a01f  cmp     [rax], dil
0x18001a022  jnz     loc_18001A155
0x18001a028  mov     rcx, [rdx+10h]
0x18001a02c  xor     r9d, r9d
0x18001a02f  mov     edx, [rdx+58h]
0x18001a032  xor     r8d, r8d
0x18001a035  shl     rdx, 4
0x18001a039  add     rdx, rcx
0x18001a03c  cmp     rcx, rdx
0x18001a03f  jz      loc_18001A155
0x18001a045  mov     rax, [rcx+8]
0x18001a049  cmp     dword ptr [rax+8], 50h ; 'P'
0x18001a04d  jnz     short loc_18001A054
0x18001a04f  mov     r9d, edi
0x18001a052  jmp     short loc_18001A05C
0x18001a054  cmp     dword ptr [rax+8], 4Fh ; 'O'
0x18001a058  cmovz   r8d, edi
0x18001a05c  add     rcx, 10h
0x18001a060  cmp     rcx, rdx
0x18001a063  jnz     short loc_18001A045
0x18001a065  test    r8d, r8d
0x18001a068  jz      loc_18001A155
0x18001a06e  test    r9d, r9d
0x18001a071  jnz     loc_18001A155
0x18001a077  mov     rax, cs:WPP_GLOBAL_Control
0x18001a07e  lea     rcx, WPP_GLOBAL_Control
0x18001a085  cmp     rax, rcx
0x18001a088  jz      short loc_18001A0C8
0x18001a08a  cmp     byte ptr [rax+19h], 2
0x18001a08e  jb      short loc_18001A0C8
0x18001a090  test    dword ptr [rax+1Ch], 100h
0x18001a097  jz      short loc_18001A0C8
0x18001a099  lea     rcx, aMessageAuthent_0; "Message Authenticator must accompany EA"...
0x18001a0a0  call    WppDbgPrint
0x18001a0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0ac  lea     r9, aNpsrad; "NPSRAD"
0x18001a0b3  mov     edx, 0Ah
0x18001a0b8  lea     r8, WPP_bd6b7d6a399730ce2a6e408bbd3e4a28_Traceguids
0x18001a0bf  mov     rcx, [rcx+10h]
0x18001a0c3  call    WPP_SF_s
0x18001a0c8  xor     edx, edx; Val
0x18001a0ca  lea     rcx, [rsp+0F8h+var_A8]; void *
0x18001a0cf  mov     r8d, 82h; Size
0x18001a0d5  call    memset_0
0x18001a0da  mov     rcx, [rbx+50h]; pSockaddr
0x18001a0de  lea     r8, [rsp+0F8h+var_B8]
0x18001a0e3  lea     rdx, [rsp+0F8h+var_A8]; void *
0x18001a0e8  mov     [rsp+0F8h+var_B8], 41h ; 'A'
0x18001a0f1  call    ias_inet_htow
0x18001a0f6  test    eax, eax
0x18001a0f8  jns     short loc_18001A104
0x18001a0fa  mov     rcx, rbx; this
0x18001a0fd  call    ?GetClientName@CPacketRadius@@QEBAPEBGXZ; CPacketRadius::GetClientName(void)
0x18001a102  jmp     short loc_18001A109
0x18001a104  lea     rax, [rsp+0F8h+var_A8]
0x18001a109  lea     r9, [rsp+0F8h+var_B0]
0x18001a10e  mov     [rsp+0F8h+var_B0], rax
0x18001a113  xor     r8d, r8d
0x18001a116  mov     [rsp+0F8h+var_D8], 0
0x18001a11f  mov     edx, edi
0x18001a121  mov     ecx, 0C0000013h
0x18001a126  call    cs:__imp_IASReportEvent
0x18001a12c  mov     rax, [rbx+18h]
0x18001a130  mov     edx, edi
0x18001a132  movzx   r9d, word ptr [rbx+20h]
0x18001a137  mov     [rsp+0F8h+var_C8], rax
0x18001a13c  movzx   r8d, byte ptr [rax]
0x18001a140  mov     rax, [rbx+50h]
0x18001a144  mov     [rsp+0F8h+var_D8], rax
0x18001a149  call    ?Process@CReportEvent@@QEAAXW4_radiuslogtype_@@W4_packettype_@@KPEAUsockaddr@@PEBGPEAX@Z; CReportEvent::Process(_radiuslogtype_,_packettype_,ulong,sockaddr *,ushort const *,void *)
0x18001a14e  mov     eax, 0C0000017h
0x18001a153  jmp     short loc_18001A157
0x18001a155  xor     eax, eax
0x18001a157  mov     rcx, [rsp+0F8h+var_18]
0x18001a15f  xor     rcx, rsp; StackCookie
0x18001a162  call    __security_check_cookie
0x18001a167  mov     rbx, [rsp+0F8h+arg_0]
0x18001a16f  add     rsp, 0F0h
0x18001a176  pop     rdi
0x18001a177  retn
```
