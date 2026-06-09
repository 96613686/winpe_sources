# CWbemClassPacket::SetData(uchar *,ulong,bool)

- ea: `0x180016414`
- end: `0x1800166a3`
- name: `?SetData@CWbemClassPacket@@QEAAXPEAEK_N@Z`
- size: `655`
- prototype: `void __fastcall(CWbemClassPacket *this, unsigned __int8 *, unsigned int, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800158e0`
- `0x180062c60`

## callees

- `0x180016414`
- `0x180035b08`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180016496`
- `wbemcomn!GetMemLogObject` at `0x1800164ff`
- `wbemcomn!GetMemLogObject` at `0x180016568`
- `wbemcomn!GetMemLogObject` at `0x1800165d1`
- `wbemcomn!GetMemLogObject` at `0x18001663a`
- `wbemcomn!GetMemLogObject` at `0x180016496`
- `wbemcomn!GetMemLogObject` at `0x1800164ff`
- `wbemcomn!GetMemLogObject` at `0x180016568`
- `wbemcomn!GetMemLogObject` at `0x1800165d1`
- `wbemcomn!GetMemLogObject` at `0x18001663a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800164a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001650d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016576`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800165df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016648`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800164a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001650d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016576`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800165df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016648`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWbemClassPacket::SetData(CWbemClassPacket *this, unsigned __int8 *a2, unsigned int a3, char a4)
{
  unsigned __int8 *v4; // rax
  CMemoryLog *v5; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v7; // rax
  CMemoryLog *v8; // rax
  CMemoryLog *v9; // rax
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

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
          20,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    *((_QWORD *)this + 2) = v4;
    if ( a3 < 0x11 )
    {
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    *((_DWORD *)this + 6) = a3 - 9;
    if ( a4 && (*(_DWORD *)v4 != 8 || *(_DWORD *)(a2 + 13) > a3 - 9) )
    {
      v5 = GetMemLogObject();
      CMemoryLog::Write(v5, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_DATA)");
      }
      pExceptionObject = 13;
      throw (SafeIntException *)&pExceptionObject;
    }
  }
  else
  {
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 6) = 0;
  }
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = a3;
  if ( a2 && a4 )
  {
    if ( a3 < 9 )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, -2);
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
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, -2);
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
}

