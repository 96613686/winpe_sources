# CParamTag::InitStatChunk(tagSTAT_CHUNK *)

- ea: `0x180007180`
- end: `0x1800073fa`
- name: `?InitStatChunk@CParamTag@@UEAAHPEAUtagSTAT_CHUNK@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(CParamTag *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007180`
- `0x180007aa0`
- `0x180008210`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000726a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000729b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007345`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000726a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000729b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007345`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000737f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800073b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800073e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000737f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800073b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800073e3`

## string_xrefs

- `0x180007389`: `LINK.STYLESHEET`
- `0x1800073c0`: `LINK.ISOFFICECHILD`
- `0x1800073f1`: `LINK.OFFICECHILDLIST`

## pseudocode

```c
__int64 __fastcall CParamTag::InitStatChunk(CHtmlScanner **this, struct tagSTAT_CHUNK *a2)
{
  CHtmlScanner *v4; // rdi
  __int64 result; // rax
  GUID *v6; // rax
  CHtmlScanner *v7; // rax
  __int64 v8; // rcx
  LCID v9; // eax
  _QWORD *v10; // r15
  _DWORD *v11; // r14
  __int64 v12; // rcx
  CHtmlScanner *v13; // rcx
  CHtmlScanner *v14; // rcx
  __int64 v15; // r9
  OLECHAR *v16; // rax
  __int64 v17; // r9

  if ( !*((_DWORD *)this + 35)
    || (v4 = this[18], !*((_QWORD *)v4 + 5))
    || *((_DWORD *)this + 34) == 22 && !*((_DWORD *)this[1] + 16) )
  {
    CHtmlScanner::ReadTag(this[3], 0);
    return 0;
  }
  CHtmlScanner::ReadTag(this[3], 1);
  v6 = (GUID *)*((_QWORD *)v4 + 5);
  if ( v6 )
  {
    a2->attribute.guidPropSet = *v6;
    a2->attribute.psProperty.ulKind = *((_DWORD *)v4 + 8);
    if ( *((_DWORD *)v4 + 8) )
      a2->attribute.psProperty.propid = *((_DWORD *)v4 + 12);
    else
      a2->attribute.psProperty.lpwstr = (LPOLESTR)*((_QWORD *)v4 + 8);
  }
  a2->flags = CHUNK_TEXT;
  a2->breakType = CHUNK_EOS;
  v7 = this[1];
  v8 = *((unsigned int *)v7 + 1392);
  if ( (_DWORD)v8 == -1 || !*((_DWORD *)v7 + 1396) )
    v9 = *((_DWORD *)v7 + 1393);
  else
    v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 697) + 8 * v8) + 12LL);
  a2->locale = v9;
  *(_QWORD *)&a2->cwcStartSource = 0;
  v10 = this + 31;
  v11 = this + 32;
  this[31] = 0;
  *((_DWORD *)this + 64) = 0;
  *((_DWORD *)this + 65) = 0;
  if ( !*((_QWORD *)v4 + 2) )
  {
    v14 = this[3];
    *v10 = *((_QWORD *)v14 + 2);
    *v11 = *((_DWORD *)v14 + 7);
    goto LABEL_16;
  }
  if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v4) && !(unsigned int)_o__wcsicmp(*((_QWORD *)v4 + 2)) )
  {
    CHtmlScanner::ScanTagBuffer(this[3], L"rel", (wchar_t **)this + 31, (unsigned int *)this + 64);
    if ( *v11 == 10 && !(unsigned int)_o__wcsnicmp(*v10, L"stylesheet", 10, v15) )
    {
      v16 = L"LINK.STYLESHEET";
LABEL_28:
      a2->attribute.psProperty.ulKind = 0;
      a2->attribute.psProperty.lpwstr = v16;
      goto LABEL_13;
    }
    if ( *v11 == 9 )
    {
      if ( (unsigned int)_o__wcsnicmp(*v10, L"Main-File", 9, v15) )
      {
        if ( !(unsigned int)_o__wcsnicmp(*v10, L"File-List", 9, v17) )
        {
          v16 = L"LINK.OFFICECHILDLIST";
          goto LABEL_28;
        }
      }
      else
      {
        a2->attribute.psProperty.ulKind = 0;
        a2->attribute.psProperty.lpwstr = L"LINK.ISOFFICECHILD";
      }
    }
  }
