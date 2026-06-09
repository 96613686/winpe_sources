# CheckLocalSystem(void)

- ea: `0x18003f2f0`
- end: `0x18003f45c`
- name: `?CheckLocalSystem@@YA_NXZ`
- size: `364`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180069660`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18003f2f0`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180055728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3bf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003f3b5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003f3b5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003f372`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003f372`

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
0x18003f2f0  mov     [rsp+arg_0], rbx
0x18003f2f5  push    rsi
0x18003f2f6  sub     rsp, 0A0h
0x18003f2fd  mov     rax, cs:__security_cookie
0x18003f304  xor     rax, rsp
0x18003f307  mov     [rsp+0A8h+var_18], rax
0x18003f30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f316  lea     rsi, WPP_GLOBAL_Control
0x18003f31d  cmp     rcx, rsi
0x18003f320  jz      short loc_18003F343
0x18003f322  test    byte ptr [rcx+1Ch], 40h
0x18003f326  jz      short loc_18003F343
0x18003f328  cmp     byte ptr [rcx+19h], 6
0x18003f32c  jb      short loc_18003F343
0x18003f32e  mov     rcx, [rcx+10h]
0x18003f332  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18003f339  mov     edx, 27h ; '''
0x18003f33e  call    WPP_SF_
0x18003f343  mov     ebx, 44h ; 'D'
0x18003f348  lea     rcx, [rsp+0A8h+pSid]; void *
0x18003f34d  mov     r8d, ebx; Size
0x18003f350  xor     edx, edx; Val
0x18003f352  call    memset_0
0x18003f357  lea     r9, [rsp+0A8h+cbSid]; cbSid
0x18003f35c  mov     [rsp+0A8h+cbSid], ebx
0x18003f360  lea     r8, [rsp+0A8h+pSid]; pSid
0x18003f365  mov     [rsp+0A8h+IsMember], 0
0x18003f36d  xor     edx, edx; DomainSid
0x18003f36f  lea     ecx, [rbx-2Eh]; WellKnownSidType
0x18003f372  call    cs:__imp_CreateWellKnownSid
0x18003f378  test    eax, eax
0x18003f37a  jnz     short loc_18003F3A7
0x18003f37c  call    cs:__imp_GetLastError
0x18003f382  mov     ebx, eax
0x18003f384  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f38b  cmp     rcx, rsi
0x18003f38e  jz      loc_18003F433
0x18003f394  test    byte ptr [rcx+1Ch], 40h
0x18003f398  jz      short loc_18003F3FE
0x18003f39a  cmp     byte ptr [rcx+19h], 2
0x18003f39e  jb      short loc_18003F3FE
0x18003f3a0  mov     edx, 28h ; '('
0x18003f3a5  jmp     short loc_18003F3E4
0x18003f3a7  lea     r8, [rsp+0A8h+IsMember]; IsMember
0x18003f3ac  xor     ecx, ecx; TokenHandle
0x18003f3ae  lea     rdx, [rsp+0A8h+pSid]; SidToCheck
0x18003f3b3  xor     ebx, ebx
0x18003f3b5  call    cs:__imp_CheckTokenMembership
0x18003f3bb  test    eax, eax
0x18003f3bd  jnz     short loc_18003F3F7
0x18003f3bf  call    cs:__imp_GetLastError
0x18003f3c5  mov     ebx, eax
0x18003f3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3ce  cmp     rcx, rsi
0x18003f3d1  jz      short loc_18003F433
0x18003f3d3  test    byte ptr [rcx+1Ch], 40h
0x18003f3d7  jz      short loc_18003F3FE
0x18003f3d9  cmp     byte ptr [rcx+19h], 2
0x18003f3dd  jb      short loc_18003F3FE
0x18003f3df  mov     edx, 29h ; ')'
0x18003f3e4  mov     rcx, [rcx+10h]
0x18003f3e8  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18003f3ef  mov     r9d, eax
0x18003f3f2  call    WPP_SF_d
0x18003f3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3fe  cmp     rcx, rsi
0x18003f401  jz      short loc_18003F433
0x18003f403  test    byte ptr [rcx+1Ch], 40h
0x18003f407  jz      short loc_18003F433
0x18003f409  cmp     byte ptr [rcx+19h], 6
0x18003f40d  jb      short loc_18003F433
0x18003f40f  cmp     [rsp+0A8h+IsMember], 0
0x18003f414  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18003f41b  mov     rcx, [rcx+10h]
0x18003f41f  mov     edx, 2Ah ; '*'
0x18003f424  setnz   al
0x18003f427  mov     r9d, ebx
0x18003f42a  mov     [rsp+0A8h+var_88], al
0x18003f42e  call    WPP_SF_Dc
0x18003f433  cmp     [rsp+0A8h+IsMember], 0
0x18003f438  setnz   al
0x18003f43b  mov     rcx, [rsp+0A8h+var_18]
0x18003f443  xor     rcx, rsp; StackCookie
0x18003f446  call    __security_check_cookie
0x18003f44b  mov     rbx, [rsp+0A8h+arg_0]
0x18003f453  add     rsp, 0A0h
0x18003f45a  pop     rsi
0x18003f45b  retn
```
