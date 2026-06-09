# CSession::GetObjectW(IWmiDbHandle *,IWbemPath *,ulong,ulong,IWmiDbHandle * *)

- ea: `0x1800038f0`
- end: `0x180003bae`
- name: `?GetObjectW@CSession@@UEAAJPEAUIWmiDbHandle@@PEAUIWbemPath@@KKPEAPEAU2@@Z`
- size: `702`
- prototype: `__int64 __fastcall(CSession *this, struct IWmiDbHandle *, struct IWbemPath *, __int64, char, struct IWmiDbHandle **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180003660`
- `0x1800038f0`
- `0x180003fb0`
- `0x1800157d0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180003a74`
- `wbemcomn!GetMemLogObject` at `0x180003ac4`
- `wbemcomn!GetMemLogObject` at `0x180003b56`
- `wbemcomn!GetMemLogObject` at `0x180003a74`
- `wbemcomn!GetMemLogObject` at `0x180003ac4`
- `wbemcomn!GetMemLogObject` at `0x180003b56`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003a82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003ad2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003b61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003a82`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003ad2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003b61`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSession::GetObjectW(
        CSession *this,
        struct IWmiDbHandle *a2,
        struct IWbemPath *a3,
        __int64 a4,
        char a5,
        struct IWmiDbHandle **a6)
{
  CLock *v9; // rsi
  int v10; // edi
  int v11; // ebx
  __int64 result; // rax
  int ObjectW; // ebx
  CVarObjHeap *v14; // rcx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CLock *v20; // [rsp+30h] [rbp-48h] BYREF
  int v21; // [rsp+38h] [rbp-40h]

  try
  {
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
    }
    v9 = (CLock *)&g_readWriteLock;
    v20 = (CLock *)&g_readWriteLock;
    v10 = 0;
    v21 = 0;
    if ( !*((_BYTE *)this + 168) )
    {
      if ( !CAutoReadLock::Lock((CAutoReadLock *)&v20) )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217407);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749889LL);
        }
        if ( v21 )
          CLock::ReadUnlock(v20);
        return 2147749889LL;
      }
      v10 = v21;
      v9 = v20;
    }
    if ( !g_bShuttingDown )
    {
      v11 = *(_DWORD *)(*((_QWORD *)a2 + 11) + 48LL);
      if ( v11 < 0 )
      {
        if ( v10 )
          CLock::ReadUnlock(v9);
        return (unsigned int)v11;
      }
      ObjectW = CNamespaceHandle::GetObjectW(a2, a3, (__int64)a3, a5, a6);
      if ( ObjectW == -1 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control )
        {
LABEL_44:
          v17 = GetMemLogObject();
          CMemoryLog::Write(v17, ObjectW);
          v14 = WPP_GLOBAL_Control;
LABEL_17:
          if ( v14 != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v14 + 28) & 1) != 0
            && *((_BYTE *)v14 + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)v14 + 2), 14, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)ObjectW);
          }
          if ( v10 )
            CLock::ReadUnlock(v9);
          return (unsigned int)ObjectW;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
LABEL_14:
          if ( v14 != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v14 + 28) & 1) != 0
            && *((_BYTE *)v14 + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)v14 + 2), 80, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
            v14 = WPP_GLOBAL_Control;
          }
          if ( ObjectW >= 0 )
            goto LABEL_17;
          goto LABEL_44;
        }
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
      }
      v14 = WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, -2147217357);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
    }
    if ( v10 )
      CLock::ReadUnlock(v9);
    result = 2147749939LL;
  }
  catch ( CX_MemoryException )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217398);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
}

