# AOMDHandler::UpdateStatsOnExit(void)

- ea: `0x1800149b8`
- end: `0x180014a44`
- name: `?UpdateStatsOnExit@AOMDHandler@@AEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180007944`

## callees

- `0x180001008`
- `0x18000e7ec`
- `0x1800149b8`

## string_xrefs

- `0x1800149e5`: `UpdateStatsOnExit_Starting`

## pseudocode

```c
__int64 __fastcall AOMDHandler::UpdateStatsOnExit(AOMDHandler *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r9
  __int64 v4; // r8
  const wchar_t *v6; // [rsp+48h] [rbp+10h] BYREF

  v2 = TlgHelper::Provider();
  if ( *(_DWORD *)v2 > 4u )
  {
    v4 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v2 + 2) & 2) != 0 && (*((_QWORD *)v2 + 3) & 2LL) == v4 )
    {
      v6 = L"UpdateStatsOnExit_Starting";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v2,
        (__int64)byte_180029A61,
        v4,
        v3,
        (int **)&v6);
    }
  }
  if ( (unsigned int)(g_aomdPromptResult - 10) <= 3 || g_aomdPromptResult == 8 )
  {
    *((_QWORD *)this + 12) = *((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    *((_DWORD *)this + 28) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800149b8  push    rbx
0x1800149ba  sub     rsp, 30h
0x1800149be  mov     rbx, rcx
0x1800149c1  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x1800149c6  mov     edx, [rax]
0x1800149c8  cmp     edx, 4
0x1800149cb  jbe     short loc_180014A0A
0x1800149cd  mov     r8, [rax+18h]
0x1800149d1  mov     rdx, [rax+10h]
0x1800149d5  test    dl, 2
0x1800149d8  jz      short loc_180014A0A
0x1800149da  mov     rcx, r8
0x1800149dd  and     ecx, 2
0x1800149e0  cmp     rcx, r8
0x1800149e3  jnz     short loc_180014A0A
0x1800149e5  lea     rcx, aUpdatestatsone; "UpdateStatsOnExit_Starting"
0x1800149ec  mov     [rsp+38h+arg_8], rcx
0x1800149f1  lea     rcx, [rsp+38h+arg_8]
0x1800149f6  mov     [rsp+38h+var_18], rcx
0x1800149fb  lea     rdx, byte_180029A61
0x180014a02  mov     rcx, rax
0x180014a05  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180014a0a  mov     ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180014a10  nop
0x180014a11  lea     eax, [rcx-0Ah]
0x180014a14  cmp     eax, 3
0x180014a17  jbe     short loc_180014A1E
0x180014a19  cmp     ecx, 8
0x180014a1c  jnz     short loc_180014A35
0x180014a1e  mov     rax, [rbx+68h]
0x180014a22  mov     [rbx+60h], rax
0x180014a26  mov     qword ptr [rbx+68h], 0
0x180014a2e  mov     dword ptr [rbx+70h], 0
0x180014a35  xor     eax, eax
0x180014a37  jmp     short loc_180014A3D
0x180014a39  mov     eax, dword ptr [rsp+38h+arg_8]
0x180014a3d  add     rsp, 30h
0x180014a41  pop     rbx
0x180014a42  retn
```
