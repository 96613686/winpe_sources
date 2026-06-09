# CSNOCplCore::OnWMConnectionRenamed(tagNETCONNNAMEDATA * const)

- ea: `0x18000ea5c`
- end: `0x18000ec67`
- name: `?OnWMConnectionRenamed@CSNOCplCore@@QEAAJQEAUtagNETCONNNAMEDATA@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct tagNETCONNNAMEDATA *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019d98`

## callees

- `0x180006b70`
- `0x180008644`
- `0x180008d70`
- `0x18000ea5c`
- `0x1800104ac`
- `0x180012324`
- `0x180014274`
- `0x18001f3a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eb97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eb97`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::OnWMConnectionRenamed(CSNOCplCore *this, struct tagNETCONNNAMEDATA *const a2)
{
  PVOID *v3; // rcx
  __int64 **v4; // rbx
  unsigned __int16 *v5; // r10
  int v6; // ebp
  const struct _GUID *v7; // r9
  __int64 v8; // rbx
  const struct _GUID *v9; // rax
  _QWORD *v10; // rdi
  struct tagNETCON_PROPERTIES *v11; // r15
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r12
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // r14
  int v16; // eax
  unsigned __int64 v17; // r9
  unsigned __int16 *v18; // rsi
  HINSTANCE v19; // rdx
  CProfileMgr *v20; // rcx
  __int64 v21; // r8
  unsigned __int16 **v23; // [rsp+20h] [rbp-68h]
  unsigned __int64 *v24; // [rsp+28h] [rbp-60h]
  unsigned int v25; // [rsp+30h] [rbp-58h]
  unsigned __int16 *v26; // [rsp+90h] [rbp+8h] BYREF
  struct tagNETCONNNAMEDATA *v27; // [rsp+98h] [rbp+10h]
  __int64 v28; // [rsp+A0h] [rbp+18h] BYREF

  v27 = a2;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    a2 = v27;
  }
  v4 = (__int64 **)*((_QWORD *)this + 19);
  v5 = 0;
  v6 = 1;
  if ( v4[1] )
  {
    v7 = 0;
    v8 = **v4;
    v28 = v8;
    while ( !v7 )
    {
      if ( v8 == **((_QWORD **)this + 19) )
        goto LABEL_29;
      v9 = *(const struct _GUID **)(v8 + 48);
      if ( *(unsigned __int16 **)v9[5].Data4 != v5 )
      {
        v10 = **(_QWORD ***)&v9[5].Data1;
        while ( 1 )
        {
          if ( v10 == *(_QWORD **)&v9[5].Data1 )
            goto LABEL_25;
          v11 = (struct tagNETCON_PROPERTIES *)v10[2];
          v12 = *((_QWORD *)a2 + 1) - *(_QWORD *)&v11->guidId.Data1;
          if ( !v12 )
            v12 = *((_QWORD *)a2 + 2) - *(_QWORD *)v11->guidId.Data4;
          if ( !v12 )
            break;
LABEL_24:
          v10 = (_QWORD *)*v10;
          if ( v7 )
            goto LABEL_25;
        }
        v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] != (_WORD)v5 );
        v15 = v14 + 1;
        v26 = v5;
        if ( v14 + 1 >= v14 )
        {
          if ( is_mul_ok(v15, 2u) )
          {
            v16 = CTCoAllocPolicy::Alloc(0, (v15 * (unsigned __int128)2uLL) >> 64, 2 * v15, (void **)&v26);
            v5 = 0;
            v6 = v16;
            if ( v16 < 0 )
            {
              a2 = v27;
            }
            else
            {
              v17 = v14;
              v18 = v26;
              StringCchCopyNExW(v26, v15, v13, v17, v23, v24, v25);
              CoTaskMemFree(v11->pszwName);
              v19 = g_hinst;
              v11->pszwName = v18;
              CProfileMgr::AppendSSID(v20, v19, v21, v11);
              a2 = v27;
              v5 = 0;
            }
            goto LABEL_23;
          }
          a2 = v27;
        }
        v6 = -2147024362;
LABEL_23:
        v7 = *(const struct _GUID **)(v8 + 48);
        v9 = v7;
        goto LABEL_24;
      }
