# CIVIAudioFilter::SetValue_AVDecCommonOutputFormat(tagVARIANT *)

- ea: `0x180017500`
- end: `0x180017790`
- name: `?SetValue_AVDecCommonOutputFormat@CIVIAudioFilter@@AEAAJPEAUtagVARIANT@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016f00`

## callees

- `0x180017500`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001751e`
- `OLEAUT32!__imp_SysAllocString` at `0x180017536`
- `OLEAUT32!__imp_SysAllocString` at `0x18001754c`
- `OLEAUT32!__imp_SysAllocString` at `0x180017562`
- `OLEAUT32!__imp_SysAllocString` at `0x180017578`
- `OLEAUT32!__imp_SysAllocString` at `0x18001751e`
- `OLEAUT32!__imp_SysAllocString` at `0x180017536`
- `OLEAUT32!__imp_SysAllocString` at `0x18001754c`
- `OLEAUT32!__imp_SysAllocString` at `0x180017562`
- `OLEAUT32!__imp_SysAllocString` at `0x180017578`
- `OLEAUT32!__imp_SysFreeString` at `0x180017732`
- `OLEAUT32!__imp_SysFreeString` at `0x180017743`
- `OLEAUT32!__imp_SysFreeString` at `0x180017752`
- `OLEAUT32!__imp_SysFreeString` at `0x180017761`
- `OLEAUT32!__imp_SysFreeString` at `0x180017770`
- `OLEAUT32!__imp_SysFreeString` at `0x180017732`
- `OLEAUT32!__imp_SysFreeString` at `0x180017743`
- `OLEAUT32!__imp_SysFreeString` at `0x180017752`
- `OLEAUT32!__imp_SysFreeString` at `0x180017761`
- `OLEAUT32!__imp_SysFreeString` at `0x180017770`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800175e1`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180017622`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180017668`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800176ac`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800176e6`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800175e1`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180017622`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180017668`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800176ac`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800176e6`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::SetValue_AVDecCommonOutputFormat(CIVIAudioFilter *this, struct tagVARIANT *a2)
{
  OLECHAR *v4; // r15
  OLECHAR *v5; // r12
  OLECHAR *v6; // r13
  BSTR v7; // rax
  int v8; // ebp
  OLECHAR *v9; // r14
  unsigned int v10; // edi
  __int64 v11; // rax
  OLECHAR *bstrLeft; // [rsp+70h] [rbp+8h]

  bstrLeft = SysAllocString(L"{696E1D31-548F-4036-825F-7026C60011BD}");
  v4 = SysAllocString(L"{696E1D30-548F-4036-825F-7026C60011BD}");
  v5 = SysAllocString(L"{696E1D33-548F-4036-825F-7026C60011BD}");
  v6 = SysAllocString(L"{696E1D34-548F-4036-825F-7026C60011BD}");
  v7 = SysAllocString(L"{696E1D35-548F-4036-825F-7026C60011BD}");
  v8 = *((_DWORD *)this + 1624);
  v9 = v7;
  if ( a2 )
  {
    if ( a2->vt == 8 )
    {
      v11 = *((_QWORD *)this + 28);
      if ( v11 && *(_QWORD *)(v11 + 48) )
      {
        v10 = 0;
      }
      else
      {
        v10 = 0;
        if ( VarBstrCmp(bstrLeft, a2->bstrVal, 0x400u, 1u) == 1 )
        {
          if ( *((_DWORD *)this + 1622) != 1 )
          {
            *((_DWORD *)this + 1622) = 1;
            *((_DWORD *)this + 60) = 1;
          }
        }
        else if ( VarBstrCmp(v5, a2->bstrVal, 0x400u, 1u) == 1 )
        {
          if ( *((_DWORD *)this + 1622) != 3 )
          {
            *((_DWORD *)this + 1622) = 3;
            *((_DWORD *)this + 60) = 1;
          }
        }
        else if ( VarBstrCmp(v6, a2->bstrVal, 0x400u, 1u) == 1 )
        {
          if ( *((_DWORD *)this + 1622) != 4 )
          {
            *((_DWORD *)this + 1622) = 4;
            *((_DWORD *)this + 60) = 1;
          }
          v8 = 2;
        }
        else if ( VarBstrCmp(v4, a2->bstrVal, 0x400u, 1u) == 1 )
        {
          if ( *((_DWORD *)this + 1622) )
          {
            *((_DWORD *)this + 1622) = 0;
            *((_DWORD *)this + 60) = 1;
          }
        }
        else if ( VarBstrCmp(v9, a2->bstrVal, 0x400u, 1u) == 1 )
        {
          if ( *((_DWORD *)this + 1622) != 5 )
          {
            *((_DWORD *)this + 1622) = 5;
            *((_DWORD *)this + 60) = 1;
          }
        }
        else
        {
          v10 = -2147467259;
        }
      }
    }
    else
    {
      v10 = -2147024809;
    }
  }
  else
  {
    v10 = -2147024809;
  }
  if ( v8 != *((_DWORD *)this + 1624) )
  {
    *((_DWORD *)this + 1624) = v8;
    *((_DWORD *)this + 60) = 1;
  }
  SysFreeString(v4);
  SysFreeString(bstrLeft);
  SysFreeString(v5);
  SysFreeString(v6);
  SysFreeString(v9);
  return v10;
}

```

