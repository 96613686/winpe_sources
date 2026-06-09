# CSNOCplCore::UpdateSignalStrength(_GUID const &,ulong)

- ea: `0x18001305c`
- end: `0x180013187`
- name: `?UpdateSignalStrength@CSNOCplCore@@QEAAJAEBU_GUID@@K@Z`
- size: `299`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180019d98`

## callees

- `0x180008644`
- `0x18000a434`
- `0x180011504`
- `0x18001305c`
- `0x180014274`

## import_xrefs

- `DUI70!StrToID` at `0x180013106`
- `DUI70!StrToID` at `0x180013106`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180013114`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180013114`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::UpdateSignalStrength(CSNOCplCore *this, const struct _GUID *a2, __int16 a3)
{
  __int64 **v3; // rax
  int ConnectionElement; // ebx
  int v8; // r9d
  __int64 v9; // rax
  struct CProfileData *v10; // rdx
  _QWORD *v11; // r8
  _QWORD *v12; // rax
  struct tagNETCON_PROPERTIES *v13; // r10
  __int64 v14; // rcx
  unsigned __int16 v15; // ax
  struct DirectUI::Element *Descendent; // rax
  CSNOCplCore *v17; // rcx
  struct DirectUI::Element *v19; // [rsp+40h] [rbp+8h] BYREF
  __int64 v20; // [rsp+58h] [rbp+20h] BYREF

  v3 = (__int64 **)*((_QWORD *)this + 19);
  ConnectionElement = 0;
  if ( v3[1] )
  {
    v8 = 0;
    v9 = **v3;
    v20 = v9;
    while ( v9 != **((_QWORD **)this + 19) )
    {
      v10 = *(struct CProfileData **)(v9 + 48);
      if ( *((_QWORD *)v10 + 11) )
      {
        v11 = (_QWORD *)*((_QWORD *)v10 + 10);
        v12 = (_QWORD *)*v11;
        if ( !v8 )
        {
          while ( v12 != v11 )
          {
            v13 = (struct tagNETCON_PROPERTIES *)v12[2];
            v14 = *(_QWORD *)&v13->guidId.Data1 - *(_QWORD *)&a2->Data1;
            if ( *(_QWORD *)&v13->guidId.Data1 == *(_QWORD *)&a2->Data1 )
              v14 = *(_QWORD *)v13->guidId.Data4 - *(_QWORD *)a2->Data4;
            if ( !v14 )
            {
              v19 = 0;
              ConnectionElement = CSNOCplCore::GetConnectionElement(this, v10, v13, &v19);
              if ( ConnectionElement >= 0 )
              {
                v15 = StrToID(L"connectionicon");
                Descendent = DirectUI::Element::FindDescendent(v19, v15);
                if ( Descendent )
                  ConnectionElement = CSNOCplCore::SetIconFromRes(v17, Descendent, a3 + 14);
              }
              break;
            }
            v12 = (_QWORD *)*v12;
          }
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(&v20);
      v9 = v20;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)ConnectionElement);
  return (unsigned int)ConnectionElement;
}

```

## disassembly

```asm
0x18001305c  mov     [rsp+arg_8], rbx
0x180013061  push    rbp
0x180013062  push    rsi
0x180013063  push    rdi
0x180013064  sub     rsp, 20h
0x180013068  mov     rax, [rcx+98h]
0x18001306f  xor     ebx, ebx
0x180013071  mov     ebp, r8d
0x180013074  mov     rsi, rdx
0x180013077  mov     rdi, rcx
0x18001307a  cmp     [rax+8], rbx
0x18001307e  jz      loc_180013147
0x180013084  mov     rax, [rax]
0x180013087  xor     r9d, r9d
0x18001308a  mov     rax, [rax]
0x18001308d  mov     [rsp+38h+arg_18], rax
0x180013092  mov     rcx, [rdi+98h]
0x180013099  cmp     rax, [rcx]
0x18001309c  jz      loc_180013147
0x1800130a2  mov     rdx, [rax+30h]; struct CProfileData *
0x1800130a6  cmp     qword ptr [rdx+58h], 0
0x1800130ab  jz      loc_180013133
0x1800130b1  mov     r8, [rdx+50h]
0x1800130b5  mov     rax, [r8]
0x1800130b8  test    r9d, r9d
0x1800130bb  jnz     short loc_180013133
0x1800130bd  cmp     rax, r8
0x1800130c0  jz      short loc_180013133
0x1800130c2  mov     r10, [rax+10h]
0x1800130c6  mov     rcx, [r10]
0x1800130c9  sub     rcx, [rsi]
0x1800130cc  jnz     short loc_1800130D6
0x1800130ce  mov     rcx, [r10+8]
0x1800130d2  sub     rcx, [rsi+8]
0x1800130d6  test    rcx, rcx
0x1800130d9  jz      short loc_1800130E0
0x1800130db  mov     rax, [rax]
0x1800130de  jmp     short loc_1800130BD
0x1800130e0  lea     r9, [rsp+38h+arg_0]; struct DirectUI::Element **
0x1800130e5  mov     [rsp+38h+arg_0], 0
0x1800130ee  mov     r8, r10; struct tagNETCON_PROPERTIES *
0x1800130f1  mov     rcx, rdi; this
0x1800130f4  call    ?GetConnectionElement@CSNOCplCore@@AEAAJPEAVCProfileData@@PEAUtagNETCON_PROPERTIES@@PEAPEAVElement@DirectUI@@@Z; CSNOCplCore::GetConnectionElement(CProfileData *,tagNETCON_PROPERTIES *,DirectUI::Element * *)
0x1800130f9  mov     ebx, eax
0x1800130fb  test    eax, eax
0x1800130fd  js      short loc_18001312D
0x1800130ff  lea     rcx, aConnectionicon; "connectionicon"
0x180013106  call    cs:__imp_StrToID
0x18001310c  mov     rcx, [rsp+38h+arg_0]
0x180013111  movzx   edx, ax
0x180013114  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001311a  test    rax, rax
0x18001311d  jz      short loc_18001312D
0x18001311f  lea     r8d, [rbp+0Eh]; unsigned int
0x180013123  mov     rdx, rax; struct DirectUI::Element *
0x180013126  call    ?SetIconFromRes@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@I@Z; CSNOCplCore::SetIconFromRes(DirectUI::Element *,uint)
0x18001312b  mov     ebx, eax
0x18001312d  mov     r9d, 1
0x180013133  lea     rcx, [rsp+38h+arg_18]
0x180013138  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(void)
0x18001313d  mov     rax, [rsp+38h+arg_18]
0x180013142  jmp     loc_180013092
0x180013147  mov     rcx, cs:WPP_GLOBAL_Control
0x18001314e  lea     rax, WPP_GLOBAL_Control
0x180013155  cmp     rcx, rax
0x180013158  jz      short loc_180013178
0x18001315a  test    byte ptr [rcx+1Ch], 8
0x18001315e  jz      short loc_180013178
0x180013160  mov     rcx, [rcx+10h]
0x180013164  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18001316b  mov     edx, 83h
0x180013170  mov     r9d, ebx
0x180013173  call    WPP_SF_d
0x180013178  mov     eax, ebx
0x18001317a  mov     rbx, [rsp+38h+arg_8]
0x18001317f  add     rsp, 20h
0x180013183  pop     rdi
0x180013184  pop     rsi
0x180013185  pop     rbp
0x180013186  retn
```
