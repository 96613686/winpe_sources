# DiscpSetDefaultiScsiName

- ea: `0x18000ba10`
- end: `0x18000bbb0`
- name: `DiscpSetDefaultiScsiName`
- size: `416`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003c30`
- `0x18001302c`

## callees

- `0x180006998`
- `0x180008960`
- `0x18000ba10`
- `0x18000ce28`

## import_xrefs

- `ISCSIUM!DiscpCopyUnicodeString` at `0x18000ba48`
- `ISCSIUM!DiscpCopyUnicodeString` at `0x18000ba48`
- `ISCSIUM!DiscpSetRegistryValue` at `0x18000bab7`
- `ISCSIUM!DiscpSetRegistryValue` at `0x18000bab7`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000baec`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x18000baec`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bb76`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bb86`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bb9b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bb76`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bb86`
- `ISCSIUM!DiscpFreeMemory` at `0x18000bb9b`
- `ISCSIUM!DiscpGenerateiScsiNameFromComputerName` at `0x18000ba54`
- `ISCSIUM!DiscpGenerateiScsiNameFromComputerName` at `0x18000ba54`
- `ntdll!RtlLeaveCriticalSection` at `0x18000baca`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb2a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000baca`
- `ntdll!RtlLeaveCriticalSection` at `0x18000bb2a`
- `ntdll!RtlEnterCriticalSection` at `0x18000ba7d`
- `ntdll!RtlEnterCriticalSection` at `0x18000ba7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bb01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bb01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb0b`

## pseudocode

