# CNamespaceHandle::FileToInstance(_IWmiObject *,ushort const *,uchar *,ulong,_IWmiObject * *,bool)

- ea: `0x18000b260`
- end: `0x18000b644`
- name: `?FileToInstance@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBGPEAEKPEAPEAU2@_N@Z`
- size: `996`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct _IWmiObject *, const unsigned __int16 *, unsigned __int8 *, unsigned int, struct _IWmiObject **)`
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004f30`
- `0x180008730`
- `0x18000a9b0`
- `0x180014290`
- `0x1800332dc`
- `0x1800345c0`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000a350`
- `0x18000b260`
- `0x18000b650`
- `0x18000bf70`
- `0x18001e134`
- `0x180026124`
- `0x180044420`
- `0x180048010`

## import_xrefs

- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18000b380`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18000b380`
- `wbemcomn!GetMemLogObject` at `0x18000b4f2`
- `wbemcomn!GetMemLogObject` at `0x18000b55d`
- `wbemcomn!GetMemLogObject` at `0x18000b5ea`
- `wbemcomn!GetMemLogObject` at `0x18000b4f2`
- `wbemcomn!GetMemLogObject` at `0x18000b55d`
- `wbemcomn!GetMemLogObject` at `0x18000b5ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b4fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b56b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b5f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b4fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b56b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b5f5`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::FileToInstance(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct _IWmiObject **a6)
{
  struct _IWmiObject *v8; // r13
  CNamespaceHandle *v9; // r10
  struct MemoryPage *v10; // r15
  unsigned __int8 *v11; // r12
  unsigned int v12; // r14d
  unsigned __int8 *v13; // rbx
  unsigned __int8 *v14; // rsi
  __int64 (__fastcall *v15)(struct _IWmiObject *, __int64, _QWORD, unsigned __int8 *, int *, __int64, struct _IWmiObject **); // rdi
  __int64 v16; // rax
  int v17; // edi
  unsigned int v19; // eax
  int ClassByHash; // ebx
  CMemoryLog *v21; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v23; // rax
  bool v24; // [rsp+40h] [rbp-C0h] BYREF
  bool v25; // [rsp+41h] [rbp-BFh] BYREF
  struct MemoryPage *v26; // [rsp+48h] [rbp-B8h] BYREF
  CNamespaceHandle *v27; // [rsp+50h] [rbp-B0h]
  unsigned __int8 *v28; // [rsp+58h] [rbp-A8h] BYREF
  struct _IWmiObject *v29; // [rsp+60h] [rbp-A0h] BYREF
  struct _IWmiObject *v30; // [rsp+68h] [rbp-98h] BYREF
  struct _IWmiObject **v31; // [rsp+70h] [rbp-90h]
  _BYTE v32[8]; // [rsp+78h] [rbp-88h] BYREF
  void (__fastcall *v33)(struct MemoryPage *, unsigned __int8 *); // [rsp+80h] [rbp-80h]
  struct MemoryPage *v34; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v35; // [rsp+90h] [rbp-70h]
  unsigned __int16 v36[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+C0h] [rbp-40h]
  __int128 v39; // [rsp+D0h] [rbp-30h]
  __int128 v40; // [rsp+E0h] [rbp-20h]
  __int128 v41; // [rsp+F0h] [rbp-10h]
  __int128 v42; // [rsp+100h] [rbp+0h]
  __int128 v43; // [rsp+110h] [rbp+10h]
  __int16 v44; // [rsp+120h] [rbp+20h]

  v8 = a2;
  v9 = this;
  v27 = this;
  v31 = a6;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
    v9 = v27;
  }
  v28 = 0;
  v10 = 0;
  v26 = 0;
  v11 = 0;
  if ( !a4 )
  {
    if ( !dword_180058AFC || g_bShuttingDown )
    {
      v19 = 1255;
    }
    else
    {
      v19 = CObjectHeap::ReadObject((CObjectHeap *)&qword_180058EF8, a3, &a5, &v28, &v26);
      if ( !v19 )
      {
        a4 = v28;
        v11 = v28;
        v10 = v26;
        v9 = v27;
        goto LABEL_4;
      }
    }
    return A51TranslateErrorCode(v19, (__int64)a2, (__int64)a3);
  }
LABEL_4:
  v32[0] = 0;
  v33 = CleanupReadObjectMemory;
  v34 = v10;
  v35 = v11;
  v12 = a5;
  if ( a5 <= 8 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>::~ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>(v32);
    return 2147749894LL;
  }
  else
  {
    *(_OWORD *)v36 = *(_OWORD *)a4;
    v37 = *((_OWORD *)a4 + 1);
    v38 = *((_OWORD *)a4 + 2);
    v39 = *((_OWORD *)a4 + 3);
    v40 = *((_OWORD *)a4 + 4);
    v41 = *((_OWORD *)a4 + 5);
    v42 = *((_OWORD *)a4 + 6);
    v43 = *((_OWORD *)a4 + 7);
    v44 = 0;
    v13 = 0;
    v29 = 0;
    if ( v8 )
      goto LABEL_6;
    v26 = 0;
    v24 = 0;
    ClassByHash = CNamespaceHandle::GetClassByHash(v9, v36, 0, &v29, (__int64 *)&v26, &v25, &v24, 0);
    if ( ClassByHash >= 0 )
    {
      v13 = (unsigned __int8 *)v29;
      v8 = v29;
      v9 = v27;
LABEL_6:
      v14 = a4 + 144;
      v28 = v13;
      v30 = 0;
      v15 = *(__int64 (__fastcall **)(struct _IWmiObject *, __int64, _QWORD, unsigned __int8 *, int *, __int64, struct _IWmiObject **))(*(_QWORD *)v8 + 768LL);
      v16 = WString::operator unsigned short *((char *)v9 + 32);
      v17 = v15(v8, 1, v12 - 144, v14, &dword_1800599AC, v16, &v30);
      if ( v17 < 0 )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, v17);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            158,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)v17);
        }
        if ( v13 )
          (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v13 + 16LL))(v13);
        ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>::~ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>(v32);
        return (unsigned int)v17;
      }
      else
      {
        *v31 = v30;
        if ( v13 )
          (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v13 + 16LL))(v13);
        CleanupReadObjectMemory(v10, v11);
        return 0;
      }
    }
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, ClassByHash);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)ClassByHash);
    }
    CleanupReadObjectMemory(v10, v11);
    return (unsigned int)ClassByHash;
  }
}

```

