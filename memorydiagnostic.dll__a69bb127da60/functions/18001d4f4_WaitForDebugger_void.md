# WaitForDebugger(void)

- ea: `0x18001d4f4`
- end: `0x18001d5bc`
- name: `?WaitForDebugger@@YAXXZ`
- size: `200`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e080`

## callees

- `0x180001008`
- `0x180006348`
- `0x18000e7ec`
- `0x18001d4f4`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18001d5a4`
- `KERNEL32!DebugBreak` at `0x18001d5a4`
- `KERNEL32!IsDebuggerPresent` at `0x18001d592`
- `KERNEL32!IsDebuggerPresent` at `0x18001d592`
- `KERNEL32!Sleep` at `0x18001d58c`
- `KERNEL32!Sleep` at `0x18001d58c`

## string_xrefs

- `0x18001d554`: `DllMain_WaitForDebugger`

## pseudocode

```c
void WaitForDebugger(void)
{
  const struct _tlgProvider_t *v0; // rax
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // ebx
  DWORD v4; // edi
  int v5; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v6; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  wil::reg::get_value_dword_nothrow<unsigned long,0>(
    -2147483646,
    L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
    L"AOMDWaitOnStartup",
    &v5);
  if ( v5 )
  {
    v0 = TlgHelper::Provider();
    if ( *(_DWORD *)v0 > 4u && (*((_QWORD *)v0 + 2) & 1) != 0 && (*((_QWORD *)v0 + 3) & 1LL) == *((_QWORD *)v0 + 3) )
    {
      v6 = L"DllMain_WaitForDebugger";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v0,
        (__int64)&word_18002A35E,
        v1,
        v2,
        (int **)&v6);
    }
    v3 = 120000;
    while ( 1 )
    {
      v4 = v3;
      if ( (unsigned int)v3 > 0x3E8 )
        v4 = 1000;
      Sleep(v4);
      if ( IsDebuggerPresent() )
        break;
      v3 -= v4;
      if ( v3 <= 0 )
        return;
    }
    DebugBreak();
  }
}

```

## disassembly

```asm
0x18001d4f4  mov     rax, rsp
0x18001d4f7  mov     [rax+18h], rbx
0x18001d4fb  mov     [rax+20h], rsi
0x18001d4ff  push    rdi
0x18001d500  sub     rsp, 30h
0x18001d504  mov     dword ptr [rax+8], 0
0x18001d50b  lea     r9, [rax+8]
0x18001d50f  lea     r8, aAomdwaitonstar; "AOMDWaitOnStartup"
0x18001d516  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18001d51d  mov     rcx, 0FFFFFFFF80000002h
0x18001d524  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001d529  cmp     [rsp+38h+arg_0], 0
0x18001d52e  jz      short loc_18001D5AB
0x18001d530  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001d535  mov     ecx, [rax]
0x18001d537  cmp     ecx, 4
0x18001d53a  jbe     short loc_18001D579
0x18001d53c  mov     rdx, [rax+18h]
0x18001d540  mov     rcx, [rax+10h]
0x18001d544  test    cl, 1
0x18001d547  jz      short loc_18001D579
0x18001d549  mov     rcx, rdx
0x18001d54c  and     ecx, 1
0x18001d54f  cmp     rcx, rdx
0x18001d552  jnz     short loc_18001D579
0x18001d554  lea     rcx, aDllmainWaitfor; "DllMain_WaitForDebugger"
0x18001d55b  mov     [rsp+38h+arg_8], rcx
0x18001d560  lea     rcx, [rsp+38h+arg_8]
0x18001d565  mov     [rsp+38h+var_18], rcx
0x18001d56a  lea     rdx, word_18002A35E
0x18001d571  mov     rcx, rax
0x18001d574  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001d579  mov     ebx, 1D4C0h
0x18001d57e  mov     esi, 3E8h
0x18001d583  mov     edi, ebx
0x18001d585  cmp     ebx, esi
0x18001d587  cmova   edi, esi
0x18001d58a  mov     ecx, edi; dwMilliseconds
0x18001d58c  call    cs:__imp_Sleep
0x18001d592  call    cs:__imp_IsDebuggerPresent
0x18001d598  test    eax, eax
0x18001d59a  jnz     short loc_18001D5A4
0x18001d59c  sub     ebx, edi
0x18001d59e  test    ebx, ebx
0x18001d5a0  jg      short loc_18001D583
0x18001d5a2  jmp     short loc_18001D5AB
0x18001d5a4  call    cs:__imp_DebugBreak
0x18001d5aa  nop
0x18001d5ab  mov     rbx, [rsp+38h+arg_10]
0x18001d5b0  mov     rsi, [rsp+38h+arg_18]
0x18001d5b5  add     rsp, 30h
0x18001d5b9  pop     rdi
0x18001d5ba  retn
```
