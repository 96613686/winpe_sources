# WaitForDebugger(void)

- ea: `0x18001e7fc`
- end: `0x18001e8f1`
- name: `?WaitForDebugger@@YAXXZ`
- size: `245`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f3c8`

## callees

- `0x180001008`
- `0x180006268`
- `0x18000f144`
- `0x18001e7fc`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18001e8d1`
- `KERNEL32!DebugBreak` at `0x18001e8d1`
- `KERNEL32!IsDebuggerPresent` at `0x18001e8b8`
- `KERNEL32!IsDebuggerPresent` at `0x18001e8b8`
- `KERNEL32!Sleep` at `0x18001e89d`
- `KERNEL32!Sleep` at `0x18001e89d`

## string_xrefs

- `0x18001e859`: `DllMain_WaitForDebugger`

## pseudocode

```c
void WaitForDebugger(void)
{
  const struct _tlgProvider_t *v0; // rax
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // esi
  int v4; // r14d
  int v5; // r15d
  unsigned int v6; // ebx
  DWORD v7; // edi
  int v8; // esi
  int v9; // [rsp+60h] [rbp+8h] BYREF
  const wchar_t *v10; // [rsp+68h] [rbp+10h] BYREF

  v9 = 0;
  wil::reg::get_value_dword_nothrow<unsigned long,0>(
    -2147483646,
    L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
    L"AOMDWaitOnStartup",
    &v9);
  if ( v9 )
  {
    v0 = TlgHelper::Provider();
    if ( *(_DWORD *)v0 > 4u && (*((_BYTE *)v0 + 16) & 1) != 0 && (*((_QWORD *)v0 + 3) & 1LL) == *((_QWORD *)v0 + 3) )
    {
      v10 = L"DllMain_WaitForDebugger";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v0,
        byte_18002AF12,
        v1,
        v2,
        (void **)&v10);
    }
    v3 = 120000;
    v4 = 120000;
    v5 = 120000;
    while ( 1 )
    {
      v6 = v3;
      v7 = v4;
      if ( (unsigned int)v3 > 0x3E8 )
        v7 = 1000;
      Sleep(v7);
      v8 = v5;
      if ( v6 <= 0x3E8 )
        v8 = v4;
      v3 = v8 - v7;
      v4 = v3;
      if ( IsDebuggerPresent() )
        break;
      v5 = v3;
      if ( v3 <= 0 )
        return;
    }
    DebugBreak();
  }
}

```

## disassembly

```asm
0x18001e7fc  mov     [rsp+arg_10], rbx
0x18001e801  push    rsi
0x18001e802  push    rdi
0x18001e803  push    r12
0x18001e805  push    r14
0x18001e807  push    r15
0x18001e809  sub     rsp, 30h
0x18001e80d  and     [rsp+58h+arg_0], 0
0x18001e812  lea     r9, [rsp+58h+arg_0]
0x18001e817  lea     r8, aAomdwaitonstar; "AOMDWaitOnStartup"
0x18001e81e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18001e825  mov     rcx, 0FFFFFFFF80000002h
0x18001e82c  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001e831  cmp     [rsp+58h+arg_0], 0
0x18001e836  jz      loc_18001E8DE
0x18001e83c  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001e841  cmp     dword ptr [rax], 4
0x18001e844  jbe     short loc_18001E87E
0x18001e846  test    byte ptr [rax+10h], 1
0x18001e84a  jz      short loc_18001E87E
0x18001e84c  mov     rcx, [rax+18h]
0x18001e850  and     ecx, 1
0x18001e853  cmp     rcx, [rax+18h]
0x18001e857  jnz     short loc_18001E87E
0x18001e859  lea     rcx, aDllmainWaitfor; "DllMain_WaitForDebugger"
0x18001e860  mov     [rsp+58h+arg_8], rcx
0x18001e865  lea     rcx, [rsp+58h+arg_8]
0x18001e86a  mov     [rsp+58h+var_38], rcx
0x18001e86f  lea     rdx, byte_18002AF12
0x18001e876  mov     rcx, rax
0x18001e879  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001e87e  mov     esi, 1D4C0h
0x18001e883  mov     r14d, esi
0x18001e886  mov     r15d, esi
0x18001e889  mov     r12d, 3E8h
0x18001e88f  mov     ebx, esi
0x18001e891  mov     edi, r14d
0x18001e894  cmp     esi, r12d
0x18001e897  cmova   edi, r12d
0x18001e89b  mov     ecx, edi; dwMilliseconds
0x18001e89d  call    cs:__imp_Sleep
0x18001e8a4  nop     dword ptr [rax+rax+00h]
0x18001e8a9  mov     esi, r15d
0x18001e8ac  cmp     ebx, r12d
0x18001e8af  cmovbe  esi, r14d
0x18001e8b3  sub     esi, edi
0x18001e8b5  mov     r14d, esi
0x18001e8b8  call    cs:__imp_IsDebuggerPresent
0x18001e8bf  nop     dword ptr [rax+rax+00h]
0x18001e8c4  test    eax, eax
0x18001e8c6  jnz     short loc_18001E8D1
0x18001e8c8  mov     r15d, esi
0x18001e8cb  test    esi, esi
0x18001e8cd  jg      short loc_18001E88F
0x18001e8cf  jmp     short loc_18001E8DE
0x18001e8d1  call    cs:__imp_DebugBreak
0x18001e8d8  nop     dword ptr [rax+rax+00h]
0x18001e8dd  nop
0x18001e8de  mov     rbx, [rsp+58h+arg_10]
0x18001e8e3  add     rsp, 30h
0x18001e8e7  pop     r15
0x18001e8e9  pop     r14
0x18001e8eb  pop     r12
0x18001e8ed  pop     rdi
0x18001e8ee  pop     rsi
0x18001e8ef  retn
```
