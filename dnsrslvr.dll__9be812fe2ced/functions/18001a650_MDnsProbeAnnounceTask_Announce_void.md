# MDnsProbeAnnounceTask::Announce(void)

- ea: `0x18001a650`
- end: `0x18001a9bc`
- name: `?Announce@MDnsProbeAnnounceTask@@CAJXZ`
- size: `876`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001a37c`

## callees

- `0x1800100d8`
- `0x180011c24`
- `0x18001a650`
- `0x18001ae5c`
- `0x18001ae98`
- `0x18003ac08`
- `0x18003ae2c`
- `0x180046ec0`
- `0x180047818`
- `0x180086700`
- `0x180086b1c`
- `0x180088044`
- `0x1800888d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a79a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a79a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a7b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a75d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a855`

## pseudocode

```c
__int64 MDnsProbeAnnounceTask::Announce(void)
{
  int v0; // edx
  int v1; // ecx
  int v2; // r8d
  __int64 v3; // rdi
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  char v7; // bl
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  unsigned int v11; // r14d
  DWORD LastError; // ebx
  struct MDnsTree *i; // rax
  MDnsTree *v14; // rsi
  __int64 v16; // rbx
  __int16 v17; // cx
  __int64 v18; // rax
  int v19; // edx
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // [rsp+28h] [rbp-A1h]
  __int64 v23; // [rsp+40h] [rbp-89h] BYREF
  int v24; // [rsp+48h] [rbp-81h]
  __int64 v25; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-71h]
  int v27; // [rsp+60h] [rbp-69h] BYREF
  __int64 v28; // [rsp+68h] [rbp-61h]
  unsigned __int64 v29; // [rsp+70h] [rbp-59h]
  int v30; // [rsp+78h] [rbp-51h]
  int v31; // [rsp+80h] [rbp-49h]
  _BYTE v32[64]; // [rsp+A0h] [rbp-29h] BYREF

  memset_0(v32, 0, sizeof(v32));
  memset_0(&v27, 0, 0x40u);
  v3 = 0;
  v23 = 0;
  v24 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qdSd(v1, v0, v2, (unsigned int)v32, 2, (__int64)&WideCharStr, 1);
  memset_0(v32, 0, sizeof(v32));
  DnsAddr_BuildFromIp4(v32);
  v25 = 767;
  v26 = 0xFB00000000000000uLL;
  v7 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_qdSd(v5, v4, v6, (unsigned int)&v27, 23, (__int64)&WideCharStr, 1);
    v7 = BYTE1(xmmword_1800AB5A0);
  }
  memset_0(&v27, 0, 0x40u);
  if ( (v7 & 8) != 0 )
  {
    WPP_SF_q_IPV6_DD(v9, v8, v10, (unsigned int)&v27, (__int64)&v25, v22, 20);
    v7 = BYTE1(xmmword_1800AB5A0);
  }
  memset_0(&v27, 0, 0x40u);
  v28 = v25;
  v29 = v26;
  v27 = -384565225;
  v30 = 0;
  v31 = 28;
  if ( (v7 & 8) != 0 )
    WPP_SF_(1035, 14, WPP_c1b4b8e4fea931768401a909cc10c664_Traceguids);
  EnterCriticalSection(&g_csMdnsTree);
  v11 = 0;
  while ( 2 )
  {
    LastError = 0;
    if ( v11 < 2 )
    {
      for ( i = MDnsTree::NextLeaf(g_MDnsTree, 0); ; i = MDnsTree::NextLeaf(v14, 0) )
      {
        v14 = i;
        if ( !i )
          break;
        v23 = 0;
        v24 = 0;
        v16 = *((_QWORD *)i + 2);
        if ( v16 )
        {
          BYTE2(v23) = 0x80;
          v17 = 0;
          v18 = v16;
          while ( 1 )
          {
            HIWORD(v23) = v17 + 1;
            *(_DWORD *)(v18 + 20) |= 0x8000u;
            v18 = *(_QWORD *)v18;
            if ( !v18 )
              break;
            v17 = HIWORD(v23);
          }
          Packet_FreeMsgBuf((void *)v3);
          v3 = Dns_BuildPacketInternal((unsigned int)&v23, v19, 0, 255, v16, 0x10000000);
          if ( !v3 )
          {
            LastError = GetLastError();
            goto LABEL_16;
          }
          LastError = 0;
          *(_DWORD *)(v3 + 664) = GetCurrentProcessId();
          *(_WORD *)(v3 + 700) = 0;
          if ( *((_DWORD *)v14 + 14) )
            v20 = MDnsSendMessage(v3, v32);
          else
            v20 = MDnsSendMessageOnAllInterfaces(v3, v32);
          if ( v20 == 1222 )
            goto LABEL_16;
          if ( v20 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_d(1035, 25, WPP_f1363454a052307e4f87df134c372536_Traceguids, v20);
          v21 = *((_DWORD *)v14 + 14) ? MDnsSendMessage(v3, &v27) : MDnsSendMessageOnAllInterfaces(v3, &v27);
          if ( v21 == 1222 )
            goto LABEL_16;
          if ( v21 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_d(1035, 26, WPP_f1363454a052307e4f87df134c372536_Traceguids, v21);
        }
      }
      if ( WaitForSingleObject(MDnsProbeAnnounceTask::s_hProbeAnnounceStop, 0x3E8u) )
      {
        ++v11;
        continue;
      }
      LastError = 1223;
    }
    break;
  }
LABEL_16:
  LeaveCriticalSection(&g_csMdnsTree);
  Packet_FreeMsgBuf((void *)v3);
  return LastError;
}

```

## disassembly

```asm
0x18001a650  push    rbp
0x18001a652  push    rbx
0x18001a653  push    rsi
0x18001a654  push    rdi
0x18001a655  push    r12
0x18001a657  push    r14
0x18001a659  push    r15
0x18001a65b  lea     rbp, [rsp-27h]
0x18001a660  sub     rsp, 0F0h
0x18001a667  mov     rax, cs:__security_cookie
0x18001a66e  xor     rax, rsp
0x18001a671  mov     [rbp+57h+var_40], rax
0x18001a675  mov     esi, 40h ; '@'
0x18001a67a  lea     rcx, [rbp+57h+var_80]; void *
0x18001a67e  mov     r8d, esi; Size
0x18001a681  xor     edx, edx; Val
0x18001a683  call    memset_0
0x18001a688  mov     r8d, esi; Size
0x18001a68b  lea     rcx, [rbp+57h+var_C0]; void *
0x18001a68f  xor     edx, edx; Val
0x18001a691  call    memset_0
0x18001a696  xor     edi, edi
0x18001a698  xor     eax, eax
0x18001a69a  mov     [rsp+120h+var_E0], rax
0x18001a69f  mov     [rsp+120h+var_D8], eax
0x18001a6a3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001a6aa  lea     r14, WideCharStr
0x18001a6b1  jnz     loc_18001A91D
0x18001a6b7  mov     r8, rsi; Size
0x18001a6ba  lea     rcx, [rbp+57h+var_80]; void *
0x18001a6be  xor     edx, edx; Val
0x18001a6c0  call    memset_0
0x18001a6c5  mov     r15d, 0E914h
0x18001a6cb  lea     rcx, [rbp+57h+var_80]; void *
0x18001a6cf  mov     r8d, r15d
0x18001a6d2  mov     edx, 0FB0000E0h
0x18001a6d7  call    DnsAddr_BuildFromIp4
0x18001a6dc  mov     rax, 0FB00000000000000h
0x18001a6e6  mov     [rbp+57h+var_D0], 2FFh
0x18001a6ee  mov     [rbp+57h+var_C8], rax
0x18001a6f2  mov     bl, byte ptr cs:xmmword_1800AB5A0+1
0x18001a6f8  mov     r12d, 17h
0x18001a6fe  test    bl, 8
0x18001a701  jnz     loc_18001A940
0x18001a707  mov     r8, rsi; Size
0x18001a70a  lea     rcx, [rbp+57h+var_C0]; void *
0x18001a70e  xor     edx, edx; Val
0x18001a710  call    memset_0
0x18001a715  test    bl, 8
0x18001a718  jnz     loc_18001A8E0
0x18001a71e  mov     r8, rsi; Size
0x18001a721  lea     rcx, [rbp+57h+var_C0]; void *
0x18001a725  xor     edx, edx; Val
0x18001a727  call    memset_0
0x18001a72c  mov     rax, [rbp+57h+var_D0]
0x18001a730  mov     [rbp+57h+var_B8], rax
0x18001a734  mov     rax, [rbp+57h+var_C8]
0x18001a738  mov     [rbp+57h+var_B0], rax
0x18001a73c  mov     [rbp+57h+var_C0], 0E9140017h
0x18001a743  mov     [rbp+57h+var_A8], edi
0x18001a746  mov     [rbp+57h+var_A0], 1Ch
0x18001a74d  test    bl, 8
0x18001a750  jnz     loc_18001A902
0x18001a756  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a75d  call    cs:__imp_EnterCriticalSection
0x18001a763  xor     r14d, r14d
0x18001a766  mov     r12d, 4C6h
0x18001a76c  xor     ebx, ebx
0x18001a76e  cmp     r14d, 2
0x18001a772  jnb     short loc_18001A7AE
0x18001a774  mov     rcx, cs:?g_MDnsTree@@3PEAVMDnsTree@@EA; this
0x18001a77b  xor     edx, edx; struct MDnsTree *
0x18001a77d  call    ?NextLeaf@MDnsTree@@QEAAPEAV1@PEAV1@@Z; MDnsTree::NextLeaf(MDnsTree *)
0x18001a782  lea     r15d, [rbx+1]
0x18001a786  mov     rsi, rax
0x18001a789  test    rax, rax
0x18001a78c  jnz     short loc_18001A7E3
0x18001a78e  mov     rcx, cs:?s_hProbeAnnounceStop@MDnsProbeAnnounceTask@@0PEAXEA; hHandle
0x18001a795  mov     edx, 3E8h; dwMilliseconds
0x18001a79a  call    cs:__imp_WaitForSingleObject
0x18001a7a0  test    eax, eax
0x18001a7a2  jz      short loc_18001A7A9
0x18001a7a4  inc     r14d
0x18001a7a7  jmp     short loc_18001A76C
0x18001a7a9  mov     ebx, 4C7h
0x18001a7ae  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a7b5  call    cs:__imp_LeaveCriticalSection
0x18001a7bb  mov     rcx, rdi; void *
0x18001a7be  call    Packet_FreeMsgBuf
0x18001a7c3  mov     eax, ebx
0x18001a7c5  mov     rcx, [rbp+57h+var_40]
0x18001a7c9  xor     rcx, rsp; StackCookie
0x18001a7cc  call    __security_check_cookie
0x18001a7d1  add     rsp, 0F0h
0x18001a7d8  pop     r15
0x18001a7da  pop     r14
0x18001a7dc  pop     r12
0x18001a7de  pop     rdi
0x18001a7df  pop     rsi
0x18001a7e0  pop     rbx
0x18001a7e1  pop     rbp
0x18001a7e2  retn
0x18001a7e3  xor     eax, eax
0x18001a7e5  mov     [rsp+120h+var_E0], rax
0x18001a7ea  mov     [rsp+120h+var_D8], eax
0x18001a7ee  mov     rbx, [rsi+10h]
0x18001a7f2  test    rbx, rbx
0x18001a7f5  jz      loc_18001A8B6
0x18001a7fb  mov     byte ptr [rsp+120h+var_E0+2], 80h
0x18001a800  xor     ecx, ecx
0x18001a802  mov     rax, rbx
0x18001a805  add     cx, r15w
0x18001a809  mov     word ptr [rsp+120h+var_E0+6], cx
0x18001a80e  bts     dword ptr [rax+14h], 0Fh
0x18001a813  mov     rax, [rax]
0x18001a816  test    rax, rax
0x18001a819  jz      short loc_18001A822
0x18001a81b  movzx   ecx, word ptr [rsp+120h+var_E0+6]
0x18001a820  jmp     short loc_18001A805
0x18001a822  mov     rcx, rdi; void *
0x18001a825  call    Packet_FreeMsgBuf
0x18001a82a  mov     r9d, 0FFh
0x18001a830  mov     [rsp+120h+var_F8], 10000000h
0x18001a839  xor     r8d, r8d
0x18001a83c  mov     [rsp+120h+var_100], rbx
0x18001a841  lea     rcx, [rsp+120h+var_E0]
0x18001a846  call    Dns_BuildPacketInternal
0x18001a84b  mov     rdi, rax
0x18001a84e  test    rax, rax
0x18001a851  jz      short loc_18001A8CC
0x18001a853  xor     ebx, ebx
0x18001a855  call    cs:__imp_GetCurrentProcessId
0x18001a85b  mov     [rdi+298h], eax
0x18001a861  lea     rdx, [rbp+57h+var_80]
0x18001a865  xor     eax, eax
0x18001a867  mov     rcx, rdi
0x18001a86a  mov     [rdi+2BCh], ax
0x18001a871  mov     r8d, [rsi+38h]
0x18001a875  test    r8d, r8d
0x18001a878  jnz     short loc_18001A8D9
0x18001a87a  call    MDnsSendMessageOnAllInterfaces
0x18001a87f  cmp     eax, r12d
0x18001a882  jz      loc_18001A7AE
0x18001a888  test    eax, eax
0x18001a88a  jnz     loc_18001A966
0x18001a890  mov     r8d, [rsi+38h]
0x18001a894  lea     rdx, [rbp+57h+var_C0]
0x18001a898  mov     rcx, rdi
0x18001a89b  test    r8d, r8d
0x18001a89e  jnz     short loc_18001A8C5
0x18001a8a0  call    MDnsSendMessageOnAllInterfaces
0x18001a8a5  cmp     eax, r12d
0x18001a8a8  jz      loc_18001A7AE
0x18001a8ae  test    eax, eax
0x18001a8b0  jnz     loc_18001A991
0x18001a8b6  xor     edx, edx; struct MDnsTree *
0x18001a8b8  mov     rcx, rsi; this
0x18001a8bb  call    ?NextLeaf@MDnsTree@@QEAAPEAV1@PEAV1@@Z; MDnsTree::NextLeaf(MDnsTree *)
0x18001a8c0  jmp     loc_18001A786
0x18001a8c5  call    MDnsSendMessage
0x18001a8ca  jmp     short loc_18001A8A5
0x18001a8cc  call    cs:__imp_GetLastError
0x18001a8d2  mov     ebx, eax
0x18001a8d4  jmp     loc_18001A7AE
0x18001a8d9  call    MDnsSendMessage
0x18001a8de  jmp     short loc_18001A87F
0x18001a8e0  lea     rax, [rbp+57h+var_D0]
0x18001a8e4  mov     [rsp+120h+var_F0], r15d
0x18001a8e9  lea     r9, [rbp+57h+var_C0]
0x18001a8ed  mov     [rsp+120h+var_100], rax
0x18001a8f2  call    WPP_SF_q_IPV6_DD
0x18001a8f7  mov     bl, byte ptr cs:xmmword_1800AB5A0+1
0x18001a8fd  jmp     loc_18001A71E
0x18001a902  mov     edx, 0Eh
0x18001a907  lea     r8, WPP_c1b4b8e4fea931768401a909cc10c664_Traceguids
0x18001a90e  mov     ecx, 40Bh
0x18001a913  call    WPP_SF_
0x18001a918  jmp     loc_18001A756
0x18001a91d  mov     [rsp+120h+var_F0], 1
0x18001a925  lea     r9, [rbp+57h+var_80]
0x18001a929  mov     [rsp+120h+var_F8], r14
0x18001a92e  mov     dword ptr [rsp+120h+var_100], 2
0x18001a936  call    WPP_SF_qdSd
0x18001a93b  jmp     loc_18001A6B7
0x18001a940  mov     [rsp+120h+var_F0], 1
0x18001a948  lea     r9, [rbp+57h+var_C0]
0x18001a94c  mov     [rsp+120h+var_F8], r14
0x18001a951  mov     dword ptr [rsp+120h+var_100], r12d
0x18001a956  call    WPP_SF_qdSd
0x18001a95b  mov     bl, byte ptr cs:xmmword_1800AB5A0+1
0x18001a961  jmp     loc_18001A707
0x18001a966  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001a96d  jz      loc_18001A890
0x18001a973  mov     edx, 19h
0x18001a978  lea     r8, WPP_f1363454a052307e4f87df134c372536_Traceguids
0x18001a97f  mov     ecx, 40Bh
0x18001a984  mov     r9d, eax
0x18001a987  call    WPP_SF_d
0x18001a98c  jmp     loc_18001A890
0x18001a991  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001a998  jz      loc_18001A8B6
0x18001a99e  mov     edx, 1Ah
0x18001a9a3  lea     r8, WPP_f1363454a052307e4f87df134c372536_Traceguids
0x18001a9aa  mov     ecx, 40Bh
0x18001a9af  mov     r9d, eax
0x18001a9b2  call    WPP_SF_d
0x18001a9b7  jmp     loc_18001A8B6
```
