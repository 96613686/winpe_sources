# CSecurityHeader::SectionIsValid(char *)

- ea: `0x18007fde8`
- end: `0x1800800bb`
- name: `?SectionIsValid@CSecurityHeader@@QEBAXPEAD@Z`
- size: `723`
- prototype: `void __fastcall(CSecurityHeader *__hidden this, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003cd68`

## callees

- `0x180004d91`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18002c4dc`
- `0x180047908`
- `0x180049df0`
- `0x18007eb54`
- `0x18007fde8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x18007fe62`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007fec9`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007ff35`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007ffc6`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180080031`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180080099`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007fe62`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007fec9`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007ff35`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18007ffc6`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180080031`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180080099`
- `ADVAPI32!IsValidSid` at `0x18008004c`
- `ADVAPI32!IsValidSid` at `0x18008004c`

## pseudocode

```c
void __fastcall CSecurityHeader::SectionIsValid(CSecurityHeader *this, char *a2)
{
  char *NextSectionSafe; // rdi
  const unsigned __int8 *Section; // rax
  __int16 v6; // ax
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-20h] BYREF

  if ( !*(_DWORD *)((char *)this + 2) && !*((_WORD *)this + 3) && !*((_DWORD *)this + 2) && !*((_DWORD *)this + 3) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_219177b1f08534930d9088c12436ecaa_Traceguids);
    LogIllegalPoint((wchar_t *)L"verifypacket", 0x5ECu);
    exception::exception((exception *)pExceptionObject);
    throw (exception *)pExceptionObject;
  }
  NextSectionSafe = CSecurityHeader::GetNextSectionSafe(this, a2);
  if ( NextSectionSafe > a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_219177b1f08534930d9088c12436ecaa_Traceguids);
    LogIllegalPoint((wchar_t *)L"verifypacket", 0x5EDu);
    exception::exception((exception *)pExceptionObject);
    throw (exception *)pExceptionObject;
  }
  if ( *((_WORD *)this + 3) && (*(_BYTE *)this & 0x40) == 0 && *((_DWORD *)this + 3) < 6u )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_219177b1f08534930d9088c12436ecaa_Traceguids);
    LogIllegalPoint((wchar_t *)L"verifypacket", 0x5EEu);
    exception::exception((exception *)pExceptionObject);
    throw (exception *)pExceptionObject;
  }
  Section = CSecurityHeader::GetSectionExPtr(this);
  if ( Section )
    pGetSubSectionEx(0, Section, NextSectionSafe);
  v6 = *(_WORD *)this & 0xF;
  if ( v6 == 2 )
  {
    if ( *((_WORD *)this + 1) != 16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          29,
          WPP_219177b1f08534930d9088c12436ecaa_Traceguids,
          *((unsigned __int16 *)this + 1));
      LogIllegalPoint((wchar_t *)L"verifypacket", 0x5EFu);
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
  }
  else if ( v6 == 1 )
  {
    if ( !*((_WORD *)this + 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_219177b1f08534930d9088c12436ecaa_Traceguids);
      LogIllegalPoint((wchar_t *)L"verifypacket", 0x5F0u);
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
    if ( !IsValidSid((char *)this + 16) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_219177b1f08534930d9088c12436ecaa_Traceguids);
      LogIllegalPoint((wchar_t *)L"verifypacket", 0x5F1u);
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18007fde8  push    rbp
0x18007fdea  push    rbx
0x18007fdeb  push    rsi
0x18007fdec  push    rdi
0x18007fded  push    r14
0x18007fdef  mov     rbp, rsp
0x18007fdf2  sub     rsp, 40h
0x18007fdf6  xor     r14d, r14d
0x18007fdf9  mov     rsi, rdx
0x18007fdfc  mov     rbx, rcx
0x18007fdff  cmp     r14w, [rcx+2]
0x18007fe04  jnz     short loc_18007FE79
0x18007fe06  cmp     r14w, [rcx+4]
0x18007fe0b  jnz     short loc_18007FE79
0x18007fe0d  cmp     r14w, [rcx+6]
0x18007fe12  jnz     short loc_18007FE79
0x18007fe14  cmp     [rcx+8], r14d
0x18007fe18  jnz     short loc_18007FE79
0x18007fe1a  cmp     [rcx+0Ch], r14d
0x18007fe1e  jnz     short loc_18007FE79
0x18007fe20  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fe27  lea     rax, WPP_GLOBAL_Control
0x18007fe2e  cmp     rcx, rax
0x18007fe31  jz      short loc_18007FE4D
0x18007fe33  test    byte ptr [rcx+6Ch], 1
0x18007fe37  jz      short loc_18007FE4D
0x18007fe39  mov     rcx, [rcx+60h]
0x18007fe3d  lea     edx, [r14+1Ah]
0x18007fe41  lea     r8, WPP_219177b1f08534930d9088c12436ecaa_Traceguids
0x18007fe48  call    WPP_SF_
0x18007fe4d  mov     edx, 5ECh; unsigned __int16
0x18007fe52  lea     rcx, aVerifypacket; "verifypacket"
0x18007fe59  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18007fe5e  lea     rcx, [rbp+pExceptionObject]
0x18007fe62  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18007fe68  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18007fe6f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007fe73  call    _CxxThrowException_0
0x18007fe79  call    ?GetNextSectionSafe@CSecurityHeader@@QEBAPEADQEAD@Z; CSecurityHeader::GetNextSectionSafe(char * const)
0x18007fe7e  mov     rdi, rax
0x18007fe81  cmp     rax, rsi
0x18007fe84  jbe     short loc_18007FEE0
0x18007fe86  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fe8d  lea     rax, WPP_GLOBAL_Control
0x18007fe94  cmp     rcx, rax
0x18007fe97  jz      short loc_18007FEB4
0x18007fe99  test    byte ptr [rcx+6Ch], 1
0x18007fe9d  jz      short loc_18007FEB4
0x18007fe9f  mov     rcx, [rcx+60h]
0x18007fea3  lea     r8, WPP_219177b1f08534930d9088c12436ecaa_Traceguids
0x18007feaa  mov     edx, 1Bh
0x18007feaf  call    WPP_SF_
0x18007feb4  mov     edx, 5EDh; unsigned __int16
0x18007feb9  lea     rcx, aVerifypacket; "verifypacket"
0x18007fec0  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18007fec5  lea     rcx, [rbp+pExceptionObject]
0x18007fec9  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18007fecf  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18007fed6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007feda  call    _CxxThrowException_0
0x18007fee0  cmp     [rbx+6], r14w
0x18007fee5  jz      short loc_18007FF4C
0x18007fee7  test    byte ptr [rbx], 40h
0x18007feea  jnz     short loc_18007FF4C
0x18007feec  cmp     dword ptr [rbx+0Ch], 6
0x18007fef0  jnb     short loc_18007FF4C
0x18007fef2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fef9  lea     rax, WPP_GLOBAL_Control
0x18007ff00  cmp     rcx, rax
0x18007ff03  jz      short loc_18007FF20
0x18007ff05  test    byte ptr [rcx+6Ch], 1
0x18007ff09  jz      short loc_18007FF20
0x18007ff0b  mov     rcx, [rcx+60h]
0x18007ff0f  lea     r8, WPP_219177b1f08534930d9088c12436ecaa_Traceguids
0x18007ff16  mov     edx, 1Ch
0x18007ff1b  call    WPP_SF_
0x18007ff20  mov     edx, 5EEh; unsigned __int16
0x18007ff25  lea     rcx, aVerifypacket; "verifypacket"
0x18007ff2c  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18007ff31  lea     rcx, [rbp+pExceptionObject]
0x18007ff35  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18007ff3b  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18007ff42  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007ff46  call    _CxxThrowException_0
0x18007ff4c  mov     rcx, rbx; this
0x18007ff4f  call    ?GetSectionExPtr@CSecurityHeader@@AEBAPEBEXZ; CSecurityHeader::GetSectionExPtr(void)
0x18007ff54  test    rax, rax
0x18007ff57  jz      short loc_18007FF66
0x18007ff59  mov     r8, rdi
0x18007ff5c  mov     rdx, rax
0x18007ff5f  xor     ecx, ecx
0x18007ff61  call    ?pGetSubSectionEx@@YAPEAU_SecuritySubSectionEx@@W4enumSecInfoType@@PEBE1@Z; pGetSubSectionEx(enumSecInfoType,uchar const *,uchar const *)
0x18007ff66  movzx   eax, word ptr [rbx]
0x18007ff69  and     ax, 0Fh
0x18007ff6d  cmp     ax, 2
0x18007ff71  jnz     short loc_18007FFDD
0x18007ff73  cmp     word ptr [rbx+2], 10h
0x18007ff78  jz      loc_1800800B0
0x18007ff7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ff85  lea     rax, WPP_GLOBAL_Control
0x18007ff8c  cmp     rcx, rax
0x18007ff8f  jz      short loc_18007FFB1
0x18007ff91  test    byte ptr [rcx+6Ch], 1
0x18007ff95  jz      short loc_18007FFB1
0x18007ff97  movzx   r9d, word ptr [rbx+2]
0x18007ff9c  lea     r8, WPP_219177b1f08534930d9088c12436ecaa_Traceguids
0x18007ffa3  mov     rcx, [rcx+60h]
0x18007ffa7  mov     edx, 1Dh
0x18007ffac  call    WPP_SF_d
0x18007ffb1  mov     edx, 5EFh; unsigned __int16
0x18007ffb6  lea     rcx, aVerifypacket; "verifypacket"
0x18007ffbd  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18007ffc2  lea     rcx, [rbp+pExceptionObject]
0x18007ffc6  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18007ffcc  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18007ffd3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007ffd7  call    _CxxThrowException_0
0x18007ffdd  cmp     ax, 1
0x18007ffe1  jnz     loc_1800800B0
0x18007ffe7  cmp     [rbx+2], r14w
0x18007ffec  jnz     short loc_180080048
0x18007ffee  mov     rcx, cs:WPP_GLOBAL_Control
0x18007fff5  lea     rax, WPP_GLOBAL_Control
0x18007fffc  cmp     rcx, rax
0x18007ffff  jz      short loc_18008001C
0x180080001  test    byte ptr [rcx+6Ch], 1
0x180080005  jz      short loc_18008001C
0x180080007  mov     rcx, [rcx+60h]
0x18008000b  lea     r8, WPP_219177b1f08534930d9088c12436ecaa_Traceguids
0x180080012  mov     edx, 1Eh
0x180080017  call    WPP_SF_
0x18008001c  mov     edx, 5F0h; unsigned __int16
0x180080021  lea     rcx, aVerifypacket; "verifypacket"
0x180080028  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18008002d  lea     rcx, [rbp+pExceptionObject]
0x180080031  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180080037  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18008003e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180080042  call    _CxxThrowException_0
0x180080048  lea     rcx, [rbx+10h]; pSid
0x18008004c  call    cs:__imp_IsValidSid
0x180080052  test    eax, eax
0x180080054  jnz     short loc_1800800B0
0x180080056  mov     rcx, cs:WPP_GLOBAL_Control
0x18008005d  lea     rax, WPP_GLOBAL_Control
0x180080064  cmp     rcx, rax
0x180080067  jz      short loc_180080084
0x180080069  test    byte ptr [rcx+6Ch], 1
0x18008006d  jz      short loc_180080084
0x18008006f  mov     rcx, [rcx+60h]
0x180080073  lea     r8, WPP_219177b1f08534930d9088c12436ecaa_Traceguids
0x18008007a  mov     edx, 1Fh
0x18008007f  call    WPP_SF_
0x180080084  mov     edx, 5F1h; unsigned __int16
0x180080089  lea     rcx, aVerifypacket; "verifypacket"
0x180080090  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180080095  lea     rcx, [rbp+pExceptionObject]
0x180080099  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18008009f  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800800a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800800aa  call    _CxxThrowException_0
0x1800800b0  add     rsp, 40h
0x1800800b4  pop     r14
0x1800800b6  pop     rdi
0x1800800b7  pop     rsi
0x1800800b8  pop     rbx
0x1800800b9  pop     rbp
0x1800800ba  retn
```
