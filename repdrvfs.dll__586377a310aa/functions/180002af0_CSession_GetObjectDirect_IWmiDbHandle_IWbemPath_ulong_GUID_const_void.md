# CSession::GetObjectDirect(IWmiDbHandle *,IWbemPath *,ulong,_GUID const &,void * *)

- ea: `0x180002af0`
- end: `0x180002f46`
- name: `?GetObjectDirect@CSession@@UEAAJPEAUIWmiDbHandle@@PEAUIWbemPath@@KAEBU_GUID@@PEAPEAX@Z`
- size: `1110`
- prototype: `__int64 __fastcall(CSession *this, struct IWmiDbHandle *, struct IWbemPath *, __int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x1800013a0`
- `0x180002af0`
- `0x180003660`
- `0x180003fb0`
- `0x1800040c0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002bd4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180002bd4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002c37`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002ee5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002c37`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002ee5`
- `wbemcomn!GetMemLogObject` at `0x180002d85`
- `wbemcomn!GetMemLogObject` at `0x180002dd7`
- `wbemcomn!GetMemLogObject` at `0x180002e38`
- `wbemcomn!GetMemLogObject` at `0x180002e99`
- `wbemcomn!GetMemLogObject` at `0x180002ef1`
- `wbemcomn!GetMemLogObject` at `0x180002d85`
- `wbemcomn!GetMemLogObject` at `0x180002dd7`
- `wbemcomn!GetMemLogObject` at `0x180002e38`
- `wbemcomn!GetMemLogObject` at `0x180002e99`
- `wbemcomn!GetMemLogObject` at `0x180002ef1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002d95`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002de7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002e48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002ea4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002efc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002d95`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002de7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002e48`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002ea4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180002efc`

## pseudocode

```c
__int64 __fastcall CSession::GetObjectDirect(
        CSession *this,
        struct IWmiDbHandle *a2,
        struct IWbemPath *a3,
        __int64 a4,
        const struct _GUID *a5,
        void **a6)
{
  CVarObjHeap *v9; // rcx
  CLock *v10; // rsi
  int v11; // r14d
  int v12; // ebx
  __int64 result; // rax
  void *v14; // rax
  void *v15; // r15
  int ObjectByPath; // ebx
  int v17; // r8d
  CVarObjHeap *v18; // rcx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CLock *v26; // [rsp+38h] [rbp-50h] BYREF
  int v27; // [rsp+40h] [rbp-48h]
  unsigned int v28; // [rsp+90h] [rbp+8h] BYREF

  try
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    v10 = (CLock *)&g_readWriteLock;
    v26 = (CLock *)&g_readWriteLock;
    v11 = 0;
    v27 = 0;
    if ( !*((_BYTE *)this + 168) )
    {
      if ( !CAutoReadLock::Lock((CAutoReadLock *)&v26) )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217407);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749889LL);
        }
        if ( v27 )
          CLock::ReadUnlock(v26);
        return 2147749889LL;
      }
      v11 = v27;
      v10 = v26;
      v9 = WPP_GLOBAL_Control;
    }
    if ( !g_bShuttingDown )
    {
      v12 = *(_DWORD *)(*((_QWORD *)a2 + 11) + 48LL);
      if ( v12 < 0 )
      {
        if ( v11 )
          CLock::ReadUnlock(v10);
        return (unsigned int)v12;
      }
      if ( v9 != (CVarObjHeap *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
        WPP_SF_q(*((_QWORD *)v9 + 2), 129, a3, a3);
      v28 = 0;
      ((void (__fastcall *)(struct IWbemPath *, __int64, unsigned int *))a3->lpVtbl->GetText)(a3, 32, &v28);
      v14 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v28, 2u));
      v15 = v14;
      if ( v14 )
      {
        ObjectByPath = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, unsigned int *, void *))a3->lpVtbl->GetText)(
                         a3,
                         32,
                         &v28,
                         v14);
        if ( ObjectByPath < 0 )
        {
          v22 = GetMemLogObject();
          CMemoryLog::Write(v22, ObjectByPath);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              131,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              (unsigned int)ObjectByPath);
          }
          CWin32DefaultArena::WbemMemFree(v15);
        }
        else
        {
          ObjectByPath = CNamespaceHandle::GetObjectByPath(a2, (const unsigned __int16 *)v15, v17, a5, a6);
          CWin32DefaultArena::WbemMemFree(v15);
        }
      }
      else
      {
        v21 = GetMemLogObject();
        ObjectByPath = -2147217402;
        CMemoryLog::Write(v21, -2147217402);
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_15;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          130,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      v18 = WPP_GLOBAL_Control;
LABEL_15:
      if ( v18 != (CVarObjHeap *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)v18 + 2), 80, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      if ( ObjectByPath == -2147217406 )
      {
        if ( v11 )
          CLock::ReadUnlock(v10);
        return 2147749890LL;
      }
      else
      {
        if ( ObjectByPath < 0 )
        {
          v23 = GetMemLogObject();
          CMemoryLog::Write(v23, ObjectByPath);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 != (CVarObjHeap *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)v18 + 2),
            20,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)ObjectByPath);
        if ( v11 )
          CLock::ReadUnlock(v10);
        return (unsigned int)ObjectByPath;
      }
    }
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217357);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
    }
    if ( v11 )
      CLock::ReadUnlock(v10);
    result = 2147749939LL;
  }
  catch ( CX_MemoryException )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, -2147217398);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  v9 = WPP_GLOBAL_Control;
}

