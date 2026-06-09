# CMSDiscMasterObj::InitInterfaceJoliet(void)

- ea: `0x180006e50`
- end: `0x180007014`
- name: `?InitInterfaceJoliet@CMSDiscMasterObj@@QEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b650`

## callees

- `0x180002ac4`
- `0x18000689c`
- `0x180006e50`
- `0x180007bac`
- `0x180007bd4`
- `0x1800127ec`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180006ec6`
- `ole32!CoCreateInstance` at `0x180006ec6`
- `OLEAUT32!__imp_SysAllocString` at `0x180006f58`
- `OLEAUT32!__imp_SysAllocString` at `0x180006f58`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f4f`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::InitInterfaceJoliet(CMSDiscMasterObj *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  HRESULT Instance; // eax
  unsigned int v5; // edi
  int v6; // eax
  const OLECHAR *v7; // rdx
  BSTR v8; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
  v2 = (_QWORD *)((char *)this + 488);
  v3 = *((_QWORD *)this + 61);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *v2 = 0;
  }
  Instance = CoCreateInstance(
               &GUID_2c941fc5_975b_59be_a960_9a2a262853a5,
               0,
               0x17u,
               &GUID_2c941fe1_975b_59be_a960_9a2a262853a5,
               (LPVOID *)this + 61);
  v5 = Instance;
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        30,
        &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
        (unsigned int)Instance);
    return v5;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v2 + 120LL))(*v2, *((_QWORD *)this + 55));
  v5 = v6;
  if ( v6 >= 0 )
    goto LABEL_20;
  if ( v6 == -1062555388 && *((_BYTE *)this + 448) )
  {
    v7 = (const OLECHAR *)*((_QWORD *)this + 55);
    if ( &word_18001BDF8 != v7 )
    {
      SysFreeString(*((BSTR *)this + 55));
      v8 = SysAllocString(&word_18001BDF8);
      *((_QWORD *)this + 55) = v8;
      v7 = v8;
      if ( !v8 )
        ATL::AtlThrowImpl(-2147024882);
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *))(*(_QWORD *)*v2 + 120LL))(*v2, v7);
    if ( (v5 & 0x80000000) == 0 )
    {
LABEL_20:
      CMSDiscMasterObj::GetRegistryValues(this);
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 232LL))(*v2, 3);
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 88LL))(*v2, 333000);
      *((_DWORD *)this + 126) = 1;
      *((_BYTE *)this + 508) = 0;
      return v5;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, v5);
  return TranslateIMAPI2Error(v5);
}

