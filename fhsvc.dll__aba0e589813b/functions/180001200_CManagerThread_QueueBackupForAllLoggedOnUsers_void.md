# CManagerThread::QueueBackupForAllLoggedOnUsers(void)

- ea: `0x180001200`
- end: `0x1800012c7`
- name: `?QueueBackupForAllLoggedOnUsers@CManagerThread@@QEAAXXZ`
- size: `199`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008180`

## callees

- `0x180001200`
- `0x1800012d0`
- `0x18000ca14`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000127a`
- `KERNEL32!GetLastError` at `0x18000127a`
- `WTSAPI32!WTSFreeMemory` at `0x1800012bf`
- `WTSAPI32!WTSFreeMemory` at `0x1800012bf`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18000122e`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18000122e`

## pseudocode

```c
void __fastcall CManagerThread::QueueBackupForAllLoggedOnUsers(CManagerThread *this)
{
  DWORD v1; // ebx
  DWORD v2; // r8d
  signed int LastError; // eax
  DWORD pCount; // [rsp+40h] [rbp+8h] BYREF
  int v5; // [rsp+44h] [rbp+Ch]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp+10h] BYREF

  v5 = HIDWORD(this);
  v1 = 0;
  ppSessionInfo = 0;
  pCount = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v2 = pCount;
    if ( pCount )
    {
      do
      {
        if ( ppSessionInfo[v1].State == WTSActive )
        {
          CManagerThread::QueueBackupForLoggedOnUser((CManagerThread *)(3LL * v1), ppSessionInfo[v1].SessionId);
          v2 = pCount;
        }
        ++v1;
      }
      while ( v1 < v2 );
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)LastError);
  }
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
}

```

## disassembly

```asm
0x180001200  mov     qword ptr [rsp+arg_0], rcx
0x180001205  push    rbx
0x180001206  sub     rsp, 30h
0x18000120a  xor     ebx, ebx
0x18000120c  lea     rax, [rsp+38h+arg_0]
0x180001211  lea     r9, [rsp+38h+ppSessionInfo]; ppSessionInfo
0x180001216  mov     [rsp+38h+ppSessionInfo], rbx
0x18000121b  xor     edx, edx; Reserved
0x18000121d  mov     [rsp+38h+arg_0], ebx
0x180001221  mov     r8d, 1; Version
0x180001227  mov     [rsp+38h+pCount], rax; pCount
0x18000122c  xor     ecx, ecx; hServer
0x18000122e  call    cs:__imp_WTSEnumerateSessionsW
0x180001234  test    eax, eax
0x180001236  jz      short loc_18000127A
0x180001238  mov     r8d, [rsp+38h+arg_0]
0x18000123d  test    r8d, r8d
0x180001240  jz      short loc_18000125B
0x180001242  mov     eax, ebx
0x180001244  lea     rcx, [rax+rax*2]; this
0x180001248  mov     rax, [rsp+38h+ppSessionInfo]
0x18000124d  cmp     dword ptr [rax+rcx*8+10h], 0
0x180001252  jz      short loc_18000126B
0x180001254  inc     ebx
0x180001256  cmp     ebx, r8d
0x180001259  jb      short loc_180001242
0x18000125b  mov     rcx, [rsp+38h+ppSessionInfo]; pMemory
0x180001260  test    rcx, rcx
0x180001263  jnz     short loc_1800012BF
0x180001265  add     rsp, 30h
0x180001269  pop     rbx
0x18000126a  retn
0x18000126b  mov     edx, [rax+rcx*8]; unsigned int
0x18000126e  call    ?QueueBackupForLoggedOnUser@CManagerThread@@QEAAXK@Z; CManagerThread::QueueBackupForLoggedOnUser(ulong)
0x180001273  mov     r8d, [rsp+38h+arg_0]
0x180001278  jmp     short loc_180001254
0x18000127a  call    cs:__imp_GetLastError
0x180001280  test    eax, eax
0x180001282  jle     short loc_18000128C
0x180001284  movzx   eax, ax
0x180001287  or      eax, 80070000h
0x18000128c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001293  lea     rdx, WPP_GLOBAL_Control
0x18000129a  cmp     rcx, rdx
0x18000129d  jz      short loc_18000125B
0x18000129f  test    byte ptr [rcx+1Ch], 1
0x1800012a3  jz      short loc_18000125B
0x1800012a5  mov     rcx, [rcx+10h]
0x1800012a9  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800012b0  mov     edx, 65h ; 'e'
0x1800012b5  mov     r9d, eax
0x1800012b8  call    WPP_SF_d
0x1800012bd  jmp     short loc_18000125B
0x1800012bf  call    cs:__imp_WTSFreeMemory
0x1800012c5  jmp     short loc_180001265
```
