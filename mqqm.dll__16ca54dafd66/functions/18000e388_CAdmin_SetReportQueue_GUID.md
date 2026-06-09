# CAdmin::SetReportQueue(_GUID *)

- ea: `0x18000e388`
- end: `0x18000e4a5`
- name: `?SetReportQueue@CAdmin@@QEAAJPEAU_GUID@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CAdmin *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009454`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18000e388`
- `0x18002c61c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e494`
- `KERNEL32!LeaveCriticalSection` at `0x18000e494`
- `mqsec!DeleteFalconKeyValue` at `0x18000e41a`
- `mqsec!DeleteFalconKeyValue` at `0x18000e438`
- `mqsec!DeleteFalconKeyValue` at `0x18000e41a`
- `mqsec!DeleteFalconKeyValue` at `0x18000e438`
- `mqsec!SetFalconKeyValue` at `0x18000e44d`
- `mqsec!SetFalconKeyValue` at `0x18000e44d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAdmin::SetReportQueue(CAdmin *this, struct _GUID *a2)
{
  unsigned int v3; // edi
  __int64 v4; // rax
  unsigned int v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF
  _RTL_CRITICAL_SECTION *v9; // [rsp+58h] [rbp+20h]

  v7 = HIDWORD(this);
  v6 = 16;
  v8 = 3;
  v3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids);
  v9 = &g_csReadWriteRequests;
  CCriticalSection::Lock((CCriticalSection *)&g_csReadWriteRequests);
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v4 )
  {
    if ( SetFalconKeyValue(L"ReportQueueGuid", &v8, a2, &v6) )
    {
      v3 = -1072824319;
      LogMsgHR(-1072824319, (wchar_t *)L"admin", 0x32u);
    }
    else
    {
      word_18013A748 = 1;
      *(__int128 *)((char *)&xmmword_18013A74A + 6) = (__int128)*a2;
      Admin = 1;
    }
  }
  else
  {
    word_18013A748 = 0;
    Admin = 0;
    DeleteFalconKeyValue(L"ReportQueueGuid");
    dword_18013A768 = 0;
    CQueueMgr::m_fReportQM = 0;
    DeleteFalconKeyValue(L"PropagateFlag");
  }
  LeaveCriticalSection(&g_csReadWriteRequests);
  return v3;
}

```

## disassembly

```asm
0x18000e388  mov     [rsp+arg_0], rcx
0x18000e38d  push    rbx
0x18000e38e  push    rbp
0x18000e38f  push    rdi
0x18000e390  sub     rsp, 20h
0x18000e394  mov     rbx, rdx
0x18000e397  mov     dword ptr [rsp+38h+arg_0], 10h
0x18000e39f  mov     [rsp+38h+arg_10], 3
0x18000e3a7  xor     edi, edi
0x18000e3a9  lea     rax, WPP_GLOBAL_Control
0x18000e3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3b7  cmp     rcx, rax
0x18000e3ba  jz      short loc_18000E3D5
0x18000e3bc  test    byte ptr [rcx+1Ch], 4
0x18000e3c0  jz      short loc_18000E3D5
0x18000e3c2  lea     edx, [rdi+0Fh]
0x18000e3c5  lea     r8, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids
0x18000e3cc  mov     rcx, [rcx+10h]
0x18000e3d0  call    WPP_SF_
0x18000e3d5  lea     rbp, ?g_csReadWriteRequests@@3VCCriticalSection@@A; CCriticalSection g_csReadWriteRequests
0x18000e3dc  mov     [rsp+38h+arg_18], rbp
0x18000e3e1  mov     rcx, rbp; this
0x18000e3e4  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000e3e9  nop
0x18000e3ea  mov     rax, [rbx]
0x18000e3ed  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000e3f4  jnz     short loc_18000E401
0x18000e3f6  mov     rax, [rbx+8]
0x18000e3fa  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000e401  lea     rcx, aReportqueuegui; "ReportQueueGuid"
0x18000e408  test    rax, rax
0x18000e40b  jnz     short loc_18000E440
0x18000e40d  mov     cs:word_18013A748, ax
0x18000e414  mov     cs:?Admin@@3VCAdmin@@A, eax; CAdmin Admin
0x18000e41a  call    cs:__imp_?DeleteFalconKeyValue@@YAJPEB_W@Z; DeleteFalconKeyValue(wchar_t const *)
0x18000e420  mov     cs:dword_18013A768, 0
0x18000e42a  mov     cs:?m_fReportQM@CQueueMgr@@0_NA, 0; bool CQueueMgr::m_fReportQM
0x18000e431  lea     rcx, aPropagateflag; "PropagateFlag"
0x18000e438  call    cs:__imp_?DeleteFalconKeyValue@@YAJPEB_W@Z; DeleteFalconKeyValue(wchar_t const *)
0x18000e43e  jmp     short loc_18000E491
0x18000e440  lea     r9, [rsp+38h+arg_0]
0x18000e445  mov     r8, rbx
0x18000e448  lea     rdx, [rsp+38h+arg_10]
0x18000e44d  call    cs:__imp_?SetFalconKeyValue@@YAJPEB_WPEAKPEBX1@Z; SetFalconKeyValue(wchar_t const *,ulong *,void const *,ulong *)
0x18000e453  test    eax, eax
0x18000e455  jnz     short loc_18000E477
0x18000e457  mov     cs:word_18013A748, 1
0x18000e460  movups  xmm0, xmmword ptr [rbx]
0x18000e463  movdqu  cs:xmmword_18013A74A+6, xmm0
0x18000e46b  mov     cs:?Admin@@3VCAdmin@@A, 1; CAdmin Admin
0x18000e475  jmp     short loc_18000E491
0x18000e477  mov     edi, 0C00E0001h
0x18000e47c  mov     r8d, 32h ; '2'; unsigned __int16
0x18000e482  lea     rdx, aAdmin; "admin"
0x18000e489  mov     ecx, edi; int
0x18000e48b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000e490  nop
0x18000e491  mov     rcx, rbp; lpCriticalSection
0x18000e494  call    cs:__imp_LeaveCriticalSection
0x18000e49a  nop
0x18000e49b  mov     eax, edi
0x18000e49d  add     rsp, 20h
0x18000e4a1  pop     rdi
0x18000e4a2  pop     rbp
0x18000e4a3  pop     rbx
0x18000e4a4  retn
```
