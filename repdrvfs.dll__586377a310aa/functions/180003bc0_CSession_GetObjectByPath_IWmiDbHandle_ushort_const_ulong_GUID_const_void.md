# CSession::GetObjectByPath(IWmiDbHandle *,ushort const *,ulong,_GUID const &,void * *)

- ea: `0x180003bc0`
- end: `0x180003f9c`
- name: `?GetObjectByPath@CSession@@UEAAJPEAUIWmiDbHandle@@PEBGKAEBU_GUID@@PEAPEAX@Z`
- size: `988`
- prototype: `__int64 __fastcall(CSession *this, struct IWmiDbHandle *, const unsigned __int16 *, __int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800013c8`
- `0x180003660`
- `0x180003bc0`
- `0x180003fb0`
- `0x1800040c0`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003cad`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003cad`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003d4f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003d88`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003d4f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003d88`
- `wbemcomn!GetMemLogObject` at `0x180003e3c`
- `wbemcomn!GetMemLogObject` at `0x180003e88`
- `wbemcomn!GetMemLogObject` at `0x180003ee0`
- `wbemcomn!GetMemLogObject` at `0x180003f44`
- `wbemcomn!GetMemLogObject` at `0x180003e3c`
- `wbemcomn!GetMemLogObject` at `0x180003e88`
- `wbemcomn!GetMemLogObject` at `0x180003ee0`
- `wbemcomn!GetMemLogObject` at `0x180003f44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003e4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003e96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003eee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003f4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003e4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003e96`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003eee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003f4f`

## pseudocode

```c
__int64 __fastcall CSession::GetObjectByPath(
        CSession *this,
        struct IWmiDbHandle *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        const struct _GUID *a5,
        void **a6)
{
  const unsigned __int16 *v6; // rbx
  CLock *v9; // rsi
  int v10; // r14d
  int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // rdi
  unsigned __int16 *v15; // rax
  int v16; // r8d
  unsigned __int16 *v17; // r12
  __int64 v18; // rcx
  unsigned __int16 v19; // dx
  unsigned __int16 *v20; // rcx
  int ObjectByPath; // ebx
  CVarObjHeap *v22; // rcx
  CMemoryLog *v23; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CLock *v29; // [rsp+30h] [rbp-38h] BYREF
  int v30; // [rsp+38h] [rbp-30h]

  try
  {
    v6 = a3;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, a3);
    }
    v9 = (CLock *)&g_readWriteLock;
    v29 = (CLock *)&g_readWriteLock;
    v10 = 0;
    v30 = 0;
    if ( *((_BYTE *)this + 168) )
      goto LABEL_4;
    if ( CAutoReadLock::Lock((CAutoReadLock *)&v29) )
    {
      v10 = v30;
      v9 = v29;
LABEL_4:
      if ( g_bShuttingDown )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217357);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749939LL);
        }
        if ( v10 )
          CLock::ReadUnlock(v9);
        return 2147749939LL;
      }
      else
      {
        v11 = *(_DWORD *)(*((_QWORD *)a2 + 11) + 48LL);
        if ( v11 >= 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v6[v13] );
          v14 = (unsigned int)(v13 + 1);
          v15 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v14, 2u));
          v17 = v15;
          if ( v15 )
          {
            if ( v14 )
            {
              if ( v14 > 0x7FFFFFFF )
              {
                *v15 = 0;
              }
              else
              {
                v18 = 2147483646;
                do
                {
                  if ( !v18 )
                    break;
                  v19 = *v6;
                  if ( !*v6 )
                    break;
                  ++v6;
                  *v15++ = v19;
                  --v18;
                  --v14;
                }
                while ( v14 );
                v20 = v15 - 1;
                if ( v14 )
                  v20 = v15;
                *v20 = 0;
              }
            }
            ObjectByPath = CNamespaceHandle::GetObjectByPath(a2, v17, v16, a5, a6);
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
              v22 = WPP_GLOBAL_Control;
            }
            if ( ObjectByPath == -2147217406 )
            {
              CWin32DefaultArena::WbemMemFree(v17);
              if ( v10 )
                CLock::ReadUnlock(v9);
              return 2147749890LL;
            }
            else
            {
              if ( ObjectByPath < 0 )
              {
                v26 = GetMemLogObject();
                CMemoryLog::Write(v26, ObjectByPath);
                v22 = WPP_GLOBAL_Control;
              }
              if ( v22 != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)v22 + 28) & 1) != 0
                && *((_BYTE *)v22 + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)v22 + 2),
                  27,
                  WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                  (unsigned int)ObjectByPath);
              }
              CWin32DefaultArena::WbemMemFree(v17);
              if ( v10 )
                CLock::ReadUnlock(v9);
              return (unsigned int)ObjectByPath;
            }
          }
          else
          {
            v25 = GetMemLogObject();
            CMemoryLog::Write(v25, -2147217402);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                2147749894LL);
            }
            if ( v10 )
              CLock::ReadUnlock(v9);
            return 2147749894LL;
          }
        }
        else
        {
          if ( v10 )
            CLock::ReadUnlock(v9);
          return (unsigned int)v11;
        }
      }
    }
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
    }
    if ( v30 )
      CLock::ReadUnlock(v29);
    result = 2147749889LL;
  }
  catch ( CX_MemoryException )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217398);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  v6 = a3;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_8], rbx
