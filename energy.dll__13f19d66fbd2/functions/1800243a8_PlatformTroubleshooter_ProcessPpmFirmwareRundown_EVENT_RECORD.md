# PlatformTroubleshooter::ProcessPpmFirmwareRundown(_EVENT_RECORD *)

- ea: `0x1800243a8`
- end: `0x1800245fc`
- name: `?ProcessPpmFirmwareRundown@PlatformTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `596`
- prototype: `void(PlatformTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024020`

## callees

- `0x1800243a8`
- `0x180024604`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180024424`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180024466`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800244ab`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800244f0`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180024535`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180024424`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180024466`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800244ab`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x1800244f0`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180024535`

## string_xrefs

- `0x180024474`: `FeaturesAccessed`

## pseudocode

```c
void __fastcall PlatformTroubleshooter::ProcessPpmFirmwareRundown(
        PlatformTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  BYTE v9[4]; // [rsp+40h] [rbp-30h] BYREF
  int v10; // [rsp+44h] [rbp-2Ch] BYREF
  BYTE pBuffer[2]; // [rsp+48h] [rbp-28h] BYREF
  BYTE v12[4]; // [rsp+4Ch] [rbp-24h] BYREF
  BYTE v13[4]; // [rsp+50h] [rbp-20h] BYREF
  BYTE v14[4]; // [rsp+54h] [rbp-1Ch] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+58h] [rbp-18h] BYREF

  pPropertyData.PropertyName = (ULONGLONG)L"Group";
  *(_DWORD *)v12 = 0;
  *(_DWORD *)v13 = 0;
  *(_DWORD *)v14 = 0;
  *(_WORD *)pBuffer = 0;
  v9[0] = 0;
  v10 = 0;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 2u, pBuffer) )
  {
    pPropertyData.Reserved = 0;
    pPropertyData.PropertyName = (ULONGLONG)L"Number";
    pPropertyData.ArrayIndex = -1;
    if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 1u, v9) )
    {
      pPropertyData.Reserved = 0;
      pPropertyData.PropertyName = (ULONGLONG)L"FeaturesAccessed";
      pPropertyData.ArrayIndex = -1;
      if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v12) )
      {
        pPropertyData.Reserved = 0;
        pPropertyData.PropertyName = (ULONGLONG)L"FeaturesPresent";
        pPropertyData.ArrayIndex = -1;
        if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v13) )
        {
          pPropertyData.Reserved = 0;
          pPropertyData.PropertyName = (ULONGLONG)L"FeaturesValidated";
          pPropertyData.ArrayIndex = -1;
          if ( !TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v14) )
          {
            v4 = *(unsigned __int16 *)pBuffer;
            v10 = v9[0] + 255 * *(unsigned __int16 *)pBuffer;
            *(_DWORD *)(*(_QWORD *)std::map<unsigned long,Processor>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 112,
                                     &pPropertyData,
                                     &v10)
                      + 32LL) = v4;
            v5 = v9[0];
            *(_DWORD *)(*(_QWORD *)std::map<unsigned long,Processor>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 112,
                                     &pPropertyData,
                                     &v10)
                      + 36LL) = v5;
            v6 = *(_DWORD *)v12;
            *(_DWORD *)(*(_QWORD *)std::map<unsigned long,Processor>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 112,
                                     &pPropertyData,
                                     &v10)
                      + 44LL) = v6;
            v7 = *(_DWORD *)v13;
            *(_DWORD *)(*(_QWORD *)std::map<unsigned long,Processor>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 112,
                                     &pPropertyData,
                                     &v10)
                      + 40LL) = v7;
            v8 = *(_DWORD *)v14;
            *(_DWORD *)(*(_QWORD *)std::map<unsigned long,Processor>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 112,
                                     &pPropertyData,
                                     &v10)
                      + 48LL) = v8;
            *((_DWORD *)this + 49) |= 8u;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800243a8  mov     [rsp-28h+arg_10], rbx
