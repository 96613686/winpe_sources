# DMConfigManagerWrap::AddConfigNode(ushort const *,ushort const *,ConfigDataType,tagVARIANT,long *)

- ea: `0x180035374`
- end: `0x180035501`
- name: `?AddConfigNode@DMConfigManagerWrap@@QEBAJPEBG0W4ConfigDataType@@UtagVARIANT@@PEAJ@Z`
- size: `397`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const OLECHAR *, unsigned int, __int128 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002feec`

## callees

- `0x180035374`
- `0x180035508`
- `0x1800355cc`
- `0x18003b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800353e1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800353e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800354e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800354e8`

## pseudocode

```c
__int64 __fastcall DMConfigManagerWrap::AddConfigNode(
        __int64 a1,
        const unsigned __int16 *a2,
        const OLECHAR *a3,
        unsigned int a4,
        __int128 *a5,
        int *a6)
{
  int *v6; // r12
  int ConfigNode; // ebx
  struct IConfigNode *v11; // rdi
  OLECHAR *v12; // r14
  __int64 v13; // xmm1_8
  __int64 v14; // rax
  DMConfigManagerWrap *v15; // rcx
  unsigned int v16; // r8d
  unsigned int v17; // r9d
  struct IConfigNode *v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF
  __int128 v21; // [rsp+40h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-18h]
  int v23; // [rsp+B0h] [rbp+48h] BYREF

  v6 = a6;
  ConfigNode = -2147418113;
  v19 = 0;
  v20 = 0;
  *a6 = 0;
  v11 = 0;
  v23 = -2147418113;
  if ( !*(_QWORD *)(a1 + 8) )
    return (unsigned int)ConfigNode;
  v12 = 0;
  if ( a2 && a3 )
  {
    ConfigNode = DMConfigManagerWrap::GetConfigNode((DMConfigManagerWrap *)a1, a2, &v19);
    if ( ConfigNode >= 0 )
    {
      v12 = SysAllocString(a3);
      if ( v12 )
      {
        if ( *(_BYTE *)(a1 + 1)
          || (ConfigNode = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 56LL))(*(_QWORD *)(a1 + 8)),
              ConfigNode >= 0) )
        {
          v11 = v19;
          v13 = *((_QWORD *)a5 + 2);
          v14 = *(_QWORD *)v19;
          v21 = *a5;
          v22 = v13;
          ConfigNode = (*(__int64 (__fastcall **)(struct IConfigNode *, OLECHAR *, _QWORD, __int128 *, __int64 *))(v14 + 24))(
                         v19,
                         v12,
                         a4,
                         &v21,
                         &v20);
          if ( ConfigNode >= 0 && !*(_BYTE *)(a1 + 1) )
          {
            ConfigNode = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 64LL))(*(_QWORD *)(a1 + 8));
            if ( ConfigNode >= 0 )
            {
              ConfigNode = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8));
              if ( ConfigNode < 0 && (int)DMConfigManagerWrap::GetExecutionHresult(v15, v11, v16, v17, &v23) >= 0 )
                *v6 = v23;
            }
          }
          goto LABEL_17;
        }
      }
      else
      {
        ConfigNode = -2147024882;
      }
    }
    v11 = v19;
  }
  else
  {
    ConfigNode = -2147024809;
  }
LABEL_17:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v12 )
    SysFreeString(v12);
  return (unsigned int)ConfigNode;
}

