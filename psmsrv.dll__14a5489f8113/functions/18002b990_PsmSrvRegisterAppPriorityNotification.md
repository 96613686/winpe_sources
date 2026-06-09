# PsmSrvRegisterAppPriorityNotification

- ea: `0x18002b990`
- end: `0x18002bb62`
- name: `PsmSrvRegisterAppPriorityNotification`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180008cc0`
- `0x180009b40`
- `0x18001622c`
- `0x18002b990`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002b9bf`
- `ntdll!RtlLengthSid` at `0x18002b9bf`
- `ntdll!NtCreateWnfStateName` at `0x18002baea`
- `ntdll!NtCreateWnfStateName` at `0x18002baea`
- `ntdll!RtlValidSid` at `0x18002b9d0`
- `ntdll!RtlValidSid` at `0x18002b9d0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002baa9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002baa9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002baf5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002baf5`

## pseudocode

```c
__int64 __fastcall PsmSrvRegisterAppPriorityNotification(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7)
{
  __int64 result; // rax
  __int64 v10; // r9
  int WnfStateName; // edi
  _DWORD *v12; // rbx
  __int64 v13; // rbp
  __int64 v14[9]; // [rsp+40h] [rbp-48h] BYREF

  v14[0] = 0;
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( a6 )
    {
      if ( a7 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(a5 + 2 * v10) );
        result = PsmpFindApplicationByManagerForUser(a3, a4, a5, 2 * v10 + 2, 0, v14);
        WnfStateName = result;
        if ( (int)result >= 0 )
        {
          v12 = (_DWORD *)v14[0];
          v13 = v14[0] + 328;
          RtlAcquireSRWLockExclusive(v14[0] + 328);
          if ( !v12[1708] && !v12[1709] )
            WnfStateName = NtCreateWnfStateName(v12 + 1708, 3, 0);
          RtlReleaseSRWLockExclusive(v13);
          if ( WnfStateName >= 0 )
          {
            *a7 = (v12[32] & 0x18000) != 0;
            *a6 = *((_QWORD *)v12 + 854);
          }
          PsmpDereferenceApplicationEx((__int64)v12, 0);
          return (unsigned int)WnfStateName;
        }
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
        return 3221225717LL;
      }
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
      return 3221225716LL;
    }
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return 3221225713LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002b990  push    rbx
0x18002b992  push    rbp
0x18002b993  push    rsi
0x18002b994  push    rdi
0x18002b995  push    r12
0x18002b997  push    r14
0x18002b999  push    r15
0x18002b99b  sub     rsp, 50h
0x18002b99f  xor     r12d, r12d
0x18002b9a2  mov     esi, r9d
0x18002b9a5  mov     rbx, r8
0x18002b9a8  mov     [rsp+88h+var_48], r12
0x18002b9ad  mov     edi, edx
0x18002b9af  lea     ebp, [r12+2]
0x18002b9b4  cmp     edx, ebp
0x18002b9b6  jb      loc_18002BB26
0x18002b9bc  mov     rcx, rbx; Sid
0x18002b9bf  call    cs:__imp_RtlLengthSid
0x18002b9c5  cmp     eax, edi
0x18002b9c7  jnz     loc_18002BB26
0x18002b9cd  mov     rcx, rbx; Sid
0x18002b9d0  call    cs:__imp_RtlValidSid
0x18002b9d6  test    al, al
0x18002b9d8  jz      loc_18002BB26
0x18002b9de  mov     r14, [rsp+88h+arg_28]
0x18002b9e6  test    r14, r14
0x18002b9e9  jnz     short loc_18002BA1B
0x18002b9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9f2  test    [rcx+1Ch], bpl
0x18002b9f6  jz      short loc_18002BA11
0x18002b9f8  cmp     [rcx+19h], bpl
0x18002b9fc  jb      short loc_18002BA11
0x18002b9fe  mov     rcx, [rcx+10h]
0x18002ba02  lea     edx, [rbp+1Dh]
0x18002ba05  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002ba0c  call    WPP_SF_
0x18002ba11  mov     eax, 0C00000F4h
0x18002ba16  jmp     loc_18002BB53
0x18002ba1b  mov     r15, [rsp+88h+arg_30]
0x18002ba23  test    r15, r15
0x18002ba26  jnz     short loc_18002BA59
0x18002ba28  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba2f  test    [rcx+1Ch], bpl
0x18002ba33  jz      short loc_18002BA4F
0x18002ba35  cmp     [rcx+19h], bpl
0x18002ba39  jb      short loc_18002BA4F
0x18002ba3b  mov     rcx, [rcx+10h]
0x18002ba3f  lea     edx, [r15+20h]
0x18002ba43  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002ba4a  call    WPP_SF_
0x18002ba4f  mov     eax, 0C00000F5h
0x18002ba54  jmp     loc_18002BB53
0x18002ba59  mov     r8, [rsp+88h+arg_20]
0x18002ba61  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ba65  inc     r9
0x18002ba68  cmp     [r8+r9*2], r12w
0x18002ba6d  jnz     short loc_18002BA65
0x18002ba6f  lea     rax, [rsp+88h+var_48]
0x18002ba74  mov     edx, esi
0x18002ba76  mov     [rsp+88h+var_60], rax; __int64
0x18002ba7b  lea     r9, ds:2[r9*2]
0x18002ba83  mov     rcx, rbx; Sid2
0x18002ba86  mov     [rsp+88h+var_68], r12d; int
0x18002ba8b  call    PsmpFindApplicationByManagerForUser
0x18002ba90  mov     edi, eax
0x18002ba92  test    eax, eax
0x18002ba94  js      loc_18002BB53
0x18002ba9a  mov     rbx, [rsp+88h+var_48]
0x18002ba9f  lea     rbp, [rbx+148h]
0x18002baa6  mov     rcx, rbp
0x18002baa9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002baaf  lea     rsi, [rbx+1AB0h]
0x18002bab6  cmp     [rsi], r12d
0x18002bab9  jnz     short loc_18002BAF2
0x18002babb  cmp     [rbx+1AB4h], r12d
0x18002bac2  jnz     short loc_18002BAF2
0x18002bac4  xor     r9d, r9d
0x18002bac7  lea     rax, PsmpResourceTimerDescriptor
0x18002bace  mov     [rsp+88h+var_58], rax
0x18002bad3  xor     r8d, r8d
0x18002bad6  mov     dword ptr [rsp+88h+var_60], 4
0x18002bade  mov     rcx, rsi
0x18002bae1  mov     qword ptr [rsp+88h+var_68], r12
0x18002bae6  lea     edx, [r9+3]
0x18002baea  call    cs:__imp_NtCreateWnfStateName
0x18002baf0  mov     edi, eax
0x18002baf2  mov     rcx, rbp
0x18002baf5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002bafb  test    edi, edi
0x18002bafd  js      short loc_18002BB18
0x18002baff  test    dword ptr [rbx+80h], 18000h
0x18002bb09  mov     eax, r12d
0x18002bb0c  setnz   al
0x18002bb0f  mov     [r15], eax
0x18002bb12  mov     rax, [rsi]
0x18002bb15  mov     [r14], rax
0x18002bb18  xor     edx, edx
0x18002bb1a  mov     rcx, rbx
0x18002bb1d  call    PsmpDereferenceApplicationEx
0x18002bb22  mov     eax, edi
0x18002bb24  jmp     short loc_18002BB53
0x18002bb26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb2d  test    [rcx+1Ch], bpl
0x18002bb31  jz      short loc_18002BB4E
0x18002bb33  cmp     [rcx+19h], bpl
0x18002bb37  jb      short loc_18002BB4E
0x18002bb39  mov     rcx, [rcx+10h]
0x18002bb3d  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002bb44  mov     edx, 1Eh
0x18002bb49  call    WPP_SF_
0x18002bb4e  mov     eax, 0C00000F1h
0x18002bb53  add     rsp, 50h
0x18002bb57  pop     r15
0x18002bb59  pop     r14
0x18002bb5b  pop     r12
0x18002bb5d  pop     rdi
0x18002bb5e  pop     rsi
0x18002bb5f  pop     rbp
0x18002bb60  pop     rbx
0x18002bb61  retn
```
