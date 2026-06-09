# CNat::IsClientAllowedToCallUs(void)

- ea: `0x180033e0c`
- end: `0x18003400a`
- name: `?IsClientAllowedToCallUs@CNat@@AEAA_NXZ`
- size: `510`
- prototype: `bool __fastcall(CNat *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180033c20`
- `0x180088200`
- `0x180088570`
- `0x180088820`
- `0x180088eb0`
- `0x180089100`
- `0x1800896d0`
- `0x1800898a0`
- `0x1800899b0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180033e0c`
- `0x180089548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033eb4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033eb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033f6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033f6e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180033e50`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180033e50`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033fbd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180033fbd`

## pseudocode

```c
bool __fastcall CNat::IsClientAllowedToCallUs(void **this)
{
  HRESULT v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  bool IsTokenPartOfWellKnowSid; // bl
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
  }
  v2 = CoImpersonateClient();
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v4 = 21;
LABEL_36:
    WPP_SF_d(v3[2], v4, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, (unsigned int)v2);
    return 0;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    IsTokenPartOfWellKnowSid = CNat::IsTokenPartOfWellKnowSid((CNat *)this, TokenHandle, WinLocalServiceSid, this + 14);
    if ( IsTokenPartOfWellKnowSid )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_26;
      }
      v8 = 22;
    }
    else
    {
      IsTokenPartOfWellKnowSid = CNat::IsTokenPartOfWellKnowSid((CNat *)this, TokenHandle, WinLocalSystemSid, this + 15);
      if ( IsTokenPartOfWellKnowSid )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_26;
        }
        v8 = 23;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_26;
        }
        v8 = 24;
      }
    }
    WPP_SF_(v7[2], v8, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
LABEL_26:
    CloseHandle(TokenHandle);
    goto LABEL_31;
  }
  IsTokenPartOfWellKnowSid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, LastError);
  }
LABEL_31:
  v2 = CoRevertToSelf();
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v4 = 26;
    goto LABEL_36;
  }
  return IsTokenPartOfWellKnowSid;
}

```

## disassembly

