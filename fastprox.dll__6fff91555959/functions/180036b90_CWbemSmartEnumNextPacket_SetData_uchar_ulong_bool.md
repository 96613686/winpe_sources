# CWbemSmartEnumNextPacket::SetData(uchar *,ulong,bool)

- ea: `0x180036b90`
- end: `0x180036dc8`
- name: `?SetData@CWbemSmartEnumNextPacket@@QEAAXPEAEK_N@Z`
- size: `568`
- prototype: `void __fastcall(CWbemSmartEnumNextPacket *__hidden this, unsigned __int8 *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035e90`
- `0x180036b60`

## callees

- `0x180035b08`
- `0x180036a90`
- `0x180036b90`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180036bd2`
- `wbemcomn!GetMemLogObject` at `0x180036c7c`
- `wbemcomn!GetMemLogObject` at `0x180036cc1`
- `wbemcomn!GetMemLogObject` at `0x180036d2a`
- `wbemcomn!GetMemLogObject` at `0x180036bd2`
- `wbemcomn!GetMemLogObject` at `0x180036c7c`
- `wbemcomn!GetMemLogObject` at `0x180036cc1`
- `wbemcomn!GetMemLogObject` at `0x180036d2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036be0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036c8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ccf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036d38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036be0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036c8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ccf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036d38`

## pseudocode

```c
void __fastcall CWbemSmartEnumNextPacket::SetData(
        CWbemSmartEnumNextPacket *this,
        unsigned __int8 *a2,
        unsigned int a3,
        char a4)
{
  unsigned __int8 *v5; // rcx
  CMemoryLog *v6; // rax
  CMemoryLog *v7; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v9; // rax
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = a2 + 26;
    if ( a2 + 26 < a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    *((_QWORD *)this + 2) = v5;
    if ( a4 )
    {
      if ( a3 < 0x22 )
      {
        v9 = GetMemLogObject();
        CMemoryLog::Write(v9, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        pExceptionObject = 87;
        throw (SafeIntException *)&pExceptionObject;
      }
      if ( *(_DWORD *)(a2 + 30) > a3 - 34 || *(_DWORD *)v5 != 8 )
      {
        v6 = GetMemLogObject();
        CMemoryLog::Write(v6, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids,
            "SafeIntException(ERROR_INVALID_DATA)");
        }
        pExceptionObject = 13;
        throw (SafeIntException *)&pExceptionObject;
      }
    }
  }
  else
  {
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = a3;
  if ( a2
    && a4
    && (*((_DWORD *)a2 + 3) != 26
     || *((unsigned int *)a2 + 4) > (unsigned __int64)a3 - 26
     || (int)CWbemDataPacket::IsValid(this, 0) < 0) )
  {
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_172c0f1e86c2386173baa66c351dfc86_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180036b90  sub     rsp, 28h
0x180036b94  mov     r10, rcx
0x180036b97  test    rdx, rdx
0x180036b9a  jz      loc_180036C3B
0x180036ba0  lea     rcx, [rdx+1Ah]
0x180036ba4  cmp     rcx, rdx
0x180036ba7  jbe     loc_180036CC1
0x180036bad  mov     [r10+10h], rcx
0x180036bb1  test    r9b, r9b
0x180036bb4  jz      loc_180036C43
0x180036bba  cmp     r8d, 22h ; '"'
0x180036bbe  jb      loc_180036D2A
0x180036bc4  lea     eax, [r8-22h]
0x180036bc8  cmp     [rcx+4], eax
0x180036bcb  ja      short loc_180036BD2
0x180036bcd  cmp     dword ptr [rcx], 8
0x180036bd0  jz      short loc_180036C43
0x180036bd2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036bd8  mov     rcx, rax
0x180036bdb  mov     edx, 0FFFFFFFEh
0x180036be0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bed  lea     rax, WPP_GLOBAL_Control
0x180036bf4  cmp     rcx, rax
0x180036bf7  jz      short loc_180036C21
0x180036bf9  test    byte ptr [rcx+1Ch], 1
0x180036bfd  jz      short loc_180036C21
0x180036bff  cmp     byte ptr [rcx+19h], 2
0x180036c03  jb      short loc_180036C21
0x180036c05  mov     rcx, [rcx+10h]
0x180036c09  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180036c10  mov     edx, 13h
0x180036c15  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x180036c1c  call    WPP_SF_s
0x180036c21  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180036c28  mov     [rsp+28h+pExceptionObject], 0Dh
0x180036c30  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180036c35  call    _CxxThrowException_0
0x180036c3b  mov     qword ptr [rcx+10h], 0
0x180036c43  mov     [r10], rdx
0x180036c46  mov     [r10+8], r8d
0x180036c4a  test    rdx, rdx
0x180036c4d  jz      short loc_180036C54
0x180036c4f  test    r9b, r9b
0x180036c52  jnz     short loc_180036C59
0x180036c54  add     rsp, 28h
0x180036c58  retn
0x180036c59  cmp     dword ptr [rdx+0Ch], 1Ah
0x180036c5d  jnz     short loc_180036C7C
0x180036c5f  mov     ecx, [rdx+10h]
0x180036c62  mov     eax, r8d
0x180036c65  sub     rax, 1Ah
0x180036c69  cmp     rcx, rax
0x180036c6c  ja      short loc_180036C7C
0x180036c6e  xor     edx, edx; int
0x180036c70  mov     rcx, r10; this
0x180036c73  call    ?IsValid@CWbemDataPacket@@QEAAJJ@Z; CWbemDataPacket::IsValid(long)
0x180036c78  test    eax, eax
0x180036c7a  jns     short loc_180036C54
0x180036c7c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036c82  mov     rcx, rax
0x180036c85  mov     edx, 0FFFFFFFEh
0x180036c8a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c97  lea     rax, WPP_GLOBAL_Control
0x180036c9e  cmp     rcx, rax
0x180036ca1  jnz     loc_180036D93
0x180036ca7  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180036cae  mov     [rsp+28h+pExceptionObject], 0Dh
0x180036cb6  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180036cbb  call    _CxxThrowException_0
0x180036cc1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036cc7  mov     rcx, rax
0x180036cca  mov     edx, 0FFFFFFFEh
0x180036ccf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cdc  lea     rax, WPP_GLOBAL_Control
0x180036ce3  cmp     rcx, rax
0x180036ce6  jz      short loc_180036D10
0x180036ce8  test    byte ptr [rcx+1Ch], 1
0x180036cec  jz      short loc_180036D10
0x180036cee  cmp     byte ptr [rcx+19h], 2
0x180036cf2  jb      short loc_180036D10
0x180036cf4  mov     rcx, [rcx+10h]
0x180036cf8  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180036cff  mov     edx, 11h
0x180036d04  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x180036d0b  call    WPP_SF_s
0x180036d10  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180036d17  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x180036d1f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180036d24  call    _CxxThrowException_0
0x180036d2a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036d30  mov     rcx, rax
0x180036d33  mov     edx, 0FFFFFFFEh
0x180036d38  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d45  lea     rax, WPP_GLOBAL_Control
0x180036d4c  cmp     rcx, rax
0x180036d4f  jz      short loc_180036D79
0x180036d51  test    byte ptr [rcx+1Ch], 1
0x180036d55  jz      short loc_180036D79
0x180036d57  cmp     byte ptr [rcx+19h], 2
0x180036d5b  jb      short loc_180036D79
0x180036d5d  mov     rcx, [rcx+10h]
0x180036d61  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180036d68  mov     edx, 12h
0x180036d6d  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x180036d74  call    WPP_SF_s
0x180036d79  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180036d80  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x180036d88  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180036d8d  call    _CxxThrowException_0
0x180036d93  test    byte ptr [rcx+1Ch], 1
0x180036d97  jz      loc_180036CA7
0x180036d9d  cmp     byte ptr [rcx+19h], 2
0x180036da1  jb      loc_180036CA7
0x180036da7  mov     rcx, [rcx+10h]
0x180036dab  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180036db2  mov     edx, 0Ch
0x180036db7  lea     r8, WPP_172c0f1e86c2386173baa66c351dfc86_Traceguids
0x180036dbe  call    WPP_SF_s
0x180036dc3  jmp     loc_180036CA7
```
