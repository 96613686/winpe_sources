# BuildSiufLocFolderPath(ushort *,uint)

- ea: `0x1400101fc`
- end: `0x1400103f0`
- name: `?BuildSiufLocFolderPath@@YAJPEAGI@Z`
- size: `500`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140010638`
- `0x140010acc`

## callees

- `0x140001418`
- `0x14000b904`
- `0x1400101fc`
- `0x14001522c`
- `0x1400195e2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400103c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400103c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400103d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400103d9`

## string_xrefs

- `0x140010276`: `BuildSiufLocFolderPath`
- `0x140010348`: `BuildSiufLocFolderPath`
- `0x14001029a`: `GetSiufLocPath failed.`

## pseudocode

```c
__int64 __fastcall BuildSiufLocFolderPath(unsigned __int16 *a1, int a2)
{
  int SiufLocPath; // ebx
  int v4; // r9d
  int v5; // r8d
  int v6; // ecx
  char *v7; // rdx
  const char **v8; // rax
  HANDLE ProcessHeap; // rax
  const char **v11; // [rsp+38h] [rbp-38h]
  const char *v12; // [rsp+50h] [rbp-20h] BYREF
  const char *v13; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-10h] BYREF
  int v15; // [rsp+90h] [rbp+20h] BYREF
  int v16; // [rsp+98h] [rbp+28h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+38h] BYREF

  v16 = a2;
  lpMem = 0;
  if ( !a1 )
    return (unsigned int)-2147467261;
  SiufLocPath = GetSiufLocPath((unsigned __int16 **)&lpMem);
  if ( SiufLocPath >= 0 )
  {
    memset_0(a1, 0, 0x208u);
    SiufLocPath = StringCchPrintfW(a1, 0x104u, L"%s", lpMem);
    if ( SiufLocPath < 0 && (unsigned int)dword_140028000 > 2 )
    {
      v6 = qword_140028018;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v16 = 276;
        v14[0] = "BuildSiufLocFolderPath";
        v7 = byte_140022C9D;
        v13 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
        v12 = "StringCchPrintfW failed to build loc folder string.";
        v11 = (const char **)v14;
        v8 = &v12;
        goto LABEL_13;
      }
    }
  }
  else if ( (unsigned int)dword_140028000 > 2 )
  {
    v5 = qword_140028018;
    v6 = qword_140028010;
    if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v16 = 263;
      v12 = "BuildSiufLocFolderPath";
      v7 = byte_140022CFB;
      v13 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v14[0] = "GetSiufLocPath failed.";
      v11 = &v12;
      v8 = (const char **)v14;
LABEL_13:
      v18 = 0x1000000;
      v15 = SiufLocPath;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v6,
        (_DWORD)v7,
        v5,
        v4,
        (__int64)v8,
        (__int64)&v15,
        (__int64)&v13,
        (__int64)v11,
        (__int64)&v16,
        (__int64)&v18);
    }
  }
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return (unsigned int)SiufLocPath;
}

