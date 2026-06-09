# CShareEngine::_SetProtectedItemAcl(ushort const *)

- ea: `0x18005c584`
- end: `0x18005c7a6`
- name: `?_SetProtectedItemAcl@CShareEngine@@AEAAJPEBG@Z`
- size: `546`
- prototype: `__int64 __fastcall(CShareEngine *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005b460`

## callees

- `0x1800098dc`
- `0x18000b660`
- `0x18000f840`
- `0x18005be58`
- `0x18005c584`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005c6b7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005c71d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005c6b7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005c71d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c69d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c6fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c69d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c6fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c6e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c74c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c76b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c77f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c6e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c74c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c76b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c77f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c789`
- `SHELL32!__imp_SHGetCorrectOwnerSid` at `0x18005c633`
- `SHELL32!__imp_SHGetCorrectOwnerSid` at `0x18005c633`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005c653`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005c653`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18005c5e8`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18005c5e8`

## pseudocode

```c
__int64 __fastcall CShareEngine::_SetProtectedItemAcl(CShareEngine *this, const unsigned __int16 *a2)
{
  signed int NamedSecurityInfoW; // eax
  signed int Instance; // ebx
  HLOCAL v6; // rax
  void *v7; // rsi
  HLOCAL v8; // rax
  void *v9; // rsi
  int v10; // r9d
  PSID Sid; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR StringSid; // [rsp+48h] [rbp-28h] BYREF
  PSID ppsidOwner; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL v15; // [rsp+58h] [rbp-18h] BYREF
  PACL v16; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbSid; // [rsp+B0h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+48h] BYREF

  v15 = 0;
  v16 = 0;
  ppsidOwner = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 5u, &ppsidOwner, 0, &v16, 0, &v15);
  Instance = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    Instance = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( Instance >= 0 )
  {
    hMem = 0;
    Instance = CAceList::CreateInstance((struct CAceList **)&hMem);
    if ( Instance < 0 )
    {
LABEL_24:
      LocalFree(v15);
      return (unsigned int)Instance;
    }
    StringSid = 0;
    Instance = SHGetCorrectOwnerSid(a2, ppsidOwner, &StringSid);
    if ( Instance < 0 )
    {
LABEL_23:
      LocalFree(hMem);
      goto LABEL_24;
    }
    Sid = 0;
    if ( !ConvertStringSidToSidW(StringSid, &Sid) )
    {
      Instance = ResultFromKnownLastError();
      if ( Instance < 0 )
      {
LABEL_22:
        LocalFree((HLOCAL)StringSid);
        goto LABEL_23;
      }
    }
    Instance = CAceList::SetExplicitAllowAce((CAceList *)hMem, Sid, 0x1F01FFu, 3u);
    cbSid = 68;
    if ( Instance >= 0 )
    {
      v6 = LocalAlloc(0x40u, 0x44u);
      v7 = v6;
      if ( !v6 )
        goto LABEL_15;
      if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid)
        || (Instance = ResultFromKnownLastError(), Instance >= 0) )
      {
        Instance = CAceList::SetExplicitAllowAce((CAceList *)hMem, v7, 0x1F01FFu, 3u);
      }
      LocalFree(v7);
      if ( Instance < 0 )
        goto LABEL_21;
      cbSid = 68;
      v8 = LocalAlloc(0x40u, 0x44u);
      v9 = v8;
      if ( v8 )
      {
        if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v8, &cbSid)
          || (Instance = ResultFromKnownLastError(), Instance >= 0) )
        {
          Instance = CAceList::SetExplicitAllowAce((CAceList *)hMem, v9, 0x1F01FFu, 3u);
        }
        LocalFree(v9);
        if ( Instance >= 0 )
          Instance = CShareEngine::_SetAcl(this, a2, (struct CAceList *)hMem, v10);
      }
      else
      {
LABEL_15:
        Instance = -2147024882;
      }
    }
LABEL_21:
    LocalFree(Sid);
    goto LABEL_22;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005c584  mov     r11, rsp