```

## disassembly

```asm
0x180006e50  push    rbx
0x180006e52  push    rsi
0x180006e53  push    rdi
0x180006e54  push    r15
0x180006e56  sub     rsp, 38h
0x180006e5a  mov     rbx, rcx
0x180006e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e64  lea     r15, WPP_GLOBAL_Control
0x180006e6b  cmp     rcx, r15
0x180006e6e  jz      short loc_180006E8B
0x180006e70  test    byte ptr [rcx+44h], 1
0x180006e74  jz      short loc_180006E8B
0x180006e76  mov     rcx, [rcx+38h]
0x180006e7a  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006e81  mov     edx, 1Dh
0x180006e86  call    WPP_SF_
0x180006e8b  lea     rsi, [rbx+1E8h]
0x180006e92  mov     rcx, [rsi]
0x180006e95  test    rcx, rcx
0x180006e98  jz      short loc_180006EAD
0x180006e9a  mov     rax, [rcx]
0x180006e9d  mov     rax, [rax+10h]
0x180006ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea6  mov     qword ptr [rsi], 0
0x180006ead  xor     edx, edx; pUnkOuter
0x180006eaf  mov     [rsp+58h+ppv], rsi; ppv
0x180006eb4  lea     r9, _GUID_2c941fe1_975b_59be_a960_9a2a262853a5; riid
0x180006ebb  lea     rcx, _GUID_2c941fc5_975b_59be_a960_9a2a262853a5; rclsid
0x180006ec2  lea     r8d, [rdx+17h]; dwClsContext
0x180006ec6  call    cs:__imp_CoCreateInstance
0x180006ecc  mov     edi, eax
0x180006ece  test    eax, eax
0x180006ed0  jns     short loc_180006F09
0x180006ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ed9  cmp     rcx, r15
0x180006edc  jz      loc_180006FFD
0x180006ee2  test    byte ptr [rcx+44h], 1
0x180006ee6  jz      loc_180006FFD
0x180006eec  mov     rcx, [rcx+38h]
0x180006ef0  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006ef7  mov     edx, 1Eh
0x180006efc  mov     r9d, eax
0x180006eff  call    WPP_SF_d
0x180006f04  jmp     loc_180006FFD
0x180006f09  mov     rcx, [rsi]
0x180006f0c  mov     rdx, [rbx+1B8h]
0x180006f13  mov     rax, [rcx]
0x180006f16  mov     rax, [rax+78h]
0x180006f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1f  mov     edi, eax
0x180006f21  test    eax, eax
0x180006f23  jns     loc_180006FB9
0x180006f29  cmp     eax, 0C0AAB104h
0x180006f2e  jnz     short loc_180006F86
0x180006f30  cmp     byte ptr [rbx+1C0h], 0
0x180006f37  jz      short loc_180006F86
0x180006f39  mov     rdx, [rbx+1B8h]
0x180006f40  lea     rdi, word_18001BDF8
0x180006f47  cmp     rdi, rdx
0x180006f4a  jz      short loc_180006F71
0x180006f4c  mov     rcx, rdx; bstrString
0x180006f4f  call    cs:__imp_SysFreeString
0x180006f55  mov     rcx, rdi; psz
0x180006f58  call    cs:__imp_SysAllocString
0x180006f5e  mov     [rbx+1B8h], rax
0x180006f65  mov     rdx, rax
0x180006f68  test    rax, rax
0x180006f6b  jz      loc_180007009
0x180006f71  mov     rcx, [rsi]
0x180006f74  mov     rax, [rcx]
0x180006f77  mov     rax, [rax+78h]
0x180006f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f80  mov     edi, eax
0x180006f82  test    eax, eax
0x180006f84  jns     short loc_180006FB9
0x180006f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f8d  cmp     rcx, r15
0x180006f90  jz      short loc_180006FB0
0x180006f92  test    byte ptr [rcx+44h], 1
0x180006f96  jz      short loc_180006FB0
0x180006f98  mov     rcx, [rcx+38h]
0x180006f9c  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006fa3  mov     edx, 1Fh
0x180006fa8  mov     r9d, edi
0x180006fab  call    WPP_SF_d
0x180006fb0  mov     ecx, edi
0x180006fb2  call    TranslateIMAPI2Error
0x180006fb7  jmp     short loc_180006FFF
0x180006fb9  mov     rcx, rbx; this
0x180006fbc  call    ?GetRegistryValues@CMSDiscMasterObj@@AEAAHXZ; CMSDiscMasterObj::GetRegistryValues(void)
0x180006fc1  mov     rcx, [rsi]
0x180006fc4  mov     edx, 3
0x180006fc9  mov     rax, [rcx]
0x180006fcc  mov     rax, [rax+0E8h]
0x180006fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd8  mov     rcx, [rsi]
0x180006fdb  mov     edx, 514C8h
0x180006fe0  mov     rax, [rcx]
0x180006fe3  mov     rax, [rax+58h]
0x180006fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fec  mov     dword ptr [rbx+1F8h], 1
0x180006ff6  mov     byte ptr [rbx+1FCh], 0
0x180006ffd  mov     eax, edi
0x180006fff  add     rsp, 38h
0x180007003  pop     r15
0x180007005  pop     rdi
0x180007006  pop     rsi
0x180007007  pop     rbx
0x180007008  retn
0x180007009  mov     ecx, 8007000Eh; int
0x18000700e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
