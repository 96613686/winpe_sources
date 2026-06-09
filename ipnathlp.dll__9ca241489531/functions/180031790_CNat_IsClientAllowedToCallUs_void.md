# CNat::IsClientAllowedToCallUs(void)

- ea: `0x180031790`
- end: `0x180031969`
- name: `?IsClientAllowedToCallUs@CNat@@AEAA_NXZ`
- size: `473`
- prototype: `bool __fastcall(void **this)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800315c0`
- `0x180081ba0`
- `0x180081ee0`
- `0x180082180`
- `0x1800827a0`
- `0x1800829c0`
- `0x180082f30`
- `0x1800830f0`
- `0x1800831f0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180031790`
- `0x180082dc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031902`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003182c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003182c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800318e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800318e0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800317d4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800317d4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180031923`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180031923`

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
0x180031790  push    rbx
0x180031792  push    rbp
0x180031793  push    rdi
0x180031794  push    r14
0x180031796  sub     rsp, 28h
0x18003179a  mov     rdi, rcx
0x18003179d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317a4  lea     rbp, WPP_GLOBAL_Control
0x1800317ab  lea     r14, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800317b2  cmp     rcx, rbp
0x1800317b5  jz      short loc_1800317D4
0x1800317b7  test    byte ptr [rcx+1Ch], 1
0x1800317bb  jz      short loc_1800317D4
0x1800317bd  cmp     byte ptr [rcx+19h], 6
0x1800317c1  jb      short loc_1800317D4
0x1800317c3  mov     rcx, [rcx+10h]
0x1800317c7  mov     edx, 14h
0x1800317cc  mov     r8, r14
0x1800317cf  call    WPP_SF_
0x1800317d4  call    cs:__imp_CoImpersonateClient
0x1800317da  test    eax, eax
0x1800317dc  jns     short loc_18003180C
0x1800317de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317e5  cmp     rcx, rbp
0x1800317e8  jz      loc_180031959
0x1800317ee  test    byte ptr [rcx+1Ch], 1
0x1800317f2  jz      loc_180031959
0x1800317f8  cmp     byte ptr [rcx+19h], 2
0x1800317fc  jb      loc_180031959
0x180031802  mov     edx, 15h
0x180031807  jmp     loc_18003194A
0x18003180c  mov     [rsp+48h+TokenHandle], 0
0x180031815  call    cs:__imp_GetCurrentThread
0x18003181b  mov     edx, 8; DesiredAccess
0x180031820  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180031825  mov     rcx, rax; ThreadHandle
0x180031828  lea     r8d, [rdx-7]; OpenAsSelf
0x18003182c  call    cs:__imp_OpenThreadToken
0x180031832  test    eax, eax
0x180031834  jz      loc_1800318E8
0x18003183a  mov     rdx, [rsp+48h+TokenHandle]; void *
0x18003183f  lea     r9, [rdi+70h]; void **
0x180031843  mov     r8d, 17h; enum WELL_KNOWN_SID_TYPE
0x180031849  mov     rcx, rdi; this
0x18003184c  call    ?IsTokenPartOfWellKnowSid@CNat@@AEAA_NPEAXW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z; CNat::IsTokenPartOfWellKnowSid(void *,WELL_KNOWN_SID_TYPE,void * &)
0x180031851  mov     bl, al
0x180031853  test    al, al
0x180031855  jz      short loc_180031876
0x180031857  mov     rcx, cs:WPP_GLOBAL_Control
0x18003185e  cmp     rcx, rbp
0x180031861  jz      short loc_1800318DB
0x180031863  test    byte ptr [rcx+1Ch], 1
0x180031867  jz      short loc_1800318DB
0x180031869  cmp     byte ptr [rcx+19h], 4
0x18003186d  jb      short loc_1800318DB
0x18003186f  mov     edx, 16h
0x180031874  jmp     short loc_1800318CF
0x180031876  mov     rdx, [rsp+48h+TokenHandle]; void *
0x18003187b  lea     r9, [rdi+78h]; void **
0x18003187f  mov     r8d, 16h; enum WELL_KNOWN_SID_TYPE
0x180031885  mov     rcx, rdi; this
0x180031888  call    ?IsTokenPartOfWellKnowSid@CNat@@AEAA_NPEAXW4WELL_KNOWN_SID_TYPE@@AEAPEAX@Z; CNat::IsTokenPartOfWellKnowSid(void *,WELL_KNOWN_SID_TYPE,void * &)
0x18003188d  mov     bl, al
0x18003188f  test    al, al
0x180031891  jz      short loc_1800318B2
0x180031893  mov     rcx, cs:WPP_GLOBAL_Control
0x18003189a  cmp     rcx, rbp
0x18003189d  jz      short loc_1800318DB
0x18003189f  test    byte ptr [rcx+1Ch], 1
0x1800318a3  jz      short loc_1800318DB
0x1800318a5  cmp     byte ptr [rcx+19h], 4
0x1800318a9  jb      short loc_1800318DB
0x1800318ab  mov     edx, 17h
0x1800318b0  jmp     short loc_1800318CF
0x1800318b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800318b9  cmp     rcx, rbp
0x1800318bc  jz      short loc_1800318DB
0x1800318be  test    byte ptr [rcx+1Ch], 1
0x1800318c2  jz      short loc_1800318DB
0x1800318c4  cmp     byte ptr [rcx+19h], 4
0x1800318c8  jb      short loc_1800318DB
0x1800318ca  mov     edx, 18h
0x1800318cf  mov     rcx, [rcx+10h]
0x1800318d3  mov     r8, r14
0x1800318d6  call    WPP_SF_
0x1800318db  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800318e0  call    cs:__imp_CloseHandle
0x1800318e6  jmp     short loc_180031923
0x1800318e8  mov     rax, cs:WPP_GLOBAL_Control
0x1800318ef  xor     bl, bl
0x1800318f1  cmp     rax, rbp
0x1800318f4  jz      short loc_180031923
0x1800318f6  test    byte ptr [rax+1Ch], 1
0x1800318fa  jz      short loc_180031923
0x1800318fc  cmp     byte ptr [rax+19h], 2
0x180031900  jb      short loc_180031923
0x180031902  call    cs:__imp_GetLastError
0x180031908  mov     rcx, cs:WPP_GLOBAL_Control
0x18003190f  mov     edx, 19h
0x180031914  mov     r9d, eax
0x180031917  mov     r8, r14
0x18003191a  mov     rcx, [rcx+10h]
0x18003191e  call    WPP_SF_d
0x180031923  call    cs:__imp_CoRevertToSelf
0x180031929  test    eax, eax
0x18003192b  jns     short loc_18003195D
0x18003192d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031934  cmp     rcx, rbp
0x180031937  jz      short loc_180031959
0x180031939  test    byte ptr [rcx+1Ch], 1
0x18003193d  jz      short loc_180031959
0x18003193f  cmp     byte ptr [rcx+19h], 2
0x180031943  jb      short loc_180031959
0x180031945  mov     edx, 1Ah
0x18003194a  mov     rcx, [rcx+10h]
0x18003194e  mov     r9d, eax
0x180031951  mov     r8, r14
0x180031954  call    WPP_SF_d
0x180031959  xor     al, al
0x18003195b  jmp     short loc_18003195F
0x18003195d  mov     al, bl
0x18003195f  add     rsp, 28h
0x180031963  pop     r14
0x180031965  pop     rdi
0x180031966  pop     rbp
0x180031967  pop     rbx
0x180031968  retn
```
