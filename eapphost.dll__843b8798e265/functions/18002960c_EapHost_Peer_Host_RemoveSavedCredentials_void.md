# EapHost::Peer::Host::RemoveSavedCredentials(void)

- ea: `0x18002960c`
- end: `0x1800297cc`
- name: `?RemoveSavedCredentials@Host@Peer@EapHost@@AEAAXXZ`
- size: `448`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005d60`

## callees

- `0x18000a24c`
- `0x180024c64`
- `0x180025c40`
- `0x18002960c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002966f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002966f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029791`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029636`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180029636`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002973b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002973b`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180029658`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800296d4`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180029658`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800296d4`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::RemoveSavedCredentials(EapHost::Peer::Host *this)
{
  void *v2; // rcx
  DWORD LastError; // eax
  DWORD v4; // esi
  unsigned int v5; // edx
  DWORD v6; // eax
  DWORD v7; // esi
  unsigned int v8; // edx
  DWORD v9; // eax
  struct _NgcTicketContext **v10; // rdx
  struct _GUID v11; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 14) == 1 )
  {
    v2 = (void *)*((_QWORD *)this + 4);
    if ( v2 != (void *)-1LL )
    {
      if ( ImpersonateLoggedOnUser(v2) )
      {
        if ( CredDeleteW(L"*Session", 2u, 0) )
        {
          v5 = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              82,
              WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids,
              LastError);
          }
          v5 = v4;
        }
        v11 = (struct _GUID)*((_OWORD *)this + 1);
        EapHostTelemetry::CredentialUnPlumbing(2u, v5, &v11);
        if ( CredDeleteW(L"*Session", 3u, 0) )
        {
          v8 = 0;
        }
        else
        {
          v6 = GetLastError();
          v7 = v6;
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, v6);
          }
          v8 = v7;
        }
        v11 = (struct _GUID)*((_OWORD *)this + 1);
        EapHostTelemetry::CredentialUnPlumbing(3u, v8, &v11);
        RevertToSelf();
      }
      else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, v9);
      }
      CloseHandle(*((HANDLE *)this + 4));
      *((_QWORD *)this + 4) = -1;
      *((_OWORD *)this + 1) = 0;
      if ( *((_QWORD *)this + 6) )
        EapHost::Peer::FreeApplicationTicket((EapHost::Peer::Host *)((char *)this + 48), v10);
    }
  }
}

