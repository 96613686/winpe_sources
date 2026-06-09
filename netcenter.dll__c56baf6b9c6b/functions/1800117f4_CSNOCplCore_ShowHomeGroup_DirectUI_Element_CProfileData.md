# CSNOCplCore::ShowHomeGroup(DirectUI::Element *,CProfileData *)

- ea: `0x1800117f4`
- end: `0x180011947`
- name: `?ShowHomeGroup@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Element *, struct CProfileData *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c7e8`
- `0x180012ec4`

## callees

- `0x180011188`
- `0x1800117f4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001187b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001187b`
- `DUI70!StrToID` at `0x18001181b`
- `DUI70!StrToID` at `0x1800118bd`
- `DUI70!StrToID` at `0x18001181b`
- `DUI70!StrToID` at `0x1800118bd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011827`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800118c9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180011827`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800118c9`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001192c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001192c`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::ShowHomeGroup(CSNOCplCore *this, struct DirectUI::Element *a2, struct CProfileData *a3)
{
  int v6; // edi
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbp
  int v9; // ebx
  struct DirectUI::Element *v10; // rdx
  unsigned __int16 v11; // ax
  CSNOCplCore *v12; // rcx
  int v13; // eax
  unsigned int v14; // r8d
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  int v17; // [rsp+78h] [rbp+20h] BYREF

  v6 = -2147467259;
  v7 = StrToID(L"HomeGroupRow");
  Descendent = DirectUI::Element::FindDescendent(a2, v7);
  if ( Descendent )
  {
    v6 = 0;
    v9 = -3;
    ppv = 0;
    if ( !*((_QWORD *)this + 44)
      || *((_DWORD *)a3 + 14) != 1
      || CoCreateInstance(&CLSID_HomeGroupNetwork, 0, 1u, &GUID_c8b8b7c0_d585_43e4_a665_fe817bfdf561, &ppv) < 0 )
    {
      goto LABEL_17;
    }
    v17 = 0;
    if ( (*(int (__fastcall **)(LPVOID, struct CProfileData *, int *))(*(_QWORD *)ppv + 40LL))(ppv, a3, &v17) >= 0
      && v17 == 1 )
    {
      v6 = -2147467259;
      v11 = StrToID(L"HomeGroupStatus");
      v10 = DirectUI::Element::FindDescendent(Descendent, v11);
      if ( v10 )
      {
        v13 = *((_DWORD *)this + 79);
        if ( (v13 & 4) != 0 )
        {
          v14 = 185;
          goto LABEL_14;
        }
        if ( (v13 & 8) != 0 )
        {
          v14 = 186;
          goto LABEL_14;
        }
        v6 = 0;
        if ( (v13 & 0x10) != 0 )
        {
          v14 = 187;
LABEL_14:
          v6 = CSNOCplCore::SetContentAndAccNameFromRes(v12, v10, v14, 0xC3u);
          if ( v6 >= 0 )
            v9 = -1;
        }
      }
    }
    (*(void (__fastcall **)(LPVOID, struct DirectUI::Element *))(*(_QWORD *)ppv + 16LL))(ppv, v10);
LABEL_17:
    DirectUI::Element::SetLayoutPos(Descendent, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800117f4  mov     [rsp+arg_0], rbx
0x1800117f9  mov     [rsp+arg_8], rbp
0x1800117fe  push    rsi
0x1800117ff  push    rdi
0x180011800  push    r14
0x180011802  sub     rsp, 40h
0x180011806  mov     rsi, rcx
0x180011809  mov     r14, r8
0x18001180c  lea     rcx, aHomegrouprow; "HomeGroupRow"
0x180011813  mov     rbx, rdx
0x180011816  mov     edi, 80004005h
0x18001181b  call    cs:__imp_StrToID
0x180011821  movzx   edx, ax
0x180011824  mov     rcx, rbx
0x180011827  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001182d  mov     rbp, rax
0x180011830  test    rax, rax
0x180011833  jz      loc_180011932
0x180011839  xor     edi, edi
0x18001183b  mov     ebx, 0FFFFFFFDh
0x180011840  mov     [rsp+58h+var_28], rdi
0x180011845  cmp     [rsi+160h], rdi
0x18001184c  jz      loc_180011927
0x180011852  cmp     dword ptr [r14+38h], 1
0x180011857  jnz     loc_180011927
0x18001185d  lea     rax, [rsp+58h+var_28]
0x180011862  xor     edx, edx; pUnkOuter
0x180011864  lea     r9, _GUID_c8b8b7c0_d585_43e4_a665_fe817bfdf561; riid
0x18001186b  mov     [rsp+58h+ppv], rax; ppv
0x180011870  lea     r8d, [rbx+4]; dwClsContext
0x180011874  lea     rcx, CLSID_HomeGroupNetwork; rclsid
0x18001187b  call    cs:__imp_CoCreateInstance
0x180011881  test    eax, eax
0x180011883  js      loc_180011927
0x180011889  mov     rcx, [rsp+58h+var_28]
0x18001188e  lea     r8, [rsp+58h+arg_18]
0x180011893  mov     [rsp+58h+arg_18], edi
0x180011897  mov     rdx, r14
0x18001189a  mov     rax, [rcx]
0x18001189d  mov     rax, [rax+28h]
0x1800118a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a6  test    eax, eax
0x1800118a8  js      short loc_180011916
0x1800118aa  cmp     [rsp+58h+arg_18], 1
0x1800118af  jnz     short loc_180011916
0x1800118b1  lea     rcx, aHomegroupstatu; "HomeGroupStatus"
0x1800118b8  mov     edi, 80004005h
0x1800118bd  call    cs:__imp_StrToID
0x1800118c3  movzx   edx, ax
0x1800118c6  mov     rcx, rbp
0x1800118c9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800118cf  mov     rdx, rax; struct DirectUI::Element *
0x1800118d2  test    rax, rax
0x1800118d5  jz      short loc_180011916
0x1800118d7  mov     eax, [rsi+13Ch]
0x1800118dd  test    al, 4
0x1800118df  jz      short loc_1800118E9
0x1800118e1  mov     r8d, 0B9h
0x1800118e7  jmp     short loc_180011901
0x1800118e9  test    al, 8
0x1800118eb  jz      short loc_1800118F5
0x1800118ed  mov     r8d, 0BAh
0x1800118f3  jmp     short loc_180011901
0x1800118f5  xor     edi, edi
0x1800118f7  test    al, 10h
0x1800118f9  jz      short loc_180011916
0x1800118fb  mov     r8d, 0BBh; unsigned int
0x180011901  mov     r9d, 0C3h; unsigned int
0x180011907  call    ?SetContentAndAccNameFromRes@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@II@Z; CSNOCplCore::SetContentAndAccNameFromRes(DirectUI::Element *,uint,uint)
0x18001190c  mov     edi, eax
0x18001190e  or      eax, 0FFFFFFFFh
0x180011911  test    edi, edi
0x180011913  cmovns  ebx, eax
0x180011916  mov     rcx, [rsp+58h+var_28]
0x18001191b  mov     r8, [rcx]
0x18001191e  mov     rax, [r8+10h]
0x180011922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011927  mov     edx, ebx
0x180011929  mov     rcx, rbp
0x18001192c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180011932  mov     rbx, [rsp+58h+arg_0]
0x180011937  mov     eax, edi
0x180011939  mov     rbp, [rsp+58h+arg_8]
0x18001193e  add     rsp, 40h
0x180011942  pop     r14
0x180011944  pop     rdi
0x180011945  pop     rsi
0x180011946  retn
```
