# Tcp::CleanupSendNotifications(void *,ulong *,ulong *)

- ea: `0x1801624f0`
- end: `0x180162755`
- name: `?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z`
- size: `613`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x1801624f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801625ef`
- `KERNEL32!GetLastError` at `0x180162650`
- `KERNEL32!GetLastError` at `0x1801625ef`
- `KERNEL32!GetLastError` at `0x180162650`
- `KERNEL32!InitializeSListHead` at `0x180162583`
- `KERNEL32!InitializeSListHead` at `0x180162583`
- `KERNEL32!InterlockedPushEntrySList` at `0x1801626a7`
- `KERNEL32!InterlockedPushEntrySList` at `0x18016270e`
- `KERNEL32!InterlockedPushEntrySList` at `0x1801626a7`
- `KERNEL32!InterlockedPushEntrySList` at `0x18016270e`
- `KERNEL32!InterlockedPopEntrySList` at `0x180162599`
- `KERNEL32!InterlockedPopEntrySList` at `0x1801626f9`
- `KERNEL32!InterlockedPopEntrySList` at `0x180162599`
- `KERNEL32!InterlockedPopEntrySList` at `0x1801626f9`
- `KERNEL32!WaitForSingleObject` at `0x1801625cc`
- `KERNEL32!WaitForSingleObject` at `0x1801625cc`
- `KERNEL32!CloseHandle` at `0x1801625e5`
- `KERNEL32!CloseHandle` at `0x1801625e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Tcp::CleanupSendNotifications()
{
  unsigned int v0; // esi
  int v1; // r14d
  int v2; // ebp
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *v4; // rdi
  HANDLE *p_Next; // rbx
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD LastError; // eax
  struct _SLIST_ENTRY *v9; // rax
  unsigned int v10; // ebx
  _QWORD v12[2]; // [rsp+40h] [rbp-48h] BYREF
  _SLIST_HEADER ListHead; // [rsp+50h] [rbp-38h] BYREF

  v12[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266A38[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      v12,
      off_180266A38[0],
      0);
  ListHead = 0;
  InitializeSListHead(&ListHead);
  v0 = 0;
  v1 = 0;
  v2 = 0;
  while ( 1 )
  {
    v3 = InterlockedPopEntrySList(&Tcp::s_slhNotificationsToClose);
    v4 = v3;
    if ( !v3 )
      break;
    ++v0;
    p_Next = (HANDLE *)&v3[1].Next->Next;
    if ( !p_Next )
      goto LABEL_16;
    if ( *(_DWORD *)p_Next == 259 || (v6 = WaitForSingleObject(p_Next[3], 0), v6 == 258) )
    {
      InterlockedPushEntrySList(&ListHead, v4);
    }
    else if ( v6 )
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_180264828[0] )
        bidTraceW(off_1802614E0[0], 3646464, off_180264828[0], LastError);
      ++v2;
      operator delete(v4, 0x20u);
    }
    else
    {
      if ( !CloseHandle(p_Next[3]) )
      {
        v7 = GetLastError();
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180264820[0] )
            bidTraceW(off_1802614D8[0], 3633152, off_180264820[0], v7);
        }
      }
      p_Next[3] = 0;
      operator delete(p_Next, 0x20u);
      ++v1;
LABEL_16:
      operator delete(v4, 0x20u);
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264830[0] )
    bidTraceW(off_1802614E8[0], 3674112, off_180264830[0], v0);
  while ( 1 )
  {
    v9 = InterlockedPopEntrySList(&ListHead);
    if ( !v9 )
      break;
    InterlockedPushEntrySList(&Tcp::s_slhNotificationsToClose, v9);
  }
  v10 = 3;
  if ( v0 )
    v10 = 0;
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v12);
  return v10;
}

