# Microsoft::Resources::RegionQualifierType::InnerCompare(Microsoft::Resources::IQualifier const *,Microsoft::Resources::IQualifier const *,_DEFCOMPARISON *)

- ea: `0x1800bad50`
- end: `0x1800bae7f`
- name: `?InnerCompare@RegionQualifierType@Resources@Microsoft@@MEBAJPEBVIQualifier@23@0PEAW4_DEFCOMPARISON@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(Microsoft::Resources::RegionQualifierType *__hidden this, const struct Microsoft::Resources::IQualifier *, const struct Microsoft::Resources::IQualifier *, enum _DEFCOMPARISON *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180027270`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x18004e050`
- `0x1800bad50`
- `0x1800c5010`

## import_xrefs

- `bcp47mrm!GetParentCompositeRegionCode` at `0x1800bae0d`
- `bcp47mrm!GetParentCompositeRegionCode` at `0x1800bae17`
- `bcp47mrm!GetParentCompositeRegionCode` at `0x1800bae0d`
- `bcp47mrm!GetParentCompositeRegionCode` at `0x1800bae17`
- `bcp47mrm!GetCompositeRegionCode` at `0x1800badea`
- `bcp47mrm!GetCompositeRegionCode` at `0x1800badff`
- `bcp47mrm!GetCompositeRegionCode` at `0x1800badea`
- `bcp47mrm!GetCompositeRegionCode` at `0x1800badff`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::RegionQualifierType::InnerCompare(
        Microsoft::Resources::RegionQualifierType *this,
        const struct Microsoft::Resources::IQualifier *a2,
        const struct Microsoft::Resources::IQualifier *a3,
        enum _DEFCOMPARISON *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const unsigned __int16 *Ref; // rax
  unsigned int CompositeRegionCode; // ebx
  const unsigned __int16 *v13; // rax
  unsigned int i; // eax
  unsigned int v15; // edi
  int v16; // ebx
  int v18[8]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v19[88]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_DWORD *)a4 = 0x7FFFFFFF;
  Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)v19);
  Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)v18);
  v8 = (*(__int64 (__fastcall **)(const struct Microsoft::Resources::IQualifier *, _BYTE *))(*(_QWORD *)a2 + 56LL))(
         a2,
         v19);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(const struct Microsoft::Resources::IQualifier *, int *))(*(_QWORD *)a3 + 56LL))(
           a3,
           v18);
    v9 = v8;
    if ( v8 >= 0 )
    {
      Ref = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v19);
      CompositeRegionCode = GetCompositeRegionCode(Ref);
      v13 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v18);
      for ( i = GetCompositeRegionCode(v13); ; i = GetParentCompositeRegionCode(v15) )
      {
        v15 = i;
        if ( !CompositeRegionCode || !i )
          break;
        CompositeRegionCode = GetParentCompositeRegionCode(CompositeRegionCode);
      }
      v16 = CompositeRegionCode - i;
      if ( v16 <= 0 )
      {
        if ( v16 >= 0 )
        {
          v8 = Microsoft::Resources::QualifierTypeBase::InnerCompare(this, a2, a3, a4);
          v9 = v8;
          if ( v8 < 0 )
          {
            v10 = 344;
            goto LABEL_5;
          }
        }
        else
        {
          *(_DWORD *)a4 = -1;
        }
      }
      else
      {
        *(_DWORD *)a4 = 1;
      }
      v9 = 0;
      goto LABEL_13;
    }
    v10 = 321;
  }
  else
  {
    v10 = 320;
  }
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\qualifiertypes.cpp",
    (const char *)(unsigned int)v8,
    v18[0]);
LABEL_13:
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v18);
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v19);
  return v9;
}

```

## disassembly

