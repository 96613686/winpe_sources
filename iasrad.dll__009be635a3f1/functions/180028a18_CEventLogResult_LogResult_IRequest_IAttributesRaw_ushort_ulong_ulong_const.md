# CEventLogResult::LogResult(IRequest *,IAttributesRaw *,ushort,ulong,ulong const *)

- ea: `0x180028a18`
- end: `0x180028b06`
- name: `?LogResult@CEventLogResult@@AEAAJPEAUIRequest@@PEAUIAttributesRaw@@GKPEBK@Z`
- size: `238`
- prototype: `__int64 __usercall@<rax>(CEventLogResult *__hidden this@<rcx>, struct IRequest *@<rdx>, struct IAttributesRaw *@<r8>, unsigned __int16@<r9w>, unsigned int, const unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800179a4`

## callees

- `0x180028538`
- `0x1800285b4`
- `0x180028a18`
- `0x180028b74`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `iassvcs!IASReportSecurityEvent` at `0x180028ad0`
- `iassvcs!IASReportSecurityEvent` at `0x180028ad0`

## pseudocode

```c
__int64 __fastcall CEventLogResult::LogResult(
        CEventLogResult *this,
        struct IRequest *a2,
        struct IAttributesRaw *a3,
        unsigned __int16 a4,
        unsigned int a5,
        const unsigned int *a6)
{
  __int64 v10; // rbx
  unsigned int v11; // ebx
  _BYTE v13[960]; // [rsp+30h] [rbp-418h] BYREF
  int v14; // [rsp+3F0h] [rbp-58h]
  int *v15; // [rsp+3F8h] [rbp-50h]

  v15 = &dword_18004156C;
  v14 = 0;
  memset_0(v13, 0, sizeof(v13));
  v10 = 0;
  if ( *a6 )
  {
    do
    {
      if ( CEventLogResult::formatAttribute(this, a2, a3, a6[v10], (struct XAuditParamWrapper *)v13) < 0 )
        XAuditParamWrapper::AddParameter((XAuditParamWrapper *)v13, APT_String, &dword_18004156C);
      v10 = (unsigned int)(v10 + 1);
    }
    while ( a6[v10] );
  }
  v11 = IASReportSecurityEvent(a4, a5, (unsigned __int16)v14, v13);
  XAuditParamWrapper::~XAuditParamWrapper((XAuditParamWrapper *)v13);
  return v11;
}

```

## disassembly

```asm
0x180028a18  mov     r11, rsp
0x180028a1b  push    rbx
0x180028a1c  push    rbp
0x180028a1d  push    rsi
0x180028a1e  push    rdi
0x180028a1f  push    r13
0x180028a21  push    r14
0x180028a23  push    r15
0x180028a25  sub     rsp, 410h
0x180028a2c  mov     rax, cs:__security_cookie
0x180028a33  xor     rax, rsp
0x180028a36  mov     [rsp+448h+var_48], rax
0x180028a3e  mov     rdi, [rsp+448h+arg_28]
0x180028a46  lea     r13, dword_18004156C
0x180028a4d  mov     r15, r8
0x180028a50  mov     [r11-50h], r13
0x180028a54  mov     r14, rdx
0x180028a57  mov     dword ptr [r11-58h], 0
0x180028a5f  mov     rbp, rcx
0x180028a62  xor     edx, edx; Val
0x180028a64  mov     r8d, 3C0h; Size
0x180028a6a  lea     rcx, [rsp+448h+var_418]; void *
0x180028a6f  movzx   esi, r9w
0x180028a73  call    memset_0
0x180028a78  xor     ebx, ebx
0x180028a7a  cmp     [rdi], ebx
0x180028a7c  jz      short loc_180028AB8
0x180028a7e  mov     r9d, [rdi+rbx*4]; unsigned int
0x180028a82  lea     rax, [rsp+448h+var_418]
0x180028a87  mov     r8, r15; struct IAttributesRaw *
0x180028a8a  mov     [rsp+448h+var_428], rax; struct XAuditParamWrapper *
0x180028a8f  mov     rdx, r14; struct IRequest *
0x180028a92  mov     rcx, rbp; this
0x180028a95  call    ?formatAttribute@CEventLogResult@@AEAAJPEAUIRequest@@PEAUIAttributesRaw@@KAEAVXAuditParamWrapper@@@Z; CEventLogResult::formatAttribute(IRequest *,IAttributesRaw *,ulong,XAuditParamWrapper &)
0x180028a9a  test    eax, eax
0x180028a9c  jns     short loc_180028AB0
0x180028a9e  mov     r8, r13; void *
0x180028aa1  lea     rcx, [rsp+448h+var_418]; this
0x180028aa6  mov     edx, 2; enum _AUDIT_PARAM_TYPE
0x180028aab  call    ?AddParameter@XAuditParamWrapper@@QEAAJW4_AUDIT_PARAM_TYPE@@PEAX@Z; XAuditParamWrapper::AddParameter(_AUDIT_PARAM_TYPE,void *)
0x180028ab0  inc     ebx
0x180028ab2  cmp     dword ptr [rdi+rbx*4], 0
0x180028ab6  jnz     short loc_180028A7E
0x180028ab8  movzx   r8d, word ptr [rsp+448h+var_58]
0x180028ac1  lea     r9, [rsp+448h+var_418]
0x180028ac6  mov     edx, [rsp+448h+arg_20]
0x180028acd  movzx   ecx, si
0x180028ad0  call    cs:__imp_IASReportSecurityEvent
0x180028ad6  lea     rcx, [rsp+448h+var_418]; this
0x180028adb  mov     ebx, eax
0x180028add  call    ??1XAuditParamWrapper@@QEAA@XZ; XAuditParamWrapper::~XAuditParamWrapper(void)
0x180028ae2  mov     eax, ebx
0x180028ae4  mov     rcx, [rsp+448h+var_48]
0x180028aec  xor     rcx, rsp; StackCookie
0x180028aef  call    __security_check_cookie
0x180028af4  add     rsp, 410h
0x180028afb  pop     r15
0x180028afd  pop     r14
0x180028aff  pop     r13
0x180028b01  pop     rdi
0x180028b02  pop     rsi
0x180028b03  pop     rbp
0x180028b04  pop     rbx
0x180028b05  retn
```
