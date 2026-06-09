# MakeSelfRelativeCopy

- ea: `0x18000e5b0`
- end: `0x18000e7a7`
- name: `MakeSelfRelativeCopy`
- size: `503`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013fa0`
- `0x180014200`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000e5b0`
- `0x180015cb2`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000e692`
- `KERNEL32!LocalAlloc` at `0x18000e71b`
- `KERNEL32!LocalAlloc` at `0x18000e692`
- `KERNEL32!LocalAlloc` at `0x18000e71b`
- `KERNEL32!LocalFree` at `0x18000e79c`
- `KERNEL32!LocalFree` at `0x18000e79c`
- `KERNEL32!GetLastError` at `0x18000e62e`
- `KERNEL32!GetLastError` at `0x18000e75d`
- `KERNEL32!GetLastError` at `0x18000e62e`
- `KERNEL32!GetLastError` at `0x18000e75d`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18000e624`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18000e624`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18000e682`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18000e682`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000e70d`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000e753`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000e70d`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000e753`

## pseudocode

```c
__int64 __fastcall MakeSelfRelativeCopy(void *Src, _QWORD *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rax
  void *v7; // rdi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  HLOCAL v11; // rax
  DWORD v12; // eax
  DWORD dwRevision; // [rsp+20h] [rbp-30h] BYREF
  _OWORD pSelfRelativeSecurityDescriptor[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v15; // [rsp+48h] [rbp-8h]
  WORD pControl; // [rsp+90h] [rbp+40h] BYREF
  size_t Size; // [rsp+98h] [rbp+48h] BYREF

  pControl = 0;
  memset(pSelfRelativeSecurityDescriptor, 0, sizeof(pSelfRelativeSecurityDescriptor));
  v15 = 0;
  dwRevision = 0;
  LODWORD(Size) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
  }
  if ( !GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
    }
    return v5;
  }
  if ( (pControl & 0x8000u) != 0 )
  {
    LODWORD(Size) = GetSecurityDescriptorLength(Src);
    v6 = LocalAlloc(0x40u, (unsigned int)Size);
    v7 = v6;
    if ( !v6 )
    {
      v5 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v9 = 39;
LABEL_16:
      WPP_SF_(v8[2], v9, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
LABEL_31:
      LocalFree(v7);
      return v5;
    }
    memcpy_0(v6, Src, (unsigned int)Size);
    goto LABEL_18;
  }
  MakeSelfRelativeSD(Src, pSelfRelativeSecurityDescriptor, (LPDWORD)&Size);
  v11 = LocalAlloc(0x40u, (unsigned int)Size);
  v7 = v11;
  if ( !v11 )
  {
    v5 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    v9 = 40;
    goto LABEL_16;
  }
  if ( MakeSelfRelativeSD(Src, v11, (LPDWORD)&Size) )
  {
LABEL_18:
    v5 = 0;
    *a2 = v7;
    return v5;
  }
  v12 = GetLastError();
  v5 = v12;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v12);
  }
  if ( v5 )
    goto LABEL_31;
  return v5;
}

