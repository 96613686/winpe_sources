# Update_Send

- ea: `0x18007b344`
- end: `0x18007b93b`
- name: `Update_Send`
- size: `1527`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006bfdc`

## callees

- `0x180019310`
- `0x18001a254`
- `0x18001bd54`
- `0x18001f03c`
- `0x180021d18`
- `0x180027a14`
- `0x18002a0e0`
- `0x18002b050`
- `0x18004edb8`
- `0x180053404`
- `0x1800556e8`
- `0x18005981c`
- `0x18005bd0c`
- `0x18005e084`
- `0x180062f60`
- `0x180063a14`
- `0x1800662b0`
- `0x18006c390`
- `0x18006ccf8`
- `0x18007b344`
- `0x18007bbb8`
- `0x18007c224`
- `0x18007d72c`
- `0x18007f67c`
- `0x180080814`
- `0x180083954`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cd0e8`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800dfcac`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b4f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b4f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007b6dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007b6dd`

## string_xrefs

- `0x18007b3dd`: `Entering Update_Send`

## pseudocode

```c
__int64 __fastcall Update_Send(__int64 a1)
{
  unsigned __int8 v2; // r14
  WCHAR **v3; // r12
  __int64 v4; // r15
  void *v5; // r13
  WCHAR **v6; // rdi
  unsigned int v7; // eax
  unsigned int started; // ebx
  void *v9; // rdi
  WCHAR *v10; // r12
  void *v11; // rax
  char *v12; // rax
  char *v13; // r14
  unsigned int v14; // eax
  unsigned int DnsPolicyConfigInfoPrivate; // eax
  unsigned int EffectiveIPSecPolicyKeys; // eax
  __int64 v17; // r12
  int v18; // edi
  unsigned int v19; // eax
  DWORD TickCount; // eax
  __int64 v21; // rbx
  int IsClear; // eax
  _DWORD *v23; // r12
  __int64 v24; // rcx
  char v25; // r14
  WCHAR *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  _BYTE *v31; // r12
  int v32[2]; // [rsp+20h] [rbp-E0h]
  __int64 MsgBuf; // [rsp+40h] [rbp-C0h]
  LPVOID v34; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v35; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h]
  LPVOID v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h]
  LPVOID v39; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v40; // [rsp+78h] [rbp-88h]
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  int v45; // [rsp+A0h] [rbp-60h]
  __int128 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int128 v48; // [rsp+D0h] [rbp-30h]
  __int128 v49; // [rsp+E0h] [rbp-20h]

  v39 = 0;
  v37 = 0;
  v40 = 0;
  v44 = 0;
  v45 = 0;
  v2 = 0;
  memset_0(&v46, 0, 0x40u);
  lpMem = 0;
  v3 = 0;
  v34 = 0;
  v4 = 0;
  v41 = 0;
  v5 = 0;
  v35 = 0;
  v42 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 11, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids, a1);
  DnsPrint_UpdateBlob("Entering Update_Send", a1);
  v6 = *(WCHAR ***)(a1 + 48);
  if ( !v6 )
  {
    if ( *(_QWORD *)(a1 + 72) )
    {
      v7 = NetInfo_CreateForUpdate(*(void **)(a1 + 56), 1, (__int64)&v34);
      v3 = (WCHAR **)v34;
      started = v7;
      if ( v7 )
        goto LABEL_9;
    }
    v6 = v3;
  }
  if ( !(unsigned int)NetInfo_IsUpdateReady(v6) )
  {
    started = 87;
LABEL_9:
    v9 = 0;
    goto LABEL_54;
  }
  v10 = v6[2];
  v11 = (void *)NetInfo_ConvertToAddrArray(v6, 0, 0);
  lpMem = v11;
  if ( v10 && v11 )
  {
    v43 = v6[14];
    MsgBuf = Packet_AllocateMsgBuf(0xFFFF);
    if ( !MsgBuf )
    {
      started = 14;
      v9 = 0;
      goto LABEL_53;
    }
    LODWORD(v44) = 2621440;
    v12 = (char *)Dns_BuildPacketInternal((unsigned int)&v44, 1, (_DWORD)v10, 6, *(_QWORD *)a1, 0x10000000, 1, 0);
    v40 = v12;
    if ( !v12 )
    {
      v9 = (void *)MsgBuf;
      started = 14;
      goto LABEL_53;
    }
    v38 = MsgBuf;
    v13 = v12;
    AddRefDnsMessage(v12);
    *((_DWORD *)v13 + 166) = GetCurrentProcessId();
    v14 = Send_CreateSendBlob(&v41);
    v4 = v41;
    started = v14;
    if ( v14 )
      goto LABEL_50;
    *(_DWORD *)(v41 + 488) = *((_DWORD *)v13 + 166);
    *(_QWORD *)(v4 + 88) = v13;
    AddRefDnsMessage(v13);
    *(_QWORD *)(v4 + 32) = v6;
    v9 = (void *)MsgBuf;
    *(_QWORD *)(v4 + 168) = *(unsigned int *)(a1 + 8);
    *(_DWORD *)(v4 + 176) = 1;
    *(_QWORD *)(v4 + 552) = MsgBuf;
    *(_QWORD *)(v4 + 160) = MsgBuf;
    if ( (*(_DWORD *)(a1 + 8) & 0x10000) != 0 && !(unsigned int)IsDirectAccessPreferLocal() )
    {
      DnsPolicyConfigInfoPrivate = FindDnsPolicyConfigInfoPrivate(v10, 0, (LPVOID *)&v35);
      started = DnsPolicyConfigInfoPrivate;
      if ( DnsPolicyConfigInfoPrivate && DnsPolicyConfigInfoPrivate != 4312 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 12, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids, DnsPolicyConfigInfoPrivate);
        v5 = v35;
        goto LABEL_51;
      }
      v5 = v35;
      if ( v35 )
      {
        if ( v35[6] )
        {
          EffectiveIPSecPolicyKeys = GetEffectiveIPSecPolicyKeys(1, v35, &v42, &v35);
          started = EffectiveIPSecPolicyKeys;
          if ( EffectiveIPSecPolicyKeys )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_d(1035, 13, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids, EffectiveIPSecPolicyKeys);
            goto LABEL_51;
          }
        }
      }
      *((_QWORD *)v13 + 26) = v42;
    }
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
    {
      v23 = lpMem;
    }
    else
    {
      started = DnsSendAndRecvSync((PVOID)v4);
      if ( *(_QWORD *)(v4 + 552) )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_qq(
            1035,
            14,
            (unsigned int)WPP_3a17ed7899f637130104fdb043d451bb_Traceguids,
            MsgBuf,
            *(_QWORD *)(v4 + 552));
        v17 = *(_QWORD *)(v4 + 552);
        v38 = v17;
      }
      else
      {
        v17 = MsgBuf;
      }
      if ( !started )
      {
        v18 = *(_BYTE *)(v17 + 703) & 0xF;
        v19 = Dns_MapRcodeToStatus(*(_BYTE *)(v17 + 703) & 0xF);
        started = v19;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_Dd(1035, 15, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids, v19, v18);
      }
      if ( started != 9005 || (*(_BYTE *)(a1 + 8) & 0x10) != 0 )
        goto LABEL_50;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        TickCount = GetTickCount();
        WPP_SF_d(1035, 16, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids, TickCount);
      }
      v21 = v17 + 60;
      IsClear = DnsAddr_IsClear(v17 + 60);
      v23 = lpMem;
      if ( !IsClear )
      {
        memset_0((char *)lpMem + 32, 0, (unsigned __int64)*((unsigned int *)lpMem + 1) << 6);
        v23[1] = 0;
        if ( !(unsigned int)DnsAddrArray_AddAddr(v23, v21, 0, 0) )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF__SOCKADDR_(1035, 17, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids);
          MicrosoftTelemetryAssertTriggeredNoArgs(v24);
          started = 14;
          goto LABEL_50;
        }
      }
    }
    v27 = v43;
    if ( v43 )
    {
      if ( g_fVelocityDisableInternalExports || (started = Dns_StartSecurity(0)) == 0 )
      {
        v28 = *(_QWORD *)(a1 + 24);
        if ( v28 )
          v29 = *(_QWORD *)(v28 + 8);
        else
          v29 = 0;
        *(_QWORD *)v32 = v27;
        v9 = (void *)MsgBuf;
        v30 = DnsDoSecureUpdate(v13, MsgBuf, *(unsigned int *)(a1 + 8), v23, *(_QWORD *)v32, v29, &v39, &v37);
        v31 = v37;
        started = v30;
        if ( !v30 )
          started = Dns_MapRcodeToStatus(*((_BYTE *)v37 + 703) & 0xF);
        if ( v39 )
        {
          v46 = *(_OWORD *)((char *)v39 + 60);
          v47 = *(_OWORD *)((char *)v39 + 76);
          v48 = *(_OWORD *)((char *)v39 + 92);
          v49 = *(_OWORD *)((char *)v39 + 108);
          v25 = v31[703];
          goto LABEL_52;
        }
LABEL_51:
        v46 = *(_OWORD *)(v13 + 60);
        v47 = *(_OWORD *)(v13 + 76);
        v48 = *(_OWORD *)(v13 + 92);
        v49 = *(_OWORD *)(v13 + 108);
        v25 = *(_BYTE *)(v38 + 703);
LABEL_52:
        v2 = v25 & 0xF;
        goto LABEL_53;
      }
    }
    else
    {
      started = 87;
    }
LABEL_50:
    v9 = (void *)MsgBuf;
    goto LABEL_51;
  }
  started = 87;
  v9 = 0;
LABEL_53:
  v3 = (WCHAR **)v34;
LABEL_54:
  Update_SaveResults(a1, started, v2, &v46);
  Packet_FreeMsgBuf(v37);
  DeRefDnsMessage(v39);
  Packet_FreeMsgBuf(v9);
  DeRefDnsMessage(v40);
  if ( v5 )
    DereferenceDnsPolicyConfigNode(v5);
  DnsApiFree(lpMem);
  NetInfo_Free(v3);
  if ( v4 )
    *(_QWORD *)(v4 + 32) = 0;
  DeRefSendBlob((LPVOID)v4);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 18, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids, started);
  return started;
}

```

