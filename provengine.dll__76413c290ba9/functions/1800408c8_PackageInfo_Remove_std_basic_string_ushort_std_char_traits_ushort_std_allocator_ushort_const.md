# PackageInfo::Remove(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800408c8`
- end: `0x180040965`
- name: `?Remove@PackageInfo@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180040514`

## callees

- `0x1800011ac`
- `0x18002f9bc`
- `0x1800408c8`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800408de`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800408de`

## pseudocode

```c
__int64 __fastcall PackageInfo::Remove(HKEY *a1, __int64 *a2)
{
  __int64 *v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // r9
  __int64 result; // rax
  __int16 *v6; // rdx
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 *v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  if ( (unsigned __int64)a2[3] >= 8 )
    a2 = (__int64 *)*a2;
  v3 = RegDeleteKeyW(*a1, (LPCWSTR)a2);
  if ( v3 == 2 )
  {
    result = (unsigned int)dword_18005A000;
    if ( (unsigned int)dword_18005A000 <= 5 )
      return result;
    if ( (unsigned __int64)v2[3] >= 8 )
      v2 = (__int64 *)*v2;
    v6 = &word_180050696;
    goto LABEL_13;
  }
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x46,
      (int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)v3,
      v7);
  result = (unsigned int)dword_18005A000;
  if ( (unsigned int)dword_18005A000 > 5 )
  {
    if ( (unsigned __int64)v2[3] >= 8 )
      v2 = (__int64 *)*v2;
    v6 = &word_1800506BE;
LABEL_13:
    v9 = v2;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
             (__int64)&dword_18005A000,
             (__int64)v6,
             0,
             v4,
             &v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800408c8  push    rbx
0x1800408ca  sub     rsp, 30h
0x1800408ce  cmp     qword ptr [rdx+18h], 8
0x1800408d3  mov     rbx, rdx
0x1800408d6  jb      short loc_1800408DB
0x1800408d8  mov     rdx, [rdx]; lpSubKey
0x1800408db  mov     rcx, [rcx]; hKey
0x1800408de  call    cs:__imp_RegDeleteKeyW
0x1800408e4  cmp     eax, 2
0x1800408e7  jnz     short loc_180040907
0x1800408e9  mov     eax, cs:dword_18005A000
0x1800408ef  cmp     eax, 5
0x1800408f2  jbe     short loc_180040945
0x1800408f4  cmp     qword ptr [rbx+18h], 8
0x1800408f9  jb      short loc_1800408FE
0x1800408fb  mov     rbx, [rbx]
0x1800408fe  lea     rdx, word_180050696
0x180040905  jmp     short loc_180040927
0x180040907  test    eax, eax
0x180040909  jnz     short loc_18004094B
0x18004090b  mov     eax, cs:dword_18005A000
0x180040911  cmp     eax, 5
0x180040914  jbe     short loc_180040945
0x180040916  cmp     qword ptr [rbx+18h], 8
0x18004091b  jb      short loc_180040920
0x18004091d  mov     rbx, [rbx]
0x180040920  lea     rdx, word_1800506BE
0x180040927  lea     rax, [rsp+38h+arg_0]
0x18004092c  mov     [rsp+38h+arg_0], rbx
0x180040931  xor     r8d, r8d
0x180040934  mov     qword ptr [rsp+38h+var_18], rax
0x180040939  lea     rcx, dword_18005A000
0x180040940  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180040945  add     rsp, 30h
0x180040949  pop     rbx
0x18004094a  retn
0x18004094b  mov     rcx, [rsp+38h]; this
0x180040950  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x180040957  mov     r9d, eax; char *
0x18004095a  mov     edx, 46h ; 'F'; void *
0x18004095f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