```

## disassembly

```asm
0x180002af0  push    rbx
0x180002af2  push    rsi
0x180002af3  push    r12
0x180002af5  push    r13
0x180002af7  push    r14
0x180002af9  push    r15
0x180002afb  sub     rsp, 58h
0x180002aff  mov     r12, r8
0x180002b02  mov     r13, rdx
0x180002b05  mov     rbx, rcx
0x180002b08  lea     rax, WPP_GLOBAL_Control
0x180002b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b16  cmp     rcx, rax
0x180002b19  jz      short loc_180002B25
0x180002b1b  test    byte ptr [rcx+1Ch], 1
0x180002b1f  jnz     loc_180002D01
0x180002b25  lea     rsi, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x180002b2c  mov     [rsp+88h+var_50], rsi
0x180002b31  xor     r15d, r15d
0x180002b34  mov     r14d, r15d
0x180002b37  mov     [rsp+88h+var_48], r15d
0x180002b3c  cmp     [rbx+0A8h], r15b
0x180002b43  jz      loc_180002C99
0x180002b49  cmp     cs:?g_bShuttingDown@@3_NA, r15b; bool g_bShuttingDown
0x180002b50  jnz     loc_180002DD7
0x180002b56  mov     rax, [r13+58h]
0x180002b5a  mov     ebx, [rax+30h]
0x180002b5d  test    ebx, ebx
0x180002b5f  jns     short loc_180002B80
0x180002b61  test    r14d, r14d
0x180002b64  jz      short loc_180002B6F
0x180002b66  mov     rcx, rsi; this
0x180002b69  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180002b6e  nop
0x180002b6f  mov     eax, ebx
0x180002b71  add     rsp, 58h
0x180002b75  pop     r15
0x180002b77  pop     r14
0x180002b79  pop     r13
0x180002b7b  pop     r12
0x180002b7d  pop     rsi
0x180002b7e  pop     rbx
0x180002b7f  retn
0x180002b80  lea     rax, WPP_GLOBAL_Control
0x180002b87  cmp     rcx, rax
0x180002b8a  jnz     loc_180002CD7
0x180002b90  mov     [rsp+88h+arg_0], r15d
0x180002b98  mov     rax, [r12]
0x180002b9c  xor     r9d, r9d
0x180002b9f  lea     r8, [rsp+88h+arg_0]
0x180002ba7  lea     ebx, [r9+20h]
0x180002bab  mov     edx, ebx
0x180002bad  mov     rcx, r12
0x180002bb0  mov     rax, [rax+20h]
0x180002bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb9  mov     ecx, [rsp+88h+arg_0]
0x180002bc0  lea     eax, [rbx-1Eh]
0x180002bc3  mul     rcx
0x180002bc6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002bcd  cmovb   rax, rcx
0x180002bd1  mov     rcx, rax
0x180002bd4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180002bda  mov     r15, rax
0x180002bdd  test    rax, rax
0x180002be0  jz      loc_180002E38
0x180002be6  mov     [rsp+88h+var_58], rax
0x180002beb  mov     rax, [r12]
0x180002bef  mov     r9, r15
0x180002bf2  lea     r8, [rsp+88h+arg_0]
0x180002bfa  mov     edx, ebx
0x180002bfc  mov     rcx, r12
0x180002bff  mov     rax, [rax+20h]
0x180002c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c08  mov     ebx, eax
0x180002c0a  test    eax, eax
0x180002c0c  js      loc_180002E99
0x180002c12  mov     rax, [rsp+88h+arg_28]
0x180002c1a  mov     [rsp+88h+var_68], rax; void **
0x180002c1f  mov     r9, [rsp+88h+arg_20]; struct _GUID *
0x180002c27  mov     rdx, r15; unsigned __int16 *
0x180002c2a  mov     rcx, r13; this
0x180002c2d  call    ?GetObjectByPath@CNamespaceHandle@@QEAAJPEBGKAEBU_GUID@@PEAPEAX@Z; CNamespaceHandle::GetObjectByPath(ushort const *,ulong,_GUID const &,void * *)
0x180002c32  mov     ebx, eax
0x180002c34  mov     rcx, r15
0x180002c37  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180002c3d  nop
0x180002c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c45  lea     rax, WPP_GLOBAL_Control
0x180002c4c  cmp     rcx, rax
0x180002c4f  jz      short loc_180002C5B
0x180002c51  test    byte ptr [rcx+1Ch], 1
0x180002c55  jnz     loc_180002D2C
0x180002c5b  mov     r15d, 80041002h
0x180002c61  cmp     ebx, r15d
0x180002c64  jz      short loc_180002CC1
0x180002c66  test    ebx, ebx
0x180002c68  js      loc_180002EF1
0x180002c6e  lea     rax, WPP_GLOBAL_Control
0x180002c75  cmp     rcx, rax
0x180002c78  jz      short loc_180002C84
0x180002c7a  test    byte ptr [rcx+1Ch], 1
0x180002c7e  jnz     loc_180002F0E
0x180002c84  test    r14d, r14d
0x180002c87  jz      short loc_180002C92
0x180002c89  mov     rcx, rsi; this
0x180002c8c  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180002c91  nop
0x180002c92  mov     eax, ebx
0x180002c94  jmp     loc_180002B71
0x180002c99  lea     rcx, [rsp+88h+var_50]; this
0x180002c9e  call    ?Lock@CAutoReadLock@@QEAA_NXZ; CAutoReadLock::Lock(void)
0x180002ca3  test    al, al
0x180002ca5  jz      loc_180002D85
0x180002cab  mov     r14d, [rsp+88h+var_48]
0x180002cb0  mov     rsi, [rsp+88h+var_50]
0x180002cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cbc  jmp     loc_180002B49
0x180002cc1  test    r14d, r14d
0x180002cc4  jz      short loc_180002CCF
0x180002cc6  mov     rcx, rsi; this
0x180002cc9  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180002cce  nop
0x180002ccf  mov     eax, r15d
0x180002cd2  jmp     loc_180002B71
0x180002cd7  test    byte ptr [rcx+1Ch], 1
0x180002cdb  jz      loc_180002B90
0x180002ce1  cmp     byte ptr [rcx+19h], 5
0x180002ce5  jb      loc_180002B90
0x180002ceb  mov     edx, 81h
0x180002cf0  mov     r9, r12
0x180002cf3  mov     rcx, [rcx+10h]
0x180002cf7  call    WPP_SF_q
0x180002cfc  jmp     loc_180002B90
0x180002d01  cmp     byte ptr [rcx+19h], 5
0x180002d05  jb      loc_180002B25
0x180002d0b  mov     edx, 11h
0x180002d10  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002d17  mov     rcx, [rcx+10h]
0x180002d1b  call    WPP_SF_
0x180002d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d27  jmp     loc_180002B25
0x180002d2c  cmp     byte ptr [rcx+19h], 5
0x180002d30  jb      loc_180002C5B
0x180002d36  mov     edx, 50h ; 'P'
0x180002d3b  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002d42  mov     rcx, [rcx+10h]
0x180002d46  call    WPP_SF_
0x180002d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d52  jmp     loc_180002C5B
0x180002d57  cmp     [rsp+88h+var_48], r15d
0x180002d5c  jz      short loc_180002D69
0x180002d5e  mov     rcx, [rsp+88h+var_50]; this
0x180002d63  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180002d68  nop
0x180002d69  mov     eax, ebx
0x180002d6b  jmp     loc_180002B71
0x180002d70  test    r14d, r14d
0x180002d73  jz      short loc_180002D7E
0x180002d75  mov     rcx, rsi; this
0x180002d78  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180002d7d  nop
0x180002d7e  mov     eax, ebx
0x180002d80  jmp     loc_180002B71
0x180002d85  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002d8b  mov     ebx, 80041001h
0x180002d90  mov     edx, ebx
0x180002d92  mov     rcx, rax
0x180002d95  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002da2  lea     rax, WPP_GLOBAL_Control
0x180002da9  cmp     rcx, rax
0x180002dac  jz      short loc_180002D57
0x180002dae  test    byte ptr [rcx+1Ch], 1
0x180002db2  jz      short loc_180002D57
0x180002db4  cmp     byte ptr [rcx+19h], 2
0x180002db8  jb      short loc_180002D57
0x180002dba  mov     edx, 12h
0x180002dbf  mov     r9d, 80041001h
0x180002dc5  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002dcc  mov     rcx, [rcx+10h]
0x180002dd0  call    WPP_SF_d
0x180002dd5  jmp     short loc_180002D57
0x180002dd7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002ddd  mov     ebx, 80041033h
0x180002de2  mov     edx, ebx
0x180002de4  mov     rcx, rax
0x180002de7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df4  lea     rax, WPP_GLOBAL_Control
0x180002dfb  cmp     rcx, rax
0x180002dfe  jz      loc_180002D70
0x180002e04  test    byte ptr [rcx+1Ch], 1
0x180002e08  jz      loc_180002D70
0x180002e0e  cmp     byte ptr [rcx+19h], 2
0x180002e12  jb      loc_180002D70
0x180002e18  mov     edx, 13h
0x180002e1d  mov     r9d, 80041033h
0x180002e23  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002e2a  mov     rcx, [rcx+10h]
0x180002e2e  call    WPP_SF_d
0x180002e33  jmp     loc_180002D70
0x180002e38  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002e3e  mov     ebx, 80041006h
0x180002e43  mov     edx, ebx
0x180002e45  mov     rcx, rax
0x180002e48  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e55  lea     rax, WPP_GLOBAL_Control
0x180002e5c  cmp     rcx, rax
0x180002e5f  jz      loc_180002C45
0x180002e65  test    byte ptr [rcx+1Ch], 1
0x180002e69  jz      loc_180002C45
0x180002e6f  cmp     byte ptr [rcx+19h], 2
0x180002e73  jb      loc_180002C45
0x180002e79  mov     edx, 82h
0x180002e7e  mov     r9d, 80041006h
0x180002e84  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002e8b  mov     rcx, [rcx+10h]
0x180002e8f  call    WPP_SF_d
0x180002e94  jmp     loc_180002C3E
0x180002e99  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002e9f  mov     edx, ebx
0x180002ea1  mov     rcx, rax
0x180002ea4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb1  lea     rax, WPP_GLOBAL_Control
0x180002eb8  cmp     rcx, rax
0x180002ebb  jz      short loc_180002EE2
0x180002ebd  test    byte ptr [rcx+1Ch], 1
0x180002ec1  jz      short loc_180002EE2
0x180002ec3  cmp     byte ptr [rcx+19h], 2
0x180002ec7  jb      short loc_180002EE2
0x180002ec9  mov     edx, 83h
0x180002ece  mov     r9d, ebx
0x180002ed1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002ed8  mov     rcx, [rcx+10h]
0x180002edc  call    WPP_SF_d
0x180002ee1  nop
0x180002ee2  mov     rcx, r15
0x180002ee5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180002eeb  nop
0x180002eec  jmp     loc_180002C3E
0x180002ef1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180002ef7  mov     edx, ebx
0x180002ef9  mov     rcx, rax
0x180002efc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180002f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f09  jmp     loc_180002C6E
0x180002f0e  cmp     byte ptr [rcx+19h], 2
0x180002f12  jb      loc_180002C84
0x180002f18  mov     edx, 14h
0x180002f1d  mov     r9d, ebx
0x180002f20  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180002f27  mov     rcx, [rcx+10h]
0x180002f2b  call    WPP_SF_d
0x180002f30  jmp     loc_180002C84
0x180002f35  mov     eax, 80041006h
0x180002f3a  jmp     short loc_180002F41
0x180002f3c  mov     eax, 8004100Ah
0x180002f41  jmp     loc_180002B71
```
