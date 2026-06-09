# EapHost::Peer::Host::CaptureSessionCreds(EapHost::Peer::Host::SessionCredType,EapHost::Peer::PeerSession &)

- ea: `0x18002367c`
- end: `0x1800237fa`
- name: `?CaptureSessionCreds@Host@Peer@EapHost@@AEAAXW4SessionCredType@123@AEAVPeerSession@23@@Z`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023380`
- `0x180023834`
- `0x180024a8c`

## callees

- `0x180009dc4`
- `0x180009dec`
- `0x18002367c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002374e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002374e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237ca`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800236f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800236f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800237ae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800237ae`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18002373d`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18002373d`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18002369d`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18002369d`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::CaptureSessionCreds(__int64 a1, int a2, __int64 a3)
{
  PVOID *v4; // rbx
  void *v5; // rcx
  DWORD LastError; // eax
  EapHost::Peer::Host *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // eax

  v4 = (PVOID *)((a2 != 0 ? 8 : 0) + a1);
  if ( *v4 )
  {
    CredFree(*v4);
    *v4 = 0;
  }
  v5 = *(void **)(a3 + 200);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
    }
    return;
  }
  if ( !ImpersonateLoggedOnUser(v5) )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return;
    }
    v8 = 74;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, LastError);
    return;
  }
  if ( !CredReadW(L"*Session", 2u, 0, (PCREDENTIALW *)v4) )
  {
    v9 = GetLastError();
    if ( v9 == 1168 )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, v9);
    }
  }
  if ( !RevertToSelf()
    && WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    v8 = 77;
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x18002367c  mov     [rsp+arg_0], rbx
0x180023681  push    rdi
0x180023682  sub     rsp, 20h
0x180023686  neg     edx
0x180023688  mov     rdi, r8
0x18002368b  sbb     rax, rax
0x18002368e  and     eax, 8
0x180023691  lea     rbx, [rax+rcx]
0x180023695  mov     rcx, [rbx]; Buffer
0x180023698  test    rcx, rcx
0x18002369b  jz      short loc_1800236AA
0x18002369d  call    cs:__imp_CredFree
0x1800236a3  mov     qword ptr [rbx], 0
0x1800236aa  mov     rcx, [rdi+0C8h]; hToken
0x1800236b1  test    rcx, rcx
0x1800236b4  jnz     short loc_1800236F1
0x1800236b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236bd  lea     rbx, WPP_GLOBAL_Control
0x1800236c4  cmp     rcx, rbx
0x1800236c7  jz      loc_1800237EF
0x1800236cd  test    byte ptr [rcx+1Ch], 1
0x1800236d1  jz      loc_1800237EF
0x1800236d7  mov     rcx, [rcx+10h]
0x1800236db  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800236e2  mov     edx, 49h ; 'I'
0x1800236e7  call    WPP_SF_
0x1800236ec  jmp     loc_1800237EF
0x1800236f1  call    cs:__imp_ImpersonateLoggedOnUser
0x1800236f7  test    eax, eax
0x1800236f9  jnz     short loc_18002372C
0x1800236fb  call    cs:__imp_GetLastError
0x180023701  mov     rcx, cs:WPP_GLOBAL_Control
0x180023708  lea     rbx, WPP_GLOBAL_Control
0x18002370f  cmp     rcx, rbx
0x180023712  jz      loc_1800237EF
0x180023718  test    byte ptr [rcx+1Ch], 1
0x18002371c  jz      loc_1800237EF
0x180023722  mov     edx, 4Ah ; 'J'
0x180023727  jmp     loc_1800237DC
0x18002372c  xor     r8d, r8d; Flags
0x18002372f  lea     rcx, TargetName; "*Session"
0x180023736  mov     r9, rbx; Credential
0x180023739  lea     edx, [r8+2]; Type
0x18002373d  call    cs:__imp_CredReadW
0x180023743  lea     rbx, WPP_GLOBAL_Control
0x18002374a  test    eax, eax
0x18002374c  jnz     short loc_1800237AE
0x18002374e  call    cs:__imp_GetLastError
0x180023754  cmp     eax, 490h
0x180023759  jnz     short loc_180023784
0x18002375b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023762  cmp     rcx, rbx
0x180023765  jz      short loc_1800237AE
0x180023767  test    byte ptr [rcx+1Ch], 4
0x18002376b  jz      short loc_1800237AE
0x18002376d  mov     rcx, [rcx+10h]
0x180023771  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180023778  mov     edx, 4Bh ; 'K'
0x18002377d  call    WPP_SF_
0x180023782  jmp     short loc_1800237AE
0x180023784  mov     rcx, cs:WPP_GLOBAL_Control
0x18002378b  cmp     rcx, rbx
0x18002378e  jz      short loc_1800237AE
0x180023790  test    byte ptr [rcx+1Ch], 1
0x180023794  jz      short loc_1800237AE
0x180023796  mov     rcx, [rcx+10h]
0x18002379a  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800237a1  mov     edx, 4Ch ; 'L'
0x1800237a6  mov     r9d, eax
0x1800237a9  call    WPP_SF_d
0x1800237ae  call    cs:__imp_RevertToSelf
0x1800237b4  test    eax, eax
0x1800237b6  jnz     short loc_1800237EF
0x1800237b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800237bf  cmp     rax, rbx
0x1800237c2  jz      short loc_1800237EF
0x1800237c4  test    byte ptr [rax+1Ch], 1
0x1800237c8  jz      short loc_1800237EF
0x1800237ca  call    cs:__imp_GetLastError
0x1800237d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237d7  mov     edx, 4Dh ; 'M'
0x1800237dc  mov     rcx, [rcx+10h]
0x1800237e0  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800237e7  mov     r9d, eax
0x1800237ea  call    WPP_SF_d
0x1800237ef  mov     rbx, [rsp+28h+arg_0]
0x1800237f4  add     rsp, 20h
0x1800237f8  pop     rdi
0x1800237f9  retn
```
