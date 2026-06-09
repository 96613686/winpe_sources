# Rdp::Utils::Props::IPropertyStore_GetInterface<IPropertyStore>(IPropertyStore *,_tagpropertykey const &,IPropertyStore * *)

- ea: `0x18000954c`
- end: `0x1800095f6`
- name: `??$IPropertyStore_GetInterface@UIPropertyStore@@@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAU3@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c010`

## callees

- `0x180006a74`
- `0x18000954c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800095e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800095e3`

## string_xrefs

- `0x180009595`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetInterface<IPropertyStore>(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a3 = 0;
  *(_OWORD *)pvar = 0;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)a1 + 40LL))(
         a1,
         PKEY_GrfxChannel_Caps_Configuration_Store,
         pvar);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( LOWORD(pvar[0]) == 13 )
    {
      if ( (**(int (__fastcall ***)(PROPVARIANT, GUID *, _QWORD *))pvar[1])(
             pvar[1],
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             a3) >= 0 )
        v5 = 0;
      else
        v5 = -2147467262;
    }
    else
    {
      v5 = -2147467259;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
      (const char *)(unsigned int)v4,
      (int)pvar[0]);
  }
  PropVariantClear(pvar);
  return v5;
}

```

## disassembly

```asm
0x18000954c  mov     [rsp+arg_0], rbx
0x180009551  push    rdi
0x180009552  sub     rsp, 40h
0x180009556  mov     rdi, r8
0x180009559  mov     qword ptr [r8], 0
0x180009560  xorps   xmm0, xmm0
0x180009563  xor     eax, eax
0x180009565  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x18000956a  mov     [rsp+48h+var_18], rax
0x18000956f  mov     rax, [rcx]
0x180009572  lea     r8, [rsp+48h+pvar]
0x180009577  lea     rdx, PKEY_GrfxChannel_Caps_Configuration_Store
0x18000957e  mov     rax, [rax+28h]
0x180009582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009587  mov     ebx, eax
0x180009589  test    eax, eax
0x18000958b  jns     short loc_1800095A8
0x18000958d  mov     rcx, [rsp+48h]; this
0x180009592  mov     r9d, eax; char *
0x180009595  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000959c  mov     edx, 0B9h; void *
0x1800095a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095a6  jmp     short loc_1800095DE
0x1800095a8  cmp     word ptr [rsp+48h+pvar], 0Dh
0x1800095ae  jz      short loc_1800095B7
0x1800095b0  mov     ebx, 80004005h
0x1800095b5  jmp     short loc_1800095DE
0x1800095b7  mov     rcx, [rsp+48h+pvar+8]
0x1800095bc  mov     rax, [rcx]
0x1800095bf  mov     r8, rdi
0x1800095c2  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800095c9  mov     rax, [rax]
0x1800095cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d1  test    eax, eax
0x1800095d3  jns     short loc_1800095DC
0x1800095d5  mov     ebx, 80004002h
0x1800095da  jmp     short loc_1800095DE
0x1800095dc  xor     ebx, ebx
0x1800095de  lea     rcx, [rsp+48h+pvar]; pvar
0x1800095e3  call    cs:__imp_PropVariantClear
0x1800095e9  mov     eax, ebx
0x1800095eb  mov     rbx, [rsp+48h+arg_0]
0x1800095f0  add     rsp, 40h
0x1800095f4  pop     rdi
0x1800095f5  retn
```