```

## disassembly

```asm
0x180016414  sub     rsp, 28h
0x180016418  mov     r10b, r9b
0x18001641b  test    rdx, rdx
0x18001641e  jnz     short loc_180016463
0x180016420  mov     [rcx+10h], rdx
0x180016424  mov     [rcx+18h], edx
0x180016427  mov     [rcx], rdx
0x18001642a  mov     [rcx+8], r8d
0x18001642e  test    rdx, rdx
0x180016431  jz      short loc_18001645E
0x180016433  test    r10b, r10b
0x180016436  jz      short loc_18001645E
0x180016438  cmp     r8d, 9
0x18001643c  jb      loc_1800165D1
0x180016442  cmp     dword ptr [rdx], 9
0x180016445  jnz     loc_18001663A
0x18001644b  mov     ecx, [rdx+4]
0x18001644e  mov     eax, r8d
0x180016451  sub     rax, 9
0x180016455  cmp     rcx, rax
0x180016458  ja      loc_18001663A
0x18001645e  add     rsp, 28h
0x180016462  retn
0x180016463  lea     rax, [rdx+9]
0x180016467  cmp     rax, rdx
0x18001646a  jbe     loc_1800164FF
0x180016470  mov     [rcx+10h], rax
0x180016474  cmp     r8d, 11h
0x180016478  jb      loc_180016568
0x18001647e  lea     r9d, [r8-9]
0x180016482  mov     [rcx+18h], r9d
0x180016486  test    r10b, r10b
0x180016489  jz      short loc_180016427
0x18001648b  cmp     dword ptr [rax], 8
0x18001648e  jnz     short loc_180016496
0x180016490  cmp     [rax+4], r9d
0x180016494  jbe     short loc_180016427
0x180016496  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001649c  mov     rcx, rax
0x18001649f  mov     edx, 0FFFFFFFEh
0x1800164a4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800164aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164b1  lea     rax, WPP_GLOBAL_Control
0x1800164b8  cmp     rcx, rax
0x1800164bb  jz      short loc_1800164E5
0x1800164bd  test    byte ptr [rcx+1Ch], 1
0x1800164c1  jz      short loc_1800164E5
0x1800164c3  cmp     byte ptr [rcx+19h], 2
0x1800164c7  jb      short loc_1800164E5
0x1800164c9  mov     rcx, [rcx+10h]
0x1800164cd  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x1800164d4  mov     edx, 16h
0x1800164d9  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800164e0  call    WPP_SF_s
0x1800164e5  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800164ec  mov     [rsp+28h+pExceptionObject], 0Dh
0x1800164f4  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800164f9  call    _CxxThrowException_0
0x1800164ff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016505  mov     rcx, rax
0x180016508  mov     edx, 0FFFFFFFEh
0x18001650d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001651a  lea     rax, WPP_GLOBAL_Control
0x180016521  cmp     rcx, rax
0x180016524  jz      short loc_18001654E
0x180016526  test    byte ptr [rcx+1Ch], 1
0x18001652a  jz      short loc_18001654E
0x18001652c  cmp     byte ptr [rcx+19h], 2
0x180016530  jb      short loc_18001654E
0x180016532  mov     rcx, [rcx+10h]
0x180016536  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18001653d  mov     edx, 14h
0x180016542  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180016549  call    WPP_SF_s
0x18001654e  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180016555  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x18001655d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180016562  call    _CxxThrowException_0
0x180016568  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001656e  mov     rcx, rax
0x180016571  mov     edx, 0FFFFFFFEh
0x180016576  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001657c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016583  lea     rax, WPP_GLOBAL_Control
0x18001658a  cmp     rcx, rax
0x18001658d  jz      short loc_1800165B7
0x18001658f  test    byte ptr [rcx+1Ch], 1
0x180016593  jz      short loc_1800165B7
0x180016595  cmp     byte ptr [rcx+19h], 2
0x180016599  jb      short loc_1800165B7
0x18001659b  mov     rcx, [rcx+10h]
0x18001659f  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x1800165a6  mov     edx, 15h
0x1800165ab  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800165b2  call    WPP_SF_s
0x1800165b7  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800165be  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x1800165c6  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800165cb  call    _CxxThrowException_0
0x1800165d1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800165d7  mov     rcx, rax
0x1800165da  mov     edx, 0FFFFFFFEh
0x1800165df  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800165e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165ec  lea     rax, WPP_GLOBAL_Control
0x1800165f3  cmp     rcx, rax
0x1800165f6  jz      short loc_180016620
0x1800165f8  test    byte ptr [rcx+1Ch], 1
0x1800165fc  jz      short loc_180016620
0x1800165fe  cmp     byte ptr [rcx+19h], 2
0x180016602  jb      short loc_180016620
0x180016604  mov     rcx, [rcx+10h]
0x180016608  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18001660f  mov     edx, 0Dh
0x180016614  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001661b  call    WPP_SF_s
0x180016620  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180016627  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x18001662f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180016634  call    _CxxThrowException_0
0x18001663a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016640  mov     rcx, rax
0x180016643  mov     edx, 0FFFFFFFEh
0x180016648  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001664e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016655  lea     rax, WPP_GLOBAL_Control
0x18001665c  cmp     rcx, rax
0x18001665f  jz      short loc_180016689
0x180016661  test    byte ptr [rcx+1Ch], 1
0x180016665  jz      short loc_180016689
0x180016667  cmp     byte ptr [rcx+19h], 2
0x18001666b  jb      short loc_180016689
0x18001666d  mov     rcx, [rcx+10h]
0x180016671  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180016678  mov     edx, 0Eh
0x18001667d  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180016684  call    WPP_SF_s
0x180016689  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180016690  mov     [rsp+28h+pExceptionObject], 0Dh
0x180016698  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001669d  call    _CxxThrowException_0
```