```

## disassembly

```asm
0x18000e5b0  mov     [rsp-28h+arg_0], rbx
0x18000e5b5  push    rbp
0x18000e5b6  push    rsi
0x18000e5b7  push    rdi
0x18000e5b8  push    r12
0x18000e5ba  push    r15
0x18000e5bc  mov     rbp, rsp
0x18000e5bf  sub     rsp, 50h
0x18000e5c3  xor     eax, eax
0x18000e5c5  xorps   xmm0, xmm0
0x18000e5c8  mov     [rbp+pControl], ax
0x18000e5cc  mov     rsi, rdx
0x18000e5cf  movups  [rbp+pSelfRelativeSecurityDescriptor], xmm0
0x18000e5d3  mov     [rbp+var_8], rax
0x18000e5d7  mov     rbx, rcx
0x18000e5da  movups  [rbp+var_18], xmm0
0x18000e5de  mov     [rbp+dwRevision], eax
0x18000e5e1  mov     dword ptr [rbp+Size], eax
0x18000e5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5eb  lea     r15, WPP_GLOBAL_Control
0x18000e5f2  lea     r12, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x18000e5f9  cmp     rcx, r15
0x18000e5fc  jz      short loc_18000E619
0x18000e5fe  test    byte ptr [rcx+1Ch], 2
0x18000e602  jz      short loc_18000E619
0x18000e604  cmp     byte ptr [rcx+19h], 5
0x18000e608  jb      short loc_18000E619
0x18000e60a  mov     rcx, [rcx+10h]
0x18000e60e  lea     edx, [rax+25h]
0x18000e611  mov     r8, r12
0x18000e614  call    WPP_SF_
0x18000e619  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18000e61d  mov     rcx, rbx; pSecurityDescriptor
0x18000e620  lea     rdx, [rbp+pControl]; pControl
0x18000e624  call    cs:__imp_GetSecurityDescriptorControl
0x18000e62a  test    eax, eax
0x18000e62c  jnz     short loc_18000E670
0x18000e62e  call    cs:__imp_GetLastError
0x18000e634  mov     ebx, eax
0x18000e636  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e63d  cmp     rcx, r15
0x18000e640  jz      loc_18000E6EF
0x18000e646  test    byte ptr [rcx+1Ch], 2
0x18000e64a  jz      loc_18000E6EF
0x18000e650  cmp     byte ptr [rcx+19h], 2
0x18000e654  jb      loc_18000E6EF
0x18000e65a  mov     rcx, [rcx+10h]
0x18000e65e  mov     edx, 26h ; '&'
0x18000e663  mov     r9d, eax
0x18000e666  mov     r8, r12
0x18000e669  call    WPP_SF_d
0x18000e66e  jmp     short loc_18000E6EF
0x18000e670  mov     eax, 8000h
0x18000e675  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18000e678  test    [rbp+pControl], ax
0x18000e67c  jz      loc_18000E705
0x18000e682  call    cs:__imp_GetSecurityDescriptorLength
0x18000e688  mov     edx, eax; uBytes
0x18000e68a  mov     ecx, 40h ; '@'; uFlags
0x18000e68f  mov     dword ptr [rbp+Size], edx
0x18000e692  call    cs:__imp_LocalAlloc
0x18000e698  mov     rdi, rax
0x18000e69b  test    rax, rax
0x18000e69e  jnz     short loc_18000E6DB
0x18000e6a0  lea     ebx, [rax+8]
0x18000e6a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6aa  cmp     rcx, r15
0x18000e6ad  jz      loc_18000E799
0x18000e6b3  test    byte ptr [rcx+1Ch], 2
0x18000e6b7  jz      loc_18000E799
0x18000e6bd  cmp     byte ptr [rcx+19h], 2
0x18000e6c1  jb      loc_18000E799
0x18000e6c7  lea     edx, [rax+27h]
0x18000e6ca  mov     rcx, [rcx+10h]
0x18000e6ce  mov     r8, r12
0x18000e6d1  call    WPP_SF_
0x18000e6d6  jmp     loc_18000E799
0x18000e6db  mov     r8d, dword ptr [rbp+Size]; Size
0x18000e6df  mov     rdx, rbx; Src
0x18000e6e2  mov     rcx, rax; void *
0x18000e6e5  call    memcpy_0
0x18000e6ea  xor     ebx, ebx
0x18000e6ec  mov     [rsi], rdi
0x18000e6ef  mov     eax, ebx
0x18000e6f1  mov     rbx, [rsp+50h+arg_0]
0x18000e6f9  add     rsp, 50h
0x18000e6fd  pop     r15
0x18000e6ff  pop     r12
0x18000e701  pop     rdi
0x18000e702  pop     rsi
0x18000e703  pop     rbp
0x18000e704  retn
0x18000e705  lea     r8, [rbp+Size]; lpdwBufferLength
0x18000e709  lea     rdx, [rbp+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000e70d  call    cs:__imp_MakeSelfRelativeSD
0x18000e713  mov     edx, dword ptr [rbp+Size]; uBytes
0x18000e716  mov     ecx, 40h ; '@'; uFlags
0x18000e71b  call    cs:__imp_LocalAlloc
0x18000e721  mov     rdi, rax
0x18000e724  test    rax, rax
0x18000e727  jnz     short loc_18000E749
0x18000e729  lea     ebx, [rax+8]
0x18000e72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e733  cmp     rcx, r15
0x18000e736  jz      short loc_18000E799
0x18000e738  test    byte ptr [rcx+1Ch], 2
0x18000e73c  jz      short loc_18000E799
0x18000e73e  cmp     byte ptr [rcx+19h], 2
0x18000e742  jb      short loc_18000E799
0x18000e744  lea     edx, [rax+28h]
0x18000e747  jmp     short loc_18000E6CA
0x18000e749  lea     r8, [rbp+Size]; lpdwBufferLength
0x18000e74d  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18000e750  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18000e753  call    cs:__imp_MakeSelfRelativeSD
0x18000e759  test    eax, eax
0x18000e75b  jnz     short loc_18000E6EA
0x18000e75d  call    cs:__imp_GetLastError
0x18000e763  mov     ebx, eax
0x18000e765  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e76c  cmp     rcx, r15
0x18000e76f  jz      short loc_18000E791
0x18000e771  test    byte ptr [rcx+1Ch], 2
0x18000e775  jz      short loc_18000E791
0x18000e777  cmp     byte ptr [rcx+19h], 2
0x18000e77b  jb      short loc_18000E791
0x18000e77d  mov     rcx, [rcx+10h]
0x18000e781  mov     edx, 29h ; ')'
0x18000e786  mov     r9d, eax
0x18000e789  mov     r8, r12
0x18000e78c  call    WPP_SF_d
0x18000e791  test    ebx, ebx
0x18000e793  jz      loc_18000E6EF
0x18000e799  mov     rcx, rdi; hMem
0x18000e79c  call    cs:__imp_LocalFree
0x18000e7a2  jmp     loc_18000E6EF
```
