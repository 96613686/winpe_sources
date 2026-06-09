# _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x18001ae54`
- end: `0x18001af91`
- name: `?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `317`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, wchar_t *, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001ace4`
- `0x18001ae54`

## callees

- `0x1800011dc`
- `0x18001ae54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af5a`
- `ntdll!wcsrchr` at `0x18001af0c`
- `ntdll!wcsrchr` at `0x18001af0c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001aec8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001af43`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001aec8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001af43`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001aee6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001aee6`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilEnsureDirectoryWorker(
        wchar_t *lpPathName,
        wchar_t *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        int a4)
{
  int v4; // ebx
  unsigned int v6; // ebx
  DWORD LastError; // eax
  const WCHAR *v8; // rcx
  DWORD FileAttributesW; // eax
  wchar_t *v10; // rsi
  unsigned int v11; // r9d
  int v12; // eax
  signed int v13; // eax
  wchar_t *v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = a2;
  v4 = (int)a3;
  if ( (unsigned int)a3 > 0x1E )
  {
    v6 = -2147024735;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      v15 = lpPathName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_180062018,
        (unsigned int)&unk_180057DF8,
        (_DWORD)a3,
        a4,
        (__int64)&v15);
    }
    return v6;
  }
  if ( CreateDirectoryW(lpPathName, 0) )
    return 0;
  LastError = GetLastError();
  v8 = lpPathName;
  if ( LastError == 183 )
  {
LABEL_8:
    FileAttributesW = GetFileAttributesW(v8);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      return (unsigned int)-2147024816;
    return 0;
  }
  v10 = wcsrchr(lpPathName, 0x5Cu);
  if ( !v10 )
    return (unsigned int)-2147024893;
  *v10 = 0;
  v12 = _werDetail::UtilEnsureDirectoryWorker(lpPathName, 0, (struct _SECURITY_ATTRIBUTES *)(unsigned int)(v4 + 1), v11);
  *v10 = 92;
  v6 = v12;
  if ( v12 < 0 )
    return v6;
  if ( CreateDirectoryW(lpPathName, 0) )
    return 0;
  if ( GetLastError() == 183 )
  {
    v8 = lpPathName;
    goto LABEL_8;
  }
  v13 = GetLastError();
  v6 = v13;
  if ( v13 > 0 )
    v6 = (unsigned __int16)v13 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
    return (unsigned int)-2147467259;
  return v6;
}

```

## disassembly

```asm
0x18001ae54  mov     r11, rsp
0x18001ae57  mov     [r11+10h], rdx
0x18001ae5b  push    rbx
0x18001ae5c  push    rsi
0x18001ae5d  push    rdi
0x18001ae5e  push    r14
0x18001ae60  sub     rsp, 38h
0x18001ae64  mov     ebx, r8d
0x18001ae67  mov     rdi, rcx
0x18001ae6a  cmp     r8d, 1Eh
0x18001ae6e  jbe     short loc_18001AEC6
0x18001ae70  mov     eax, cs:dword_180062000
0x18001ae76  mov     ebx, 800700A1h
0x18001ae7b  cmp     eax, 2
0x18001ae7e  jbe     loc_18001AF85
0x18001ae84  mov     rcx, cs:qword_180062018
0x18001ae8b  mov     rax, cs:qword_180062010
0x18001ae92  test    al, 8
0x18001ae94  jz      loc_18001AF85
0x18001ae9a  mov     rax, rcx
0x18001ae9d  and     eax, 8
0x18001aea0  cmp     rax, rcx
0x18001aea3  jnz     loc_18001AF85
0x18001aea9  lea     rax, [r11+10h]
0x18001aead  mov     [r11+10h], rdi
0x18001aeb1  lea     rdx, unk_180057DF8
0x18001aeb8  mov     [r11-38h], rax
0x18001aebc  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001aec1  jmp     loc_18001AF85
0x18001aec6  xor     edx, edx; lpSecurityAttributes
0x18001aec8  call    cs:__imp_CreateDirectoryW
0x18001aece  test    eax, eax
0x18001aed0  jnz     loc_18001AF83
0x18001aed6  call    cs:__imp_GetLastError
0x18001aedc  mov     rcx, rdi; Str
0x18001aedf  cmp     eax, 0B7h
0x18001aee4  jnz     short loc_18001AF03
0x18001aee6  call    cs:__imp_GetFileAttributesW
0x18001aeec  cmp     eax, 0FFFFFFFFh
0x18001aeef  jz      short loc_18001AEF9
0x18001aef1  test    al, 10h
0x18001aef3  jnz     loc_18001AF83
0x18001aef9  mov     ebx, 80070050h
0x18001aefe  jmp     loc_18001AF85
0x18001af03  mov     r14d, 5Ch ; '\'
0x18001af09  mov     edx, r14d; Ch
0x18001af0c  call    cs:__imp_wcsrchr
0x18001af12  mov     rsi, rax
0x18001af15  test    rax, rax
0x18001af18  jnz     short loc_18001AF21
0x18001af1a  mov     ebx, 80070003h
0x18001af1f  jmp     short loc_18001AF85
0x18001af21  xor     eax, eax
0x18001af23  lea     r8d, [rbx+1]; struct _SECURITY_ATTRIBUTES *
0x18001af27  xor     edx, edx; wchar_t *
0x18001af29  mov     [rsi], ax
0x18001af2c  mov     rcx, rdi; lpPathName
0x18001af2f  call    ?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z; _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)
0x18001af34  mov     [rsi], r14w
0x18001af38  mov     ebx, eax
0x18001af3a  test    eax, eax
0x18001af3c  js      short loc_18001AF85
0x18001af3e  xor     edx, edx; lpSecurityAttributes
0x18001af40  mov     rcx, rdi; lpPathName
0x18001af43  call    cs:__imp_CreateDirectoryW
0x18001af49  test    eax, eax
0x18001af4b  jnz     short loc_18001AF83
0x18001af4d  call    cs:__imp_GetLastError
0x18001af53  cmp     eax, 0B7h
0x18001af58  jz      short loc_18001AF7B
0x18001af5a  call    cs:__imp_GetLastError
0x18001af60  mov     ebx, eax
0x18001af62  test    eax, eax
0x18001af64  jle     short loc_18001AF6F
0x18001af66  movzx   ebx, ax
0x18001af69  or      ebx, 80070000h
0x18001af6f  test    ebx, ebx
0x18001af71  mov     eax, 80004005h
0x18001af76  cmovns  ebx, eax
0x18001af79  jmp     short loc_18001AF85
0x18001af7b  mov     rcx, rdi
0x18001af7e  jmp     loc_18001AEE6
0x18001af83  xor     ebx, ebx
0x18001af85  mov     eax, ebx
0x18001af87  add     rsp, 38h
0x18001af8b  pop     r14
0x18001af8d  pop     rdi
0x18001af8e  pop     rsi
0x18001af8f  pop     rbx
0x18001af90  retn
```
