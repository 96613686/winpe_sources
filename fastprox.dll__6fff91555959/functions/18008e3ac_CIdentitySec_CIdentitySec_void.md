# CIdentitySec::CIdentitySec(void)

- ea: `0x18008e3ac`
- end: `0x18008e51e`
- name: `??0CIdentitySec@@QEAA@XZ`
- size: `370`
- prototype: `CIdentitySec *__fastcall(CIdentitySec *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008a72c`

## callees

- `0x180035b08`
- `0x18006fa4c`
- `0x18008e3ac`
- `0x18008f600`
- `0x1800919b0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18008e426`
- `wbemcomn!GetMemLogObject` at `0x18008e492`
- `wbemcomn!GetMemLogObject` at `0x18008e426`
- `wbemcomn!GetMemLogObject` at `0x18008e492`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18008e4f6`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18008e4f6`
- `wbemcomn!??0CNtSid@@QEAA@XZ` at `0x18008e3d3`
- `wbemcomn!??0CNtSid@@QEAA@XZ` at `0x18008e3e1`
- `wbemcomn!??0CNtSid@@QEAA@XZ` at `0x18008e3d3`
- `wbemcomn!??0CNtSid@@QEAA@XZ` at `0x18008e3e1`
- `wbemcomn!??4CNtSid@@QEAAAEAV0@AEBV0@@Z` at `0x18008e413`
- `wbemcomn!??4CNtSid@@QEAAAEAV0@AEBV0@@Z` at `0x18008e413`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18008e405`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18008e405`
- `wbemcomn!?IsValid@CNtSid@@QEAAHXZ` at `0x18008e41c`
- `wbemcomn!?IsValid@CNtSid@@QEAAHXZ` at `0x18008e41c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008e434`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008e4a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008e434`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CIdentitySec *__fastcall CIdentitySec::CIdentitySec(CIdentitySec *this)
{
  CIdentitySec *v2; // rcx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v4; // rax
  char pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v7[16]; // [rsp+28h] [rbp-38h] BYREF
  CIdentitySec *v8; // [rsp+38h] [rbp-28h]
  _DWORD v9[4]; // [rsp+40h] [rbp-20h] BYREF

  v8 = this;
  CNtSid::CNtSid(this);
  CNtSid::CNtSid((CIdentitySec *)((char *)this + 16));
  v9[0] = 257;
  v9[1] = 83886080;
  v9[2] = 18;
  CNtSid::CNtSid((CNtSid *)v7, v9);
  CNtSid::operator=((char *)this + 16, v7);
  if ( !CNtSid::IsValid((CIdentitySec *)((char *)this + 16)) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_a3414c62bfc43c14b650084b64f85981_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  if ( CIdentitySec::RetrieveSidFromCall(v2, this) < 0 )
  {
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_a3414c62bfc43c14b650084b64f85981_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  CNtSid::~CNtSid((CNtSid *)v7);
  return this;
}

```

## disassembly

```asm
0x18008e3ac  mov     [rsp-8+arg_8], rbx
0x18008e3b1  mov     [rsp-8+arg_10], rdi
0x18008e3b6  push    rbp
0x18008e3b7  mov     rbp, rsp
0x18008e3ba  sub     rsp, 60h
0x18008e3be  mov     rax, cs:__security_cookie
0x18008e3c5  xor     rax, rsp
0x18008e3c8  mov     [rbp+var_10], rax
0x18008e3cc  mov     rdi, rcx
0x18008e3cf  mov     [rbp+var_28], rcx
0x18008e3d3  call    cs:__imp_??0CNtSid@@QEAA@XZ; CNtSid::CNtSid(void)
0x18008e3d9  nop
0x18008e3da  lea     rbx, [rdi+10h]
0x18008e3de  mov     rcx, rbx
0x18008e3e1  call    cs:__imp_??0CNtSid@@QEAA@XZ; CNtSid::CNtSid(void)
0x18008e3e7  nop
0x18008e3e8  mov     [rbp+var_20], 101h
0x18008e3ef  mov     [rbp+var_1C], 5000000h
0x18008e3f6  mov     [rbp+var_18], 12h
0x18008e3fd  lea     rdx, [rbp+var_20]
0x18008e401  lea     rcx, [rbp+var_38]
0x18008e405  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18008e40b  nop
0x18008e40c  lea     rdx, [rbp+var_38]
0x18008e410  mov     rcx, rbx
0x18008e413  call    cs:__imp_??4CNtSid@@QEAAAEAV0@AEBV0@@Z; CNtSid::operator=(CNtSid const &)
0x18008e419  mov     rcx, rbx
0x18008e41c  call    cs:__imp_?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18008e422  test    eax, eax
0x18008e424  jnz     short loc_18008E486
0x18008e426  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008e42c  mov     edx, 0FFFFFFFEh
0x18008e431  mov     rcx, rax
0x18008e434  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008e43a  lea     rax, WPP_GLOBAL_Control
0x18008e441  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e448  cmp     rcx, rax
0x18008e44b  jz      short loc_18008E475
0x18008e44d  test    byte ptr [rcx+1Ch], 1
0x18008e451  jz      short loc_18008E475
0x18008e453  cmp     byte ptr [rcx+19h], 2
0x18008e457  jb      short loc_18008E475
0x18008e459  mov     edx, 1Fh
0x18008e45e  lea     r9, aCxException; "CX_Exception()"
0x18008e465  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008e46c  mov     rcx, [rcx+10h]
0x18008e470  call    WPP_SF_s
0x18008e475  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18008e47c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18008e480  call    _CxxThrowException_0
0x18008e486  mov     rdx, rdi; struct CNtSid *
0x18008e489  call    ?RetrieveSidFromCall@CIdentitySec@@AEAAJAEAVCNtSid@@@Z; CIdentitySec::RetrieveSidFromCall(CNtSid &)
0x18008e48e  test    eax, eax
0x18008e490  jns     short loc_18008E4F2
0x18008e492  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008e498  mov     edx, 0FFFFFFFEh
0x18008e49d  mov     rcx, rax
0x18008e4a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008e4a6  lea     rax, WPP_GLOBAL_Control
0x18008e4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e4b4  cmp     rcx, rax
0x18008e4b7  jz      short loc_18008E4E1
0x18008e4b9  test    byte ptr [rcx+1Ch], 1
0x18008e4bd  jz      short loc_18008E4E1
0x18008e4bf  cmp     byte ptr [rcx+19h], 2
0x18008e4c3  jb      short loc_18008E4E1
0x18008e4c5  mov     edx, 20h ; ' '
0x18008e4ca  lea     r9, aCxException; "CX_Exception()"
0x18008e4d1  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008e4d8  mov     rcx, [rcx+10h]
0x18008e4dc  call    WPP_SF_s
0x18008e4e1  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18008e4e8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18008e4ec  call    _CxxThrowException_0
0x18008e4f2  lea     rcx, [rbp+var_38]
0x18008e4f6  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18008e4fc  nop
0x18008e4fd  mov     rax, rdi
0x18008e500  mov     rcx, [rbp+var_10]
0x18008e504  xor     rcx, rsp; StackCookie
0x18008e507  call    __security_check_cookie
0x18008e50c  lea     r11, [rsp+60h+var_s0]
0x18008e511  mov     rbx, [r11+18h]
0x18008e515  mov     rdi, [r11+20h]
0x18008e519  mov     rsp, r11
0x18008e51c  pop     rbp
0x18008e51d  retn
```