LABEL_25:
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(&v28);
      if ( v6 < 0 )
        goto LABEL_29;
      v8 = v28;
      a2 = v27;
    }
    v6 = CSNOCplCore::ReorderConnection(this, v7);
LABEL_29:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(v3[2], 95, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ea5c  mov     [rsp+arg_8], rdx
0x18000ea61  push    rbx
0x18000ea62  push    rbp
0x18000ea63  push    rsi
0x18000ea64  push    rdi
0x18000ea65  push    r12
0x18000ea67  push    r13
0x18000ea69  push    r14
0x18000ea6b  push    r15
0x18000ea6d  sub     rsp, 48h
0x18000ea71  mov     r13, rcx
0x18000ea74  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea7b  lea     rdi, WPP_GLOBAL_Control
0x18000ea82  cmp     rcx, rdi
0x18000ea85  jz      short loc_18000EAB1
0x18000ea87  test    byte ptr [rcx+1Ch], 8
0x18000ea8b  jz      short loc_18000EAB1
0x18000ea8d  mov     rcx, [rcx+10h]
0x18000ea91  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000ea98  mov     edx, 5Eh ; '^'
0x18000ea9d  call    WPP_SF_
0x18000eaa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eaa9  mov     rdx, [rsp+88h+arg_8]; unsigned int
0x18000eab1  mov     rbx, [r13+98h]
0x18000eab8  xor     r10d, r10d
0x18000eabb  mov     ebp, 1
0x18000eac0  cmp     [rbx+8], r10
0x18000eac4  jz      loc_18000EC31
0x18000eaca  mov     rbx, [rbx]
0x18000eacd  mov     r9d, r10d
0x18000ead0  mov     rbx, [rbx]
0x18000ead3  mov     [rsp+88h+arg_10], rbx
0x18000eadb  test    r9, r9
0x18000eade  jnz     loc_18000EC16
0x18000eae4  mov     rax, [r13+98h]
0x18000eaeb  cmp     rbx, [rax]
0x18000eaee  jz      loc_18000EC0D
0x18000eaf4  mov     rax, [rbx+30h]
0x18000eaf8  cmp     [rax+58h], r10
0x18000eafc  jz      loc_18000EBE7
0x18000eb02  mov     rdi, [rax+50h]
0x18000eb06  mov     rdi, [rdi]
0x18000eb09  cmp     rdi, [rax+50h]
0x18000eb0d  jz      loc_18000EBE7
0x18000eb13  mov     r15, [rdi+10h]
0x18000eb17  mov     rcx, [rdx+8]
0x18000eb1b  sub     rcx, [r15]
0x18000eb1e  jnz     short loc_18000EB28
0x18000eb20  mov     rcx, [rdx+10h]
0x18000eb24  sub     rcx, [r15+8]; void *
0x18000eb28  test    rcx, rcx
0x18000eb2b  jnz     loc_18000EBDB
0x18000eb31  mov     r12, [rdx+18h]
0x18000eb35  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000eb39  inc     rsi
0x18000eb3c  cmp     [r12+rsi*2], r10w
0x18000eb41  jnz     short loc_18000EB39
0x18000eb43  lea     r14, [rsi+1]
0x18000eb47  mov     [rsp+88h+arg_0], r10
0x18000eb4f  cmp     r14, rsi
0x18000eb52  jb      short loc_18000EBCF
0x18000eb54  mov     eax, 2
0x18000eb59  mul     r14
0x18000eb5c  test    rdx, rdx
0x18000eb5f  jnz     short loc_18000EBC7
0x18000eb61  lea     r9, [rsp+88h+arg_0]; void **
0x18000eb69  mov     r8, rax; unsigned __int64
0x18000eb6c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000eb71  xor     r10d, r10d
0x18000eb74  mov     ebp, eax
0x18000eb76  test    eax, eax
0x18000eb78  js      short loc_18000EBBD
0x18000eb7a  mov     r9, rsi; unsigned __int64
0x18000eb7d  mov     r8, r12; unsigned __int16 *
0x18000eb80  mov     rsi, [rsp+88h+arg_0]
0x18000eb88  mov     rdx, r14; unsigned __int64
0x18000eb8b  mov     rcx, rsi; unsigned __int16 *
0x18000eb8e  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000eb93  mov     rcx, [r15+10h]; pv
0x18000eb97  call    cs:__imp_CoTaskMemFree
0x18000eb9d  mov     rdx, cs:g_hinst; HINSTANCE
0x18000eba4  mov     r9, r15; struct tagNETCON_PROPERTIES *
0x18000eba7  mov     [r15+10h], rsi
0x18000ebab  call    ?AppendSSID@CProfileMgr@@QEAAJPEAUHINSTANCE__@@IPEAUtagNETCON_PROPERTIES@@@Z; CProfileMgr::AppendSSID(HINSTANCE__ *,uint,tagNETCON_PROPERTIES *)
0x18000ebb0  mov     rdx, [rsp+88h+arg_8]
0x18000ebb8  xor     r10d, r10d
0x18000ebbb  jmp     short loc_18000EBD4
0x18000ebbd  mov     rdx, [rsp+88h+arg_8]
0x18000ebc5  jmp     short loc_18000EBD4
0x18000ebc7  mov     rdx, [rsp+88h+arg_8]
0x18000ebcf  mov     ebp, 80070216h
0x18000ebd4  mov     r9, [rbx+30h]
0x18000ebd8  mov     rax, r9
0x18000ebdb  mov     rdi, [rdi]
0x18000ebde  test    r9, r9
0x18000ebe1  jz      loc_18000EB09
0x18000ebe7  lea     rcx, [rsp+88h+arg_10]
0x18000ebef  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(void)
0x18000ebf4  test    ebp, ebp
0x18000ebf6  js      short loc_18000EC23
0x18000ebf8  mov     rbx, [rsp+88h+arg_10]
0x18000ec00  mov     rdx, [rsp+88h+arg_8]
0x18000ec08  jmp     loc_18000EADB
0x18000ec0d  test    ebp, ebp
0x18000ec0f  js      short loc_18000EC23
0x18000ec11  test    r9, r9
0x18000ec14  jz      short loc_18000EC23
0x18000ec16  mov     rdx, r9; struct _GUID *
0x18000ec19  mov     rcx, r13; this
0x18000ec1c  call    ?ReorderConnection@CSNOCplCore@@AEAAJAEBU_GUID@@@Z; CSNOCplCore::ReorderConnection(_GUID const &)
0x18000ec21  mov     ebp, eax
0x18000ec23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec2a  lea     rdi, WPP_GLOBAL_Control
0x18000ec31  cmp     rcx, rdi
0x18000ec34  jz      short loc_18000EC54
0x18000ec36  test    byte ptr [rcx+1Ch], 8
0x18000ec3a  jz      short loc_18000EC54
0x18000ec3c  mov     rcx, [rcx+10h]
0x18000ec40  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000ec47  mov     edx, 5Fh ; '_'
0x18000ec4c  mov     r9d, ebp
0x18000ec4f  call    WPP_SF_d
0x18000ec54  mov     eax, ebp
0x18000ec56  add     rsp, 48h
0x18000ec5a  pop     r15
0x18000ec5c  pop     r14
0x18000ec5e  pop     r13
0x18000ec60  pop     r12
0x18000ec62  pop     rdi
0x18000ec63  pop     rsi
0x18000ec64  pop     rbp
0x18000ec65  pop     rbx
0x18000ec66  retn
```