```

## disassembly

```asm
0x180035374  push    rbp
0x180035376  push    rbx
0x180035377  push    rsi
0x180035378  push    rdi
0x180035379  push    r12
0x18003537b  push    r13
0x18003537d  push    r14
0x18003537f  push    r15
0x180035381  mov     rbp, rsp
0x180035384  sub     rsp, 68h
0x180035388  mov     r12, [rbp+arg_28]
0x18003538c  mov     rsi, rcx
0x18003538f  xor     ecx, ecx
0x180035391  mov     ebx, 8000FFFFh
0x180035396  mov     r13d, r9d
0x180035399  mov     [rbp+var_38], rcx
0x18003539d  mov     r15, r8
0x1800353a0  mov     [rbp+var_30], rcx
0x1800353a4  mov     [r12], ecx
0x1800353a8  mov     edi, ecx
0x1800353aa  mov     [rbp+arg_0], ebx
0x1800353ad  cmp     [rsi+8], rcx
0x1800353b1  jz      loc_1800354EE
0x1800353b7  mov     r14d, ecx
0x1800353ba  test    rdx, rdx
0x1800353bd  jz      loc_1800354AA
0x1800353c3  test    r8, r8
0x1800353c6  jz      loc_1800354AA
0x1800353cc  lea     r8, [rbp+var_38]; struct IConfigNode **
0x1800353d0  mov     rcx, rsi; this
0x1800353d3  call    ?GetConfigNode@DMConfigManagerWrap@@QEBAJPEBGPEAPEAUIConfigNode@@@Z; DMConfigManagerWrap::GetConfigNode(ushort const *,IConfigNode * *)
0x1800353d8  mov     ebx, eax
0x1800353da  test    eax, eax
0x1800353dc  js      short loc_1800353F4
0x1800353de  mov     rcx, r15; psz
0x1800353e1  call    cs:__imp_SysAllocString
0x1800353e7  mov     r14, rax
0x1800353ea  test    rax, rax
0x1800353ed  jnz     short loc_1800353FD
0x1800353ef  mov     ebx, 8007000Eh
0x1800353f4  mov     rdi, [rbp+var_38]
0x1800353f8  jmp     loc_1800354AF
0x1800353fd  cmp     [rsi+1], dil
0x180035401  jnz     short loc_180035419
0x180035403  mov     rcx, [rsi+8]
0x180035407  mov     rax, [rcx]
0x18003540a  mov     rax, [rax+38h]
0x18003540e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035413  mov     ebx, eax
0x180035415  test    eax, eax
0x180035417  js      short loc_1800353F4
0x180035419  mov     rax, [rbp+arg_20]
0x18003541d  lea     rcx, [rbp+var_30]
0x180035421  mov     rdi, [rbp+var_38]
0x180035425  lea     r9, [rbp+var_28]
0x180035429  mov     [rsp+68h+var_48], rcx
0x18003542e  mov     r8d, r13d
0x180035431  mov     rdx, r14
0x180035434  mov     rcx, rdi
0x180035437  movaps  xmm0, xmmword ptr [rax]
0x18003543a  movsd   xmm1, qword ptr [rax+10h]
0x18003543f  mov     rax, [rdi]
0x180035442  movaps  [rbp+var_28], xmm0
0x180035446  movsd   [rbp+var_18], xmm1
0x18003544b  mov     rax, [rax+18h]
0x18003544f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035454  mov     ebx, eax
0x180035456  test    eax, eax
0x180035458  js      short loc_1800354AF
0x18003545a  cmp     byte ptr [rsi+1], 0
0x18003545e  jnz     short loc_1800354AF
0x180035460  mov     rcx, [rsi+8]
0x180035464  mov     rax, [rcx]
0x180035467  mov     rax, [rax+40h]
0x18003546b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035470  mov     ebx, eax
0x180035472  test    eax, eax
0x180035474  js      short loc_1800354AF
0x180035476  mov     rcx, [rsi+8]
0x18003547a  mov     rax, [rcx]
0x18003547d  mov     rax, [rax+18h]
0x180035481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035486  mov     ebx, eax
0x180035488  test    eax, eax
0x18003548a  jns     short loc_1800354AF
0x18003548c  lea     rax, [rbp+arg_0]
0x180035490  mov     rdx, rdi; struct IConfigNode *
0x180035493  mov     [rsp+68h+var_48], rax; int *
0x180035498  call    ?GetExecutionHresult@DMConfigManagerWrap@@QEBAJPEAUIConfigNode@@KKPEAJ@Z; DMConfigManagerWrap::GetExecutionHresult(IConfigNode *,ulong,ulong,long *)
0x18003549d  test    eax, eax
0x18003549f  js      short loc_1800354AF
0x1800354a1  mov     eax, [rbp+arg_0]
0x1800354a4  mov     [r12], eax
0x1800354a8  jmp     short loc_1800354AF
0x1800354aa  mov     ebx, 80070057h
0x1800354af  mov     rcx, [rbp+var_30]
0x1800354b3  test    rcx, rcx
0x1800354b6  jz      short loc_1800354CC
0x1800354b8  mov     rax, [rcx]
0x1800354bb  mov     rax, [rax+10h]
0x1800354bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354c4  mov     [rbp+var_30], 0
0x1800354cc  test    rdi, rdi
0x1800354cf  jz      short loc_1800354E0
0x1800354d1  mov     rax, [rdi]
0x1800354d4  mov     rcx, rdi
0x1800354d7  mov     rax, [rax+10h]
0x1800354db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354e0  test    r14, r14
0x1800354e3  jz      short loc_1800354EE
0x1800354e5  mov     rcx, r14; bstrString
0x1800354e8  call    cs:__imp_SysFreeString
0x1800354ee  mov     eax, ebx
0x1800354f0  add     rsp, 68h
0x1800354f4  pop     r15
0x1800354f6  pop     r14
0x1800354f8  pop     r13
0x1800354fa  pop     r12
0x1800354fc  pop     rdi
0x1800354fd  pop     rsi
0x1800354fe  pop     rbx
0x1800354ff  pop     rbp
0x180035500  retn
```
