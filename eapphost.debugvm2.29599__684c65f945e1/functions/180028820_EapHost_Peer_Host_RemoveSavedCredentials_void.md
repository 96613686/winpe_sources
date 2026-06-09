# EapHost::Peer::Host::RemoveSavedCredentials(void)

- ea: `0x180028820`
- end: `0x1800289af`
- name: `?RemoveSavedCredentials@Host@Peer@EapHost@@AEAAXXZ`
- size: `399`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180009dec`
- `0x180023f90`
- `0x180024f50`
- `0x180028820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002897b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002897b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002884a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002884a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028931`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028931`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180028866`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800288d6`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180028866`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800288d6`

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
0x180028820  mov     [rsp+arg_0], rbx
0x180028825  mov     [rsp+arg_8], rsi
0x18002882a  push    rdi
0x18002882b  sub     rsp, 30h
0x18002882f  cmp     dword ptr [rcx+38h], 1
0x180028833  mov     rbx, rcx
0x180028836  jnz     loc_18002899F
0x18002883c  mov     rcx, [rcx+20h]; hToken
0x180028840  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180028844  jz      loc_18002899F
0x18002884a  call    cs:__imp_ImpersonateLoggedOnUser
0x180028850  test    eax, eax
0x180028852  jz      loc_180028939
0x180028858  xor     r8d, r8d; Flags
0x18002885b  lea     rcx, TargetName; "*Session"
0x180028862  lea     edx, [r8+2]; Type
0x180028866  call    cs:__imp_CredDeleteW
0x18002886c  lea     rdi, WPP_GLOBAL_Control
0x180028873  test    eax, eax
0x180028875  jnz     short loc_1800288AD
0x180028877  call    cs:__imp_GetLastError
0x18002887d  mov     esi, eax
0x18002887f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028886  cmp     rcx, rdi
0x180028889  jz      short loc_1800288A9
0x18002888b  test    byte ptr [rcx+1Ch], 1
0x18002888f  jz      short loc_1800288A9
0x180028891  mov     rcx, [rcx+10h]
0x180028895  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002889c  mov     edx, 52h ; 'R'
0x1800288a1  mov     r9d, eax
0x1800288a4  call    WPP_SF_d
0x1800288a9  mov     edx, esi
0x1800288ab  jmp     short loc_1800288AF
0x1800288ad  xor     edx, edx; unsigned int
0x1800288af  movups  xmm0, xmmword ptr [rbx+10h]
0x1800288b3  lea     r8, [rsp+38h+var_18]; struct _GUID *
0x1800288b8  mov     ecx, 2; unsigned int
0x1800288bd  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1800288c3  call    ?CredentialUnPlumbing@EapHostTelemetry@@SAXKKAEBU_GUID@@@Z; EapHostTelemetry::CredentialUnPlumbing(ulong,ulong,_GUID const &)
0x1800288c8  xor     r8d, r8d; Flags
0x1800288cb  lea     rcx, TargetName; "*Session"
0x1800288d2  lea     edx, [r8+3]; Type
0x1800288d6  call    cs:__imp_CredDeleteW
0x1800288dc  test    eax, eax
0x1800288de  jnz     short loc_180028916
0x1800288e0  call    cs:__imp_GetLastError
0x1800288e6  mov     esi, eax
0x1800288e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288ef  cmp     rcx, rdi
0x1800288f2  jz      short loc_180028912
0x1800288f4  test    byte ptr [rcx+1Ch], 1
0x1800288f8  jz      short loc_180028912
0x1800288fa  mov     rcx, [rcx+10h]
0x1800288fe  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180028905  mov     edx, 53h ; 'S'
0x18002890a  mov     r9d, eax
0x18002890d  call    WPP_SF_d
0x180028912  mov     edx, esi
0x180028914  jmp     short loc_180028918
0x180028916  xor     edx, edx; unsigned int
0x180028918  movups  xmm0, xmmword ptr [rbx+10h]
0x18002891c  lea     r8, [rsp+38h+var_18]; struct _GUID *
0x180028921  mov     ecx, 3; unsigned int
0x180028926  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x18002892c  call    ?CredentialUnPlumbing@EapHostTelemetry@@SAXKKAEBU_GUID@@@Z; EapHostTelemetry::CredentialUnPlumbing(ulong,ulong,_GUID const &)
0x180028931  call    cs:__imp_RevertToSelf
0x180028937  jmp     short loc_180028977
0x180028939  mov     rax, cs:WPP_GLOBAL_Control
0x180028940  lea     rdi, WPP_GLOBAL_Control
0x180028947  cmp     rax, rdi
0x18002894a  jz      short loc_180028977
0x18002894c  test    byte ptr [rax+1Ch], 1
0x180028950  jz      short loc_180028977
0x180028952  call    cs:__imp_GetLastError
0x180028958  mov     rcx, cs:WPP_GLOBAL_Control
0x18002895f  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180028966  mov     edx, 54h ; 'T'
0x18002896b  mov     r9d, eax
0x18002896e  mov     rcx, [rcx+10h]
0x180028972  call    WPP_SF_d
0x180028977  mov     rcx, [rbx+20h]; hObject
0x18002897b  call    cs:__imp_CloseHandle
0x180028981  xorps   xmm0, xmm0
0x180028984  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18002898c  lea     rcx, [rbx+30h]; this
0x180028990  movups  xmmword ptr [rbx+10h], xmm0
0x180028994  cmp     qword ptr [rcx], 0
0x180028998  jz      short loc_18002899F
0x18002899a  call    ?FreeApplicationTicket@Peer@EapHost@@YAKPEAPEAU_NgcTicketContext@@@Z; EapHost::Peer::FreeApplicationTicket(_NgcTicketContext * *)
0x18002899f  mov     rbx, [rsp+38h+arg_0]
0x1800289a4  mov     rsi, [rsp+38h+arg_8]
0x1800289a9  add     rsp, 30h
0x1800289ad  pop     rdi
0x1800289ae  retn
```
