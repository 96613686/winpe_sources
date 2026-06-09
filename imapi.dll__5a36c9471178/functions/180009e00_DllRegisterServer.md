# DllRegisterServer

- ea: `0x180009e00`
- end: `0x180009f15`
- name: `DllRegisterServer`
- size: `277`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007bd4`
- `0x1800082ac`
- `0x180009e00`
- `0x180019010`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rbx
  int v1; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rbx
  __int64 *v4; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  v0 = qword_180022B48;
  if ( qword_180022B48 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64))(v0 + 8))(1);
      if ( v1 < 0 )
        goto LABEL_17;
      v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v2, 1);
      if ( v1 < 0 )
        goto LABEL_17;
      v0 += 72;
    }
  }
  v3 = off_1800213E0;
  v1 = 0;
  v4 = off_1800213E8;
  while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      v1 = (*((__int64 (__fastcall **)(__int64))v5 + 1))(1);
      if ( v1 < 0 )
        goto LABEL_17;
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v5 + 7))();
      v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v5, v6, 1);
      if ( v1 < 0 )
        goto LABEL_17;
      v4 = off_1800213E8;
    }
    ++v3;
  }
  if ( ATL::_pPerfRegFunc )
    v1 = ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hInstance);
  if ( v1 < 0 )
  {
LABEL_17:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        14,
        WPP_0a790e4df2ea300a977d38634cc427f5_Traceguids,
        (unsigned int)v1);
  }
  return 0;
}

```

## disassembly

```asm
0x180009e00  mov     [rsp+arg_0], rbx
0x180009e05  push    rdi
0x180009e06  sub     rsp, 20h
0x180009e0a  mov     rbx, cs:qword_180022B48
0x180009e11  test    rbx, rbx
0x180009e14  jz      short loc_180009E5A
0x180009e16  jmp     short loc_180009E54
0x180009e18  mov     rax, [rbx+8]
0x180009e1c  mov     ecx, 1
0x180009e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e26  test    eax, eax
0x180009e28  js      loc_180009ED7
0x180009e2e  mov     rax, [rbx+38h]
0x180009e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e37  mov     rcx, [rbx]; rguid
0x180009e3a  mov     r8d, 1; int
0x180009e40  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009e43  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009e48  test    eax, eax
0x180009e4a  js      loc_180009ED7
0x180009e50  add     rbx, 48h ; 'H'
0x180009e54  cmp     qword ptr [rbx], 0
0x180009e58  jnz     short loc_180009E18
0x180009e5a  mov     rbx, cs:off_1800213E0
0x180009e61  xor     eax, eax
0x180009e63  mov     rcx, cs:off_1800213E8
0x180009e6a  jmp     short loc_180009EAF
0x180009e6c  mov     rdi, [rbx]
0x180009e6f  test    rdi, rdi
0x180009e72  jz      short loc_180009EAB
0x180009e74  mov     rax, [rdi+8]
0x180009e78  mov     ecx, 1
0x180009e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e82  test    eax, eax
0x180009e84  js      short loc_180009ED7
0x180009e86  mov     rax, [rdi+38h]
0x180009e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e8f  mov     rcx, [rdi]; rguid
0x180009e92  mov     r8d, 1; int
0x180009e98  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009e9b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009ea0  test    eax, eax
0x180009ea2  js      short loc_180009ED7
0x180009ea4  mov     rcx, cs:off_1800213E8
0x180009eab  add     rbx, 8
0x180009eaf  cmp     rbx, rcx
0x180009eb2  jb      short loc_180009E6C
0x180009eb4  test    eax, eax
0x180009eb6  js      short loc_180009ED7
0x180009eb8  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180009ebf  test    rdx, rdx
0x180009ec2  jz      short loc_180009ED3
0x180009ec4  mov     rcx, cs:hInstance
0x180009ecb  mov     rax, rdx
0x180009ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed3  test    eax, eax
0x180009ed5  jns     short loc_180009F08
0x180009ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ede  lea     rdx, WPP_GLOBAL_Control
0x180009ee5  cmp     rcx, rdx
0x180009ee8  jz      short loc_180009F08
0x180009eea  test    byte ptr [rcx+44h], 1
0x180009eee  jz      short loc_180009F08
0x180009ef0  mov     rcx, [rcx+38h]
0x180009ef4  lea     r8, WPP_0a790e4df2ea300a977d38634cc427f5_Traceguids
0x180009efb  mov     edx, 0Eh
0x180009f00  mov     r9d, eax
0x180009f03  call    WPP_SF_d
0x180009f08  mov     rbx, [rsp+28h+arg_0]
0x180009f0d  xor     eax, eax
0x180009f0f  add     rsp, 20h
0x180009f13  pop     rdi
0x180009f14  retn
```
