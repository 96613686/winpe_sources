# CPacketRadius::FillInAttributeInfo(CDictionary *,_packettype_,_IASATTRIBUTE *,_attribute_ *)

- ea: `0x1800131b8`
- end: `0x180013451`
- name: `?FillInAttributeInfo@CPacketRadius@@AEAAJPEAVCDictionary@@W4_packettype_@@PEAU_IASATTRIBUTE@@PEAU_attribute_@@@Z`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012c68`

## callees

- `0x180002106`
- `0x1800131b8`
- `0x180014478`
- `0x18001d124`
- `0x18002ab6c`
- `0x18002ad8c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800132e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800133fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800132e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800133fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPacketRadius::FillInAttributeInfo(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int8 *a5)
{
  unsigned int v6; // r14d
  unsigned __int8 *v7; // rsi
  __int64 v8; // rcx
  int v9; // ecx
  SIZE_T v10; // rbx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  void *v15; // rax
  int v16; // ecx
  int v17; // ecx
  unsigned __int16 v18; // dx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rax
  char *v23; // rbx
  const _com_error *v24; // [rsp+40h] [rbp-28h] BYREF
  __int64 v26; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v27; // [rsp+80h] [rbp+18h]

  v27 = a3;
  v6 = 0;
  v7 = a5;
  *(_DWORD *)(a4 + 8) = *a5;
  *(_DWORD *)(a4 + 16) = *(_DWORD *)(a2 + 4LL * *v7);
  v8 = *(_QWORD *)(a1 + 128);
  try
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
    if ( (unsigned int)(*(_DWORD *)(a4 + 8) - 107) <= 0x94 && v9 != 529 )
      *(_DWORD *)(a4 + 16) = 6;
    v10 = (unsigned int)v7[1] - 2;
    v11 = *(_DWORD *)(a4 + 16);
    if ( v11 > 5 )
    {
      v16 = v11 - 6;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( !v17 )
        {
          if ( v7[1] != 6 )
            _com_issue_error(-1073741809);
          v20 = (v7[5] | ((v7[4] | ((((unsigned __int64)v7[2] << 8) | v7[3]) << 8)) << 8)) + 0x2B6109100LL;
          *(_DWORD *)(a4 + 24) = 10000000 * ((v7[5] | ((v7[4] | (((v7[2] << 8) | v7[3]) << 8)) << 8)) - 1240428288);
          *(_DWORD *)(a4 + 28) = (10000000 * v20) >> 32;
          goto LABEL_46;
        }
        if ( v17 == 3 )
          goto LABEL_30;
        goto LABEL_37;
      }
      *(_DWORD *)(a4 + 24) = v10;
      if ( (_DWORD)v10 )
      {
        v21 = CoTaskMemAlloc(v10);
        *(_QWORD *)(a4 + 32) = v21;
        if ( !v21 )
          _com_issue_error(-2147024882);
        memcpy_0(v21, v7 + 2, v10);
        goto LABEL_46;
      }
    }
    else
    {
      if ( v11 != 5 )
      {
        if ( !v11 )
          goto LABEL_37;
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 == 1 )
              {
LABEL_30:
                v26 = a4;
                IASAttributeAddRef(a4, 2);
                if ( *(_DWORD *)(a4 + 16) != 4 )
                  v18 = 23;
                v19 = 16;
                if ( *(_DWORD *)(a4 + 16) == 4 )
                  v19 = 4;
                if ( v19 != (unsigned int)v10 )
                  _com_issue_error(-1073741809);
                IASTL::IASAttribute::setSockAddress((IASTL::IASAttribute *)&v26, v18, v7 + 2);
                IASTL::IASAttribute::_release((IASTL::IASAttribute *)&v26);
                goto LABEL_46;
              }
LABEL_37:
              _com_issue_error(-2147467259);
            }
            if ( v7[1] != 6 )
              _com_issue_error(-1073741809);
          }
          else if ( v7[1] != 6 )
          {
            _com_issue_error(-1073741809);
          }
        }
        else if ( v7[1] != 6 )
        {
          _com_issue_error(-1073741809);
        }
        *(_DWORD *)(a4 + 24) = v7[5] | ((v7[4] | (((v7[2] << 8) | v7[3]) << 8)) << 8);