0x180003bc5  mov     [rsp+arg_10], rsi
0x180003bca  push    rdi
0x180003bcb  push    r12
0x180003bcd  push    r13
0x180003bcf  push    r14
0x180003bd1  push    r15
0x180003bd3  sub     rsp, 40h
0x180003bd7  mov     rbx, r8
0x180003bda  mov     r15, rdx
0x180003bdd  mov     rdi, rcx
0x180003be0  lea     r13, WPP_GLOBAL_Control
0x180003be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bee  cmp     rcx, r13
0x180003bf1  jnz     short loc_180003C57
0x180003bf3  lea     rsi, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x180003bfa  mov     [rsp+68h+var_38], rsi
0x180003bff  xor     r14d, r14d
0x180003c02  mov     [rsp+68h+var_30], r14d
0x180003c07  cmp     [rdi+0A8h], r14b
0x180003c0e  jz      loc_180003DA4
0x180003c14  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180003c1b  jnz     loc_180003E88
0x180003c21  mov     rax, [r15+58h]
0x180003c25  mov     edi, [rax+30h]
0x180003c28  test    edi, edi
0x180003c2a  jns     short loc_180003C80
0x180003c2c  test    r14d, r14d
0x180003c2f  jz      short loc_180003C3A
0x180003c31  mov     rcx, rsi; this
0x180003c34  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003c39  nop
0x180003c3a  mov     eax, edi
0x180003c3c  mov     rbx, [rsp+68h+arg_8]
0x180003c41  mov     rsi, [rsp+68h+arg_10]
0x180003c49  add     rsp, 40h
0x180003c4d  pop     r15
0x180003c4f  pop     r14
0x180003c51  pop     r13
0x180003c53  pop     r12
0x180003c55  pop     rdi
0x180003c56  retn
0x180003c57  test    byte ptr [rcx+1Ch], 1
0x180003c5b  jz      short loc_180003BF3
0x180003c5d  cmp     byte ptr [rcx+19h], 5
0x180003c61  jb      short loc_180003BF3
0x180003c63  mov     edx, 17h
0x180003c68  mov     r9, rbx
0x180003c6b  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003c72  mov     rcx, [rcx+10h]
0x180003c76  call    WPP_SF_S
0x180003c7b  jmp     loc_180003BF3
0x180003c80  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003c87  mov     rax, rcx
0x180003c8a  nop     word ptr [rax+rax+00h]
0x180003c90  lea     rax, [rax+1]
0x180003c94  cmp     word ptr [rbx+rax*2], 0
0x180003c99  jnz     short loc_180003C90
0x180003c9b  lea     edi, [rax+1]
0x180003c9e  mov     eax, 2
0x180003ca3  mul     rdi
0x180003ca6  cmovb   rax, rcx
0x180003caa  mov     rcx, rax
0x180003cad  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003cb3  mov     r12, rax
0x180003cb6  test    rax, rax
0x180003cb9  jz      loc_180003EE0
0x180003cbf  test    rdi, rdi
0x180003cc2  jz      short loc_180003D07
0x180003cc4  cmp     rdi, 7FFFFFFFh
0x180003ccb  ja      loc_180003F38
0x180003cd1  mov     ecx, 7FFFFFFEh
0x180003cd6  test    rcx, rcx
0x180003cd9  jz      short loc_180003CF7
0x180003cdb  movzx   edx, word ptr [rbx]
0x180003cde  test    dx, dx
0x180003ce1  jz      short loc_180003CF7
0x180003ce3  add     rbx, 2
0x180003ce7  mov     [rax], dx
0x180003cea  add     rax, 2
0x180003cee  dec     rcx
0x180003cf1  sub     rdi, 1
0x180003cf5  jnz     short loc_180003CD6
0x180003cf7  lea     rcx, [rax-2]
0x180003cfb  test    rdi, rdi
0x180003cfe  cmovnz  rcx, rax
0x180003d02  xor     eax, eax
0x180003d04  mov     [rcx], ax
0x180003d07  mov     [rsp+68h+arg_0], r12
0x180003d0c  mov     rax, [rsp+68h+arg_28]
0x180003d14  mov     [rsp+68h+var_48], rax; void **
0x180003d19  mov     r9, [rsp+68h+arg_20]; struct _GUID *
0x180003d21  mov     rdx, r12; unsigned __int16 *
0x180003d24  mov     rcx, r15; this
0x180003d27  call    ?GetObjectByPath@CNamespaceHandle@@QEAAJPEBGKAEBU_GUID@@PEAPEAX@Z; CNamespaceHandle::GetObjectByPath(ushort const *,ulong,_GUID const &,void * *)
0x180003d2c  mov     ebx, eax
0x180003d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d35  cmp     rcx, r13
0x180003d38  jz      short loc_180003D44
0x180003d3a  test    byte ptr [rcx+1Ch], 1
0x180003d3e  jnz     loc_180003DC5
0x180003d44  cmp     ebx, 80041002h
0x180003d4a  jnz     short loc_180003D6E
0x180003d4c  mov     rcx, r12
0x180003d4f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003d55  nop
0x180003d56  test    r14d, r14d
0x180003d59  jz      short loc_180003D64
0x180003d5b  mov     rcx, rsi; this
0x180003d5e  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003d63  nop
0x180003d64  mov     eax, 80041002h
0x180003d69  jmp     loc_180003C3C
0x180003d6e  test    ebx, ebx
0x180003d70  js      loc_180003F44
0x180003d76  cmp     rcx, r13
0x180003d79  jz      short loc_180003D85
0x180003d7b  test    byte ptr [rcx+1Ch], 1
0x180003d7f  jnz     loc_180003F61
0x180003d85  mov     rcx, r12
0x180003d88  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003d8e  nop
0x180003d8f  test    r14d, r14d
0x180003d92  jz      short loc_180003D9D
0x180003d94  mov     rcx, rsi; this
0x180003d97  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003d9c  nop
0x180003d9d  mov     eax, ebx
0x180003d9f  jmp     loc_180003C3C
0x180003da4  lea     rcx, [rsp+68h+var_38]; this
0x180003da9  call    ?Lock@CAutoReadLock@@QEAA_NXZ; CAutoReadLock::Lock(void)
0x180003dae  test    al, al
0x180003db0  jz      loc_180003E3C
0x180003db6  mov     r14d, [rsp+68h+var_30]
0x180003dbb  mov     rsi, [rsp+68h+var_38]
0x180003dc0  jmp     loc_180003C14
0x180003dc5  cmp     byte ptr [rcx+19h], 5
0x180003dc9  jb      loc_180003D44
0x180003dcf  mov     edx, 50h ; 'P'
0x180003dd4  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003ddb  mov     rcx, [rcx+10h]
0x180003ddf  call    WPP_SF_
0x180003de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003deb  jmp     loc_180003D44
0x180003df0  cmp     [rsp+68h+var_30], 0
0x180003df5  jz      short loc_180003E02
0x180003df7  mov     rcx, [rsp+68h+var_38]; this
0x180003dfc  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003e01  nop
0x180003e02  mov     eax, 80041001h
0x180003e07  jmp     loc_180003C3C
0x180003e0c  test    r14d, r14d
0x180003e0f  jz      short loc_180003E1A
0x180003e11  mov     rcx, rsi; this
0x180003e14  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003e19  nop
0x180003e1a  mov     eax, 80041033h
0x180003e1f  jmp     loc_180003C3C
0x180003e24  test    r14d, r14d
0x180003e27  jz      short loc_180003E32
0x180003e29  mov     rcx, rsi; this
0x180003e2c  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003e31  nop
0x180003e32  mov     eax, 80041006h
0x180003e37  jmp     loc_180003C3C
0x180003e3c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003e42  mov     edx, 80041001h
0x180003e47  mov     rcx, rax
0x180003e4a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e57  cmp     rcx, r13
0x180003e5a  jz      short loc_180003DF0
0x180003e5c  test    byte ptr [rcx+1Ch], 1
0x180003e60  jz      short loc_180003DF0
0x180003e62  cmp     byte ptr [rcx+19h], 2
0x180003e66  jb      short loc_180003DF0
0x180003e68  mov     edx, 18h
0x180003e6d  mov     r9d, 80041001h
0x180003e73  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003e7a  mov     rcx, [rcx+10h]
0x180003e7e  call    WPP_SF_d
0x180003e83  jmp     loc_180003DF0
0x180003e88  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003e8e  mov     edx, 80041033h
0x180003e93  mov     rcx, rax
0x180003e96  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ea3  cmp     rcx, r13
0x180003ea6  jz      loc_180003E0C
0x180003eac  test    byte ptr [rcx+1Ch], 1
0x180003eb0  jz      loc_180003E0C
0x180003eb6  cmp     byte ptr [rcx+19h], 2
0x180003eba  jb      loc_180003E0C
0x180003ec0  mov     edx, 19h
0x180003ec5  mov     r9d, 80041033h
0x180003ecb  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003ed2  mov     rcx, [rcx+10h]
0x180003ed6  call    WPP_SF_d
0x180003edb  jmp     loc_180003E0C
0x180003ee0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003ee6  mov     edx, 80041006h
0x180003eeb  mov     rcx, rax
0x180003eee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003efb  cmp     rcx, r13
0x180003efe  jz      loc_180003E24
0x180003f04  test    byte ptr [rcx+1Ch], 1
0x180003f08  jz      loc_180003E24
0x180003f0e  cmp     byte ptr [rcx+19h], 2
0x180003f12  jb      loc_180003E24
0x180003f18  mov     edx, 1Ah
0x180003f1d  mov     r9d, 80041006h
0x180003f23  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003f2a  mov     rcx, [rcx+10h]
0x180003f2e  call    WPP_SF_d
0x180003f33  jmp     loc_180003E24
0x180003f38  xor     eax, eax
0x180003f3a  mov     [r12], ax
0x180003f3f  jmp     loc_180003D07
0x180003f44  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003f4a  mov     edx, ebx
0x180003f4c  mov     rcx, rax
0x180003f4f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f5c  jmp     loc_180003D76
0x180003f61  cmp     byte ptr [rcx+19h], 2
0x180003f65  jb      loc_180003D85
0x180003f6b  mov     edx, 1Bh
0x180003f70  mov     r9d, ebx
0x180003f73  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003f7a  mov     rcx, [rcx+10h]
0x180003f7e  call    WPP_SF_d
0x180003f83  jmp     loc_180003D85
0x180003f88  mov     eax, 80041006h
0x180003f8d  jmp     loc_180003C3C
0x180003f92  mov     eax, 8004100Ah
0x180003f97  jmp     loc_180003C3C
```
