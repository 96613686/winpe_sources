# NcbCCResetSignalHelper

- ea: `0x180015164`
- end: `0x1800152c9`
- name: `NcbCCResetSignalHelper`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000723c`

## callees

- `0x18000a160`
- `0x180015164`
- `0x18001d8e0`
- `0x18002063c`
- `0x180020c24`
- `0x180025ec4`

## import_xrefs

- `BrokerLib!BrQueryBrokeredEvents` at `0x1800151c3`
- `BrokerLib!BrQueryBrokeredEvents` at `0x1800151c3`
- `BrokerLib!BrBufferFree` at `0x180015222`
- `BrokerLib!BrBufferFree` at `0x180015222`

## string_xrefs

- `0x1800151de`: `NcbCCResetSignalHelper: BrQueryBrokeredEvents`

## pseudocode

```c
ULONG __fastcall NcbCCResetSignalHelper(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, char a5, char a6)
{
  __int64 v6; // r12
  ULONG result; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  ULONG v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // esi
  ULONG v16; // [rsp+30h] [rbp-61h] BYREF
  __int64 v17; // [rsp+38h] [rbp-59h] BYREF
  ULONG v18; // [rsp+40h] [rbp-51h] BYREF
  __int128 v19; // [rsp+50h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+60h] [rbp-31h] BYREF
  const wchar_t *v21; // [rsp+70h] [rbp-21h]
  __int64 v22; // [rsp+78h] [rbp-19h]
  ULONG *v23; // [rsp+80h] [rbp-11h]
  __int64 v24; // [rsp+88h] [rbp-9h]

  v6 = g_NcbCCResetBroker;
  v16 = 0;
  v17 = 0;
  result = BrQueryBrokeredEvents(g_NcbCCResetBroker, a1, a2, 0, &v16, &v17);
  v12 = result;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v18 = result;
    v22 = 92;
    v21 = L"NcbCCResetSignalHelper: BrQueryBrokeredEvents";
    v24 = 4;
    v23 = &v18;
    result = McGenEventWrite_EventWriteTransfer(v10, (const EVENT_DESCRIPTOR *)NcbApiStatus, v11, 3u, &v20);
  }
  if ( !v12 )
  {
    if ( v16 )
    {
      do
      {
        v19 = *(_OWORD *)(v17 + 16LL * v12);
        if ( (unsigned __int8)AppResurrectionManager::ShouldEventBeFired(g_NcbCCResetAppResurrectionManager, &v19, a4) )
        {
          v15 = 1;
          v19 = *(_OWORD *)(v17 + 16LL * v12);
          NcbCCResetSignalEventId(v14, a4, a5, a6, v6, &v19);
        }
        else
        {
          v15 = 0;
        }
        if ( a4 == 3 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zt_EventWriteTransfer(v14, v13, a2, v15);
        ++v12;
      }
      while ( v12 < v16 );
    }
    return BrBufferFree(v17);
  }
  return result;
}