0x1800243ad  push    rbp
0x1800243ae  push    rsi
0x1800243af  push    rdi
0x1800243b0  push    r14
0x1800243b2  push    r15
0x1800243b4  mov     rbp, rsp
0x1800243b7  sub     rsp, 70h
0x1800243bb  mov     rax, cs:__security_cookie
0x1800243c2  xor     rax, rsp
0x1800243c5  mov     [rbp+var_8], rax
0x1800243c9  xor     edi, edi
0x1800243cb  lea     rax, aGroup; "Group"
0x1800243d2  mov     [rbp+var_18.PropertyName], rax
0x1800243d6  mov     rbx, rdx
0x1800243d9  lea     rax, [rbp+var_28]
0x1800243dd  mov     dword ptr [rbp+var_24], edi
0x1800243e0  mov     [rsp+70h+pBuffer], rax; pBuffer
0x1800243e5  mov     rsi, rcx
0x1800243e8  lea     rax, [rbp+var_18]
0x1800243ec  mov     [rsp+70h+BufferSize], 2; BufferSize
0x1800243f4  lea     r14d, [rdi+1]
0x1800243f8  mov     [rsp+70h+pPropertyData], rax; pPropertyData
0x1800243fd  or      r15d, 0FFFFFFFFh
0x180024401  mov     dword ptr [rbp+var_20], edi
0x180024404  mov     r9d, r14d; PropertyDataCount
0x180024407  mov     dword ptr [rbp+var_1C], edi
0x18002440a  xor     r8d, r8d; pTdhContext
0x18002440d  mov     word ptr [rbp+var_28], di
0x180024411  xor     edx, edx; TdhContextCount
0x180024413  mov     [rbp+var_30], dil
0x180024417  mov     rcx, rbx; pEvent
0x18002441a  mov     [rbp+var_2C], edi
0x18002441d  mov     [rbp+var_18.Reserved], edi
0x180024420  mov     [rbp+var_18.ArrayIndex], r15d
0x180024424  call    cs:__imp_TdhGetProperty
0x18002442a  test    eax, eax
0x18002442c  jnz     loc_1800245DC
0x180024432  lea     rax, aNumber; "Number"
0x180024439  mov     [rbp+var_18.Reserved], edi
0x18002443c  mov     [rbp+var_18.PropertyName], rax
0x180024440  mov     r9d, r14d; PropertyDataCount
0x180024443  lea     rax, [rbp+var_30]
0x180024447  mov     [rbp+var_18.ArrayIndex], r15d
0x18002444b  mov     [rsp+70h+pBuffer], rax; pBuffer
0x180024450  xor     r8d, r8d; pTdhContext
0x180024453  lea     rax, [rbp+var_18]
0x180024457  mov     [rsp+70h+BufferSize], r14d; BufferSize
0x18002445c  xor     edx, edx; TdhContextCount
0x18002445e  mov     [rsp+70h+pPropertyData], rax; pPropertyData
0x180024463  mov     rcx, rbx; pEvent
0x180024466  call    cs:__imp_TdhGetProperty
0x18002446c  test    eax, eax
0x18002446e  jnz     loc_1800245DC
0x180024474  lea     rax, aFeaturesaccess; "FeaturesAccessed"
0x18002447b  mov     [rbp+var_18.Reserved], edi
0x18002447e  mov     [rbp+var_18.PropertyName], rax
0x180024482  mov     r9d, r14d; PropertyDataCount
0x180024485  lea     rax, [rbp+var_24]
0x180024489  mov     [rbp+var_18.ArrayIndex], r15d
0x18002448d  mov     [rsp+70h+pBuffer], rax; pBuffer
0x180024492  xor     r8d, r8d; pTdhContext
0x180024495  lea     rax, [rbp+var_18]
0x180024499  mov     [rsp+70h+BufferSize], 4; BufferSize
0x1800244a1  xor     edx, edx; TdhContextCount
0x1800244a3  mov     [rsp+70h+pPropertyData], rax; pPropertyData
0x1800244a8  mov     rcx, rbx; pEvent
0x1800244ab  call    cs:__imp_TdhGetProperty
0x1800244b1  test    eax, eax
0x1800244b3  jnz     loc_1800245DC
0x1800244b9  lea     rax, aFeaturespresen; "FeaturesPresent"
0x1800244c0  mov     [rbp+var_18.Reserved], edi
0x1800244c3  mov     [rbp+var_18.PropertyName], rax
0x1800244c7  mov     r9d, r14d; PropertyDataCount
0x1800244ca  lea     rax, [rbp+var_20]
0x1800244ce  mov     [rbp+var_18.ArrayIndex], r15d
0x1800244d2  mov     [rsp+70h+pBuffer], rax; pBuffer
0x1800244d7  xor     r8d, r8d; pTdhContext
0x1800244da  lea     rax, [rbp+var_18]
0x1800244de  mov     [rsp+70h+BufferSize], 4; BufferSize
0x1800244e6  xor     edx, edx; TdhContextCount
0x1800244e8  mov     [rsp+70h+pPropertyData], rax; pPropertyData
0x1800244ed  mov     rcx, rbx; pEvent
0x1800244f0  call    cs:__imp_TdhGetProperty
0x1800244f6  test    eax, eax
0x1800244f8  jnz     loc_1800245DC
0x1800244fe  lea     rax, aFeaturesvalida; "FeaturesValidated"
0x180024505  mov     [rbp+var_18.Reserved], edi
0x180024508  mov     [rbp+var_18.PropertyName], rax
0x18002450c  mov     r9d, r14d; PropertyDataCount
0x18002450f  lea     rax, [rbp+var_1C]
0x180024513  mov     [rbp+var_18.ArrayIndex], r15d
0x180024517  mov     [rsp+70h+pBuffer], rax; pBuffer
0x18002451c  xor     r8d, r8d; pTdhContext
0x18002451f  lea     rax, [rbp+var_18]
0x180024523  mov     [rsp+70h+BufferSize], 4; BufferSize
0x18002452b  xor     edx, edx; TdhContextCount
0x18002452d  mov     [rsp+70h+pPropertyData], rax; pPropertyData
0x180024532  mov     rcx, rbx; pEvent
0x180024535  call    cs:__imp_TdhGetProperty
0x18002453b  test    eax, eax
0x18002453d  jnz     loc_1800245DC
0x180024543  movzx   ebx, word ptr [rbp+var_28]
0x180024547  lea     rdi, [rsi+70h]
0x18002454b  movzx   eax, [rbp+var_30]
0x18002454f  lea     r8, [rbp+var_2C]
0x180024553  imul    ecx, ebx, 0FFh
0x180024559  lea     rdx, [rbp+var_18]
0x18002455d  add     ecx, eax
0x18002455f  mov     [rbp+var_2C], ecx
0x180024562  mov     rcx, rdi
0x180024565  call    ??$_Try_emplace@AEBK$$V@?$map@KVProcessor@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVProcessor@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVProcessor@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,Processor>::_Try_emplace<ulong const &,>(ulong const &)
0x18002456a  lea     r8, [rbp+var_2C]
0x18002456e  lea     rdx, [rbp+var_18]
0x180024572  mov     rcx, [rax]
0x180024575  mov     [rcx+20h], ebx
0x180024578  mov     rcx, rdi
0x18002457b  movzx   ebx, [rbp+var_30]
0x18002457f  call    ??$_Try_emplace@AEBK$$V@?$map@KVProcessor@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVProcessor@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVProcessor@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,Processor>::_Try_emplace<ulong const &,>(ulong const &)
0x180024584  lea     r8, [rbp+var_2C]
0x180024588  lea     rdx, [rbp+var_18]
0x18002458c  mov     rcx, [rax]
0x18002458f  mov     [rcx+24h], ebx
0x180024592  mov     rcx, rdi
0x180024595  mov     ebx, dword ptr [rbp+var_24]
0x180024598  call    ??$_Try_emplace@AEBK$$V@?$map@KVProcessor@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVProcessor@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVProcessor@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,Processor>::_Try_emplace<ulong const &,>(ulong const &)
0x18002459d  lea     r8, [rbp+var_2C]
0x1800245a1  mov     rcx, rdi
0x1800245a4  mov     rdx, [rax]
0x1800245a7  mov     [rdx+2Ch], ebx
0x1800245aa  lea     rdx, [rbp+var_18]
0x1800245ae  mov     ebx, dword ptr [rbp+var_20]
0x1800245b1  call    ??$_Try_emplace@AEBK$$V@?$map@KVProcessor@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVProcessor@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVProcessor@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,Processor>::_Try_emplace<ulong const &,>(ulong const &)
0x1800245b6  lea     r8, [rbp+var_2C]
0x1800245ba  mov     rcx, rdi
0x1800245bd  mov     rdx, [rax]
0x1800245c0  mov     [rdx+28h], ebx
0x1800245c3  lea     rdx, [rbp+var_18]
0x1800245c7  mov     ebx, dword ptr [rbp+var_1C]
0x1800245ca  call    ??$_Try_emplace@AEBK$$V@?$map@KVProcessor@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVProcessor@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVProcessor@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,Processor>::_Try_emplace<ulong const &,>(ulong const &)
0x1800245cf  mov     rcx, [rax]
0x1800245d2  mov     [rcx+30h], ebx
0x1800245d5  or      dword ptr [rsi+0C4h], 8
0x1800245dc  mov     rcx, [rbp+var_8]
0x1800245e0  xor     rcx, rsp; StackCookie
0x1800245e3  call    __security_check_cookie
0x1800245e8  mov     rbx, [rsp+70h+arg_10]
0x1800245f0  add     rsp, 70h
0x1800245f4  pop     r15
0x1800245f6  pop     r14
0x1800245f8  pop     rdi
0x1800245f9  pop     rsi
0x1800245fa  pop     rbp
0x1800245fb  retn
```