LABEL_46:
        *(_DWORD *)(a4 + 4) |= 0x18u;
        if ( *(_DWORD *)(a4 + 8) == 33 )
          *(_DWORD *)(a4 + 4) |= 7u;
        return v6;
      }
      if ( v7[1] == 2 )
      {
        *(_QWORD *)(a4 + 24) = 0;
      }
      else
      {
        if ( (int)v10 + 1 < (unsigned int)v10 )
          _com_issue_error(-1073741809);
        v15 = CoTaskMemAlloc((unsigned int)(v10 + 1));
        *(_QWORD *)(a4 + 24) = v15;
        if ( !v15 )
          _com_issue_error(-2147024882);
        memcpy_0(v15, v7 + 2, v10);
        *(_BYTE *)(v10 + *(_QWORD *)(a4 + 24)) = 0;
      }
    }
    *(_QWORD *)(a4 + 32) = 0;
    goto LABEL_46;
  }
  catch ( const _com_error *v24 )
  {
    v27 = *((_DWORD *)v24 + 2);
    if ( v27 == -1073741809 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v23 = (char *)a5;
        WppDbgPrint("Incorrect attribute:%d in packet");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_680dfa5530f83761685653fb6ea5f689_Traceguids,
          (unsigned int)"NPSRAD",
          *v23);
      }
      CPacketRadius::reportMalformed((CPacketRadius *)a1);
      CReportEvent::Process(
        *(_QWORD *)(a1 + 24),
        1,
        **(unsigned __int8 **)(a1 + 24),
        *(unsigned __int16 *)(a1 + 72),
        *(_QWORD *)(a1 + 80));
      return (unsigned int)-1073741801;
    }
    return v27;
  }
  return v6;
}

