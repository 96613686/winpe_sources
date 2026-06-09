# NfsUpCallpPasswdGroupRefreshPasswdIfNeeded

- ea: `0x140011968`
- end: `0x140011b4b`
- name: `NfsUpCallpPasswdGroupRefreshPasswdIfNeeded`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140010be4`
- `0x140011e80`

## callees

- `0x140011440`
- `0x140011800`
- `0x140011968`
- `0x1400120d4`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140011b24`
- `ADVAPI32!EventWrite` at `0x140011b24`
- `ADVAPI32!EventEnabled` at `0x140011b05`
- `ADVAPI32!EventEnabled` at `0x140011b05`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400119b1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400119b1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140011ab0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140011ab0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011a86`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011a86`
- `KERNEL32!ReleaseSRWLockShared` at `0x140011a03`
- `KERNEL32!ReleaseSRWLockShared` at `0x140011a03`
- `KERNEL32!AcquireSRWLockShared` at `0x1400119e0`
- `KERNEL32!AcquireSRWLockShared` at `0x1400119e0`
- `KERNEL32!GetLastError` at `0x1400119bb`
- `KERNEL32!GetLastError` at `0x1400119bb`
- `ntdll!RtlFreeHeap` at `0x140011a9f`
- `ntdll!RtlFreeHeap` at `0x140011a9f`

## string_xrefs

- `0x140011994`: `%SystemRoot%\System32\drivers\etc\passwd`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupRefreshPasswdIfNeeded(__int64 a1, __int64 a2)
{
  ULONGLONG Ptr; // rbx
  DWORD LastError; // eax
  DWORD refreshed; // esi
  char v6; // r14
  __int64 v7; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-D0h] BYREF

  Ptr = 0;
  UserData.Ptr = 0;
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\drivers\\etc\\passwd", Dst, 0x105u) )
  {
    LastError = NfsUpCallpPasswdGroupQueryLastWriteTime(Dst, &UserData);
    Ptr = UserData.Ptr;
  }
  else
  {
    LastError = GetLastError();
  }
  refreshed = LastError;
  if ( LastError )
    goto LABEL_34;
  AcquireSRWLockShared((PSRWLOCK)a2);
  if ( !*(_QWORD *)(a2 + 8)
    || *(_DWORD *)(a2 + 24) != (_DWORD)Ptr
    || (v6 = 0, *(_DWORD *)(a2 + 28) != HIDWORD(UserData.Ptr)) )
  {
    v6 = 1;
  }
  ReleaseSRWLockShared((PSRWLOCK)a2);
  if ( v6 )
  {
    refreshed = NfsUpCallpPasswdGroupRefreshPasswd(v7, a2, Dst, Ptr);
    if ( refreshed )
    {
LABEL_34:
      if ( *(_QWORD *)(a2 + 8) )
      {
        switch ( refreshed )
        {
          case 2u:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_FILE_NOT_FOUND;
            break;
          case 8u:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_NOT_ENOUGH_MEMORY;
            break;
          case 0xDu:
            v8 = 0;
            break;
          case 0xDFu:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_FILE_TOO_LARGE;
            break;
          case 0xE8u:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_NO_DATA;
            break;
          default:
            v8 = (__int64 *)&EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_FAILED;
            break;
        }
        AcquireSRWLockExclusive((PSRWLOCK)a2);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)(a2 + 8));
        *(_QWORD *)(a2 + 8) = 0;
        *(_QWORD *)(a2 + 24) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)a2);
        if ( *(_QWORD *)(a2 + 40) )
          SendMapCacheRefreshIoctlToDriver();
        if ( v8 )
        {
          UserData.Ptr = (ULONGLONG)Dst;
          v9 = -1;
          do
            ++v9;
          while ( Dst[v9] );
          UserData.Size = 2 * v9 + 2;
          UserData.Reserved = 0;
          if ( RegHandle )
          {
            if ( EventEnabled(RegHandle, (PCEVENT_DESCRIPTOR)v8) )
              EventWrite(RegHandle, (PCEVENT_DESCRIPTOR)v8, 1u, &UserData);
          }
        }
      }
    }
  }
  return refreshed;
}