```

## disassembly

```asm
0x18002960c  mov     [rsp+arg_0], rbx
0x180029611  mov     [rsp+arg_8], rsi
0x180029616  push    rdi
0x180029617  sub     rsp, 30h
0x18002961b  cmp     dword ptr [rcx+38h], 1
0x18002961f  mov     rbx, rcx
0x180029622  jnz     loc_1800297BB
0x180029628  mov     rcx, [rcx+20h]; hToken
0x18002962c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029630  jz      loc_1800297BB
0x180029636  call    cs:__imp_ImpersonateLoggedOnUser
0x18002963d  nop     dword ptr [rax+rax+00h]
0x180029642  test    eax, eax
0x180029644  jz      loc_180029749
0x18002964a  xor     r8d, r8d; Flags
0x18002964d  lea     rcx, TargetName; "*Session"
0x180029654  lea     edx, [r8+2]; Type
0x180029658  call    cs:__imp_CredDeleteW
0x18002965f  nop     dword ptr [rax+rax+00h]
0x180029664  lea     rdi, WPP_GLOBAL_Control
0x18002966b  test    eax, eax
0x18002966d  jnz     short loc_1800296AB
0x18002966f  call    cs:__imp_GetLastError
0x180029676  nop     dword ptr [rax+rax+00h]
0x18002967b  mov     esi, eax
0x18002967d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029684  cmp     rcx, rdi
0x180029687  jz      short loc_1800296A7
0x180029689  test    byte ptr [rcx+1Ch], 1
0x18002968d  jz      short loc_1800296A7
0x18002968f  mov     rcx, [rcx+10h]
0x180029693  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002969a  mov     edx, 52h ; 'R'
0x18002969f  mov     r9d, eax
0x1800296a2  call    WPP_SF_d
0x1800296a7  mov     edx, esi
0x1800296a9  jmp     short loc_1800296AD
0x1800296ab  xor     edx, edx; unsigned int
0x1800296ad  movups  xmm0, xmmword ptr [rbx+10h]
0x1800296b1  lea     r8, [rsp+38h+var_18]; struct _GUID *
0x1800296b6  mov     ecx, 2; unsigned int
0x1800296bb  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1800296c1  call    ?CredentialUnPlumbing@EapHostTelemetry@@SAXKKAEBU_GUID@@@Z; EapHostTelemetry::CredentialUnPlumbing(ulong,ulong,_GUID const &)
0x1800296c6  xor     r8d, r8d; Flags
0x1800296c9  lea     rcx, TargetName; "*Session"
0x1800296d0  lea     edx, [r8+3]; Type
0x1800296d4  call    cs:__imp_CredDeleteW
0x1800296db  nop     dword ptr [rax+rax+00h]
0x1800296e0  test    eax, eax
0x1800296e2  jnz     short loc_180029720
0x1800296e4  call    cs:__imp_GetLastError
0x1800296eb  nop     dword ptr [rax+rax+00h]
0x1800296f0  mov     esi, eax
0x1800296f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296f9  cmp     rcx, rdi
0x1800296fc  jz      short loc_18002971C
0x1800296fe  test    byte ptr [rcx+1Ch], 1
0x180029702  jz      short loc_18002971C
0x180029704  mov     rcx, [rcx+10h]
0x180029708  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002970f  mov     edx, 53h ; 'S'
0x180029714  mov     r9d, eax
0x180029717  call    WPP_SF_d
0x18002971c  mov     edx, esi
0x18002971e  jmp     short loc_180029722
0x180029720  xor     edx, edx; unsigned int
0x180029722  movups  xmm0, xmmword ptr [rbx+10h]
0x180029726  lea     r8, [rsp+38h+var_18]; struct _GUID *
0x18002972b  mov     ecx, 3; unsigned int
0x180029730  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x180029736  call    ?CredentialUnPlumbing@EapHostTelemetry@@SAXKKAEBU_GUID@@@Z; EapHostTelemetry::CredentialUnPlumbing(ulong,ulong,_GUID const &)
0x18002973b  call    cs:__imp_RevertToSelf
0x180029742  nop     dword ptr [rax+rax+00h]
0x180029747  jmp     short loc_18002978D
0x180029749  mov     rax, cs:WPP_GLOBAL_Control
0x180029750  lea     rdi, WPP_GLOBAL_Control
0x180029757  cmp     rax, rdi
0x18002975a  jz      short loc_18002978D
0x18002975c  test    byte ptr [rax+1Ch], 1
0x180029760  jz      short loc_18002978D
0x180029762  call    cs:__imp_GetLastError
0x180029769  nop     dword ptr [rax+rax+00h]
0x18002976e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029775  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002977c  mov     edx, 54h ; 'T'
0x180029781  mov     r9d, eax
0x180029784  mov     rcx, [rcx+10h]
0x180029788  call    WPP_SF_d
0x18002978d  mov     rcx, [rbx+20h]; hObject
0x180029791  call    cs:__imp_CloseHandle
0x180029798  nop     dword ptr [rax+rax+00h]
0x18002979d  xorps   xmm0, xmm0
0x1800297a0  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x1800297a8  lea     rcx, [rbx+30h]; this
0x1800297ac  movups  xmmword ptr [rbx+10h], xmm0
0x1800297b0  cmp     qword ptr [rcx], 0
0x1800297b4  jz      short loc_1800297BB
0x1800297b6  call    ?FreeApplicationTicket@Peer@EapHost@@YAKPEAPEAU_NgcTicketContext@@@Z; EapHost::Peer::FreeApplicationTicket(_NgcTicketContext * *)
0x1800297bb  mov     rbx, [rsp+38h+arg_0]
0x1800297c0  mov     rsi, [rsp+38h+arg_8]
0x1800297c5  add     rsp, 30h
0x1800297c9  pop     rdi
0x1800297ca  retn
```
