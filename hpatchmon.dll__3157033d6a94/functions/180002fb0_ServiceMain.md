# ServiceMain

- ea: `0x180002fb0`
- end: `0x180003088`
- name: `ServiceMain`
- size: `216`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180001008`
- `0x1800011cc`
- `0x180002270`
- `0x180002fb0`
- `0x180007400`
- `0x180009a80`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, unsigned __int16 **a2, int a3, int a4)
{
  int v6; // eax
  const char *v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-40h] BYREF
  const char **v9; // [rsp+58h] [rbp-20h]
  __int64 v10; // [rsp+60h] [rbp-18h]

  if ( (unsigned int)dword_18001E048 > 5 )
  {
    v7 = "Entry";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      a1,
      (unsigned int)&dword_180018594,
      a3,
      a4,
      (__int64)&v7);
  }
  v6 = HotpatchMonitor::Initialize((HotpatchMonitor *)&g_Server, a1, a2);
  if ( v6 < 0 && (unsigned int)dword_18001E048 > 5 )
  {
    LODWORD(v7) = v6;
    v10 = 4;
    v9 = &v7;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, word_1800185B2, 0, 0, 3, v8, v7);
  }
  HotpatchMonitor::ServiceMain((HotpatchMonitor *)&g_Server, a1, a2);
}

```

## disassembly

```asm
0x180002fb0  mov     r11, rsp
0x180002fb3  mov     [r11+18h], rbx
0x180002fb7  push    rdi
0x180002fb8  sub     rsp, 70h
0x180002fbc  mov     rax, cs:__security_cookie
0x180002fc3  xor     rax, rsp
0x180002fc6  mov     [rsp+78h+var_10], rax
0x180002fcb  mov     eax, cs:dword_18001E048
0x180002fd1  mov     rdi, rdx
0x180002fd4  mov     ebx, ecx
0x180002fd6  cmp     eax, 5
0x180002fd9  jbe     short loc_180002FFA
0x180002fdb  lea     rax, aEntry; "Entry"
0x180002fe2  mov     [r11-48h], rax
0x180002fe6  lea     rdx, dword_180018594
0x180002fed  lea     rax, [r11-48h]
0x180002ff1  mov     [r11-58h], rax
0x180002ff5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180002ffa  mov     r8, rdi; unsigned __int16 **
0x180002ffd  lea     rcx, ?g_Server@@3VHotpatchMonitor@@A; this
0x180003004  mov     edx, ebx; unsigned int
0x180003006  call    ?Initialize@HotpatchMonitor@@UEAAJKQEAPEAG@Z; HotpatchMonitor::Initialize(ulong,ushort * * const)
0x18000300b  test    eax, eax
0x18000300d  jns     short loc_18000305C
0x18000300f  mov     ecx, cs:dword_18001E048
0x180003015  cmp     ecx, 5
0x180003018  jbe     short loc_18000305C
0x18000301a  mov     dword ptr [rsp+78h+var_48], eax
0x18000301e  lea     rdx, word_1800185B2
0x180003025  lea     rax, [rsp+78h+var_48]
0x18000302a  mov     [rsp+78h+var_18], 4
0x180003033  mov     [rsp+78h+var_20], rax
0x180003038  lea     rcx, dword_18001E048
0x18000303f  lea     rax, [rsp+78h+var_40]
0x180003044  xor     r9d, r9d
0x180003047  mov     [rsp+78h+var_50], rax
0x18000304c  xor     r8d, r8d
0x18000304f  mov     [rsp+78h+var_58], 3
0x180003057  call    _tlgWriteTransfer_EventWriteTransfer
0x18000305c  mov     r8, rdi; unsigned __int16 **
0x18000305f  lea     rcx, ?g_Server@@3VHotpatchMonitor@@A; this
0x180003066  mov     edx, ebx; unsigned int
0x180003068  call    ?ServiceMain@HotpatchMonitor@@UEAAXKQEAPEAG@Z; HotpatchMonitor::ServiceMain(ulong,ushort * * const)
0x18000306d  mov     rcx, [rsp+78h+var_10]
0x180003072  xor     rcx, rsp; StackCookie
0x180003075  call    __security_check_cookie
0x18000307a  mov     rbx, [rsp+78h+arg_10]
0x180003082  add     rsp, 70h
0x180003086  pop     rdi
0x180003087  retn
```
