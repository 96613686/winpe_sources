# CMsftDiscRecorder2::GetSupportedFeaturePages(uchar,_IMAPI_FEATURE_PAGE_TYPE * *,ulong *)

- ea: `0x180029d10`
- end: `0x180029fc9`
- name: `?GetSupportedFeaturePages@CMsftDiscRecorder2@@UEAAJEPEAPEAW4_IMAPI_FEATURE_PAGE_TYPE@@PEAK@Z`
- size: `697`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, unsigned __int8, enum _IMAPI_FEATURE_PAGE_TYPE **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180004af0`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180029d10`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180029dda`
- `ole32!CoTaskMemFree` at `0x180029de5`
- `ole32!CoTaskMemFree` at `0x180029dda`
- `ole32!CoTaskMemFree` at `0x180029de5`
- `ole32!CoTaskMemAlloc` at `0x180029f27`
- `ole32!CoTaskMemAlloc` at `0x180029f27`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetSupportedFeaturePages(
        CMsftDiscRecorder2 *this,
        unsigned __int8 a2,
        enum _IMAPI_FEATURE_PAGE_TYPE **a3,
        unsigned int *a4)
{
  PVOID *v8; // rcx
  signed int FeaturesHelper; // ebx
  const struct _GUID *v10; // r8
  __int64 v12; // r9
  char *v13; // rcx
  unsigned int v14; // edi
  enum _IMAPI_FEATURE_PAGE_TYPE *v15; // rsi
  unsigned __int8 *v16; // rdx
  __int64 i; // r8
  unsigned int v18; // [rsp+70h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v18 = 0;
  if ( a3 )
  {
    FeaturesHelper = 0;
    *a3 = 0;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 132, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    FeaturesHelper = -2147467261;
  }
  if ( !a4 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 188) & 4) != 0 && *((_BYTE *)v8 + 185) >= 3u )
      WPP_SF_(v8[22], 133, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    FeaturesHelper = -2147467261;
    goto LABEL_14;
  }
  *a4 = 0;
  if ( FeaturesHelper < 0 )
  {
LABEL_14:
    CoTaskMemFree(0);
    goto LABEL_15;
  }
  v12 = *((unsigned int *)this + 58);
  if ( (v12 & 2) == 0 )
  {
    FeaturesHelper = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        134,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v12,
        -2147467259);
    }
    goto LABEL_14;
  }
  FeaturesHelper = CMsftDiscRecorder2::GetFeaturesHelper(
                     (CMsftDiscRecorder2 *)((char *)this - 8),
                     1u,
                     0,
                     a2,
                     (unsigned __int8 **)&pv,
                     &v18);
  if ( FeaturesHelper < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        135,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned int)FeaturesHelper);
    }
    goto LABEL_14;
  }
  v13 = (char *)pv;
  v14 = 0;
  while ( v13 <= (char *)pv + v18 - 4 )
  {
    ++v14;
    v13 += (unsigned __int8)v13[3] + 4;
  }
  v15 = (enum _IMAPI_FEATURE_PAGE_TYPE *)CoTaskMemAlloc(4LL * v14);
  if ( !v15 )
  {
    FeaturesHelper = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 136, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v14, v14);
    }
    goto LABEL_14;
  }
  v16 = (unsigned __int8 *)pv;
  for ( i = 0; (unsigned int)i < v14; v16 += v16[3] + 4 )
  {
    v15[i] = v16[1] | (*v16 << 8);
    i = (unsigned int)(i + 1);
  }
  *a3 = v15;
  *a4 = v14;
LABEL_15:
  CoTaskMemFree(pv);
  pv = 0;
  if ( (FeaturesHelper & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(FeaturesHelper, (int)&CLSID_MsftDiscRecorder2, v10);
  return (unsigned int)FeaturesHelper;
}

```

## disassembly