```

## disassembly

```asm
0x1800038f0  push    rbx
0x1800038f2  push    rsi
0x1800038f3  push    rdi
0x1800038f4  push    r12
0x1800038f6  push    r14
0x1800038f8  push    r15
0x1800038fa  sub     rsp, 48h
0x1800038fe  mov     r15, r8
0x180003901  mov     r14, rdx
0x180003904  mov     rbx, rcx
0x180003907  lea     r12, WPP_GLOBAL_Control
0x18000390e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003915  cmp     rcx, r12
0x180003918  jz      short loc_180003924
0x18000391a  test    byte ptr [rcx+1Ch], 1
0x18000391e  jnz     loc_180003A50
0x180003924  lea     rsi, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18000392b  mov     [rsp+78h+var_48], rsi
0x180003930  xor     edi, edi
0x180003932  mov     [rsp+78h+var_40], edi
0x180003936  cmp     [rbx+0A8h], dil
0x18000393d  jz      short loc_180003974
0x18000393f  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180003946  jnz     loc_180003AC4
0x18000394c  mov     rbx, [r14+58h]
0x180003950  mov     ebx, [rbx+30h]
0x180003953  test    ebx, ebx
0x180003955  jns     short loc_180003991
0x180003957  test    edi, edi
0x180003959  jz      short loc_180003964
0x18000395b  mov     rcx, rsi; this
0x18000395e  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003963  nop
0x180003964  mov     eax, ebx
0x180003966  add     rsp, 48h
0x18000396a  pop     r15
0x18000396c  pop     r14
0x18000396e  pop     r12
0x180003970  pop     rdi
0x180003971  pop     rsi
0x180003972  pop     rbx
0x180003973  retn
0x180003974  lea     rcx, [rsp+78h+var_48]; this
0x180003979  call    ?Lock@CAutoReadLock@@QEAA_NXZ; CAutoReadLock::Lock(void)
0x18000397e  test    al, al
0x180003980  jz      loc_180003A74
0x180003986  mov     edi, [rsp+78h+var_40]
0x18000398a  mov     rsi, [rsp+78h+var_48]
0x18000398f  jmp     short loc_18000393F
0x180003991  mov     rax, [rsp+78h+arg_28]
0x180003999  mov     [rsp+78h+var_58], rax; struct IWmiDbHandle **
0x18000399e  mov     r9d, dword ptr [rsp+78h+arg_20]; unsigned int
0x1800039a6  mov     rdx, r15; struct IWbemPath *
0x1800039a9  mov     rcx, r14; this
0x1800039ac  call    ?GetObjectW@CNamespaceHandle@@QEAAJPEAUIWbemPath@@KKPEAPEAUIWmiDbHandle@@@Z; CNamespaceHandle::GetObjectW(IWbemPath *,ulong,ulong,IWmiDbHandle * *)
0x1800039b1  mov     ebx, eax
0x1800039b3  cmp     eax, 0FFFFFFFFh
0x1800039b6  jz      loc_180003B1C
0x1800039bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039c3  cmp     rcx, r12
0x1800039c6  jz      short loc_1800039CE
0x1800039c8  test    byte ptr [rcx+1Ch], 1
0x1800039cc  jnz     short loc_1800039F9
0x1800039ce  test    ebx, ebx
0x1800039d0  js      loc_180003B56
0x1800039d6  cmp     rcx, r12
0x1800039d9  jz      short loc_1800039E5
0x1800039db  test    byte ptr [rcx+1Ch], 1
0x1800039df  jnz     loc_180003B73
0x1800039e5  test    edi, edi
0x1800039e7  jz      short loc_1800039F2
0x1800039e9  mov     rcx, rsi; this
0x1800039ec  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x1800039f1  nop
0x1800039f2  mov     eax, ebx
0x1800039f4  jmp     loc_180003966
0x1800039f9  cmp     byte ptr [rcx+19h], 5
0x1800039fd  jb      short loc_1800039CE
0x1800039ff  mov     edx, 50h ; 'P'
0x180003a04  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003a0b  mov     rcx, [rcx+10h]
0x180003a0f  call    WPP_SF_
0x180003a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a1b  jmp     short loc_1800039CE
0x180003a1d  cmp     [rsp+78h+var_40], 0
0x180003a22  jz      short loc_180003A2F
0x180003a24  mov     rcx, [rsp+78h+var_48]; this
0x180003a29  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003a2e  nop
0x180003a2f  mov     eax, 80041001h
0x180003a34  jmp     loc_180003966
0x180003a39  test    edi, edi
0x180003a3b  jz      short loc_180003A46
0x180003a3d  mov     rcx, rsi; this
0x180003a40  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003a45  nop
0x180003a46  mov     eax, 80041033h
0x180003a4b  jmp     loc_180003966
0x180003a50  cmp     byte ptr [rcx+19h], 5
0x180003a54  jb      loc_180003924
0x180003a5a  mov     edx, 0Ah
0x180003a5f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003a66  mov     rcx, [rcx+10h]
0x180003a6a  call    WPP_SF_
0x180003a6f  jmp     loc_180003924
0x180003a74  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003a7a  mov     edx, 80041001h
0x180003a7f  mov     rcx, rax
0x180003a82  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a8f  cmp     rcx, r12
0x180003a92  jz      short loc_180003A1D
0x180003a94  test    byte ptr [rcx+1Ch], 1
0x180003a98  jz      short loc_180003A1D
0x180003a9a  cmp     byte ptr [rcx+19h], 2
0x180003a9e  jb      loc_180003A1D
0x180003aa4  mov     edx, 0Bh
0x180003aa9  mov     r9d, 80041001h
0x180003aaf  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003ab6  mov     rcx, [rcx+10h]
0x180003aba  call    WPP_SF_d
0x180003abf  jmp     loc_180003A1D
0x180003ac4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003aca  mov     edx, 80041033h
0x180003acf  mov     rcx, rax
0x180003ad2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003adf  cmp     rcx, r12
0x180003ae2  jz      loc_180003A39
0x180003ae8  test    byte ptr [rcx+1Ch], 1
0x180003aec  jz      loc_180003A39
0x180003af2  cmp     byte ptr [rcx+19h], 2
0x180003af6  jb      loc_180003A39
0x180003afc  mov     edx, 0Ch
0x180003b01  mov     r9d, 80041033h
0x180003b07  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003b0e  mov     rcx, [rcx+10h]
0x180003b12  call    WPP_SF_d
0x180003b17  jmp     loc_180003A39
0x180003b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b23  cmp     rcx, r12
0x180003b26  jz      short loc_180003B56
0x180003b28  test    byte ptr [rcx+1Ch], 8
0x180003b2c  jz      loc_1800039C3
0x180003b32  cmp     byte ptr [rcx+19h], 0
0x180003b36  jnz     loc_1800039C3
0x180003b3c  mov     edx, 0Dh
0x180003b41  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003b48  mov     rcx, [rcx+10h]
0x180003b4c  call    WPP_SF_
0x180003b51  jmp     loc_1800039BC
0x180003b56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003b5c  mov     edx, ebx
0x180003b5e  mov     rcx, rax
0x180003b61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b6e  jmp     loc_1800039D6
0x180003b73  cmp     byte ptr [rcx+19h], 2
0x180003b77  jb      loc_1800039E5
0x180003b7d  mov     edx, 0Eh
0x180003b82  mov     r9d, ebx
0x180003b85  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003b8c  mov     rcx, [rcx+10h]
0x180003b90  call    WPP_SF_d
0x180003b95  jmp     loc_1800039E5
0x180003b9a  mov     eax, 80041006h
0x180003b9f  jmp     loc_180003966
0x180003ba4  mov     eax, 8004100Ah
0x180003ba9  jmp     loc_180003966
```