## disassembly

```asm
0x18007b344  push    rbp
0x18007b346  push    rbx
0x18007b347  push    rsi
0x18007b348  push    rdi
0x18007b349  push    r12
0x18007b34b  push    r13
0x18007b34d  push    r14
0x18007b34f  push    r15
0x18007b351  lea     rbp, [rsp-8]
0x18007b356  sub     rsp, 108h
0x18007b35d  mov     rax, cs:__security_cookie
0x18007b364  xor     rax, rsp
0x18007b367  mov     [rbp+40h+var_50], rax
0x18007b36b  xor     ebx, ebx
0x18007b36d  xor     eax, eax
0x18007b36f  mov     rsi, rcx
0x18007b372  mov     [rsp+140h+var_D0], rbx
0x18007b377  xor     edx, edx; Val
0x18007b379  mov     [rsp+140h+var_E0], rbx
0x18007b37e  lea     rcx, [rbp+40h+var_90]; void *
0x18007b382  mov     [rsp+140h+var_C8], rbx
0x18007b387  lea     r8d, [rbx+40h]; Size
0x18007b38b  mov     [rbp+40h+var_A8], rax
0x18007b38f  mov     [rbp+40h+var_A0], eax
0x18007b392  mov     r14b, bl
0x18007b395  call    memset_0
0x18007b39a  mov     [rsp+140h+lpMem], rbx
0x18007b39f  mov     r12d, ebx
0x18007b3a2  mov     [rsp+140h+var_F8], rbx
0x18007b3a7  mov     r15d, ebx
0x18007b3aa  mov     [rbp+40h+var_C0], rbx
0x18007b3ae  mov     r13d, ebx
0x18007b3b1  mov     [rsp+140h+var_F0], rbx
0x18007b3b6  mov     [rbp+40h+var_B8], rbx
0x18007b3ba  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b3c1  jz      short loc_18007B3DA
0x18007b3c3  lea     edx, [rbx+0Bh]
0x18007b3c6  mov     ecx, 40Bh
0x18007b3cb  mov     r9, rsi
0x18007b3ce  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b3d5  call    WPP_SF_q
0x18007b3da  mov     rdx, rsi
0x18007b3dd  lea     rcx, aEnteringUpdate_0; "Entering Update_Send"
0x18007b3e4  call    DnsPrint_UpdateBlob
0x18007b3e9  mov     rdi, [rsi+30h]
0x18007b3ed  test    rdi, rdi
0x18007b3f0  jnz     short loc_18007B428
0x18007b3f2  mov     r8, [rsi+48h]
0x18007b3f6  test    r8, r8
0x18007b3f9  jz      short loc_18007B425
0x18007b3fb  mov     rdx, [rsi+40h]
0x18007b3ff  lea     rax, [rsp+140h+var_F8]
0x18007b404  mov     rcx, [rsi+38h]; Src
0x18007b408  mov     [rsp+140h+var_118], rax; __int64
0x18007b40d  mov     [rsp+140h+var_120], 1; int
0x18007b415  call    NetInfo_CreateForUpdate
0x18007b41a  mov     r12, [rsp+140h+var_F8]
0x18007b41f  mov     ebx, eax
0x18007b421  test    eax, eax
0x18007b423  jnz     short loc_18007B437
0x18007b425  mov     rdi, r12
0x18007b428  mov     rcx, rdi
0x18007b42b  call    NetInfo_IsUpdateReady
0x18007b430  test    eax, eax
0x18007b432  jnz     short loc_18007B43F
0x18007b434  lea     ebx, [rax+57h]
0x18007b437  mov     rdi, r13
0x18007b43a  jmp     loc_18007B7BB
0x18007b43f  mov     r12, [rdi+10h]
0x18007b443  xor     r8d, r8d
0x18007b446  xor     edx, edx
0x18007b448  mov     rcx, rdi
0x18007b44b  call    NetInfo_ConvertToAddrArray
0x18007b450  mov     [rsp+140h+lpMem], rax
0x18007b455  test    r12, r12
0x18007b458  jnz     short loc_18007B467
0x18007b45a  mov     ebx, 57h ; 'W'
0x18007b45f  mov     rdi, r13
0x18007b462  jmp     loc_18007B7B6
0x18007b467  test    rax, rax
0x18007b46a  jz      short loc_18007B45A
0x18007b46c  mov     rax, [rdi+70h]
0x18007b470  mov     ecx, 0FFFFh
0x18007b475  mov     [rbp+40h+var_B0], rax
0x18007b479  call    Packet_AllocateMsgBuf
0x18007b47e  mov     [rsp+140h+var_100], rax
0x18007b483  mov     rbx, rax
0x18007b486  test    rax, rax
0x18007b489  jnz     short loc_18007B496
0x18007b48b  lea     ebx, [rax+0Eh]
0x18007b48e  mov     rdi, rax
0x18007b491  jmp     loc_18007B7B6
0x18007b496  xor     eax, eax
0x18007b498  mov     dword ptr [rbp+40h+var_A8], r13d
0x18007b49c  mov     word ptr [rsp+140h+var_108], ax
0x18007b4a1  mov     r8, r12
0x18007b4a4  mov     byte ptr [rbp+40h+var_A8+2], 28h ; '('
0x18007b4a8  lea     ecx, [rax+1]
0x18007b4ab  mov     dword ptr [rsp+140h+var_110], ecx
0x18007b4af  lea     r9d, [rax+6]
0x18007b4b3  mov     rax, [rsi]
0x18007b4b6  mov     edx, ecx
0x18007b4b8  mov     [rsp+140h+var_118], 10000000h
0x18007b4c1  lea     rcx, [rbp+40h+var_A8]
0x18007b4c5  mov     qword ptr [rsp+140h+var_120], rax
0x18007b4ca  call    Dns_BuildPacketInternal
0x18007b4cf  mov     [rsp+140h+var_C8], rax
0x18007b4d4  test    rax, rax
0x18007b4d7  jnz     short loc_18007B4E6
0x18007b4d9  mov     rdi, [rsp+140h+var_100]
0x18007b4de  lea     ebx, [rax+0Eh]
0x18007b4e1  jmp     loc_18007B7B6
0x18007b4e6  mov     rcx, rax
0x18007b4e9  mov     [rsp+140h+var_D8], rbx
0x18007b4ee  mov     r14, rax
0x18007b4f1  call    AddRefDnsMessage
0x18007b4f6  call    cs:__imp_GetCurrentProcessId
0x18007b4fd  nop     dword ptr [rax+rax+00h]
0x18007b502  lea     rcx, [rbp+40h+var_C0]
0x18007b506  mov     [r14+298h], eax
0x18007b50d  call    Send_CreateSendBlob
0x18007b512  mov     r15, [rbp+40h+var_C0]
0x18007b516  mov     ebx, eax
0x18007b518  test    eax, eax
0x18007b51a  jnz     loc_18007B77D
0x18007b520  mov     eax, [r14+298h]
0x18007b527  mov     rcx, r14
0x18007b52a  mov     [r15+1E8h], eax
0x18007b531  mov     [r15+58h], r14
0x18007b535  call    AddRefDnsMessage
0x18007b53a  mov     [r15+20h], rdi
0x18007b53e  mov     eax, [rsi+8]
0x18007b541  mov     rdi, [rsp+140h+var_100]
0x18007b546  mov     [r15+0A8h], rax
0x18007b54d  mov     dword ptr [r15+0B0h], 1
0x18007b558  mov     [r15+228h], rdi
0x18007b55f  mov     [r15+0A0h], rdi
0x18007b566  test    dword ptr [rsi+8], 10000h
0x18007b56d  jz      loc_18007B624
0x18007b573  call    IsDirectAccessPreferLocal
0x18007b578  test    eax, eax
0x18007b57a  jnz     loc_18007B624
0x18007b580  lea     r8, [rsp+140h+var_F0]
0x18007b585  xor     edx, edx
0x18007b587  mov     rcx, r12; Src
0x18007b58a  call    FindDnsPolicyConfigInfoPrivate
0x18007b58f  mov     ebx, eax
0x18007b591  test    eax, eax
0x18007b593  jz      short loc_18007B5C8
0x18007b595  cmp     eax, 10D8h
0x18007b59a  jz      short loc_18007B5C8
0x18007b59c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b5a3  jz      short loc_18007B5BE
0x18007b5a5  mov     edx, 0Ch
0x18007b5aa  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b5b1  mov     ecx, 40Bh
0x18007b5b6  mov     r9d, eax
0x18007b5b9  call    WPP_SF_d
0x18007b5be  mov     r13, [rsp+140h+var_F0]
0x18007b5c3  jmp     loc_18007B782
0x18007b5c8  mov     r13, [rsp+140h+var_F0]
0x18007b5cd  test    r13, r13
0x18007b5d0  jz      short loc_18007B619
0x18007b5d2  cmp     qword ptr [r13+30h], 0
0x18007b5d7  jz      short loc_18007B619
0x18007b5d9  lea     r9, [rsp+140h+var_F0]
0x18007b5de  mov     rdx, r13
0x18007b5e1  lea     r8, [rbp+40h+var_B8]
0x18007b5e5  mov     ecx, 1
0x18007b5ea  call    GetEffectiveIPSecPolicyKeys
0x18007b5ef  mov     ebx, eax
0x18007b5f1  test    eax, eax
0x18007b5f3  jz      short loc_18007B619
0x18007b5f5  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b5fc  jz      short loc_18007B5C3
0x18007b5fe  mov     edx, 0Dh
0x18007b603  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b60a  mov     ecx, 40Bh
0x18007b60f  mov     r9d, eax
0x18007b612  call    WPP_SF_d
0x18007b617  jmp     short loc_18007B5C3
0x18007b619  mov     rax, [rbp+40h+var_B8]
0x18007b61d  mov     [r14+0D0h], rax
0x18007b624  test    dword ptr [rsi+8], 100h
0x18007b62b  jnz     loc_18007B86C
0x18007b631  mov     rcx, r15
0x18007b634  call    DnsSendAndRecvSync
0x18007b639  mov     ebx, eax
0x18007b63b  mov     rax, [r15+228h]
0x18007b642  test    rax, rax
0x18007b645  jz      short loc_18007B67C
0x18007b647  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b64e  jz      short loc_18007B66E
0x18007b650  mov     edx, 0Eh
0x18007b655  mov     qword ptr [rsp+140h+var_120], rax
0x18007b65a  mov     ecx, 40Bh
0x18007b65f  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b666  mov     r9, rdi
0x18007b669  call    WPP_SF_qq
0x18007b66e  mov     r12, [r15+228h]
0x18007b675  mov     [rsp+140h+var_D8], r12
0x18007b67a  jmp     short loc_18007B67F
0x18007b67c  mov     r12, rdi
0x18007b67f  test    ebx, ebx
0x18007b681  jnz     short loc_18007B6BE
0x18007b683  movzx   edi, byte ptr [r12+2BFh]
0x18007b68c  and     edi, 0Fh
0x18007b68f  mov     ecx, edi
0x18007b691  call    Dns_MapRcodeToStatus
0x18007b696  mov     ebx, eax
0x18007b698  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b69f  jz      short loc_18007B6BE
0x18007b6a1  mov     edx, 0Fh
0x18007b6a6  mov     [rsp+140h+var_120], edi
0x18007b6aa  mov     ecx, 40Bh
0x18007b6af  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b6b6  mov     r9d, eax
0x18007b6b9  call    WPP_SF_Dd
0x18007b6be  cmp     ebx, 232Dh
0x18007b6c4  jnz     loc_18007B77D
0x18007b6ca  test    byte ptr [rsi+8], 10h
0x18007b6ce  jnz     loc_18007B77D
0x18007b6d4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b6db  jz      short loc_18007B702
0x18007b6dd  call    cs:__imp_GetTickCount
0x18007b6e4  nop     dword ptr [rax+rax+00h]
0x18007b6e9  mov     edx, 10h
0x18007b6ee  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b6f5  mov     r9d, eax
0x18007b6f8  mov     ecx, 40Bh
0x18007b6fd  call    WPP_SF_d
0x18007b702  lea     rbx, [r12+3Ch]
0x18007b707  mov     rcx, rbx
0x18007b70a  call    DnsAddr_IsClear
0x18007b70f  mov     r12, [rsp+140h+lpMem]
0x18007b714  test    eax, eax
0x18007b716  jnz     loc_18007B871
0x18007b71c  mov     r8d, [r12+4]
0x18007b721  lea     rcx, [r12+20h]; void *
0x18007b726  shl     r8, 6; Size
0x18007b72a  xor     edx, edx; Val
0x18007b72c  call    memset_0
0x18007b731  xor     r9d, r9d
0x18007b734  mov     dword ptr [r12+4], 0
0x18007b73d  xor     r8d, r8d
0x18007b740  mov     rdx, rbx
0x18007b743  mov     rcx, r12
0x18007b746  call    DnsAddrArray_AddAddr
0x18007b74b  test    eax, eax
0x18007b74d  jnz     loc_18007B871
0x18007b753  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b75a  jz      short loc_18007B773
0x18007b75c  lea     edx, [rax+11h]
0x18007b75f  mov     ecx, 40Bh
0x18007b764  mov     r9, rbx
0x18007b767  lea     r8, WPP_3a17ed7899f637130104fdb043d451bb_Traceguids
0x18007b76e  call    WPP_SF__SOCKADDR_
0x18007b773  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007b778  mov     ebx, 0Eh
0x18007b77d  mov     rdi, [rsp+140h+var_100]
0x18007b782  movups  xmm0, xmmword ptr [r14+3Ch]
0x18007b787  movaps  [rbp+40h+var_90], xmm0
0x18007b78b  movups  xmm1, xmmword ptr [r14+4Ch]
0x18007b790  movaps  [rbp+40h+var_80], xmm1
0x18007b794  movups  xmm0, xmmword ptr [r14+5Ch]
0x18007b799  movaps  [rbp+40h+var_70], xmm0
0x18007b79d  movups  xmm1, xmmword ptr [r14+6Ch]
0x18007b7a2  mov     r14, [rsp+140h+var_D8]
0x18007b7a7  movaps  [rbp+40h+var_60], xmm1
0x18007b7ab  mov     r14b, [r14+2BFh]
0x18007b7b2  and     r14b, 0Fh
0x18007b7b6  mov     r12, [rsp+140h+var_F8]
0x18007b7bb  movzx   r8d, r14b
0x18007b7bf  lea     r9, [rbp+40h+var_90]
0x18007b7c3  mov     edx, ebx
0x18007b7c5  mov     rcx, rsi
0x18007b7c8  call    Update_SaveResults
0x18007b7cd  mov     rcx, [rsp+140h+var_E0]; lpMem
0x18007b7d2  call    Packet_FreeMsgBuf
0x18007b7d7  mov     rcx, [rsp+140h+var_D0]; lpMem
0x18007b7dc  call    DeRefDnsMessage
0x18007b7e1  mov     rcx, rdi; lpMem
0x18007b7e4  call    Packet_FreeMsgBuf
0x18007b7e9  mov     rcx, [rsp+140h+var_C8]; lpMem
0x18007b7ee  call    DeRefDnsMessage
0x18007b7f3  test    r13, r13
0x18007b7f6  jz      short loc_18007B800
0x18007b7f8  mov     rcx, r13; lpMem
0x18007b7fb  call    DereferenceDnsPolicyConfigNode
0x18007b800  mov     rcx, [rsp+140h+lpMem]; lpMem
0x18007b805  call    DnsApiFree
0x18007b80a  mov     rcx, r12; lpMem
0x18007b80d  call    NetInfo_Free
0x18007b812  test    r15, r15
0x18007b815  jz      short loc_18007B81F
0x18007b817  mov     qword ptr [r15+20h], 0
0x18007b81f  mov     rcx, r15; lpMem
0x18007b822  call    DeRefSendBlob
0x18007b827  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007b82e  jz      short loc_18007B849
  ... truncated ...
```
