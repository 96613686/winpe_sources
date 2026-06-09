# PpfhEventLogEvent::PpfhEventLogEvent(uint,uint,uchar *,uint,ushort const *)

- ea: `0x18002b36c`
- end: `0x18002b44f`
- name: `??0PpfhEventLogEvent@@QEAA@IIPEAEIPEBG@Z`
- size: `227`
- prototype: `PpfhEventLogEvent *__fastcall(PpfhEventLogEvent *this, int, int, unsigned __int8 *, unsigned int, char *lpMem)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002ad1c`
- `0x18002c7b0`
- `0x18002da6c`

## callees

- `0x18000f0c8`
- `0x18002b36c`
- `0x18002b8f4`
- `0x18002c5e4`
- `0x180034ff8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b40d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b40d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b421`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b421`

## string_xrefs

- `0x18002b43d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
PpfhEventLogEvent *__fastcall PpfhEventLogEvent::PpfhEventLogEvent(
        PpfhEventLogEvent *this,
        int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        char *lpMem)
{
  const char *v7; // r9
  const char *v8; // r9
  unsigned __int16 *v9; // rdi
  HANDLE ProcessHeap; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *(_DWORD *)this = a2;
  *((_DWORD *)this + 1) = a3;
  PpfhEventLogEvent::CopyEventData(this, a4, a5);
  if ( lpMem )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpMem,
      lpMem,
      0xFFFFFFFFFFFFFFFFuLL,
      v7);
    if ( !lpMem )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      (char *)this + 48,
      &lpMem);
    v9 = (unsigned __int16 *)lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18002b36c  mov     [rsp+arg_10], rbx
0x18002b371  mov     [rsp+arg_0], rcx
0x18002b376  push    rdi
0x18002b377  sub     rsp, 20h
0x18002b37b  mov     rbx, rcx
0x18002b37e  mov     [rsp+28h+arg_8], 0
0x18002b386  mov     qword ptr [rcx+8], 0
0x18002b38e  mov     qword ptr [rcx+10h], 0
0x18002b396  mov     qword ptr [rcx+18h], 0
0x18002b39e  mov     qword ptr [rcx+20h], 0
0x18002b3a6  mov     dword ptr [rcx+28h], 0
0x18002b3ad  mov     qword ptr [rcx+30h], 0
0x18002b3b5  mov     [rcx], edx
0x18002b3b7  mov     [rcx+4], r8d
0x18002b3bb  mov     r8d, [rsp+28h+arg_20]; unsigned int
0x18002b3c0  mov     rdx, r9; unsigned __int8 *
0x18002b3c3  call    ?CopyEventData@PpfhEventLogEvent@@AEAAXPEAEI@Z; PpfhEventLogEvent::CopyEventData(uchar *,uint)
0x18002b3c8  mov     rdx, [rsp+28h+lpMem]
0x18002b3cd  test    rdx, rdx
0x18002b3d0  jz      short loc_18002B42E
0x18002b3d2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b3d6  lea     rcx, [rsp+28h+lpMem]
0x18002b3db  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002b3e0  mov     [rsp+28h+arg_8], 2
0x18002b3e8  mov     rcx, [rsp+28h]; this
0x18002b3ed  cmp     [rsp+28h+lpMem], 0
0x18002b3f3  jz      short loc_18002B43D
0x18002b3f5  lea     rdx, [rsp+28h+lpMem]
0x18002b3fa  lea     rcx, [rbx+30h]
0x18002b3fe  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002b403  mov     rdi, [rsp+28h+lpMem]
0x18002b408  test    rdi, rdi
0x18002b40b  jz      short loc_18002B42E
0x18002b40d  call    cs:__imp_GetProcessHeap
0x18002b414  nop     dword ptr [rax+rax+00h]
0x18002b419  mov     rcx, rax; hHeap
0x18002b41c  mov     r8, rdi; lpMem
0x18002b41f  xor     edx, edx; dwFlags
0x18002b421  call    cs:__imp_HeapFree
0x18002b428  nop     dword ptr [rax+rax+00h]
0x18002b42d  nop
0x18002b42e  mov     rax, rbx
0x18002b431  mov     rbx, [rsp+28h+arg_10]
0x18002b436  add     rsp, 20h
0x18002b43a  pop     rdi
0x18002b43b  retn
0x18002b43d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b444  mov     edx, 0FF8h; void *
0x18002b449  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
