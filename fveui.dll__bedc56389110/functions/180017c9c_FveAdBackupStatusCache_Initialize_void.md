# FveAdBackupStatusCache::Initialize(void)

- ea: `0x180017c9c`
- end: `0x180017de6`
- name: `?Initialize@FveAdBackupStatusCache@@QEAAJXZ`
- size: `330`
- prototype: `__int64 __fastcall(FveAdBackupStatusCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180027a3c`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x18000e354`
- `0x180011e28`
- `0x180017c9c`
- `0x18002d010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180017d76`
- `ADVAPI32!RegGetValueW` at `0x180017d76`

## pseudocode

```c
__int64 __fastcall FveAdBackupStatusCache::Initialize(FveAdBackupStatusCache *this)
{
  unsigned int DomainInfo; // eax
  int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rax
  bool v7; // [rsp+40h] [rbp-48h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-44h] BYREF
  __int128 pvData; // [rsp+48h] [rbp-40h] BYREF

  pcbData = 16;
  pvData = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
  DomainInfo = FveDomain::GetDomainInfo(&v7, (struct _GUID *)((char *)this + 8));
  v3 = DomainInfo;
  if ( !DomainInfo )
    goto LABEL_9;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, DomainInfo);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 >= 0 )
  {
LABEL_9:
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceEncryption\\ADBackup",
      L"DomainGuid",
      8u,
      0,
      &pvData,
      &pcbData);
    v5 = pvData - *((_QWORD *)this + 1);
    if ( (_QWORD)pvData == *((_QWORD *)this + 1) )
      v5 = *((_QWORD *)&pvData + 1) - *((_QWORD *)this + 2);
    if ( v5 )
      (*(void (__fastcall **)(FveAdBackupStatusCache *))(*(_QWORD *)this + 16LL))(this);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 137, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017c9c  push    rbx
0x180017c9e  push    rbp
0x180017c9f  push    rsi
0x180017ca0  push    rdi
0x180017ca1  sub     rsp, 68h
0x180017ca5  mov     rax, cs:__security_cookie
0x180017cac  xor     rax, rsp
0x180017caf  mov     [rsp+88h+var_30], rax
0x180017cb4  xorps   xmm0, xmm0
0x180017cb7  mov     [rsp+88h+var_44], 10h
0x180017cbf  movups  [rsp+88h+var_40], xmm0
0x180017cc4  mov     rsi, rcx
0x180017cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cce  lea     rbp, WPP_GLOBAL_Control
0x180017cd5  cmp     rcx, rbp
0x180017cd8  jz      short loc_180017CF5
0x180017cda  test    byte ptr [rcx+1Ch], 20h
0x180017cde  jz      short loc_180017CF5
0x180017ce0  mov     rcx, [rcx+10h]
0x180017ce4  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180017ceb  mov     edx, 87h
0x180017cf0  call    WPP_SF_
0x180017cf5  lea     rdx, [rsi+8]; struct _GUID *
0x180017cf9  lea     rcx, [rsp+88h+var_48]; bool *
0x180017cfe  call    ?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z; FveDomain::GetDomainInfo(bool *,_GUID *)
0x180017d03  mov     ebx, eax
0x180017d05  test    eax, eax
0x180017d07  jz      short loc_180017D3E
0x180017d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d10  cmp     rcx, rbp
0x180017d13  jz      short loc_180017D3A
0x180017d15  test    byte ptr [rcx+1Ch], 40h
0x180017d19  jz      short loc_180017D3A
0x180017d1b  mov     rcx, [rcx+10h]
0x180017d1f  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180017d26  mov     edx, 88h
0x180017d2b  mov     r9d, eax
0x180017d2e  call    WPP_SF_d
0x180017d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d3a  test    ebx, ebx
0x180017d3c  js      short loc_180017DAB
0x180017d3e  lea     rax, [rsp+88h+var_44]
0x180017d43  mov     r9d, 8; dwFlags
0x180017d49  mov     [rsp+88h+pcbData], rax; pcbData
0x180017d4e  lea     r8, aDomainguid; "DomainGuid"
0x180017d55  lea     rax, [rsp+88h+var_40]
0x180017d5a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180017d61  mov     [rsp+88h+pvData], rax; pvData
0x180017d66  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180017d6d  mov     [rsp+88h+pdwType], 0; pdwType
0x180017d76  call    cs:__imp_RegGetValueW
0x180017d7c  mov     rax, qword ptr [rsp+88h+var_40]
0x180017d81  sub     rax, [rsi+8]
0x180017d85  jnz     short loc_180017D90
0x180017d87  mov     rax, qword ptr [rsp+88h+var_40+8]
0x180017d8c  sub     rax, [rsi+10h]
0x180017d90  test    rax, rax
0x180017d93  jz      short loc_180017DA4
0x180017d95  mov     rax, [rsi]
0x180017d98  mov     rcx, rsi
0x180017d9b  mov     rax, [rax+10h]
0x180017d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dab  cmp     rcx, rbp
0x180017dae  jz      short loc_180017DCE
0x180017db0  test    byte ptr [rcx+1Ch], 20h
0x180017db4  jz      short loc_180017DCE
0x180017db6  mov     rcx, [rcx+10h]
0x180017dba  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180017dc1  mov     edx, 89h
0x180017dc6  mov     r9d, ebx
0x180017dc9  call    WPP_SF_d
0x180017dce  mov     eax, ebx
0x180017dd0  mov     rcx, [rsp+88h+var_30]
0x180017dd5  xor     rcx, rsp; StackCookie
0x180017dd8  call    __security_check_cookie
0x180017ddd  add     rsp, 68h
0x180017de1  pop     rdi
0x180017de2  pop     rsi
0x180017de3  pop     rbp
0x180017de4  pop     rbx
0x180017de5  retn
```
