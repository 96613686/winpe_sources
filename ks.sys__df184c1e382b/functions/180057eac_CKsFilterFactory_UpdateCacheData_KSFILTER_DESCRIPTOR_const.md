# CKsFilterFactory::UpdateCacheData(_KSFILTER_DESCRIPTOR const *)

- ea: `0x180057eac`
- end: `0x1800580fd`
- name: `?UpdateCacheData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(CKsFilterFactory *__hidden this, const struct _KSFILTER_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180057e90`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180057eac`
- `0x180058104`
- `0x180058460`
- `0x1800588a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800580a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800580a1`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::UpdateCacheData(CKsFilterFactory *this, const struct _KSFILTER_DESCRIPTOR *a2)
{
  const KSFILTER_DESCRIPTOR *FilterDescriptor; // rdi
  int v4; // eax
  int v5; // edx
  int updated; // ebx
  const struct _GUID *Categories; // r15
  ULONG v8; // ebp
  unsigned int v9; // r12d
  int v10; // edx
  int v11; // eax
  __int64 v13; // [rsp+28h] [rbp-30h]
  int v14; // [rsp+28h] [rbp-30h]
  unsigned int v15; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  FilterDescriptor = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      30,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
  }
  if ( !FilterDescriptor )
    FilterDescriptor = this->m_Ext.Public.FilterDescriptor;
  P = 0;
  v15 = 0;
  v4 = KspBuildFilterDataBlob(FilterDescriptor, &P, &v15);
  updated = v4;
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = v4;
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        34,
        (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
        v14);
    }
  }
  else
  {
    Categories = FilterDescriptor->Categories;
    v8 = 0;
    v9 = v15;
    while ( v8 < FilterDescriptor->CategoriesCount )
    {
      updated = CKsFilterFactory::UpdateFilterRegistryData(
                  this,
                  FilterDescriptor,
                  Categories,
                  (unsigned __int8 *const)P,
                  v9);
      if ( updated < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v13) = updated;
          LOBYTE(v10) = 4;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            1,
            31,
            (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
            v13);
        }
        updated = 0;
      }
      ++Categories;
      ++v8;
    }
    if ( (unsigned __int8)IsVideoCameraLikeFilter(FilterDescriptor) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          1,
          32,
          (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
      }
      v11 = CKsFilterFactory::UpdateFilterRegistryData(
              this,
              FilterDescriptor,
              &this->m_GuidVideoCamera,
              (unsigned __int8 *const)P,
              v9);
      updated = v11;
      if ( v11 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v13) = v11;
          LOBYTE(v5) = 4;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v5,
            1,
            33,
            (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
            v13);
        }
        updated = 0;
      }
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v13) = updated;
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      35,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      v13);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180057eac  mov     [rsp+arg_0], rbx
0x180057eb1  mov     [rsp+arg_18], rbp
0x180057eb6  push    rdi
0x180057eb7  push    r12
0x180057eb9  push    r13
0x180057ebb  push    r14
0x180057ebd  push    r15
0x180057ebf  sub     rsp, 30h
0x180057ec3  mov     rdi, rdx
0x180057ec6  mov     r14, rcx
0x180057ec9  lea     rbp, WPP_RECORDER_INITIALIZED
0x180057ed0  xor     r13d, r13d
0x180057ed3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057eda  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057ee1  jz      short loc_180057F09
0x180057ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x180057eea  cmp     [rcx+48h], r13w
0x180057eef  jz      short loc_180057F09
0x180057ef1  mov     rcx, [rcx+40h]
0x180057ef5  lea     r9d, [r13+1Eh]
0x180057ef9  lea     r8d, [r13+1]
0x180057efd  mov     qword ptr [rsp+58h+var_38], r15
0x180057f02  mov     dl, 5
0x180057f04  call    WPP_RECORDER_SF_
0x180057f09  test    rdi, rdi
0x180057f0c  jnz     short loc_180057F15
0x180057f0e  mov     rdi, [r14+0C0h]
0x180057f15  lea     r8, [rsp+58h+arg_8]
0x180057f1a  mov     [rsp+58h+P], r13
0x180057f1f  lea     rdx, [rsp+58h+P]
0x180057f24  mov     [rsp+58h+arg_8], r13d
0x180057f29  mov     rcx, rdi
0x180057f2c  call    KspBuildFilterDataBlob
0x180057f31  mov     ebx, eax
0x180057f33  test    eax, eax
0x180057f35  js      loc_180058065
0x180057f3b  mov     r15, [rdi+38h]
0x180057f3f  mov     ebp, r13d
0x180057f42  mov     r12d, [rsp+58h+arg_8]
0x180057f47  cmp     ebp, [rdi+30h]
0x180057f4a  jnb     short loc_180057FB1
0x180057f4c  mov     r9, [rsp+58h+P]; unsigned __int8 *
0x180057f51  mov     r8, r15; struct _GUID *
0x180057f54  mov     rdx, rdi; struct _KSFILTER_DESCRIPTOR *
0x180057f57  mov     [rsp+58h+var_38], r12d; unsigned int
0x180057f5c  mov     rcx, r14; this
0x180057f5f  call    ?UpdateFilterRegistryData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@QEAEK@Z; CKsFilterFactory::UpdateFilterRegistryData(_KSFILTER_DESCRIPTOR const *,_GUID const *,uchar * const,ulong)
0x180057f64  mov     ebx, eax
0x180057f66  test    eax, eax
0x180057f68  jns     short loc_180057FA9
0x180057f6a  lea     rax, WPP_RECORDER_INITIALIZED
0x180057f71  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180057f78  jz      short loc_180057FA6
0x180057f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f81  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057f88  mov     r9d, 1Fh
0x180057f8e  mov     dword ptr [rsp+58h+var_30], ebx
0x180057f92  mov     dl, 4
0x180057f94  mov     qword ptr [rsp+58h+var_38], rax
0x180057f99  mov     rcx, [rcx+40h]
0x180057f9d  lea     r8d, [r9-1Eh]
0x180057fa1  call    WPP_RECORDER_SF_D
0x180057fa6  mov     ebx, r13d
0x180057fa9  add     r15, 10h
0x180057fad  inc     ebp
0x180057faf  jmp     short loc_180057F47
0x180057fb1  mov     rcx, rdi
0x180057fb4  call    IsVideoCameraLikeFilter
0x180057fb9  test    al, al
0x180057fbb  jz      loc_180058055
0x180057fc1  lea     rbp, WPP_RECORDER_INITIALIZED
0x180057fc8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057fcf  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057fd6  jz      short loc_180058000
0x180057fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180057fdf  cmp     [rcx+48h], r13w
0x180057fe4  jz      short loc_180058000
0x180057fe6  mov     rcx, [rcx+40h]
0x180057fea  mov     r9d, 20h ; ' '
0x180057ff0  mov     dl, 5
0x180057ff2  mov     qword ptr [rsp+58h+var_38], r15
0x180057ff7  lea     r8d, [r9-1Fh]
0x180057ffb  call    WPP_RECORDER_SF_
0x180058000  mov     r9, [rsp+58h+P]; unsigned __int8 *
0x180058005  lea     r8, [r14+198h]; struct _GUID *
0x18005800c  mov     rdx, rdi; struct _KSFILTER_DESCRIPTOR *
0x18005800f  mov     [rsp+58h+var_38], r12d; unsigned int
0x180058014  mov     rcx, r14; this
0x180058017  call    ?UpdateFilterRegistryData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@QEAEK@Z; CKsFilterFactory::UpdateFilterRegistryData(_KSFILTER_DESCRIPTOR const *,_GUID const *,uchar * const,ulong)
0x18005801c  mov     ebx, eax
0x18005801e  test    eax, eax
0x180058020  jns     short loc_180058093
0x180058022  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180058029  jz      short loc_180058050
0x18005802b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058032  mov     r9d, 21h ; '!'
0x180058038  mov     dword ptr [rsp+58h+var_30], eax
0x18005803c  mov     dl, 4
0x18005803e  mov     qword ptr [rsp+58h+var_38], r15
0x180058043  mov     rcx, [rcx+40h]
0x180058047  lea     r8d, [r9-20h]
0x18005804b  call    WPP_RECORDER_SF_D
0x180058050  mov     ebx, r13d
0x180058053  jmp     short loc_180058093
0x180058055  lea     rbp, WPP_RECORDER_INITIALIZED
0x18005805c  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180058063  jmp     short loc_180058093
0x180058065  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18005806c  jz      short loc_180058093
0x18005806e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058075  mov     r9d, 22h ; '"'
0x18005807b  mov     dword ptr [rsp+58h+var_30], eax
0x18005807f  mov     dl, 4
0x180058081  mov     qword ptr [rsp+58h+var_38], r15
0x180058086  mov     rcx, [rcx+40h]
0x18005808a  lea     r8d, [r9-21h]
0x18005808e  call    WPP_RECORDER_SF_D
0x180058093  cmp     [rsp+58h+P], r13
0x180058098  jz      short loc_1800580AD
0x18005809a  mov     rcx, [rsp+58h+P]; P
0x18005809f  xor     edx, edx; Tag
0x1800580a1  call    cs:__imp_ExFreePoolWithTag
0x1800580a8  nop     dword ptr [rax+rax+00h]
0x1800580ad  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1800580b4  jz      short loc_1800580E2
0x1800580b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580bd  cmp     [rcx+48h], r13w
0x1800580c2  jz      short loc_1800580E2
0x1800580c4  mov     rcx, [rcx+40h]
0x1800580c8  mov     r9d, 23h ; '#'
0x1800580ce  mov     dword ptr [rsp+58h+var_30], ebx
0x1800580d2  mov     dl, 5
0x1800580d4  mov     qword ptr [rsp+58h+var_38], r15
0x1800580d9  lea     r8d, [r9-22h]
0x1800580dd  call    WPP_RECORDER_SF_D
0x1800580e2  mov     rbp, [rsp+58h+arg_18]
0x1800580e7  mov     eax, ebx
0x1800580e9  mov     rbx, [rsp+58h+arg_0]
0x1800580ee  add     rsp, 30h
0x1800580f2  pop     r15
0x1800580f4  pop     r14
0x1800580f6  pop     r13
0x1800580f8  pop     r12
0x1800580fa  pop     rdi
0x1800580fb  retn
```
