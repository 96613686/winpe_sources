# CProviderOrderDlg::UpdateProviderPriorities(HWND__ *)

- ea: `0x180011780`
- end: `0x180011ae2`
- name: `?UpdateProviderPriorities@CProviderOrderDlg@@AEAAXPEAUHWND__@@@Z`
- size: `866`
- prototype: `void(CProviderOrderDlg *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180011c38`

## callees

- `0x180011780`

## import_xrefs

- `USER32!SendMessageW` at `0x1800117d3`
- `USER32!SendMessageW` at `0x180011804`
- `USER32!SendMessageW` at `0x180011858`
- `USER32!SendMessageW` at `0x180011877`
- `USER32!SendMessageW` at `0x1800118b3`
- `USER32!SendMessageW` at `0x1800118d1`
- `USER32!SendMessageW` at `0x1800118fa`
- `USER32!SendMessageW` at `0x180011943`
- `USER32!SendMessageW` at `0x180011962`
- `USER32!SendMessageW` at `0x180011987`
- `USER32!SendMessageW` at `0x1800119cf`
- `USER32!SendMessageW` at `0x1800119ff`
- `USER32!SendMessageW` at `0x180011a15`
- `USER32!SendMessageW` at `0x180011a54`
- `USER32!SendMessageW` at `0x180011a80`
- `USER32!SendMessageW` at `0x180011ac0`
- `USER32!SendMessageW` at `0x1800117d3`
- `USER32!SendMessageW` at `0x180011804`
- `USER32!SendMessageW` at `0x180011858`
- `USER32!SendMessageW` at `0x180011877`
- `USER32!SendMessageW` at `0x1800118b3`
- `USER32!SendMessageW` at `0x1800118d1`
- `USER32!SendMessageW` at `0x1800118fa`
- `USER32!SendMessageW` at `0x180011943`
- `USER32!SendMessageW` at `0x180011962`
- `USER32!SendMessageW` at `0x180011987`
- `USER32!SendMessageW` at `0x1800119cf`
- `USER32!SendMessageW` at `0x1800119ff`
- `USER32!SendMessageW` at `0x180011a15`
- `USER32!SendMessageW` at `0x180011a54`
- `USER32!SendMessageW` at `0x180011a80`
- `USER32!SendMessageW` at `0x180011ac0`

## pseudocode

