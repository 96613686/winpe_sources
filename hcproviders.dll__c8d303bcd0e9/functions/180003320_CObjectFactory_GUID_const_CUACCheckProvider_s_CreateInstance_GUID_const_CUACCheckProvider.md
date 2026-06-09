# CObjectFactory<_GUID const &,CUACCheckProvider>::s_CreateInstance(_GUID const &,CUACCheckProvider * *)

- ea: `0x180003320`
- end: `0x18000343f`
- name: `?s_CreateInstance@?$CObjectFactory@AEBU_GUID@@VCUACCheckProvider@@@@SAJAEBU_GUID@@PEAPEAVCUACCheckProvider@@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800032b0`

## callees

- `0x180003320`
- `0x180003510`
- `0x180004fc8`
- `0x180008948`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003374`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003374`
- `COMCTL32!__imp_DPA_Create` at `0x1800033b2`
- `COMCTL32!__imp_DPA_Create` at `0x1800033b2`

## pseudocode

```c
__int64 __fastcall CObjectFactory<_GUID const &,CUACCheckProvider>::s_CreateInstance(__int64 a1, _QWORD *a2)
{
  _OWORD *v3; // rax
  __int64 v4; // rax
  _QWORD *v5; // rdi
  HRESULT v6; // ebx
  void *v7; // rax
  _QWORD *v8; // rsi
  HDPA v9; // rax
  __int64 v11; // rax

  v3 = operator new(0x20u);
  if ( v3 )
  {
    *v3 = 0;
    v3[1] = 0;
    v4 = CObjectFactory<_GUID const &,CUACCheckProvider>::CObjectFactory<_GUID const &,CUACCheckProvider>(v3);
    v5 = (_QWORD *)v4;
    if ( v4 )
    {
      v6 = StringFromCLSID(&rclsid, (LPOLESTR *)(v4 + 16));
      if ( v6 >= 0 )
      {
        v7 = operator new(0x18u);
        if ( !v7 || (v8 = (_QWORD *)CCheckCollection<CCheckBase>::CCheckCollection<CCheckBase>(v7)) == 0 )
        {
          v6 = -2147024882;
          goto LABEL_8;
        }
        v9 = DPA_Create(1);
        v8[2] = v9;
        if ( !v9 )
        {
          v6 = -2147024882;
          (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
          goto LABEL_8;
        }
        v11 = *v5;
        v5[3] = v8;
        v6 = (*(__int64 (__fastcall **)(_QWORD *))(v11 + 56))(v5);
      }
      if ( v6 >= 0 )
      {
        *a2 = v5;
        return (unsigned int)v6;
      }
LABEL_8:
      (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
      return (unsigned int)v6;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180003320  mov     [rsp+arg_8], rbx
0x180003325  mov     [rsp+arg_10], rdi
0x18000332a  push    r14
0x18000332c  sub     rsp, 20h
0x180003330  mov     ecx, 20h ; ' '; Size
0x180003335  mov     r14, rdx
0x180003338  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000333d  test    rax, rax
0x180003340  jz      loc_180003428
0x180003346  xorps   xmm0, xmm0
0x180003349  mov     rcx, rax
0x18000334c  movups  xmmword ptr [rax], xmm0
0x18000334f  movups  xmmword ptr [rax+10h], xmm0
0x180003353  call    ??0?$CObjectFactory@AEBU_GUID@@VCUACCheckProvider@@@@QEAA@XZ; CObjectFactory<_GUID const &,CUACCheckProvider>::CObjectFactory<_GUID const &,CUACCheckProvider>(void)
0x180003358  mov     rdi, rax
0x18000335b  test    rax, rax
0x18000335e  jz      loc_180003428
0x180003364  lea     rdx, [rax+10h]; lplpsz
0x180003368  mov     [rsp+28h+arg_0], rsi
0x18000336d  lea     rcx, rclsid; rclsid
0x180003374  call    cs:__imp_StringFromCLSID
0x18000337b  nop     dword ptr [rax+rax+00h]
0x180003380  mov     ebx, eax
0x180003382  test    eax, eax
0x180003384  js      loc_180003418
0x18000338a  mov     ecx, 18h; Size
0x18000338f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003394  test    rax, rax
0x180003397  jz      loc_180003421
0x18000339d  mov     rcx, rax
0x1800033a0  call    ??0?$CCheckCollection@VCCheckBase@@@@IEAA@XZ; CCheckCollection<CCheckBase>::CCheckCollection<CCheckBase>(void)
0x1800033a5  mov     rsi, rax
0x1800033a8  test    rax, rax
0x1800033ab  jz      short loc_180003421
0x1800033ad  mov     ecx, 1; cItemGrow
0x1800033b2  call    cs:__imp_DPA_Create
0x1800033b9  nop     dword ptr [rax+rax+00h]
0x1800033be  mov     [rsi+10h], rax
0x1800033c2  test    rax, rax
0x1800033c5  jnz     short loc_180003403
0x1800033c7  mov     rcx, [rsi]
0x1800033ca  mov     ebx, 8007000Eh
0x1800033cf  mov     rax, [rcx+10h]
0x1800033d3  mov     rcx, rsi
0x1800033d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033db  mov     rax, [rdi]
0x1800033de  mov     rcx, rdi
0x1800033e1  mov     rax, [rax+10h]
0x1800033e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ea  mov     rsi, [rsp+28h+arg_0]
0x1800033ef  mov     eax, ebx
0x1800033f1  mov     rbx, [rsp+28h+arg_8]
0x1800033f6  mov     rdi, [rsp+28h+arg_10]
0x1800033fb  add     rsp, 20h
0x1800033ff  pop     r14
0x180003401  retn
0x180003403  mov     rax, [rdi]
0x180003406  mov     rcx, rdi
0x180003409  mov     [rdi+18h], rsi
0x18000340d  mov     rax, [rax+38h]
0x180003411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003416  mov     ebx, eax
0x180003418  test    ebx, ebx
0x18000341a  js      short loc_1800033DB
0x18000341c  mov     [r14], rdi
0x18000341f  jmp     short loc_1800033EA
0x180003421  mov     ebx, 8007000Eh
0x180003426  jmp     short loc_1800033DB
0x180003428  mov     rbx, [rsp+28h+arg_8]
0x18000342d  mov     eax, 8007000Eh
0x180003432  mov     rdi, [rsp+28h+arg_10]
0x180003437  add     rsp, 20h
0x18000343b  pop     r14
0x18000343d  retn
```
