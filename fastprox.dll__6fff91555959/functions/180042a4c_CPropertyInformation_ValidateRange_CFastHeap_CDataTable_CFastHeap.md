# CPropertyInformation::ValidateRange(CFastHeap *,CDataTable *,CFastHeap *)

- ea: `0x180042a4c`
- end: `0x180042da5`
- name: `?ValidateRange@CPropertyInformation@@QEAAJPEAVCFastHeap@@PEAVCDataTable@@0@Z`
- size: `857`
- prototype: `int __fastcall(CPropertyInformation *this, struct CFastHeap *, struct CDataTable *, struct CFastHeap *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800428b0`

## callees

- `0x180004060`
- `0x18000b070`
- `0x180013ae0`
- `0x180021820`
- `0x180024390`
- `0x1800255a0`
- `0x180037120`
- `0x180042a4c`
- `0x180042dac`
- `0x180043674`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180042c78`
- `wbemcomn!GetMemLogObject` at `0x180042cca`
- `wbemcomn!GetMemLogObject` at `0x180042d56`
- `wbemcomn!GetMemLogObject` at `0x180042c78`
- `wbemcomn!GetMemLogObject` at `0x180042cca`
- `wbemcomn!GetMemLogObject` at `0x180042d56`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x180042b96`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x180042b96`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180042ba6`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180042ba6`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180042b66`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180042b66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042c88`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042cd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042d61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042c88`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042cd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042d61`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180042c03`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180042c03`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
int __fastcall CPropertyInformation::ValidateRange(
        CPropertyInformation *this,
        struct CFastHeap *a2,
        struct CDataTable *a3,
        struct CFastHeap *a4)
{
  int v8; // eax
  unsigned int v9; // edx
  struct CCompressedString *v10; // rax
  unsigned __int8 *v12; // r14
  int j; // esi
  struct CQualifier *QualifierLocally; // rsi
  unsigned __int16 *LPWSTR; // rsi
  const unsigned __int16 *v16; // r14
  unsigned int v17; // edx
  unsigned __int8 *v18; // rsi
  int i; // edi
  int v20; // ebx
  struct CEmbeddedObject *v21; // rax
  CPropertyInformation *v22; // rcx
  struct CEmbeddedObject *v23; // rax
  CPropertyInformation *v24; // rcx
  CMemoryLog *v25; // rax
  CWbemRefreshingSvc *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  CMemoryLog *MemLogObject; // rax
  struct CCompressedString *v30; // rax
  int v31; // edi
  CMemoryLog *v32; // rax
  _BYTE v33[32]; // [rsp+30h] [rbp-38h] BYREF
  int v34; // [rsp+70h] [rbp+8h] BYREF

  if ( (unsigned int)CBitBlockTable<2>::GetBit(*(_QWORD *)a3, *((unsigned __int16 *)this + 2), 0)
    || (unsigned int)CBitBlockTable<2>::GetBit(*(_QWORD *)a3, *((unsigned __int16 *)this + 2), 1) )
  {
    return 0;
  }
  v8 = *(_DWORD *)this & 0xFFF;
  if ( v8 == 13 )
  {
    v34 = 0;
    QualifierLocally = CBasicQualifierSet::GetQualifierLocally((unsigned __int8 *)this + 14, a2, L"cimtype", &v34);
    if ( !QualifierLocally )
      return 0;
    CVar::CVar((CVar *)v33);
    if ( CUntypedValue::StoreToCVar(
           (unsigned int *)((char *)QualifierLocally + 9),
           *(_DWORD *)((char *)QualifierLocally + 5),
           (CVar *)v33,
           a2,
           0) )
    {
      if ( CVar::GetType((CVar *)v33) == 8
        && (LPWSTR = CVar::GetLPWSTR((CVar *)v33), (unsigned int)wbem_wcsicmp(LPWSTR, L"object")) )
      {
        v16 = LPWSTR + 7;
        v17 = *(_DWORD *)(*(unsigned int *)((char *)this + 6) + *((_QWORD *)a3 + 1));
        if ( (*(_DWORD *)this & 0x2000) != 0 )
        {
          v18 = CFastHeap::ResolveHeapPointer(a4, v17);
          for ( i = 0; ; ++i )
          {
            if ( i >= *(_DWORD *)v18 )
            {
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8db10d0debd535326cee342840d89e0d_Traceguids, 0);
              }
              goto LABEL_23;
            }
            v23 = (struct CEmbeddedObject *)CFastHeap::ResolveHeapPointer(a4, *(_DWORD *)&v18[4 * i + 4]);
            v20 = CPropertyInformation::ValidateObjectRange(v24, v23, v16);
            if ( v20 )
              break;
          }
          if ( v20 < 0 )
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, v20);
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 11;
            v28 = (unsigned int)v20;
            goto LABEL_41;
          }
        }
        else
        {
          v21 = (struct CEmbeddedObject *)CFastHeap::ResolveHeapPointer(a4, v17);
          v20 = CPropertyInformation::ValidateObjectRange(v22, v21, LPWSTR + 7);
        }
      }
      else
      {
LABEL_23:
        v20 = 0;
      }
    }
    else
    {
      v25 = GetMemLogObject();
      v20 = -2147217402;
      CMemoryLog::Write(v25, -2147217402);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 10;
        v28 = 2147749894LL;
LABEL_41:
        WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_8db10d0debd535326cee342840d89e0d_Traceguids, v28);
      }
    }
    CVar::~CVar((CVar *)v33);
    return v20;
  }
  else
  {
    if ( v8 != 101 && v8 != 102 )
      return 0;
    v9 = *(_DWORD *)(*(unsigned int *)((char *)this + 6) + *((_QWORD *)a3 + 1));
    if ( (*(_DWORD *)this & 0x2000) != 0 )
    {
      v12 = CFastHeap::ResolveHeapPointer(a4, v9);
      for ( j = 0; ; ++j )
      {
        if ( j >= *(_DWORD *)v12 )
        {
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8db10d0debd535326cee342840d89e0d_Traceguids, 0);
          }
          return 0;
        }
        v30 = CFastHeap::ResolveString(a4, *(_DWORD *)&v12[4 * j + 4]);
        v31 = CPropertyInformation::ValidateStringRange(this, v30);
        if ( v31 )
          break;
      }
      if ( v31 < 0 )
      {
        v32 = GetMemLogObject();
        CMemoryLog::Write(v32, v31);
      }
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_8db10d0debd535326cee342840d89e0d_Traceguids,
          (unsigned int)v31);
      }
      return v31;
    }
    else
    {
      v10 = CFastHeap::ResolveString(a4, v9);
      return CPropertyInformation::ValidateStringRange(this, v10);
    }
  }
}

```

