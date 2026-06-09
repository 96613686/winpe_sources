# CGeneralPage::_OnCommand(unsigned __int64,__int64)

- ea: `0x1800135d0`
- end: `0x1800137d8`
- name: `?_OnCommand@CGeneralPage@@MEAAK_K_J@Z`
- size: `520`
- prototype: `unsigned int __fastcall(CGeneralPage *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001910`
- `0x18000688c`
- `0x180013028`
- `0x1800135d0`
- `0x18001406c`
- `0x180019224`
- `0x18001eef4`
- `0x180020580`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `USER32!GetDlgItemInt` at `0x180013697`
- `USER32!GetDlgItemInt` at `0x180013697`

## pseudocode

```c
__int64 __fastcall CGeneralPage::_OnCommand(CGeneralPage *this, unsigned __int64 a2)
{
  int v3; // edx
  UINT DlgItemInt; // edi
  unsigned int v5; // eax
  int v6; // edx
  struct CLogInfo *v7; // rdx
  HWND v8; // rcx
  int v9; // eax
  _QWORD *v10; // r9
  __int64 v11; // rdx
  unsigned int v13; // [rsp+20h] [rbp-268h]
  unsigned int v14; // [rsp+30h] [rbp-258h] BYREF
  _QWORD v15[5]; // [rsp+38h] [rbp-250h] BYREF
  unsigned __int16 v16[264]; // [rsp+60h] [rbp-228h] BYREF

  switch ( (unsigned __int16)a2 )
  {
    case 0x70u:
      if ( *((_QWORD *)this + 6) )
      {
        v7 = (struct CLogInfo *)*((_QWORD *)this + 7);
        v8 = (HWND)*((_QWORD *)this + 2);
        v14 = 0;
        if ( (unsigned int)PromptForLogClear(v8, v7, (enum SAVE_TYPE *)&v14, v16, v13) != 2 )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 6) + 24LL))(
                 *((_QWORD *)this + 6),
                 *((_QWORD *)this + 7),
                 v14,
                 v16);
          if ( v9 < 0 )
          {
            ComposeErrorMessgeFromHRESULT(v15, (unsigned int)v9);
            v10 = v15;
            if ( v15[3] >= 8u )
              v10 = (_QWORD *)v15[0];
            MsgBox(*((HWND *)this + 2), 0x130u, 0x10u, v10);
            LOBYTE(v11) = 1;
            std::wstring::_Tidy(v15, v11, 0);
          }
        }
      }
      return 0;
    case 0x74u:
      goto LABEL_21;
    case 0x79u:
LABEL_22:
      CPropSheetPage::_EnableApply(this, a2);
      return 0;
    case 0x7Au:
      goto LABEL_19;
    case 0x7Bu:
      CPropSheetPage::_EnableApply(this, a2);
      v6 = 1;
LABEL_20:
      CGeneralPage::_EnableOlderThanCtrls(this, v6);
      return 0;
    case 0x7Cu:
LABEL_19:
      CPropSheetPage::_EnableApply(this, a2);
      v6 = 0;
      goto LABEL_20;
    case 0x7Du:
      if ( WORD1(a2) == 1024 )
      {
        DlgItemInt = GetDlgItemInt(*((HWND *)this + 2), 125, 0, 0);
        if ( *((_DWORD *)this + 16) != DlgItemInt )
        {
          CPropSheetPage::_EnableApply(this, v3);
          v5 = (DlgItemInt + 32) & 0xFFFFFFC0;
          *((_DWORD *)this + 16) = v5;
          if ( v5 >= 0x40 )
          {
            if ( v5 > 0x3FFFC0 )
              *((_DWORD *)this + 16) = 4194240;
          }
          else
          {
            *((_DWORD *)this + 16) = 64;
          }
        }
      }
      return 0;
    case 0x82u:
LABEL_21:
      a2 >>= 16;
      if ( (_WORD)a2 == 1024 )
        goto LABEL_22;
      return 0;
  }
  if ( (unsigned __int16)a2 == 135 && (unsigned int)MsgBox(*((HWND *)this + 2), 0xF4u, 0x124u) == 6 )
  {
    CGeneralPage::_SetValues(this, 0x4000, 122, 7);
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x1800135d0  mov     [rsp+arg_8], rbx
0x1800135d5  push    rdi
0x1800135d6  sub     rsp, 280h
0x1800135dd  mov     rax, cs:__security_cookie
0x1800135e4  xor     rax, rsp
0x1800135e7  mov     [rsp+288h+var_18], rax
0x1800135ef  mov     rbx, rcx
0x1800135f2  movzx   ecx, dx
0x1800135f5  sub     ecx, 70h ; 'p'
0x1800135f8  jz      loc_180013724
0x1800135fe  sub     ecx, 4
0x180013601  jz      loc_180013705
0x180013607  sub     ecx, 5
0x18001360a  jz      loc_180013717
0x180013610  sub     ecx, 1
0x180013613  jz      loc_1800136EE
0x180013619  sub     ecx, 1
0x18001361c  jz      loc_1800136DF
0x180013622  sub     ecx, 1
0x180013625  jz      loc_1800136EE
0x18001362b  sub     ecx, 1
0x18001362e  jz      short loc_180013677
0x180013630  sub     ecx, 5
0x180013633  jz      loc_180013705
0x180013639  cmp     ecx, 5
0x18001363c  jnz     loc_1800137B5
0x180013642  mov     rcx, [rbx+10h]; hWnd
0x180013646  mov     edx, 0F4h; uID
0x18001364b  lea     r8d, [rdx+30h]; unsigned int
0x18001364f  call    ?MsgBox@@YAHPEAUHWND__@@KKZZ; MsgBox(HWND__ *,ulong,ulong,...)
0x180013654  cmp     eax, 6
0x180013657  jnz     loc_1800137B5
0x18001365d  mov     edx, 4000h
0x180013662  lea     r9d, [rax+1]
0x180013666  lea     r8d, [rax+74h]
0x18001366a  mov     rcx, rbx
0x18001366d  call    ?_SetValues@CGeneralPage@@IEAAXKW4OVERWRITE_METHOD@@K@Z; CGeneralPage::_SetValues(ulong,OVERWRITE_METHOD,ulong)
0x180013672  jmp     loc_180013717
0x180013677  shr     rdx, 10h
0x18001367b  mov     eax, 400h
0x180013680  cmp     dx, ax
0x180013683  jnz     loc_1800137B5
0x180013689  mov     rcx, [rbx+10h]; hDlg
0x18001368d  xor     r9d, r9d; bSigned
0x180013690  xor     r8d, r8d; lpTranslated
0x180013693  lea     edx, [r9+7Dh]; nIDDlgItem
0x180013697  call    cs:__imp_GetDlgItemInt
0x18001369d  mov     edi, eax
0x18001369f  cmp     [rbx+40h], eax
0x1800136a2  jz      loc_1800137B5
0x1800136a8  mov     rcx, rbx; this
0x1800136ab  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x1800136b0  lea     eax, [rdi+20h]
0x1800136b3  and     eax, 0FFFFFFC0h
0x1800136b6  mov     [rbx+40h], eax
0x1800136b9  cmp     eax, 40h ; '@'
0x1800136bc  jnb     short loc_1800136CA
0x1800136be  mov     dword ptr [rbx+40h], 40h ; '@'
0x1800136c5  jmp     loc_1800137B5
0x1800136ca  mov     ecx, 3FFFC0h
0x1800136cf  cmp     eax, ecx
0x1800136d1  jbe     loc_1800137B5
0x1800136d7  mov     [rbx+40h], ecx
0x1800136da  jmp     loc_1800137B5
0x1800136df  mov     rcx, rbx; this
0x1800136e2  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x1800136e7  mov     edx, 1; int
0x1800136ec  jmp     short loc_1800136F8
0x1800136ee  mov     rcx, rbx; this
0x1800136f1  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x1800136f6  xor     edx, edx; int
0x1800136f8  mov     rcx, rbx; this
0x1800136fb  call    ?_EnableOlderThanCtrls@CGeneralPage@@IEAAXH@Z; CGeneralPage::_EnableOlderThanCtrls(int)
0x180013700  jmp     loc_1800137B5
0x180013705  shr     rdx, 10h; int
0x180013709  mov     eax, 400h
0x18001370e  cmp     dx, ax
0x180013711  jnz     loc_1800137B5
0x180013717  mov     rcx, rbx; this
0x18001371a  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x18001371f  jmp     loc_1800137B5
0x180013724  cmp     qword ptr [rbx+30h], 0
0x180013729  jz      loc_1800137B5
0x18001372f  mov     rdx, [rbx+38h]; struct CLogInfo *
0x180013733  lea     r9, [rsp+288h+var_228]; unsigned __int16 *
0x180013738  mov     rcx, [rbx+10h]; HWND
0x18001373c  lea     r8, [rsp+288h+var_258]; enum SAVE_TYPE *
0x180013741  mov     [rsp+288h+var_258], 0
0x180013749  call    ?PromptForLogClear@@YAJPEAUHWND__@@PEAVCLogInfo@@PEAW4SAVE_TYPE@@PEAGK@Z; PromptForLogClear(HWND__ *,CLogInfo *,SAVE_TYPE *,ushort *,ulong)
0x18001374e  cmp     eax, 2
0x180013751  jz      short loc_1800137B5
0x180013753  mov     rcx, [rbx+30h]
0x180013757  lea     r9, [rsp+288h+var_228]
0x18001375c  mov     r8d, [rsp+288h+var_258]
0x180013761  mov     rdx, [rbx+38h]
0x180013765  mov     rax, [rcx]
0x180013768  mov     rax, [rax+18h]
0x18001376c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013771  test    eax, eax
0x180013773  jns     short loc_1800137B5
0x180013775  mov     edx, eax
0x180013777  lea     rcx, [rsp+288h+var_250]
0x18001377c  call    ?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; ComposeErrorMessgeFromHRESULT(long)
0x180013781  cmp     [rsp+288h+var_238], 8
0x180013787  lea     r9, [rsp+288h+var_250]
0x18001378c  mov     rcx, [rbx+10h]; hWnd
0x180013790  mov     edx, 130h; uID
0x180013795  cmovnb  r9, [rsp+288h+var_250]
0x18001379b  mov     r8d, 10h; unsigned int
0x1800137a1  call    ?MsgBox@@YAHPEAUHWND__@@KKZZ; MsgBox(HWND__ *,ulong,ulong,...)
0x1800137a6  xor     r8d, r8d
0x1800137a9  lea     rcx, [rsp+288h+var_250]
0x1800137ae  mov     dl, 1
0x1800137b0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800137b5  xor     eax, eax
0x1800137b7  mov     rcx, [rsp+288h+var_18]
0x1800137bf  xor     rcx, rsp; StackCookie
0x1800137c2  call    __security_check_cookie
0x1800137c7  mov     rbx, [rsp+288h+arg_8]
0x1800137cf  add     rsp, 280h
0x1800137d6  pop     rdi
0x1800137d7  retn
```
