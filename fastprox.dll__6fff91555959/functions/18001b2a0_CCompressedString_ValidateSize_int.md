# CCompressedString::ValidateSize(int)

- ea: `0x18001b2a0`
- end: `0x18001b4b5`
- name: `?ValidateSize@CCompressedString@@QEBAHH@Z`
- size: `533`
- prototype: `__int64 __fastcall(CCompressedString *__hidden this, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018f50`
- `0x18001a6d0`
- `0x18001a7c0`
- `0x18001ab90`
- `0x18001ac00`
- `0x180023bd0`

## callees

- `0x18001b2a0`
- `0x180035b08`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001b2ed`
- `wbemcomn!GetMemLogObject` at `0x18001b362`
- `wbemcomn!GetMemLogObject` at `0x18001b3ee`
- `wbemcomn!GetMemLogObject` at `0x18001b427`
- `wbemcomn!GetMemLogObject` at `0x18001b2ed`
- `wbemcomn!GetMemLogObject` at `0x18001b362`
- `wbemcomn!GetMemLogObject` at `0x18001b3ee`
- `wbemcomn!GetMemLogObject` at `0x18001b427`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b2fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b370`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b3fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b435`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b2fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b370`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b3fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b435`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCompressedString::ValidateSize(CCompressedString *this, int a2)
{
  int v3; // r9d
  char *v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  CMemoryLog *v7; // rax
  _BYTE *v8; // rax
  int v9; // ecx
  CMemoryLog *v10; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *MemLogObject; // rax
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 < 2 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  if ( *(_BYTE *)this == 1 )
  {
    if ( a2 < 3 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
          "CX_Exception()");
      }
      throw (CX_Exception *)&pExceptionObject;
    }
    v3 = a2 - 1;
    v4 = (char *)this + 1;
    v5 = (a2 - 1) / 2;
    v6 = v5;
    if ( !v5 )
      goto LABEL_7;
    while ( *v4 || v4[1] )
    {
      v4 += 2;
      v3 -= 2;
      if ( !--v6 )
        goto LABEL_7;
    }
    if ( !v6 )
    {
LABEL_7:
      v7 = GetMemLogObject();
      CMemoryLog::Write(v7, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
          "CX_Exception()");
      }
      throw (CX_Exception *)&pExceptionObject;
    }
    return (unsigned int)(a2 - v3 + 2);
  }
  else
  {
    v8 = (char *)this + 1;
    v9 = a2 - 1;
    while ( *v8 )
    {
      ++v8;
      if ( !--v9 )
      {
        v10 = GetMemLogObject();
        CMemoryLog::Write(v10, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
            "CX_Exception()");
        }
        throw (CX_Exception *)&pExceptionObject;
      }
    }
    return (unsigned int)(a2 - v9 + 1);
  }
}

```

## disassembly