```asm
0x1800bad50  push    rbx
0x1800bad52  push    rbp
0x1800bad53  push    rsi
0x1800bad54  push    rdi
0x1800bad55  push    r14
0x1800bad57  push    r15
0x1800bad59  sub     rsp, 68h
0x1800bad5d  mov     rbp, rcx
0x1800bad60  mov     dword ptr [r9], 7FFFFFFFh
0x1800bad67  lea     rcx, [rsp+98h+var_58]; this
0x1800bad6c  mov     rsi, r9
0x1800bad6f  mov     r14, r8
0x1800bad72  mov     r15, rdx
0x1800bad75  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x1800bad7a  lea     rcx, [rsp+98h+var_78]; this
0x1800bad7f  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x1800bad84  mov     rax, [r15]
0x1800bad87  lea     rdx, [rsp+98h+var_58]
0x1800bad8c  mov     rcx, r15
0x1800bad8f  mov     rax, [rax+38h]
0x1800bad93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad98  mov     ebx, eax
0x1800bad9a  test    eax, eax
0x1800bad9c  jns     short loc_1800BADA5
0x1800bad9e  mov     edx, 140h
0x1800bada3  jmp     short loc_1800BADC4
0x1800bada5  mov     rax, [r14]
0x1800bada8  lea     rdx, [rsp+98h+var_78]
0x1800badad  mov     rcx, r14
0x1800badb0  mov     rax, [rax+38h]
0x1800badb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800badb9  mov     ebx, eax
0x1800badbb  test    eax, eax
0x1800badbd  jns     short loc_1800BADDD
0x1800badbf  mov     edx, 141h; void *
0x1800badc4  mov     rcx, [rsp+98h]; this
0x1800badcc  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\mrt\\mrm\\src\\qualif"...
0x1800badd3  mov     r9d, eax; char *
0x1800badd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baddb  jmp     short loc_1800BAE31
0x1800baddd  lea     rcx, [rsp+98h+var_58]; this
0x1800bade2  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800bade7  mov     rcx, rax
0x1800badea  call    cs:__imp_GetCompositeRegionCode
0x1800badf0  lea     rcx, [rsp+98h+var_78]; this
0x1800badf5  mov     ebx, eax
0x1800badf7  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800badfc  mov     rcx, rax
0x1800badff  call    cs:__imp_GetCompositeRegionCode
0x1800bae05  jmp     short loc_1800BAE1D
0x1800bae07  test    edi, edi
0x1800bae09  jz      short loc_1800BAE23
0x1800bae0b  mov     ecx, ebx
0x1800bae0d  call    cs:__imp_GetParentCompositeRegionCode
0x1800bae13  mov     ecx, edi
0x1800bae15  mov     ebx, eax
0x1800bae17  call    cs:__imp_GetParentCompositeRegionCode
0x1800bae1d  mov     edi, eax
0x1800bae1f  test    ebx, ebx
0x1800bae21  jnz     short loc_1800BAE07
0x1800bae23  sub     ebx, edi
0x1800bae25  test    ebx, ebx
0x1800bae27  jle     short loc_1800BAE54
0x1800bae29  mov     dword ptr [rsi], 1
0x1800bae2f  xor     ebx, ebx
0x1800bae31  lea     rcx, [rsp+98h+var_78]; this
0x1800bae36  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800bae3b  lea     rcx, [rsp+98h+var_58]; this
0x1800bae40  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800bae45  mov     eax, ebx
0x1800bae47  add     rsp, 68h
0x1800bae4b  pop     r15
0x1800bae4d  pop     r14
0x1800bae4f  pop     rdi
0x1800bae50  pop     rsi
0x1800bae51  pop     rbp
0x1800bae52  pop     rbx
0x1800bae53  retn
0x1800bae54  jns     short loc_1800BAE5E
0x1800bae56  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800bae5c  jmp     short loc_1800BAE2F
0x1800bae5e  mov     r9, rsi; enum _DEFCOMPARISON *
0x1800bae61  mov     r8, r14; struct Microsoft::Resources::IQualifier *
0x1800bae64  mov     rdx, r15; struct Microsoft::Resources::IQualifier *
0x1800bae67  mov     rcx, rbp; this
0x1800bae6a  call    ?InnerCompare@QualifierTypeBase@Resources@Microsoft@@MEBAJPEBVIQualifier@23@0PEAW4_DEFCOMPARISON@@@Z; Microsoft::Resources::QualifierTypeBase::InnerCompare(Microsoft::Resources::IQualifier const *,Microsoft::Resources::IQualifier const *,_DEFCOMPARISON *)
0x1800bae6f  mov     ebx, eax
0x1800bae71  test    eax, eax
0x1800bae73  jns     short loc_1800BAE2F
0x1800bae75  mov     edx, 158h
0x1800bae7a  jmp     loc_1800BADC4
```