```c
__int64 __fastcall DiscpSetDefaultiScsiName(_WORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rsi
  unsigned int v7; // edi
  __int64 i; // r12
  __int64 v9; // r14
  unsigned int v11; // [rsp+80h] [rbp+38h] BYREF
  __int64 v12; // [rsp+88h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+48h] BYREF
  __int64 v14; // [rsp+98h] [rbp+50h] BYREF

  v12 = 0;
  v11 = 0;
  v14 = 0;
  hKey = 0;
  if ( a1 && *a1 )
    v2 = DiscpCopyUnicodeString(&v12, a1);
  else
    v2 = DiscpGenerateiScsiNameFromComputerName(&v12);
  v3 = v2;
  if ( !v2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v12 + 2 * v4) );
    RtlEnterCriticalSection(&DiscpCritSection);
    if ( a1 )
    {
      v3 = DiscpSetRegistryValue(
             0,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
             L"DefaultInitiatorName",
             1,
             v12,
             2 * (int)v4 + 2,
             0);
      if ( v3 )
      {
        RtlLeaveCriticalSection(&DiscpCritSection);
        v5 = v12;
        if ( !v12 )
          return v3;
        goto LABEL_21;
      }
    }
    else if ( !(unsigned int)DiscpOpenRegistryKey(
                               &hKey,
                               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
                               983103) )
    {
      RegDeleteValueW(hKey, L"DefaultInitiatorName");
      RegCloseKey(hKey);
    }
    v6 = DiscpiScsiNodeName;
    DiscpiScsiNodeName = v12;
    RtlLeaveCriticalSection(&DiscpCritSection);
    if ( !(unsigned int)DiscpGetInitiatorInstanceList(0, &v11, &v14) )
    {
      v7 = 0;
      for ( i = v14; v7 < v11; ++v7 )
      {
        v9 = *(_QWORD *)(i + 8LL * v7);
        DiscpChangeiqnNameForHBA(v9, v6, v12);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 16), 0xFFFFFFFF) == 1 )
          DiscpFreeMemory(v9);
      }
      DiscpFreeMemory(i);
    }
    DiscpiSNSChangeiSCSIName(v6, v12);
    v5 = v6;
LABEL_21:
    DiscpFreeMemory(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x18000ba10  push    rbp
0x18000ba12  push    rbx
0x18000ba13  push    rsi
0x18000ba14  push    rdi
0x18000ba15  push    r12
0x18000ba17  push    r14
0x18000ba19  mov     rbp, rsp
0x18000ba1c  sub     rsp, 48h
0x18000ba20  xor     r14d, r14d
0x18000ba23  mov     rdi, rcx
0x18000ba26  mov     [rbp+arg_8], r14
0x18000ba2a  mov     [rbp+arg_0], r14d
0x18000ba2e  mov     [rbp+arg_18], r14
0x18000ba32  mov     [rbp+hKey], r14
0x18000ba36  test    rcx, rcx
0x18000ba39  jz      short loc_18000BA50
0x18000ba3b  cmp     [rcx], r14w
0x18000ba3f  jz      short loc_18000BA50
0x18000ba41  mov     rdx, rcx
0x18000ba44  lea     rcx, [rbp+arg_8]
0x18000ba48  call    cs:__imp_DiscpCopyUnicodeString
0x18000ba4e  jmp     short loc_18000BA5A
0x18000ba50  lea     rcx, [rbp+arg_8]
0x18000ba54  call    cs:__imp_DiscpGenerateiScsiNameFromComputerName
0x18000ba5a  mov     ebx, eax
0x18000ba5c  test    eax, eax
0x18000ba5e  jnz     loc_18000BBA1
0x18000ba64  mov     rax, [rbp+arg_8]
0x18000ba68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ba6c  inc     rsi
0x18000ba6f  cmp     [rax+rsi*2], r14w
0x18000ba74  jnz     short loc_18000BA6C
0x18000ba76  lea     rcx, DiscpCritSection; CriticalSection
0x18000ba7d  call    cs:__imp_RtlEnterCriticalSection
0x18000ba83  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000ba8a  test    rdi, rdi
0x18000ba8d  jz      short loc_18000BAE2
0x18000ba8f  lea     eax, ds:2[rsi*2]
0x18000ba96  mov     [rsp+48h+var_18], r14b
0x18000ba9b  mov     [rsp+48h+var_20], eax
0x18000ba9f  lea     r8, aDefaultinitiat; "DefaultInitiatorName"
0x18000baa6  mov     rax, [rbp+arg_8]
0x18000baaa  mov     r9d, 1
0x18000bab0  xor     ecx, ecx
0x18000bab2  mov     [rsp+48h+var_28], rax
0x18000bab7  call    cs:__imp_DiscpSetRegistryValue
0x18000babd  mov     ebx, eax
0x18000babf  test    eax, eax
0x18000bac1  jz      short loc_18000BB11
0x18000bac3  lea     rcx, DiscpCritSection; CriticalSection
0x18000baca  call    cs:__imp_RtlLeaveCriticalSection
0x18000bad0  mov     rcx, [rbp+arg_8]
0x18000bad4  test    rcx, rcx
0x18000bad7  jnz     loc_18000BB9B
0x18000badd  jmp     loc_18000BBA1
0x18000bae2  mov     r8d, 0F003Fh
0x18000bae8  lea     rcx, [rbp+hKey]
0x18000baec  call    cs:__imp_DiscpOpenRegistryKey
0x18000baf2  test    eax, eax
0x18000baf4  jnz     short loc_18000BB11
0x18000baf6  mov     rcx, [rbp+hKey]; hKey
0x18000bafa  lea     rdx, aDefaultinitiat; "DefaultInitiatorName"
0x18000bb01  call    cs:__imp_RegDeleteValueW
0x18000bb07  mov     rcx, [rbp+hKey]; hKey
0x18000bb0b  call    cs:__imp_RegCloseKey
0x18000bb11  mov     rax, [rbp+arg_8]
0x18000bb15  lea     rcx, DiscpCritSection; CriticalSection
0x18000bb1c  mov     rsi, cs:DiscpiScsiNodeName
0x18000bb23  mov     cs:DiscpiScsiNodeName, rax
0x18000bb2a  call    cs:__imp_RtlLeaveCriticalSection
0x18000bb30  lea     r8, [rbp+arg_18]
0x18000bb34  xor     ecx, ecx
0x18000bb36  lea     rdx, [rbp+arg_0]
0x18000bb3a  call    DiscpGetInitiatorInstanceList
0x18000bb3f  test    eax, eax
0x18000bb41  jnz     short loc_18000BB8C
0x18000bb43  mov     edi, r14d
0x18000bb46  mov     r12, [rbp+arg_18]
0x18000bb4a  cmp     [rbp+arg_0], r14d
0x18000bb4e  jbe     short loc_18000BB83
0x18000bb50  mov     r8, [rbp+arg_8]
0x18000bb54  mov     rdx, rsi
0x18000bb57  mov     eax, edi
0x18000bb59  mov     r14, [r12+rax*8]
0x18000bb5d  mov     rcx, r14
0x18000bb60  call    DiscpChangeiqnNameForHBA
0x18000bb65  or      eax, 0FFFFFFFFh
0x18000bb68  lock xadd [r14+10h], eax
0x18000bb6e  cmp     eax, 1
0x18000bb71  jnz     short loc_18000BB7C
0x18000bb73  mov     rcx, r14
0x18000bb76  call    cs:__imp_DiscpFreeMemory
0x18000bb7c  inc     edi
0x18000bb7e  cmp     edi, [rbp+arg_0]
0x18000bb81  jb      short loc_18000BB50
0x18000bb83  mov     rcx, r12
0x18000bb86  call    cs:__imp_DiscpFreeMemory
0x18000bb8c  mov     rdx, [rbp+arg_8]
0x18000bb90  mov     rcx, rsi
0x18000bb93  call    DiscpiSNSChangeiSCSIName
0x18000bb98  mov     rcx, rsi
0x18000bb9b  call    cs:__imp_DiscpFreeMemory
0x18000bba1  mov     eax, ebx
0x18000bba3  add     rsp, 48h
0x18000bba7  pop     r14
0x18000bba9  pop     r12
0x18000bbab  pop     rdi
0x18000bbac  pop     rsi
0x18000bbad  pop     rbx
0x18000bbae  pop     rbp
0x18000bbaf  retn
```
