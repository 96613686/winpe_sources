# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x14000a414`
- end: `0x14000a548`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `308`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1400084f8`
- `0x14001c324`
- `0x14001c58c`
- `0x14001dae4`

## callees

- `0x140004588`
- `0x140005b50`
- `0x140005b70`
- `0x1400069b0`
- `0x140007b78`
- `0x140009cd8`
- `0x14000a414`

## import_xrefs

- `msvcrt!wcscspn` at `0x14000a494`
- `msvcrt!wcscspn` at `0x14000a494`
- `msvcrt!wcsspn` at `0x14000a478`
- `msvcrt!wcsspn` at `0x14000a478`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        char **a2,
        const wchar_t *a3,
        int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  const wchar_t *v10; // r15
  unsigned __int64 v11; // rbp
  int v12; // r12d
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  _BYTE *v17; // rdi
  __int64 v18; // rax
  __int64 Manager; // rax

  v8 = *a4;
  if ( (int)v8 < 0 )
    ATL::AtlThrowImpl(-2147024809);
  if ( a3 && *a3 )
  {
    v9 = *a1;
    v10 = (const wchar_t *)(v9 + 2 * v8);
    v11 = v9 + 2LL * *(int *)(v9 - 16);
    if ( (unsigned __int64)v10 < v11 )
    {
      v12 = wcsspn(v10, a3);
      v13 = &v10[v12];
      if ( (unsigned __int64)v13 < v11 )
      {
        v14 = wcscspn(v13, a3);
        v15 = (unsigned int)(v12 + *a4);
        *a4 = v15 + v14 + 1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          a1,
          a2,
          v15,
          v14);
        return a2;
      }
    }
LABEL_16:
    *a4 = -1;
    Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(a1);
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, Manager);
    return a2;
  }
  if ( (int)v8 >= *(_DWORD *)(*a1 - 16) )
    goto LABEL_16;
  v16 = ((__int64 (*)(void))ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager)();
  v17 = (_BYTE *)(*a1 + 2LL * *a4);
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, v16);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           a2,
                           v17) )
  {
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)&v17[2 * v18] );
    }
    else
    {
      LODWORD(v18) = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v17, v18);
  }
  return a2;
}

```

## disassembly

```asm
0x14000a414  mov     [rsp+arg_0], rbx
0x14000a419  mov     [rsp+arg_10], rbp
0x14000a41e  mov     [rsp+arg_8], rdx
0x14000a423  push    rsi
0x14000a424  push    rdi
0x14000a425  push    r12
0x14000a427  push    r14
0x14000a429  push    r15
0x14000a42b  sub     rsp, 30h
0x14000a42f  mov     r14, r9
0x14000a432  mov     rsi, r8
0x14000a435  mov     rbx, rdx
0x14000a438  mov     rdi, rcx
0x14000a43b  xor     ebp, ebp
0x14000a43d  movsxd  rdx, dword ptr [r9]
0x14000a440  test    edx, edx
0x14000a442  jns     short loc_14000A44F
0x14000a444  mov     ecx, 80070057h; int
0x14000a449  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000a44f  test    rsi, rsi
0x14000a452  jz      short loc_14000A4B9
0x14000a454  cmp     [r8], bp
0x14000a458  jz      short loc_14000A4B9
0x14000a45a  mov     rcx, [rcx]
0x14000a45d  lea     r15, [rcx+rdx*2]
0x14000a461  movsxd  rax, dword ptr [rcx-10h]
0x14000a465  lea     rbp, [rcx+rax*2]
0x14000a469  cmp     r15, rbp
0x14000a46c  jnb     loc_14000A512
0x14000a472  mov     rdx, rsi; Control
0x14000a475  mov     rcx, r15; String
0x14000a478  call    cs:__imp_wcsspn
0x14000a47e  mov     r12, rax
0x14000a481  movsxd  rcx, eax
0x14000a484  lea     rcx, [r15+rcx*2]; String
0x14000a488  cmp     rcx, rbp
0x14000a48b  jnb     loc_14000A512
0x14000a491  mov     rdx, rsi; Control
0x14000a494  call    cs:__imp_wcscspn
0x14000a49a  mov     r8d, [r14]
0x14000a49d  add     r8d, r12d
0x14000a4a0  lea     ecx, [rax+1]
0x14000a4a3  add     ecx, r8d
0x14000a4a6  mov     [r14], ecx
0x14000a4a9  mov     r9d, eax
0x14000a4ac  mov     rdx, rbx
0x14000a4af  mov     rcx, rdi
0x14000a4b2  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x14000a4b7  jmp     short loc_14000A52E
0x14000a4b9  mov     rax, [rcx]
0x14000a4bc  cmp     edx, [rax-10h]
0x14000a4bf  jge     short loc_14000A512
0x14000a4c1  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x14000a4c6  movsxd  rdx, dword ptr [r14]
0x14000a4c9  mov     rcx, [rdi]
0x14000a4cc  lea     rdi, [rcx+rdx*2]
0x14000a4d0  mov     rdx, rax
0x14000a4d3  mov     rcx, rbx
0x14000a4d6  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x14000a4db  nop
0x14000a4dc  mov     rdx, rdi
0x14000a4df  mov     rcx, rbx
0x14000a4e2  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000a4e7  test    al, al
0x14000a4e9  jnz     short loc_14000A510
0x14000a4eb  test    rdi, rdi
0x14000a4ee  jnz     short loc_14000A4F4
0x14000a4f0  mov     eax, ebp
0x14000a4f2  jmp     short loc_14000A501
0x14000a4f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a4f8  inc     rax
0x14000a4fb  cmp     [rdi+rax*2], bp
0x14000a4ff  jnz     short loc_14000A4F8
0x14000a501  mov     r8d, eax
0x14000a504  mov     rdx, rdi
0x14000a507  mov     rcx, rbx
0x14000a50a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000a50f  nop
0x14000a510  jmp     short loc_14000A52E
0x14000a512  mov     dword ptr [r14], 0FFFFFFFFh
0x14000a519  mov     rcx, rdi
0x14000a51c  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x14000a521  nop
0x14000a522  mov     rdx, rax
0x14000a525  mov     rcx, rbx
0x14000a528  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x14000a52d  nop
0x14000a52e  mov     rax, rbx
0x14000a531  mov     rbx, [rsp+58h+arg_0]
0x14000a536  mov     rbp, [rsp+58h+arg_10]
0x14000a53b  add     rsp, 30h
0x14000a53f  pop     r15
0x14000a541  pop     r14
0x14000a543  pop     r12
0x14000a545  pop     rdi
0x14000a546  pop     rsi
0x14000a547  retn
```
