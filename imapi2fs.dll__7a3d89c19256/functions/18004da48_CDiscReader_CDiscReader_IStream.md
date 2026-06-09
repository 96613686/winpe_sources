# CDiscReader::CDiscReader(IStream *)

- ea: `0x18004da48`
- end: `0x18004dc87`
- name: `??0CDiscReader@@QEAA@PEAUIStream@@@Z`
- size: `575`
- prototype: `CDiscReader *__fastcall(CDiscReader *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x1800072d0`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x1800063b8`
- `0x18000960c`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18004da48`
- `0x18008170e`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004dc1d`
- `ole32!CoTaskMemFree` at `0x18004dc1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CDiscReader *__fastcall CDiscReader::CDiscReader(CDiscReader *this, struct IStream *a2)
{
  int v4; // edi
  CIMAPIException *v5; // rax
  CIMAPIException *v6; // rbx
  void *v7; // rax
  CIMAPIException *pExceptionObject; // [rsp+20h] [rbp-89h] BYREF
  _QWORD v10[2]; // [rsp+28h] [rbp-81h] BYREF
  _BYTE v11[88]; // [rsp+38h] [rbp-71h] BYREF
  LPVOID pv[10]; // [rsp+90h] [rbp-19h] BYREF

  v10[1] = this;
  *(_QWORD *)this = &CDiscReader::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
  memset_0(pv, 0, sizeof(pv));
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = a2;
  (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)this + 11) = 2048;
  *((_DWORD *)this + 10) = 0;
  v4 = (*(__int64 (__fastcall **)(struct IStream *, LPVOID *, __int64))(*(_QWORD *)a2 + 96LL))(a2, pv, 1);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
    }
    v5 = (CIMAPIException *)operator new(0x58u);
    pExceptionObject = v5;
    if ( v5 )
      v5 = CIMAPIException::CIMAPIException(v5, v4);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(v10, v5);
    v6 = (CIMAPIException *)v10[0];
    if ( v10[0] && *(_QWORD *)v10[0] )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v10[0],
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp",
        369);
      pExceptionObject = v6;
      if ( v6 )
        ++*((_DWORD *)v6 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v11, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v11;
  }
  v7 = pv[0];
  if ( pv[0] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
      v7 = pv[0];
    }
    CoTaskMemFree(v7);
    pv[0] = 0;
  }
  *((_DWORD *)this + 10) = (unsigned __int64)pv[2] >> 11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x18004da48  mov     [rsp-8+arg_10], rbx
