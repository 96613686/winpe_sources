# CWbemClass::Delete(ushort const *)

- ea: `0x180073a70`
- end: `0x180073cec`
- name: `?Delete@CWbemClass@@UEAAJPEBG@Z`
- size: `636`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005720`
- `0x18000d230`
- `0x180037120`
- `0x18004cc70`
- `0x180050490`
- `0x1800733d0`
- `0x180073a70`
- `0x180073e40`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180073a96`
- `wbemcomn!GetMemLogObject` at `0x180073b20`
- `wbemcomn!GetMemLogObject` at `0x180073bd2`
- `wbemcomn!GetMemLogObject` at `0x180073c6c`
- `wbemcomn!GetMemLogObject` at `0x180073a96`
- `wbemcomn!GetMemLogObject` at `0x180073b20`
- `wbemcomn!GetMemLogObject` at `0x180073bd2`
- `wbemcomn!GetMemLogObject` at `0x180073c6c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073aa6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073b30`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073be2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073c7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073aa6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073b30`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073be2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073c7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemClass::Delete(CWbemClass *this, const unsigned __int16 *a2)
{
  CMemoryLog *v4; // rax
  __int64 result; // rax
  struct CPropertyInformation *PropertyInfo; // rsi
  CMemoryLog *v7; // rax
  CClassPart *v8; // rcx
  CMemoryLog *v9; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v11; // rax
  char v12; // [rsp+60h] [rbp+18h] BYREF

  try
  {
    CWbemObject::CLock::CLock((CWbemObject::CLock *)&v12, this, 0);
    if ( a2 )
    {
      PropertyInfo = CClassPart::FindPropertyInfo((CWbemClass *)((char *)this + 520), a2);
      if ( PropertyInfo )
      {
        (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)this + 80LL))(this);
        v8 = (CWbemClass *)((char *)this + 520);
        if ( (*(_DWORD *)PropertyInfo & 0x4000) != 0 )
        {
          CClassPart::CopyParentProperty(v8, (CWbemClass *)((char *)this + 176), a2);
          if ( (*(int (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 744LL))(this, 0) >= 0 )
          {
            CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v12);
            return 262146;
          }
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2147217407);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              112,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749889LL);
          }
        }
        else
        {
          CClassPart::DeleteProperty(v8, a2);
          if ( (*(int (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)this + 744LL))(this, 0) >= 0 )
          {
            CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v12);
            return 0;
          }
          v9 = GetMemLogObject();
          CMemoryLog::Write(v9, -2147217407);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749889LL);
          }
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v12);
        return 2147749889LL;
      }
      if ( (int)CSystemProperties::FindName(a2) < 0 )
      {
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v12);
        result = 2147749890LL;
      }
      else
      {
        v7 = GetMemLogObject();
        CMemoryLog::Write(v7, -2147217360);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            110,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749936LL);
        }
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v12);
        result = 2147749936LL;
      }
    }
    else
    {
      v4 = GetMemLogObject();
      CMemoryLog::Write(v4, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749896LL);
      }
      CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v12);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180073a70  push    rbx
0x180073a72  push    rsi
0x180073a73  push    rdi
0x180073a74  push    r14
0x180073a76  sub     rsp, 28h
0x180073a7a  mov     rdi, rdx
0x180073a7d  mov     rbx, rcx
0x180073a80  xor     r8d, r8d; int
0x180073a83  mov     rdx, rcx; struct CWbemObject *
0x180073a86  lea     rcx, [rsp+48h+arg_10]; this
0x180073a8b  call    ??0CLock@CWbemObject@@QEAA@PEAV1@J@Z; CWbemObject::CLock::CLock(CWbemObject *,long)
0x180073a90  nop
0x180073a91  test    rdi, rdi
0x180073a94  jnz     short loc_180073AF6
0x180073a96  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073a9c  mov     ebx, 80041008h
0x180073aa1  mov     edx, ebx
0x180073aa3  mov     rcx, rax
0x180073aa6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073aac  lea     rax, WPP_GLOBAL_Control
0x180073ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180073aba  cmp     rcx, rax
0x180073abd  jz      short loc_180073AE5
0x180073abf  test    byte ptr [rcx+1Ch], 1
0x180073ac3  jz      short loc_180073AE5
0x180073ac5  cmp     byte ptr [rcx+19h], 2
0x180073ac9  jb      short loc_180073AE5
0x180073acb  lea     edx, [rdi+6Dh]
0x180073ace  mov     r9d, 80041008h
0x180073ad4  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180073adb  mov     rcx, [rcx+10h]
0x180073adf  call    WPP_SF_d
0x180073ae4  nop
0x180073ae5  lea     rcx, [rsp+48h+arg_10]; this
0x180073aea  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073aef  mov     eax, ebx
0x180073af1  jmp     loc_180073CE1
0x180073af6  lea     r14, [rbx+208h]
0x180073afd  mov     rdx, rdi; unsigned __int16 *
0x180073b00  mov     rcx, r14; this
0x180073b03  call    ?FindPropertyInfo@CClassPart@@QEAAPEAVCPropertyInformation@@PEBG@Z; CClassPart::FindPropertyInfo(ushort const *)
0x180073b08  mov     rsi, rax
0x180073b0b  test    rax, rax
0x180073b0e  jnz     loc_180073B94
0x180073b14  mov     rcx, rdi; unsigned __int16 *
0x180073b17  call    ?FindName@CSystemProperties@@SAHPEBG@Z; CSystemProperties::FindName(ushort const *)
0x180073b1c  test    eax, eax
0x180073b1e  js      short loc_180073B80
0x180073b20  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073b26  mov     ebx, 80041030h
0x180073b2b  mov     edx, ebx
0x180073b2d  mov     rcx, rax
0x180073b30  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073b36  lea     rax, WPP_GLOBAL_Control
0x180073b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073b44  cmp     rcx, rax
0x180073b47  jz      short loc_180073B6F
0x180073b49  test    byte ptr [rcx+1Ch], 1
0x180073b4d  jz      short loc_180073B6F
0x180073b4f  cmp     byte ptr [rcx+19h], 2
0x180073b53  jb      short loc_180073B6F
0x180073b55  lea     edx, [rsi+6Eh]
0x180073b58  mov     r9d, 80041030h
0x180073b5e  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180073b65  mov     rcx, [rcx+10h]
0x180073b69  call    WPP_SF_d
0x180073b6e  nop
0x180073b6f  lea     rcx, [rsp+48h+arg_10]; this
0x180073b74  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073b79  mov     eax, ebx
0x180073b7b  jmp     loc_180073CE1
0x180073b80  lea     rcx, [rsp+48h+arg_10]; this
0x180073b85  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073b8a  mov     eax, 80041002h
0x180073b8f  jmp     loc_180073CE1
0x180073b94  mov     rax, [rbx]
0x180073b97  mov     rcx, rbx
0x180073b9a  mov     rax, [rax+50h]
0x180073b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ba3  mov     rcx, r14; this
0x180073ba6  test    dword ptr [rsi], 4000h
0x180073bac  jnz     loc_180073C45
0x180073bb2  mov     rdx, rdi; unsigned __int16 *
0x180073bb5  call    ?DeleteProperty@CClassPart@@QEAAJPEBG@Z; CClassPart::DeleteProperty(ushort const *)
0x180073bba  mov     rax, [rbx]
0x180073bbd  xor     edx, edx
0x180073bbf  mov     rcx, rbx
0x180073bc2  mov     rax, [rax+2E8h]
0x180073bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073bce  test    eax, eax
0x180073bd0  jns     short loc_180073C34
0x180073bd2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073bd8  mov     ebx, 80041001h
0x180073bdd  mov     edx, ebx
0x180073bdf  mov     rcx, rax
0x180073be2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073be8  lea     rax, WPP_GLOBAL_Control
0x180073bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180073bf6  cmp     rcx, rax
0x180073bf9  jz      short loc_180073C23
0x180073bfb  test    byte ptr [rcx+1Ch], 1
0x180073bff  jz      short loc_180073C23
0x180073c01  cmp     byte ptr [rcx+19h], 2
0x180073c05  jb      short loc_180073C23
0x180073c07  mov     edx, 6Fh ; 'o'
0x180073c0c  mov     r9d, 80041001h
0x180073c12  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180073c19  mov     rcx, [rcx+10h]
0x180073c1d  call    WPP_SF_d
0x180073c22  nop
0x180073c23  lea     rcx, [rsp+48h+arg_10]; this
0x180073c28  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073c2d  mov     eax, ebx
0x180073c2f  jmp     loc_180073CE1
0x180073c34  lea     rcx, [rsp+48h+arg_10]; this
0x180073c39  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073c3e  xor     eax, eax
0x180073c40  jmp     loc_180073CE1
0x180073c45  lea     rdx, [rbx+0B0h]; struct CClassPart *
0x180073c4c  mov     r8, rdi; unsigned __int16 *
0x180073c4f  call    ?CopyParentProperty@CClassPart@@QEAAJAEAV1@PEBG@Z; CClassPart::CopyParentProperty(CClassPart &,ushort const *)
0x180073c54  mov     rax, [rbx]
0x180073c57  xor     edx, edx
0x180073c59  mov     rcx, rbx
0x180073c5c  mov     rax, [rax+2E8h]
0x180073c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073c68  test    eax, eax
0x180073c6a  jns     short loc_180073CCB
0x180073c6c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073c72  mov     ebx, 80041001h
0x180073c77  mov     edx, ebx
0x180073c79  mov     rcx, rax
0x180073c7c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073c82  lea     rax, WPP_GLOBAL_Control
0x180073c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c90  cmp     rcx, rax
0x180073c93  jz      short loc_180073CBD
0x180073c95  test    byte ptr [rcx+1Ch], 1
0x180073c99  jz      short loc_180073CBD
0x180073c9b  cmp     byte ptr [rcx+19h], 2
0x180073c9f  jb      short loc_180073CBD
0x180073ca1  mov     edx, 70h ; 'p'
0x180073ca6  mov     r9d, 80041001h
0x180073cac  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180073cb3  mov     rcx, [rcx+10h]
0x180073cb7  call    WPP_SF_d
0x180073cbc  nop
0x180073cbd  lea     rcx, [rsp+48h+arg_10]; this
0x180073cc2  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073cc7  mov     eax, ebx
0x180073cc9  jmp     short loc_180073CE1
0x180073ccb  lea     rcx, [rsp+48h+arg_10]; this
0x180073cd0  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x180073cd5  mov     eax, 40002h
0x180073cda  jmp     short loc_180073CE1
0x180073cdc  mov     eax, 80041006h
0x180073ce1  add     rsp, 28h
0x180073ce5  pop     r14
0x180073ce7  pop     rdi
0x180073ce8  pop     rsi
0x180073ce9  pop     rbx
0x180073cea  retn
```