```

## disassembly

```asm
0x1801624f0  mov     r11, rsp
0x1801624f3  mov     [r11+8], rbx
0x1801624f7  mov     [r11+10h], rbp
0x1801624fb  mov     [r11+18h], rsi
0x1801624ff  push    rdi
0x180162500  push    r14
0x180162502  push    r15
0x180162504  sub     rsp, 70h
0x180162508  mov     rax, cs:__security_cookie
0x18016250f  xor     rax, rsp
0x180162512  mov     [rsp+88h+var_28], rax
0x180162517  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFFh
0x18016251f  mov     eax, cs:_bidGblFlags
0x180162525  and     eax, 20004h
0x18016252a  xor     r15d, r15d
0x18016252d  cmp     eax, 20004h
0x180162532  jnz     short loc_180162576
0x180162534  mov     rax, cs:off_180266A38; "<Tcp::CleanupSendNotifications|API|SNI>"...
0x18016253b  test    rax, rax
0x18016253e  jz      short loc_180162576
0x180162540  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180162548  jz      short loc_180162576
0x18016254a  mov     rax, cs:off_180248060
0x180162551  mov     [r11-60h], r15
0x180162555  mov     rcx, cs:off_180266A38; "<Tcp::CleanupSendNotifications|API|SNI>"...
0x18016255c  mov     [r11-68h], rcx
0x180162560  lea     r9, [r11-48h]
0x180162564  xor     r8d, r8d
0x180162567  xor     edx, edx
0x180162569  mov     rcx, cs:_bidID
0x180162570  call    cs:__guard_dispatch_icall_fptr
0x180162576  xorps   xmm0, xmm0
0x180162579  movups  xmmword ptr [rsp+88h+ListHead], xmm0
0x18016257e  lea     rcx, [rsp+88h+ListHead]; ListHead
0x180162583  call    cs:__imp_InitializeSListHead
0x180162589  mov     esi, r15d
0x18016258c  mov     r14d, r15d
0x18016258f  mov     ebp, r15d
0x180162592  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x180162599  call    cs:__imp_InterlockedPopEntrySList
0x18016259f  mov     rdi, rax
0x1801625a2  test    rax, rax
0x1801625a5  jz      loc_1801626B2
0x1801625ab  inc     esi
0x1801625ad  mov     rbx, [rax+10h]
0x1801625b1  test    rbx, rbx
0x1801625b4  jz      loc_18016263E
0x1801625ba  cmp     dword ptr [rbx], 103h
0x1801625c0  jz      loc_18016269F
0x1801625c6  xor     edx, edx; dwMilliseconds
0x1801625c8  mov     rcx, [rbx+18h]; hHandle
0x1801625cc  call    cs:__imp_WaitForSingleObject
0x1801625d2  cmp     eax, 102h
0x1801625d7  jz      loc_18016269F
0x1801625dd  test    eax, eax
0x1801625df  jnz     short loc_180162650
0x1801625e1  mov     rcx, [rbx+18h]; hObject
0x1801625e5  call    cs:__imp_CloseHandle
0x1801625eb  test    eax, eax
0x1801625ed  jnz     short loc_18016262A
0x1801625ef  call    cs:__imp_GetLastError
0x1801625f5  test    byte ptr cs:_bidGblFlags, 2
0x1801625fc  jz      short loc_18016262A
0x1801625fe  mov     rcx, cs:off_180264820; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x180162605  test    rcx, rcx
0x180162608  jz      short loc_18016262A
0x18016260a  mov     [rsp+88h+var_68], rbx
0x18016260f  mov     r9d, eax
0x180162612  mov     r8, cs:off_180264820; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x180162619  mov     edx, 377000h
0x18016261e  mov     rcx, cs:off_1802614D8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180162625  call    _bidTraceW
0x18016262a  mov     [rbx+18h], r15
0x18016262e  mov     edx, 20h ; ' '; unsigned __int64
0x180162633  mov     rcx, rbx; void *
0x180162636  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18016263b  inc     r14d
0x18016263e  mov     edx, 20h ; ' '; unsigned __int64
0x180162643  mov     rcx, rdi; void *
0x180162646  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18016264b  jmp     loc_180162592
0x180162650  call    cs:__imp_GetLastError
0x180162656  test    byte ptr cs:_bidGblFlags, 2
0x18016265d  jz      short loc_18016268B
0x18016265f  mov     rcx, cs:off_180264828; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x180162666  test    rcx, rcx
0x180162669  jz      short loc_18016268B
0x18016266b  mov     [rsp+88h+var_68], rbx
0x180162670  mov     r9d, eax
0x180162673  mov     r8, cs:off_180264828; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x18016267a  mov     edx, 37A400h
0x18016267f  mov     rcx, cs:off_1802614E0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180162686  call    _bidTraceW
0x18016268b  inc     ebp
0x18016268d  mov     edx, 20h ; ' '; unsigned __int64
0x180162692  mov     rcx, rdi; void *
0x180162695  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18016269a  jmp     loc_180162592
0x18016269f  mov     rdx, rdi; ListEntry
0x1801626a2  lea     rcx, [rsp+88h+ListHead]; ListHead
0x1801626a7  call    cs:__imp_InterlockedPushEntrySList
0x1801626ad  jmp     loc_180162592
0x1801626b2  mov     eax, cs:_bidGblFlags
0x1801626b8  and     eax, 20002h
0x1801626bd  cmp     eax, 20002h
0x1801626c2  jnz     short loc_1801626F4
0x1801626c4  mov     rax, cs:off_180264830; "<Tcp::CleanupSendNotifications|SNI> Ite"...
0x1801626cb  test    rax, rax
0x1801626ce  jz      short loc_1801626F4
0x1801626d0  mov     [rsp+88h+var_60], ebp
0x1801626d4  mov     dword ptr [rsp+88h+var_68], r14d
0x1801626d9  mov     r9d, esi
0x1801626dc  mov     r8, cs:off_180264830; "<Tcp::CleanupSendNotifications|SNI> Ite"...
0x1801626e3  mov     edx, 381000h
0x1801626e8  mov     rcx, cs:off_1802614E8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801626ef  call    _bidTraceW
0x1801626f4  lea     rcx, [rsp+88h+ListHead]; ListHead
0x1801626f9  call    cs:__imp_InterlockedPopEntrySList
0x1801626ff  test    rax, rax
0x180162702  jz      short loc_180162716
0x180162704  mov     rdx, rax; ListEntry
0x180162707  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x18016270e  call    cs:__imp_InterlockedPushEntrySList
0x180162714  jmp     short loc_1801626F4
0x180162716  mov     ebx, 3
0x18016271b  test    esi, esi
0x18016271d  cmovnz  ebx, r15d
0x180162721  lea     rcx, [rsp+88h+var_48]; this
0x180162726  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18016272b  nop
0x18016272c  mov     eax, ebx
0x18016272e  mov     rcx, [rsp+88h+var_28]
0x180162733  xor     rcx, rsp; StackCookie
0x180162736  call    __security_check_cookie
0x18016273b  lea     r11, [rsp+88h+var_18]
0x180162740  mov     rbx, [r11+20h]
0x180162744  mov     rbp, [r11+28h]
0x180162748  mov     rsi, [r11+30h]
0x18016274c  mov     rsp, r11
0x18016274f  pop     r15
0x180162751  pop     r14
0x180162753  pop     rdi
0x180162754  retn
```
