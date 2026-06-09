# _AlreadyNT4Format

- ea: `0x1800226a4`
- end: `0x1800227de`
- name: `_AlreadyNT4Format`
- size: `314`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021d10`

## callees

- `0x180003426`
- `0x1800049ac`
- `0x18000ca5c`
- `0x1800226a4`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180022750`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180022750`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800226d6`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800226d6`
- `KERNEL32!GetLastError` at `0x1800226e0`
- `KERNEL32!GetLastError` at `0x18002275a`
- `KERNEL32!GetLastError` at `0x1800226e0`
- `KERNEL32!GetLastError` at `0x18002275a`

## pseudocode

```c
_BOOL8 __fastcall AlreadyNT4Format(PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  DWORD v4; // eax
  unsigned int v5; // ebx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-20h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp+18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp+20h] BYREF
  PACL pDacl; // [rsp+68h] [rbp+28h] BYREF

  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 23, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, LastError);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v3);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( !bDaclPresent )
  {
    if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v4 = GetLastError();
      v5 = v4;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 24, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v4);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v5);
      throw (bad_win32_error *)pExceptionObject;
    }
    if ( !bDaclPresent )
      return 1;
  }
  return !pDacl || pDacl->AclRevision == 2;
}

```

## disassembly

```asm
0x1800226a4  mov     [rsp-8+arg_0], rbx
0x1800226a9  push    rbp
0x1800226aa  mov     rbp, rsp
0x1800226ad  sub     rsp, 40h
0x1800226b1  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800226b5  mov     [rbp+bDaclPresent], 0
0x1800226bc  lea     r8, [rbp+pDacl]; pDacl
0x1800226c0  mov     [rbp+bDaclDefaulted], 0
0x1800226c7  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800226cb  mov     [rbp+pDacl], 0
0x1800226d3  mov     rbx, rcx
0x1800226d6  call    cs:__imp_GetSecurityDescriptorDacl
0x1800226dc  test    eax, eax
0x1800226de  jnz     short loc_18002273B
0x1800226e0  call    cs:__imp_GetLastError
0x1800226e6  mov     ebx, eax
0x1800226e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226ef  lea     rdx, WPP_GLOBAL_Control
0x1800226f6  cmp     rcx, rdx
0x1800226f9  jz      short loc_18002271F
0x1800226fb  test    byte ptr [rcx+10Ch], 1
0x180022702  jz      short loc_18002271F
0x180022704  mov     rcx, [rcx+100h]
0x18002270b  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180022712  mov     edx, 17h
0x180022717  mov     r9d, eax
0x18002271a  call    WPP_SF_d
0x18002271f  mov     edx, ebx; unsigned int
0x180022721  lea     rcx, [rbp+pExceptionObject]; this
0x180022725  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18002272a  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180022731  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180022735  call    _CxxThrowException_0
0x18002273b  cmp     [rbp+bDaclPresent], 0
0x18002273f  jnz     short loc_1800227BB
0x180022741  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x180022745  mov     rcx, rbx; pSecurityDescriptor
0x180022748  lea     r8, [rbp+pDacl]; pSacl
0x18002274c  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180022750  call    cs:__imp_GetSecurityDescriptorSacl
0x180022756  test    eax, eax
0x180022758  jnz     short loc_1800227B5
0x18002275a  call    cs:__imp_GetLastError
0x180022760  mov     ebx, eax
0x180022762  mov     rcx, cs:WPP_GLOBAL_Control
0x180022769  lea     rdx, WPP_GLOBAL_Control
0x180022770  cmp     rcx, rdx
0x180022773  jz      short loc_180022799
0x180022775  test    byte ptr [rcx+10Ch], 1
0x18002277c  jz      short loc_180022799
0x18002277e  mov     rcx, [rcx+100h]
0x180022785  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x18002278c  mov     edx, 18h
0x180022791  mov     r9d, eax
0x180022794  call    WPP_SF_d
0x180022799  mov     edx, ebx; unsigned int
0x18002279b  lea     rcx, [rbp+pExceptionObject]; this
0x18002279f  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800227a4  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800227ab  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800227af  call    _CxxThrowException_0
0x1800227b5  cmp     [rbp+bDaclPresent], 0
0x1800227b9  jz      short loc_1800227CE
0x1800227bb  mov     rcx, [rbp+pDacl]
0x1800227bf  test    rcx, rcx
0x1800227c2  jz      short loc_1800227CE
0x1800227c4  xor     eax, eax
0x1800227c6  cmp     byte ptr [rcx], 2
0x1800227c9  setz    al
0x1800227cc  jmp     short loc_1800227D3
0x1800227ce  mov     eax, 1
0x1800227d3  mov     rbx, [rsp+40h+arg_0]
0x1800227d8  add     rsp, 40h
0x1800227dc  pop     rbp
0x1800227dd  retn
```
