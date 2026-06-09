# DisplayEdidHelpers::GetAdapterAndTargetFromEdid(EdidIdentificationBlock const *,_LUID *,ulong *)

- ea: `0x180090e14`
- end: `0x180090fa2`
- name: `?GetAdapterAndTargetFromEdid@DisplayEdidHelpers@@YAJPEBUEdidIdentificationBlock@@PEAU_LUID@@PEAK@Z`
- size: `398`
- prototype: `__int64 __fastcall(DisplayEdidHelpers *__hidden this, const struct EdidIdentificationBlock *, struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800905cc`

## callees

- `0x18007dc50`
- `0x180090e14`
- `0x1800f0a90`
- `0x1800f246c`
- `0x18013ecf0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180090e4e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180090e4e`
- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180090ec7`
- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180090ec7`

## string_xrefs

- `0x180090e5c`: `onecoreuap\windows\moderncore\inputv2\utilities\inputconfiguration\inputconfigurationhelpers.cpp`
- `0x180090ed5`: `onecoreuap\windows\moderncore\inputv2\utilities\inputconfiguration\inputconfigurationhelpers.cpp`

## pseudocode

```c
__int64 __fastcall DisplayEdidHelpers::GetAdapterAndTargetFromEdid(
        DisplayEdidHelpers *this,
        LUID *a2,
        struct _LUID *a3,
        unsigned int *a4)
{
  unsigned int DisplayConfigBufferSizes; // eax
  DISPLAYCONFIG_PATH_INFO *v9; // rbx
  DISPLAYCONFIG_MODE_INFO *v10; // rdi
  unsigned int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  struct EdidIdentificationBlock *v13; // r9
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // esi
  __int64 i; // rsi
  struct _LUID id; // rdx
  DisplayEdidHelpers *adapterId; // rcx
  unsigned int modeInfoArray; // [rsp+20h] [rbp-38h]
  unsigned int modeInfoArraya; // [rsp+20h] [rbp-38h]
  UINT32 numModeInfoArrayElements[4]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v22[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v23; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  UINT32 numPathArrayElements; // [rsp+B8h] [rbp+60h] BYREF

  numPathArrayElements = 0;
  numModeInfoArrayElements[0] = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x31,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\inputconfiguration\\inputconfigurationhelpers.cpp",
             (const char *)DisplayConfigBufferSizes,
             modeInfoArray);
  v9 = (DISPLAYCONFIG_PATH_INFO *)operator new[](saturated_mul(numPathArrayElements, 0x48u));
  v10 = (DISPLAYCONFIG_MODE_INFO *)operator new[](saturated_mul(numModeInfoArrayElements[0], 0x40u));
  v11 = QueryDisplayConfig(2u, &numPathArrayElements, v9, numModeInfoArrayElements, v10, 0);
  if ( v11 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\inputconfiguration\\inputconfigurationhelpers.cpp",
            (const char *)v11,
            modeInfoArraya);
    if ( v9 )
      operator delete(v9, v14);
    if ( v10 )
      operator delete(v10, v14);
    return v15;
  }
  else
  {
    for ( i = 0; (unsigned int)i < numPathArrayElements; i = (unsigned int)(i + 1) )
    {
      id = (struct _LUID)v9[i].targetInfo.id;
      adapterId = (DisplayEdidHelpers *)v9[i].sourceInfo.adapterId;
      *(_QWORD *)v22 = 0;
      v23 = 0;
      if ( (int)DisplayEdidHelpers::GetRawEdidIdentificationBlock(adapterId, id, (unsigned int)v22, v13) >= 0
        && v22[0] == *(_DWORD *)this
        && v22[1] == *((_DWORD *)this + 1)
        && v23 == *((_WORD *)this + 4) )
      {
        *a2 = v9[i].sourceInfo.adapterId;
        a3->LowPart = v9[i].targetInfo.id;
        break;
      }
    }
    if ( v9 )
      operator delete(v9, v12);
    if ( v10 )
      operator delete(v10, v12);
    return 0;
  }
}

```

## disassembly

