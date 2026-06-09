# PlaiGetFileSize(ushort const *,__int64 *)

- ea: `0x1800f2240`
- end: `0x1800f24b1`
- name: `?PlaiGetFileSize@@YAJPEBGPEA_J@Z`
- size: `625`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800be5d4`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800f2240`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f22aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f23d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f22aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f23d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f23a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f23a8`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800f2391`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800f2391`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f2294`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f2294`

## pseudocode

```c
__int64 __fastcall PlaiGetFileSize(const unsigned __int16 *a1, union _LARGE_INTEGER *a2)
{
  HANDLE FileW; // rax
  __int64 v4; // rbx
  void *v5; // rsi
  DWORD v6; // eax
  unsigned int v7; // edi
  DWORD LastError; // eax
  int v10; // eax
  int v11; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v12; // [rsp+78h] [rbp-88h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v14[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v15[64]; // [rsp+110h] [rbp+10h] BYREF

  FileSize.QuadPart = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v4 = -1;
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = PlaiHResultFromWin32(LastError);
      v7 = v10;
      if ( v10 < 0 )
      {
        v12 = 0;
        v11 = v10;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v15, 0x4000000000000800uLL);
          do
            ++v4;
          while ( v15[v4] );
          EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v11);
        }
        goto LABEL_11;
      }
    }
    *a2 = FileSize;
LABEL_11:
    CloseHandle(v5);
    return v7;
  }
  v6 = GetLastError();
  v7 = PlaiHResultFromWin32(v6);
  v11 = 0;
  v12 = v7;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v14, 0x4000000000000800uLL);
    do
      ++v4;
    while ( v14[v4] );
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v12);
  }
  return v7;
}

