# DllUnregisterServer

- ea: `0x180009f20`
- end: `0x18000a01b`
- name: `DllUnregisterServer`
- size: `251`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007bd4`
- `0x1800082ac`
- `0x180009f20`
- `0x180019010`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v1; // rax
  int v2; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rbx
  __int64 *v4; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  v0 = qword_180022B48;
  if ( qword_180022B48 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0);
      if ( v2 < 0 )
        goto LABEL_17;
      v2 = (*(__int64 (__fastcall **)(_QWORD))(v0 + 8))(0);
      if ( v2 < 0 )
        goto LABEL_17;
      v0 += 72;
    }
  }
  if ( ATL::_pPerfUnRegFunc && (v2 = ATL::_pPerfUnRegFunc(), v2 < 0) )
  {
LABEL_17:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        15,
        WPP_0a790e4df2ea300a977d38634cc427f5_Traceguids,
        (unsigned int)v2);
  }
  else
  {
    v3 = off_1800213E0;
    v4 = off_1800213E8;
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
    {
      v5 = *v3;
      if ( *v3 )
      {
        v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
        v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 0);
        if ( v2 < 0 )
          goto LABEL_17;
        v2 = (*((__int64 (__fastcall **)(_QWORD))v5 + 1))(0);
        if ( v2 < 0 )
          goto LABEL_17;
        v4 = off_1800213E8;
      }
      ++v3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009f20  mov     [rsp+arg_0], rbx
0x180009f25  push    rdi
0x180009f26  sub     rsp, 20h
0x180009f2a  mov     rbx, cs:qword_180022B48
0x180009f31  test    rbx, rbx
0x180009f34  jz      short loc_180009F70
0x180009f36  jmp     short loc_180009F6A
0x180009f38  mov     rax, [rbx+38h]
0x180009f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f41  mov     rcx, [rbx]; rguid
0x180009f44  xor     r8d, r8d; int
0x180009f47  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009f4a  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009f4f  test    eax, eax
0x180009f51  js      loc_180009FDD
0x180009f57  mov     rax, [rbx+8]
0x180009f5b  xor     ecx, ecx
0x180009f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f62  test    eax, eax
0x180009f64  js      short loc_180009FDD
0x180009f66  add     rbx, 48h ; 'H'
0x180009f6a  cmp     qword ptr [rbx], 0
0x180009f6e  jnz     short loc_180009F38
0x180009f70  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180009f77  test    rax, rax
0x180009f7a  jz      short loc_180009F85
0x180009f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f81  test    eax, eax
0x180009f83  js      short loc_180009FDD
0x180009f85  mov     rbx, cs:off_1800213E0
0x180009f8c  xor     eax, eax
0x180009f8e  mov     rcx, cs:off_1800213E8
0x180009f95  jmp     short loc_180009FD4
0x180009f97  mov     rdi, [rbx]
0x180009f9a  test    rdi, rdi
0x180009f9d  jz      short loc_180009FD0
0x180009f9f  mov     rax, [rdi+38h]
0x180009fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fa8  mov     rcx, [rdi]; rguid
0x180009fab  xor     r8d, r8d; int
0x180009fae  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009fb1  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009fb6  test    eax, eax
0x180009fb8  js      short loc_180009FDD
0x180009fba  mov     rax, [rdi+8]
0x180009fbe  xor     ecx, ecx
0x180009fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc5  test    eax, eax
0x180009fc7  js      short loc_180009FDD
0x180009fc9  mov     rcx, cs:off_1800213E8
0x180009fd0  add     rbx, 8
0x180009fd4  cmp     rbx, rcx
0x180009fd7  jb      short loc_180009F97
0x180009fd9  test    eax, eax
0x180009fdb  jns     short loc_18000A00E
0x180009fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fe4  lea     rdx, WPP_GLOBAL_Control
0x180009feb  cmp     rcx, rdx
0x180009fee  jz      short loc_18000A00E
0x180009ff0  test    byte ptr [rcx+44h], 1
0x180009ff4  jz      short loc_18000A00E
0x180009ff6  mov     rcx, [rcx+38h]
0x180009ffa  lea     r8, WPP_0a790e4df2ea300a977d38634cc427f5_Traceguids
0x18000a001  mov     edx, 0Fh
0x18000a006  mov     r9d, eax
0x18000a009  call    WPP_SF_d
0x18000a00e  mov     rbx, [rsp+28h+arg_0]
0x18000a013  xor     eax, eax
0x18000a015  add     rsp, 20h
0x18000a019  pop     rdi
0x18000a01a  retn
```