```asm
0x180090e14  push    rbp
0x180090e16  push    rbx
0x180090e17  push    rsi
0x180090e18  push    rdi
0x180090e19  push    r12
0x180090e1b  push    r13
0x180090e1d  push    r14
0x180090e1f  push    r15
0x180090e21  mov     rbp, rsp
0x180090e24  sub     rsp, 58h
0x180090e28  mov     r12, r8
0x180090e2b  mov     [rbp+numPathArrayElements], 0
0x180090e32  mov     r13, rdx
0x180090e35  mov     [rbp+numModeInfoArrayElements], 0
0x180090e3c  mov     r14, rcx
0x180090e3f  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x180090e43  mov     esi, 2
0x180090e48  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180090e4c  mov     ecx, esi; flags
0x180090e4e  call    cs:__imp_GetDisplayConfigBufferSizes
0x180090e54  test    eax, eax
0x180090e56  jz      short loc_180090E73
0x180090e58  mov     rcx, [rbp+40h]; this
0x180090e5c  lea     r8, aOnecoreuapWind_83; "onecoreuap\\windows\\moderncore\\inputv"...
0x180090e63  mov     r9d, eax; char *
0x180090e66  lea     edx, [rsi+2Fh]; void *
0x180090e69  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180090e6e  jmp     loc_180090F91
0x180090e73  mov     ecx, [rbp+numPathArrayElements]
0x180090e76  mov     eax, 48h ; 'H'
0x180090e7b  mul     rcx
0x180090e7e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180090e85  cmovb   rax, rdi
0x180090e89  mov     rcx, rax; unsigned __int64
0x180090e8c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180090e91  mov     edx, [rbp+numModeInfoArrayElements]
0x180090e94  mov     rbx, rax
0x180090e97  lea     eax, [rdi+41h]
0x180090e9a  mul     rdx
0x180090e9d  cmovb   rax, rdi
0x180090ea1  mov     rcx, rax; unsigned __int64
0x180090ea4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180090ea9  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x180090ead  mov     [rsp+58h+currentTopologyId], 0; currentTopologyId
0x180090eb6  mov     r8, rbx; pathArray
0x180090eb9  mov     [rsp+58h+modeInfoArray], rax; unsigned int
0x180090ebe  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180090ec2  mov     ecx, esi; flags
0x180090ec4  mov     rdi, rax
0x180090ec7  call    cs:__imp_QueryDisplayConfig
0x180090ecd  test    eax, eax
0x180090ecf  jz      short loc_180090F0C
0x180090ed1  mov     rcx, [rbp+40h]; this
0x180090ed5  lea     r8, aOnecoreuapWind_83; "onecoreuap\\windows\\moderncore\\inputv"...
0x180090edc  mov     r9d, eax; char *
0x180090edf  mov     edx, 3Eh ; '>'; void *
0x180090ee4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180090ee9  mov     esi, eax
0x180090eeb  test    rbx, rbx
0x180090eee  jz      short loc_180090EF8
0x180090ef0  mov     rcx, rbx; void *
0x180090ef3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090ef8  test    rdi, rdi
0x180090efb  jz      short loc_180090F05
0x180090efd  mov     rcx, rdi; void *
0x180090f00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090f05  mov     eax, esi
0x180090f07  jmp     loc_180090F91
0x180090f0c  xor     esi, esi
0x180090f0e  cmp     esi, [rbp+numPathArrayElements]
0x180090f11  jnb     short loc_180090F75
0x180090f13  xor     eax, eax
0x180090f15  lea     r15, [rsi+rsi*8]
0x180090f19  mov     edx, [rbx+r15*8+1Ch]; struct _LUID
0x180090f1e  lea     r8, [rbp+var_18]; unsigned int
0x180090f22  mov     rcx, [rbx+r15*8]; this
0x180090f26  mov     qword ptr [rbp+var_18], rax
0x180090f2a  mov     [rbp+var_10], ax
0x180090f2e  call    ?GetRawEdidIdentificationBlock@DisplayEdidHelpers@@YAJU_LUID@@KPEAUEdidIdentificationBlock@@@Z; DisplayEdidHelpers::GetRawEdidIdentificationBlock(_LUID,ulong,EdidIdentificationBlock *)
0x180090f33  test    eax, eax
0x180090f35  js      short loc_180090F60
0x180090f37  movzx   eax, word ptr [r14]
0x180090f3b  cmp     word ptr [rbp+var_18], ax
0x180090f3f  jnz     short loc_180090F60
0x180090f41  movzx   eax, word ptr [r14+2]
0x180090f46  cmp     word ptr [rbp+var_18+2], ax
0x180090f4a  jnz     short loc_180090F60
0x180090f4c  mov     eax, [r14+4]
0x180090f50  cmp     [rbp+var_18+4], eax
0x180090f53  jnz     short loc_180090F60
0x180090f55  movzx   eax, word ptr [r14+8]
0x180090f5a  cmp     [rbp+var_10], ax
0x180090f5e  jz      short loc_180090F64
0x180090f60  inc     esi
0x180090f62  jmp     short loc_180090F0E
0x180090f64  mov     rax, [rbx+r15*8]
0x180090f68  mov     [r13+0], rax
0x180090f6c  mov     eax, [rbx+r15*8+1Ch]
0x180090f71  mov     [r12], eax
0x180090f75  test    rbx, rbx
0x180090f78  jz      short loc_180090F82
0x180090f7a  mov     rcx, rbx; void *
0x180090f7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090f82  test    rdi, rdi
0x180090f85  jz      short loc_180090F8F
0x180090f87  mov     rcx, rdi; void *
0x180090f8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180090f8f  xor     eax, eax
0x180090f91  add     rsp, 58h
0x180090f95  pop     r15
0x180090f97  pop     r14
0x180090f99  pop     r13
0x180090f9b  pop     r12
0x180090f9d  pop     rdi
0x180090f9e  pop     rsi
0x180090f9f  pop     rbx
0x180090fa0  pop     rbp
0x180090fa1  retn
```
