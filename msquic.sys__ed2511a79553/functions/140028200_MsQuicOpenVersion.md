# MsQuicOpenVersion

- ea: `0x140028200`
- end: `0x140028543`
- name: `MsQuicOpenVersion`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140023e4c`
- `0x140025700`
- `0x140028200`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003edb4`
- `0x14003ee80`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002827f`
- `ntoskrnl!_snprintf_s` at `0x1400282bf`
- `ntoskrnl!_snprintf_s` at `0x1400284ea`
- `ntoskrnl!_snprintf_s` at `0x14002827f`
- `ntoskrnl!_snprintf_s` at `0x1400282bf`
- `ntoskrnl!_snprintf_s` at `0x1400284ea`
- `ntoskrnl!ExAllocatePool2` at `0x1400282fe`
- `ntoskrnl!ExAllocatePool2` at `0x1400282fe`

## string_xrefs

- `0x140028239`: `Only v2 is supported in MsQuicOpenVersion`
- `0x14002826a`: `[ api] MsQuicOpenVersion, NULL`
- `0x1400282aa`: `[ api] MsQuicOpenVersion`
- `0x1400284d1`: `[ api] MsQuicOpenVersion, status=0x%x`

## pseudocode

```c
__int64 __fastcall MsQuicOpenVersion(__int64 a1, _QWORD *a2)
{
  char v2; // bp
  __int64 v5; // rcx
  int v6; // edi
  __int64 v7; // rcx
  _QWORD *Pool2; // rax
  __int64 v9; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  v2 = 0;
  if ( (_DWORD)a1 == 2 )
  {
    MsQuicLibraryLoad();
    if ( a2 )
    {
      if ( byte_14005C48E < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ api] MsQuicOpenVersion");
        McTemplateU0s_EtwWriteTransfer(v7, QuicLogVerbose, DstBuf);
      }
      v6 = MsQuicAddRef();
      if ( v6 >= 0 )
      {
        v2 = 1;
        Pool2 = (_QWORD *)ExAllocatePool2(66, 272, 942760785);
        if ( Pool2 )
        {
          *Pool2 = MsQuicSetContext;
          Pool2[1] = MsQuicGetContext;
          Pool2[2] = MsQuicSetCallbackHandler;
          Pool2[3] = MsQuicSetParam;
          Pool2[4] = MsQuicGetParam;
          Pool2[5] = &MsQuicRegistrationOpen;
          Pool2[6] = MsQuicRegistrationClose;
          Pool2[7] = MsQuicRegistrationShutdown;
          Pool2[8] = MsQuicConfigurationOpen;
          Pool2[9] = MsQuicConfigurationClose;
          Pool2[10] = MsQuicConfigurationLoadCredential;
          Pool2[11] = MsQuicListenerOpen;
          Pool2[12] = MsQuicListenerClose;
          Pool2[13] = MsQuicListenerStart;
          Pool2[14] = MsQuicListenerStop;
          Pool2[15] = MsQuicConnectionOpen;
          Pool2[31] = MsQuicConnectionOpenInPartition;
          Pool2[16] = MsQuicConnectionClose;
          Pool2[17] = MsQuicConnectionShutdown;
          Pool2[18] = &MsQuicConnectionStart;
          Pool2[19] = MsQuicConnectionSetConfiguration;
          Pool2[20] = &MsQuicConnectionSendResumptionTicket;
          Pool2[29] = MsQuicConnectionResumptionTicketValidationComplete;
          Pool2[30] = MsQuicConnectionCertificateValidationComplete;
          Pool2[21] = MsQuicStreamOpen;
          Pool2[22] = MsQuicStreamClose;
          Pool2[24] = MsQuicStreamShutdown;
          Pool2[23] = MsQuicStreamStart;
          Pool2[25] = MsQuicStreamSend;
          Pool2[26] = MsQuicStreamReceiveComplete;
          Pool2[27] = MsQuicStreamReceiveSetEnabled;
          Pool2[32] = MsQuicStreamProvideReceiveBuffers;
          Pool2[28] = MsQuicDatagramSend;
          Pool2[33] = &MsQuicConnectionPoolCreate;
          *a2 = Pool2;
        }
        else
        {
          v6 = -1073741801;
        }
      }
    }
    else
    {
      if ( byte_14005C48E < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ api] MsQuicOpenVersion, NULL");
        McTemplateU0s_EtwWriteTransfer(v5, QuicLogVerbose, DstBuf);
      }
      v6 = -1073741811;
    }
    if ( byte_14005C48E < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ api] MsQuicOpenVersion, status=0x%x", v6);
      McTemplateU0s_EtwWriteTransfer(v9, QuicLogVerbose, DstBuf);
    }
    if ( v6 < 0 )
    {
      if ( v2 )
        MsQuicRelease();
      MsQuicLibraryUnload();
    }
    return (unsigned int)v6;
  }
  else
  {
    if ( (Microsoft_QuicEnableBits & 4) != 0 )
      McTemplateU0s_EtwWriteTransfer(a1, QuicLibraryError, "Only v2 is supported in MsQuicOpenVersion");
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140028200  mov     [rsp+arg_0], rbp
0x140028205  mov     [rsp+arg_10], rdi
0x14002820a  push    r14
0x14002820c  sub     rsp, 0C0h
0x140028213  mov     rax, cs:__security_cookie
0x14002821a  xor     rax, rsp
0x14002821d  mov     [rsp+0C8h+var_18], rax
0x140028225  xor     bpl, bpl
0x140028228  mov     r14, rdx
0x14002822b  cmp     ecx, 2
0x14002822e  jz      short loc_140028256
0x140028230  test    cs:Microsoft_QuicEnableBits, 4
0x140028237  jz      short loc_14002824C
0x140028239  lea     r8, aOnlyV2IsSuppor; "Only v2 is supported in MsQuicOpenVersi"...
0x140028240  lea     rdx, QuicLibraryError
0x140028247  call    McTemplateU0s_EtwWriteTransfer
0x14002824c  mov     eax, 0C00000BBh
0x140028251  jmp     loc_14002851C
0x140028256  call    MsQuicLibraryLoad
0x14002825b  mov     al, cs:byte_14005C48E
0x140028261  test    r14, r14
0x140028264  jnz     short loc_1400282A6
0x140028266  test    al, al
0x140028268  jns     short loc_14002829C
0x14002826a  lea     r9, aApiMsquicopenv_1; "[ api] MsQuicOpenVersion, NULL"
0x140028271  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028275  mov     edx, 80h; SizeInBytes
0x14002827a  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x14002827f  call    cs:__imp__snprintf_s
0x140028286  nop     dword ptr [rax+rax+00h]
0x14002828b  lea     r8, [rsp+0C8h+DstBuf]
0x140028290  lea     rdx, QuicLogVerbose
0x140028297  call    McTemplateU0s_EtwWriteTransfer
0x14002829c  mov     edi, 0C000000Dh
0x1400282a1  jmp     loc_1400284C7
0x1400282a6  test    al, al
0x1400282a8  jns     short loc_1400282DC
0x1400282aa  lea     r9, aApiMsquicopenv_0; "[ api] MsQuicOpenVersion"
0x1400282b1  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400282b5  mov     edx, 80h; SizeInBytes
0x1400282ba  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x1400282bf  call    cs:__imp__snprintf_s
0x1400282c6  nop     dword ptr [rax+rax+00h]
0x1400282cb  lea     r8, [rsp+0C8h+DstBuf]
0x1400282d0  lea     rdx, QuicLogVerbose
0x1400282d7  call    McTemplateU0s_EtwWriteTransfer
0x1400282dc  call    MsQuicAddRef
0x1400282e1  mov     edi, eax
0x1400282e3  test    eax, eax
0x1400282e5  js      loc_1400284C7
0x1400282eb  mov     edx, 110h
0x1400282f0  mov     ecx, 42h ; 'B'
0x1400282f5  mov     r8d, 38316351h
0x1400282fb  mov     bpl, 1
0x1400282fe  call    cs:__imp_ExAllocatePool2
0x140028305  nop     dword ptr [rax+rax+00h]
0x14002830a  test    rax, rax
0x14002830d  jnz     short loc_140028319
0x14002830f  mov     edi, 0C0000017h
0x140028314  jmp     loc_1400284C7
0x140028319  lea     rcx, MsQuicSetContext
0x140028320  mov     [rax], rcx
0x140028323  lea     rcx, MsQuicGetContext
0x14002832a  mov     [rax+8], rcx
0x14002832e  lea     rcx, MsQuicSetCallbackHandler
0x140028335  mov     [rax+10h], rcx
0x140028339  lea     rcx, MsQuicSetParam
0x140028340  mov     [rax+18h], rcx
0x140028344  lea     rcx, MsQuicGetParam
0x14002834b  mov     [rax+20h], rcx
0x14002834f  lea     rcx, MsQuicRegistrationOpen
0x140028356  mov     [rax+28h], rcx
0x14002835a  lea     rcx, MsQuicRegistrationClose
0x140028361  mov     [rax+30h], rcx
0x140028365  lea     rcx, MsQuicRegistrationShutdown
0x14002836c  mov     [rax+38h], rcx
0x140028370  lea     rcx, MsQuicConfigurationOpen
0x140028377  mov     [rax+40h], rcx
0x14002837b  lea     rcx, MsQuicConfigurationClose
0x140028382  mov     [rax+48h], rcx
0x140028386  lea     rcx, MsQuicConfigurationLoadCredential
0x14002838d  mov     [rax+50h], rcx
0x140028391  lea     rcx, MsQuicListenerOpen
0x140028398  mov     [rax+58h], rcx
0x14002839c  lea     rcx, MsQuicListenerClose
0x1400283a3  mov     [rax+60h], rcx
0x1400283a7  lea     rcx, MsQuicListenerStart
0x1400283ae  mov     [rax+68h], rcx
0x1400283b2  lea     rcx, MsQuicListenerStop
0x1400283b9  mov     [rax+70h], rcx
0x1400283bd  lea     rcx, MsQuicConnectionOpen
0x1400283c4  mov     [rax+78h], rcx
0x1400283c8  lea     rcx, MsQuicConnectionOpenInPartition
0x1400283cf  mov     [rax+0F8h], rcx
0x1400283d6  lea     rcx, MsQuicConnectionClose
0x1400283dd  mov     [rax+80h], rcx
0x1400283e4  lea     rcx, MsQuicConnectionShutdown
0x1400283eb  mov     [rax+88h], rcx
0x1400283f2  lea     rcx, MsQuicConnectionStart
0x1400283f9  mov     [rax+90h], rcx
0x140028400  lea     rcx, MsQuicConnectionSetConfiguration
0x140028407  mov     [rax+98h], rcx
0x14002840e  lea     rcx, MsQuicConnectionSendResumptionTicket
0x140028415  mov     [rax+0A0h], rcx
0x14002841c  lea     rcx, MsQuicConnectionResumptionTicketValidationComplete
0x140028423  mov     [rax+0E8h], rcx
0x14002842a  lea     rcx, MsQuicConnectionCertificateValidationComplete
0x140028431  mov     [rax+0F0h], rcx
0x140028438  lea     rcx, MsQuicStreamOpen
0x14002843f  mov     [rax+0A8h], rcx
0x140028446  lea     rcx, MsQuicStreamClose
0x14002844d  mov     [rax+0B0h], rcx
0x140028454  lea     rcx, MsQuicStreamShutdown
0x14002845b  mov     [rax+0C0h], rcx
0x140028462  lea     rcx, MsQuicStreamStart
0x140028469  mov     [rax+0B8h], rcx
0x140028470  lea     rcx, MsQuicStreamSend
0x140028477  mov     [rax+0C8h], rcx
0x14002847e  lea     rcx, MsQuicStreamReceiveComplete
0x140028485  mov     [rax+0D0h], rcx
0x14002848c  lea     rcx, MsQuicStreamReceiveSetEnabled
0x140028493  mov     [rax+0D8h], rcx
0x14002849a  lea     rcx, MsQuicStreamProvideReceiveBuffers
0x1400284a1  mov     [rax+100h], rcx
0x1400284a8  lea     rcx, MsQuicDatagramSend
0x1400284af  mov     [rax+0E0h], rcx
0x1400284b6  lea     rcx, MsQuicConnectionPoolCreate
0x1400284bd  mov     [rax+108h], rcx
0x1400284c4  mov     [r14], rax
0x1400284c7  mov     al, cs:byte_14005C48E
0x1400284cd  test    al, al
0x1400284cf  jns     short loc_140028507
0x1400284d1  lea     r9, aApiMsquicopenv; "[ api] MsQuicOpenVersion, status=0x%x"
0x1400284d8  mov     [rsp+0C8h+var_A8], edi
0x1400284dc  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400284e0  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x1400284e5  mov     edx, 80h; SizeInBytes
0x1400284ea  call    cs:__imp__snprintf_s
0x1400284f1  nop     dword ptr [rax+rax+00h]
0x1400284f6  lea     r8, [rsp+0C8h+DstBuf]
0x1400284fb  lea     rdx, QuicLogVerbose
0x140028502  call    McTemplateU0s_EtwWriteTransfer
0x140028507  test    edi, edi
0x140028509  jns     short loc_14002851A
0x14002850b  test    bpl, bpl
0x14002850e  jz      short loc_140028515
0x140028510  call    MsQuicRelease
0x140028515  call    MsQuicLibraryUnload
0x14002851a  mov     eax, edi
0x14002851c  mov     rcx, [rsp+0C8h+var_18]
0x140028524  xor     rcx, rsp; StackCookie
0x140028527  call    __security_check_cookie
0x14002852c  lea     r11, [rsp+0C8h+var_8]
0x140028534  mov     rbp, [r11+10h]
0x140028538  mov     rdi, [r11+20h]
0x14002853c  mov     rsp, r11
0x14002853f  pop     r14
0x140028541  retn
```
