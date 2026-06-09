# BuildSiufLocFolderPath(ushort *,uint)

- ea: `0x14000fc30`
- end: `0x14000fe17`
- name: `?BuildSiufLocFolderPath@@YAJPEAGI@Z`
- size: `487`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140010050`
- `0x140010470`

## callees

- `0x140001414`
- `0x14000b5c4`
- `0x14000fc30`
- `0x140017468`
- `0x1400187b2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fdf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fdf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fe07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fe07`

## string_xrefs

- `0x14000fcaa`: `BuildSiufLocFolderPath`
- `0x14000fd7c`: `BuildSiufLocFolderPath`
- `0x14000fcce`: `GetSiufLocPath failed.`

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
    if ( SiufLocPath < 0 && (unsigned int)dword_140027000 > 2 )
    {
      v6 = qword_140027018;
      if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v16 = 276;
        v14[0] = "BuildSiufLocFolderPath";
        v7 = byte_140021C95;
        v13 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
        v12 = "StringCchPrintfW failed to build loc folder string.";
        v11 = (const char **)v14;
        v8 = &v12;
        goto LABEL_13;
      }
    }
  }
  else if ( (unsigned int)dword_140027000 > 2 )
  {
    v5 = qword_140027018;
    v6 = qword_140027010;
    if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v16 = 263;
      v12 = "BuildSiufLocFolderPath";
      v7 = byte_140021CF3;
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
0x14000fc30  mov     [rsp-18h+arg_8], edx
0x14000fc34  push    rbp
0x14000fc35  push    rbx
0x14000fc36  push    rdi
0x14000fc37  mov     rbp, rsp
0x14000fc3a  sub     rsp, 70h
0x14000fc3e  mov     [rbp+lpMem], 0
0x14000fc46  mov     rdi, rcx
0x14000fc49  test    rcx, rcx
0x14000fc4c  jnz     short loc_14000FC58
0x14000fc4e  mov     ebx, 80004003h
0x14000fc53  jmp     loc_14000FE0D
0x14000fc58  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x14000fc5c  call    ?GetSiufLocPath@@YAJPEAPEAG@Z; GetSiufLocPath(ushort * *)
0x14000fc61  mov     ebx, eax
0x14000fc63  test    eax, eax
0x14000fc65  jns     loc_14000FD0F
0x14000fc6b  mov     ecx, cs:dword_140027000
0x14000fc71  cmp     ecx, 2
0x14000fc74  jbe     loc_14000FDF1
0x14000fc7a  mov     r8, cs:qword_140027018
0x14000fc81  mov     rdx, 400000000000h
0x14000fc8b  mov     rcx, cs:qword_140027010
0x14000fc92  test    rdx, rcx
0x14000fc95  jz      loc_14000FDF1
0x14000fc9b  mov     rax, r8
0x14000fc9e  and     rax, rdx
0x14000fca1  cmp     rax, r8
0x14000fca4  jnz     loc_14000FDF1
0x14000fcaa  lea     rax, aBuildsiuflocfo; "BuildSiufLocFolderPath"
0x14000fcb1  mov     [rbp+arg_8], 107h
0x14000fcb8  mov     [rbp+var_20], rax
0x14000fcbc  lea     rdx, byte_140021CF3
0x14000fcc3  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000fcca  mov     [rbp+var_18], rax
0x14000fcce  lea     rax, aGetsiuflocpath; "GetSiufLocPath failed."
0x14000fcd5  mov     [rbp+var_10], rax
0x14000fcd9  lea     rax, [rbp+arg_18]
0x14000fcdd  mov     [rsp+70h+var_28], rax
0x14000fce2  lea     rax, [rbp+arg_8]
0x14000fce6  mov     [rsp+70h+var_30], rax
0x14000fceb  lea     rax, [rbp+var_20]
0x14000fcef  mov     [rsp+70h+var_38], rax
0x14000fcf4  lea     rax, [rbp+var_18]
0x14000fcf8  mov     [rsp+70h+var_40], rax
0x14000fcfd  lea     rax, [rbp+arg_0]
0x14000fd01  mov     [rsp+70h+var_48], rax
0x14000fd06  lea     rax, [rbp+var_10]
0x14000fd0a  jmp     loc_14000FDDC
0x14000fd0f  xor     edx, edx; Val
0x14000fd11  mov     r8d, 208h; Size
0x14000fd17  mov     rcx, rdi; void *
0x14000fd1a  call    memset_0
0x14000fd1f  mov     r9, [rbp+lpMem]
0x14000fd23  lea     r8, aS; "%s"
0x14000fd2a  mov     edx, 104h; unsigned __int64
0x14000fd2f  mov     rcx, rdi; unsigned __int16 *
0x14000fd32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fd37  mov     ebx, eax
0x14000fd39  test    eax, eax
0x14000fd3b  jns     loc_14000FDF1
0x14000fd41  mov     eax, cs:dword_140027000
0x14000fd47  cmp     eax, 2
0x14000fd4a  jbe     loc_14000FDF1
0x14000fd50  mov     rcx, cs:qword_140027018
0x14000fd57  mov     rdx, 400000000000h
0x14000fd61  mov     rax, cs:qword_140027010
0x14000fd68  test    rdx, rax
0x14000fd6b  jz      loc_14000FDF1
0x14000fd71  mov     rax, rcx
0x14000fd74  and     rax, rdx
0x14000fd77  cmp     rax, rcx
0x14000fd7a  jnz     short loc_14000FDF1
0x14000fd7c  lea     rax, aBuildsiuflocfo; "BuildSiufLocFolderPath"
0x14000fd83  mov     [rbp+arg_8], 114h
0x14000fd8a  mov     [rbp+var_10], rax
0x14000fd8e  lea     rdx, byte_140021C95
0x14000fd95  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000fd9c  mov     [rbp+var_18], rax
0x14000fda0  lea     rax, aStringcchprint_1; "StringCchPrintfW failed to build loc fo"...
0x14000fda7  mov     [rbp+var_20], rax
0x14000fdab  lea     rax, [rbp+arg_18]
0x14000fdaf  mov     [rsp+70h+var_28], rax
0x14000fdb4  lea     rax, [rbp+arg_8]
0x14000fdb8  mov     [rsp+70h+var_30], rax
0x14000fdbd  lea     rax, [rbp+var_10]
0x14000fdc1  mov     [rsp+70h+var_38], rax
0x14000fdc6  lea     rax, [rbp+var_18]
0x14000fdca  mov     [rsp+70h+var_40], rax
0x14000fdcf  lea     rax, [rbp+arg_0]
0x14000fdd3  mov     [rsp+70h+var_48], rax
0x14000fdd8  lea     rax, [rbp+var_20]
0x14000fddc  mov     [rsp+70h+var_50], rax
0x14000fde1  mov     [rbp+arg_18], 1000000h
0x14000fde9  mov     [rbp+arg_0], ebx
0x14000fdec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000fdf1  cmp     [rbp+lpMem], 0
0x14000fdf6  jz      short loc_14000FE0D
0x14000fdf8  call    cs:__imp_GetProcessHeap
0x14000fdfe  mov     r8, [rbp+lpMem]; lpMem
0x14000fe02  xor     edx, edx; dwFlags
0x14000fe04  mov     rcx, rax; hHeap
0x14000fe07  call    cs:__imp_HeapFree
0x14000fe0d  mov     eax, ebx
0x14000fe0f  add     rsp, 70h
0x14000fe13  pop     rdi
0x14000fe14  pop     rbx
0x14000fe15  pop     rbp
0x14000fe16  retn
```
