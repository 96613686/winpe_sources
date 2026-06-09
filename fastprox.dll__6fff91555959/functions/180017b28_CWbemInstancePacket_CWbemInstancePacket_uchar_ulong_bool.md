# CWbemInstancePacket::CWbemInstancePacket(uchar *,ulong,bool)

- ea: `0x180017b28`
- end: `0x180017dd6`
- name: `??0CWbemInstancePacket@@QEAA@PEAEK_N@Z`
- size: `686`
- prototype: `CWbemInstancePacket *__fastcall(CWbemInstancePacket *this, unsigned __int8 *, unsigned int, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017910`
- `0x18001b8b0`

## callees

- `0x180017b28`
- `0x180035b08`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180017bc9`
- `wbemcomn!GetMemLogObject` at `0x180017c32`
- `wbemcomn!GetMemLogObject` at `0x180017c9b`
- `wbemcomn!GetMemLogObject` at `0x180017d04`
- `wbemcomn!GetMemLogObject` at `0x180017d6d`
- `wbemcomn!GetMemLogObject` at `0x180017bc9`
- `wbemcomn!GetMemLogObject` at `0x180017c32`
- `wbemcomn!GetMemLogObject` at `0x180017c9b`
- `wbemcomn!GetMemLogObject` at `0x180017d04`
- `wbemcomn!GetMemLogObject` at `0x180017d6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017bd7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017c40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017ca9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017bd7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017c40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017ca9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017d7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CWbemInstancePacket *__fastcall CWbemInstancePacket::CWbemInstancePacket(
        CWbemInstancePacket *this,
        unsigned __int8 *a2,
        unsigned int a3,
        char a4)
{
  unsigned __int8 *v4; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  CMemoryLog *v10; // rax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *(_QWORD *)this = &CWbemInstancePacket::`vftable';
  if ( a2 )
  {
    v4 = a2 + 9;
    if ( a2 + 9 < a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    *((_QWORD *)this + 3) = v4;
    if ( a3 < 0x21 )
    {
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    *((_DWORD *)this + 8) = a3 - 9;
    if ( a4 && (*(_DWORD *)v4 != 24 || *(_DWORD *)(a2 + 13) > a3 - 9) )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_DATA)");
      }
      pExceptionObject = 13;
      throw (SafeIntException *)&pExceptionObject;
    }
  }
  else
  {
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 8) = 0;
  }
  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 4) = a3;
  if ( a2 && a4 )
  {
    if ( a3 < 9 )
    {
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    if ( *(_DWORD *)a2 != 9 || *((unsigned int *)a2 + 1) > (unsigned __int64)a3 - 9 )
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_DATA)");
      }
      pExceptionObject = 13;
      throw (SafeIntException *)&pExceptionObject;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180017b28  sub     rsp, 28h
