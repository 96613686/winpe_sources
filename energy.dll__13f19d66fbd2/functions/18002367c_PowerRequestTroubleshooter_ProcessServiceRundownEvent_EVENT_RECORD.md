# PowerRequestTroubleshooter::ProcessServiceRundownEvent(_EVENT_RECORD *)

- ea: `0x18002367c`
- end: `0x18002379a`
- name: `?ProcessServiceRundownEvent@PowerRequestTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `286`
- prototype: `void(PowerRequestTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800235b0`

## callees

- `0x180009658`
- `0x18000b6f0`
- `0x18001be60`
- `0x18001c8cc`
- `0x18002367c`
- `0x18003bb60`
- `0x18003bf74`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180023708`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180023708`

## string_xrefs

- `0x180023719`: `ServiceName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PowerRequestTroubleshooter::ProcessServiceRundownEvent(
        PowerRequestTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  BYTE pBuffer[8]; // [rsp+40h] [rbp-19h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+48h] [rbp-11h] BYREF
  __int128 v6; // [rsp+58h] [rbp-1h] BYREF
  __int128 v7; // [rsp+68h] [rbp+Fh]
  int v8; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE v9[32]; // [rsp+80h] [rbp+27h] BYREF

  v6 = 0;
  v7 = 0;
  std::wstring::_Construct_empty(&v6);
  *(_DWORD *)pBuffer = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"SubProcessTag";
  if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, pBuffer) && !(unsigned int)GetEventProperty(a2) )
  {
    v8 = *(_DWORD *)pBuffer;
    std::wstring::wstring((__int64)v9, &v6);
    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::_Emplace<std::pair<unsigned long,std::wstring>>(
      (char *)this + 24,
      &pPropertyData,
      &v8);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v9);
  }
  if ( *((_QWORD *)&v7 + 1) > 7u )
    std::_Deallocate<16>((void *)v6, 2LL * *((_QWORD *)&v7 + 1) + 2);
}

```

## disassembly

```asm
0x18002367c  mov     [rsp-8+arg_10], rbx
0x180023681  mov     [rsp-8+arg_18], rdi
0x180023686  push    rbp
0x180023687  lea     rbp, [rsp-57h]
0x18002368c  sub     rsp, 0B0h
0x180023693  mov     rax, cs:__security_cookie
0x18002369a  xor     rax, rsp
0x18002369d  mov     [rbp+57h+var_10], rax
0x1800236a1  mov     rbx, rdx
0x1800236a4  mov     rdi, rcx
0x1800236a7  xorps   xmm0, xmm0
0x1800236aa  movups  [rbp+57h+var_58], xmm0
0x1800236ae  xorps   xmm1, xmm1
0x1800236b1  movdqu  [rbp+57h+var_48], xmm1
0x1800236b6  lea     rcx, [rbp+57h+var_58]
0x1800236ba  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800236bf  nop
0x1800236c0  mov     dword ptr [rbp+57h+var_70], 0
0x1800236c7  mov     [rbp+57h+var_68.Reserved], 0
0x1800236ce  mov     [rbp+57h+var_68.ArrayIndex], 0FFFFFFFFh
0x1800236d5  lea     rax, aSubprocesstag; "SubProcessTag"
0x1800236dc  mov     [rbp+57h+var_68.PropertyName], rax
0x1800236e0  lea     rax, [rbp+57h+var_70]
0x1800236e4  mov     [rsp+0B0h+pBuffer], rax; pBuffer
0x1800236e9  mov     [rsp+0B0h+BufferSize], 4; BufferSize
0x1800236f1  lea     rax, [rbp+57h+var_68]
0x1800236f5  mov     [rsp+0B0h+pPropertyData], rax; pPropertyData
0x1800236fa  mov     r9d, 1; PropertyDataCount
0x180023700  xor     r8d, r8d; pTdhContext
0x180023703  xor     edx, edx; TdhContextCount
0x180023705  mov     rcx, rbx; pEvent
0x180023708  call    cs:__imp_TdhGetProperty
0x18002370e  test    eax, eax
0x180023710  jnz     short loc_18002375C
0x180023712  xor     r9d, r9d
0x180023715  lea     r8, [rbp+57h+var_58]
0x180023719  lea     rdx, aServicename; "ServiceName"
0x180023720  mov     rcx, rbx; pEvent
0x180023723  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x180023728  test    eax, eax
0x18002372a  jnz     short loc_18002375C
0x18002372c  mov     eax, dword ptr [rbp+57h+var_70]
0x18002372f  mov     [rbp+57h+var_38], eax
0x180023732  lea     rdx, [rbp+57h+var_58]
0x180023736  lea     rcx, [rbp+57h+var_30]
0x18002373a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002373f  nop
0x180023740  lea     rcx, [rdi+18h]
0x180023744  lea     r8, [rbp+57h+var_38]
0x180023748  lea     rdx, [rbp+57h+var_68]
0x18002374c  call    ??$_Emplace@U?$pair@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::_Emplace<std::pair<ulong,std::wstring>>(std::pair<ulong,std::wstring> &&)
0x180023751  nop
0x180023752  lea     rcx, [rbp+57h+var_30]; void *
0x180023756  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18002375b  nop
0x18002375c  mov     rdx, qword ptr [rbp+57h+var_48+8]
0x180023760  cmp     rdx, 7
0x180023764  ja      short loc_180023787
0x180023766  mov     rcx, [rbp+57h+var_10]
0x18002376a  xor     rcx, rsp; StackCookie
0x18002376d  call    __security_check_cookie
0x180023772  lea     r11, [rsp+0B0h+var_s0]
0x18002377a  mov     rbx, [r11+20h]
0x18002377e  mov     rdi, [r11+28h]
0x180023782  mov     rsp, r11
0x180023785  pop     rbp
0x180023786  retn
0x180023787  lea     rdx, ds:2[rdx*2]
0x18002378f  mov     rcx, qword ptr [rbp+57h+var_58]
0x180023793  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180023798  jmp     short loc_180023766
```
