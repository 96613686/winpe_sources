# CPacketSender::SendPacket(CPacketRadius *)

- ea: `0x1800162d8`
- end: `0x180016560`
- name: `?SendPacket@CPacketSender@@QEAAJPEAVCPacketRadius@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(CPacketSender *__hidden this, struct CPacketRadius *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016e00`

## callees

- `0x1800094e4`
- `0x18000dc54`
- `0x1800126b8`
- `0x1800162d8`
- `0x18001d31c`
- `0x18002bf6c`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `iassvcs!IASReportEvent` at `0x18001652a`
- `iassvcs!IASReportEvent` at `0x18001652a`
- `WS2_32!__imp_ntohs` at `0x180016321`
- `WS2_32!__imp_ntohs` at `0x180016321`
- `WS2_32!__imp_sendto` at `0x180016433`
- `WS2_32!__imp_sendto` at `0x180016433`
- `WS2_32!__imp_WSAGetLastError` at `0x1800164ad`
- `WS2_32!__imp_WSAGetLastError` at `0x1800164ad`

## string_xrefs

- `0x180016470`: `Unable to send out complete Radius packet`

## pseudocode

```c
__int64 __fastcall CPacketSender::SendPacket(CPacketSender *this, struct CPacketRadius *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // r14
  int v5; // r15d
  __int64 v6; // rcx
  int v7; // edi
  int v8; // eax
  int v10[4]; // [rsp+30h] [rbp-B8h] BYREF
  struct sockaddr to; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v12; // [rsp+50h] [rbp-98h]
  __int128 v13; // [rsp+60h] [rbp-88h]
  __int128 v14; // [rsp+70h] [rbp-78h]
  __int128 v15; // [rsp+80h] [rbp-68h]
  __int128 v16; // [rsp+90h] [rbp-58h]
  __int128 v17; // [rsp+A0h] [rbp-48h]
  __int128 v18; // [rsp+B0h] [rbp-38h]

  v3 = 0;
  if ( (unsigned int)CPacketIo::IsProcessingEnabled(this) )
  {
    v4 = *((_QWORD *)a2 + 5);
    v5 = ntohs(*(_WORD *)(v4 + 2));
    memset_0(&to, 0, 0x80u);
    v6 = *((_QWORD *)a2 + 10);
    to = *(struct sockaddr *)v6;
    v12 = *(_OWORD *)(v6 + 16);
    v13 = *(_OWORD *)(v6 + 32);
    v14 = *(_OWORD *)(v6 + 48);
    v15 = *(_OWORD *)(v6 + 64);
    v16 = *(_OWORD *)(v6 + 80);
    v17 = *(_OWORD *)(v6 + 96);
    v18 = *(_OWORD *)(v6 + 112);
    v7 = ConvertToV4MappedAddressIfNeeded(&to);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("ConvertToV4MappedAddressIfNeeded() failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_a886b8b128e33d28608518e1637f7ba5_Traceguids,
          (unsigned int)"NPSRAD",
          v7);
      }
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      else
        return (unsigned int)v7;
    }
    else
    {
      v8 = sendto(*((_QWORD *)a2 + 12), (const char *)v4, v5, 0, &to, 128);
      if ( v8 <= 0 || v8 >= v5 )
      {
        if ( v8 == -1 )
        {
          v10[0] = WSAGetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to send Radius packet due to error:%d");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              (unsigned int)WPP_a886b8b128e33d28608518e1637f7ba5_Traceguids,
              (unsigned int)"NPSRAD",
              v10[0]);
          }
          IASReportEvent(3221225494LL, 0, 4, 0, v10);
          return (unsigned int)-1073741801;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to send out complete Radius packet");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a886b8b128e33d28608518e1637f7ba5_Traceguids, "NPSRAD");
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v3;
}

```

## disassembly