```asm
0x180033e0c  push    rbx
0x180033e0e  push    rbp
0x180033e0f  push    rdi
0x180033e10  push    r14
0x180033e12  sub     rsp, 28h
0x180033e16  mov     rdi, rcx
0x180033e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e20  lea     rbp, WPP_GLOBAL_Control
0x180033e27  lea     r14, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180033e2e  cmp     rcx, rbp
0x180033e31  jz      short loc_180033E50
0x180033e33  test    byte ptr [rcx+1Ch], 1
0x180033e37  jz      short loc_180033E50
0x180033e39  cmp     byte ptr [rcx+19h], 6
0x180033e3d  jb      short loc_180033E50
0x180033e3f  mov     rcx, [rcx+10h]
0x180033e43  mov     edx, 14h
0x180033e48  mov     r8, r14
0x180033e4b  call    WPP_SF_
0x180033e50  call    cs:__imp_CoImpersonateClient
0x180033e57  nop     dword ptr [rax+rax+00h]
0x180033e5c  test    eax, eax
0x180033e5e  jns     short loc_180033E8E
0x180033e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e67  cmp     rcx, rbp
0x180033e6a  jz      loc_180033FF9
0x180033e70  test    byte ptr [rcx+1Ch], 1
0x180033e74  jz      loc_180033FF9
0x180033e7a  cmp     byte ptr [rcx+19h], 2
0x180033e7e  jb      loc_180033FF9
0x180033e84  mov     edx, 15h
0x180033e89  jmp     loc_180033FEA
0x180033e8e  mov     [rsp+48h+TokenHandle], 0
0x180033e97  call    cs:__imp_GetCurrentThread
0x180033e9e  nop     dword ptr [rax+rax+00h]
0x180033ea3  mov     edx, 8; DesiredAccess
0x180033ea8  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180033ead  mov     rcx, rax; ThreadHandle
0x180033eb0  lea     r8d, [rdx-7]; OpenAsSelf
0x180033eb4  call    cs:__imp_OpenThreadToken
0x180033ebb  nop     dword ptr [rax+rax+00h]
0x180033ec0  test    eax, eax
0x180033ec2  jz      loc_180033F7C
0x180033ec8  mov     rdx, [rsp+48h+TokenHandle]; void *
0x180033ecd  lea     r9, [rdi+70h]; void **
0x180033ed1  mov     r8d, 17h; enum WELL_KNOWN_SID_TYPE
0x180033ed7  mov     rcx, rdi; this
0x180033eda  call    ?IsTokenPartOfWellKnowSid@CNat@@AEAA_NPEAXW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z; CNat::IsTokenPartOfWellKnowSid(void *,WELL_KNOWN_SID_TYPE,void * &)
0x180033edf  mov     bl, al
0x180033ee1  test    al, al
0x180033ee3  jz      short loc_180033F04
0x180033ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033eec  cmp     rcx, rbp
0x180033eef  jz      short loc_180033F69
0x180033ef1  test    byte ptr [rcx+1Ch], 1
0x180033ef5  jz      short loc_180033F69
0x180033ef7  cmp     byte ptr [rcx+19h], 4
0x180033efb  jb      short loc_180033F69
0x180033efd  mov     edx, 16h
0x180033f02  jmp     short loc_180033F5D
0x180033f04  mov     rdx, [rsp+48h+TokenHandle]; void *
0x180033f09  lea     r9, [rdi+78h]; void **
0x180033f0d  mov     r8d, 16h; enum WELL_KNOWN_SID_TYPE
0x180033f13  mov     rcx, rdi; this
0x180033f16  call    ?IsTokenPartOfWellKnowSid@CNat@@AEAA_NPEAXW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z; CNat::IsTokenPartOfWellKnowSid(void *,WELL_KNOWN_SID_TYPE,void * &)
0x180033f1b  mov     bl, al
0x180033f1d  test    al, al
0x180033f1f  jz      short loc_180033F40
0x180033f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f28  cmp     rcx, rbp
0x180033f2b  jz      short loc_180033F69
0x180033f2d  test    byte ptr [rcx+1Ch], 1
0x180033f31  jz      short loc_180033F69
0x180033f33  cmp     byte ptr [rcx+19h], 4
0x180033f37  jb      short loc_180033F69
0x180033f39  mov     edx, 17h
0x180033f3e  jmp     short loc_180033F5D
0x180033f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f47  cmp     rcx, rbp
0x180033f4a  jz      short loc_180033F69
0x180033f4c  test    byte ptr [rcx+1Ch], 1
0x180033f50  jz      short loc_180033F69
0x180033f52  cmp     byte ptr [rcx+19h], 4
0x180033f56  jb      short loc_180033F69
0x180033f58  mov     edx, 18h
0x180033f5d  mov     rcx, [rcx+10h]
0x180033f61  mov     r8, r14
0x180033f64  call    WPP_SF_
0x180033f69  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180033f6e  call    cs:__imp_CloseHandle
0x180033f75  nop     dword ptr [rax+rax+00h]
0x180033f7a  jmp     short loc_180033FBD
0x180033f7c  mov     rax, cs:WPP_GLOBAL_Control
0x180033f83  xor     bl, bl
0x180033f85  cmp     rax, rbp
0x180033f88  jz      short loc_180033FBD
0x180033f8a  test    byte ptr [rax+1Ch], 1
0x180033f8e  jz      short loc_180033FBD
0x180033f90  cmp     byte ptr [rax+19h], 2
0x180033f94  jb      short loc_180033FBD
0x180033f96  call    cs:__imp_GetLastError
0x180033f9d  nop     dword ptr [rax+rax+00h]
0x180033fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fa9  mov     edx, 19h
0x180033fae  mov     r9d, eax
0x180033fb1  mov     r8, r14
0x180033fb4  mov     rcx, [rcx+10h]
0x180033fb8  call    WPP_SF_d
0x180033fbd  call    cs:__imp_CoRevertToSelf
0x180033fc4  nop     dword ptr [rax+rax+00h]
0x180033fc9  test    eax, eax
0x180033fcb  jns     short loc_180033FFD
0x180033fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fd4  cmp     rcx, rbp
0x180033fd7  jz      short loc_180033FF9
0x180033fd9  test    byte ptr [rcx+1Ch], 1
0x180033fdd  jz      short loc_180033FF9
0x180033fdf  cmp     byte ptr [rcx+19h], 2
0x180033fe3  jb      short loc_180033FF9
0x180033fe5  mov     edx, 1Ah
0x180033fea  mov     rcx, [rcx+10h]
0x180033fee  mov     r9d, eax
0x180033ff1  mov     r8, r14
0x180033ff4  call    WPP_SF_d
0x180033ff9  xor     al, al
0x180033ffb  jmp     short loc_180033FFF
0x180033ffd  mov     al, bl
0x180033fff  add     rsp, 28h
0x180034003  pop     r14
0x180034005  pop     rdi
0x180034006  pop     rbp
0x180034007  pop     rbx
0x180034008  retn
```