## disassembly

```asm
0x18000b260  push    rbp
0x18000b262  push    rbx
0x18000b263  push    rsi
0x18000b264  push    rdi
0x18000b265  push    r12
0x18000b267  push    r13
0x18000b269  push    r14
0x18000b26b  push    r15
0x18000b26d  lea     rbp, [rsp-48h]
0x18000b272  sub     rsp, 148h
0x18000b279  mov     rax, cs:__security_cookie
0x18000b280  xor     rax, rsp
0x18000b283  mov     [rbp+80h+var_50], rax
0x18000b287  mov     rdi, r9
0x18000b28a  mov     rbx, r8
0x18000b28d  mov     r13, rdx
0x18000b290  mov     r10, rcx
0x18000b293  mov     [rsp+180h+var_130], rcx
0x18000b298  mov     rax, [rbp+80h+arg_28]
0x18000b29f  mov     [rsp+180h+var_110], rax
0x18000b2a4  lea     rsi, WPP_GLOBAL_Control
0x18000b2ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2b2  cmp     rcx, rsi
0x18000b2b5  jz      short loc_18000B2C1
0x18000b2b7  test    byte ptr [rcx+1Ch], 1
0x18000b2bb  jnz     loc_18000B4C9
0x18000b2c1  xor     ecx, ecx
0x18000b2c3  mov     [rsp+180h+var_128], rcx
0x18000b2c8  mov     r15d, ecx
0x18000b2cb  mov     [rsp+180h+var_138], rcx
0x18000b2d0  mov     r12d, ecx
0x18000b2d3  test    rdi, rdi
0x18000b2d6  jz      loc_18000B411
0x18000b2dc  mov     [rsp+180h+var_108], 0
0x18000b2e1  lea     rax, ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x18000b2e8  mov     [rbp+80h+var_100], rax
0x18000b2ec  mov     [rbp+80h+var_F8], r15
0x18000b2f0  mov     [rbp+80h+var_F0], r12
0x18000b2f4  mov     r14d, [rbp+80h+arg_20]
0x18000b2fb  cmp     r14d, 8
0x18000b2ff  jbe     loc_18000B55D
0x18000b305  movups  xmm0, xmmword ptr [rdi]
0x18000b308  movaps  xmmword ptr [rbp+80h+var_E0], xmm0
0x18000b30c  movups  xmm1, xmmword ptr [rdi+10h]
0x18000b310  movaps  [rbp+80h+var_D0], xmm1
0x18000b314  movups  xmm0, xmmword ptr [rdi+20h]
0x18000b318  movaps  [rbp+80h+var_C0], xmm0
0x18000b31c  movups  xmm1, xmmword ptr [rdi+30h]
0x18000b320  movaps  [rbp+80h+var_B0], xmm1
0x18000b324  movups  xmm0, xmmword ptr [rdi+40h]
0x18000b328  movaps  [rbp+80h+var_A0], xmm0
0x18000b32c  movups  xmm1, xmmword ptr [rdi+50h]
0x18000b330  movaps  [rbp+80h+var_90], xmm1
0x18000b334  movups  xmm0, xmmword ptr [rdi+60h]
0x18000b338  movaps  [rbp+80h+var_80], xmm0
0x18000b33c  movups  xmm1, xmmword ptr [rdi+70h]
0x18000b340  movaps  [rbp+80h+var_70], xmm1
0x18000b344  mov     [rbp+80h+var_60], cx
0x18000b348  mov     rbx, rcx
0x18000b34b  mov     [rsp+180h+var_120], rcx
0x18000b350  test    r13, r13
0x18000b353  jz      loc_18000B46F
0x18000b359  add     r14d, 0FFFFFF70h
0x18000b360  lea     rsi, [rdi+90h]
0x18000b367  mov     [rsp+180h+var_128], rbx
0x18000b36c  mov     [rsp+180h+var_118], rcx
0x18000b371  mov     rax, [r13+0]
0x18000b375  mov     rdi, [rax+300h]
0x18000b37c  lea     rcx, [r10+20h]
0x18000b380  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18000b386  lea     rcx, [rsp+180h+var_118]
0x18000b38b  mov     [rsp+180h+var_150], rcx
0x18000b390  mov     [rsp+180h+var_158], rax
0x18000b395  lea     rax, dword_1800599AC
0x18000b39c  mov     [rsp+180h+var_160], rax
0x18000b3a1  mov     r9, rsi
0x18000b3a4  mov     r8d, r14d
0x18000b3a7  mov     edx, 1
0x18000b3ac  mov     rcx, r13
0x18000b3af  mov     rax, rdi
0x18000b3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b7  mov     edi, eax
0x18000b3b9  test    eax, eax
0x18000b3bb  js      loc_18000B5EA
0x18000b3c1  mov     rax, [rsp+180h+var_118]
0x18000b3c6  mov     rcx, [rsp+180h+var_110]
0x18000b3cb  mov     [rcx], rax
0x18000b3ce  test    rbx, rbx
0x18000b3d1  jz      short loc_18000B3E3
0x18000b3d3  mov     rax, [rbx]
0x18000b3d6  mov     rcx, rbx
0x18000b3d9  mov     rax, [rax+10h]
0x18000b3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e2  nop
0x18000b3e3  mov     rdx, r12; unsigned __int8 *
0x18000b3e6  mov     rcx, r15; struct MemoryPage *
0x18000b3e9  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x18000b3ee  nop
0x18000b3ef  xor     eax, eax
0x18000b3f1  mov     rcx, [rbp+80h+var_50]
0x18000b3f5  xor     rcx, rsp; StackCookie
0x18000b3f8  call    __security_check_cookie
0x18000b3fd  add     rsp, 148h
0x18000b404  pop     r15
0x18000b406  pop     r14
0x18000b408  pop     r13
0x18000b40a  pop     r12
0x18000b40c  pop     rdi
0x18000b40d  pop     rsi
0x18000b40e  pop     rbx
0x18000b40f  pop     rbp
0x18000b410  retn
0x18000b411  cmp     cs:dword_180058AFC, ecx
0x18000b417  jz      loc_18000B54C
0x18000b41d  cmp     cs:?g_bShuttingDown@@3_NA, cl; bool g_bShuttingDown
0x18000b423  jnz     loc_18000B54C
0x18000b429  lea     rax, [rsp+180h+var_138]
0x18000b42e  mov     [rsp+180h+var_160], rax; struct MemoryPage **
0x18000b433  lea     r9, [rsp+180h+var_128]; unsigned __int8 **
0x18000b438  lea     r8, [rbp+80h+arg_20]; unsigned int *
0x18000b43f  mov     rdx, rbx; unsigned __int16 *
0x18000b442  lea     rcx, qword_180058EF8; this
0x18000b449  call    ?ReadObject@CObjectHeap@@QEAAJPEBGPEAKPEAPEAEPEAPEAVMemoryPage@@@Z; CObjectHeap::ReadObject(ushort const *,ulong *,uchar * *,MemoryPage * *)
0x18000b44e  test    eax, eax
0x18000b450  jnz     loc_18000B551
0x18000b456  mov     rdi, [rsp+180h+var_128]
0x18000b45b  mov     r12, rdi
0x18000b45e  mov     r15, [rsp+180h+var_138]
0x18000b463  mov     r10, [rsp+180h+var_130]
0x18000b468  xor     ecx, ecx
0x18000b46a  jmp     loc_18000B2DC
0x18000b46f  mov     [rsp+180h+var_138], rcx
0x18000b474  mov     [rsp+180h+var_140], 0
0x18000b479  mov     [rsp+180h+var_148], ecx; unsigned int
0x18000b47d  lea     rax, [rsp+180h+var_140]
0x18000b482  mov     [rsp+180h+var_150], rax; bool *
0x18000b487  lea     rax, [rsp+180h+var_13F]
0x18000b48c  mov     [rsp+180h+var_158], rax; bool *
0x18000b491  lea     rax, [rsp+180h+var_138]
0x18000b496  mov     [rsp+180h+var_160], rax; __int64 *
0x18000b49b  lea     r9, [rsp+180h+var_120]; struct _IWmiObject **
0x18000b4a0  xor     r8d, r8d; bool
0x18000b4a3  lea     rdx, [rbp+80h+var_E0]; unsigned __int16 *
0x18000b4a7  mov     rcx, r10; this
0x18000b4aa  call    ?GetClassByHash@CNamespaceHandle@@IEAAJPEBG_NPEAPEAU_IWmiObject@@PEA_JPEA_N4K@Z; CNamespaceHandle::GetClassByHash(ushort const *,bool,_IWmiObject * *,__int64 *,bool *,bool *,ulong)
0x18000b4af  mov     ebx, eax
0x18000b4b1  test    eax, eax
0x18000b4b3  js      short loc_18000B4F2
0x18000b4b5  mov     rbx, [rsp+180h+var_120]
0x18000b4ba  mov     r13, rbx
0x18000b4bd  mov     r10, [rsp+180h+var_130]
0x18000b4c2  xor     ecx, ecx
0x18000b4c4  jmp     loc_18000B359
0x18000b4c9  cmp     byte ptr [rcx+19h], 5
0x18000b4cd  jb      loc_18000B2C1
0x18000b4d3  mov     edx, 9Bh
0x18000b4d8  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000b4df  mov     rcx, [rcx+10h]
0x18000b4e3  call    WPP_SF_
0x18000b4e8  mov     r10, [rsp+180h+var_130]
0x18000b4ed  jmp     loc_18000B2C1
0x18000b4f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b4f8  mov     edx, ebx
0x18000b4fa  mov     rcx, rax
0x18000b4fd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b503  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b50a  cmp     rcx, rsi
0x18000b50d  jnz     loc_18000B5B9
0x18000b513  mov     rdx, r12; unsigned __int8 *
0x18000b516  mov     rcx, r15; struct MemoryPage *
0x18000b519  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x18000b51e  nop
0x18000b51f  mov     eax, ebx
0x18000b521  jmp     loc_18000B3F1
0x18000b526  test    rbx, rbx
0x18000b529  jz      short loc_18000B53B
0x18000b52b  mov     rax, [rbx]
0x18000b52e  mov     rcx, rbx
0x18000b531  mov     rax, [rax+10h]
0x18000b535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b53a  nop
0x18000b53b  lea     rcx, [rsp+180h+var_108]
0x18000b540  call    ??1?$ScopeGuardImpl2@P6AXPEAVMemoryPage@@PEAE@ZPEAV1@PEAE@@QEAA@XZ; ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>::~ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>(void)
0x18000b545  mov     eax, edi
0x18000b547  jmp     loc_18000B3F1
0x18000b54c  mov     eax, 4E7h
0x18000b551  mov     ecx, eax; int
0x18000b553  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x18000b558  jmp     loc_18000B3F1
0x18000b55d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b563  mov     edx, 80041006h
0x18000b568  mov     rcx, rax
0x18000b56b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b571  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b578  cmp     rcx, rsi
0x18000b57b  jz      short loc_18000B5A5
0x18000b57d  test    byte ptr [rcx+1Ch], 1
0x18000b581  jz      short loc_18000B5A5
0x18000b583  cmp     byte ptr [rcx+19h], 2
0x18000b587  jb      short loc_18000B5A5
0x18000b589  mov     edx, 9Ch
0x18000b58e  mov     r9d, 80041006h
0x18000b594  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000b59b  mov     rcx, [rcx+10h]
0x18000b59f  call    WPP_SF_d
0x18000b5a4  nop
0x18000b5a5  lea     rcx, [rsp+180h+var_108]
0x18000b5aa  call    ??1?$ScopeGuardImpl2@P6AXPEAVMemoryPage@@PEAE@ZPEAV1@PEAE@@QEAA@XZ; ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>::~ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>(void)
0x18000b5af  mov     eax, 80041006h
0x18000b5b4  jmp     loc_18000B3F1
0x18000b5b9  test    byte ptr [rcx+1Ch], 1
0x18000b5bd  jz      loc_18000B513
0x18000b5c3  cmp     byte ptr [rcx+19h], 2
0x18000b5c7  jb      loc_18000B513
0x18000b5cd  mov     edx, 9Dh
0x18000b5d2  mov     r9d, ebx
0x18000b5d5  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000b5dc  mov     rcx, [rcx+10h]
0x18000b5e0  call    WPP_SF_d
0x18000b5e5  jmp     loc_18000B513
0x18000b5ea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b5f0  mov     edx, edi
0x18000b5f2  mov     rcx, rax
0x18000b5f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b602  lea     rax, WPP_GLOBAL_Control
0x18000b609  cmp     rcx, rax
0x18000b60c  jz      loc_18000B526
0x18000b612  test    byte ptr [rcx+1Ch], 1
0x18000b616  jz      loc_18000B526
0x18000b61c  cmp     byte ptr [rcx+19h], 2
0x18000b620  jb      loc_18000B526
0x18000b626  mov     edx, 9Eh
0x18000b62b  mov     r9d, edi
0x18000b62e  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000b635  mov     rcx, [rcx+10h]
0x18000b639  call    WPP_SF_d
0x18000b63e  jmp     loc_18000B526
```
