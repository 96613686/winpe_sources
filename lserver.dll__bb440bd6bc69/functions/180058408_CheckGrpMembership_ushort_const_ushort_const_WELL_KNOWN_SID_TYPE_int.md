# CheckGrpMembership(ushort const *,ushort const *,WELL_KNOWN_SID_TYPE,int *)

- ea: `0x180058408`
- end: `0x180058627`
- name: `?CheckGrpMembership@@YAKPEBG0W4WELL_KNOWN_SID_TYPE@@PEAH@Z`
- size: `543`
- prototype: `unsigned int __fastcall(LPCWSTR servername, LPCWSTR localgroupname, enum WELL_KNOWN_SID_TYPE, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x180058b00`

## callees

- `0x180005705`
- `0x18001ad74`
- `0x18001ae3c`
- `0x180058408`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x1800584cb`
- `ADVAPI32!CreateWellKnownSid` at `0x1800584cb`
- `ADVAPI32!GetLengthSid` at `0x180058549`
- `ADVAPI32!GetLengthSid` at `0x180058562`
- `ADVAPI32!GetLengthSid` at `0x180058549`
- `ADVAPI32!GetLengthSid` at `0x180058562`
- `NETAPI32!NetLocalGroupGetMembers` at `0x18005851b`
- `NETAPI32!NetLocalGroupGetMembers` at `0x18005851b`
- `NETAPI32!NetApiBufferFree` at `0x18005859f`
- `NETAPI32!NetApiBufferFree` at `0x18005859f`
- `KERNEL32!GetLastError` at `0x1800584ac`
- `KERNEL32!GetLastError` at `0x1800584db`
- `KERNEL32!GetLastError` at `0x1800584ac`
- `KERNEL32!GetLastError` at `0x1800584db`
- `KERNEL32!LocalAlloc` at `0x180058498`
- `KERNEL32!LocalAlloc` at `0x180058498`
- `KERNEL32!LocalFree` at `0x180058600`
- `KERNEL32!LocalFree` at `0x180058600`

## pseudocode

```c
__int64 __fastcall CheckGrpMembership(LPCWSTR servername, LPCWSTR localgroupname, enum WELL_KNOWN_SID_TYPE a3, int *a4)
{
  __int64 v4; // rdi
  const WCHAR *v7; // rbx
  HLOCAL v9; // rax
  void *v10; // r14
  DWORD LastError; // ebx
  DWORD Members; // eax
  LPBYTE v13; // r12
  DWORD i; // r15d
  size_t LengthSid; // r8
  DWORD totalentries; // [rsp+40h] [rbp-20h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-18h] BYREF
  ULONG_PTR resumehandle[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD entriesread; // [rsp+B0h] [rbp+50h] BYREF
  DWORD cbSid; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  bufptr = 0;
  entriesread = 0;
  v7 = servername;
  totalentries = 0;
  resumehandle[0] = 0;
  cbSid = 68;
  if ( a4 )
  {
    *a4 = 0;
    v9 = LocalAlloc(0x40u, 0x44u);
    v10 = v9;
    if ( v9 )
    {
      if ( CreateWellKnownSid(WinNetworkServiceSid, 0, v9, &cbSid) )
      {
        while ( 1 )
        {
          Members = NetLocalGroupGetMembers(
                      v7,
                      localgroupname,
                      0,
                      &bufptr,
                      0xFFFFFFFF,
                      &entriesread,
                      &totalentries,
                      resumehandle);
          LastError = Members;
          if ( Members )
          {
            if ( Members != 234 )
              break;
          }
          v13 = bufptr;
          for ( i = 0; i < entriesread; ++i )
          {
            if ( GetLengthSid(*(PSID *)&v13[v4]) >= 0x44 )
              LengthSid = 68;
            else
              LengthSid = GetLengthSid(*(PSID *)&bufptr[v4]);
            v13 = bufptr;
            if ( !memcmp_0(*(const void **)&bufptr[v4], v10, LengthSid) )
            {
              *a4 = 1;
              break;
            }
            v4 += 8;
          }
          NetApiBufferFree(v13);
          if ( LastError != 234 )
            goto LABEL_28;
          v4 = 0;
          if ( *a4 )
          {
            if ( *a4 == 1 )
              LastError = 0;
            goto LABEL_28;
          }
          v7 = servername;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids, Members);
      }
      else
      {
        LastError = GetLastError();
      }
LABEL_28:
      LocalFree(v10);
    }
    else
    {
      return GetLastError();
    }
    return LastError;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids,
        L"CheckGrpMembership");
    return 87;
  }
}