```

## disassembly

```asm
0x140011968  push    rbp
0x14001196a  push    rbx
0x14001196b  push    rsi
0x14001196c  push    rdi
0x14001196d  push    r14
0x14001196f  push    r15
0x140011971  lea     rbp, [rsp-158h]
0x140011979  sub     rsp, 258h
0x140011980  mov     rax, cs:__security_cookie
0x140011987  xor     rax, rsp
0x14001198a  mov     [rbp+180h+var_40], rax
0x140011991  mov     rdi, rdx
0x140011994  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\drivers\\etc\\p"...
0x14001199b  xor     r15d, r15d
0x14001199e  lea     rdx, [rsp+280h+Dst]; lpDst
0x1400119a3  mov     ebx, r15d
0x1400119a6  mov     r8d, 105h; nSize
0x1400119ac  mov     [rsp+280h+UserData.Ptr], rbx
0x1400119b1  call    cs:__imp_ExpandEnvironmentStringsW
0x1400119b7  test    eax, eax
0x1400119b9  jnz     short loc_1400119C3
0x1400119bb  call    cs:__imp_GetLastError
0x1400119c1  jmp     short loc_1400119D7
0x1400119c3  lea     rdx, [rsp+280h+UserData]
0x1400119c8  lea     rcx, [rsp+280h+Dst]
0x1400119cd  call    NfsUpCallpPasswdGroupQueryLastWriteTime
0x1400119d2  mov     rbx, [rsp+280h+UserData.Ptr]
0x1400119d7  mov     esi, eax
0x1400119d9  test    eax, eax
0x1400119db  jnz     short loc_140011A2C
0x1400119dd  mov     rcx, rdi; SRWLock
0x1400119e0  call    cs:__imp_AcquireSRWLockShared
0x1400119e6  cmp     [rdi+8], r15
0x1400119ea  jz      short loc_1400119FD
0x1400119ec  cmp     [rdi+18h], ebx
0x1400119ef  jnz     short loc_1400119FD
0x1400119f1  mov     eax, dword ptr [rsp+280h+UserData.Ptr+4]
0x1400119f5  mov     r14b, r15b
0x1400119f8  cmp     [rdi+1Ch], eax
0x1400119fb  jz      short loc_140011A00
0x1400119fd  mov     r14b, 1
0x140011a00  mov     rcx, rdi; SRWLock
0x140011a03  call    cs:__imp_ReleaseSRWLockShared
0x140011a09  test    r14b, r14b
0x140011a0c  jz      loc_140011B2A
0x140011a12  mov     r9, rbx
0x140011a15  lea     r8, [rsp+280h+Dst]
0x140011a1a  mov     rdx, rdi
0x140011a1d  call    NfsUpCallpPasswdGroupRefreshPasswd
0x140011a22  mov     esi, eax
0x140011a24  test    eax, eax
0x140011a26  jz      loc_140011B2A
0x140011a2c  cmp     [rdi+8], r15
0x140011a30  jz      loc_140011B2A
0x140011a36  mov     eax, esi
0x140011a38  sub     eax, 2
0x140011a3b  jz      short loc_140011A7C
0x140011a3d  sub     eax, 6
0x140011a40  jz      short loc_140011A73
0x140011a42  sub     eax, 5
0x140011a45  jz      short loc_140011A6E
0x140011a47  sub     eax, 0D2h
0x140011a4c  jz      short loc_140011A65
0x140011a4e  cmp     eax, 9
0x140011a51  jz      short loc_140011A5C
0x140011a53  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_FAILED
0x140011a5a  jmp     short loc_140011A83
0x140011a5c  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_NO_DATA
0x140011a63  jmp     short loc_140011A83
0x140011a65  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_FILE_TOO_LARGE
0x140011a6c  jmp     short loc_140011A83
0x140011a6e  mov     rbx, r15
0x140011a71  jmp     short loc_140011A83
0x140011a73  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_NOT_ENOUGH_MEMORY
0x140011a7a  jmp     short loc_140011A83
0x140011a7c  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_FILE_NOT_FOUND
0x140011a83  mov     rcx, rdi; SRWLock
0x140011a86  call    cs:__imp_AcquireSRWLockExclusive
0x140011a8c  mov     rcx, gs:60h
0x140011a95  xor     edx, edx; Flags
0x140011a97  mov     r8, [rdi+8]; P
0x140011a9b  mov     rcx, [rcx+30h]; HeapHandle
0x140011a9f  call    cs:__imp_RtlFreeHeap
0x140011aa5  mov     rcx, rdi; SRWLock
0x140011aa8  mov     [rdi+8], r15
0x140011aac  mov     [rdi+18h], r15
0x140011ab0  call    cs:__imp_ReleaseSRWLockExclusive
0x140011ab6  mov     rcx, [rdi+28h]
0x140011aba  test    rcx, rcx
0x140011abd  jz      short loc_140011AC4
0x140011abf  call    SendMapCacheRefreshIoctlToDriver
0x140011ac4  test    rbx, rbx
0x140011ac7  jz      short loc_140011B2A
0x140011ac9  lea     rax, [rsp+280h+Dst]
0x140011ace  mov     [rsp+280h+UserData.Ptr], rax
0x140011ad3  lea     rcx, [rsp+280h+Dst]
0x140011ad8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011adc  inc     rax
0x140011adf  cmp     [rcx+rax*2], r15w
0x140011ae4  jnz     short loc_140011ADC
0x140011ae6  mov     rcx, cs:RegHandle; RegHandle
0x140011aed  lea     eax, ds:2[rax*2]
0x140011af4  mov     [rsp+280h+UserData.Size], eax
0x140011af8  mov     dword ptr [rsp+280h+UserData.0Ch], r15d
0x140011afd  test    rcx, rcx
0x140011b00  jz      short loc_140011B2A
0x140011b02  mov     rdx, rbx; EventDescriptor
0x140011b05  call    cs:__imp_EventEnabled
0x140011b0b  test    al, al
0x140011b0d  jz      short loc_140011B2A
0x140011b0f  mov     rcx, cs:RegHandle; RegHandle
0x140011b16  lea     r9, [rsp+280h+UserData]; UserData
0x140011b1b  mov     r8d, 1; UserDataCount
0x140011b21  mov     rdx, rbx; EventDescriptor
0x140011b24  call    cs:__imp_EventWrite
0x140011b2a  mov     eax, esi
0x140011b2c  mov     rcx, [rbp+180h+var_40]
0x140011b33  xor     rcx, rsp; StackCookie
0x140011b36  call    __security_check_cookie
0x140011b3b  add     rsp, 258h
0x140011b42  pop     r15
0x140011b44  pop     r14
0x140011b46  pop     rdi
0x140011b47  pop     rsi
0x140011b48  pop     rbx
0x140011b49  pop     rbp
0x140011b4a  retn
```