```c
void __fastcall CProviderOrderDlg::UpdateProviderPriorities(CProviderOrderDlg *this, HWND a2)
{
  LPARAM v2; // r9
  CProviderOrderDlg *v4; // r13
  LRESULT v5; // rsi
  LPARAM v6; // r9
  HWND v7; // rcx
  int v8; // r14d
  LRESULT v9; // rax
  LPARAM v10; // rdi
  int v11; // r15d
  LRESULT v12; // rax
  unsigned int v13; // r14d
  unsigned int v14; // r14d
  LPARAM v15; // r9
  unsigned int v16; // esi
  LRESULT v17; // rdi
  __int64 v18; // r14
  LRESULT v19; // rax
  LRESULT i; // rsi
  unsigned int v21; // edi
  LRESULT v22; // r14
  __int64 v23; // rax
  unsigned int v24; // ecx
  LPARAM v25[2]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v26; // [rsp+30h] [rbp-49h]
  __int128 v27; // [rsp+40h] [rbp-39h]
  __int64 v28; // [rsp+50h] [rbp-29h]
  LPARAM lParam[2]; // [rsp+58h] [rbp-21h] BYREF
  __int128 v30; // [rsp+68h] [rbp-11h]
  __int128 v31; // [rsp+78h] [rbp-1h]
  __int64 v32; // [rsp+88h] [rbp+Fh]

  v2 = *((_QWORD *)this + 6);
  v4 = this;
  v32 = 0;
  *(_OWORD *)lParam = 0;
  LODWORD(lParam[0]) = 4;
  v30 = 0;
  v31 = 0;
  v5 = SendMessageW(a2, 0x110Au, 4u, v2);
  if ( !v5 )
    goto LABEL_19;
  while ( 1 )
  {
    lParam[1] = v5;
    SendMessageW(a2, 0x113Eu, 0, (LPARAM)lParam);
    v6 = v5;
    v7 = a2;
    if ( *(_BYTE *)(v32 + 68) == 1 )
      break;
LABEL_17:
    v5 = SendMessageW(v7, 0x110Au, 1u, v6);
    if ( !v5 )
      goto LABEL_18;
  }
  *(_OWORD *)v25 = 0;
  LODWORD(v25[0]) = 4;
  v8 = 1;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  while ( 1 )
  {
    v9 = SendMessageW(v7, 0x110Au, 1u, v6);
    v10 = v9;
    if ( !v9 )
      break;
    v25[1] = v9;
    SendMessageW(a2, 0x113Eu, 0, (LPARAM)v25);
    if ( !*(_BYTE *)(v28 + 68) )
      break;
    ++v8;
    v6 = v10;
    v7 = a2;
  }
  *(_OWORD *)v25 = 0;
  v28 = 0;
  LODWORD(v25[0]) = 4;
  v26 = 0;
  v11 = 0;
  v27 = 0;
  v12 = SendMessageW(a2, 0x110Au, 2u, v5);
  if ( v12 )
  {
    v25[1] = v12;
    SendMessageW(a2, 0x113Eu, 0, (LPARAM)v25);
    v11 = *(_DWORD *)(v28 + 64);
  }
  v13 = v8 + 1;
  if ( v10 )
  {
    v25[1] = v10;
    SendMessageW(a2, 0x113Eu, 0, (LPARAM)v25);
    v14 = (*(_DWORD *)(v28 + 64) - v11) / v13;
  }
  else
  {
    v14 = (0x7FFFFFFF - v11) / v13;
    if ( v14 > 0x3E8 )
      v14 = 1000;
  }
  for ( ; v5 != v10; v5 = SendMessageW(a2, 0x110Au, 1u, v5) )
  {
    v25[1] = v5;
    SendMessageW(a2, 0x113Eu, 0, (LPARAM)v25);
    v11 += v14;
    *(_DWORD *)(v28 + 64) = v11;
  }
  if ( v10 )
  {
    v6 = v10;
    v7 = a2;
    goto LABEL_17;
  }
LABEL_18:
  v4 = this;
LABEL_19:
  v15 = *((_QWORD *)v4 + 6);
  *(_OWORD *)v25 = 0;
  v28 = 0;
  v26 = 0;
  LODWORD(v25[0]) = 4;
  v27 = 0;
  v16 = 0;
  v17 = SendMessageW(a2, 0x110Au, 4u, v15);
  if ( v17 )
  {
    while ( v16 != 0x7FFFFFFF )
    {
      v25[1] = v17;
      SendMessageW(a2, 0x113Eu, 0, (LPARAM)v25);
      v18 = v28;
      v19 = SendMessageW(a2, 0x110Au, 1u, v17);
      v17 = v19;
      if ( *(_DWORD *)(v18 + 64) > v16 )
      {
        v16 = *(_DWORD *)(v18 + 64);
      }
      else
      {
        ++v16;
        *(_BYTE *)(v18 + 68) = 1;
        *(_DWORD *)(v18 + 64) = v16;
      }
      if ( !v19 )
        return;
    }
    for ( i = 0; v17; v17 = SendMessageW(a2, 0x110Au, 1u, v17) )
      i = v17;
    v21 = 0x7FFFFFFF;
    v22 = i;
    if ( i )
    {
      while ( 2 )
      {
        v25[1] = v22;
        SendMessageW(a2, 0x113Eu, 0, (LPARAM)v25);
        v23 = v28;
        v24 = *(_DWORD *)(v28 + 64);
        if ( v22 == i )
        {
          if ( v24 != 0x7FFFFFFF )
          {
            *(_DWORD *)(v28 + 64) = 0x7FFFFFFF;
            v21 = 0x7FFFFFFF;
            goto LABEL_34;
          }
LABEL_35:
          v21 = *(_DWORD *)(v28 + 64);
        }
        else
        {
          if ( v24 < v21 )
            goto LABEL_35;
          *(_DWORD *)(v28 + 64) = --v21;
LABEL_34:
          *(_BYTE *)(v23 + 68) = 1;
        }
        v22 = SendMessageW(a2, 0x110Au, 2u, v22);
        if ( !v22 )
          return;
        continue;
      }
    }
  }
}

```

## disassembly

