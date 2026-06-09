# InitializeJobManager(_REG_FAX_SERVICE *)

- ea: `0x1400326fc`
- end: `0x140032815`
- name: `?InitializeJobManager@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400472a0`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x1400326fc`
- `0x140065df8`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140032770`
- `KERNEL32!GetLastError` at `0x1400327d4`
- `KERNEL32!GetLastError` at `0x140032770`
- `KERNEL32!GetLastError` at `0x1400327d4`
- `KERNEL32!CreateIoCompletionPort` at `0x14003275a`
- `KERNEL32!CreateIoCompletionPort` at `0x14003275a`

## pseudocode

```c
__int64 __fastcall InitializeJobManager(struct _REG_FAX_SERVICE *a1)
{
  unsigned int v1; // ebx
  DWORD v2; // eax
  DWORD LastError; // [rsp+30h] [rbp-38h]
  unsigned __int16 v5[14]; // [rsp+34h] [rbp-34h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v1 = 1;
  g_StatusCompletionPortHandle = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  if ( !g_StatusCompletionPortHandle )
  {
    LastError = GetLastError();
    v5[0] = 0;
    StringCchPrintfW(v5, 0xCu, L"%ld", LastError);
    FaxLog(1, 1, 1, 3221257516LL);
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v2);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x1400326fc  mov     [rsp+arg_0], rbx
0x140032701  push    rdi
0x140032702  sub     rsp, 60h
0x140032706  mov     rax, cs:__security_cookie
0x14003270d  xor     rax, rsp
0x140032710  mov     [rsp+68h+var_18], rax
0x140032715  mov     rcx, cs:WPP_GLOBAL_Control
0x14003271c  lea     rdi, WPP_GLOBAL_Control
0x140032723  cmp     rcx, rdi
0x140032726  jz      short loc_140032749
0x140032728  test    byte ptr [rcx+1Ch], 4
0x14003272c  jz      short loc_140032749
0x14003272e  cmp     byte ptr [rcx+19h], 5
0x140032732  jb      short loc_140032749
0x140032734  mov     rcx, [rcx+10h]
0x140032738  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003273f  mov     edx, 87h
0x140032744  call    WPP_SF_
0x140032749  mov     ebx, 1
0x14003274e  xor     r8d, r8d; CompletionKey
0x140032751  mov     r9d, ebx; NumberOfConcurrentThreads
0x140032754  xor     edx, edx; ExistingCompletionPort
0x140032756  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14003275a  call    cs:__imp_CreateIoCompletionPort
0x140032760  mov     cs:?g_StatusCompletionPortHandle@@3PEAXEA, rax; void * g_StatusCompletionPortHandle
0x140032767  test    rax, rax
0x14003276a  jnz     loc_1400327FB
0x140032770  call    cs:__imp_GetLastError
0x140032776  xor     ecx, ecx
0x140032778  lea     r8, aLd; "%ld"
0x14003277f  lea     edx, [rbx+0Bh]; unsigned __int64
0x140032782  mov     [rsp+68h+var_38], eax
0x140032786  mov     [rsp+68h+var_34], cx
0x14003278b  mov     r9d, eax
0x14003278e  lea     rcx, [rsp+68h+var_34]; unsigned __int16 *
0x140032793  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140032798  xor     ecx, ecx
0x14003279a  lea     rdx, [rsp+68h+var_34]
0x14003279f  test    eax, eax
0x1400327a1  mov     r9d, 0C0007D2Ch
0x1400327a7  mov     r8d, ebx
0x1400327aa  cmovs   rdx, rcx
0x1400327ae  mov     ecx, ebx
0x1400327b0  mov     [rsp+68h+var_48], rdx
0x1400327b5  mov     edx, ebx
0x1400327b7  call    FaxLog
0x1400327bc  mov     rax, cs:WPP_GLOBAL_Control
0x1400327c3  cmp     rax, rdi
0x1400327c6  jz      short loc_1400327F9
0x1400327c8  test    byte ptr [rax+1Ch], 4
0x1400327cc  jz      short loc_1400327F9
0x1400327ce  cmp     byte ptr [rax+19h], 2
0x1400327d2  jb      short loc_1400327F9
0x1400327d4  call    cs:__imp_GetLastError
0x1400327da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400327e1  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400327e8  mov     edx, 88h
0x1400327ed  mov     r9d, eax
0x1400327f0  mov     rcx, [rcx+10h]
0x1400327f4  call    WPP_SF_d
0x1400327f9  xor     ebx, ebx
0x1400327fb  mov     eax, ebx
0x1400327fd  mov     rcx, [rsp+68h+var_18]
0x140032802  xor     rcx, rsp; StackCookie
0x140032805  call    __security_check_cookie
0x14003280a  mov     rbx, [rsp+68h+arg_0]
0x14003280f  add     rsp, 60h
0x140032813  pop     rdi
0x140032814  retn
```
