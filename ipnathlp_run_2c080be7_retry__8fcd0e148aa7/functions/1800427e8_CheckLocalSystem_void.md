# CheckLocalSystem(void)

- ea: `0x1800427e8`
- end: `0x18004296d`
- name: `?CheckLocalSystem@@YA_NXZ`
- size: `389`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006e900`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800427e8`
- `0x180051f30`
- `0x180052bf4`
- `0x180059a04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004287a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004287a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428c9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800428b9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800428b9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004286a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004286a`

## pseudocode

```c
bool CheckLocalSystem(void)
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  PVOID *v2; // rcx
  __int64 v3; // rdx
  bool v5; // [rsp+20h] [rbp-88h]
  WINBOOL IsMember; // [rsp+30h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+34h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids);
  }
  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  IsMember = 0;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid) )
  {
    v1 = 0;
    if ( CheckTokenMembership(0, pSid, &IsMember) )
    {
LABEL_16:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    LastError = GetLastError();
    v1 = LastError;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return IsMember != 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v3 = 41;
LABEL_15:
    WPP_SF_d(v2[2], v3, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, LastError);
    goto LABEL_16;
  }
  LastError = GetLastError();
  v1 = LastError;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return IsMember != 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = 40;
    goto LABEL_15;
  }
LABEL_17:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v5 = IsMember != 0;
    WPP_SF_Dc(v2[2], 42, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, v1, v5);
  }
  return IsMember != 0;
}

```

## disassembly

```asm
0x1800427e8  mov     [rsp+arg_0], rbx
0x1800427ed  push    rsi
0x1800427ee  sub     rsp, 0A0h
0x1800427f5  mov     rax, cs:__security_cookie
0x1800427fc  xor     rax, rsp
0x1800427ff  mov     [rsp+0A8h+var_18], rax
0x180042807  mov     rcx, cs:WPP_GLOBAL_Control
0x18004280e  lea     rsi, WPP_GLOBAL_Control
0x180042815  cmp     rcx, rsi
0x180042818  jz      short loc_18004283B
0x18004281a  test    byte ptr [rcx+1Ch], 40h
0x18004281e  jz      short loc_18004283B
0x180042820  cmp     byte ptr [rcx+19h], 6
0x180042824  jb      short loc_18004283B
0x180042826  mov     rcx, [rcx+10h]
0x18004282a  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x180042831  mov     edx, 27h ; '''
0x180042836  call    WPP_SF_
0x18004283b  mov     ebx, 44h ; 'D'
0x180042840  lea     rcx, [rsp+0A8h+pSid]; void *
0x180042845  mov     r8d, ebx; Size
0x180042848  xor     edx, edx; Val
0x18004284a  call    memset_0
0x18004284f  lea     r9, [rsp+0A8h+cbSid]; cbSid
0x180042854  mov     [rsp+0A8h+cbSid], ebx
0x180042858  lea     r8, [rsp+0A8h+pSid]; pSid
0x18004285d  mov     [rsp+0A8h+IsMember], 0
0x180042865  xor     edx, edx; DomainSid
0x180042867  lea     ecx, [rbx-2Eh]; WellKnownSidType
0x18004286a  call    cs:__imp_CreateWellKnownSid
0x180042871  nop     dword ptr [rax+rax+00h]
0x180042876  test    eax, eax
0x180042878  jnz     short loc_1800428AB
0x18004287a  call    cs:__imp_GetLastError
0x180042881  nop     dword ptr [rax+rax+00h]
0x180042886  mov     ebx, eax
0x180042888  mov     rcx, cs:WPP_GLOBAL_Control
0x18004288f  cmp     rcx, rsi
0x180042892  jz      loc_180042943
0x180042898  test    byte ptr [rcx+1Ch], 40h
0x18004289c  jz      short loc_18004290E
0x18004289e  cmp     byte ptr [rcx+19h], 2
0x1800428a2  jb      short loc_18004290E
0x1800428a4  mov     edx, 28h ; '('
0x1800428a9  jmp     short loc_1800428F4
0x1800428ab  lea     r8, [rsp+0A8h+IsMember]; IsMember
0x1800428b0  xor     ecx, ecx; TokenHandle
0x1800428b2  lea     rdx, [rsp+0A8h+pSid]; SidToCheck
0x1800428b7  xor     ebx, ebx
0x1800428b9  call    cs:__imp_CheckTokenMembership
0x1800428c0  nop     dword ptr [rax+rax+00h]
0x1800428c5  test    eax, eax
0x1800428c7  jnz     short loc_180042907
0x1800428c9  call    cs:__imp_GetLastError
0x1800428d0  nop     dword ptr [rax+rax+00h]
0x1800428d5  mov     ebx, eax
0x1800428d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428de  cmp     rcx, rsi
0x1800428e1  jz      short loc_180042943
0x1800428e3  test    byte ptr [rcx+1Ch], 40h
0x1800428e7  jz      short loc_18004290E
0x1800428e9  cmp     byte ptr [rcx+19h], 2
0x1800428ed  jb      short loc_18004290E
0x1800428ef  mov     edx, 29h ; ')'
0x1800428f4  mov     rcx, [rcx+10h]
0x1800428f8  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x1800428ff  mov     r9d, eax
0x180042902  call    WPP_SF_d
0x180042907  mov     rcx, cs:WPP_GLOBAL_Control
0x18004290e  cmp     rcx, rsi
0x180042911  jz      short loc_180042943
0x180042913  test    byte ptr [rcx+1Ch], 40h
0x180042917  jz      short loc_180042943
0x180042919  cmp     byte ptr [rcx+19h], 6
0x18004291d  jb      short loc_180042943
0x18004291f  cmp     [rsp+0A8h+IsMember], 0
0x180042924  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18004292b  mov     rcx, [rcx+10h]
0x18004292f  mov     edx, 2Ah ; '*'
0x180042934  setnz   al
0x180042937  mov     r9d, ebx
0x18004293a  mov     [rsp+0A8h+var_88], al
0x18004293e  call    WPP_SF_Dc
0x180042943  cmp     [rsp+0A8h+IsMember], 0
0x180042948  setnz   al
0x18004294b  mov     rcx, [rsp+0A8h+var_18]
0x180042953  xor     rcx, rsp; StackCookie
0x180042956  call    __security_check_cookie
0x18004295b  mov     rbx, [rsp+0A8h+arg_0]
0x180042963  add     rsp, 0A0h
0x18004296a  pop     rsi
0x18004296b  retn
```