0x180017b2c  xor     r11d, r11d
0x180017b2f  lea     rax, ??_7CWbemInstancePacket@@6B@; const CWbemInstancePacket::`vftable'
0x180017b36  mov     [rcx+8], r11
0x180017b3a  mov     r10, rcx
0x180017b3d  mov     [rcx+10h], r11d
0x180017b41  mov     [rcx], rax
0x180017b44  test    rdx, rdx
0x180017b47  jz      short loc_180017BBF
0x180017b49  lea     rax, [rdx+9]
0x180017b4d  cmp     rax, rdx
0x180017b50  jbe     short loc_180017BC9
0x180017b52  mov     [rcx+18h], rax
0x180017b56  cmp     r8d, 21h ; '!'
0x180017b5a  jb      loc_180017C32
0x180017b60  lea     ecx, [r8-9]
0x180017b64  mov     [r10+20h], ecx
0x180017b68  test    r9b, r9b
0x180017b6b  jz      short loc_180017B7F
0x180017b6d  cmp     dword ptr [rax], 18h
0x180017b70  jnz     loc_180017C9B
0x180017b76  cmp     [rax+4], ecx
0x180017b79  ja      loc_180017C9B
0x180017b7f  mov     [r10+8], rdx
0x180017b83  mov     [r10+10h], r8d
0x180017b87  test    rdx, rdx
0x180017b8a  jz      short loc_180017BB7
0x180017b8c  test    r9b, r9b
0x180017b8f  jz      short loc_180017BB7
0x180017b91  cmp     r8d, 9
0x180017b95  jb      loc_180017D04
0x180017b9b  cmp     dword ptr [rdx], 9
0x180017b9e  jnz     loc_180017D6D
0x180017ba4  mov     ecx, [rdx+4]
0x180017ba7  mov     eax, r8d
0x180017baa  sub     rax, 9
0x180017bae  cmp     rcx, rax
0x180017bb1  ja      loc_180017D6D
0x180017bb7  mov     rax, r10
0x180017bba  add     rsp, 28h
0x180017bbe  retn
0x180017bbf  mov     [rcx+18h], r11
0x180017bc3  mov     [rcx+20h], r11d
0x180017bc7  jmp     short loc_180017B7F
0x180017bc9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017bcf  mov     rcx, rax
0x180017bd2  mov     edx, 0FFFFFFFEh
0x180017bd7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180017be4  lea     rax, WPP_GLOBAL_Control
0x180017beb  cmp     rcx, rax
0x180017bee  jz      short loc_180017C18
0x180017bf0  test    byte ptr [rcx+1Ch], 1
0x180017bf4  jz      short loc_180017C18
0x180017bf6  cmp     byte ptr [rcx+19h], 2
0x180017bfa  jb      short loc_180017C18
0x180017bfc  mov     rcx, [rcx+10h]
0x180017c00  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180017c07  mov     edx, 1Eh
0x180017c0c  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180017c13  call    WPP_SF_s
0x180017c18  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180017c1f  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x180017c27  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180017c2c  call    _CxxThrowException_0
0x180017c32  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017c38  mov     rcx, rax
0x180017c3b  mov     edx, 0FFFFFFFEh
0x180017c40  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c4d  lea     rax, WPP_GLOBAL_Control
0x180017c54  cmp     rcx, rax
0x180017c57  jz      short loc_180017C81
0x180017c59  test    byte ptr [rcx+1Ch], 1
0x180017c5d  jz      short loc_180017C81
0x180017c5f  cmp     byte ptr [rcx+19h], 2
0x180017c63  jb      short loc_180017C81
0x180017c65  mov     rcx, [rcx+10h]
0x180017c69  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180017c70  mov     edx, 1Fh
0x180017c75  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180017c7c  call    WPP_SF_s
0x180017c81  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180017c88  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x180017c90  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180017c95  call    _CxxThrowException_0
0x180017c9b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017ca1  mov     rcx, rax
0x180017ca4  mov     edx, 0FFFFFFFEh
0x180017ca9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017caf  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cb6  lea     rax, WPP_GLOBAL_Control
0x180017cbd  cmp     rcx, rax
0x180017cc0  jz      short loc_180017CEA
0x180017cc2  test    byte ptr [rcx+1Ch], 1
0x180017cc6  jz      short loc_180017CEA
0x180017cc8  cmp     byte ptr [rcx+19h], 2
0x180017ccc  jb      short loc_180017CEA
0x180017cce  mov     rcx, [rcx+10h]
0x180017cd2  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180017cd9  mov     edx, 20h ; ' '
0x180017cde  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180017ce5  call    WPP_SF_s
0x180017cea  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180017cf1  mov     [rsp+28h+pExceptionObject], 0Dh
0x180017cf9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180017cfe  call    _CxxThrowException_0
0x180017d04  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017d0a  mov     rcx, rax
0x180017d0d  mov     edx, 0FFFFFFFEh
0x180017d12  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d1f  lea     rax, WPP_GLOBAL_Control
0x180017d26  cmp     rcx, rax
0x180017d29  jz      short loc_180017D53
0x180017d2b  test    byte ptr [rcx+1Ch], 1
0x180017d2f  jz      short loc_180017D53
0x180017d31  cmp     byte ptr [rcx+19h], 2
0x180017d35  jb      short loc_180017D53
0x180017d37  mov     rcx, [rcx+10h]
0x180017d3b  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180017d42  mov     edx, 0Dh
0x180017d47  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180017d4e  call    WPP_SF_s
0x180017d53  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180017d5a  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x180017d62  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180017d67  call    _CxxThrowException_0
0x180017d6d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017d73  mov     rcx, rax
0x180017d76  mov     edx, 0FFFFFFFEh
0x180017d7b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d88  lea     rax, WPP_GLOBAL_Control
0x180017d8f  cmp     rcx, rax
0x180017d92  jz      short loc_180017DBC
0x180017d94  test    byte ptr [rcx+1Ch], 1
0x180017d98  jz      short loc_180017DBC
0x180017d9a  cmp     byte ptr [rcx+19h], 2
0x180017d9e  jb      short loc_180017DBC
0x180017da0  mov     rcx, [rcx+10h]
0x180017da4  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180017dab  mov     edx, 0Eh
0x180017db0  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180017db7  call    WPP_SF_s
0x180017dbc  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180017dc3  mov     [rsp+28h+pExceptionObject], 0Dh
0x180017dcb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180017dd0  call    _CxxThrowException_0
```
