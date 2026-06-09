# CFaxSecurity::SetSecurity(ulong,void *)

- ea: `0x180014200`
- end: `0x180014358`
- name: `?SetSecurity@CFaxSecurity@@UEAAJKPEAX@Z`
- size: `344`
- prototype: `int(CFaxSecurity *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000e3b4`
- `0x18000e5b0`
- `0x18000e7b0`
- `0x180014200`

## import_xrefs

- `FXSAPI!FaxSetSecurityEx2` at `0x1800142d3`
- `FXSAPI!FaxSetSecurityEx2` at `0x1800142d3`
- `KERNEL32!LocalFree` at `0x180014332`
- `KERNEL32!LocalFree` at `0x180014332`
- `KERNEL32!GetLastError` at `0x1800142dd`
- `KERNEL32!GetLastError` at `0x1800142dd`

## string_xrefs

- `0x1800142a4`: `SeTakeOwnershipPrivilege`
- `0x1800142b9`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::SetSecurity(CFaxSecurity *this, unsigned int a2, void *a3)
{
  __int64 v3; // rbp
  __int64 v4; // r15
  int SelfRelativeCopy; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  v3 = -1;
  hMem = 0;
  v4 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
  }
  SelfRelativeCopy = MakeSelfRelativeCopy(a3, &hMem);
  if ( SelfRelativeCopy )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 22;
LABEL_19:
      WPP_SF_d(v9[2], v10, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids, (unsigned int)SelfRelativeCopy);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  SelfRelativeCopy = 0;
  if ( (a2 & 1) != 0 )
    v3 = EnablePrivilege(L"SeTakeOwnershipPrivilege");
  if ( (a2 & 8) != 0 )
    v4 = EnablePrivilege(L"SeSecurityPrivilege");
  if ( !(unsigned int)FaxSetSecurityEx2(*((_QWORD *)this + 1), a2, hMem) )
  {
    SelfRelativeCopy = GetLastError();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 23;
      goto LABEL_19;
    }
LABEL_20:
    if ( SelfRelativeCopy > 0 )
      SelfRelativeCopy = (unsigned __int16)SelfRelativeCopy | 0x80070000;
  }
  if ( hMem )
    LocalFree(hMem);
  ReleasePrivilege((HANDLE)v4);
  ReleasePrivilege((HANDLE)v3);
  return (unsigned int)SelfRelativeCopy;
}

```

## disassembly

```asm
0x180014200  push    rbx
0x180014202  push    rbp
0x180014203  push    rsi
0x180014204  push    r13
0x180014206  push    r14
0x180014208  push    r15
0x18001420a  sub     rsp, 28h
0x18001420e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180014212  mov     [rsp+58h+hMem], 0
0x18001421b  mov     r15, rbp
0x18001421e  mov     rbx, r8
0x180014221  mov     esi, edx
0x180014223  mov     r14, rcx
0x180014226  mov     rcx, cs:WPP_GLOBAL_Control
0x18001422d  lea     r13, WPP_GLOBAL_Control
0x180014234  cmp     rcx, r13
0x180014237  jz      short loc_18001425B
0x180014239  test    dword ptr [rcx+1Ch], 100h
0x180014240  jz      short loc_18001425B
0x180014242  cmp     byte ptr [rcx+19h], 5
0x180014246  jb      short loc_18001425B
0x180014248  mov     rcx, [rcx+10h]
0x18001424c  lea     edx, [rbp+16h]
0x18001424f  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180014256  call    WPP_SF_
0x18001425b  lea     rdx, [rsp+58h+hMem]
0x180014260  mov     rcx, rbx; Src
0x180014263  call    MakeSelfRelativeCopy
0x180014268  mov     ebx, eax
0x18001426a  test    eax, eax
0x18001426c  jz      short loc_18001429C
0x18001426e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014275  cmp     rcx, r13
0x180014278  jz      loc_180014318
0x18001427e  test    dword ptr [rcx+1Ch], 100h
0x180014285  jz      loc_180014318
0x18001428b  cmp     byte ptr [rcx+19h], 2
0x18001428f  jb      loc_180014318
0x180014295  mov     edx, 16h
0x18001429a  jmp     short loc_180014305
0x18001429c  xor     ebx, ebx
0x18001429e  test    sil, 1
0x1800142a2  jz      short loc_1800142B3
0x1800142a4  lea     rcx, Name; "SeTakeOwnershipPrivilege"
0x1800142ab  call    EnablePrivilege
0x1800142b0  mov     rbp, rax
0x1800142b3  test    sil, 8
0x1800142b7  jz      short loc_1800142C8
0x1800142b9  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x1800142c0  call    EnablePrivilege
0x1800142c5  mov     r15, rax
0x1800142c8  mov     r8, [rsp+58h+hMem]
0x1800142cd  mov     edx, esi
0x1800142cf  mov     rcx, [r14+8]
0x1800142d3  call    cs:__imp_FaxSetSecurityEx2
0x1800142d9  test    eax, eax
0x1800142db  jnz     short loc_180014325
0x1800142dd  call    cs:__imp_GetLastError
0x1800142e3  mov     ebx, eax
0x1800142e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142ec  cmp     rcx, r13
0x1800142ef  jz      short loc_180014318
0x1800142f1  test    dword ptr [rcx+1Ch], 100h
0x1800142f8  jz      short loc_180014318
0x1800142fa  cmp     byte ptr [rcx+19h], 2
0x1800142fe  jb      short loc_180014318
0x180014300  mov     edx, 17h
0x180014305  mov     rcx, [rcx+10h]
0x180014309  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180014310  mov     r9d, ebx
0x180014313  call    WPP_SF_d
0x180014318  test    ebx, ebx
0x18001431a  jle     short loc_180014325
0x18001431c  movzx   ebx, bx
0x18001431f  or      ebx, 80070000h
0x180014325  cmp     [rsp+58h+hMem], 0
0x18001432b  jz      short loc_180014338
0x18001432d  mov     rcx, [rsp+58h+hMem]; hMem
0x180014332  call    cs:__imp_LocalFree
0x180014338  mov     rcx, r15; hObject
0x18001433b  call    ReleasePrivilege
0x180014340  mov     rcx, rbp; hObject
0x180014343  call    ReleasePrivilege
0x180014348  mov     eax, ebx
0x18001434a  add     rsp, 28h
0x18001434e  pop     r15
0x180014350  pop     r14
0x180014352  pop     r13
0x180014354  pop     rsi
0x180014355  pop     rbp
0x180014356  pop     rbx
0x180014357  retn
```