```

## disassembly

```asm
0x1800131b8  mov     [rsp+arg_18], rbx
0x1800131bd  mov     [rsp+arg_10], r8d
0x1800131c2  mov     [rsp+arg_0], rcx
0x1800131c7  push    rsi
0x1800131c8  push    rdi
0x1800131c9  push    r14
0x1800131cb  sub     rsp, 50h
0x1800131cf  mov     rdi, r9
0x1800131d2  xor     r14d, r14d
0x1800131d5  mov     rsi, [rsp+68h+arg_20]
0x1800131dd  movzx   eax, byte ptr [rsi]
0x1800131e0  mov     [r9+8], eax
0x1800131e4  movzx   eax, byte ptr [rsi]
0x1800131e7  mov     edx, [rdx+rax*4]
0x1800131ea  mov     [r9+10h], edx
0x1800131ee  mov     rcx, [rcx+80h]
0x1800131f5  mov     rax, [rcx]
0x1800131f8  mov     rax, [rax+30h]
0x1800131fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013201  mov     ecx, eax
0x180013203  mov     eax, [rdi+8]
0x180013206  sub     eax, 6Bh ; 'k'
0x180013209  cmp     eax, 94h
0x18001320e  ja      short loc_18001321F
0x180013210  cmp     ecx, 211h
0x180013216  jz      short loc_18001321F
0x180013218  mov     dword ptr [rdi+10h], 6
0x18001321f  movzx   ebx, byte ptr [rsi+1]
0x180013223  add     ebx, 0FFFFFFFEh
0x180013226  mov     ecx, [rdi+10h]
0x180013229  cmp     ecx, 5
0x18001322c  jg      loc_180013319
0x180013232  jz      loc_1800132C0
0x180013238  test    ecx, ecx
0x18001323a  jz      loc_180013387
0x180013240  sub     ecx, 1
0x180013243  jz      short loc_180013286
0x180013245  sub     ecx, 1
0x180013248  jz      short loc_180013273
0x18001324a  sub     ecx, 1
0x18001324d  jz      short loc_180013260
0x18001324f  cmp     ecx, 1
0x180013252  jnz     loc_180013387
0x180013258  lea     edx, [rcx+1]
0x18001325b  jmp     loc_180013335
0x180013260  mov     eax, 4
0x180013265  cmp     ebx, eax
0x180013267  jz      short loc_180013299
0x180013269  mov     ecx, 0C000000Fh; int
0x18001326e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013273  mov     eax, 4
0x180013278  cmp     ebx, eax
0x18001327a  jz      short loc_180013299
0x18001327c  mov     ecx, 0C000000Fh; int
0x180013281  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013286  mov     eax, 4
0x18001328b  cmp     ebx, eax
0x18001328d  jz      short loc_180013299
0x18001328f  mov     ecx, 0C000000Fh; int
0x180013294  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013299  movzx   ecx, byte ptr [rsi+3]
0x18001329d  movzx   eax, byte ptr [rsi+2]
0x1800132a1  shl     eax, 8
0x1800132a4  or      ecx, eax
0x1800132a6  shl     ecx, 8
0x1800132a9  movzx   eax, byte ptr [rsi+4]
0x1800132ad  or      ecx, eax
0x1800132af  shl     ecx, 8
0x1800132b2  movzx   eax, byte ptr [rsi+5]
0x1800132b6  or      ecx, eax
0x1800132b8  mov     [rdi+18h], ecx
0x1800132bb  jmp     loc_180013425
0x1800132c0  test    ebx, ebx
0x1800132c2  jnz     short loc_1800132D1
0x1800132c4  mov     qword ptr [rdi+18h], 0
0x1800132cc  jmp     loc_1800133F0
0x1800132d1  lea     eax, [rbx+1]
0x1800132d4  cmp     eax, ebx
0x1800132d6  jnb     short loc_1800132E2
0x1800132d8  mov     ecx, 0C000000Fh; int
0x1800132dd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800132e2  mov     ecx, eax; cb
0x1800132e4  call    cs:__imp_CoTaskMemAlloc
0x1800132ea  mov     [rdi+18h], rax
0x1800132ee  test    rax, rax
0x1800132f1  jnz     short loc_1800132FD
0x1800132f3  mov     ecx, 8007000Eh; int
0x1800132f8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800132fd  lea     rdx, [rsi+2]; Src
0x180013301  mov     r8, rbx; Size
0x180013304  mov     rcx, rax; void *
0x180013307  call    memcpy_0
0x18001330c  mov     rax, [rdi+18h]
0x180013310  mov     byte ptr [rbx+rax], 0
0x180013314  jmp     loc_1800133F0
0x180013319  sub     ecx, 6
0x18001331c  jz      loc_1800133E9
0x180013322  sub     ecx, 1
0x180013325  jz      short loc_180013391
0x180013327  sub     ecx, 1
0x18001332a  jz      short loc_180013387
0x18001332c  mov     edx, 2
0x180013331  cmp     ecx, edx
0x180013333  jnz     short loc_180013387
0x180013335  mov     [rsp+68h+arg_8], rdi
0x18001333a  mov     rcx, rdi
0x18001333d  call    IASAttributeAddRef
0x180013342  nop
0x180013343  mov     ecx, 17h
0x180013348  lea     eax, [rcx-13h]
0x18001334b  cmp     [rdi+10h], eax
0x18001334e  cmovnz  dx, cx; unsigned __int16
0x180013352  lea     ecx, [rax+0Ch]
0x180013355  cmovz   ecx, eax
0x180013358  mov     eax, ebx
0x18001335a  cmp     rcx, rax
0x18001335d  jz      short loc_180013369
0x18001335f  mov     ecx, 0C000000Fh; int
0x180013364  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013369  lea     r8, [rsi+2]; unsigned __int8 *
0x18001336d  lea     rcx, [rsp+68h+arg_8]; this
0x180013372  call    ?setSockAddress@IASAttribute@IASTL@@QEAAXGQEAE@Z; IASTL::IASAttribute::setSockAddress(ushort,uchar * const)
0x180013377  nop
0x180013378  lea     rcx, [rsp+68h+arg_8]; this
0x18001337d  call    ?_release@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_release(void)
0x180013382  jmp     loc_180013425
0x180013387  mov     ecx, 80004005h; int
0x18001338c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013391  mov     eax, 4
0x180013396  cmp     ebx, eax
0x180013398  jz      short loc_1800133A4
0x18001339a  mov     ecx, 0C000000Fh; int
0x18001339f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800133a4  movzx   ecx, byte ptr [rsi+3]
0x1800133a8  movzx   eax, byte ptr [rsi+2]
0x1800133ac  shl     rax, 8
0x1800133b0  or      rcx, rax
0x1800133b3  shl     rcx, 8
0x1800133b7  movzx   eax, byte ptr [rsi+4]
0x1800133bb  or      rcx, rax
0x1800133be  shl     rcx, 8
0x1800133c2  movzx   eax, byte ptr [rsi+5]
0x1800133c6  or      rcx, rax
0x1800133c9  mov     rax, 2B6109100h
0x1800133d3  add     rcx, rax
0x1800133d6  imul    rax, rcx, 989680h
0x1800133dd  mov     [rdi+18h], eax
0x1800133e0  shr     rax, 20h
0x1800133e4  mov     [rdi+1Ch], eax
0x1800133e7  jmp     short loc_180013425
0x1800133e9  mov     [rdi+18h], ebx
0x1800133ec  test    ebx, ebx
0x1800133ee  jnz     short loc_1800133FA
0x1800133f0  mov     qword ptr [rdi+20h], 0
0x1800133f8  jmp     short loc_180013425
0x1800133fa  mov     rcx, rbx; cb
0x1800133fd  call    cs:__imp_CoTaskMemAlloc
0x180013403  mov     [rdi+20h], rax
0x180013407  test    rax, rax
0x18001340a  jnz     short loc_180013416
0x18001340c  mov     ecx, 8007000Eh; int
0x180013411  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180013416  lea     rdx, [rsi+2]; Src
0x18001341a  mov     r8, rbx; Size
0x18001341d  mov     rcx, rax; void *
0x180013420  call    memcpy_0
0x180013425  or      dword ptr [rdi+4], 18h
0x180013429  cmp     dword ptr [rdi+8], 21h ; '!'
0x18001342d  jnz     short loc_180013433
0x18001342f  or      dword ptr [rdi+4], 7
0x180013433  jmp     short loc_18001343D
0x180013435  mov     r14d, [rsp+68h+arg_10]
0x18001343d  mov     eax, r14d
0x180013440  mov     rbx, [rsp+68h+arg_18]
0x180013448  add     rsp, 50h
0x18001344c  pop     r14
0x18001344e  pop     rdi
0x18001344f  pop     rsi
0x180013450  retn
```
