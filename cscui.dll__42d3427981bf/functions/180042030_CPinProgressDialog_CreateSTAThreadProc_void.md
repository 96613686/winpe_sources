# CPinProgressDialog::_CreateSTAThreadProc(void *)

- ea: `0x180042030`
- end: `0x18004213f`
- name: `?_CreateSTAThreadProc@CPinProgressDialog@@CAKPEAX@Z`
- size: `271`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006500`
- `0x180010ff4`
- `0x180042030`
- `0x180043378`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18004207c`
- `SHLWAPI!__imp_SHCreateThread` at `0x18004207c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004208d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004209a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004208d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004209a`

## pseudocode

```c
__int64 __fastcall CPinProgressDialog::_CreateSTAThreadProc(HANDLE *Parameter)
{
  UstCommon::CImpersonator *v2; // rcx

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
  }
  if ( SHCreateThread(CPinProgressDialog::_OpenTaskDialog, Parameter, 0x10u, 0) )
  {
    CPinProgressDialog::_WaitForSyncComplete((CPinProgressDialog *)Parameter);
    CRefCounted::ReleaseReference((CRefCounted *)Parameter);
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
    }
    return 0;
  }
  else
  {
    SetEvent(Parameter[31]);
    SetEvent(Parameter[30]);
    CRefCounted::ReleaseReference((CRefCounted *)Parameter);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)v2 + 2), 50, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
    }
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x180042030  mov     [rsp+arg_0], rbx
0x180042035  push    rsi
0x180042036  sub     rsp, 20h
0x18004203a  mov     rbx, rcx
0x18004203d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042044  lea     rsi, WPP_GLOBAL_Control
0x18004204b  cmp     rcx, rsi
0x18004204e  jz      short loc_18004206B
0x180042050  test    byte ptr [rcx+1Ch], 40h
0x180042054  jz      short loc_18004206B
0x180042056  mov     rcx, [rcx+10h]
0x18004205a  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042061  mov     edx, 30h ; '0'
0x180042066  call    WPP_SF_
0x18004206b  xor     r9d, r9d; pfnCallback
0x18004206e  lea     rcx, ?_OpenTaskDialog@CPinProgressDialog@@CAKPEAX@Z; pfnThreadProc
0x180042075  mov     rdx, rbx; pData
0x180042078  lea     r8d, [r9+10h]; flags
0x18004207c  call    cs:__imp_SHCreateThread
0x180042082  test    eax, eax
0x180042084  jnz     short loc_1800420FB
0x180042086  mov     rcx, [rbx+0F8h]; hEvent
0x18004208d  call    cs:__imp_SetEvent
0x180042093  mov     rcx, [rbx+0F0h]; hEvent
0x18004209a  call    cs:__imp_SetEvent
0x1800420a0  mov     rcx, rbx; this
0x1800420a3  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x1800420a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800420af  cmp     rcx, rsi
0x1800420b2  jz      short loc_1800420F6
0x1800420b4  test    byte ptr [rcx+1Ch], 2
0x1800420b8  jz      short loc_1800420D6
0x1800420ba  mov     rcx, [rcx+10h]
0x1800420be  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800420c5  mov     edx, 31h ; '1'
0x1800420ca  call    WPP_SF_
0x1800420cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800420d6  cmp     rcx, rsi
0x1800420d9  jz      short loc_1800420F6
0x1800420db  test    byte ptr [rcx+1Ch], 40h
0x1800420df  jz      short loc_1800420F6
0x1800420e1  mov     rcx, [rcx+10h]
0x1800420e5  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800420ec  mov     edx, 32h ; '2'
0x1800420f1  call    WPP_SF_
0x1800420f6  or      eax, 0FFFFFFFFh
0x1800420f9  jmp     short loc_180042134
0x1800420fb  mov     rcx, rbx; this
0x1800420fe  call    ?_WaitForSyncComplete@CPinProgressDialog@@AEAAXXZ; CPinProgressDialog::_WaitForSyncComplete(void)
0x180042103  mov     rcx, rbx; this
0x180042106  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18004210b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042112  cmp     rcx, rsi
0x180042115  jz      short loc_180042132
0x180042117  test    byte ptr [rcx+1Ch], 40h
0x18004211b  jz      short loc_180042132
0x18004211d  mov     rcx, [rcx+10h]
0x180042121  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042128  mov     edx, 33h ; '3'
0x18004212d  call    WPP_SF_
0x180042132  xor     eax, eax
0x180042134  mov     rbx, [rsp+28h+arg_0]
0x180042139  add     rsp, 20h
0x18004213d  pop     rsi
0x18004213e  retn
```