```asm
0x18001b2a0  sub     rsp, 28h
0x18001b2a4  mov     r8d, edx
0x18001b2a7  cmp     edx, 2
0x18001b2aa  jl      loc_18001B427
0x18001b2b0  cmp     byte ptr [rcx], 1
0x18001b2b3  jnz     loc_18001B34E
0x18001b2b9  cmp     edx, 3
0x18001b2bc  jl      loc_18001B3EE
0x18001b2c2  lea     r9d, [rdx-1]
0x18001b2c6  inc     rcx
0x18001b2c9  mov     eax, r9d
0x18001b2cc  cdq
0x18001b2cd  sub     eax, edx
0x18001b2cf  sar     eax, 1
0x18001b2d1  movsxd  rdx, eax
0x18001b2d4  jz      short loc_18001B2ED
0x18001b2d6  cmp     byte ptr [rcx], 0
0x18001b2d9  jz      loc_18001B3CF
0x18001b2df  add     rcx, 2
0x18001b2e3  sub     r9d, 2
0x18001b2e7  sub     rdx, 1
0x18001b2eb  jnz     short loc_18001B2D6
0x18001b2ed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b2f3  mov     rcx, rax
0x18001b2f6  mov     edx, 0FFFFFFFEh
0x18001b2fb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b301  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b308  lea     rax, WPP_GLOBAL_Control
0x18001b30f  cmp     rcx, rax
0x18001b312  jz      short loc_18001B33C
0x18001b314  test    byte ptr [rcx+1Ch], 1
0x18001b318  jz      short loc_18001B33C
0x18001b31a  cmp     byte ptr [rcx+19h], 2
0x18001b31e  jb      short loc_18001B33C
0x18001b320  mov     rcx, [rcx+10h]
0x18001b324  lea     r9, aCxException; "CX_Exception()"
0x18001b32b  mov     edx, 0Eh
0x18001b330  lea     r8, WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids
0x18001b337  call    WPP_SF_s
0x18001b33c  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001b343  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001b348  call    _CxxThrowException_0
0x18001b34e  lea     rax, [rcx+1]
0x18001b352  lea     ecx, [rdx-1]
0x18001b355  cmp     byte ptr [rax], 0
0x18001b358  jz      short loc_18001B3C3
0x18001b35a  inc     rax
0x18001b35d  sub     ecx, 1
0x18001b360  jnz     short loc_18001B355
0x18001b362  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b368  mov     rcx, rax
0x18001b36b  mov     edx, 0FFFFFFFEh
0x18001b370  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b376  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b37d  lea     rax, WPP_GLOBAL_Control
0x18001b384  cmp     rcx, rax
0x18001b387  jz      short loc_18001B3B1
0x18001b389  test    byte ptr [rcx+1Ch], 1
0x18001b38d  jz      short loc_18001B3B1
0x18001b38f  cmp     byte ptr [rcx+19h], 2
0x18001b393  jb      short loc_18001B3B1
0x18001b395  mov     rcx, [rcx+10h]
0x18001b399  lea     r9, aCxException; "CX_Exception()"
0x18001b3a0  mov     edx, 0Fh
0x18001b3a5  lea     r8, WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids
0x18001b3ac  call    WPP_SF_s
0x18001b3b1  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001b3b8  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001b3bd  call    _CxxThrowException_0
0x18001b3c3  sub     r8d, ecx
0x18001b3c6  lea     eax, [r8+1]
0x18001b3ca  add     rsp, 28h
0x18001b3ce  retn
0x18001b3cf  cmp     byte ptr [rcx+1], 0
0x18001b3d3  jnz     loc_18001B2DF
0x18001b3d9  test    rdx, rdx
0x18001b3dc  jz      loc_18001B2ED
0x18001b3e2  sub     r8d, r9d
0x18001b3e5  lea     eax, [r8+2]
0x18001b3e9  add     rsp, 28h
0x18001b3ed  retn
0x18001b3ee  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b3f4  mov     rcx, rax
0x18001b3f7  mov     edx, 0FFFFFFFEh
0x18001b3fc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b402  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b409  lea     rax, WPP_GLOBAL_Control
0x18001b410  cmp     rcx, rax
0x18001b413  jnz     short loc_18001B488
0x18001b415  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001b41c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001b421  call    _CxxThrowException_0
0x18001b427  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b42d  mov     rcx, rax
0x18001b430  mov     edx, 0FFFFFFFEh
0x18001b435  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b442  lea     rax, WPP_GLOBAL_Control
0x18001b449  cmp     rcx, rax
0x18001b44c  jz      short loc_18001B476
0x18001b44e  test    byte ptr [rcx+1Ch], 1
0x18001b452  jz      short loc_18001B476
0x18001b454  cmp     byte ptr [rcx+19h], 2
0x18001b458  jb      short loc_18001B476
0x18001b45a  mov     rcx, [rcx+10h]
0x18001b45e  lea     r9, aCxException; "CX_Exception()"
0x18001b465  mov     edx, 0Ch
0x18001b46a  lea     r8, WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids
0x18001b471  call    WPP_SF_s
0x18001b476  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001b47d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001b482  call    _CxxThrowException_0
0x18001b488  test    byte ptr [rcx+1Ch], 1
0x18001b48c  jz      short loc_18001B415
0x18001b48e  cmp     byte ptr [rcx+19h], 2
0x18001b492  jb      short loc_18001B415
0x18001b494  mov     rcx, [rcx+10h]
0x18001b498  lea     r9, aCxException; "CX_Exception()"
0x18001b49f  mov     edx, 0Dh
0x18001b4a4  lea     r8, WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids
0x18001b4ab  call    WPP_SF_s
0x18001b4b0  jmp     loc_18001B415
```
