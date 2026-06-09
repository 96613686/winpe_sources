# CEventLogResult::LogResult(IRequest *,IAttributesRaw *,ushort,ulong,ulong const *)

- ea: `0x180025e60`
- end: `0x180025f49`
- name: `?LogResult@CEventLogResult@@AEAAJPEAUIRequest@@PEAUIAttributesRaw@@GKPEBK@Z`
- size: `233`
- prototype: `__int64 __fastcall(CEventLogResult *__hidden this, struct IRequest *, struct IAttributesRaw *, unsigned __int16, unsigned int, const unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f040`
- `0x1800194b8`

## callees

- `0x180025a78`
- `0x180025af4`
- `0x180025e60`
- `0x180025fb8`
- `0x18002b472`
- `0x18002b4a0`

## import_xrefs

- `iassvcs!IASReportSecurityEvent` at `0x180025f0e`
- `iassvcs!IASReportSecurityEvent` at `0x180025f0e`

## pseudocode

```c
__int64 __fastcall CEventLogResult::LogResult(CEventLogResult *this, struct IRequest *a2, struct IAttributesRaw *a3)
{
  __int64 v6; // rbx
  unsigned int v7; // ebx
  _BYTE v9[960]; // [rsp+30h] [rbp-408h] BYREF
  int v10; // [rsp+3F0h] [rbp-48h]
  __int64 *v11; // [rsp+3F8h] [rbp-40h]

  v10 = 0;
  v11 = &qword_18003F900;
  memset_0(v9, 0, sizeof(v9));
  v6 = 0;
  do
  {
    if ( CEventLogResult::formatAttribute(
           this,
           a2,
           a3,
           *((_DWORD *)&CEventLogResult::USR_ACCOUNT_LOCKED_ATTRS + v6),
           (struct XAuditParamWrapper *)v9) < 0 )
      XAuditParamWrapper::AddParameter((XAuditParamWrapper *)v9, APT_String, &qword_18003F900);
    v6 = (unsigned int)(v6 + 1);
  }
  while ( *((_DWORD *)&CEventLogResult::USR_ACCOUNT_LOCKED_ATTRS + v6) );
  v7 = IASReportSecurityEvent(6279, 0, (unsigned __int16)v10, v9);
  XAuditParamWrapper::~XAuditParamWrapper((XAuditParamWrapper *)v9);
  return v7;
}

```

## disassembly

```asm
0x180025e60  mov     r11, rsp
0x180025e63  mov     [r11+20h], rbx
0x180025e67  push    rbp
0x180025e68  push    rsi
0x180025e69  push    rdi
0x180025e6a  push    r14
0x180025e6c  push    r15
0x180025e6e  sub     rsp, 410h
0x180025e75  mov     rax, cs:__security_cookie
0x180025e7c  xor     rax, rsp
0x180025e7f  mov     [rsp+438h+var_38], rax
0x180025e87  mov     rbp, r8
0x180025e8a  mov     dword ptr [r11-48h], 0
0x180025e92  mov     rsi, rdx
0x180025e95  lea     r15, qword_18003F900
0x180025e9c  mov     rdi, rcx
0x180025e9f  mov     [r11-40h], r15
0x180025ea3  xor     edx, edx; Val
0x180025ea5  lea     rcx, [rsp+438h+var_408]; void *
0x180025eaa  mov     r8d, 3C0h; Size
0x180025eb0  call    memset_0
0x180025eb5  xor     ebx, ebx
0x180025eb7  lea     r14, ?USR_ACCOUNT_LOCKED_ATTRS@CEventLogResult@@0QBKB; ulong const near * const CEventLogResult::USR_ACCOUNT_LOCKED_ATTRS
0x180025ebe  mov     r9d, [r14+rbx*4]; unsigned int
0x180025ec2  lea     rax, [rsp+438h+var_408]
0x180025ec7  mov     r8, rbp; struct IAttributesRaw *
0x180025eca  mov     [rsp+438h+var_418], rax; struct XAuditParamWrapper *
0x180025ecf  mov     rdx, rsi; struct IRequest *
0x180025ed2  mov     rcx, rdi; this
0x180025ed5  call    ?formatAttribute@CEventLogResult@@AEAAJPEAUIRequest@@PEAUIAttributesRaw@@KAEAVXAuditParamWrapper@@@Z; CEventLogResult::formatAttribute(IRequest *,IAttributesRaw *,ulong,XAuditParamWrapper &)
0x180025eda  test    eax, eax
0x180025edc  jns     short loc_180025EF0
0x180025ede  mov     r8, r15; void *
0x180025ee1  lea     rcx, [rsp+438h+var_408]; this
0x180025ee6  mov     edx, 2; enum _AUDIT_PARAM_TYPE
0x180025eeb  call    ?AddParameter@XAuditParamWrapper@@QEAAJW4_AUDIT_PARAM_TYPE@@PEAX@Z; XAuditParamWrapper::AddParameter(_AUDIT_PARAM_TYPE,void *)
0x180025ef0  inc     ebx
0x180025ef2  cmp     dword ptr [r14+rbx*4], 0
0x180025ef7  jnz     short loc_180025EBE
0x180025ef9  movzx   r8d, word ptr [rsp+438h+var_48]
0x180025f02  lea     r9, [rsp+438h+var_408]
0x180025f07  mov     ecx, 1887h
0x180025f0c  xor     edx, edx
0x180025f0e  call    cs:__imp_IASReportSecurityEvent
0x180025f14  lea     rcx, [rsp+438h+var_408]; this
0x180025f19  mov     ebx, eax
0x180025f1b  call    ??1XAuditParamWrapper@@QEAA@XZ; XAuditParamWrapper::~XAuditParamWrapper(void)
0x180025f20  mov     eax, ebx
0x180025f22  mov     rcx, [rsp+438h+var_38]
0x180025f2a  xor     rcx, rsp; StackCookie
0x180025f2d  call    __security_check_cookie
0x180025f32  mov     rbx, [rsp+438h+arg_18]
0x180025f3a  add     rsp, 410h
0x180025f41  pop     r15
0x180025f43  pop     r14
0x180025f45  pop     rdi
0x180025f46  pop     rsi
0x180025f47  pop     rbp
0x180025f48  retn
```