0x18005c587  mov     [r11+8], rbx
0x18005c58b  push    rbp
0x18005c58c  push    rsi
0x18005c58d  push    r13
0x18005c58f  push    r14
0x18005c591  push    r15
0x18005c593  mov     rbp, rsp
0x18005c596  sub     rsp, 70h
0x18005c59a  mov     r14, rdx
0x18005c59d  mov     [rbp+var_18], 0
0x18005c5a5  mov     edx, 1; ObjectType
0x18005c5aa  mov     [rbp+var_10], 0
0x18005c5b2  lea     rax, [rbp+var_18]
0x18005c5b6  mov     [rbp+ppsidOwner], 0
0x18005c5be  mov     [r11-60h], rax
0x18005c5c2  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x18005c5c6  mov     qword ptr [r11-68h], 0
0x18005c5ce  lea     rax, [rbp+var_10]
0x18005c5d2  mov     r15, rcx
0x18005c5d5  mov     [r11-70h], rax
0x18005c5d9  lea     r8d, [rdx+4]; SecurityInfo
0x18005c5dd  mov     qword ptr [r11-78h], 0
0x18005c5e5  mov     rcx, r14; pObjectName
0x18005c5e8  call    cs:__imp_GetNamedSecurityInfoW
0x18005c5ee  mov     ebx, eax
0x18005c5f0  test    eax, eax
0x18005c5f2  jle     short loc_18005C5FD
0x18005c5f4  movzx   ebx, ax
0x18005c5f7  or      ebx, 80070000h
0x18005c5fd  test    ebx, ebx
0x18005c5ff  js      loc_18005C78F
0x18005c605  lea     rcx, [rbp+hMem]; struct CAceList **
0x18005c609  mov     [rbp+hMem], 0
0x18005c611  call    ?CreateInstance@CAceList@@SAJPEAPEAV1@@Z; CAceList::CreateInstance(CAceList * *)
0x18005c616  mov     ebx, eax
0x18005c618  test    eax, eax
0x18005c61a  js      loc_18005C785
0x18005c620  mov     rdx, [rbp+ppsidOwner]
0x18005c624  lea     r8, [rbp+StringSid]
0x18005c628  mov     rcx, r14
0x18005c62b  mov     [rbp+StringSid], 0
0x18005c633  call    cs:__imp_SHGetCorrectOwnerSid
0x18005c639  mov     ebx, eax
0x18005c63b  test    eax, eax
0x18005c63d  js      loc_18005C77B
0x18005c643  mov     rcx, [rbp+StringSid]; StringSid
0x18005c647  lea     rdx, [rbp+Sid]; Sid
0x18005c64b  mov     [rbp+Sid], 0
0x18005c653  call    cs:__imp_ConvertStringSidToSidW
0x18005c659  test    eax, eax
0x18005c65b  jnz     short loc_18005C66C
0x18005c65d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005c662  mov     ebx, eax
0x18005c664  test    eax, eax
0x18005c666  js      loc_18005C771
0x18005c66c  mov     rdx, [rbp+Sid]; void *
0x18005c670  mov     r9b, 3; unsigned __int8
0x18005c673  mov     rcx, [rbp+hMem]; this
0x18005c677  mov     r8d, 1F01FFh; unsigned int
0x18005c67d  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x18005c682  mov     r13d, 44h ; 'D'
0x18005c688  mov     ebx, eax
0x18005c68a  mov     [rbp+cbSid], r13d
0x18005c68e  test    eax, eax
0x18005c690  js      loc_18005C767
0x18005c696  mov     edx, r13d; uBytes
0x18005c699  lea     ecx, [r13-4]; uFlags
0x18005c69d  call    cs:__imp_LocalAlloc
0x18005c6a3  mov     rsi, rax
0x18005c6a6  test    rax, rax
0x18005c6a9  jz      short loc_18005C70A
0x18005c6ab  xor     edx, edx; DomainSid
0x18005c6ad  lea     r9, [rbp+cbSid]; cbSid
0x18005c6b1  mov     r8, rax; pSid
0x18005c6b4  lea     ecx, [rdx+16h]; WellKnownSidType
0x18005c6b7  call    cs:__imp_CreateWellKnownSid
0x18005c6bd  test    eax, eax
0x18005c6bf  jnz     short loc_18005C6CC
0x18005c6c1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005c6c6  mov     ebx, eax
0x18005c6c8  test    eax, eax
0x18005c6ca  js      short loc_18005C6E3
0x18005c6cc  mov     rcx, [rbp+hMem]; this
0x18005c6d0  mov     r9b, 3; unsigned __int8
0x18005c6d3  mov     r8d, 1F01FFh; unsigned int
0x18005c6d9  mov     rdx, rsi; void *
0x18005c6dc  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x18005c6e1  mov     ebx, eax
0x18005c6e3  mov     rcx, rsi; hMem
0x18005c6e6  call    cs:__imp_LocalFree
0x18005c6ec  test    ebx, ebx
0x18005c6ee  js      short loc_18005C767
0x18005c6f0  mov     rdx, r13; uBytes
0x18005c6f3  mov     [rbp+cbSid], r13d
0x18005c6f7  mov     ecx, 40h ; '@'; uFlags
0x18005c6fc  call    cs:__imp_LocalAlloc
0x18005c702  mov     rsi, rax
0x18005c705  test    rax, rax
0x18005c708  jnz     short loc_18005C711
0x18005c70a  mov     ebx, 8007000Eh
0x18005c70f  jmp     short loc_18005C767
0x18005c711  xor     edx, edx; DomainSid
0x18005c713  lea     r9, [rbp+cbSid]; cbSid
0x18005c717  mov     r8, rsi; pSid
0x18005c71a  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18005c71d  call    cs:__imp_CreateWellKnownSid
0x18005c723  test    eax, eax
0x18005c725  jnz     short loc_18005C732
0x18005c727  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005c72c  mov     ebx, eax
0x18005c72e  test    eax, eax
0x18005c730  js      short loc_18005C749
0x18005c732  mov     rcx, [rbp+hMem]; this
0x18005c736  mov     r9b, 3; unsigned __int8
0x18005c739  mov     r8d, 1F01FFh; unsigned int
0x18005c73f  mov     rdx, rsi; void *
0x18005c742  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x18005c747  mov     ebx, eax
0x18005c749  mov     rcx, rsi; hMem
0x18005c74c  call    cs:__imp_LocalFree
0x18005c752  test    ebx, ebx
0x18005c754  js      short loc_18005C767
0x18005c756  mov     r8, [rbp+hMem]; struct CAceList *
0x18005c75a  mov     rdx, r14; unsigned __int16 *
0x18005c75d  mov     rcx, r15; this
0x18005c760  call    ?_SetAcl@CShareEngine@@AEAAJPEBGPEAVCAceList@@H@Z; CShareEngine::_SetAcl(ushort const *,CAceList *,int)
0x18005c765  mov     ebx, eax
0x18005c767  mov     rcx, [rbp+Sid]; hMem
0x18005c76b  call    cs:__imp_LocalFree
0x18005c771  mov     rcx, [rbp+StringSid]; hMem
0x18005c775  call    cs:__imp_LocalFree
0x18005c77b  mov     rcx, [rbp+hMem]; hMem
0x18005c77f  call    cs:__imp_LocalFree
0x18005c785  mov     rcx, [rbp+var_18]; hMem
0x18005c789  call    cs:__imp_LocalFree
0x18005c78f  mov     eax, ebx
0x18005c791  mov     rbx, [rsp+70h+arg_0]
0x18005c799  add     rsp, 70h
0x18005c79d  pop     r15
0x18005c79f  pop     r14
0x18005c7a1  pop     r13
0x18005c7a3  pop     rsi
0x18005c7a4  pop     rbp
0x18005c7a5  retn
```