```asm
0x180011780  mov     [rsp-8+arg_0], rcx
0x180011785  push    rbp
0x180011786  push    rbx
0x180011787  push    rsi
0x180011788  push    rdi
0x180011789  push    r12
0x18001178b  push    r13
0x18001178d  push    r14
0x18001178f  push    r15
0x180011791  lea     rbp, [rsp-1Fh]
0x180011796  sub     rsp, 98h
0x18001179d  mov     r9, [rcx+30h]; lParam
0x1800117a1  xorps   xmm0, xmm0
0x1800117a4  xor     eax, eax
0x1800117a6  mov     rbx, rdx
0x1800117a9  mov     r13, rcx
0x1800117ac  mov     [rbp+57h+var_48], rax
0x1800117b0  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x1800117b4  mov     r15d, 110Ah
0x1800117ba  mov     dword ptr [rbp+57h+lParam], 4
0x1800117c1  lea     r8d, [rax+4]; wParam
0x1800117c5  mov     edx, r15d; Msg
0x1800117c8  mov     rcx, rbx; hWnd
0x1800117cb  movups  [rbp+57h+var_68], xmm0
0x1800117cf  movups  [rbp+57h+var_58], xmm0
0x1800117d3  call    cs:__imp_SendMessageW
0x1800117d9  mov     rsi, rax
0x1800117dc  mov     r12d, 1
0x1800117e2  test    rax, rax
0x1800117e5  jz      loc_1800119A3
0x1800117eb  mov     r13d, 3E8h
0x1800117f1  lea     r9, [rbp+57h+lParam]; lParam
0x1800117f5  mov     [rbp+57h+lParam+8], rsi
0x1800117f9  xor     r8d, r8d; wParam
0x1800117fc  mov     edx, 113Eh; Msg
0x180011801  mov     rcx, rbx; hWnd
0x180011804  call    cs:__imp_SendMessageW
0x18001180a  mov     rax, [rbp+57h+var_48]
0x18001180e  mov     r9, rsi
0x180011811  mov     r8, r12
0x180011814  mov     edx, r15d
0x180011817  mov     rcx, rbx
0x18001181a  cmp     [rax+44h], r12b
0x18001181e  jnz     loc_180011987
0x180011824  xorps   xmm0, xmm0
0x180011827  xor     eax, eax
0x180011829  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001182d  mov     dword ptr [rbp+57h+var_B0], 4
0x180011834  mov     r14d, r12d
0x180011837  movups  [rbp+57h+var_A0], xmm0
0x18001183b  mov     [rbp+57h+var_80], rax
0x18001183f  movups  [rbp+57h+var_90], xmm0
0x180011843  jmp     short loc_180011877
0x180011845  lea     r9, [rbp+57h+var_B0]; lParam
0x180011849  mov     [rbp+57h+var_B0+8], rdi
0x18001184d  xor     r8d, r8d; wParam
0x180011850  mov     edx, 113Eh; Msg
0x180011855  mov     rcx, rbx; hWnd
0x180011858  call    cs:__imp_SendMessageW
0x18001185e  mov     rcx, [rbp+57h+var_80]
0x180011862  cmp     byte ptr [rcx+44h], 0
0x180011866  jz      short loc_180011885
0x180011868  add     r14d, r12d
0x18001186b  mov     r9, rdi; lParam
0x18001186e  mov     r8, r12; wParam
0x180011871  mov     edx, r15d; Msg
0x180011874  mov     rcx, rbx; hWnd
0x180011877  call    cs:__imp_SendMessageW
0x18001187d  mov     rdi, rax
0x180011880  test    rax, rax
0x180011883  jnz     short loc_180011845
0x180011885  xorps   xmm0, xmm0
0x180011888  xor     eax, eax
0x18001188a  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001188e  mov     r9, rsi; lParam
0x180011891  mov     [rbp+57h+var_80], rax
0x180011895  mov     edx, 110Ah; Msg
0x18001189a  mov     dword ptr [rbp+57h+var_B0], 4
0x1800118a1  lea     r8d, [rax+2]; wParam
0x1800118a5  mov     rcx, rbx; hWnd
0x1800118a8  movups  [rbp+57h+var_A0], xmm0
0x1800118ac  xor     r15d, r15d
0x1800118af  movups  [rbp+57h+var_90], xmm0
0x1800118b3  call    cs:__imp_SendMessageW
0x1800118b9  test    rax, rax
0x1800118bc  jz      short loc_1800118DF
0x1800118be  lea     r9, [rbp+57h+var_B0]; lParam
0x1800118c2  mov     [rbp+57h+var_B0+8], rax
0x1800118c6  xor     r8d, r8d; wParam
0x1800118c9  mov     edx, 113Eh; Msg
0x1800118ce  mov     rcx, rbx; hWnd
0x1800118d1  call    cs:__imp_SendMessageW
0x1800118d7  mov     rax, [rbp+57h+var_80]
0x1800118db  mov     r15d, [rax+40h]
0x1800118df  inc     r14d
0x1800118e2  test    rdi, rdi
0x1800118e5  jz      short loc_180011914
0x1800118e7  lea     r9, [rbp+57h+var_B0]; lParam
0x1800118eb  mov     [rbp+57h+var_B0+8], rdi
0x1800118ef  xor     r8d, r8d; wParam
0x1800118f2  mov     edx, 113Eh; Msg
0x1800118f7  mov     rcx, rbx; hWnd
0x1800118fa  call    cs:__imp_SendMessageW
0x180011900  mov     rax, [rbp+57h+var_80]
0x180011904  xor     edx, edx
0x180011906  mov     eax, [rax+40h]
0x180011909  sub     eax, r15d
0x18001190c  div     r14d
0x18001190f  mov     r14d, eax
0x180011912  jmp     short loc_18001192B
0x180011914  xor     edx, edx
0x180011916  mov     eax, 7FFFFFFFh
0x18001191b  sub     eax, r15d
0x18001191e  div     r14d
0x180011921  cmp     eax, r13d
0x180011924  mov     r14d, eax
0x180011927  cmova   r14d, r13d
0x18001192b  cmp     rsi, rdi
0x18001192e  jz      short loc_180011970
0x180011930  lea     r9, [rbp+57h+var_B0]; lParam
0x180011934  mov     [rbp+57h+var_B0+8], rsi
0x180011938  xor     r8d, r8d; wParam
0x18001193b  mov     edx, 113Eh; Msg
0x180011940  mov     rcx, rbx; hWnd
0x180011943  call    cs:__imp_SendMessageW
0x180011949  mov     rax, [rbp+57h+var_80]
0x18001194d  add     r15d, r14d
0x180011950  mov     r9, rsi; lParam
0x180011953  mov     r8, r12; wParam
0x180011956  mov     edx, 110Ah; Msg
0x18001195b  mov     rcx, rbx; hWnd
0x18001195e  mov     [rax+40h], r15d
0x180011962  call    cs:__imp_SendMessageW
0x180011968  mov     rsi, rax
0x18001196b  cmp     rax, rdi
0x18001196e  jnz     short loc_180011930
0x180011970  test    rdi, rdi
0x180011973  jz      short loc_180011999
0x180011975  mov     r15d, 110Ah
0x18001197b  mov     r9, rdi; lParam
0x18001197e  mov     edx, r15d; Msg
0x180011981  mov     r8, r12; wParam
0x180011984  mov     rcx, rbx; hWnd
0x180011987  call    cs:__imp_SendMessageW
0x18001198d  mov     rsi, rax
0x180011990  test    rax, rax
0x180011993  jnz     loc_1800117F1
0x180011999  mov     r13, [rbp+57h+arg_0]
0x18001199d  mov     r15d, 110Ah
0x1800119a3  mov     r9, [r13+30h]; lParam
0x1800119a7  xorps   xmm0, xmm0
0x1800119aa  xor     eax, eax
0x1800119ac  mov     edx, r15d; Msg
0x1800119af  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800119b3  mov     rcx, rbx; hWnd
0x1800119b6  mov     [rbp+57h+var_80], rax
0x1800119ba  movups  [rbp+57h+var_A0], xmm0
0x1800119be  lea     r8d, [rax+4]; wParam
0x1800119c2  mov     dword ptr [rbp+57h+var_B0], 4
0x1800119c9  movups  [rbp+57h+var_90], xmm0
0x1800119cd  xor     esi, esi
0x1800119cf  call    cs:__imp_SendMessageW
0x1800119d5  mov     rdi, rax
0x1800119d8  test    rax, rax
0x1800119db  jz      loc_180011ACE
0x1800119e1  mov     r13d, 7FFFFFFFh
0x1800119e7  cmp     esi, r13d
0x1800119ea  jz      short loc_180011A3E
0x1800119ec  lea     r9, [rbp+57h+var_B0]; lParam
0x1800119f0  mov     [rbp+57h+var_B0+8], rdi
0x1800119f4  xor     r8d, r8d; wParam
0x1800119f7  mov     edx, 113Eh; Msg
0x1800119fc  mov     rcx, rbx; hWnd
0x1800119ff  call    cs:__imp_SendMessageW
0x180011a05  mov     r14, [rbp+57h+var_80]
0x180011a09  mov     r9, rdi; lParam
0x180011a0c  mov     r8, r12; wParam
0x180011a0f  mov     edx, r15d; Msg
0x180011a12  mov     rcx, rbx; hWnd
0x180011a15  call    cs:__imp_SendMessageW
0x180011a1b  mov     rdi, rax
0x180011a1e  cmp     [r14+40h], esi
0x180011a22  ja      short loc_180011A30
0x180011a24  inc     esi
0x180011a26  mov     [r14+44h], r12b
0x180011a2a  mov     [r14+40h], esi
0x180011a2e  jmp     short loc_180011A34
0x180011a30  mov     esi, [r14+40h]
0x180011a34  test    rax, rax
0x180011a37  jnz     short loc_1800119E7
0x180011a39  jmp     loc_180011ACE
0x180011a3e  xor     esi, esi
0x180011a40  test    rdi, rdi
0x180011a43  jz      short loc_180011A62
0x180011a45  mov     r9, rdi; lParam
0x180011a48  mov     r8, r12; wParam
0x180011a4b  mov     edx, r15d; Msg
0x180011a4e  mov     rcx, rbx; hWnd
0x180011a51  mov     rsi, rdi
0x180011a54  call    cs:__imp_SendMessageW
0x180011a5a  mov     rdi, rax
0x180011a5d  test    rax, rax
0x180011a60  jnz     short loc_180011A45
0x180011a62  mov     edi, r13d
0x180011a65  mov     r14, rsi
0x180011a68  test    rsi, rsi
0x180011a6b  jz      short loc_180011ACE
0x180011a6d  lea     r9, [rbp+57h+var_B0]; lParam
0x180011a71  mov     [rbp+57h+var_B0+8], r14
0x180011a75  xor     r8d, r8d; wParam
0x180011a78  mov     edx, 113Eh; Msg
0x180011a7d  mov     rcx, rbx; hWnd
0x180011a80  call    cs:__imp_SendMessageW
0x180011a86  mov     rax, [rbp+57h+var_80]
0x180011a8a  mov     ecx, [rax+40h]
0x180011a8d  cmp     r14, rsi
0x180011a90  jnz     short loc_180011AA0
0x180011a92  cmp     ecx, r13d
0x180011a95  jz      short loc_180011AAF
0x180011a97  mov     [rax+40h], r13d
0x180011a9b  mov     edi, r13d
0x180011a9e  jmp     short loc_180011AA9
0x180011aa0  cmp     ecx, edi
0x180011aa2  jb      short loc_180011AAF
0x180011aa4  dec     edi
0x180011aa6  mov     [rax+40h], edi
0x180011aa9  mov     [rax+44h], r12b
0x180011aad  jmp     short loc_180011AB1
0x180011aaf  mov     edi, ecx
0x180011ab1  mov     r9, r14; lParam
0x180011ab4  mov     r8d, 2; wParam
0x180011aba  mov     edx, r15d; Msg
0x180011abd  mov     rcx, rbx; hWnd
0x180011ac0  call    cs:__imp_SendMessageW
0x180011ac6  mov     r14, rax
0x180011ac9  test    rax, rax
0x180011acc  jnz     short loc_180011A6D
0x180011ace  add     rsp, 98h
0x180011ad5  pop     r15
0x180011ad7  pop     r14
0x180011ad9  pop     r13
0x180011adb  pop     r12
0x180011add  pop     rdi
0x180011ade  pop     rsi
0x180011adf  pop     rbx
0x180011ae0  pop     rbp
0x180011ae1  retn
```
