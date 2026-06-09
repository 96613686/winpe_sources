# qmcomm_v1_0_S_QMCreateObjectInternal

- ea: `0x180036d10`
- end: `0x180037008`
- name: `qmcomm_v1_0_S_QMCreateObjectInternal`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800056f0`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18000e558`
- `0x18000f35c`
- `0x180011578`
- `0x18001bba0`
- `0x18002c61c`
- `0x1800363d0`
- `0x180036d10`

## import_xrefs

- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x180036e22`
- `ADVAPI32!IsValidRelativeSecurityDescriptor` at `0x180036e22`
- `KERNEL32!LeaveCriticalSection` at `0x180036f33`
- `KERNEL32!LeaveCriticalSection` at `0x180036ff0`
- `KERNEL32!LeaveCriticalSection` at `0x180036f33`
- `KERNEL32!LeaveCriticalSection` at `0x180036ff0`
- `mqsec!mqrpcIsLocalCall` at `0x180036edb`
- `mqsec!mqrpcIsLocalCall` at `0x180036edb`

## string_xrefs

- `0x180036d70`: `qmcommnd`
- `0x180036df7`: `qmcommnd`
- `0x180036f1c`: `qmcommnd`
- `0x180036fda`: `qmcommnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall qmcomm_v1_0_S_QMCreateObjectInternal(
        void *a1,
        int a2,
        wchar_t *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7,
        struct tagPROPVARIANT *a8)
{
  unsigned __int16 v11; // r8
  unsigned int v12; // ebx
  int v14; // eax
  int v15; // edi
  PVOID *v16; // rcx
  int v17; // r14d
  CQPrivate *v18; // rcx
  int v19; // eax

  if ( a4 && !a5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
    v11 = 1141;
LABEL_7:
    v12 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"qmcommnd", v11);
    return v12;
  }
  v14 = QMpCheckQueueProps(a6, a7, a8, 1u, 1);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids,
        (unsigned int)v14);
    LogMsgHR(v15, (wchar_t *)L"qmcommnd", 0x476u);
    return (unsigned int)v15;
  }
  if ( a5 && !(unsigned int)IsValidRelativeSecurityDescriptor(a5, a4, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
    v11 = 1143;
    goto LABEL_7;
  }
  CCriticalSection::Lock((CCriticalSection *)&qmcmd_cs);
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = a2 - 1;
  if ( v17 )
  {
    if ( v17 != 1 )
    {
      v15 = -1072824319;
      goto LABEL_41;
    }
    if ( CQueueMgr::m_fCreatePublicQueueOnBehalfOfRT )
    {
      if ( mqrpcIsLocalCall(a1) )
      {
        v19 = CQPrivate::QMCreatePrivateQueue(v18, a3, a5, a6, a7, a8, 0);
        goto LABEL_35;
      }
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      WPP_SF_(v16[2], 25, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids);
    v12 = -1072824283;
    LogMsgHR(-1072824283, (wchar_t *)L"qmcommnd", 0x47Fu);
    LeaveCriticalSection(&qmcmd_cs);
    return v12;
  }
  v19 = CQPrivate::QMCreatePrivateQueue((CQPrivate *)v16, a3, a5, a6, a7, a8, 1);
LABEL_35:
  v15 = v19;
  if ( v19 < 0 )
  {
    if ( v19 == -1072824315 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
LABEL_45:
      LogMsgHR(v15, (wchar_t *)L"qmcommnd", 0x480u);
      goto LABEL_46;
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_41:
    if ( v16 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v16 + 28) & 1) != 0 )
        WPP_SF_Sd((TRACEHANDLE)v16[2], v15);
      if ( v15 >= 0 )
        goto LABEL_46;
    }
    goto LABEL_45;
  }
LABEL_46:
  LeaveCriticalSection(&qmcmd_cs);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180036d10  mov     [rsp+arg_0], rcx
