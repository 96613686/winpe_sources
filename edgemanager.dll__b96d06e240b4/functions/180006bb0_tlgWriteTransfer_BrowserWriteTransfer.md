# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x180006bb0`
- end: `0x180006d7c`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000102c`

## callees

- `0x180006bb0`
- `0x180085010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180006d02`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180006d02`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180006cf8`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180006cf8`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180006cbe`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180006ced`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180006cbe`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180006ced`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006c62`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006c9f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006cb4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006c62`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006c9f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180006cb4`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180006c91`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180006c91`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180006cc9`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180006cc9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180006d60`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180006d60`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_BrowserWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR a6)
{
  PEVENT_DATA_DESCRIPTOR UserData; // rbx
  ULONG v8; // esi
  ULONGLONG v11; // rax
  unsigned __int16 *v12; // rdx
  int DWORD; // r15d
  int v14; // ecx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-28h] BYREF

  UserData = a6;
  v8 = 0;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v11 = *(_QWORD *)(a2 + 3);
  v12 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v11;
  a6->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v12;
  UserData->Reserved = 2;
  UserData[1].Size = *v12;
  UserData[1].Reserved = 1;
  LODWORD(a6) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( *(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) )
    return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v8, a3, a4, UserDataCount, UserData);
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
  {
LABEL_16:
    v8 = 2;
    return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v8, a3, a4, UserDataCount, UserData);
  }
  LOBYTE(a6) = 1;
  if ( dword_1800B6770 == 2 )
  {
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) && DWORD == 2 )
    {
      if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
        || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
            (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, PEVENT_DATA_DESCRIPTOR *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                               + 120LL))(
              EdgeBrowsingEnvironment,
              &a6) < 0) )
      {
        LOBYTE(v14) = LCIEIsCurrentProcessUsingInPrivateComponents();
        goto LABEL_15;
      }
      goto LABEL_13;
    }
    if ( !LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
LABEL_13:
      LOBYTE(v14) = (_BYTE)a6;
      goto LABEL_15;
    }
    v14 = LCIEIsCurrentProcessInPrivate();
    if ( DWORD != 3 )
      dword_1800B6770 = v14;
  }
  else
  {
    LOBYTE(v14) = dword_1800B6770 == 1;
  }
