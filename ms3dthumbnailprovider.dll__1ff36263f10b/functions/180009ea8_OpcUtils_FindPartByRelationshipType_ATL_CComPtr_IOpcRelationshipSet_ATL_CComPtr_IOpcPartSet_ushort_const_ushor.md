# OpcUtils::FindPartByRelationshipType(ATL::CComPtr<IOpcRelationshipSet> &,ATL::CComPtr<IOpcPartSet> &,ushort const *,ushort const *,ATL::CComPtr<IOpcPart> &)

- ea: `0x180009ea8`
- end: `0x18000a157`
- name: `?FindPartByRelationshipType@OpcUtils@@YAJAEAV?$CComPtr@UIOpcRelationshipSet@@@ATL@@AEAV?$CComPtr@UIOpcPartSet@@@3@PEBG2AEAV?$CComPtr@UIOpcPart@@@3@@Z`
- size: `687`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64, unsigned __int16 *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009dd4`

## callees

- `0x180009ea8`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000a0c7`
- `ole32!CoTaskMemFree` at `0x18000a0c7`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a093`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a09f`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a0b1`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a0bd`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a093`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a09f`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a0b1`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a0bd`

## string_xrefs

- `0x180009eda`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`

## pseudocode

```c
__int64 __fastcall OpcUtils::FindPartByRelationshipType(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned __int16 *a4,
        _QWORD *a5)
{
  int v7; // ebx
  _QWORD *v8; // rdi
  unsigned __int16 *v9; // rax
  int v10; // r8d
  int v11; // edx
  int v13; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+28h] [rbp-40h] BYREF
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv[3]; // [rsp+50h] [rbp-18h] BYREF
  int v20; // [rsp+B0h] [rbp+48h] BYREF
  int v21; // [rsp+B4h] [rbp+4Ch]

  v21 = HIDWORD(a3);
  v16 = 0;
  v20 = 1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(*(_QWORD *)*a1 + 64LL))(
         *a1,
         L"http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail",
         &v16);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 24LL))(v16, &v20);
    if ( v7 >= 0 )
    {
      v8 = a5;
      do
      {
        if ( !v20 || *v8 )
          break;
        v17 = 0;
        v15 = 0;
        v13 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 40LL))(v16, &v15);
        if ( v7 >= 0 )
        {
          pv[0] = 0;
          v18 = 0;
          LODWORD(v14) = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 56LL))(v15, &v14);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, &v18);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 40LL))(v15, pv);
              if ( v7 >= 0 )
                v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)pv[0] + 240LL))(
                       pv[0],
                       v18,
                       &v17);
            }
          }
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          if ( pv[0] )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(*(_QWORD *)*a2 + 48LL))(*a2, v17, &v13);
            if ( v7 >= 0 )
            {
              if ( !v13 )
                goto LABEL_30;
              pv[0] = 0;
              v14 = 0;
              v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)*a2 + 24LL))(*a2, v17, &v14);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 48LL))(v14, pv);
                if ( v7 >= 0 )
                {
                  v9 = a4;
                  do
                  {
                    v10 = *(unsigned __int16 *)((char *)v9 + (char *)pv[0] - (char *)a4);
                    v11 = *v9 - v10;
                    if ( v11 )
                      break;
                    ++v9;
                  }
                  while ( v10 );
                  if ( !v11 )
                  {
                    AtlComPtrAssign(v8, v14);
                    AtlComPtrAssign(&v14, 0);
                  }
                  if ( !a4 )
                  {
                    AtlComPtrAssign(v8, v14);
                    AtlComPtrAssign(&v14, 0);
                  }
                }
              }
              CoTaskMemFree(pv[0]);
              if ( v14 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              if ( v7 >= 0 )
LABEL_30:
                v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 24LL))(v16, &v20);
            }
          }
        }
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      while ( v7 >= 0 );
    }
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009ea8  mov     [rsp-30h+arg_10], r8
0x180009ead  push    rbp
0x180009eae  push    rbx
0x180009eaf  push    rsi
0x180009eb0  push    rdi
0x180009eb1  push    r14
0x180009eb3  push    r15
0x180009eb5  mov     rbp, rsp
0x180009eb8  sub     rsp, 68h
0x180009ebc  mov     rsi, r9
0x180009ebf  mov     r14, rdx
0x180009ec2  xor     r15d, r15d
0x180009ec5  mov     [rbp+var_30], r15
0x180009ec9  mov     dword ptr [rbp+arg_10], 1
0x180009ed0  mov     rcx, [rcx]
0x180009ed3  mov     rax, [rcx]
0x180009ed6  lea     r8, [rbp+var_30]
0x180009eda  lea     rdx, aHttpSchemasOpe; "http://schemas.openxmlformats.org/packa"...
0x180009ee1  mov     rax, [rax+40h]
0x180009ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eea  mov     ebx, eax
0x180009eec  test    eax, eax
0x180009eee  js      loc_18000A132
0x180009ef4  mov     rcx, [rbp+var_30]
0x180009ef8  mov     rax, [rcx]
0x180009efb  lea     rdx, [rbp+arg_10]
0x180009eff  mov     rax, [rax+18h]
0x180009f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f08  mov     ebx, eax
0x180009f0a  test    eax, eax
0x180009f0c  js      loc_18000A132
0x180009f12  mov     rdi, [rbp+arg_20]
0x180009f16  cmp     dword ptr [rbp+arg_10], r15d
0x180009f1a  jz      loc_18000A132
0x180009f20  cmp     [rdi], r15
0x180009f23  jnz     loc_18000A132
0x180009f29  mov     [rbp+var_28], r15
0x180009f2d  mov     [rbp+var_38], r15
0x180009f31  mov     [rbp+var_48], r15d
0x180009f35  mov     rcx, [rbp+var_30]
0x180009f39  mov     rax, [rcx]
0x180009f3c  lea     rdx, [rbp+var_38]
0x180009f40  mov     rax, [rax+28h]
0x180009f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f49  mov     ebx, eax
0x180009f4b  test    eax, eax
0x180009f4d  js      loc_18000A0FE
0x180009f53  mov     [rbp+pv], r15
0x180009f57  mov     [rbp+var_20], r15
0x180009f5b  mov     dword ptr [rbp+var_40], r15d
0x180009f5f  mov     rcx, [rbp+var_38]
0x180009f63  mov     rax, [rcx]
0x180009f66  lea     rdx, [rbp+var_40]
0x180009f6a  mov     rax, [rax+38h]
0x180009f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f73  mov     ebx, eax
0x180009f75  test    eax, eax
0x180009f77  js      short loc_180009FCA
0x180009f79  mov     rcx, [rbp+var_38]
0x180009f7d  mov     rax, [rcx]
0x180009f80  lea     rdx, [rbp+var_20]
0x180009f84  mov     rax, [rax+30h]
0x180009f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f8d  mov     ebx, eax
0x180009f8f  test    eax, eax
0x180009f91  js      short loc_180009FCA
0x180009f93  mov     rcx, [rbp+var_38]
0x180009f97  mov     rax, [rcx]
0x180009f9a  lea     rdx, [rbp+pv]
0x180009f9e  mov     rax, [rax+28h]
0x180009fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fa7  mov     ebx, eax
0x180009fa9  test    eax, eax
0x180009fab  js      short loc_180009FCA
0x180009fad  mov     rcx, [rbp+pv]
0x180009fb1  mov     rax, [rcx]
0x180009fb4  lea     r8, [rbp+var_28]
0x180009fb8  mov     rdx, [rbp+var_20]
0x180009fbc  mov     rax, [rax+0F0h]
0x180009fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc8  mov     ebx, eax
0x180009fca  mov     rcx, [rbp+var_20]
0x180009fce  test    rcx, rcx
0x180009fd1  jz      short loc_180009FE0
0x180009fd3  mov     rax, [rcx]
0x180009fd6  mov     rax, [rax+10h]
0x180009fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fdf  nop
0x180009fe0  mov     rcx, [rbp+pv]
0x180009fe4  test    rcx, rcx
0x180009fe7  jz      short loc_180009FF6
0x180009fe9  mov     rax, [rcx]
0x180009fec  mov     rax, [rax+10h]
0x180009ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff5  nop
0x180009ff6  test    ebx, ebx
0x180009ff8  js      loc_18000A0FE
0x180009ffe  mov     rcx, [r14]
0x18000a001  mov     rax, [rcx]
0x18000a004  lea     r8, [rbp+var_48]
0x18000a008  mov     rdx, [rbp+var_28]
0x18000a00c  mov     rax, [rax+30h]
0x18000a010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a015  mov     ebx, eax
0x18000a017  test    eax, eax
0x18000a019  js      loc_18000A0FE
0x18000a01f  cmp     [rbp+var_48], r15d
0x18000a023  jz      loc_18000A0E8
0x18000a029  mov     [rbp+pv], r15
0x18000a02d  mov     [rbp+var_40], r15
0x18000a031  mov     rcx, [r14]
0x18000a034  mov     rax, [rcx]
0x18000a037  lea     r8, [rbp+var_40]
0x18000a03b  mov     rdx, [rbp+var_28]
0x18000a03f  mov     rax, [rax+18h]
0x18000a043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a048  mov     ebx, eax
0x18000a04a  test    eax, eax
0x18000a04c  js      short loc_18000A0C3
0x18000a04e  mov     rcx, [rbp+var_40]
0x18000a052  mov     rax, [rcx]
0x18000a055  lea     rdx, [rbp+pv]
0x18000a059  mov     rax, [rax+30h]
0x18000a05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a062  mov     ebx, eax
0x18000a064  test    eax, eax
0x18000a066  js      short loc_18000A0C3
0x18000a068  mov     rax, rsi
0x18000a06b  mov     rcx, [rbp+pv]
0x18000a06f  sub     rcx, rsi
0x18000a072  movzx   edx, word ptr [rax]
0x18000a075  movzx   r8d, word ptr [rax+rcx]
0x18000a07a  sub     edx, r8d
0x18000a07d  jnz     short loc_18000A088
0x18000a07f  add     rax, 2
0x18000a083  test    r8d, r8d
0x18000a086  jnz     short loc_18000A072
0x18000a088  test    edx, edx
0x18000a08a  jnz     short loc_18000A0A5
0x18000a08c  mov     rdx, [rbp+var_40]
0x18000a090  mov     rcx, rdi
0x18000a093  call    cs:__imp_AtlComPtrAssign
0x18000a099  xor     edx, edx
0x18000a09b  lea     rcx, [rbp+var_40]
0x18000a09f  call    cs:__imp_AtlComPtrAssign
0x18000a0a5  test    rsi, rsi
0x18000a0a8  jnz     short loc_18000A0C3
0x18000a0aa  mov     rdx, [rbp+var_40]
0x18000a0ae  mov     rcx, rdi
0x18000a0b1  call    cs:__imp_AtlComPtrAssign
0x18000a0b7  xor     edx, edx
0x18000a0b9  lea     rcx, [rbp+var_40]
0x18000a0bd  call    cs:__imp_AtlComPtrAssign
0x18000a0c3  mov     rcx, [rbp+pv]; pv
0x18000a0c7  call    cs:__imp_CoTaskMemFree
0x18000a0cd  nop
0x18000a0ce  mov     rcx, [rbp+var_40]
0x18000a0d2  test    rcx, rcx
0x18000a0d5  jz      short loc_18000A0E4
0x18000a0d7  mov     rax, [rcx]
0x18000a0da  mov     rax, [rax+10h]
0x18000a0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e3  nop
0x18000a0e4  test    ebx, ebx
0x18000a0e6  js      short loc_18000A0FE
0x18000a0e8  mov     rcx, [rbp+var_30]
0x18000a0ec  mov     rax, [rcx]
0x18000a0ef  lea     rdx, [rbp+arg_10]
0x18000a0f3  mov     rax, [rax+18h]
0x18000a0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fc  mov     ebx, eax
0x18000a0fe  mov     rcx, [rbp+var_38]
0x18000a102  test    rcx, rcx
0x18000a105  jz      short loc_18000A114
0x18000a107  mov     rax, [rcx]
0x18000a10a  mov     rax, [rax+10h]
0x18000a10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a113  nop
0x18000a114  mov     rcx, [rbp+var_28]
0x18000a118  test    rcx, rcx
0x18000a11b  jz      short loc_18000A12A
0x18000a11d  mov     rax, [rcx]
0x18000a120  mov     rax, [rax+10h]
0x18000a124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a129  nop
0x18000a12a  test    ebx, ebx
0x18000a12c  jns     loc_180009F16
0x18000a132  mov     rcx, [rbp+var_30]
0x18000a136  test    rcx, rcx
0x18000a139  jz      short loc_18000A148
0x18000a13b  mov     rax, [rcx]
0x18000a13e  mov     rax, [rax+10h]
0x18000a142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a147  nop
0x18000a148  mov     eax, ebx
0x18000a14a  add     rsp, 68h
0x18000a14e  pop     r15
0x18000a150  pop     r14
0x18000a152  pop     rdi
0x18000a153  pop     rsi
0x18000a154  pop     rbx
0x18000a155  pop     rbp
0x18000a156  retn
```
