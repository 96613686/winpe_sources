# ListViewPage::GetUserChoices(tagSAFEARRAY * *)

- ea: `0x14002b5a0`
- end: `0x14002b902`
- name: `?GetUserChoices@ListViewPage@@MEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(ListViewPage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000e72c`
- `0x140020420`
- `0x14002ad30`
- `0x14002b5a0`

## import_xrefs

- `USER32!SendMessageW` at `0x14002b65c`
- `USER32!SendMessageW` at `0x14002b6aa`
- `USER32!SendMessageW` at `0x14002b755`
- `USER32!SendMessageW` at `0x14002b782`
- `USER32!SendMessageW` at `0x14002b806`
- `USER32!SendMessageW` at `0x14002b65c`
- `USER32!SendMessageW` at `0x14002b6aa`
- `USER32!SendMessageW` at `0x14002b755`
- `USER32!SendMessageW` at `0x14002b782`
- `USER32!SendMessageW` at `0x14002b806`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b6e7`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b83a`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b6e7`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b83a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b735`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b870`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b8a6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b735`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b870`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b8a6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b628`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b7bd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b628`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b7bd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002b8e4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002b8e4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b715`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b858`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b715`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b858`

## pseudocode

```c
__int64 __fastcall ListViewPage::GetUserChoices(ListViewPage *this, struct tagSAFEARRAY **a2)
{
  int NamedHandle; // eax
  unsigned int v4; // ebx
  int v5; // r9d
  SAFEARRAY *v6; // rsi
  int v7; // r9d
  int Item; // eax
  unsigned int v9; // eax
  BSTR v10; // rax
  OLECHAR *v11; // r14
  HRESULT v12; // eax
  int v13; // r9d
  ULONG v14; // esi
  int v15; // r14d
  int v16; // r15d
  int v17; // eax
  ULONG v18; // ecx
  signed int i; // r15d
  BSTR v20; // rax
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-10h] BYREF
  struct InteractivityChoice *v23; // [rsp+38h] [rbp-8h] BYREF
  LONG rgIndices; // [rsp+90h] [rbp+50h] BYREF
  HWND hWnd; // [rsp+98h] [rbp+58h] BYREF

  hWnd = 0;
  rgIndices = 0;
  v23 = 0;
  NamedHandle = WizardPage::GetNamedHandle(this, L"lstView", &hWnd);
  v4 = NamedHandle;
  if ( NamedHandle >= 0 )
  {
    if ( *((_DWORD *)this + 46) )
    {
      rgsabound = (SAFEARRAYBOUND)1LL;
      v6 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( !v6 )
      {
        v5 = 3424;
LABEL_7:
        NamedHandle = -2147024882;
        v4 = -2147024882;
        goto LABEL_3;
      }
      if ( (unsigned int)SendMessageW(hWnd, 0x1032u, 0, 0) != 1 )
      {
        v7 = 3431;
LABEL_10:
        Item = -2147467259;
LABEL_11:
        v4 = Item;
LABEL_12:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ListViewPage::GetUserChoices", v7, Item);
LABEL_41:
        SafeArrayDestroy(v6);
        return v4;
      }
      v9 = SendMessageW(hWnd, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
      if ( v9 == -1 )
      {
        v7 = 3437;
        goto LABEL_10;
      }
      Item = InteractivityPage::GetItem(this, v9, &v23);
      v4 = Item;
      if ( Item < 0 )
      {
        v7 = 3441;
        goto LABEL_12;
      }
      v10 = SysAllocString(*((const OLECHAR **)v23 + 2));
      v11 = v10;
      if ( !v10 )
      {
        Item = -2147024882;
        v7 = 3444;
        goto LABEL_11;
      }
      v12 = SafeArrayPutElement(v6, &rgIndices, v10);
      v4 = v12;
      if ( v12 < 0 )
      {
        v13 = 3450;
LABEL_37:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ListViewPage::GetUserChoices", v13, v12);
        SysFreeString(v11);
        goto LABEL_41;
      }
      SysFreeString(v11);
    }
    else
    {
      v14 = 0;
      v15 = 0;
      v16 = SendMessageW(hWnd, 0x1004u, 0, 0);
      if ( v16 > 0 )
      {
        do
        {
          v17 = SendMessageW(hWnd, 0x102Cu, (unsigned int)v15, 61440);
          v18 = v14 + 1;
          if ( (v17 & 0xFFFFF000) == 0x1000 )
            v18 = v14;
          ++v15;
          v14 = v18;
        }
        while ( v15 < v16 );
      }
      rgsabound.lLbound = 0;
      rgsabound.cElements = v14;
      v6 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( !v6 )
      {
        v5 = 3471;
        goto LABEL_7;
      }
      rgIndices = 0;
      for ( i = 0; i < *((_DWORD *)this + 42); ++i )
      {
        if ( (unsigned int)SendMessageW(hWnd, 0x102Cu, i, 61440) >> 12 != 1 )
        {
          Item = InteractivityPage::GetItem(this, i, &v23);
          v4 = Item;
          if ( Item < 0 )
          {
            v7 = 3481;
            goto LABEL_12;
          }
          v20 = SysAllocString(*((const OLECHAR **)v23 + 2));
          v11 = v20;
          if ( !v20 )
          {
            Item = -2147024882;
            v7 = 3484;
            goto LABEL_11;
          }
          v12 = SafeArrayPutElement(v6, &rgIndices, v20);
          v4 = v12;
          if ( v12 < 0 )
          {
            v13 = 3490;
            goto LABEL_37;
          }
          ++rgIndices;
          SysFreeString(v11);
        }
      }
    }
    *a2 = v6;
    return v4;
  }
  v5 = 3415;
LABEL_3:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ListViewPage::GetUserChoices", v5, NamedHandle);
  return v4;
}

