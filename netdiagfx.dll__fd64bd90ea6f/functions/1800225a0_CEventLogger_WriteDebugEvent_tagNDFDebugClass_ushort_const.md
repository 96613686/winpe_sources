# CEventLogger::WriteDebugEvent(tagNDFDebugClass,ushort const *)

- ea: `0x1800225a0`
- end: `0x1800226ba`
- name: `?WriteDebugEvent@CEventLogger@@UEAAJW4tagNDFDebugClass@@PEBG@Z`
- size: `282`
- prototype: `int __high(enum tagNDFDebugClass, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x1800056bc`
- `0x1800225a0`
- `0x18002c840`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18002263d`
- `msvcrt!wcsnlen` at `0x18002263d`
- `ADVAPI32!EventWrite` at `0x180022686`
- `ADVAPI32!EventWrite` at `0x180022686`
- `ADVAPI32!EventEnabled` at `0x180022667`
- `ADVAPI32!EventEnabled` at `0x180022667`

## pseudocode

```c
__int64 __fastcall CEventLogger::WriteDebugEvent(__int64 a1, int a2, const wchar_t *a3)
{
  unsigned int v5; // edi
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  __int64 *v11; // rbx
  size_t v12; // rax
  signed int v13; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v5 = 0;
  if ( !a2 )
  {
    v11 = NDFDiagnosticsDebugEvtDesc;
LABEL_17:
    v12 = wcsnlen(a3, 0x2000u);
    UserData.Ptr = (ULONGLONG)a3;
    UserData.Size = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v12 + 2);
    UserData.Reserved = 0;
    if ( EventEnabled(NETDIAG_EVT_GUID_Context, (PCEVENT_DESCRIPTOR)v11) )
    {
      v13 = EventWrite(NETDIAG_EVT_GUID_Context, (PCEVENT_DESCRIPTOR)v11, 1u, &UserData);
      v5 = v13;
      if ( v13 > 0 )
        return (unsigned __int16)v13 | 0x80070000;
    }
    return v5;
  }
  v6 = a2 - 1;
  if ( !v6 )
  {
    v11 = NDFHypothesisDebugEvtDesc;
    goto LABEL_17;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v11 = NDFRepairDebugEvtDesc;
    goto LABEL_17;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v11 = NDFValidationDebugEvtDesc;
    goto LABEL_17;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v11 = NDFCacheHitDebugEvtDesc;
    goto LABEL_17;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v11 = NDFRegistryDebugEvtDesc;
    goto LABEL_17;
  }
  if ( v10 == 1 )
  {
    v11 = (__int64 *)&NDFUnclassifiedDebugEvtDesc;
    goto LABEL_17;
  }
  return v5;
}

```

## disassembly

```asm
0x1800225a0  mov     [rsp+arg_0], rbx
0x1800225a5  mov     [rsp+arg_8], rsi
0x1800225aa  push    rdi
0x1800225ab  sub     rsp, 40h
0x1800225af  mov     rax, cs:__security_cookie
0x1800225b6  xor     rax, rsp
0x1800225b9  mov     [rsp+48h+var_18], rax
0x1800225be  mov     rsi, r8
0x1800225c1  test    r8, r8
0x1800225c4  jnz     short loc_1800225D0
0x1800225c6  mov     eax, 80070057h
0x1800225cb  jmp     loc_18002269D
0x1800225d0  xor     edi, edi
0x1800225d2  test    edx, edx
0x1800225d4  jz      short loc_18002262E
0x1800225d6  sub     edx, 1
0x1800225d9  jz      short loc_180022625
0x1800225db  sub     edx, 1
0x1800225de  jz      short loc_18002261C
0x1800225e0  sub     edx, 1
0x1800225e3  jz      short loc_180022613
0x1800225e5  sub     edx, 1
0x1800225e8  jz      short loc_18002260A
0x1800225ea  sub     edx, 1
0x1800225ed  jz      short loc_180022601
0x1800225ef  cmp     edx, 1
0x1800225f2  jnz     loc_18002269B
0x1800225f8  lea     rbx, NDFUnclassifiedDebugEvtDesc
0x1800225ff  jmp     short loc_180022635
0x180022601  lea     rbx, NDFRegistryDebugEvtDesc
0x180022608  jmp     short loc_180022635
0x18002260a  lea     rbx, NDFCacheHitDebugEvtDesc
0x180022611  jmp     short loc_180022635
0x180022613  lea     rbx, NDFValidationDebugEvtDesc
0x18002261a  jmp     short loc_180022635
0x18002261c  lea     rbx, NDFRepairDebugEvtDesc
0x180022623  jmp     short loc_180022635
0x180022625  lea     rbx, NDFHypothesisDebugEvtDesc
0x18002262c  jmp     short loc_180022635
0x18002262e  lea     rbx, NDFDiagnosticsDebugEvtDesc
0x180022635  mov     edx, 2000h; MaxCount
0x18002263a  mov     rcx, rsi; Source
0x18002263d  call    cs:__imp_wcsnlen
0x180022643  lea     rcx, ds:2[rax*2]
0x18002264b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180022650  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022657  mov     rdx, rbx; EventDescriptor
0x18002265a  mov     [rsp+48h+UserData.Ptr], rsi
0x18002265f  mov     [rsp+48h+UserData.Size], eax
0x180022663  mov     dword ptr [rsp+48h+UserData.0Ch], edi
0x180022667  call    cs:__imp_EventEnabled
0x18002266d  test    al, al
0x18002266f  jz      short loc_18002269B
0x180022671  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022678  lea     r9, [rsp+48h+UserData]; UserData
0x18002267d  mov     r8d, 1; UserDataCount
0x180022683  mov     rdx, rbx; EventDescriptor
0x180022686  call    cs:__imp_EventWrite
0x18002268c  mov     edi, eax
0x18002268e  test    eax, eax
0x180022690  jle     short loc_18002269B
0x180022692  movzx   edi, ax
0x180022695  or      edi, 80070000h
0x18002269b  mov     eax, edi
0x18002269d  mov     rcx, [rsp+48h+var_18]
0x1800226a2  xor     rcx, rsp; StackCookie
0x1800226a5  call    __security_check_cookie
0x1800226aa  mov     rbx, [rsp+48h+arg_0]
0x1800226af  mov     rsi, [rsp+48h+arg_8]
0x1800226b4  add     rsp, 40h
0x1800226b8  pop     rdi
0x1800226b9  retn
```