```asm
0x1800162d8  mov     [rsp+arg_10], rbx
0x1800162dd  mov     [rsp+arg_18], rsi
0x1800162e2  push    rdi
0x1800162e3  push    r14
0x1800162e5  push    r15
0x1800162e7  sub     rsp, 0D0h
0x1800162ee  mov     rax, cs:__security_cookie
0x1800162f5  xor     rax, rsp
0x1800162f8  mov     [rsp+0E8h+var_28], rax
0x180016300  mov     rsi, rdx
0x180016303  xor     ebx, ebx
0x180016305  call    ?IsProcessingEnabled@CPacketIo@@IEAAHXZ; CPacketIo::IsProcessingEnabled(void)
0x18001630a  test    eax, eax
0x18001630c  jnz     short loc_180016318
0x18001630e  mov     ebx, 80004005h
0x180016313  jmp     loc_180016535
0x180016318  mov     r14, [rsi+28h]
0x18001631c  movzx   ecx, word ptr [r14+2]; netshort
0x180016321  call    cs:__imp_ntohs
0x180016327  movzx   r15d, ax
0x18001632b  xor     edx, edx; Val
0x18001632d  mov     r8d, 80h; Size
0x180016333  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180016338  call    memset_0
0x18001633d  mov     rcx, [rsi+50h]
0x180016341  movups  xmm0, xmmword ptr [rcx]
0x180016344  movaps  xmmword ptr [rsp+0E8h+var_A8.sa_family], xmm0
0x180016349  movups  xmm1, xmmword ptr [rcx+10h]
0x18001634d  movaps  [rsp+0E8h+var_98], xmm1
0x180016352  movups  xmm0, xmmword ptr [rcx+20h]
0x180016356  movaps  [rsp+0E8h+var_88], xmm0
0x18001635b  movups  xmm1, xmmword ptr [rcx+30h]
0x18001635f  movaps  [rsp+0E8h+var_78], xmm1
0x180016364  movups  xmm0, xmmword ptr [rcx+40h]
0x180016368  movaps  [rsp+0E8h+var_68], xmm0
0x180016370  movups  xmm1, xmmword ptr [rcx+50h]
0x180016374  movaps  [rsp+0E8h+var_58], xmm1
0x18001637c  movups  xmm0, xmmword ptr [rcx+60h]
0x180016380  movaps  [rsp+0E8h+var_48], xmm0
0x180016388  movups  xmm1, xmmword ptr [rcx+70h]
0x18001638c  movaps  [rsp+0E8h+var_38], xmm1
0x180016394  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180016399  call    ConvertToV4MappedAddressIfNeeded
0x18001639e  mov     edi, eax
0x1800163a0  test    eax, eax
0x1800163a2  jz      short loc_180016414
0x1800163a4  lea     rcx, WPP_GLOBAL_Control
0x1800163ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800163b2  cmp     rax, rcx
0x1800163b5  jz      short loc_1800163FB
0x1800163b7  cmp     byte ptr [rax+19h], 2
0x1800163bb  jb      short loc_1800163FB
0x1800163bd  test    dword ptr [rax+1Ch], 100h
0x1800163c4  jz      short loc_1800163FB
0x1800163c6  mov     edx, edi
0x1800163c8  lea     rcx, aConverttov4map_1; "ConvertToV4MappedAddressIfNeeded() fail"...
0x1800163cf  call    WppDbgPrint
0x1800163d4  mov     edx, 0Ah
0x1800163d9  mov     dword ptr [rsp+0E8h+to], edi
0x1800163dd  lea     r9, aNpsrad; "NPSRAD"
0x1800163e4  lea     r8, WPP_a886b8b128e33d28608518e1637f7ba5_Traceguids
0x1800163eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163f2  mov     rcx, [rcx+10h]
0x1800163f6  call    WPP_SF_sd
0x1800163fb  test    edi, edi
0x1800163fd  jg      short loc_180016406
0x1800163ff  mov     ebx, edi
0x180016401  jmp     loc_180016535
0x180016406  movzx   ebx, di
0x180016409  or      ebx, 80070000h
0x18001640f  jmp     loc_180016535
0x180016414  mov     [rsp+0E8h+tolen], 80h; tolen
0x18001641c  lea     rax, [rsp+0E8h+var_A8]
0x180016421  mov     [rsp+0E8h+to], rax; to
0x180016426  xor     r9d, r9d; flags
0x180016429  mov     r8d, r15d; len
0x18001642c  mov     rdx, r14; buf
0x18001642f  mov     rcx, [rsi+60h]; s
0x180016433  call    cs:__imp_sendto
0x180016439  test    eax, eax
0x18001643b  jle     short loc_1800164A4
0x18001643d  cmp     eax, r15d
0x180016440  jge     short loc_1800164A4
0x180016442  lea     rcx, WPP_GLOBAL_Control
0x180016449  mov     rax, cs:WPP_GLOBAL_Control
0x180016450  cmp     rax, rcx
0x180016453  jz      loc_180016535
0x180016459  cmp     byte ptr [rax+19h], 2
0x18001645d  jb      loc_180016535
0x180016463  test    dword ptr [rax+1Ch], 100h
0x18001646a  jz      loc_180016535
0x180016470  lea     rcx, aUnableToSendOu; "Unable to send out complete Radius pack"...
0x180016477  call    WppDbgPrint
0x18001647c  mov     edx, 0Bh
0x180016481  lea     r9, aNpsrad; "NPSRAD"
0x180016488  lea     r8, WPP_a886b8b128e33d28608518e1637f7ba5_Traceguids
0x18001648f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016496  mov     rcx, [rcx+10h]
0x18001649a  call    WPP_SF_s
0x18001649f  jmp     loc_180016535
0x1800164a4  cmp     eax, 0FFFFFFFFh
0x1800164a7  jnz     loc_180016535
0x1800164ad  call    cs:__imp_WSAGetLastError
0x1800164b3  mov     [rsp+0E8h+var_B8], eax
0x1800164b7  lea     rcx, WPP_GLOBAL_Control
0x1800164be  mov     rdx, cs:WPP_GLOBAL_Control
0x1800164c5  cmp     rdx, rcx
0x1800164c8  jz      short loc_180016512
0x1800164ca  cmp     byte ptr [rdx+19h], 2
0x1800164ce  jb      short loc_180016512
0x1800164d0  test    dword ptr [rdx+1Ch], 100h
0x1800164d7  jz      short loc_180016512
0x1800164d9  mov     edx, eax
0x1800164db  lea     rcx, aUnableToSendRa; "Unable to send Radius packet due to err"...
0x1800164e2  call    WppDbgPrint
0x1800164e7  mov     edx, 0Ch
0x1800164ec  mov     eax, [rsp+0E8h+var_B8]
0x1800164f0  mov     dword ptr [rsp+0E8h+to], eax
0x1800164f4  lea     r9, aNpsrad; "NPSRAD"
0x1800164fb  lea     r8, WPP_a886b8b128e33d28608518e1637f7ba5_Traceguids
0x180016502  mov     rcx, cs:WPP_GLOBAL_Control
0x180016509  mov     rcx, [rcx+10h]
0x18001650d  call    WPP_SF_sd
0x180016512  lea     rax, [rsp+0E8h+var_B8]
0x180016517  mov     [rsp+0E8h+to], rax
0x18001651c  xor     r9d, r9d
0x18001651f  xor     edx, edx
0x180016521  mov     ecx, 0C0000016h
0x180016526  lea     r8d, [r9+4]
0x18001652a  call    cs:__imp_IASReportEvent
0x180016530  mov     ebx, 0C0000017h
0x180016535  mov     eax, ebx
0x180016537  mov     rcx, [rsp+0E8h+var_28]
0x18001653f  xor     rcx, rsp; StackCookie
0x180016542  call    __security_check_cookie
0x180016547  lea     r11, [rsp+0E8h+var_18]
0x18001654f  mov     rbx, [r11+30h]
0x180016553  mov     rsi, [r11+38h]
0x180016557  mov     rsp, r11
0x18001655a  pop     r15
0x18001655c  pop     r14
0x18001655e  pop     rdi
0x18001655f  retn
0x18002ea65  push    rbp
0x18002ea67  sub     rsp, 30h
0x18002ea6b  mov     rbp, rdx
0x18002ea6e  add     rsp, 30h
0x18002ea72  pop     rbp
0x18002ea73  retn
```
