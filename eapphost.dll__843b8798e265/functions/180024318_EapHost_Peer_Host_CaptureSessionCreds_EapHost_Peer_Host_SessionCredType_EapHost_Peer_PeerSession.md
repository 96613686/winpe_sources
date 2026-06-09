# EapHost::Peer::Host::CaptureSessionCreds(EapHost::Peer::Host::SessionCredType,EapHost::Peer::PeerSession &)

- ea: `0x180024318`
- end: `0x1800244c1`
- name: `?CaptureSessionCreds@Host@Peer@EapHost@@AEAAXW4SessionCredType@123@AEAVPeerSession@23@@Z`
- size: `425`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024010`
- `0x1800244fc`
- `0x180025770`

## callees

- `0x18000a21c`
- `0x18000a24c`
- `0x180024318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002448a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002448a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024393`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024393`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024468`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024468`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x1800243eb`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x1800243eb`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180024339`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180024339`

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
0x180024318  mov     [rsp+arg_0], rbx
0x18002431d  push    rdi
0x18002431e  sub     rsp, 20h
0x180024322  neg     edx
0x180024324  mov     rdi, r8
0x180024327  sbb     rax, rax
0x18002432a  and     eax, 8
0x18002432d  lea     rbx, [rax+rcx]
0x180024331  mov     rcx, [rbx]; Buffer
0x180024334  test    rcx, rcx
0x180024337  jz      short loc_18002434C
0x180024339  call    cs:__imp_CredFree
0x180024340  nop     dword ptr [rax+rax+00h]
0x180024345  mov     qword ptr [rbx], 0
0x18002434c  mov     rcx, [rdi+0C8h]; hToken
0x180024353  test    rcx, rcx
0x180024356  jnz     short loc_180024393
0x180024358  mov     rcx, cs:WPP_GLOBAL_Control
0x18002435f  lea     rbx, WPP_GLOBAL_Control
0x180024366  cmp     rcx, rbx
0x180024369  jz      loc_1800244B5
0x18002436f  test    byte ptr [rcx+1Ch], 1
0x180024373  jz      loc_1800244B5
0x180024379  mov     rcx, [rcx+10h]
0x18002437d  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180024384  mov     edx, 49h ; 'I'
0x180024389  call    WPP_SF_
0x18002438e  jmp     loc_1800244B5
0x180024393  call    cs:__imp_ImpersonateLoggedOnUser
0x18002439a  nop     dword ptr [rax+rax+00h]
0x18002439f  test    eax, eax
0x1800243a1  jnz     short loc_1800243DA
0x1800243a3  call    cs:__imp_GetLastError
0x1800243aa  nop     dword ptr [rax+rax+00h]
0x1800243af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243b6  lea     rbx, WPP_GLOBAL_Control
0x1800243bd  cmp     rcx, rbx
0x1800243c0  jz      loc_1800244B5
0x1800243c6  test    byte ptr [rcx+1Ch], 1
0x1800243ca  jz      loc_1800244B5
0x1800243d0  mov     edx, 4Ah ; 'J'
0x1800243d5  jmp     loc_1800244A2
0x1800243da  xor     r8d, r8d; Flags
0x1800243dd  lea     rcx, TargetName; "*Session"
0x1800243e4  mov     r9, rbx; Credential
0x1800243e7  lea     edx, [r8+2]; Type
0x1800243eb  call    cs:__imp_CredReadW
0x1800243f2  nop     dword ptr [rax+rax+00h]
0x1800243f7  lea     rbx, WPP_GLOBAL_Control
0x1800243fe  test    eax, eax
0x180024400  jnz     short loc_180024468
0x180024402  call    cs:__imp_GetLastError
0x180024409  nop     dword ptr [rax+rax+00h]
0x18002440e  cmp     eax, 490h
0x180024413  jnz     short loc_18002443E
0x180024415  mov     rcx, cs:WPP_GLOBAL_Control
0x18002441c  cmp     rcx, rbx
0x18002441f  jz      short loc_180024468
0x180024421  test    byte ptr [rcx+1Ch], 4
0x180024425  jz      short loc_180024468
0x180024427  mov     rcx, [rcx+10h]
0x18002442b  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180024432  mov     edx, 4Bh ; 'K'
0x180024437  call    WPP_SF_
0x18002443c  jmp     short loc_180024468
0x18002443e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024445  cmp     rcx, rbx
0x180024448  jz      short loc_180024468
0x18002444a  test    byte ptr [rcx+1Ch], 1
0x18002444e  jz      short loc_180024468
0x180024450  mov     rcx, [rcx+10h]
0x180024454  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002445b  mov     edx, 4Ch ; 'L'
0x180024460  mov     r9d, eax
0x180024463  call    WPP_SF_d
0x180024468  call    cs:__imp_RevertToSelf
0x18002446f  nop     dword ptr [rax+rax+00h]
0x180024474  test    eax, eax
0x180024476  jnz     short loc_1800244B5
0x180024478  mov     rax, cs:WPP_GLOBAL_Control
0x18002447f  cmp     rax, rbx
0x180024482  jz      short loc_1800244B5
0x180024484  test    byte ptr [rax+1Ch], 1
0x180024488  jz      short loc_1800244B5
0x18002448a  call    cs:__imp_GetLastError
0x180024491  nop     dword ptr [rax+rax+00h]
0x180024496  mov     rcx, cs:WPP_GLOBAL_Control
0x18002449d  mov     edx, 4Dh ; 'M'
0x1800244a2  mov     rcx, [rcx+10h]
0x1800244a6  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800244ad  mov     r9d, eax
0x1800244b0  call    WPP_SF_d
0x1800244b5  mov     rbx, [rsp+28h+arg_0]
0x1800244ba  add     rsp, 20h
0x1800244be  pop     rdi
0x1800244bf  retn
```
