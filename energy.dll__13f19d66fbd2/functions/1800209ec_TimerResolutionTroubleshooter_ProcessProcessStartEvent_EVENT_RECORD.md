# TimerResolutionTroubleshooter::ProcessProcessStartEvent(_EVENT_RECORD *)

- ea: `0x1800209ec`
- end: `0x180020b0e`
- name: `?ProcessProcessStartEvent@TimerResolutionTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `290`
- prototype: `void __fastcall(TimerResolutionTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001c230`

## callees

- `0x180004e20`
- `0x18000ae78`
- `0x1800209ec`
- `0x180020bcc`
- `0x180020f9c`
- `0x18003bb60`
- `0x18003bf74`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180020a78`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180020a78`

## string_xrefs

- `0x180020a45`: `ProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TimerResolutionTroubleshooter::ProcessProcessStartEvent(
        TimerResolutionTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  PEVENT_RECORD v3; // r10
  __int64 v4; // rbx
  BYTE pBuffer[8]; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v6[3]; // [rsp+48h] [rbp-1h] BYREF
  char *v7; // [rsp+60h] [rbp+17h]
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v9; // [rsp+78h] [rbp+2Fh] BYREF
  __int128 v10; // [rsp+88h] [rbp+3Fh]

  *(_DWORD *)pBuffer = 0;
  v9 = 0;
  v10 = 0;
  std::wstring::_Construct_empty(&v9);
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ProcessId";
  if ( !TdhGetProperty(v3, 0, 0, 1u, &pPropertyData, 4u, pBuffer) )
  {
    std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(v6);
    v7 = (char *)this + 136;
    v4 = *(_QWORD *)std::map<unsigned long,RundownProcess>::_Try_emplace<unsigned long const &,>(
                      (char *)this + 96,
                      &pPropertyData,
                      pBuffer);
    std::vector<ImageMapping>::operator=(v4 + 40, v6);
    *(_QWORD *)(v4 + 64) = v7;
    std::vector<ImageMapping>::_Tidy(v6);
    *((_DWORD *)this + 40) |= 0x80u;
  }
  if ( *((_QWORD *)&v10 + 1) > 7u )
    std::_Deallocate<16>((void *)v9, 2LL * *((_QWORD *)&v10 + 1) + 2);
}

```

## disassembly

```asm
0x1800209ec  mov     [rsp-8+arg_10], rbx
0x1800209f1  mov     [rsp-8+arg_18], rdi
0x1800209f6  push    rbp
0x1800209f7  lea     rbp, [rsp-57h]
0x1800209fc  sub     rsp, 0A0h
0x180020a03  mov     rax, cs:__security_cookie
0x180020a0a  xor     rax, rsp
0x180020a0d  mov     [rbp+57h+var_8], rax
0x180020a11  mov     r10, rdx
0x180020a14  mov     rdi, rcx
0x180020a17  mov     dword ptr [rbp+57h+var_60], 0
0x180020a1e  xorps   xmm0, xmm0
0x180020a21  movups  [rbp+57h+var_28], xmm0
0x180020a25  xorps   xmm1, xmm1
0x180020a28  movdqu  [rbp+57h+var_18], xmm1
0x180020a2d  lea     rcx, [rbp+57h+var_28]
0x180020a31  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180020a36  nop
0x180020a37  mov     [rbp+57h+var_38.Reserved], 0
0x180020a3e  mov     [rbp+57h+var_38.ArrayIndex], 0FFFFFFFFh
0x180020a45  lea     rax, aProcessid; "ProcessId"
0x180020a4c  mov     [rbp+57h+var_38.PropertyName], rax
0x180020a50  lea     rax, [rbp+57h+var_60]
0x180020a54  mov     [rsp+0A0h+pBuffer], rax; pBuffer
0x180020a59  mov     [rsp+0A0h+BufferSize], 4; BufferSize
0x180020a61  lea     rax, [rbp+57h+var_38]
0x180020a65  mov     [rsp+0A0h+pPropertyData], rax; pPropertyData
0x180020a6a  mov     r9d, 1; PropertyDataCount
0x180020a70  xor     r8d, r8d; pTdhContext
0x180020a73  xor     edx, edx; TdhContextCount
0x180020a75  mov     rcx, r10; pEvent
0x180020a78  call    cs:__imp_TdhGetProperty
0x180020a7e  test    eax, eax
0x180020a80  jnz     short loc_180020AD0
0x180020a82  lea     rcx, [rbp+57h+var_58]; void *
0x180020a86  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x180020a8b  lea     rcx, [rdi+88h]
0x180020a92  mov     [rbp+57h+var_40], rcx
0x180020a96  lea     rcx, [rdi+60h]
0x180020a9a  lea     r8, [rbp+57h+var_60]
0x180020a9e  lea     rdx, [rbp+57h+var_38]
0x180020aa2  call    ??$_Try_emplace@AEBK$$V@?$map@KVRundownProcess@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVRundownProcess@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVRundownProcess@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,RundownProcess>::_Try_emplace<ulong const &,>(ulong const &)
0x180020aa7  mov     rbx, [rax]
0x180020aaa  lea     rdx, [rbp+57h+var_58]
0x180020aae  lea     rcx, [rbx+28h]
0x180020ab2  call    ??4?$vector@VImageMapping@@V?$allocator@VImageMapping@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<ImageMapping>::operator=(std::vector<ImageMapping> &&)
0x180020ab7  mov     rax, [rbp+57h+var_40]
0x180020abb  mov     [rbx+40h], rax
0x180020abf  lea     rcx, [rbp+57h+var_58]
0x180020ac3  call    ?_Tidy@?$vector@VImageMapping@@V?$allocator@VImageMapping@@@std@@@std@@AEAAXXZ; std::vector<ImageMapping>::_Tidy(void)
0x180020ac8  bts     dword ptr [rdi+0A0h], 7
0x180020ad0  mov     rdx, qword ptr [rbp+57h+var_18+8]
0x180020ad4  cmp     rdx, 7
0x180020ad8  ja      short loc_180020AFB
0x180020ada  mov     rcx, [rbp+57h+var_8]
0x180020ade  xor     rcx, rsp; StackCookie
0x180020ae1  call    __security_check_cookie
0x180020ae6  lea     r11, [rsp+0A0h+var_s0]
0x180020aee  mov     rbx, [r11+20h]
0x180020af2  mov     rdi, [r11+28h]
0x180020af6  mov     rsp, r11
0x180020af9  pop     rbp
0x180020afa  retn
0x180020afb  lea     rdx, ds:2[rdx*2]
0x180020b03  mov     rcx, qword ptr [rbp+57h+var_28]
0x180020b07  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180020b0c  jmp     short loc_180020ADA
```