## disassembly

```asm
0x180042a4c  mov     [rsp+arg_8], rbx
0x180042a51  mov     [rsp+arg_10], rbp
0x180042a56  push    rsi
0x180042a57  push    rdi
0x180042a58  push    r14
0x180042a5a  sub     rsp, 50h
0x180042a5e  mov     rbp, r9
0x180042a61  mov     rdi, r8
0x180042a64  mov     r14, rdx
0x180042a67  mov     rbx, rcx
0x180042a6a  movzx   edx, word ptr [rcx+4]
0x180042a6e  xor     r8d, r8d
0x180042a71  mov     rcx, [rdi]
0x180042a74  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x180042a79  test    eax, eax
0x180042a7b  jnz     short loc_180042AD2
0x180042a7d  movzx   edx, word ptr [rbx+4]
0x180042a81  lea     r8d, [rax+1]
0x180042a85  mov     rcx, [rdi]
0x180042a88  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x180042a8d  test    eax, eax
0x180042a8f  jnz     short loc_180042AD2
0x180042a91  mov     eax, [rbx]
0x180042a93  and     eax, 0FFFh
0x180042a98  cmp     eax, 0Dh
0x180042a9b  jz      loc_180042B35
0x180042aa1  cmp     eax, 65h ; 'e'
0x180042aa4  jnz     short loc_180042ACD
0x180042aa6  mov     ecx, [rbx+6]
0x180042aa9  mov     rax, [rdi+8]
0x180042aad  mov     edx, [rcx+rax]; unsigned int
0x180042ab0  mov     rcx, rbp; this
0x180042ab3  test    dword ptr [rbx], 2000h
0x180042ab9  jnz     short loc_180042AE9
0x180042abb  call    ?ResolveString@CFastHeap@@QEAAPEAVCCompressedString@@K@Z; CFastHeap::ResolveString(ulong)
0x180042ac0  mov     rdx, rax; struct CCompressedString *
0x180042ac3  mov     rcx, rbx; this
0x180042ac6  call    ?ValidateStringRange@CPropertyInformation@@QEAAJPEAVCCompressedString@@@Z; CPropertyInformation::ValidateStringRange(CCompressedString *)
0x180042acb  jmp     short loc_180042AD4
0x180042acd  cmp     eax, 66h ; 'f'
0x180042ad0  jz      short loc_180042AA6
0x180042ad2  xor     eax, eax
0x180042ad4  lea     r11, [rsp+68h+var_18]
0x180042ad9  mov     rbx, [r11+28h]
0x180042add  mov     rbp, [r11+30h]
0x180042ae1  mov     rsp, r11
0x180042ae4  pop     r14
0x180042ae6  pop     rdi
0x180042ae7  pop     rsi
0x180042ae8  retn
0x180042ae9  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x180042aee  mov     r14, rax
0x180042af1  xor     esi, esi
0x180042af3  cmp     esi, [r14]
0x180042af6  jl      loc_180042D23
0x180042afc  lea     rax, WPP_GLOBAL_Control
0x180042b03  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b0a  cmp     rcx, rax
0x180042b0d  jz      short loc_180042AD2
0x180042b0f  test    byte ptr [rcx+1Ch], 1
0x180042b13  jz      short loc_180042AD2
0x180042b15  cmp     byte ptr [rcx+19h], 2
0x180042b19  jb      short loc_180042AD2
0x180042b1b  mov     edx, 0Eh
0x180042b20  xor     r9d, r9d
0x180042b23  lea     r8, WPP_8db10d0debd535326cee342840d89e0d_Traceguids
0x180042b2a  mov     rcx, [rcx+10h]
0x180042b2e  call    WPP_SF_d
0x180042b33  jmp     short loc_180042AD2
0x180042b35  mov     [rsp+68h+arg_0], 0
0x180042b3d  lea     rcx, [rbx+0Eh]; unsigned __int8 *
0x180042b41  lea     r9, [rsp+68h+arg_0]; int *
0x180042b46  lea     r8, aCimtype; "cimtype"
0x180042b4d  mov     rdx, r14; struct CFastHeap *
0x180042b50  call    ?GetQualifierLocally@CBasicQualifierSet@@SAPEAUCQualifier@@PEAEPEAVCFastHeap@@PEBGAEAH@Z; CBasicQualifierSet::GetQualifierLocally(uchar *,CFastHeap *,ushort const *,int &)
0x180042b55  mov     rsi, rax
0x180042b58  test    rax, rax
0x180042b5b  jz      loc_180042AD2
0x180042b61  lea     rcx, [rsp+68h+var_38]
0x180042b66  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180042b6c  nop
0x180042b6d  lea     rcx, [rsi+9]
0x180042b71  mov     [rsp+68h+var_48], 0
0x180042b79  mov     r9, r14
0x180042b7c  lea     r8, [rsp+68h+var_38]
0x180042b81  mov     edx, [rsi+5]
0x180042b84  call    ?StoreToCVar@CUntypedValue@@QEAAHVCType@@AEAVCVar@@PEAVCFastHeap@@H@Z; CUntypedValue::StoreToCVar(CType,CVar &,CFastHeap *,int)
0x180042b89  test    eax, eax
0x180042b8b  jz      loc_180042C78
0x180042b91  lea     rcx, [rsp+68h+var_38]
0x180042b96  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x180042b9c  cmp     eax, 8
0x180042b9f  jnz     short loc_180042BFC
0x180042ba1  lea     rcx, [rsp+68h+var_38]
0x180042ba6  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180042bac  mov     rsi, rax
0x180042baf  lea     rdx, aObject_0; "object"
0x180042bb6  mov     rcx, rax; unsigned __int16 *
0x180042bb9  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180042bbe  test    eax, eax
0x180042bc0  jz      short loc_180042BFC
0x180042bc2  lea     r14, [rsi+0Eh]
0x180042bc6  mov     ecx, [rbx+6]
0x180042bc9  mov     rax, [rdi+8]
0x180042bcd  mov     edx, [rcx+rax]; unsigned int
0x180042bd0  mov     rcx, rbp; this
0x180042bd3  test    dword ptr [rbx], 2000h
0x180042bd9  jz      short loc_180042C36
0x180042bdb  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x180042be0  mov     rsi, rax
0x180042be3  xor     edi, edi
0x180042be5  cmp     edi, [rsi]
0x180042be7  jl      short loc_180042C4A
0x180042be9  lea     rax, WPP_GLOBAL_Control
0x180042bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180042bf7  cmp     rcx, rax
0x180042bfa  jnz     short loc_180042C10
0x180042bfc  xor     ebx, ebx
0x180042bfe  lea     rcx, [rsp+68h+var_38]
0x180042c03  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180042c09  mov     eax, ebx
0x180042c0b  jmp     loc_180042AD4
0x180042c10  test    byte ptr [rcx+1Ch], 1
0x180042c14  jz      short loc_180042BFC
0x180042c16  cmp     byte ptr [rcx+19h], 2
0x180042c1a  jb      short loc_180042BFC
0x180042c1c  mov     edx, 0Ch
0x180042c21  xor     r9d, r9d
0x180042c24  lea     r8, WPP_8db10d0debd535326cee342840d89e0d_Traceguids
0x180042c2b  mov     rcx, [rcx+10h]
0x180042c2f  call    WPP_SF_d
0x180042c34  jmp     short loc_180042BFC
0x180042c36  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x180042c3b  mov     r8, r14; unsigned __int16 *
0x180042c3e  mov     rdx, rax; struct CEmbeddedObject *
0x180042c41  call    ?ValidateObjectRange@CPropertyInformation@@QEAAJPEAVCEmbeddedObject@@PEBG@Z; CPropertyInformation::ValidateObjectRange(CEmbeddedObject *,ushort const *)
0x180042c46  mov     ebx, eax
0x180042c48  jmp     short loc_180042BFE
0x180042c4a  lea     ecx, ds:0[rdi*4]
0x180042c51  movsxd  rdx, ecx
0x180042c54  mov     edx, [rdx+rsi+4]; unsigned int
0x180042c58  mov     rcx, rbp; this
0x180042c5b  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x180042c60  mov     r8, r14; unsigned __int16 *
0x180042c63  mov     rdx, rax; struct CEmbeddedObject *
0x180042c66  call    ?ValidateObjectRange@CPropertyInformation@@QEAAJPEAVCEmbeddedObject@@PEBG@Z; CPropertyInformation::ValidateObjectRange(CEmbeddedObject *,ushort const *)
0x180042c6b  mov     ebx, eax
0x180042c6d  test    eax, eax
0x180042c6f  jnz     short loc_180042CC6
0x180042c71  inc     edi
0x180042c73  jmp     loc_180042BE5
0x180042c78  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042c7e  mov     ebx, 80041006h
0x180042c83  mov     edx, ebx
0x180042c85  mov     rcx, rax
0x180042c88  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042c8e  lea     rax, WPP_GLOBAL_Control
0x180042c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c9c  cmp     rcx, rax
0x180042c9f  jz      loc_180042BFE
0x180042ca5  test    byte ptr [rcx+1Ch], 1
0x180042ca9  jz      loc_180042BFE
0x180042caf  cmp     byte ptr [rcx+19h], 2
0x180042cb3  jb      loc_180042BFE
0x180042cb9  mov     edx, 0Ah
0x180042cbe  mov     r9d, 80041006h
0x180042cc4  jmp     short loc_180042D0E
0x180042cc6  test    ebx, ebx
0x180042cc8  jns     short loc_180042CDB
0x180042cca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042cd0  mov     edx, ebx
0x180042cd2  mov     rcx, rax
0x180042cd5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042cdb  lea     rax, WPP_GLOBAL_Control
0x180042ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ce9  cmp     rcx, rax
0x180042cec  jz      loc_180042BFE
0x180042cf2  test    byte ptr [rcx+1Ch], 1
0x180042cf6  jz      loc_180042BFE
0x180042cfc  cmp     byte ptr [rcx+19h], 2
0x180042d00  jb      loc_180042BFE
0x180042d06  mov     edx, 0Bh
0x180042d0b  mov     r9d, ebx
0x180042d0e  lea     r8, WPP_8db10d0debd535326cee342840d89e0d_Traceguids
0x180042d15  mov     rcx, [rcx+10h]
0x180042d19  call    WPP_SF_d
0x180042d1e  jmp     loc_180042BFE
0x180042d23  lea     ecx, ds:0[rsi*4]
0x180042d2a  movsxd  rdx, ecx
0x180042d2d  mov     edx, [rdx+r14+4]; unsigned int
0x180042d32  mov     rcx, rbp; this
0x180042d35  call    ?ResolveString@CFastHeap@@QEAAPEAVCCompressedString@@K@Z; CFastHeap::ResolveString(ulong)
0x180042d3a  mov     rdx, rax; struct CCompressedString *
0x180042d3d  mov     rcx, rbx; this
0x180042d40  call    ?ValidateStringRange@CPropertyInformation@@QEAAJPEAVCCompressedString@@@Z; CPropertyInformation::ValidateStringRange(CCompressedString *)
0x180042d45  mov     edi, eax
0x180042d47  test    eax, eax
0x180042d49  jnz     short loc_180042D52
0x180042d4b  inc     esi
0x180042d4d  jmp     loc_180042AF3
0x180042d52  test    edi, edi
0x180042d54  jns     short loc_180042D67
0x180042d56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042d5c  mov     edx, edi
0x180042d5e  mov     rcx, rax
0x180042d61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042d67  lea     rax, WPP_GLOBAL_Control
0x180042d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d75  cmp     rcx, rax
0x180042d78  jz      short loc_180042D9E
0x180042d7a  test    byte ptr [rcx+1Ch], 1
0x180042d7e  jz      short loc_180042D9E
0x180042d80  cmp     byte ptr [rcx+19h], 2
0x180042d84  jb      short loc_180042D9E
0x180042d86  mov     edx, 0Dh
0x180042d8b  mov     r9d, edi
0x180042d8e  lea     r8, WPP_8db10d0debd535326cee342840d89e0d_Traceguids
0x180042d95  mov     rcx, [rcx+10h]
0x180042d99  call    WPP_SF_d
0x180042d9e  mov     eax, edi
0x180042da0  jmp     loc_180042AD4
```