```asm
0x180029d10  mov     [rsp+arg_0], rbx
0x180029d15  push    rbp
0x180029d16  push    rsi
0x180029d17  push    rdi
0x180029d18  push    r14
0x180029d1a  push    r15
0x180029d1c  sub     rsp, 30h
0x180029d20  xor     esi, esi
0x180029d22  lea     rax, WPP_GLOBAL_Control
0x180029d29  mov     [rsp+58h+pv], rsi
0x180029d2e  mov     r14, r9
0x180029d31  mov     [rsp+58h+arg_10], esi
0x180029d35  mov     r15, r8
0x180029d38  mov     bpl, dl
0x180029d3b  mov     rdi, rcx
0x180029d3e  test    r8, r8
0x180029d41  jnz     short loc_180029D8E
0x180029d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d4a  cmp     rcx, rax
0x180029d4d  jz      short loc_180029D87
0x180029d4f  test    byte ptr [rcx+0BCh], 4
0x180029d56  jz      short loc_180029D87
0x180029d58  cmp     byte ptr [rcx+0B9h], 3
0x180029d5f  jb      short loc_180029D87
0x180029d61  mov     rcx, [rcx+0B0h]
0x180029d68  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029d6f  mov     edx, 84h
0x180029d74  call    WPP_SF_
0x180029d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d80  lea     rax, WPP_GLOBAL_Control
0x180029d87  mov     ebx, 80004003h
0x180029d8c  jmp     short loc_180029D9A
0x180029d8e  xor     ebx, ebx
0x180029d90  mov     [r8], rbx
0x180029d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d9a  test    r14, r14
0x180029d9d  jnz     loc_180029E23
0x180029da3  cmp     rcx, rax
0x180029da6  jz      short loc_180029DD2
0x180029da8  test    byte ptr [rcx+0BCh], 4
0x180029daf  jz      short loc_180029DD2
0x180029db1  cmp     byte ptr [rcx+0B9h], 3
0x180029db8  jb      short loc_180029DD2
0x180029dba  mov     rcx, [rcx+0B0h]
0x180029dc1  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029dc8  mov     edx, 85h
0x180029dcd  call    WPP_SF_
0x180029dd2  mov     ebx, 80004003h
0x180029dd7  mov     rcx, rsi; pv
0x180029dda  call    cs:__imp_CoTaskMemFree
0x180029de0  mov     rcx, [rsp+58h+pv]; pv
0x180029de5  call    cs:__imp_CoTaskMemFree
0x180029deb  mov     eax, ebx
0x180029ded  mov     [rsp+58h+pv], 0
0x180029df6  and     eax, 80FF0000h
0x180029dfb  cmp     eax, 80AA0000h
0x180029e00  jnz     short loc_180029E10
0x180029e02  lea     rdx, CLSID_MsftDiscRecorder2; int
0x180029e09  mov     ecx, ebx; dwMessageId
0x180029e0b  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180029e10  mov     eax, ebx
0x180029e12  mov     rbx, [rsp+58h+arg_0]
0x180029e17  add     rsp, 30h
0x180029e1b  pop     r15
0x180029e1d  pop     r14
0x180029e1f  pop     rdi
0x180029e20  pop     rsi
0x180029e21  pop     rbp
0x180029e22  retn
0x180029e23  mov     [r14], esi
0x180029e26  test    ebx, ebx
0x180029e28  js      short loc_180029DD7
0x180029e2a  mov     r9d, [rdi+0E8h]
0x180029e31  test    r9b, 2
0x180029e35  jnz     short loc_180029E7F
0x180029e37  mov     ebx, 80004005h
0x180029e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e43  cmp     rcx, rax
0x180029e46  jz      short loc_180029DD7
0x180029e48  test    byte ptr [rcx+0BCh], 4
0x180029e4f  jz      short loc_180029DD7
0x180029e51  cmp     byte ptr [rcx+0B9h], 3
0x180029e58  jb      loc_180029DD7
0x180029e5e  mov     rcx, [rcx+0B0h]
0x180029e65  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029e6c  mov     edx, 86h
0x180029e71  mov     dword ptr [rsp+58h+var_38], ebx
0x180029e75  call    WPP_SF_Dd
0x180029e7a  jmp     loc_180029DD7
0x180029e7f  lea     rax, [rsp+58h+arg_10]
0x180029e84  xor     r8d, r8d; unsigned __int16
0x180029e87  mov     [rsp+58h+var_30], rax; unsigned int *
0x180029e8c  lea     rcx, [rdi-8]; this
0x180029e90  lea     rax, [rsp+58h+pv]
0x180029e95  mov     r9b, bpl; unsigned __int8
0x180029e98  mov     dl, 1; unsigned __int8
0x180029e9a  mov     [rsp+58h+var_38], rax; unsigned __int8 **
0x180029e9f  call    ?GetFeaturesHelper@CMsftDiscRecorder2@@AEAAJEGEPEAPEAEPEAK@Z; CMsftDiscRecorder2::GetFeaturesHelper(uchar,ushort,uchar,uchar * *,ulong *)
0x180029ea4  mov     ebx, eax
0x180029ea6  test    eax, eax
0x180029ea8  jns     short loc_180029EFB
0x180029eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180029eb1  lea     rax, WPP_GLOBAL_Control
0x180029eb8  cmp     rcx, rax
0x180029ebb  jz      loc_180029DD7
0x180029ec1  test    byte ptr [rcx+0BCh], 4
0x180029ec8  jz      loc_180029DD7
0x180029ece  cmp     byte ptr [rcx+0B9h], 3
0x180029ed5  jb      loc_180029DD7
0x180029edb  mov     rcx, [rcx+0B0h]
0x180029ee2  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029ee9  mov     edx, 87h
0x180029eee  mov     r9d, ebx
0x180029ef1  call    WPP_SF_d
0x180029ef6  jmp     loc_180029DD7
0x180029efb  mov     rcx, [rsp+58h+pv]
0x180029f00  xor     edi, edi
0x180029f02  mov     eax, [rsp+58h+arg_10]
0x180029f06  lea     rdx, [rcx-4]
0x180029f0a  add     rdx, rax
0x180029f0d  jmp     short loc_180029F1C
0x180029f0f  movzx   eax, byte ptr [rcx+3]
0x180029f13  inc     edi
0x180029f15  add     rcx, 4
0x180029f19  add     rcx, rax
0x180029f1c  cmp     rcx, rdx
0x180029f1f  jbe     short loc_180029F0F
0x180029f21  mov     ecx, edi
0x180029f23  shl     rcx, 2; cb
0x180029f27  call    cs:__imp_CoTaskMemAlloc
0x180029f2d  mov     rsi, rax
0x180029f30  test    rax, rax
0x180029f33  jnz     short loc_180029F8F
0x180029f35  mov     ebx, 8007000Eh
0x180029f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f41  lea     rax, WPP_GLOBAL_Control
0x180029f48  cmp     rcx, rax
0x180029f4b  jz      loc_180029DD7
0x180029f51  test    byte ptr [rcx+0BCh], 4
0x180029f58  jz      loc_180029DD7
0x180029f5e  cmp     byte ptr [rcx+0B9h], 3
0x180029f65  jb      loc_180029DD7
0x180029f6b  mov     rcx, [rcx+0B0h]
0x180029f72  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029f79  mov     edx, 88h
0x180029f7e  mov     dword ptr [rsp+58h+var_38], edi
0x180029f82  mov     r9d, edi
0x180029f85  call    WPP_SF_Dd
0x180029f8a  jmp     loc_180029DD7
0x180029f8f  mov     rdx, [rsp+58h+pv]
0x180029f94  xor     r8d, r8d
0x180029f97  test    edi, edi
0x180029f99  jz      short loc_180029FBE
0x180029f9b  movzx   eax, byte ptr [rdx+1]
0x180029f9f  movzx   ecx, byte ptr [rdx]
0x180029fa2  shl     ecx, 8
0x180029fa5  or      ecx, eax
0x180029fa7  mov     [rsi+r8*4], ecx
0x180029fab  inc     r8d
0x180029fae  movzx   eax, byte ptr [rdx+3]
0x180029fb2  add     rdx, 4
0x180029fb6  add     rdx, rax
0x180029fb9  cmp     r8d, edi
0x180029fbc  jb      short loc_180029F9B
0x180029fbe  mov     [r15], rsi
0x180029fc1  mov     [r14], edi
0x180029fc4  jmp     loc_180029DE0
```
