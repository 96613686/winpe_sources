# DestroySecurityAttributes

- ea: `0x1400732cc`
- end: `0x140073411`
- name: `DestroySecurityAttributes`
- size: `325`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400723b4`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065dbc`
- `0x1400732cc`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400733a4`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400733a4`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14007333f`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14007333f`
- `KERNEL32!GetLastError` at `0x140073361`
- `KERNEL32!GetLastError` at `0x1400733c6`
- `KERNEL32!GetLastError` at `0x140073361`
- `KERNEL32!GetLastError` at `0x1400733c6`
- `KERNEL32!LocalFree` at `0x1400733f2`
- `KERNEL32!LocalFree` at `0x1400733f2`

## pseudocode

```c
__int64 __fastcall DestroySecurityAttributes(_QWORD *lpMem)
{
  void *v2; // rbx
  DWORD LastError; // eax
  DWORD v4; // eax
  WINBOOL bOwnerDefaulted; // [rsp+40h] [rbp+8h] BYREF
  WINBOOL bDaclPresent; // [rsp+48h] [rbp+10h] BYREF
  PSID pOwner; // [rsp+50h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v2 = (void *)lpMem[1];
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  pOwner = 0;
  pDacl = 0;
  if ( GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted) )
  {
    pMemFree(pOwner);
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
  }
  if ( GetSecurityDescriptorDacl(v2, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    LocalFree(pDacl);
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_db036311db36307996a98c23702218b2_Traceguids, v4);
  }
  pMemFree(lpMem);
  return pMemFree(v2);
}

```

## disassembly

```asm
0x1400732cc  push    rbx
0x1400732ce  push    rdi
0x1400732cf  push    r14
0x1400732d1  sub     rsp, 20h
0x1400732d5  mov     rdi, rcx
0x1400732d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400732df  lea     r14, WPP_GLOBAL_Control
0x1400732e6  cmp     rcx, r14
0x1400732e9  jz      short loc_14007330C
0x1400732eb  test    byte ptr [rcx+1Ch], 2
0x1400732ef  jz      short loc_14007330C
0x1400732f1  cmp     byte ptr [rcx+19h], 5
0x1400732f5  jb      short loc_14007330C
0x1400732f7  mov     rcx, [rcx+10h]
0x1400732fb  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073302  mov     edx, 43h ; 'C'
0x140073307  call    WPP_SF_
0x14007330c  mov     rbx, [rdi+8]
0x140073310  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x140073315  mov     rcx, rbx; pSecurityDescriptor
0x140073318  mov     [rsp+38h+bOwnerDefaulted], 0
0x140073320  lea     rdx, [rsp+38h+pOwner]; pOwner
0x140073325  mov     [rsp+38h+bDaclPresent], 0
0x14007332d  mov     [rsp+38h+pOwner], 0
0x140073336  mov     [rsp+38h+pDacl], 0
0x14007333f  call    cs:__imp_GetSecurityDescriptorOwner
0x140073345  test    eax, eax
0x140073347  jnz     short loc_140073388
0x140073349  mov     rax, cs:WPP_GLOBAL_Control
0x140073350  cmp     rax, r14
0x140073353  jz      short loc_140073392
0x140073355  test    byte ptr [rax+1Ch], 2
0x140073359  jz      short loc_140073392
0x14007335b  cmp     byte ptr [rax+19h], 2
0x14007335f  jb      short loc_140073392
0x140073361  call    cs:__imp_GetLastError
0x140073367  mov     rcx, cs:WPP_GLOBAL_Control
0x14007336e  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073375  mov     edx, 44h ; 'D'
0x14007337a  mov     r9d, eax
0x14007337d  mov     rcx, [rcx+10h]
0x140073381  call    WPP_SF_d
0x140073386  jmp     short loc_140073392
0x140073388  mov     rcx, [rsp+38h+pOwner]; lpMem
0x14007338d  call    pMemFree
0x140073392  lea     r9, [rsp+38h+bOwnerDefaulted]; lpbDaclDefaulted
0x140073397  mov     rcx, rbx; pSecurityDescriptor
0x14007339a  lea     r8, [rsp+38h+pDacl]; pDacl
0x14007339f  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x1400733a4  call    cs:__imp_GetSecurityDescriptorDacl
0x1400733aa  test    eax, eax
0x1400733ac  jnz     short loc_1400733ED
0x1400733ae  mov     rax, cs:WPP_GLOBAL_Control
0x1400733b5  cmp     rax, r14
0x1400733b8  jz      short loc_1400733F8
0x1400733ba  test    byte ptr [rax+1Ch], 2
0x1400733be  jz      short loc_1400733F8
0x1400733c0  cmp     byte ptr [rax+19h], 2
0x1400733c4  jb      short loc_1400733F8
0x1400733c6  call    cs:__imp_GetLastError
0x1400733cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400733d3  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400733da  mov     edx, 45h ; 'E'
0x1400733df  mov     r9d, eax
0x1400733e2  mov     rcx, [rcx+10h]
0x1400733e6  call    WPP_SF_d
0x1400733eb  jmp     short loc_1400733F8
0x1400733ed  mov     rcx, [rsp+38h+pDacl]; hMem
0x1400733f2  call    cs:__imp_LocalFree
0x1400733f8  mov     rcx, rdi; lpMem
0x1400733fb  call    pMemFree
0x140073400  mov     rcx, rbx; lpMem
0x140073403  call    pMemFree
0x140073408  add     rsp, 20h
0x14007340c  pop     r14
0x14007340e  pop     rdi
0x14007340f  pop     rbx
0x140073410  retn
```