```

## disassembly

```asm
0x180058408  mov     [rsp-38h+arg_8], rbx
0x18005840d  mov     [rsp-38h+arg_10], r8d
0x180058412  mov     [rsp-38h+arg_0], rcx
0x180058417  push    rbp
0x180058418  push    rsi
0x180058419  push    rdi
0x18005841a  push    r12
0x18005841c  push    r13
0x18005841e  push    r14
0x180058420  push    r15
0x180058422  mov     rbp, rsp
0x180058425  sub     rsp, 60h
0x180058429  xor     edi, edi
0x18005842b  mov     rsi, r9
0x18005842e  mov     [rbp+bufptr], rdi
0x180058432  mov     r13, rdx
0x180058435  mov     [rbp+arg_10], edi
0x180058438  mov     rbx, rcx
0x18005843b  mov     [rbp+var_20], edi
0x18005843e  mov     [rbp+var_10], rdi
0x180058442  lea     eax, [rdi+44h]
0x180058445  mov     [rbp+cbSid], eax
0x180058448  test    r9, r9
0x18005844b  jnz     short loc_18005848D
0x18005844d  mov     rcx, cs:WPP_GLOBAL_Control
0x180058454  lea     rax, WPP_GLOBAL_Control
0x18005845b  cmp     rcx, rax
0x18005845e  jz      short loc_180058483
0x180058460  test    dword ptr [rcx+1Ch], 1000h
0x180058467  jz      short loc_180058483
0x180058469  mov     rcx, [rcx+10h]
0x18005846d  lea     edx, [rdi+20h]
0x180058470  lea     r9, aCheckgrpmember; "CheckGrpMembership"
0x180058477  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x18005847e  call    WPP_SF_S
0x180058483  mov     eax, 57h ; 'W'
0x180058488  jmp     loc_18005860E
0x18005848d  mov     rdx, rax; uBytes
0x180058490  mov     [r9], edi
0x180058493  mov     ecx, 40h ; '@'; uFlags
0x180058498  call    cs:__imp_LocalAlloc
0x18005849f  nop     dword ptr [rax+rax+00h]
0x1800584a4  mov     r14, rax
0x1800584a7  test    rax, rax
0x1800584aa  jnz     short loc_1800584BF
0x1800584ac  call    cs:__imp_GetLastError
0x1800584b3  nop     dword ptr [rax+rax+00h]
0x1800584b8  mov     ebx, eax
0x1800584ba  jmp     loc_18005860C
0x1800584bf  xor     edx, edx; DomainSid
0x1800584c1  lea     r9, [rbp+cbSid]; cbSid
0x1800584c5  mov     r8, r14; pSid
0x1800584c8  lea     ecx, [rdx+18h]; WellKnownSidType
0x1800584cb  call    cs:__imp_CreateWellKnownSid
0x1800584d2  nop     dword ptr [rax+rax+00h]
0x1800584d7  test    eax, eax
0x1800584d9  jnz     short loc_1800584EE
0x1800584db  call    cs:__imp_GetLastError
0x1800584e2  nop     dword ptr [rax+rax+00h]
0x1800584e7  mov     ebx, eax
0x1800584e9  jmp     loc_1800585FD
0x1800584ee  lea     rax, [rbp+var_10]
0x1800584f2  xor     r8d, r8d; level
0x1800584f5  mov     [rsp+60h+resumehandle], rax; resumehandle
0x1800584fa  lea     r9, [rbp+bufptr]; bufptr
0x1800584fe  lea     rax, [rbp+var_20]
0x180058502  mov     rdx, r13; localgroupname
0x180058505  mov     [rsp+60h+totalentries], rax; totalentries
0x18005850a  mov     rcx, rbx; servername
0x18005850d  lea     rax, [rbp+arg_10]
0x180058511  mov     [rsp+60h+entriesread], rax; entriesread
0x180058516  or      [rsp+60h+var_40], 0FFFFFFFFh
0x18005851b  call    cs:__imp_NetLocalGroupGetMembers
0x180058522  nop     dword ptr [rax+rax+00h]
0x180058527  mov     ebx, eax
0x180058529  test    eax, eax
0x18005852b  jz      short loc_180058538
0x18005852d  cmp     eax, 0EAh
0x180058532  jnz     loc_1800585C4
0x180058538  mov     r12, [rbp+bufptr]
0x18005853c  mov     r15d, edi
0x18005853f  cmp     r15d, [rbp+arg_10]
0x180058543  jnb     short loc_18005859C
0x180058545  mov     rcx, [rdi+r12]; pSid
0x180058549  call    cs:__imp_GetLengthSid
0x180058550  nop     dword ptr [rax+rax+00h]
0x180058555  cmp     eax, 44h ; 'D'
0x180058558  jnb     short loc_180058573
0x18005855a  mov     rcx, [rbp+bufptr]
0x18005855e  mov     rcx, [rdi+rcx]; pSid
0x180058562  call    cs:__imp_GetLengthSid
0x180058569  nop     dword ptr [rax+rax+00h]
0x18005856e  mov     r8d, eax
0x180058571  jmp     short loc_180058579
0x180058573  mov     r8d, 44h ; 'D'; Size
0x180058579  mov     r12, [rbp+bufptr]
0x18005857d  mov     rdx, r14; Buf2
0x180058580  mov     rcx, [rdi+r12]; Buf1
0x180058584  call    memcmp_0
0x180058589  test    eax, eax
0x18005858b  jz      short loc_180058596
0x18005858d  inc     r15d
0x180058590  add     rdi, 8
0x180058594  jmp     short loc_18005853F
0x180058596  mov     dword ptr [rsi], 1
0x18005859c  mov     rcx, r12; Buffer
0x18005859f  call    cs:__imp_NetApiBufferFree
0x1800585a6  nop     dword ptr [rax+rax+00h]
0x1800585ab  cmp     ebx, 0EAh
0x1800585b1  jnz     short loc_1800585FD
0x1800585b3  mov     eax, [rsi]
0x1800585b5  xor     edi, edi
0x1800585b7  test    eax, eax
0x1800585b9  jnz     short loc_1800585F7
0x1800585bb  mov     rbx, [rbp+arg_0]
0x1800585bf  jmp     loc_1800584EE
0x1800585c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800585cb  lea     rax, WPP_GLOBAL_Control
0x1800585d2  cmp     rcx, rax
0x1800585d5  jz      short loc_1800585FD
0x1800585d7  test    byte ptr [rcx+1Ch], 20h
0x1800585db  jz      short loc_1800585FD
0x1800585dd  mov     rcx, [rcx+10h]
0x1800585e1  lea     r8, WPP_32285b1e2ab033aa73a29666e87f0116_Traceguids
0x1800585e8  mov     edx, 21h ; '!'
0x1800585ed  mov     r9d, ebx
0x1800585f0  call    WPP_SF_D
0x1800585f5  jmp     short loc_1800585FD
0x1800585f7  cmp     eax, 1
0x1800585fa  cmovz   ebx, edi
0x1800585fd  mov     rcx, r14; hMem
0x180058600  call    cs:__imp_LocalFree
0x180058607  nop     dword ptr [rax+rax+00h]
0x18005860c  mov     eax, ebx
0x18005860e  mov     rbx, [rsp+60h+arg_8]
0x180058616  add     rsp, 60h
0x18005861a  pop     r15
0x18005861c  pop     r14
0x18005861e  pop     r13
0x180058620  pop     r12
0x180058622  pop     rdi
0x180058623  pop     rsi
0x180058624  pop     rbp
0x180058625  retn
```
