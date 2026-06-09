# PROTOCOL_MESSAGING_HANDLER::ExecuteWorkItem(WORK_ITEM const *)

- ea: `0x18002a7e0`
- end: `0x18002aad3`
- name: `?ExecuteWorkItem@PROTOCOL_MESSAGING_HANDLER@@UEAAJPEBVWORK_ITEM@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(PROTOCOL_MESSAGING_HANDLER *__hidden this, const struct WORK_ITEM *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b9ac`
- `0x18001bbac`
- `0x18001bcb8`
- `0x18001c10c`
- `0x18002a58c`
- `0x18002a7e0`
- `0x18002aadc`
- `0x18002af10`
- `0x18002b21c`
- `0x18002c7dc`
- `0x18002c8ec`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18002a83c`
- `iisutil!PuDbgPrint` at `0x18002a9a6`
- `iisutil!PuDbgPrint` at `0x18002aa0e`
- `iisutil!PuDbgPrint` at `0x18002aa90`
- `iisutil!PuDbgPrint` at `0x18002a83c`
- `iisutil!PuDbgPrint` at `0x18002a9a6`
- `iisutil!PuDbgPrint` at `0x18002aa0e`
- `iisutil!PuDbgPrint` at `0x18002aa90`
- `iisutil!PuDbgPrintError` at `0x18002aa54`
- `iisutil!PuDbgPrintError` at `0x18002aa54`

## string_xrefs

- `0x18002a7f4`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002a820`: `PROTOCOL_MESSAGING_HANDLER::ExecuteWorkItem called \n`
- `0x18002a827`: `PROTOCOL_MESSAGING_HANDLER::ExecuteWorkItem`
- `0x18002a9f2`: `PROTOCOL_MESSAGING_HANDLER::PipeConnected called\n`
- `0x18002a9f9`: `PROTOCOL_MESSAGING_HANDLER::PipeConnectedMainThread`
- `0x18002aa3f`: `PROTOCOL_MESSAGING_HANDLER::PipeConnectedMainThread`
- `0x18002aa2d`: `Error deleting protocol pipe info`
- `0x18002aa74`: `MESSAGING_HANDLER::PipeMessageInvalidMainThread called \n`
- `0x18002aa7b`: `PROTOCOL_MESSAGING_HANDLER::PipeMessageInvalidMainThread`
- `0x18002a99a`: `DeRegister Protocol called for %S on PROTOCOL_MESSAGING_HANDLER %p\n`
- `0x18002a972`: `PROTOCOL_MESSAGING_HANDLER::DeRegisterProtocol`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::ExecuteWorkItem(
        PROTOCOL_MESSAGING_HANDLER *this,
        const struct WORK_ITEM *a2)
{
  int v2; // r8d
  __int64 v3; // rsi
  char *v5; // rbx
  unsigned int v7; // r15d
  LA_PROTOCOL *v8; // r14
  _QWORD *i; // rdi
  _QWORD *v10; // rdx
  _QWORD *v11; // rax
  unsigned int v12; // ebx
  LA_PROTOCOL *v13; // rcx
  int v14; // eax

  v2 = g_dwDebugFlags;
  v3 = *((_QWORD *)a2 + 3);
  if ( (g_dwDebugFlags & 0x210000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      971,
      "PROTOCOL_MESSAGING_HANDLER::ExecuteWorkItem",
      "PROTOCOL_MESSAGING_HANDLER::ExecuteWorkItem called \n");
    v2 = g_dwDebugFlags;
  }
  v5 = (char *)this - 8;
  if ( *((_DWORD *)this + 4) == 3 )
    return 0;
  v7 = 0;
  switch ( *(_DWORD *)(v3 + 8) )
  {
    case 1:
      PROTOCOL_MESSAGING_HANDLER::PipeDisconnectedMainThread(
        (PROTOCOL_MESSAGING_HANDLER *)((char *)this - 8),
        (const struct MESSAGING_WORK_ITEM *)v3);
      goto LABEL_43;
    case 2:
      if ( (v2 & 0x210000) != 0 && (v2 & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
          1503,
          "PROTOCOL_MESSAGING_HANDLER::PipeMessageInvalidMainThread",
          "MESSAGING_HANDLER::PipeMessageInvalidMainThread called \n");
LABEL_41:
      PROTOCOL_MESSAGING_HANDLER::HandleBadIPMData((PROTOCOL_MESSAGING_HANDLER *)((char *)this - 8));
      goto LABEL_43;
    case 3:
      if ( (v2 & 0x210000) != 0 && (v2 & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
          1331,
          "PROTOCOL_MESSAGING_HANDLER::PipeConnectedMainThread",
          "PROTOCOL_MESSAGING_HANDLER::PipeConnected called\n");
      v14 = PROTOCOL_MESSAGING_HANDLER::DeletePipeInfo((PROTOCOL_MESSAGING_HANDLER *)((char *)this - 8));
      if ( v14 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
          1341,
          "PROTOCOL_MESSAGING_HANDLER::PipeConnectedMainThread",
          v14,
          "Error deleting protocol pipe info");
      goto LABEL_43;
    case 4:
      PROTOCOL_MESSAGING_HANDLER::RegisterProtocol(
        (PROTOCOL_MESSAGING_HANDLER *)((char *)this - 8),
        (const struct MESSAGING_WORK_ITEM *)v3);
      goto LABEL_43;
    case 5:
      if ( (v2 & 3) != 0 && (v2 & 0x20000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
          3059,
          "PROTOCOL_MESSAGING_HANDLER::DeRegisterProtocol",
          "DeRegister Protocol called for %S on PROTOCOL_MESSAGING_HANDLER %p\n",
          *(const wchar_t **)(*((_QWORD *)v5 + 5) + 152LL),
          (char *)this - 8);
      v13 = (LA_PROTOCOL *)*((_QWORD *)v5 + 5);
      *((_DWORD *)v5 + 12) = 1;
      goto LABEL_31;
    case 6:
      PROTOCOL_MESSAGING_HANDLER::StartQueue(
        (PROTOCOL_MESSAGING_HANDLER *)((char *)this - 8),
        (const struct MESSAGING_WORK_ITEM *)v3);
      goto LABEL_43;
    case 7:
      PROTOCOL_MESSAGING_HANDLER::StopQueue(
        (PROTOCOL_MESSAGING_HANDLER *)((char *)this - 8),
        (const struct MESSAGING_WORK_ITEM *)v3);
      goto LABEL_43;
    case 8:
      v13 = (LA_PROTOCOL *)*((_QWORD *)this + 4);
LABEL_31:
      if ( v13 )
        LA_PROTOCOL::HandleIPMRelease(v13);
      goto LABEL_43;
    case 9:
      if ( *(_DWORD *)(v3 + 24) >= 4u )
      {
        v8 = (LA_PROTOCOL *)*((_QWORD *)v5 + 5);
        for ( i = (_QWORD *)*((_QWORD *)v8 + 46); i != (_QWORD *)((char *)v8 + 368); i = (_QWORD *)*i )
        {
          if ( *((_DWORD *)i - 3) == **(_DWORD **)(v3 + 16) )
          {
            IDENTITY_ACK_DATA::CancelAckTimer((IDENTITY_ACK_DATA *)(i - 7));
            v10 = (_QWORD *)*i;
            if ( *(_QWORD **)(*i + 8LL) != i || (v11 = (_QWORD *)i[1], (_QWORD *)*v11 != i) )
              __fastfail(3u);
            v12 = *((_DWORD *)i - 2);
            *v11 = v10;
            v10[1] = v11;
            *i = 0;
            i[1] = 0;
            IDENTITY_ACK_DATA::Terminate((IDENTITY_ACK_DATA *)(i - 7));
            LA_PROTOCOL::AcknowledgeProtocolPool(v8, v12);
            goto LABEL_43;
          }
        }
        goto LABEL_43;
      }
      goto LABEL_41;
  }
  v7 = -2147024809;
LABEL_43:
  if ( v3 )
    (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
  return v7;
}

```

## disassembly

```asm
0x18002a7e0  push    rbx
0x18002a7e2  push    rbp
0x18002a7e3  push    rsi
0x18002a7e4  push    rdi
0x18002a7e5  push    r14
0x18002a7e7  push    r15
0x18002a7e9  sub     rsp, 48h
0x18002a7ed  mov     r8d, cs:g_dwDebugFlags
0x18002a7f4  lea     rbp, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a7fb  mov     rsi, [rdx+18h]
0x18002a7ff  mov     r14d, 210000h
0x18002a805  test    r14d, r8d
0x18002a808  mov     rdi, rcx
0x18002a80b  setnz   dl
0x18002a80e  test    r8b, 3
0x18002a812  setnz   al
0x18002a815  test    al, dl
0x18002a817  jz      short loc_18002A849
0x18002a819  mov     rcx, cs:g_pDebug
0x18002a820  lea     rax, aProtocolMessag_15; "PROTOCOL_MESSAGING_HANDLER::ExecuteWork"...
0x18002a827  lea     r9, aProtocolMessag_9; "PROTOCOL_MESSAGING_HANDLER::ExecuteWork"...
0x18002a82e  mov     [rsp+78h+var_58], rax
0x18002a833  mov     r8d, 3CBh
0x18002a839  mov     rdx, rbp
0x18002a83c  call    cs:__imp_PuDbgPrint
0x18002a842  mov     r8d, cs:g_dwDebugFlags
0x18002a849  lea     rbx, [rdi-8]
0x18002a84d  cmp     dword ptr [rbx+18h], 3
0x18002a851  jnz     short loc_18002A85A
0x18002a853  xor     eax, eax
0x18002a855  jmp     loc_18002AAC6
0x18002a85a  mov     ecx, [rsi+8]
0x18002a85d  xor     r15d, r15d
0x18002a860  sub     ecx, 1
0x18002a863  jz      loc_18002AAA0
0x18002a869  sub     ecx, 1
0x18002a86c  jz      loc_18002AA5C
0x18002a872  sub     ecx, 1
0x18002a875  jz      loc_18002A9DA
0x18002a87b  sub     ecx, 1
0x18002a87e  jz      loc_18002A9CA
0x18002a884  sub     ecx, 1
0x18002a887  jz      loc_18002A95B
0x18002a88d  sub     ecx, 1
0x18002a890  jz      loc_18002A94B
0x18002a896  sub     ecx, 1
0x18002a899  jz      loc_18002A93B
0x18002a89f  sub     ecx, 1
0x18002a8a2  jz      loc_18002A935
0x18002a8a8  cmp     ecx, 1
0x18002a8ab  jz      short loc_18002A8B8
0x18002a8ad  mov     r15d, 80070057h
0x18002a8b3  jmp     loc_18002AAAB
0x18002a8b8  cmp     dword ptr [rsi+18h], 4
0x18002a8bc  jb      loc_18002AA96
0x18002a8c2  mov     rax, [rsi+10h]
0x18002a8c6  mov     r14, [rbx+28h]
0x18002a8ca  mov     ecx, [rax]
0x18002a8cc  lea     rax, [r14+170h]
0x18002a8d3  mov     rdi, [rax]
0x18002a8d6  jmp     short loc_18002A8E0
0x18002a8d8  cmp     [rdi-0Ch], ecx
0x18002a8db  jz      short loc_18002A8EA
0x18002a8dd  mov     rdi, [rdi]
0x18002a8e0  cmp     rdi, rax
0x18002a8e3  jnz     short loc_18002A8D8
0x18002a8e5  jmp     loc_18002AAAB
0x18002a8ea  lea     rcx, [rdi-38h]; this
0x18002a8ee  call    ?CancelAckTimer@IDENTITY_ACK_DATA@@QEAAJXZ; IDENTITY_ACK_DATA::CancelAckTimer(void)
0x18002a8f3  mov     rdx, [rdi]
0x18002a8f6  cmp     [rdx+8], rdi
0x18002a8fa  jnz     short loc_18002A92E
0x18002a8fc  mov     rax, [rdi+8]
0x18002a900  cmp     [rax], rdi
0x18002a903  jnz     short loc_18002A92E
0x18002a905  mov     ebx, [rdi-8]
0x18002a908  lea     rcx, [rdi-38h]; this
0x18002a90c  mov     [rax], rdx
0x18002a90f  mov     [rdx+8], rax
0x18002a913  mov     [rdi], r15
0x18002a916  mov     [rdi+8], r15
0x18002a91a  call    ?Terminate@IDENTITY_ACK_DATA@@QEAAXXZ; IDENTITY_ACK_DATA::Terminate(void)
0x18002a91f  mov     edx, ebx; unsigned int
0x18002a921  mov     rcx, r14; this
0x18002a924  call    ?AcknowledgeProtocolPool@LA_PROTOCOL@@AEAAXK@Z; LA_PROTOCOL::AcknowledgeProtocolPool(ulong)
0x18002a929  jmp     loc_18002AAAB
0x18002a92e  mov     ecx, 3
0x18002a933  int     29h; Win8: RtlFailFast(ecx)
0x18002a935  mov     rcx, [rdi+20h]
0x18002a939  jmp     short loc_18002A9B7
0x18002a93b  mov     rdx, rsi; struct MESSAGING_WORK_ITEM *
0x18002a93e  mov     rcx, rbx; this
0x18002a941  call    ?StopQueue@PROTOCOL_MESSAGING_HANDLER@@AEAAXPEBVMESSAGING_WORK_ITEM@@@Z; PROTOCOL_MESSAGING_HANDLER::StopQueue(MESSAGING_WORK_ITEM const *)
0x18002a946  jmp     loc_18002AAAB
0x18002a94b  mov     rdx, rsi; struct MESSAGING_WORK_ITEM *
0x18002a94e  mov     rcx, rbx; this
0x18002a951  call    ?StartQueue@PROTOCOL_MESSAGING_HANDLER@@AEAAXPEBVMESSAGING_WORK_ITEM@@@Z; PROTOCOL_MESSAGING_HANDLER::StartQueue(MESSAGING_WORK_ITEM const *)
0x18002a956  jmp     loc_18002AAAB
0x18002a95b  test    r8b, 3
0x18002a95f  setnz   cl
0x18002a962  bt      r8d, 1Dh
0x18002a967  setb    al
0x18002a96a  test    al, cl
0x18002a96c  jz      short loc_18002A9AC
0x18002a96e  mov     rax, [rbx+28h]
0x18002a972  lea     r9, aProtocolMessag_26; "PROTOCOL_MESSAGING_HANDLER::DeRegisterP"...
0x18002a979  mov     rcx, cs:g_pDebug
0x18002a980  mov     r8d, 0BF3h
0x18002a986  mov     [rsp+78h+var_48], rbx
0x18002a98b  mov     rdx, rbp
0x18002a98e  mov     rax, [rax+98h]
0x18002a995  mov     [rsp+78h+var_50], rax
0x18002a99a  lea     rax, aDeregisterProt; "DeRegister Protocol called for %S on PR"...
0x18002a9a1  mov     [rsp+78h+var_58], rax
0x18002a9a6  call    cs:__imp_PuDbgPrint
0x18002a9ac  mov     rcx, [rbx+28h]; this
0x18002a9b0  mov     dword ptr [rbx+30h], 1
0x18002a9b7  test    rcx, rcx
0x18002a9ba  jz      loc_18002AAAB
0x18002a9c0  call    ?HandleIPMRelease@LA_PROTOCOL@@QEAAXXZ; LA_PROTOCOL::HandleIPMRelease(void)
0x18002a9c5  jmp     loc_18002AAAB
0x18002a9ca  mov     rdx, rsi; struct MESSAGING_WORK_ITEM *
0x18002a9cd  mov     rcx, rbx; this
0x18002a9d0  call    ?RegisterProtocol@PROTOCOL_MESSAGING_HANDLER@@AEAAXPEBVMESSAGING_WORK_ITEM@@@Z; PROTOCOL_MESSAGING_HANDLER::RegisterProtocol(MESSAGING_WORK_ITEM const *)
0x18002a9d5  jmp     loc_18002AAAB
0x18002a9da  test    r14d, r8d
0x18002a9dd  setnz   cl
0x18002a9e0  test    r8b, 3
0x18002a9e4  setnz   al
0x18002a9e7  test    al, cl
0x18002a9e9  jz      short loc_18002AA14
0x18002a9eb  mov     rcx, cs:g_pDebug
0x18002a9f2  lea     rax, aProtocolMessag_19; "PROTOCOL_MESSAGING_HANDLER::PipeConnect"...
0x18002a9f9  lea     r9, aProtocolMessag_44; "PROTOCOL_MESSAGING_HANDLER::PipeConnect"...
0x18002aa00  mov     [rsp+78h+var_58], rax
0x18002aa05  mov     r8d, 533h
0x18002aa0b  mov     rdx, rbp
0x18002aa0e  call    cs:__imp_PuDbgPrint
0x18002aa14  mov     rcx, rbx; this
0x18002aa17  call    ?DeletePipeInfo@PROTOCOL_MESSAGING_HANDLER@@AEAAJXZ; PROTOCOL_MESSAGING_HANDLER::DeletePipeInfo(void)
0x18002aa1c  test    eax, eax
0x18002aa1e  jns     loc_18002AAAB
0x18002aa24  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002aa2b  jz      short loc_18002AAAB
0x18002aa2d  lea     rcx, aErrorDeletingP; "Error deleting protocol pipe info"
0x18002aa34  mov     r8d, 53Dh
0x18002aa3a  mov     [rsp+78h+var_50], rcx
0x18002aa3f  lea     r9, aProtocolMessag_44; "PROTOCOL_MESSAGING_HANDLER::PipeConnect"...
0x18002aa46  mov     rcx, cs:g_pDebug
0x18002aa4d  mov     rdx, rbp
0x18002aa50  mov     dword ptr [rsp+78h+var_58], eax
0x18002aa54  call    cs:__imp_PuDbgPrintError
0x18002aa5a  jmp     short loc_18002AAAB
0x18002aa5c  test    r14d, r8d
0x18002aa5f  setnz   cl
0x18002aa62  test    r8b, 3
0x18002aa66  setnz   al
0x18002aa69  test    al, cl
0x18002aa6b  jz      short loc_18002AA96
0x18002aa6d  mov     rcx, cs:g_pDebug
0x18002aa74  lea     rax, aMessagingHandl_0; "MESSAGING_HANDLER::PipeMessageInvalidMa"...
0x18002aa7b  lea     r9, aProtocolMessag_0; "PROTOCOL_MESSAGING_HANDLER::PipeMessage"...
0x18002aa82  mov     [rsp+78h+var_58], rax
0x18002aa87  mov     r8d, 5DFh
0x18002aa8d  mov     rdx, rbp
0x18002aa90  call    cs:__imp_PuDbgPrint
0x18002aa96  mov     rcx, rbx; this
0x18002aa99  call    ?HandleBadIPMData@PROTOCOL_MESSAGING_HANDLER@@AEAAXXZ; PROTOCOL_MESSAGING_HANDLER::HandleBadIPMData(void)
0x18002aa9e  jmp     short loc_18002AAAB
0x18002aaa0  mov     rdx, rsi; struct MESSAGING_WORK_ITEM *
0x18002aaa3  mov     rcx, rbx; this
0x18002aaa6  call    ?PipeDisconnectedMainThread@PROTOCOL_MESSAGING_HANDLER@@AEAAXPEBVMESSAGING_WORK_ITEM@@@Z; PROTOCOL_MESSAGING_HANDLER::PipeDisconnectedMainThread(MESSAGING_WORK_ITEM const *)
0x18002aaab  test    rsi, rsi
0x18002aaae  jz      short loc_18002AAC3
0x18002aab0  mov     r8, [rsi]
0x18002aab3  mov     edx, 1
0x18002aab8  mov     rcx, rsi
0x18002aabb  mov     rax, [r8]
0x18002aabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aac3  mov     eax, r15d
0x18002aac6  add     rsp, 48h
0x18002aaca  pop     r15
0x18002aacc  pop     r14
0x18002aace  pop     rdi
0x18002aacf  pop     rsi
0x18002aad0  pop     rbp
0x18002aad1  pop     rbx
0x18002aad2  retn
```