LABEL_15:
  if ( (_BYTE)v14 )
    goto LABEL_16;
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v8, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180006bb0  mov     [rsp+arg_8], rbx
0x180006bb5  mov     [rsp+arg_10], rbp
0x180006bba  push    rsi
0x180006bbb  push    rdi
0x180006bbc  push    r14
0x180006bbe  sub     rsp, 50h
0x180006bc2  movzx   eax, byte ptr [rdx]
0x180006bc5  mov     rdi, rcx
0x180006bc8  mov     rbx, [rsp+68h+arg_28]
0x180006bd0  xor     esi, esi
0x180006bd2  shl     eax, 18h
0x180006bd5  mov     rbp, r9
0x180006bd8  mov     dword ptr [rsp+68h+EventDescriptor.Id], eax
0x180006bdc  mov     r14, r8
0x180006bdf  movzx   eax, word ptr [rdx+1]
0x180006be3  mov     dword ptr [rsp+68h+EventDescriptor.Level], eax
0x180006be7  mov     rax, [rdx+3]
0x180006beb  add     rdx, 0Bh
0x180006bef  mov     [rsp+68h+EventDescriptor.Keyword], rax
0x180006bf4  mov     rax, [rcx+8]
0x180006bf8  mov     [rbx], rax
0x180006bfb  mov     rax, [rcx+8]
0x180006bff  movzx   ecx, word ptr [rax]
0x180006c02  mov     [rbx+8], ecx
0x180006c05  lea     rcx, _TraceLoggingMetadata
0x180006c0c  mov     [rbx+10h], rdx
0x180006c10  mov     dword ptr [rbx+0Ch], 2
0x180006c17  movzx   eax, word ptr [rdx]
0x180006c1a  mov     [rbx+18h], eax
0x180006c1d  lea     rax, _TraceLoggingMetadataEnd
0x180006c24  sub     eax, ecx
0x180006c26  mov     dword ptr [rbx+1Ch], 1
0x180006c2d  mov     ecx, cs:_tls_index
0x180006c33  mov     dword ptr [rsp+68h+arg_28], eax
0x180006c3a  mov     eax, dword ptr [rsp+68h+arg_28]
0x180006c41  mov     rax, gs:58h
0x180006c4a  mov     edx, 10h
0x180006c4f  mov     rax, [rax+rcx*8]
0x180006c53  cmp     [rdx+rax], sil
0x180006c57  jnz     loc_180006D37
0x180006c5d  mov     ecx, 20000019h
0x180006c62  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180006c68  test    al, al
0x180006c6a  jz      loc_180006D32
0x180006c70  mov     eax, cs:dword_1800B6770
0x180006c76  mov     [rsp+68h+arg_0], r15
0x180006c7b  mov     byte ptr [rsp+68h+arg_28], 1
0x180006c83  cmp     eax, 2
0x180006c86  jnz     loc_180006D23
0x180006c8c  mov     ecx, 1000002Dh
0x180006c91  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180006c97  mov     ecx, 20000002h
0x180006c9c  mov     r15d, eax
0x180006c9f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180006ca5  test    al, al
0x180006ca7  jnz     short loc_180006CF8
0x180006ca9  cmp     r15d, 2
0x180006cad  jnz     short loc_180006CF8
0x180006caf  mov     ecx, 10000038h
0x180006cb4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180006cba  test    al, al
0x180006cbc  jz      short loc_180006CC9
0x180006cbe  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180006cc4  movzx   ecx, al
0x180006cc7  jmp     short loc_180006D29
0x180006cc9  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180006ccf  mov     r8, rax
0x180006cd2  lea     rdx, [rsp+68h+arg_28]
0x180006cda  mov     rcx, [rax]
0x180006cdd  mov     rax, [rcx+78h]
0x180006ce1  mov     rcx, r8
0x180006ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce9  test    eax, eax
0x180006ceb  jns     short loc_180006D19
0x180006ced  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180006cf3  movzx   ecx, al
0x180006cf6  jmp     short loc_180006D29
0x180006cf8  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180006cfe  test    al, al
0x180006d00  jz      short loc_180006D19
0x180006d02  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180006d08  movzx   ecx, al
0x180006d0b  cmp     r15d, 3
0x180006d0f  jz      short loc_180006D29
0x180006d11  mov     cs:dword_1800B6770, ecx
0x180006d17  jmp     short loc_180006D29
0x180006d19  movzx   ecx, byte ptr [rsp+68h+arg_28]
0x180006d21  jmp     short loc_180006D29
0x180006d23  cmp     eax, 1
0x180006d26  setz    cl
0x180006d29  mov     r15, [rsp+68h+arg_0]
0x180006d2e  test    cl, cl
0x180006d30  jz      short loc_180006D37
0x180006d32  mov     esi, 2
0x180006d37  mov     eax, [rsp+68h+arg_20]
0x180006d3e  lea     rdx, [rsp+68h+EventDescriptor]; EventDescriptor
0x180006d43  mov     rcx, [rdi+20h]; RegHandle
0x180006d47  mov     r9d, esi; Flags
0x180006d4a  mov     [rsp+68h+UserData], rbx; UserData
0x180006d4f  xor     r8d, r8d; Filter
0x180006d52  mov     [rsp+68h+UserDataCount], eax; UserDataCount
0x180006d56  mov     [rsp+68h+RelatedActivityId], rbp; RelatedActivityId
0x180006d5b  mov     [rsp+68h+ActivityId], r14; ActivityId
0x180006d60  call    cs:__imp_EventWriteEx
0x180006d66  mov     rbx, [rsp+68h+arg_8]
0x180006d6b  mov     rbp, [rsp+68h+arg_10]
0x180006d73  add     rsp, 50h
0x180006d77  pop     r14
0x180006d79  pop     rdi
0x180006d7a  pop     rsi
0x180006d7b  retn
```