## disassembly

```asm
0x180017500  push    rbx
0x180017502  push    rbp
0x180017503  push    rsi
0x180017504  push    rdi
0x180017505  push    r12
0x180017507  push    r13
0x180017509  push    r14
0x18001750b  push    r15
0x18001750d  sub     rsp, 28h
0x180017511  mov     rbx, rcx
0x180017514  mov     rsi, rdx
0x180017517  lea     rcx, psz; "{696E1D31-548F-4036-825F-7026C60011BD}"
0x18001751e  call    cs:__imp_SysAllocString
0x180017525  nop     dword ptr [rax+rax+00h]
0x18001752a  lea     rcx, a696e1d30548f40; "{696E1D30-548F-4036-825F-7026C60011BD}"
0x180017531  mov     [rsp+68h+bstrLeft], rax
0x180017536  call    cs:__imp_SysAllocString
0x18001753d  nop     dword ptr [rax+rax+00h]
0x180017542  lea     rcx, a696e1d33548f40; "{696E1D33-548F-4036-825F-7026C60011BD}"
0x180017549  mov     r15, rax
0x18001754c  call    cs:__imp_SysAllocString
0x180017553  nop     dword ptr [rax+rax+00h]
0x180017558  lea     rcx, a696e1d34548f40; "{696E1D34-548F-4036-825F-7026C60011BD}"
0x18001755f  mov     r12, rax
0x180017562  call    cs:__imp_SysAllocString
0x180017569  nop     dword ptr [rax+rax+00h]
0x18001756e  lea     rcx, a696e1d35548f40; "{696E1D35-548F-4036-825F-7026C60011BD}"
0x180017575  mov     r13, rax
0x180017578  call    cs:__imp_SysAllocString
0x18001757f  nop     dword ptr [rax+rax+00h]
0x180017584  mov     ebp, [rbx+1960h]
0x18001758a  mov     r14, rax
0x18001758d  test    rsi, rsi
0x180017590  jnz     short loc_18001759C
0x180017592  mov     edi, 80070057h
0x180017597  jmp     loc_180017717
0x18001759c  mov     eax, 8
0x1800175a1  cmp     ax, [rsi]
0x1800175a4  jz      short loc_1800175B0
0x1800175a6  mov     edi, 80070057h
0x1800175ab  jmp     loc_180017717
0x1800175b0  mov     rax, [rbx+0E0h]
0x1800175b7  test    rax, rax
0x1800175ba  jz      short loc_1800175CA
0x1800175bc  cmp     qword ptr [rax+30h], 0
0x1800175c1  jz      short loc_1800175CA
0x1800175c3  xor     edi, edi
0x1800175c5  jmp     loc_180017717
0x1800175ca  mov     rdx, [rsi+8]; bstrRight
0x1800175ce  mov     r9d, 1; dwFlags
0x1800175d4  mov     rcx, [rsp+68h+bstrLeft]; bstrLeft
0x1800175d9  mov     r8d, 400h; lcid
0x1800175df  xor     edi, edi
0x1800175e1  call    cs:__imp_VarBstrCmp
0x1800175e8  nop     dword ptr [rax+rax+00h]
0x1800175ed  cmp     eax, 1
0x1800175f0  jnz     short loc_18001760F
0x1800175f2  cmp     [rbx+1958h], eax
0x1800175f8  jz      loc_180017717
0x1800175fe  mov     [rbx+1958h], eax
0x180017604  mov     [rbx+0F0h], eax
0x18001760a  jmp     loc_180017717
0x18001760f  mov     rdx, [rsi+8]; bstrRight
0x180017613  mov     r9d, 1; dwFlags
0x180017619  mov     r8d, 400h; lcid
0x18001761f  mov     rcx, r12; bstrLeft
0x180017622  call    cs:__imp_VarBstrCmp
0x180017629  nop     dword ptr [rax+rax+00h]
0x18001762e  cmp     eax, 1
0x180017631  jnz     short loc_180017655
0x180017633  cmp     dword ptr [rbx+1958h], 3
0x18001763a  jz      loc_180017717
0x180017640  mov     dword ptr [rbx+1958h], 3
0x18001764a  mov     [rbx+0F0h], eax
0x180017650  jmp     loc_180017717
0x180017655  mov     rdx, [rsi+8]; bstrRight
0x180017659  mov     r9d, 1; dwFlags
0x18001765f  mov     r8d, 400h; lcid
0x180017665  mov     rcx, r13; bstrLeft
0x180017668  call    cs:__imp_VarBstrCmp
0x18001766f  nop     dword ptr [rax+rax+00h]
0x180017674  cmp     eax, 1
0x180017677  jnz     short loc_180017699
0x180017679  cmp     dword ptr [rbx+1958h], 4
0x180017680  jz      short loc_180017692
0x180017682  mov     dword ptr [rbx+1958h], 4
0x18001768c  mov     [rbx+0F0h], eax
0x180017692  mov     ebp, 2
0x180017697  jmp     short loc_180017717
0x180017699  mov     rdx, [rsi+8]; bstrRight
0x18001769d  mov     r9d, 1; dwFlags
0x1800176a3  mov     r8d, 400h; lcid
0x1800176a9  mov     rcx, r15; bstrLeft
0x1800176ac  call    cs:__imp_VarBstrCmp
0x1800176b3  nop     dword ptr [rax+rax+00h]
0x1800176b8  cmp     eax, 1
0x1800176bb  jnz     short loc_1800176D3
0x1800176bd  cmp     [rbx+1958h], edi
0x1800176c3  jz      short loc_180017717
0x1800176c5  mov     [rbx+1958h], edi
0x1800176cb  mov     [rbx+0F0h], eax
0x1800176d1  jmp     short loc_180017717
0x1800176d3  mov     rdx, [rsi+8]; bstrRight
0x1800176d7  mov     r9d, 1; dwFlags
0x1800176dd  mov     r8d, 400h; lcid
0x1800176e3  mov     rcx, r14; bstrLeft
0x1800176e6  call    cs:__imp_VarBstrCmp
0x1800176ed  nop     dword ptr [rax+rax+00h]
0x1800176f2  cmp     eax, 1
0x1800176f5  jnz     short loc_180017712
0x1800176f7  cmp     dword ptr [rbx+1958h], 5
0x1800176fe  jz      short loc_180017717
0x180017700  mov     dword ptr [rbx+1958h], 5
0x18001770a  mov     [rbx+0F0h], eax
0x180017710  jmp     short loc_180017717
0x180017712  mov     edi, 80004005h
0x180017717  cmp     ebp, [rbx+1960h]
0x18001771d  jz      short loc_18001772F
0x18001771f  mov     [rbx+1960h], ebp
0x180017725  mov     dword ptr [rbx+0F0h], 1
0x18001772f  mov     rcx, r15; bstrString
0x180017732  call    cs:__imp_SysFreeString
0x180017739  nop     dword ptr [rax+rax+00h]
0x18001773e  mov     rcx, [rsp+68h+bstrLeft]; bstrString
0x180017743  call    cs:__imp_SysFreeString
0x18001774a  nop     dword ptr [rax+rax+00h]
0x18001774f  mov     rcx, r12; bstrString
0x180017752  call    cs:__imp_SysFreeString
0x180017759  nop     dword ptr [rax+rax+00h]
0x18001775e  mov     rcx, r13; bstrString
0x180017761  call    cs:__imp_SysFreeString
0x180017768  nop     dword ptr [rax+rax+00h]
0x18001776d  mov     rcx, r14; bstrString
0x180017770  call    cs:__imp_SysFreeString
0x180017777  nop     dword ptr [rax+rax+00h]
0x18001777c  mov     eax, edi
0x18001777e  add     rsp, 28h
0x180017782  pop     r15
0x180017784  pop     r14
0x180017786  pop     r13
0x180017788  pop     r12
0x18001778a  pop     rdi
0x18001778b  pop     rsi
0x18001778c  pop     rbp
0x18001778d  pop     rbx
0x18001778e  retn
```