```

## disassembly

```asm
0x180015164  push    rbp
0x180015166  push    rbx
0x180015167  push    rsi
0x180015168  push    rdi
0x180015169  push    r12
0x18001516b  push    r14
0x18001516d  push    r15
0x18001516f  lea     rbp, [rsp-0Fh]
0x180015174  sub     rsp, 0A0h
0x18001517b  mov     rax, cs:__security_cookie
0x180015182  xor     rax, rsp
0x180015185  mov     [rbp+3Fh+var_40], rax
0x180015189  mov     r12, cs:g_NcbCCResetBroker
0x180015190  lea     rax, [rbp+3Fh+var_98]
0x180015194  mov     [rsp+0D0h+var_A8], rax
0x180015199  mov     r15, rdx
0x18001519c  mov     r8, rdx
0x18001519f  mov     [rbp+3Fh+var_A0], 0
0x1800151a6  lea     rax, [rbp+3Fh+var_A0]
0x1800151aa  mov     [rbp+3Fh+var_98], 0
0x1800151b2  mov     r14d, r9d
0x1800151b5  mov     [rsp+0D0h+var_B0], rax
0x1800151ba  mov     rdx, rcx
0x1800151bd  xor     r9d, r9d
0x1800151c0  mov     rcx, r12
0x1800151c3  call    cs:__imp_BrQueryBrokeredEvents
0x1800151c9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800151d0  mov     ebx, eax
0x1800151d2  jz      short loc_180015215
0x1800151d4  mov     [rbp+3Fh+var_90], eax
0x1800151d7  lea     rdx, NcbApiStatus
0x1800151de  lea     rax, aNcbccresetsign_3; "NcbCCResetSignalHelper: BrQueryBrokered"...
0x1800151e5  mov     [rbp+3Fh+var_58], 5Ch ; '\'
0x1800151ed  mov     [rbp+3Fh+var_60], rax
0x1800151f1  mov     r9d, 3
0x1800151f7  lea     rax, [rbp+3Fh+var_90]
0x1800151fb  mov     [rbp+3Fh+var_48], 4
0x180015203  mov     [rbp+3Fh+var_50], rax
0x180015207  lea     rax, [rbp+3Fh+var_70]
0x18001520b  mov     [rsp+0D0h+var_B0], rax
0x180015210  call    McGenEventWrite_EventWriteTransfer
0x180015215  test    ebx, ebx
0x180015217  jnz     short loc_180015228
0x180015219  cmp     [rbp+3Fh+var_A0], ebx
0x18001521c  ja      short loc_180015246
0x18001521e  mov     rcx, [rbp+3Fh+var_98]
0x180015222  call    cs:__imp_BrBufferFree
0x180015228  mov     rcx, [rbp+3Fh+var_40]
0x18001522c  xor     rcx, rsp; StackCookie
0x18001522f  call    __security_check_cookie
0x180015234  add     rsp, 0A0h
0x18001523b  pop     r15
0x18001523d  pop     r14
0x18001523f  pop     r12
0x180015241  pop     rdi
0x180015242  pop     rsi
0x180015243  pop     rbx
0x180015244  pop     rbp
0x180015245  retn
0x180015246  mov     rax, [rbp+3Fh+var_98]
0x18001524a  lea     rdx, [rbp+3Fh+var_80]
0x18001524e  mov     rcx, cs:g_NcbCCResetAppResurrectionManager
0x180015255  mov     r8d, r14d
0x180015258  mov     edi, ebx
0x18001525a  add     rdi, rdi
0x18001525d  movups  xmm0, xmmword ptr [rax+rdi*8]
0x180015261  movdqu  [rbp+3Fh+var_80], xmm0
0x180015266  call    ?ShouldEventBeFired@AppResurrectionManager@@QEAA_NU_GUID@@W4_CCT_RESET_EVENT_REASON@@@Z; AppResurrectionManager::ShouldEventBeFired(_GUID,_CCT_RESET_EVENT_REASON)
0x18001526b  test    al, al
0x18001526d  jz      short loc_1800152A1
0x18001526f  mov     rax, [rbp+3Fh+var_98]
0x180015273  mov     edx, r14d
0x180015276  mov     r9b, [rbp+3Fh+arg_28]
0x18001527a  mov     esi, 1
0x18001527f  mov     r8b, [rbp+3Fh+arg_20]
0x180015283  movups  xmm0, xmmword ptr [rax+rdi*8]
0x180015287  lea     rax, [rbp+3Fh+var_80]
0x18001528b  mov     [rsp+0D0h+var_A8], rax
0x180015290  movdqu  [rbp+3Fh+var_80], xmm0
0x180015295  mov     [rsp+0D0h+var_B0], r12
0x18001529a  call    NcbCCResetSignalEventId
0x18001529f  jmp     short loc_1800152A3
0x1800152a1  xor     esi, esi
0x1800152a3  cmp     r14d, 3
0x1800152a7  jnz     short loc_1800152BD
0x1800152a9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800152b0  jz      short loc_1800152BD
0x1800152b2  mov     r9d, esi
0x1800152b5  mov     r8, r15
0x1800152b8  call    McTemplateU0zt_EventWriteTransfer
0x1800152bd  inc     ebx
0x1800152bf  cmp     ebx, [rbp+3Fh+var_A0]
0x1800152c2  jb      short loc_180015246
0x1800152c4  jmp     loc_18001521E
```