```

## disassembly

```asm
0x1400101fc  mov     [rsp-18h+arg_8], edx
0x140010200  push    rbp
0x140010201  push    rbx
0x140010202  push    rdi
0x140010203  mov     rbp, rsp
0x140010206  sub     rsp, 70h
0x14001020a  mov     [rbp+lpMem], 0
0x140010212  mov     rdi, rcx
0x140010215  test    rcx, rcx
0x140010218  jnz     short loc_140010224
0x14001021a  mov     ebx, 80004003h
0x14001021f  jmp     loc_1400103E5
0x140010224  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x140010228  call    ?GetSiufLocPath@@YAJPEAPEAG@Z; GetSiufLocPath(ushort * *)
0x14001022d  mov     ebx, eax
0x14001022f  test    eax, eax
0x140010231  jns     loc_1400102DB
0x140010237  mov     ecx, cs:dword_140028000
0x14001023d  cmp     ecx, 2
0x140010240  jbe     loc_1400103BD
0x140010246  mov     r8, cs:qword_140028018
0x14001024d  mov     rdx, 400000000000h
0x140010257  mov     rcx, cs:qword_140028010
0x14001025e  test    rdx, rcx
0x140010261  jz      loc_1400103BD
0x140010267  mov     rax, r8
0x14001026a  and     rax, rdx
0x14001026d  cmp     rax, r8
0x140010270  jnz     loc_1400103BD
0x140010276  lea     rax, aBuildsiuflocfo; "BuildSiufLocFolderPath"
0x14001027d  mov     [rbp+arg_8], 107h
0x140010284  mov     [rbp+var_20], rax
0x140010288  lea     rdx, byte_140022CFB
0x14001028f  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010296  mov     [rbp+var_18], rax
0x14001029a  lea     rax, aGetsiuflocpath; "GetSiufLocPath failed."
0x1400102a1  mov     [rbp+var_10], rax
0x1400102a5  lea     rax, [rbp+arg_18]
0x1400102a9  mov     [rsp+70h+var_28], rax
0x1400102ae  lea     rax, [rbp+arg_8]
0x1400102b2  mov     [rsp+70h+var_30], rax
0x1400102b7  lea     rax, [rbp+var_20]
0x1400102bb  mov     [rsp+70h+var_38], rax
0x1400102c0  lea     rax, [rbp+var_18]
0x1400102c4  mov     [rsp+70h+var_40], rax
0x1400102c9  lea     rax, [rbp+arg_0]
0x1400102cd  mov     [rsp+70h+var_48], rax
0x1400102d2  lea     rax, [rbp+var_10]
0x1400102d6  jmp     loc_1400103A8
0x1400102db  xor     edx, edx; Val
0x1400102dd  mov     r8d, 208h; Size
0x1400102e3  mov     rcx, rdi; void *
0x1400102e6  call    memset_0
0x1400102eb  mov     r9, [rbp+lpMem]
0x1400102ef  lea     r8, aS; "%s"
0x1400102f6  mov     edx, 104h; unsigned __int64
0x1400102fb  mov     rcx, rdi; unsigned __int16 *
0x1400102fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010303  mov     ebx, eax
0x140010305  test    eax, eax
0x140010307  jns     loc_1400103BD
0x14001030d  mov     eax, cs:dword_140028000
0x140010313  cmp     eax, 2
0x140010316  jbe     loc_1400103BD
0x14001031c  mov     rcx, cs:qword_140028018
0x140010323  mov     rdx, 400000000000h
0x14001032d  mov     rax, cs:qword_140028010
0x140010334  test    rdx, rax
0x140010337  jz      loc_1400103BD
0x14001033d  mov     rax, rcx
0x140010340  and     rax, rdx
0x140010343  cmp     rax, rcx
0x140010346  jnz     short loc_1400103BD
0x140010348  lea     rax, aBuildsiuflocfo; "BuildSiufLocFolderPath"
0x14001034f  mov     [rbp+arg_8], 114h
0x140010356  mov     [rbp+var_10], rax
0x14001035a  lea     rdx, byte_140022C9D
0x140010361  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010368  mov     [rbp+var_18], rax
0x14001036c  lea     rax, aStringcchprint_1; "StringCchPrintfW failed to build loc fo"...
0x140010373  mov     [rbp+var_20], rax
0x140010377  lea     rax, [rbp+arg_18]
0x14001037b  mov     [rsp+70h+var_28], rax
0x140010380  lea     rax, [rbp+arg_8]
0x140010384  mov     [rsp+70h+var_30], rax
0x140010389  lea     rax, [rbp+var_10]
0x14001038d  mov     [rsp+70h+var_38], rax
0x140010392  lea     rax, [rbp+var_18]
0x140010396  mov     [rsp+70h+var_40], rax
0x14001039b  lea     rax, [rbp+arg_0]
0x14001039f  mov     [rsp+70h+var_48], rax
0x1400103a4  lea     rax, [rbp+var_20]
0x1400103a8  mov     [rsp+70h+var_50], rax
0x1400103ad  mov     [rbp+arg_18], 1000000h
0x1400103b5  mov     [rbp+arg_0], ebx
0x1400103b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400103bd  cmp     [rbp+lpMem], 0
0x1400103c2  jz      short loc_1400103E5
0x1400103c4  call    cs:__imp_GetProcessHeap
0x1400103cb  nop     dword ptr [rax+rax+00h]
0x1400103d0  mov     r8, [rbp+lpMem]; lpMem
0x1400103d4  xor     edx, edx; dwFlags
0x1400103d6  mov     rcx, rax; hHeap
0x1400103d9  call    cs:__imp_HeapFree
0x1400103e0  nop     dword ptr [rax+rax+00h]
0x1400103e5  mov     eax, ebx
0x1400103e7  add     rsp, 70h
0x1400103eb  pop     rdi
0x1400103ec  pop     rbx
0x1400103ed  pop     rbp
0x1400103ee  retn
```