0x180036d15  push    rbx
0x180036d16  push    rdi
0x180036d17  push    r12
0x180036d19  push    r13
0x180036d1b  push    r14
0x180036d1d  push    r15
0x180036d1f  sub     rsp, 58h
0x180036d23  mov     ebx, r9d
0x180036d26  mov     r15, r8
0x180036d29  mov     r14d, edx
0x180036d2c  test    r9d, r9d
0x180036d2f  jz      short loc_180036D8A
0x180036d31  cmp     [rsp+88h+arg_20], 0
0x180036d3a  jnz     short loc_180036D8A
0x180036d3c  lea     rbx, WPP_GLOBAL_Control
0x180036d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d4a  cmp     rcx, rbx
0x180036d4d  jz      short loc_180036D6A
0x180036d4f  test    byte ptr [rcx+1Ch], 1
0x180036d53  jz      short loc_180036D6A
0x180036d55  mov     edx, 15h
0x180036d5a  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036d61  mov     rcx, [rcx+10h]
0x180036d65  call    WPP_SF_
0x180036d6a  mov     r8d, 475h; unsigned __int16
0x180036d70  lea     rdx, aQmcommnd; "qmcommnd"
0x180036d77  mov     ebx, 0C00E0006h
0x180036d7c  mov     ecx, ebx; int
0x180036d7e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036d83  mov     eax, ebx
0x180036d85  jmp     loc_180036FF9
0x180036d8a  mov     dword ptr [rsp+88h+var_68], 1; int
0x180036d92  mov     r9d, 1; unsigned int
0x180036d98  mov     r12, [rsp+88h+arg_38]
0x180036da0  mov     r8, r12; struct tagPROPVARIANT *
0x180036da3  mov     r13, [rsp+88h+arg_30]
0x180036dab  mov     rdx, r13; unsigned int *
0x180036dae  mov     ecx, [rsp+88h+arg_28]; unsigned int
0x180036db5  call    ?QMpCheckQueueProps@@YAJKPEAKPEAUtagPROPVARIANT@@KH@Z; QMpCheckQueueProps(ulong,ulong *,tagPROPVARIANT *,ulong,int)
0x180036dba  mov     edi, eax
0x180036dbc  test    eax, eax
0x180036dbe  jns     short loc_180036E0A
0x180036dc0  lea     rbx, WPP_GLOBAL_Control
0x180036dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036dce  cmp     rcx, rbx
0x180036dd1  jz      short loc_180036DF1
0x180036dd3  test    byte ptr [rcx+1Ch], 1
0x180036dd7  jz      short loc_180036DF1
0x180036dd9  mov     edx, 16h
0x180036dde  mov     r9d, eax
0x180036de1  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036de8  mov     rcx, [rcx+10h]
0x180036dec  call    WPP_SF_d
0x180036df1  mov     r8d, 476h; unsigned __int16
0x180036df7  lea     rdx, aQmcommnd; "qmcommnd"
0x180036dfe  mov     ecx, edi; int
0x180036e00  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036e05  jmp     loc_180036FF7
0x180036e0a  cmp     [rsp+88h+arg_20], 0
0x180036e13  jz      short loc_180036E63
0x180036e15  xor     r8d, r8d
0x180036e18  mov     edx, ebx
0x180036e1a  mov     rcx, [rsp+88h+arg_20]
0x180036e22  call    cs:__imp_IsValidRelativeSecurityDescriptor
0x180036e28  test    eax, eax
0x180036e2a  jnz     short loc_180036E63
0x180036e2c  lea     rbx, WPP_GLOBAL_Control
0x180036e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e3a  cmp     rcx, rbx
0x180036e3d  jz      short loc_180036E58
0x180036e3f  test    byte ptr [rcx+1Ch], 1
0x180036e43  jz      short loc_180036E58
0x180036e45  lea     edx, [rax+17h]
0x180036e48  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036e4f  mov     rcx, [rcx+10h]
0x180036e53  call    WPP_SF_
0x180036e58  mov     r8d, 477h
0x180036e5e  jmp     loc_180036D70
0x180036e63  lea     rdi, ?qmcmd_cs@@3VCCriticalSection@@A; CCriticalSection qmcmd_cs
0x180036e6a  mov     [rsp+88h+var_48], rdi
0x180036e6f  mov     rcx, rdi; this
0x180036e72  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180036e77  nop
0x180036e78  lea     rbx, WPP_GLOBAL_Control
0x180036e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e86  cmp     rcx, rbx
0x180036e89  jz      short loc_180036EB0
0x180036e8b  test    byte ptr [rcx+1Ch], 2
0x180036e8f  jz      short loc_180036EB0
0x180036e91  mov     edx, 18h
0x180036e96  mov     r9, r15
0x180036e99  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036ea0  mov     rcx, [rcx+10h]; LoggerHandle
0x180036ea4  call    WPP_SF_S
0x180036ea9  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180036eb0  sub     r14d, 1
0x180036eb4  jz      loc_180036F3F
0x180036eba  cmp     r14d, 1
0x180036ebe  jz      short loc_180036ECA
0x180036ec0  mov     edi, 0C00E0001h
0x180036ec5  jmp     loc_180036FA9
0x180036eca  cmp     cs:?m_fCreatePublicQueueOnBehalfOfRT@CQueueMgr@@0_NA, 0; bool CQueueMgr::m_fCreatePublicQueueOnBehalfOfRT
0x180036ed1  jz      short loc_180036EF6
0x180036ed3  mov     rcx, [rsp+88h+arg_0]
0x180036edb  call    cs:__imp_?mqrpcIsLocalCall@@YAHPEAX@Z; mqrpcIsLocalCall(void *)
0x180036ee1  test    eax, eax
0x180036ee3  jz      short loc_180036EEF
0x180036ee5  mov     [rsp+88h+var_58], 0
0x180036eed  jmp     short loc_180036F47
0x180036eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ef6  cmp     rcx, rbx
0x180036ef9  jz      short loc_180036F16
0x180036efb  test    byte ptr [rcx+1Ch], 1
0x180036eff  jz      short loc_180036F16
0x180036f01  mov     edx, 19h
0x180036f06  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036f0d  mov     rcx, [rcx+10h]
0x180036f11  call    WPP_SF_
0x180036f16  mov     r8d, 47Fh; unsigned __int16
0x180036f1c  lea     rdx, aQmcommnd; "qmcommnd"
0x180036f23  mov     ebx, 0C00E0025h
0x180036f28  mov     ecx, ebx; int
0x180036f2a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036f2f  nop
0x180036f30  mov     rcx, rdi; lpCriticalSection
0x180036f33  call    cs:__imp_LeaveCriticalSection
0x180036f39  nop
0x180036f3a  jmp     loc_180036D83
0x180036f3f  mov     [rsp+88h+var_58], 1; int
0x180036f47  mov     [rsp+88h+var_60], r12; struct tagPROPVARIANT *
0x180036f4c  mov     [rsp+88h+var_68], r13; unsigned int *
0x180036f51  mov     r9d, [rsp+88h+arg_28]; unsigned int
0x180036f59  mov     r8, [rsp+88h+arg_20]; void *
0x180036f61  mov     rdx, r15; wchar_t *
0x180036f64  call    ?QMCreatePrivateQueue@CQPrivate@@QEAAJPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@H@Z; CQPrivate::QMCreatePrivateQueue(wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,int)
0x180036f69  mov     edi, eax
0x180036f6b  test    eax, eax
0x180036f6d  jns     short loc_180036FE9
0x180036f6f  cmp     eax, 0C00E0005h
0x180036f74  jnz     short loc_180036FA2
0x180036f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f7d  cmp     rcx, rbx
0x180036f80  jz      short loc_180036FD4
0x180036f82  test    byte ptr [rcx+1Ch], 2
0x180036f86  jz      short loc_180036FD4
0x180036f88  mov     edx, 1Ah
0x180036f8d  mov     r9, r15
0x180036f90  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036f97  mov     rcx, [rcx+10h]; LoggerHandle
0x180036f9b  call    WPP_SF_S
0x180036fa0  jmp     short loc_180036FD4
0x180036fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fa9  cmp     rcx, rbx
0x180036fac  jz      short loc_180036FD4
0x180036fae  test    byte ptr [rcx+1Ch], 1
0x180036fb2  jz      short loc_180036FD0
0x180036fb4  mov     edx, 1Bh
0x180036fb9  mov     dword ptr [rsp+88h+var_68], edi; char
0x180036fbd  mov     r9, r15
0x180036fc0  lea     r8, WPP_9c98d10e93893ba66448161eb5c1aef0_Traceguids
0x180036fc7  mov     rcx, [rcx+10h]; LoggerHandle
0x180036fcb  call    WPP_SF_Sd
0x180036fd0  test    edi, edi
0x180036fd2  jns     short loc_180036FE9
0x180036fd4  mov     r8d, 480h; unsigned __int16
0x180036fda  lea     rdx, aQmcommnd; "qmcommnd"
0x180036fe1  mov     ecx, edi; int
0x180036fe3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036fe8  nop
0x180036fe9  lea     rcx, ?qmcmd_cs@@3VCCriticalSection@@A; lpCriticalSection
0x180036ff0  call    cs:__imp_LeaveCriticalSection
0x180036ff6  nop
0x180036ff7  mov     eax, edi
0x180036ff9  add     rsp, 58h
0x180036ffd  pop     r15
0x180036fff  pop     r14
0x180037001  pop     r13
0x180037003  pop     r12
0x180037005  pop     rdi
0x180037006  pop     rbx
0x180037007  retn
```
