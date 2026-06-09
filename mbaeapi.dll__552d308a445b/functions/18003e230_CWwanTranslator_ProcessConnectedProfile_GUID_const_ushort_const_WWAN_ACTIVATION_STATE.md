# CWwanTranslator::_ProcessConnectedProfile(_GUID const &,ushort const *,_WWAN_ACTIVATION_STATE)

- ea: `0x18003e230`
- end: `0x18003e4eb`
- name: `?_ProcessConnectedProfile@CWwanTranslator@@AEAAJAEBU_GUID@@PEBGW4_WWAN_ACTIVATION_STATE@@@Z`
- size: `699`
- prototype: `int __fastcall(__int64, __int64, _WORD *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003e4f4`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003e230`
- `0x180043de4`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003e3ea`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003e420`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003e3ea`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003e420`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003e3dd`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003e413`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003e3dd`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003e413`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003e32f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003e32f`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x18003e392`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetProfileIstream` at `0x18003e392`

## pseudocode

```c
int __fastcall CWwanTranslator::_ProcessConnectedProfile(__int64 a1, __int64 a2, _WORD *a3, int a4)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // eax
  int ProfileIstream; // eax
  signed int v14; // ebx
  __int64 v15; // rdx
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19[2]; // [rsp+20h] [rbp-39h]
  int v20; // [rsp+20h] [rbp-39h]
  int v21; // [rsp+30h] [rbp-29h] BYREF
  int v22; // [rsp+34h] [rbp-25h] BYREF
  int v23[2]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v24; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v25[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1h]
  unsigned __int16 *v27[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v28; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned __int16 *v30; // [rsp+D0h] [rbp+77h] BYREF

  *(_OWORD *)v25 = 0;
  v26 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  std::vector<unsigned short>::resize(v25);
  std::vector<unsigned short>::resize(v27);
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"Enter");
  v19[0] = 1813;
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"%S(%d):%s", "CWwanTranslator::_ProcessConnectedProfile");
  v8 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    v30 = v27[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)byte_180076F19,
      v9,
      v10,
      (const unsigned __int16 **)&v30);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  if ( a3 && *a3 )
  {
    v24 = 0;
    v21 = 0;
    v11 = WwanOpenHandle(1, 0, &v21, &v24);
    if ( v11 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x71D,
               (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
               (const char *)v11,
               v19[0]);
    v25[0] = (unsigned __int16 *)&v24;
    LOBYTE(v25[1]) = 1;
    LODWORD(v30) = 0;
    *(_QWORD *)v23 = 0;
    v27[0] = (unsigned __int16 *)v23;
    LOBYTE(v27[1]) = 1;
    v22 = 0;
    ProfileIstream = WwanGetProfileIstream(v24, a3, &v22, &v30, v23);
    v14 = ProfileIstream;
    if ( ProfileIstream > 0 )
      v14 = (unsigned __int16)ProfileIstream | 0x80070000;
    if ( v14 < 0 )
    {
      v15 = 1831;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
        (const char *)(unsigned int)v14,
        v20);
      WwanFreeMemory(*(_QWORD *)v23);
      WwanCloseHandle(v24, 0);
      return v14;
    }
    if ( (unsigned int)v30 < 0x18D8 )
    {
      v14 = -2147024882;
      v15 = 1832;
      goto LABEL_13;
    }
    CWwanTranslator::_ProcessWwanProfile(a1, a2, a4, *(__int64 *)v23, 0);
    WwanFreeMemory(*(_QWORD *)v23);
    WwanCloseHandle(v24, 0);
  }
  *(_OWORD *)v25 = 0;
  v26 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  std::vector<unsigned short>::resize(v25);
  std::vector<unsigned short>::resize(v27);
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"Exit");
  v19[0] = 1837;
  StringCchPrintfW(
    v27[0],
    v27[1] - v27[0],
    L"%S(%d):%s",
    "CWwanTranslator::_ProcessConnectedProfile",
    *(_QWORD *)v19,
    v25[0]);
  v16 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v16 > 5u )
  {
    v30 = v27[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v16,
      (__int64)byte_180076ED3,
      v17,
      v18,
      (const unsigned __int16 **)&v30);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  return 0;
}

```

## disassembly

