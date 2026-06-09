# Tcp::CleanupSendNotifications(void *,ulong *,ulong *)

- ea: `0x100432c70`
- end: `0x100432ec1`
- name: `?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x100432c70`
- `0x100545d84`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x100432e1f`
- `KERNEL32!InterlockedPushEntrySList` at `0x100432e81`
- `KERNEL32!InterlockedPushEntrySList` at `0x100432e1f`
- `KERNEL32!InterlockedPushEntrySList` at `0x100432e81`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432d16`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432e6c`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432d16`
- `KERNEL32!InterlockedPopEntrySList` at `0x100432e6c`
- `KERNEL32!InitializeSListHead` at `0x100432d01`
- `KERNEL32!InitializeSListHead` at `0x100432d01`
- `KERNEL32!WaitForSingleObject` at `0x100432d49`
- `KERNEL32!WaitForSingleObject` at `0x100432d49`
- `KERNEL32!GetLastError` at `0x100432d6c`
- `KERNEL32!GetLastError` at `0x100432ddc`
- `KERNEL32!GetLastError` at `0x100432d6c`
- `KERNEL32!GetLastError` at `0x100432ddc`
- `KERNEL32!CloseHandle` at `0x100432d62`
- `KERNEL32!CloseHandle` at `0x100432d62`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Tcp::CleanupSendNotifications()
{
  unsigned int v0; // ebx
  unsigned int v1; // esi
  int v2; // r15d
  int v3; // r14d
  PSLIST_ENTRY v4; // rax
  struct _SLIST_ENTRY *v5; // rbp
  struct _SLIST_ENTRY *Next; // rdi
  DWORD v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 LastError; // r9
  struct _SLIST_ENTRY *v11; // rax
  struct _SLIST_ENTRY *v13; // [rsp+20h] [rbp-68h]
  _QWORD v14[2]; // [rsp+40h] [rbp-48h] BYREF
  _SLIST_HEADER ListHead; // [rsp+50h] [rbp-38h] BYREF

  v14[1] = -2;
  v14[0] = -1;
  v0 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7D70[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      v14,
      off_1005E7D70[0],
      0);
  InitializeSListHead(&ListHead);
  v1 = 0;
  v2 = 0;
  v3 = 0;
  while ( 1 )
  {
    v4 = InterlockedPopEntrySList(&Tcp::s_slhNotificationsToClose);
    v5 = v4;
    if ( !v4 )
      break;
    ++v1;
    Next = v4[1].Next;
    if ( !Next )
      goto LABEL_16;
    if ( LODWORD(Next->Next) == 259 || (v7 = WaitForSingleObject(*((HANDLE *)&Next[1].Next + 1), 0), v7 == 258) )
    {
      InterlockedPushEntrySList(&ListHead, v5);
    }
    else
    {
      if ( v7 )
      {
        LastError = GetLastError();
        if ( (bidGblFlags & 2) != 0 && off_1005E5A38[0] )
        {
          v13 = Next;
          bidTraceW(0, 3630080, off_1005E5A38[0], LastError);
        }
        ++v3;
      }
      else
      {
        if ( !CloseHandle(*((HANDLE *)&Next[1].Next + 1)) )
        {
          v9 = GetLastError();
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_1005E5A30[0] )
            {
              v13 = Next;
              bidTraceW(0, 3616768, off_1005E5A30[0], v9);
            }
          }
        }
        *((_QWORD *)&Next[1].Next + 1) = 0;
        ((void (__fastcall *)(struct IMalloc *, struct _SLIST_ENTRY *, __int64, __int64, struct _SLIST_ENTRY *))g_pMO->lpVtbl[1].Realloc)(
          g_pMO,
          Next,
          v8,
          v9,
          v13);
        ++v2;
      }
LABEL_16:
      ((void (__fastcall *)(struct IMalloc *, struct _SLIST_ENTRY *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v5);
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5A40[0] )
    bidTraceW(0, 3655680, off_1005E5A40[0], v1);
  while ( 1 )
  {
    v11 = InterlockedPopEntrySList(&ListHead);
    if ( !v11 )
      break;
    InterlockedPushEntrySList(&Tcp::s_slhNotificationsToClose, v11);
  }
  LOBYTE(v0) = v1 == 0;
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v14);
  return v0;
}