```

## disassembly

```asm
0x1800f2240  mov     [rsp-8+arg_10], rbx
0x1800f2245  push    rbp
0x1800f2246  push    rsi
0x1800f2247  push    rdi
0x1800f2248  push    r14
0x1800f224a  push    r15
0x1800f224c  lea     rbp, [rsp-0A0h]
0x1800f2254  sub     rsp, 1A0h
0x1800f225b  mov     rax, cs:__security_cookie
0x1800f2262  xor     rax, rsp
0x1800f2265  mov     [rbp+0C0h+var_30], rax
0x1800f226c  xor     r15d, r15d
0x1800f226f  mov     r14, rdx
0x1800f2272  mov     [rsp+1C0h+hTemplateFile], r15; hTemplateFile
0x1800f2277  xor     r9d, r9d; lpSecurityAttributes
0x1800f227a  mov     [rsp+1C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f2282  mov     edx, 80000000h; dwDesiredAccess
0x1800f2287  mov     qword ptr [rbp+0C0h+FileSize], r15
0x1800f228b  lea     r8d, [r15+3]; dwShareMode
0x1800f228f  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800f2294  call    cs:__imp_CreateFileW
0x1800f229a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f229e  mov     rsi, rax
0x1800f22a1  cmp     rax, rbx
0x1800f22a4  jnz     loc_1800F238A
0x1800f22aa  call    cs:__imp_GetLastError
0x1800f22b0  mov     ecx, eax; unsigned int
0x1800f22b2  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f22b7  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f22be  mov     edi, eax
0x1800f22c0  mov     [rsp+1C0h+var_150], r15d
0x1800f22c5  mov     [rsp+1C0h+var_148], eax
0x1800f22c9  jz      loc_1800F23AE
0x1800f22cf  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f22d9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f22e0  jz      loc_1800F23AE
0x1800f22e6  mov     rax, cs:qword_180169748
0x1800f22ed  and     rax, rdx
0x1800f22f0  cmp     cs:qword_180169748, rax
0x1800f22f7  jnz     loc_1800F23AE
0x1800f22fd  lea     rcx, [rbp+0C0h+var_130]; unsigned __int16 *
0x1800f2301  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f2306  lea     rax, [rbp+0C0h+var_130]
0x1800f230a  inc     rbx
0x1800f230d  cmp     [rax+rbx*2], r15w
0x1800f2312  jnz     short loc_1800F230A
0x1800f2314  lea     rax, [rbp+0C0h+var_130]
0x1800f2318  lea     ecx, [rbx+rbx]
0x1800f231b  add     rcx, 2
0x1800f231f  lea     r9, [rsp+1C0h+var_148]
0x1800f2324  mov     [rsp+1C0h+var_160], rcx
0x1800f2329  lea     rdx, PLA_EVENT_ERROR
0x1800f2330  mov     [rsp+1C0h+var_168], rax
0x1800f2335  lea     rcx, [rsp+1C0h+var_150]
0x1800f233a  mov     [rsp+1C0h+var_170], 10h
0x1800f2343  lea     rax, aPlaigetfilesiz; "PlaiGetFileSize"
0x1800f234a  mov     [rsp+1C0h+var_178], rax
0x1800f234f  mov     eax, 4
0x1800f2354  mov     [rsp+1C0h+var_180], rax
0x1800f2359  mov     [rsp+1C0h+var_188], rcx
0x1800f235e  lea     rcx, qword_180147320
0x1800f2365  mov     [rsp+1C0h+hTemplateFile], 1
0x1800f236e  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rcx
0x1800f2373  lea     r8d, [rax+1]
0x1800f2377  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f237e  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax
0x1800f2383  call    EventingWriteEvent
0x1800f2388  jmp     short loc_1800F23AE
0x1800f238a  lea     rdx, [rbp+0C0h+FileSize]; lpFileSize
0x1800f238e  mov     rcx, rsi; hFile
0x1800f2391  call    cs:__imp_GetFileSizeEx
0x1800f2397  test    eax, eax
0x1800f2399  jz      short loc_1800F23D6
0x1800f239b  mov     edi, r15d
0x1800f239e  mov     rcx, qword ptr [rbp+0C0h+FileSize]
0x1800f23a2  mov     [r14], rcx
0x1800f23a5  mov     rcx, rsi; hObject
0x1800f23a8  call    cs:__imp_CloseHandle
0x1800f23ae  mov     eax, edi
0x1800f23b0  mov     rcx, [rbp+0C0h+var_30]
0x1800f23b7  xor     rcx, rsp; StackCookie
0x1800f23ba  call    __security_check_cookie
0x1800f23bf  mov     rbx, [rsp+1C0h+arg_10]
0x1800f23c7  add     rsp, 1A0h
0x1800f23ce  pop     r15
0x1800f23d0  pop     r14
0x1800f23d2  pop     rdi
0x1800f23d3  pop     rsi
0x1800f23d4  pop     rbp
0x1800f23d5  retn
0x1800f23d6  call    cs:__imp_GetLastError
0x1800f23dc  mov     ecx, eax; unsigned int
0x1800f23de  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f23e3  mov     edi, eax
0x1800f23e5  test    eax, eax
0x1800f23e7  jns     short loc_1800F239E
0x1800f23e9  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f23f0  mov     [rsp+1C0h+var_148], r15d
0x1800f23f5  mov     [rsp+1C0h+var_150], eax
0x1800f23f9  jz      short loc_1800F23A5
0x1800f23fb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f2405  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f240c  jz      short loc_1800F23A5
0x1800f240e  mov     rax, cs:qword_180169748
0x1800f2415  and     rax, rdx
0x1800f2418  cmp     cs:qword_180169748, rax
0x1800f241f  jnz     short loc_1800F23A5
0x1800f2421  lea     rcx, [rbp+0C0h+var_B0]; unsigned __int16 *
0x1800f2425  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f242a  lea     rax, [rbp+0C0h+var_B0]
0x1800f242e  inc     rbx
0x1800f2431  cmp     [rax+rbx*2], r15w
0x1800f2436  jnz     short loc_1800F242E
0x1800f2438  lea     rax, [rbp+0C0h+var_B0]
0x1800f243c  lea     ecx, [rbx+rbx]
0x1800f243f  add     rcx, 2
0x1800f2443  lea     r9, [rsp+1C0h+var_150]
0x1800f2448  mov     [rsp+1C0h+var_160], rcx
0x1800f244d  lea     rdx, PLA_EVENT_ERROR
0x1800f2454  mov     [rsp+1C0h+var_168], rax
0x1800f2459  lea     rcx, [rsp+1C0h+var_148]
0x1800f245e  mov     [rsp+1C0h+var_170], 10h
0x1800f2467  lea     rax, aPlaigetfilesiz; "PlaiGetFileSize"
0x1800f246e  mov     [rsp+1C0h+var_178], rax
0x1800f2473  mov     eax, 4
0x1800f2478  mov     [rsp+1C0h+var_180], rax
0x1800f247d  mov     [rsp+1C0h+var_188], rcx
0x1800f2482  lea     rcx, qword_180147320
0x1800f2489  mov     [rsp+1C0h+hTemplateFile], 1
0x1800f2492  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rcx
0x1800f2497  lea     r8d, [rax+1]
0x1800f249b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f24a2  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax
0x1800f24a7  call    EventingWriteEvent
0x1800f24ac  jmp     loc_1800F23A5
```
