# ServiceCallbacks::GetSystemMapDataDirectory(HSTRING__ * *)

- ea: `0x180009540`
- end: `0x18000962b`
- name: `?GetSystemMapDataDirectory@ServiceCallbacks@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(ServiceCallbacks *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180001d00`
- `0x180009540`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800095a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800095a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800095c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800095c0`
- `MosStorage!MosStorageGetSystemDataDirectory` at `0x180009578`
- `MosStorage!MosStorageGetSystemDataDirectory` at `0x180009578`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800095f3`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800095f3`

## string_xrefs

- `0x1800095ea`: `ServiceCallbacks::GetSystemMapDataDirectory`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::GetSystemMapDataDirectory(ServiceCallbacks *this, HSTRING *a2)
{
  HRESULT SystemDataDirectory; // eax
  int v5; // r8d
  unsigned __int64 v6; // rbx
  unsigned int v7; // ebx
  HSTRING v8; // rax
  HSTRING string; // [rsp+20h] [rbp-248h] BYREF
  WCHAR sourceString[264]; // [rsp+30h] [rbp-238h] BYREF

  string = 0;
  SystemDataDirectory = MosStorageGetSystemDataDirectory(sourceString, 0x104u);
  if ( SystemDataDirectory < 0 )
  {
    v5 = 53;
LABEL_10:
    v7 = ZTraceReportPropagation(
           SystemDataDirectory,
           "ServiceCallbacks::GetSystemMapDataDirectory",
           v5,
           (char *)this - 8);
    goto LABEL_11;
  }
  v6 = -1;
  do
    ++v6;
  while ( sourceString[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    SystemDataDirectory = -2147024362;
    goto LABEL_9;
  }
  WindowsDeleteString(string);
  string = 0;
  SystemDataDirectory = WindowsCreateString(sourceString, v6, &string);
  if ( SystemDataDirectory < 0 )
  {
LABEL_9:
    v5 = 55;
    goto LABEL_10;
  }
  v7 = 0;
  v8 = string;
  string = 0;
  *a2 = v8;
LABEL_11:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x180009540  mov     [rsp+arg_10], rbx
0x180009545  push    rbp
0x180009546  push    rsi
0x180009547  push    rdi
0x180009548  sub     rsp, 250h
0x18000954f  mov     rax, cs:__security_cookie
0x180009556  xor     rax, rsp
0x180009559  mov     [rsp+268h+var_28], rax
0x180009561  mov     rsi, rdx
0x180009564  mov     rdi, rcx
0x180009567  xor     ebp, ebp
0x180009569  mov     [rsp+268h+string], rbp
0x18000956e  mov     edx, 104h
0x180009573  lea     rcx, [rsp+268h+sourceString]
0x180009578  call    cs:__imp_?MosStorageGetSystemDataDirectory@@YAJPEAGK@Z; MosStorageGetSystemDataDirectory(ushort *,ulong)
0x18000957e  test    eax, eax
0x180009580  jns     short loc_180009588
0x180009582  lea     r8d, [rbp+35h]
0x180009586  jmp     short loc_1800095E6
0x180009588  lea     rax, [rsp+268h+sourceString]
0x18000958d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009591  inc     rbx
0x180009594  cmp     [rax+rbx*2], bp
0x180009598  jnz     short loc_180009591
0x18000959a  mov     eax, 0FFFFFFFFh
0x18000959f  cmp     rbx, rax
0x1800095a2  ja      short loc_1800095DB
0x1800095a4  mov     rcx, [rsp+268h+string]; string
0x1800095a9  call    cs:__imp_WindowsDeleteString
0x1800095af  mov     [rsp+268h+string], rbp
0x1800095b4  mov     edx, ebx; length
0x1800095b6  lea     r8, [rsp+268h+string]; string
0x1800095bb  lea     rcx, [rsp+268h+sourceString]; sourceString
0x1800095c0  call    cs:__imp_WindowsCreateString
0x1800095c6  test    eax, eax
0x1800095c8  js      short loc_1800095E0
0x1800095ca  mov     ebx, ebp
0x1800095cc  mov     rax, [rsp+268h+string]
0x1800095d1  mov     [rsp+268h+string], rbp
0x1800095d6  mov     [rsi], rax
0x1800095d9  jmp     short loc_1800095FB
0x1800095db  mov     eax, 80070216h
0x1800095e0  mov     r8d, 37h ; '7'
0x1800095e6  lea     r9, [rdi-8]
0x1800095ea  lea     rdx, aServicecallbac; "ServiceCallbacks::GetSystemMapDataDirec"...
0x1800095f1  mov     ecx, eax
0x1800095f3  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800095f9  mov     ebx, eax
0x1800095fb  mov     rcx, [rsp+268h+string]; string
0x180009600  call    cs:__imp_WindowsDeleteString
0x180009606  mov     eax, ebx
0x180009608  mov     rcx, [rsp+268h+var_28]
0x180009610  xor     rcx, rsp; StackCookie
0x180009613  call    __security_check_cookie
0x180009618  mov     rbx, [rsp+268h+arg_10]
0x180009620  add     rsp, 250h
0x180009627  pop     rdi
0x180009628  pop     rsi
0x180009629  pop     rbp
0x18000962a  retn
```