```

## disassembly

```asm
0x100432c70  mov     r11, rsp
0x100432c73  push    rdi
0x100432c74  push    r14
0x100432c76  push    r15
0x100432c78  sub     rsp, 70h
0x100432c7c  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x100432c84  mov     [r11+8], rbx
0x100432c88  mov     [r11+10h], rbp
0x100432c8c  mov     [r11+18h], rsi
0x100432c90  mov     rax, cs:__security_cookie
0x100432c97  xor     rax, rsp
0x100432c9a  mov     [rsp+88h+var_28], rax
0x100432c9f  or      qword ptr [r11-48h], 0FFFFFFFFFFFFFFFFh
0x100432ca4  mov     eax, cs:_bidGblFlags
0x100432caa  mov     ecx, 20004h
0x100432caf  and     eax, ecx
0x100432cb1  xor     ebx, ebx
0x100432cb3  cmp     eax, ecx
0x100432cb5  jnz     short loc_100432CFC
0x100432cb7  mov     rax, cs:off_1005E7D70; "<Tcp::CleanupSendNotifications|API|SNI>"...
0x100432cbe  test    rax, rax
0x100432cc1  jz      short loc_100432CFC
0x100432cc3  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100432ccb  jz      short loc_100432CFC
0x100432ccd  mov     r10, cs:off_1005D39F0
0x100432cd4  mov     [r11-60h], rbx
0x100432cd8  mov     rax, cs:off_1005E7D70; "<Tcp::CleanupSendNotifications|API|SNI>"...
0x100432cdf  mov     [r11-68h], rax
0x100432ce3  lea     r9, [r11-48h]
0x100432ce7  xor     r8d, r8d
0x100432cea  xor     edx, edx
0x100432cec  mov     rcx, cs:_bidID
0x100432cf3  mov     rax, r10
0x100432cf6  call    cs:__guard_dispatch_icall_fptr
0x100432cfc  lea     rcx, [rsp+88h+ListHead]; ListHead
0x100432d01  call    cs:__imp_InitializeSListHead
0x100432d07  mov     esi, ebx
0x100432d09  mov     r15d, ebx
0x100432d0c  mov     r14d, ebx
0x100432d0f  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x100432d16  call    cs:__imp_InterlockedPopEntrySList
0x100432d1c  mov     rbp, rax
0x100432d1f  test    rax, rax
0x100432d22  jz      loc_100432E2A
0x100432d28  inc     esi
0x100432d2a  mov     rdi, [rax+10h]
0x100432d2e  test    rdi, rdi
0x100432d31  jz      loc_100432DC0
0x100432d37  cmp     dword ptr [rdi], 103h
0x100432d3d  jz      loc_100432E17
0x100432d43  xor     edx, edx; dwMilliseconds
0x100432d45  mov     rcx, [rdi+18h]; hHandle
0x100432d49  call    cs:__imp_WaitForSingleObject
0x100432d4f  cmp     eax, 102h
0x100432d54  jz      loc_100432E17
0x100432d5a  test    eax, eax
0x100432d5c  jnz     short loc_100432DDC
0x100432d5e  mov     rcx, [rdi+18h]; hObject
0x100432d62  call    cs:__imp_CloseHandle
0x100432d68  test    eax, eax
0x100432d6a  jnz     short loc_100432DA2
0x100432d6c  call    cs:__imp_GetLastError
0x100432d72  mov     r9d, eax
0x100432d75  test    byte ptr cs:_bidGblFlags, 2
0x100432d7c  jz      short loc_100432DA2
0x100432d7e  mov     rax, cs:off_1005E5A30; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x100432d85  test    rax, rax
0x100432d88  jz      short loc_100432DA2
0x100432d8a  mov     [rsp+88h+var_68], rdi
0x100432d8f  mov     r8, cs:off_1005E5A30; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x100432d96  mov     edx, 373000h
0x100432d9b  xor     ecx, ecx
0x100432d9d  call    _bidTraceW
0x100432da2  mov     [rdi+18h], rbx
0x100432da6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100432dad  mov     rax, [rcx]
0x100432db0  mov     rdx, rdi
0x100432db3  mov     rax, [rax+68h]
0x100432db7  call    cs:__guard_dispatch_icall_fptr
0x100432dbd  inc     r15d
0x100432dc0  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100432dc7  mov     rax, [rcx]
0x100432dca  mov     rdx, rbp
0x100432dcd  mov     rax, [rax+68h]
0x100432dd1  call    cs:__guard_dispatch_icall_fptr
0x100432dd7  jmp     loc_100432D0F
0x100432ddc  call    cs:__imp_GetLastError
0x100432de2  mov     r9d, eax
0x100432de5  test    byte ptr cs:_bidGblFlags, 2
0x100432dec  jz      short loc_100432E12
0x100432dee  mov     rax, cs:off_1005E5A38; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x100432df5  test    rax, rax
0x100432df8  jz      short loc_100432E12
0x100432dfa  mov     [rsp+88h+var_68], rdi
0x100432dff  mov     r8, cs:off_1005E5A38; "<Tcp::CleanupSendNotifications|ERR|SNI>"...
0x100432e06  mov     edx, 376400h
0x100432e0b  xor     ecx, ecx
0x100432e0d  call    _bidTraceW
0x100432e12  inc     r14d
0x100432e15  jmp     short loc_100432DC0
0x100432e17  mov     rdx, rbp; ListEntry
0x100432e1a  lea     rcx, [rsp+88h+ListHead]; ListHead
0x100432e1f  call    cs:__imp_InterlockedPushEntrySList
0x100432e25  jmp     loc_100432D0F
0x100432e2a  mov     eax, cs:_bidGblFlags
0x100432e30  mov     ecx, 20002h
0x100432e35  and     eax, ecx
0x100432e37  cmp     eax, ecx
0x100432e39  jnz     short loc_100432E67
0x100432e3b  mov     rax, cs:off_1005E5A40; "<Tcp::CleanupSendNotifications|SNI> Ite"...
0x100432e42  test    rax, rax
0x100432e45  jz      short loc_100432E67
0x100432e47  mov     [rsp+88h+var_60], r14d
0x100432e4c  mov     dword ptr [rsp+88h+var_68], r15d
0x100432e51  mov     r9d, esi
0x100432e54  mov     r8, cs:off_1005E5A40; "<Tcp::CleanupSendNotifications|SNI> Ite"...
0x100432e5b  mov     edx, 37C800h
0x100432e60  xor     ecx, ecx
0x100432e62  call    _bidTraceW
0x100432e67  lea     rcx, [rsp+88h+ListHead]; ListHead
0x100432e6c  call    cs:__imp_InterlockedPopEntrySList
0x100432e72  test    rax, rax
0x100432e75  jz      short loc_100432E89
0x100432e77  mov     rdx, rax; ListEntry
0x100432e7a  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x100432e81  call    cs:__imp_InterlockedPushEntrySList
0x100432e87  jmp     short loc_100432E67
0x100432e89  test    esi, esi
0x100432e8b  setz    bl
0x100432e8e  lea     rcx, [rsp+88h+var_48]; this
0x100432e93  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100432e98  mov     eax, ebx
0x100432e9a  mov     rcx, [rsp+88h+var_28]
0x100432e9f  xor     rcx, rsp; StackCookie
0x100432ea2  call    __security_check_cookie
0x100432ea7  lea     r11, [rsp+88h+var_18]
0x100432eac  mov     rbx, [r11+20h]
0x100432eb0  mov     rbp, [r11+28h]
0x100432eb4  mov     rsi, [r11+30h]
0x100432eb8  mov     rsp, r11
0x100432ebb  pop     r15
0x100432ebd  pop     r14
0x100432ebf  pop     rdi
0x100432ec0  retn
```