LABEL_13:
  CHtmlScanner::ScanTagBuffer(this[3], *((const wchar_t **)v4 + 2), (wchar_t **)this + 31, (unsigned int *)this + 64);
  v12 = *((_QWORD *)v4 + 2);
  if ( v12 )
  {
    if ( !(unsigned int)_o__wcsicmp(v12) )
      a2->locale = 0;
  }
LABEL_16:
  if ( !*v11 )
    return 0;
  v13 = this[1];
  result = 1;
  LODWORD(v13) = ++*((_DWORD *)v13 + 24);
  a2->idChunk = (unsigned int)v13;
  a2->idChunkSource = (unsigned int)v13;
  return result;
}

```

## disassembly

```asm
0x180007180  push    rbx
0x180007182  push    rsi
0x180007183  push    rdi
0x180007184  sub     rsp, 20h
0x180007188  cmp     dword ptr [rcx+8Ch], 0
0x18000718f  mov     rsi, rdx
0x180007192  mov     rbx, rcx
0x180007195  jz      short loc_1800071A5
0x180007197  mov     rdi, [rcx+90h]
0x18000719e  cmp     qword ptr [rdi+28h], 0
0x1800071a3  jnz     short loc_1800071BA
0x1800071a5  mov     rcx, [rcx+18h]; this
0x1800071a9  xor     edx, edx; int
0x1800071ab  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x1800071b0  xor     eax, eax
0x1800071b2  add     rsp, 20h
0x1800071b6  pop     rdi
0x1800071b7  pop     rsi
0x1800071b8  pop     rbx
0x1800071b9  retn
0x1800071ba  cmp     dword ptr [rcx+88h], 16h
0x1800071c1  jz      loc_1800072E9
0x1800071c7  mov     rcx, [rcx+18h]; this
0x1800071cb  mov     edx, 1; int
0x1800071d0  mov     [rsp+38h+arg_0], rbp
0x1800071d5  mov     [rsp+38h+arg_8], r14
0x1800071da  mov     [rsp+38h+arg_10], r15
0x1800071df  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x1800071e4  mov     rax, [rdi+28h]
0x1800071e8  test    rax, rax
0x1800071eb  jz      short loc_18000720C
0x1800071ed  movups  xmm0, xmmword ptr [rax]
0x1800071f0  movups  xmmword ptr [rsi+10h], xmm0
0x1800071f4  mov     eax, [rdi+20h]
0x1800071f7  mov     [rsi+20h], eax
0x1800071fa  cmp     dword ptr [rdi+20h], 0
0x1800071fe  jnz     loc_1800072DE
0x180007204  mov     rax, [rdi+40h]
0x180007208  mov     [rsi+28h], rax
0x18000720c  mov     dword ptr [rsi+8], 1
0x180007213  mov     dword ptr [rsi+4], 2
0x18000721a  mov     rax, [rbx+8]
0x18000721e  mov     ecx, [rax+15C0h]
0x180007224  cmp     ecx, 0FFFFFFFFh
0x180007227  jnz     loc_1800072FC
0x18000722d  mov     eax, [rax+15C4h]
0x180007233  xor     ebp, ebp
0x180007235  mov     [rsi+0Ch], eax
0x180007238  mov     [rsi+34h], rbp
0x18000723c  lea     r15, [rbx+0F8h]
0x180007243  lea     r14, [rbx+100h]
0x18000724a  mov     [r15], rbp
0x18000724d  mov     [r14], ebp
0x180007250  mov     [rbx+104h], ebp
0x180007256  cmp     [rdi+10h], rbp
0x18000725a  jz      loc_18000731C
0x180007260  mov     rcx, [rdi]
0x180007263  lea     rdx, aLink; "link"
0x18000726a  call    cs:__imp__o__wcsicmp
0x180007270  test    eax, eax
0x180007272  jz      loc_18000733A
0x180007278  mov     rdx, [rdi+10h]; wchar_t *
0x18000727c  mov     r9, r14; unsigned int *
0x18000727f  mov     rcx, [rbx+18h]; this
0x180007283  mov     r8, r15; wchar_t **
0x180007286  call    ?ScanTagBuffer@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI@Z; CHtmlScanner::ScanTagBuffer(wchar_t const *,wchar_t * &,uint &)
0x18000728b  mov     rcx, [rdi+10h]
0x18000728f  test    rcx, rcx
0x180007292  jz      short loc_1800072A9
0x180007294  lea     rdx, aHref; "href"
0x18000729b  call    cs:__imp__o__wcsicmp
0x1800072a1  test    eax, eax
0x1800072a3  jz      loc_180007332
0x1800072a9  cmp     dword ptr [r14], 0
0x1800072ad  mov     r14, [rsp+38h+arg_8]
0x1800072b2  mov     r15, [rsp+38h+arg_10]
0x1800072b7  mov     rbp, [rsp+38h+arg_0]
0x1800072bc  jz      loc_1800071B0
0x1800072c2  mov     rcx, [rbx+8]
0x1800072c6  mov     eax, 1
0x1800072cb  inc     dword ptr [rcx+60h]
0x1800072ce  mov     ecx, [rcx+60h]
0x1800072d1  mov     [rsi], ecx
0x1800072d3  mov     [rsi+30h], ecx
0x1800072d6  add     rsp, 20h
0x1800072da  pop     rdi
0x1800072db  pop     rsi
0x1800072dc  pop     rbx
0x1800072dd  retn
0x1800072de  mov     eax, [rdi+30h]
0x1800072e1  mov     [rsi+28h], eax
0x1800072e4  jmp     loc_18000720C
0x1800072e9  mov     rax, [rcx+8]
0x1800072ed  cmp     dword ptr [rax+40h], 0
0x1800072f1  jnz     loc_1800071C7
0x1800072f7  jmp     loc_1800071A5
0x1800072fc  cmp     dword ptr [rax+15D0h], 0
0x180007303  jz      loc_18000722D
0x180007309  mov     rax, [rax+15C8h]
0x180007310  mov     rcx, [rax+rcx*8]
0x180007314  mov     eax, [rcx+0Ch]
0x180007317  jmp     loc_180007233
0x18000731c  mov     rcx, [rbx+18h]
0x180007320  mov     rax, [rcx+10h]
0x180007324  mov     [r15], rax
0x180007327  mov     eax, [rcx+1Ch]
0x18000732a  mov     [r14], eax
0x18000732d  jmp     loc_1800072A9
0x180007332  mov     [rsi+0Ch], ebp
0x180007335  jmp     loc_1800072A9
0x18000733a  mov     rcx, [rdi+10h]
0x18000733e  lea     rdx, aHref; "href"
0x180007345  call    cs:__imp__o__wcsicmp
0x18000734b  test    eax, eax
0x18000734d  jnz     loc_180007278
0x180007353  mov     rcx, [rbx+18h]; this
0x180007357  lea     rdx, aRel; "rel"
0x18000735e  mov     r9, r14; unsigned int *
0x180007361  mov     r8, r15; wchar_t **
0x180007364  call    ?ScanTagBuffer@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI@Z; CHtmlScanner::ScanTagBuffer(wchar_t const *,wchar_t * &,uint &)
0x180007369  cmp     dword ptr [r14], 0Ah
0x18000736d  jnz     short loc_18000739C
0x18000736f  mov     rcx, [r15]
0x180007372  lea     rdx, aStylesheet; "stylesheet"
0x180007379  mov     r8d, 0Ah
0x18000737f  call    cs:__imp__o__wcsnicmp
0x180007385  test    eax, eax
0x180007387  jnz     short loc_18000739C
0x180007389  lea     rax, aLinkStylesheet; "LINK.STYLESHEET"
0x180007390  mov     [rsi+20h], ebp
0x180007393  mov     [rsi+28h], rax
0x180007397  jmp     loc_180007278
0x18000739c  cmp     dword ptr [r14], 9
0x1800073a0  jnz     loc_180007278
0x1800073a6  mov     rcx, [r15]
0x1800073a9  lea     rdx, aMainFile; "Main-File"
0x1800073b0  mov     r8d, 9
0x1800073b6  call    cs:__imp__o__wcsnicmp
0x1800073bc  test    eax, eax
0x1800073be  jnz     short loc_1800073D3
0x1800073c0  lea     rax, aLinkIsofficech; "LINK.ISOFFICECHILD"
0x1800073c7  mov     [rsi+20h], ebp
0x1800073ca  mov     [rsi+28h], rax
0x1800073ce  jmp     loc_180007278
0x1800073d3  mov     rcx, [r15]
0x1800073d6  lea     rdx, aFileList; "File-List"
0x1800073dd  mov     r8d, 9
0x1800073e3  call    cs:__imp__o__wcsnicmp
0x1800073e9  test    eax, eax
0x1800073eb  jnz     loc_180007278
0x1800073f1  lea     rax, aLinkOfficechil_0; "LINK.OFFICECHILDLIST"
0x1800073f8  jmp     short loc_180007390
```