```asm
0x18003e230  push    rbp
0x18003e232  push    rbx
0x18003e233  push    rsi
0x18003e234  push    rdi
0x18003e235  push    r14
0x18003e237  push    r15
0x18003e239  lea     rbp, [rsp-2Fh]
0x18003e23e  sub     rsp, 88h
0x18003e245  mov     edi, r9d
0x18003e248  mov     rbx, r8
0x18003e24b  mov     rsi, rdx
0x18003e24e  mov     r14, rcx
0x18003e251  xorps   xmm0, xmm0
0x18003e254  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18003e259  xor     r15d, r15d
0x18003e25c  mov     [rbp+57h+var_58], r15
0x18003e260  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18003e265  mov     [rbp+57h+var_40], r15
0x18003e269  lea     rcx, [rbp+57h+var_68]
0x18003e26d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e272  lea     rcx, [rbp+57h+var_50]
0x18003e276  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e27b  mov     rdx, [rbp+57h+var_68+8]
0x18003e27f  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18003e283  sub     rdx, rcx
0x18003e286  sar     rdx, 1; unsigned __int64
0x18003e289  lea     r8, aEnter; "Enter"
0x18003e290  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e295  mov     rdx, [rbp+57h+var_50+8]
0x18003e299  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18003e29d  sub     rdx, rcx
0x18003e2a0  sar     rdx, 1; unsigned __int64
0x18003e2a3  mov     rax, [rbp+57h+var_68]
0x18003e2a7  mov     [rsp+0B0h+var_88], rax
0x18003e2ac  mov     [rsp+0B0h+var_90], 715h
0x18003e2b4  lea     r9, aCwwantranslato_28; "CWwanTranslator::_ProcessConnectedProfi"...
0x18003e2bb  lea     r8, aSDS; "%S(%d):%s"
0x18003e2c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e2c7  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003e2cc  mov     ecx, [rax]
0x18003e2ce  cmp     ecx, 5
0x18003e2d1  jbe     short loc_18003E2F4
0x18003e2d3  mov     rcx, [rbp+57h+var_50]
0x18003e2d7  mov     [rbp+57h+arg_10], rcx
0x18003e2db  lea     rcx, [rbp+57h+arg_10]
0x18003e2df  mov     qword ptr [rsp+0B0h+var_90], rcx; unsigned int
0x18003e2e4  lea     rdx, byte_180076F19
0x18003e2eb  mov     rcx, rax
0x18003e2ee  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003e2f3  nop
0x18003e2f4  lea     rcx, [rbp+57h+var_50]
0x18003e2f8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e2fd  nop
0x18003e2fe  lea     rcx, [rbp+57h+var_68]
0x18003e302  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e307  test    rbx, rbx
0x18003e30a  jz      loc_18003E426
0x18003e310  cmp     [rbx], r15w
0x18003e314  jz      loc_18003E426
0x18003e31a  mov     [rbp+57h+var_70], r15
0x18003e31e  mov     [rbp+57h+var_80], r15d
0x18003e322  lea     r9, [rbp+57h+var_70]
0x18003e326  lea     r8, [rbp+57h+var_80]
0x18003e32a  xor     edx, edx
0x18003e32c  lea     ecx, [rdx+1]
0x18003e32f  call    cs:__imp_WwanOpenHandle
0x18003e335  test    eax, eax
0x18003e337  jz      short loc_18003E356
0x18003e339  mov     rcx, [rbp+5Fh]; this
0x18003e33d  mov     r9d, eax; char *
0x18003e340  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003e347  mov     edx, 71Dh; void *
0x18003e34c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e351  jmp     loc_18003E4DB
0x18003e356  lea     rax, [rbp+57h+var_70]
0x18003e35a  mov     [rbp+57h+var_68], rax
0x18003e35e  mov     byte ptr [rbp+57h+var_68+8], 1
0x18003e362  mov     dword ptr [rbp+57h+arg_10], r15d
0x18003e366  mov     qword ptr [rbp+57h+var_78], r15
0x18003e36a  lea     rax, [rbp+57h+var_78]
0x18003e36e  mov     [rbp+57h+var_50], rax
0x18003e372  mov     byte ptr [rbp+57h+var_50+8], 1
0x18003e376  mov     [rbp+57h+var_7C], r15d
0x18003e37a  lea     rax, [rbp+57h+var_78]
0x18003e37e  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18003e383  lea     r9, [rbp+57h+arg_10]
0x18003e387  lea     r8, [rbp+57h+var_7C]
0x18003e38b  mov     rdx, rbx
0x18003e38e  mov     rcx, [rbp+57h+var_70]
0x18003e392  call    cs:__imp_WwanGetProfileIstream
0x18003e398  mov     ebx, eax
0x18003e39a  test    eax, eax
0x18003e39c  jle     short loc_18003E3A7
0x18003e39e  movzx   ebx, ax
0x18003e3a1  or      ebx, 80070000h
0x18003e3a7  test    ebx, ebx
0x18003e3a9  jns     short loc_18003E3B2
0x18003e3ab  mov     edx, 727h
0x18003e3b0  jmp     short loc_18003E3C5
0x18003e3b2  cmp     dword ptr [rbp+57h+arg_10], 18D8h
0x18003e3b9  jnb     short loc_18003E3F7
0x18003e3bb  mov     ebx, 8007000Eh
0x18003e3c0  mov     edx, 728h; void *
0x18003e3c5  mov     r9d, ebx; char *
0x18003e3c8  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003e3cf  mov     rcx, [rbp+5Fh]; this
0x18003e3d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e3d8  nop
0x18003e3d9  mov     rcx, qword ptr [rbp+57h+var_78]
0x18003e3dd  call    cs:__imp_WwanFreeMemory
0x18003e3e3  nop
0x18003e3e4  xor     edx, edx
0x18003e3e6  mov     rcx, [rbp+57h+var_70]
0x18003e3ea  call    cs:__imp_WwanCloseHandle
0x18003e3f0  mov     eax, ebx
0x18003e3f2  jmp     loc_18003E4DB
0x18003e3f7  mov     byte ptr [rsp+0B0h+var_90], r15b
0x18003e3fc  mov     r9, qword ptr [rbp+57h+var_78]
0x18003e400  mov     r8d, edi
0x18003e403  mov     rdx, rsi
0x18003e406  mov     rcx, r14
0x18003e409  call    ?_ProcessWwanProfile@CWwanTranslator@@AEAAJAEBU_GUID@@W4_WWAN_ACTIVATION_STATE@@AEBUWWAN_PROFILE@@_N@Z; CWwanTranslator::_ProcessWwanProfile(_GUID const &,_WWAN_ACTIVATION_STATE,WWAN_PROFILE const &,bool)
0x18003e40e  nop
0x18003e40f  mov     rcx, qword ptr [rbp+57h+var_78]
0x18003e413  call    cs:__imp_WwanFreeMemory
0x18003e419  nop
0x18003e41a  xor     edx, edx
0x18003e41c  mov     rcx, [rbp+57h+var_70]
0x18003e420  call    cs:__imp_WwanCloseHandle
0x18003e426  xorps   xmm0, xmm0
0x18003e429  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18003e42e  mov     [rbp+57h+var_58], r15
0x18003e432  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18003e437  mov     [rbp+57h+var_40], r15
0x18003e43b  lea     rcx, [rbp+57h+var_68]
0x18003e43f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e444  lea     rcx, [rbp+57h+var_50]
0x18003e448  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003e44d  mov     rdx, [rbp+57h+var_68+8]
0x18003e451  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18003e455  sub     rdx, rcx
0x18003e458  sar     rdx, 1; unsigned __int64
0x18003e45b  lea     r8, aExit; "Exit"
0x18003e462  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e467  mov     rdx, [rbp+57h+var_50+8]
0x18003e46b  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18003e46f  sub     rdx, rcx
0x18003e472  sar     rdx, 1; unsigned __int64
0x18003e475  mov     rax, [rbp+57h+var_68]
0x18003e479  mov     [rsp+0B0h+var_88], rax
0x18003e47e  mov     [rsp+0B0h+var_90], 72Dh
0x18003e486  lea     r9, aCwwantranslato_28; "CWwanTranslator::_ProcessConnectedProfi"...
0x18003e48d  lea     r8, aSDS; "%S(%d):%s"
0x18003e494  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e499  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003e49e  mov     ecx, [rax]
0x18003e4a0  cmp     ecx, 5
0x18003e4a3  jbe     short loc_18003E4C6
0x18003e4a5  mov     rcx, [rbp+57h+var_50]
0x18003e4a9  mov     [rbp+57h+arg_10], rcx
0x18003e4ad  lea     rcx, [rbp+57h+arg_10]
0x18003e4b1  mov     qword ptr [rsp+0B0h+var_90], rcx
0x18003e4b6  lea     rdx, byte_180076ED3
0x18003e4bd  mov     rcx, rax
0x18003e4c0  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003e4c5  nop
0x18003e4c6  lea     rcx, [rbp+57h+var_50]
0x18003e4ca  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e4cf  nop
0x18003e4d0  lea     rcx, [rbp+57h+var_68]
0x18003e4d4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003e4d9  xor     eax, eax
0x18003e4db  add     rsp, 88h
0x18003e4e2  pop     r15
0x18003e4e4  pop     r14
0x18003e4e6  pop     rdi
0x18003e4e7  pop     rsi
0x18003e4e8  pop     rbx
0x18003e4e9  pop     rbp
0x18003e4ea  retn
```