```

## disassembly

```asm
0x14002b5a0  mov     [rsp-38h+arg_8], rdx
0x14002b5a5  push    rbp
0x14002b5a6  push    rbx
0x14002b5a7  push    rsi
0x14002b5a8  push    rdi
0x14002b5a9  push    r12
0x14002b5ab  push    r14
0x14002b5ad  push    r15
0x14002b5af  mov     rbp, rsp
0x14002b5b2  sub     rsp, 40h
0x14002b5b6  xor     r15d, r15d
0x14002b5b9  lea     r8, [rbp+hWnd]; HWND *
0x14002b5bd  lea     rdx, aLstview; "lstView"
0x14002b5c4  mov     [rbp+hWnd], r15
0x14002b5c8  mov     [rbp+rgIndices], r15d
0x14002b5cc  mov     r12, rcx
0x14002b5cf  mov     [rbp+var_8], r15
0x14002b5d3  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002b5d8  mov     ebx, eax
0x14002b5da  test    eax, eax
0x14002b5dc  jns     short loc_14002B604
0x14002b5de  mov     r9d, 0D57h
0x14002b5e4  lea     ecx, [r15+1]; Level
0x14002b5e8  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b5ef  mov     [rsp+40h+var_20], eax
0x14002b5f3  lea     r8, aListviewpageGe; "ListViewPage::GetUserChoices"
0x14002b5fa  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b5ff  jmp     loc_14002B8F0
0x14002b604  cmp     [r12+0B8h], r15d
0x14002b60c  jz      loc_14002B746
0x14002b612  mov     edi, 1
0x14002b617  mov     qword ptr [rbp+rgsabound.cElements], 1
0x14002b61f  lea     r8, [rbp+rgsabound]; rgsabound
0x14002b623  mov     edx, edi; cDims
0x14002b625  lea     ecx, [rdi+7]; vt
0x14002b628  call    cs:__imp_SafeArrayCreate
0x14002b62f  nop     dword ptr [rax+rax+00h]
0x14002b634  mov     rsi, rax
0x14002b637  test    rax, rax
0x14002b63a  jnz     short loc_14002B64D
0x14002b63c  mov     r9d, 0D60h
0x14002b642  mov     eax, 8007000Eh
0x14002b647  mov     ecx, edi
0x14002b649  mov     ebx, eax
0x14002b64b  jmp     short loc_14002B5E8
0x14002b64d  mov     rcx, [rbp+hWnd]; hWnd
0x14002b651  xor     r9d, r9d; lParam
0x14002b654  xor     r8d, r8d; wParam
0x14002b657  mov     edx, 1032h; Msg
0x14002b65c  call    cs:__imp_SendMessageW
0x14002b663  nop     dword ptr [rax+rax+00h]
0x14002b668  cmp     eax, edi
0x14002b66a  jz      short loc_14002B697
0x14002b66c  mov     r9d, 0D67h
0x14002b672  mov     eax, 80004005h
0x14002b677  mov     ebx, eax
0x14002b679  lea     r8, aListviewpageGe; "ListViewPage::GetUserChoices"
0x14002b680  mov     [rsp+40h+var_20], eax
0x14002b684  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b68b  mov     ecx, edi; Level
0x14002b68d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b692  jmp     loc_14002B8E1
0x14002b697  mov     rcx, [rbp+hWnd]; hWnd
0x14002b69b  mov     r9d, 2; lParam
0x14002b6a1  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x14002b6a5  mov     edx, 100Ch; Msg
0x14002b6aa  call    cs:__imp_SendMessageW
0x14002b6b1  nop     dword ptr [rax+rax+00h]
0x14002b6b6  cmp     eax, 0FFFFFFFFh
0x14002b6b9  jnz     short loc_14002B6C3
0x14002b6bb  mov     r9d, 0D6Dh
0x14002b6c1  jmp     short loc_14002B672
0x14002b6c3  lea     r8, [rbp+var_8]; struct InteractivityChoice **
0x14002b6c7  mov     edx, eax; unsigned int
0x14002b6c9  mov     rcx, r12; this
0x14002b6cc  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x14002b6d1  mov     ebx, eax
0x14002b6d3  test    eax, eax
0x14002b6d5  jns     short loc_14002B6DF
0x14002b6d7  mov     r9d, 0D71h
0x14002b6dd  jmp     short loc_14002B679
0x14002b6df  mov     rcx, [rbp+var_8]
0x14002b6e3  mov     rcx, [rcx+10h]; psz
0x14002b6e7  call    cs:__imp_SysAllocString
0x14002b6ee  nop     dword ptr [rax+rax+00h]
0x14002b6f3  mov     r14, rax
0x14002b6f6  test    rax, rax
0x14002b6f9  jnz     short loc_14002B70B
0x14002b6fb  mov     eax, 8007000Eh
0x14002b700  mov     r9d, 0D74h
0x14002b706  jmp     loc_14002B677
0x14002b70b  mov     r8, r14; pv
0x14002b70e  lea     rdx, [rbp+rgIndices]; rgIndices
0x14002b712  mov     rcx, rsi; psa
0x14002b715  call    cs:__imp_SafeArrayPutElement
0x14002b71c  nop     dword ptr [rax+rax+00h]
0x14002b721  mov     ebx, eax
0x14002b723  test    eax, eax
0x14002b725  jns     short loc_14002B732
0x14002b727  mov     r9d, 0D7Ah
0x14002b72d  jmp     loc_14002B88A
0x14002b732  mov     rcx, r14; bstrString
0x14002b735  call    cs:__imp_SysFreeString
0x14002b73c  nop     dword ptr [rax+rax+00h]
0x14002b741  jmp     loc_14002B8D2
0x14002b746  mov     rcx, [rbp+hWnd]; hWnd
0x14002b74a  xor     r9d, r9d; lParam
0x14002b74d  xor     r8d, r8d; wParam
0x14002b750  mov     edx, 1004h; Msg
0x14002b755  call    cs:__imp_SendMessageW
0x14002b75c  nop     dword ptr [rax+rax+00h]
0x14002b761  xor     esi, esi
0x14002b763  xor     r14d, r14d
0x14002b766  mov     r15, rax
0x14002b769  lea     edi, [rsi+1]
0x14002b76c  test    eax, eax
0x14002b76e  jle     short loc_14002B7A8
0x14002b770  mov     rcx, [rbp+hWnd]; hWnd
0x14002b774  mov     edx, 102Ch; Msg
0x14002b779  mov     r8d, r14d; wParam
0x14002b77c  mov     r9d, 0F000h; lParam
0x14002b782  call    cs:__imp_SendMessageW
0x14002b789  nop     dword ptr [rax+rax+00h]
0x14002b78e  and     eax, 0FFFFF000h
0x14002b793  lea     ecx, [rsi+1]
0x14002b796  cmp     eax, 1000h
0x14002b79b  cmovz   ecx, esi
0x14002b79e  add     r14d, edi
0x14002b7a1  mov     esi, ecx
0x14002b7a3  cmp     r14d, r15d
0x14002b7a6  jl      short loc_14002B770
0x14002b7a8  mov     ecx, 8; vt
0x14002b7ad  mov     [rbp+rgsabound.lLbound], 0
0x14002b7b4  lea     r8, [rbp+rgsabound]; rgsabound
0x14002b7b8  mov     [rbp+rgsabound.cElements], esi
0x14002b7bb  mov     edx, edi; cDims
0x14002b7bd  call    cs:__imp_SafeArrayCreate
0x14002b7c4  nop     dword ptr [rax+rax+00h]
0x14002b7c9  mov     rsi, rax
0x14002b7cc  test    rax, rax
0x14002b7cf  jnz     short loc_14002B7DC
0x14002b7d1  mov     r9d, 0D8Fh
0x14002b7d7  jmp     loc_14002B642
0x14002b7dc  mov     [rbp+rgIndices], 0
0x14002b7e3  xor     r15d, r15d
0x14002b7e6  cmp     r15d, [r12+0A8h]
0x14002b7ee  jge     loc_14002B8CF
0x14002b7f4  mov     rcx, [rbp+hWnd]; hWnd
0x14002b7f8  mov     edx, 102Ch; Msg
0x14002b7fd  movsxd  r8, r15d; wParam
0x14002b800  mov     r9d, 0F000h; lParam
0x14002b806  call    cs:__imp_SendMessageW
0x14002b80d  nop     dword ptr [rax+rax+00h]
0x14002b812  shr     eax, 0Ch
0x14002b815  cmp     eax, edi
0x14002b817  jz      short loc_14002B87C
0x14002b819  lea     r8, [rbp+var_8]; struct InteractivityChoice **
0x14002b81d  mov     edx, r15d; unsigned int
0x14002b820  mov     rcx, r12; this
0x14002b823  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x14002b828  mov     ebx, eax
0x14002b82a  test    eax, eax
0x14002b82c  js      loc_14002B8C4
0x14002b832  mov     rcx, [rbp+var_8]
0x14002b836  mov     rcx, [rcx+10h]; psz
0x14002b83a  call    cs:__imp_SysAllocString
0x14002b841  nop     dword ptr [rax+rax+00h]
0x14002b846  mov     r14, rax
0x14002b849  test    rax, rax
0x14002b84c  jz      short loc_14002B8B4
0x14002b84e  mov     r8, rax; pv
0x14002b851  lea     rdx, [rbp+rgIndices]; rgIndices
0x14002b855  mov     rcx, rsi; psa
0x14002b858  call    cs:__imp_SafeArrayPutElement
0x14002b85f  nop     dword ptr [rax+rax+00h]
0x14002b864  mov     ebx, eax
0x14002b866  test    eax, eax
0x14002b868  js      short loc_14002B884
0x14002b86a  add     [rbp+rgIndices], edi
0x14002b86d  mov     rcx, r14; bstrString
0x14002b870  call    cs:__imp_SysFreeString
0x14002b877  nop     dword ptr [rax+rax+00h]
0x14002b87c  add     r15d, edi
0x14002b87f  jmp     loc_14002B7E6
0x14002b884  mov     r9d, 0DA2h
0x14002b88a  lea     r8, aListviewpageGe; "ListViewPage::GetUserChoices"
0x14002b891  mov     [rsp+40h+var_20], eax
0x14002b895  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b89c  mov     ecx, edi; Level
0x14002b89e  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b8a3  mov     rcx, r14; bstrString
0x14002b8a6  call    cs:__imp_SysFreeString
0x14002b8ad  nop     dword ptr [rax+rax+00h]
0x14002b8b2  jmp     short loc_14002B8E1
0x14002b8b4  mov     eax, 8007000Eh
0x14002b8b9  mov     r9d, 0D9Ch
0x14002b8bf  jmp     loc_14002B677
0x14002b8c4  mov     r9d, 0D99h
0x14002b8ca  jmp     loc_14002B679
0x14002b8cf  xor     r15d, r15d
0x14002b8d2  mov     rax, [rbp+arg_8]
0x14002b8d6  mov     [rax], rsi
0x14002b8d9  mov     rsi, r15
0x14002b8dc  test    r15, r15
0x14002b8df  jz      short loc_14002B8F0
0x14002b8e1  mov     rcx, rsi; psa
0x14002b8e4  call    cs:__imp_SafeArrayDestroy
0x14002b8eb  nop     dword ptr [rax+rax+00h]
0x14002b8f0  mov     eax, ebx
0x14002b8f2  add     rsp, 40h
0x14002b8f6  pop     r15
0x14002b8f8  pop     r14
0x14002b8fa  pop     r12
0x14002b8fc  pop     rdi
0x14002b8fd  pop     rsi
0x14002b8fe  pop     rbx
0x14002b8ff  pop     rbp
0x14002b900  retn
```
