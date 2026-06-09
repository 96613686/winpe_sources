# TlgHelper::LogInfo<ushort const (&)[34],uint>(ushort const (&)[34],uint &&)

- ea: `0x1800044e8`
- end: `0x180004557`
- name: `??$LogInfo@AEAY0CC@$$CBGI@TlgHelper@@SAXAEAY0CC@$$CBG$$QEAI@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800132f0`

## callees

- `0x180001174`
- `0x1800044e8`
- `0x18000e7ec`

## string_xrefs

- `0x18000452c`: `Stop_SkippedOverwritePromptResult`

## pseudocode

```c
__int64 __fastcall TlgHelper::LogInfo<unsigned short const (&)[34],unsigned int>(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  int v4; // r9d
  __int64 v5; // r8
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *v7; // [rsp+50h] [rbp+18h] BYREF

  v6 = a1;
  result = (__int64)TlgHelper::Provider();
  v5 = result;
  if ( *(_DWORD *)result > 4u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v5 + 16) & 2) != 0 && (result & 2) == result )
    {
      LODWORD(v6) = *a2;
      v7 = L"Stop_SkippedOverwritePromptResult";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v5,
               (unsigned int)&byte_18002A31F,
               v5,
               v4,
               (__int64)&v7,
               (__int64)&v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800044e8  mov     [rsp+arg_0], rcx
0x1800044ed  push    rbx
0x1800044ee  sub     rsp, 30h
0x1800044f2  mov     rbx, rdx
0x1800044f5  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x1800044fa  mov     r8, rax
0x1800044fd  mov     ecx, [rax]
0x1800044ff  cmp     ecx, 4
0x180004502  jbe     short loc_180004551
0x180004504  mov     rax, [rax+18h]
0x180004508  mov     rcx, [r8+10h]
0x18000450c  test    cl, 2
0x18000450f  jz      short loc_180004551
0x180004511  mov     rcx, rax
0x180004514  and     ecx, 2
0x180004517  cmp     rcx, rax
0x18000451a  jnz     short loc_180004551
0x18000451c  mov     eax, [rbx]
0x18000451e  lea     rdx, byte_18002A31F
0x180004525  mov     dword ptr [rsp+38h+arg_0], eax
0x180004529  mov     rcx, r8
0x18000452c  lea     rax, aStopSkippedove; "Stop_SkippedOverwritePromptResult"
0x180004533  mov     [rsp+38h+arg_10], rax
0x180004538  lea     rax, [rsp+38h+arg_0]
0x18000453d  mov     [rsp+38h+var_10], rax
0x180004542  lea     rax, [rsp+38h+arg_10]
0x180004547  mov     [rsp+38h+var_18], rax
0x18000454c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180004551  add     rsp, 30h
0x180004555  pop     rbx
0x180004556  retn
```
