# CKsFilterFactory::UpdateCacheData(_KSFILTER_DESCRIPTOR const *)

- ea: `0x180057d0c`
- end: `0x180057f5d`
- name: `?UpdateCacheData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(CKsFilterFactory *__hidden this, const struct _KSFILTER_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180057cf0`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180057d0c`
- `0x180057f64`
- `0x1800582c0`
- `0x180058700`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180057f01`
- `ntoskrnl!ExFreePoolWithTag` at `0x180057f01`

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
  ULONG v9; // r12d
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
0x180057d0c  mov     [rsp+arg_0], rbx
0x180057d11  mov     [rsp+arg_18], rbp
0x180057d16  push    rdi
0x180057d17  push    r12
0x180057d19  push    r13
0x180057d1b  push    r14
0x180057d1d  push    r15
0x180057d1f  sub     rsp, 30h
0x180057d23  mov     rdi, rdx
0x180057d26  mov     r14, rcx
0x180057d29  lea     rbp, WPP_RECORDER_INITIALIZED
0x180057d30  xor     r13d, r13d
0x180057d33  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057d3a  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057d41  jz      short loc_180057D69
0x180057d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d4a  cmp     [rcx+48h], r13w
0x180057d4f  jz      short loc_180057D69
0x180057d51  mov     rcx, [rcx+40h]
0x180057d55  lea     r9d, [r13+1Eh]
0x180057d59  lea     r8d, [r13+1]
0x180057d5d  mov     qword ptr [rsp+58h+var_38], r15
0x180057d62  mov     dl, 5
0x180057d64  call    WPP_RECORDER_SF_
0x180057d69  test    rdi, rdi
0x180057d6c  jnz     short loc_180057D75
0x180057d6e  mov     rdi, [r14+0C0h]
0x180057d75  lea     r8, [rsp+58h+arg_8]
0x180057d7a  mov     [rsp+58h+P], r13
0x180057d7f  lea     rdx, [rsp+58h+P]
0x180057d84  mov     [rsp+58h+arg_8], r13d
0x180057d89  mov     rcx, rdi
0x180057d8c  call    KspBuildFilterDataBlob
0x180057d91  mov     ebx, eax
0x180057d93  test    eax, eax
0x180057d95  js      loc_180057EC5
0x180057d9b  mov     r15, [rdi+38h]
0x180057d9f  mov     ebp, r13d
0x180057da2  mov     r12d, [rsp+58h+arg_8]
0x180057da7  cmp     ebp, [rdi+30h]
0x180057daa  jnb     short loc_180057E11
0x180057dac  mov     r9, [rsp+58h+P]; unsigned __int8 *
0x180057db1  mov     r8, r15; struct _GUID *
0x180057db4  mov     rdx, rdi; struct _KSFILTER_DESCRIPTOR *
0x180057db7  mov     [rsp+58h+var_38], r12d; unsigned int
0x180057dbc  mov     rcx, r14; this
0x180057dbf  call    ?UpdateFilterRegistryData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@QEAEK@Z; CKsFilterFactory::UpdateFilterRegistryData(_KSFILTER_DESCRIPTOR const *,_GUID const *,uchar * const,ulong)
0x180057dc4  mov     ebx, eax
0x180057dc6  test    eax, eax
0x180057dc8  jns     short loc_180057E09
0x180057dca  lea     rax, WPP_RECORDER_INITIALIZED
0x180057dd1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180057dd8  jz      short loc_180057E06
0x180057dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180057de1  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057de8  mov     r9d, 1Fh
0x180057dee  mov     dword ptr [rsp+58h+var_30], ebx
0x180057df2  mov     dl, 4
0x180057df4  mov     qword ptr [rsp+58h+var_38], rax
0x180057df9  mov     rcx, [rcx+40h]
0x180057dfd  lea     r8d, [r9-1Eh]
0x180057e01  call    WPP_RECORDER_SF_D
0x180057e06  mov     ebx, r13d
0x180057e09  add     r15, 10h
0x180057e0d  inc     ebp
0x180057e0f  jmp     short loc_180057DA7
0x180057e11  mov     rcx, rdi
0x180057e14  call    IsVideoCameraLikeFilter
0x180057e19  test    al, al
0x180057e1b  jz      loc_180057EB5
0x180057e21  lea     rbp, WPP_RECORDER_INITIALIZED
0x180057e28  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057e2f  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057e36  jz      short loc_180057E60
0x180057e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e3f  cmp     [rcx+48h], r13w
0x180057e44  jz      short loc_180057E60
0x180057e46  mov     rcx, [rcx+40h]
0x180057e4a  mov     r9d, 20h ; ' '
0x180057e50  mov     dl, 5
0x180057e52  mov     qword ptr [rsp+58h+var_38], r15
0x180057e57  lea     r8d, [r9-1Fh]
0x180057e5b  call    WPP_RECORDER_SF_
0x180057e60  mov     r9, [rsp+58h+P]; unsigned __int8 *
0x180057e65  lea     r8, [r14+198h]; struct _GUID *
0x180057e6c  mov     rdx, rdi; struct _KSFILTER_DESCRIPTOR *
0x180057e6f  mov     [rsp+58h+var_38], r12d; unsigned int
0x180057e74  mov     rcx, r14; this
0x180057e77  call    ?UpdateFilterRegistryData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@QEAEK@Z; CKsFilterFactory::UpdateFilterRegistryData(_KSFILTER_DESCRIPTOR const *,_GUID const *,uchar * const,ulong)
0x180057e7c  mov     ebx, eax
0x180057e7e  test    eax, eax
0x180057e80  jns     short loc_180057EF3
0x180057e82  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057e89  jz      short loc_180057EB0
0x180057e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e92  mov     r9d, 21h ; '!'
0x180057e98  mov     dword ptr [rsp+58h+var_30], eax
0x180057e9c  mov     dl, 4
0x180057e9e  mov     qword ptr [rsp+58h+var_38], r15
0x180057ea3  mov     rcx, [rcx+40h]
0x180057ea7  lea     r8d, [r9-20h]
0x180057eab  call    WPP_RECORDER_SF_D
0x180057eb0  mov     ebx, r13d
0x180057eb3  jmp     short loc_180057EF3
0x180057eb5  lea     rbp, WPP_RECORDER_INITIALIZED
0x180057ebc  lea     r15, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057ec3  jmp     short loc_180057EF3
0x180057ec5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057ecc  jz      short loc_180057EF3
0x180057ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ed5  mov     r9d, 22h ; '"'
0x180057edb  mov     dword ptr [rsp+58h+var_30], eax
0x180057edf  mov     dl, 4
0x180057ee1  mov     qword ptr [rsp+58h+var_38], r15
0x180057ee6  mov     rcx, [rcx+40h]
0x180057eea  lea     r8d, [r9-21h]
0x180057eee  call    WPP_RECORDER_SF_D
0x180057ef3  cmp     [rsp+58h+P], r13
0x180057ef8  jz      short loc_180057F0D
0x180057efa  mov     rcx, [rsp+58h+P]; P
0x180057eff  xor     edx, edx; Tag
0x180057f01  call    cs:__imp_ExFreePoolWithTag
0x180057f08  nop     dword ptr [rax+rax+00h]
0x180057f0d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180057f14  jz      short loc_180057F42
0x180057f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f1d  cmp     [rcx+48h], r13w
0x180057f22  jz      short loc_180057F42
0x180057f24  mov     rcx, [rcx+40h]
0x180057f28  mov     r9d, 23h ; '#'
0x180057f2e  mov     dword ptr [rsp+58h+var_30], ebx
0x180057f32  mov     dl, 5
0x180057f34  mov     qword ptr [rsp+58h+var_38], r15
0x180057f39  lea     r8d, [r9-22h]
0x180057f3d  call    WPP_RECORDER_SF_D
0x180057f42  mov     rbp, [rsp+58h+arg_18]
0x180057f47  mov     eax, ebx
0x180057f49  mov     rbx, [rsp+58h+arg_0]
0x180057f4e  add     rsp, 30h
0x180057f52  pop     r15
0x180057f54  pop     r14
0x180057f56  pop     r13
0x180057f58  pop     r12
0x180057f5a  pop     rdi
0x180057f5b  retn
```
