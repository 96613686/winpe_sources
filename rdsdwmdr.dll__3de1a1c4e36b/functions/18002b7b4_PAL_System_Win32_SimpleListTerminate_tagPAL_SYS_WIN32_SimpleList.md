# PAL_System_Win32_SimpleListTerminate(tagPAL_SYS_WIN32_SimpleList *)

- ea: `0x18002b7b4`
- end: `0x18002b873`
- name: `?PAL_System_Win32_SimpleListTerminate@@YAJPEAUtagPAL_SYS_WIN32_SimpleList@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct tagPAL_SYS_WIN32_SimpleList *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ad68`

## callees

- `0x18000160c`
- `0x18002b7b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b85f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b85f`

## string_xrefs

- `0x18002b7ea`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommonint.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_SimpleListTerminate(
        struct tagPAL_SYS_WIN32_SimpleList *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  struct tagPAL_SYS_WIN32_SimpleList *v6; // rdi
  struct tagPAL_SYS_WIN32_SimpleList *v7; // rcx
  const char *v8; // [rsp+50h] [rbp-28h] BYREF
  int v9; // [rsp+80h] [rbp+8h] BYREF
  int v10; // [rsp+88h] [rbp+10h] BYREF
  const char *v11; // [rsp+90h] [rbp+18h] BYREF
  const char *v12; // [rsp+98h] [rbp+20h] BYREF

  if ( a1 )
  {
    v6 = (struct tagPAL_SYS_WIN32_SimpleList *)*((_QWORD *)a1 + 2);
    while ( a1 != v6 )
    {
      **((_QWORD **)v6 + 2) = *(_QWORD *)v6;
      *(_QWORD *)(*(_QWORD *)v6 + 16LL) = *((_QWORD *)v6 + 2);
      v7 = v6;
      v6 = (struct tagPAL_SYS_WIN32_SimpleList *)*((_QWORD *)v6 + 2);
      LocalFree(v7);
    }
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v9 = 110;
      v11 = "PAL_System_Win32_SimpleListTerminate";
      v10 = -2147467259;
      v12 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommonint.cpp";
      v8 = "Invalid parameter passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (__int64)&word_18004062E,
        a3,
        a4,
        (const unsigned __int16 **)&v8,
        (__int64)&v10,
        (const unsigned __int16 **)&v12,
        (__int64)&v9,
        (const unsigned __int16 **)&v11);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002b7b4  mov     r11, rsp
0x18002b7b7  push    rbx
0x18002b7b8  push    rdi
0x18002b7b9  sub     rsp, 68h
0x18002b7bd  mov     rbx, rcx
0x18002b7c0  test    rcx, rcx
0x18002b7c3  jnz     short loc_18002B83C
0x18002b7c5  mov     eax, cs:dword_180044008
0x18002b7cb  cmp     eax, 2
0x18002b7ce  jbe     short loc_18002B835
0x18002b7d0  lea     rax, aPalSystemWin32_1; "PAL_System_Win32_SimpleListTerminate"
0x18002b7d7  mov     dword ptr [r11+8], 6Eh ; 'n'
0x18002b7df  mov     [r11+18h], rax
0x18002b7e3  lea     rdx, word_18004062E
0x18002b7ea  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b7f1  mov     dword ptr [r11+10h], 80004005h
0x18002b7f9  mov     [r11+20h], rax
0x18002b7fd  lea     rax, aInvalidParamet; "Invalid parameter passed"
0x18002b804  mov     [r11-28h], rax
0x18002b808  lea     rax, [r11+18h]
0x18002b80c  mov     [r11-38h], rax
0x18002b810  lea     rax, [r11+8]
0x18002b814  mov     [r11-40h], rax
0x18002b818  lea     rax, [r11+20h]
0x18002b81c  mov     [r11-48h], rax
0x18002b820  lea     rax, [r11+10h]
0x18002b824  mov     [r11-50h], rax
0x18002b828  lea     rax, [r11-28h]
0x18002b82c  mov     [r11-58h], rax
0x18002b830  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b835  mov     eax, 80070057h
0x18002b83a  jmp     short loc_18002B86C
0x18002b83c  mov     rdi, [rcx+10h]
0x18002b840  jmp     short loc_18002B865
0x18002b842  mov     rax, [rdi]
0x18002b845  lea     rdx, [rdi+10h]
0x18002b849  mov     rcx, [rdx]
0x18002b84c  mov     [rcx], rax
0x18002b84f  mov     rcx, [rdi]
0x18002b852  mov     rax, [rdx]
0x18002b855  mov     [rcx+10h], rax
0x18002b859  mov     rcx, rdi; hMem
0x18002b85c  mov     rdi, [rdx]
0x18002b85f  call    cs:__imp_LocalFree
0x18002b865  cmp     rbx, rdi
0x18002b868  jnz     short loc_18002B842
0x18002b86a  xor     eax, eax
0x18002b86c  add     rsp, 68h
0x18002b870  pop     rdi
0x18002b871  pop     rbx
0x18002b872  retn
```
