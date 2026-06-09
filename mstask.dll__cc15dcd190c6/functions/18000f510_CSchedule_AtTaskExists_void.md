# CSchedule::_AtTaskExists(void)

- ea: `0x18000f510`
- end: `0x18000f600`
- name: `?_AtTaskExists@CSchedule@@AEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000e7f8`

## callees

- `0x18000865c`
- `0x18000c8a4`
- `0x18000c93c`
- `0x18000f510`
- `0x18001aa9a`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000f5af`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000f5af`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000f552`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000f552`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f5c4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000f5c4`

## pseudocode

```c
__int64 __fastcall CSchedule::_AtTaskExists(CSchedule *this)
{
  HANDLE FirstFileW; // rsi
  struct CJob *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(g_wszAtJobSearchPath, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return 1;
  v3 = CJob::Create();
  if ( !v3 )
    return 2147942414LL;
  v4 = 1;
  while ( 1 )
  {
    if ( !(unsigned int)IsValidAtFilename(FindFileData.cFileName) )
      goto LABEL_9;
    v5 = LoadAtJob(v3, FindFileData.cFileName);
    if ( v5 < 0 )
      break;
    if ( (*((_DWORD *)v3 + 22) & 0x200000) != 0 )
    {
      v4 = 0;
      goto LABEL_13;
    }
LABEL_9:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_13;
  }
  v4 = v5;
LABEL_13:
  FindClose(FirstFileW);
  (*(void (__fastcall **)(struct CJob *))(*(_QWORD *)v3 + 16LL))(v3);
  return v4;
}

```

## disassembly

```asm
0x18000f510  mov     [rsp+arg_0], rbx
0x18000f515  mov     [rsp+arg_8], rsi
0x18000f51a  push    rdi
0x18000f51b  sub     rsp, 280h
0x18000f522  mov     rax, cs:__security_cookie
0x18000f529  xor     rax, rsp
0x18000f52c  mov     [rsp+288h+var_18], rax
0x18000f534  xor     edx, edx; Val
0x18000f536  lea     rcx, [rsp+288h+FindFileData]; void *
0x18000f53b  mov     r8d, 250h; Size
0x18000f541  call    memset_0
0x18000f546  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x18000f54b  lea     rcx, ?g_wszAtJobSearchPath@@3PAGA; lpFileName
0x18000f552  call    cs:__imp_FindFirstFileW
0x18000f558  mov     rsi, rax
0x18000f55b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f55f  jnz     short loc_18000F566
0x18000f561  lea     eax, [rsi+2]
0x18000f564  jmp     short loc_18000F5DB
0x18000f566  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x18000f56b  mov     rdi, rax
0x18000f56e  test    rax, rax
0x18000f571  jnz     short loc_18000F57A
0x18000f573  mov     eax, 8007000Eh
0x18000f578  jmp     short loc_18000F5DB
0x18000f57a  mov     ebx, 1
0x18000f57f  lea     rcx, [rsp+288h+FindFileData.cFileName]; unsigned __int16 *
0x18000f584  call    ?IsValidAtFilename@@YAHPEBG@Z; IsValidAtFilename(ushort const *)
0x18000f589  test    eax, eax
0x18000f58b  jz      short loc_18000F5A7
0x18000f58d  lea     rdx, [rsp+288h+FindFileData.cFileName]; unsigned __int16 *
0x18000f592  mov     rcx, rdi; this
0x18000f595  call    ?LoadAtJob@@YAJPEAVCJob@@PEAG@Z; LoadAtJob(CJob *,ushort *)
0x18000f59a  test    eax, eax
0x18000f59c  js      short loc_18000F5BF
0x18000f59e  test    dword ptr [rdi+58h], 200000h
0x18000f5a5  jnz     short loc_18000F5BB
0x18000f5a7  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x18000f5ac  mov     rcx, rsi; hFindFile
0x18000f5af  call    cs:__imp_FindNextFileW
0x18000f5b5  test    eax, eax
0x18000f5b7  jnz     short loc_18000F57F
0x18000f5b9  jmp     short loc_18000F5C1
0x18000f5bb  xor     ebx, ebx
0x18000f5bd  jmp     short loc_18000F5C1
0x18000f5bf  mov     ebx, eax
0x18000f5c1  mov     rcx, rsi; hFindFile
0x18000f5c4  call    cs:__imp_FindClose
0x18000f5ca  mov     rcx, [rdi]
0x18000f5cd  mov     rax, [rcx+10h]
0x18000f5d1  mov     rcx, rdi
0x18000f5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d9  mov     eax, ebx
0x18000f5db  mov     rcx, [rsp+288h+var_18]
0x18000f5e3  xor     rcx, rsp; StackCookie
0x18000f5e6  call    __security_check_cookie
0x18000f5eb  lea     r11, [rsp+288h+var_8]
0x18000f5f3  mov     rbx, [r11+10h]
0x18000f5f7  mov     rsi, [r11+18h]
0x18000f5fb  mov     rsp, r11
0x18000f5fe  pop     rdi
0x18000f5ff  retn
```
