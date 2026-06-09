# PackageInfo::Remove(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002d218`
- end: `0x18002d2b4`
- name: `?Remove@PackageInfo@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(HKEY *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180016d64`

## callees

- `0x1800017ec`
- `0x18001b3a8`
- `0x18002d218`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d22e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d22e`

## pseudocode

```c
__int64 __fastcall PackageInfo::Remove(HKEY *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 result; // rax
  __int16 *v7; // rdx
  unsigned int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _QWORD *v10; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  if ( a2[3] >= 8u )
    a2 = (_QWORD *)*a2;
  v3 = RegDeleteKeyW(*a1, (LPCWSTR)a2);
  if ( v3 == 2 )
  {
    v5 = g_hProvTraceProvider;
    result = *(unsigned int *)g_hProvTraceProvider;
    if ( (unsigned int)result <= 5 )
      return result;
    if ( v2[3] >= 8u )
      v2 = (_QWORD *)*v2;
    v7 = (__int16 *)byte_1800419AB;
    goto LABEL_13;
  }
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)v3,
      v8);
  v5 = g_hProvTraceProvider;
  result = *(unsigned int *)g_hProvTraceProvider;
  if ( (unsigned int)result > 5 )
  {
    if ( v2[3] >= 8u )
      v2 = (_QWORD *)*v2;
    v7 = &word_18004197E;
LABEL_13:
    v10 = v2;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
             v5,
             (__int64)v7,
             0,
             v4,
             &v10);
  }
  return result;
}

```

## disassembly

```asm
0x18002d218  push    rbx
0x18002d21a  sub     rsp, 30h
0x18002d21e  cmp     qword ptr [rdx+18h], 8
0x18002d223  mov     rbx, rdx
0x18002d226  jb      short loc_18002D22B
0x18002d228  mov     rdx, [rdx]; lpSubKey
0x18002d22b  mov     rcx, [rcx]; hKey
0x18002d22e  call    cs:__imp_RegDeleteKeyW
0x18002d234  cmp     eax, 2
0x18002d237  jnz     short loc_18002D25A
0x18002d239  mov     rcx, cs:g_hProvTraceProvider
0x18002d240  mov     eax, [rcx]
0x18002d242  cmp     eax, 5
0x18002d245  jbe     short loc_18002D294
0x18002d247  cmp     qword ptr [rbx+18h], 8
0x18002d24c  jb      short loc_18002D251
0x18002d24e  mov     rbx, [rbx]
0x18002d251  lea     rdx, byte_1800419AB
0x18002d258  jmp     short loc_18002D27D
0x18002d25a  test    eax, eax
0x18002d25c  jnz     short loc_18002D29A
0x18002d25e  mov     rcx, cs:g_hProvTraceProvider
0x18002d265  mov     eax, [rcx]
0x18002d267  cmp     eax, 5
0x18002d26a  jbe     short loc_18002D294
0x18002d26c  cmp     qword ptr [rbx+18h], 8
0x18002d271  jb      short loc_18002D276
0x18002d273  mov     rbx, [rbx]
0x18002d276  lea     rdx, word_18004197E
0x18002d27d  lea     rax, [rsp+38h+arg_0]
0x18002d282  mov     [rsp+38h+arg_0], rbx
0x18002d287  xor     r8d, r8d
0x18002d28a  mov     qword ptr [rsp+38h+var_18], rax
0x18002d28f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002d294  add     rsp, 30h
0x18002d298  pop     rbx
0x18002d299  retn
0x18002d29a  mov     rcx, [rsp+38h]; this
0x18002d29f  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x18002d2a6  mov     r9d, eax; char *
0x18002d2a9  mov     edx, 46h ; 'F'; void *
0x18002d2ae  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