0x18004da4d  push    rbp
0x18004da4e  push    rdi
0x18004da4f  push    r14
0x18004da51  lea     rbp, [rsp-47h]
0x18004da56  sub     rsp, 0F0h
0x18004da5d  mov     rax, cs:__security_cookie
0x18004da64  xor     rax, rsp
0x18004da67  mov     [rbp+57h+var_20], rax
0x18004da6b  mov     rdi, rdx
0x18004da6e  mov     rbx, rcx
0x18004da71  mov     [rbp+57h+var_D0], rcx
0x18004da75  lea     rax, ??_7CDiscReader@@6B@; const CDiscReader::`vftable'
0x18004da7c  mov     [rcx], rax
0x18004da7f  mov     qword ptr [rcx+10h], 0
0x18004da87  mov     qword ptr [rcx+18h], 0
0x18004da8f  lea     r14, WPP_GLOBAL_Control
0x18004da96  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da9d  cmp     rcx, r14
0x18004daa0  jz      short loc_18004DAC3
0x18004daa2  test    byte ptr [rcx+44h], 8
0x18004daa6  jz      short loc_18004DAC3
0x18004daa8  cmp     byte ptr [rcx+41h], 5
0x18004daac  jb      short loc_18004DAC3
0x18004daae  mov     edx, 1Ah
0x18004dab3  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004daba  mov     rcx, [rcx+38h]
0x18004dabe  call    WPP_SF_
0x18004dac3  xor     edx, edx; Val
0x18004dac5  lea     r8d, [rdx+50h]; Size
0x18004dac9  lea     rcx, [rbp+57h+pv]; void *
0x18004dacd  call    memset_0
0x18004dad2  mov     qword ptr [rbx+20h], 0
0x18004dada  mov     [rbx+8], rdi
0x18004dade  mov     rax, [rdi]
0x18004dae1  mov     rcx, rdi
0x18004dae4  mov     rax, [rax+8]
0x18004dae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daed  mov     dword ptr [rbx+2Ch], 800h
0x18004daf4  mov     dword ptr [rbx+28h], 0
0x18004dafb  mov     rax, [rdi]
0x18004dafe  mov     r8d, 1
0x18004db04  lea     rdx, [rbp+57h+pv]
0x18004db08  mov     rcx, rdi
0x18004db0b  mov     rax, [rax+60h]
0x18004db0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db14  mov     edi, eax
0x18004db16  test    eax, eax
0x18004db18  jns     loc_18004DBE0
0x18004db1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db25  cmp     rcx, r14
0x18004db28  jz      short loc_18004DB4E
0x18004db2a  test    byte ptr [rcx+44h], 4
0x18004db2e  jz      short loc_18004DB4E
0x18004db30  cmp     byte ptr [rcx+41h], 2
0x18004db34  jb      short loc_18004DB4E
0x18004db36  mov     edx, 1Bh
0x18004db3b  mov     r9d, eax
0x18004db3e  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004db45  mov     rcx, [rcx+38h]
0x18004db49  call    WPP_SF_d
0x18004db4e  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004db53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004db58  mov     [rsp+100h+pExceptionObject], rax
0x18004db5d  test    rax, rax
0x18004db60  jz      short loc_18004DB6D
0x18004db62  mov     edx, edi; int
0x18004db64  mov     rcx, rax; this
0x18004db67  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18004db6c  nop
0x18004db6d  mov     rdx, rax
0x18004db70  lea     rcx, [rsp+100h+var_D8]
0x18004db75  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004db7a  nop
0x18004db7b  mov     rbx, [rsp+100h+var_D8]
0x18004db80  test    rbx, rbx
0x18004db83  jz      short loc_18004DBBF
0x18004db85  cmp     qword ptr [rbx], 0
0x18004db89  jz      short loc_18004DBBF
0x18004db8b  mov     r8d, 171h; int
0x18004db91  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x18004db98  mov     rcx, [rbx]; this
0x18004db9b  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004dba0  mov     [rsp+100h+pExceptionObject], rbx
0x18004dba5  test    rbx, rbx
0x18004dba8  jz      short loc_18004DBAD
0x18004dbaa  inc     dword ptr [rbx+8]
0x18004dbad  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18004dbb4  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x18004dbb9  call    _CxxThrowException_0
0x18004dbbf  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004dbc6  lea     rcx, [rbp+57h+var_C8]; this
0x18004dbca  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004dbcf  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18004dbd6  lea     rcx, [rbp+57h+var_C8]; pExceptionObject
0x18004dbda  call    _CxxThrowException_0
0x18004dbe0  mov     rax, [rbp+57h+pv]
0x18004dbe4  test    rax, rax
0x18004dbe7  jz      short loc_18004DC2B
0x18004dbe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dbf0  cmp     rcx, r14
0x18004dbf3  jz      short loc_18004DC1A
0x18004dbf5  test    byte ptr [rcx+44h], 4
0x18004dbf9  jz      short loc_18004DC1A
0x18004dbfb  cmp     byte ptr [rcx+41h], 2
0x18004dbff  jb      short loc_18004DC1A
0x18004dc01  mov     edx, 1Ch
0x18004dc06  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004dc0d  mov     rcx, [rcx+38h]
0x18004dc11  call    WPP_SF_
0x18004dc16  mov     rax, [rbp+57h+pv]
0x18004dc1a  mov     rcx, rax; pv
0x18004dc1d  call    cs:__imp_CoTaskMemFree
0x18004dc23  mov     [rbp+57h+pv], 0
0x18004dc2b  mov     rax, [rbp+57h+var_60]
0x18004dc2f  shr     rax, 0Bh
0x18004dc33  mov     [rbx+28h], eax
0x18004dc36  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc3d  cmp     rcx, r14
0x18004dc40  jz      short loc_18004DC64
0x18004dc42  test    byte ptr [rcx+44h], 8
0x18004dc46  jz      short loc_18004DC64
0x18004dc48  cmp     byte ptr [rcx+41h], 5
0x18004dc4c  jb      short loc_18004DC64
0x18004dc4e  mov     edx, 1Dh
0x18004dc53  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004dc5a  mov     rcx, [rcx+38h]
0x18004dc5e  call    WPP_SF_
0x18004dc63  nop
0x18004dc64  mov     rax, rbx
0x18004dc67  mov     rcx, [rbp+57h+var_20]
0x18004dc6b  xor     rcx, rsp; StackCookie
0x18004dc6e  call    __security_check_cookie
0x18004dc73  mov     rbx, [rsp+100h+arg_10]
0x18004dc7b  add     rsp, 0F0h
0x18004dc82  pop     r14
0x18004dc84  pop     rdi
0x18004dc85  pop     rbp
0x18004dc86  retn
```
