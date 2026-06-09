# CAdvancedPage::_OnSettingChange(DirectUI::Event *,ushort)

- ea: `0x180009ff0`
- end: `0x18000a28a`
- name: `?_OnSettingChange@CAdvancedPage@@AEAAXPEAUEvent@DirectUI@@G@Z`
- size: `666`
- prototype: `void __fastcall(CAdvancedPage *__hidden this, struct DirectUI::Event *, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008250`

## callees

- `0x180009ad4`
- `0x180009ff0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a0d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a1c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a0d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a1c7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a05c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a103`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a260`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a05c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a103`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a260`
- `DUI70!StrToID` at `0x18000a050`
- `DUI70!StrToID` at `0x18000a0f5`
- `DUI70!StrToID` at `0x18000a141`
- `DUI70!StrToID` at `0x18000a158`
- `DUI70!StrToID` at `0x18000a16f`
- `DUI70!StrToID` at `0x18000a189`
- `DUI70!StrToID` at `0x18000a254`
- `DUI70!StrToID` at `0x18000a050`
- `DUI70!StrToID` at `0x18000a0f5`
- `DUI70!StrToID` at `0x18000a141`
- `DUI70!StrToID` at `0x18000a158`
- `DUI70!StrToID` at `0x18000a16f`
- `DUI70!StrToID` at `0x18000a189`
- `DUI70!StrToID` at `0x18000a254`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a283`
- `DUI70!?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z` at `0x18000a077`
- `DUI70!?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z` at `0x18000a11e`
- `DUI70!?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z` at `0x18000a077`
- `DUI70!?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z` at `0x18000a11e`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18000a1ed`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18000a1ed`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000a130`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18000a130`

## pseudocode

```c
void __fastcall CAdvancedPage::_OnSettingChange(CAdvancedPage *this, DirectUI::Element **a2, __int16 a3)
{
  char v3; // r14
  DirectUI::Element **v4; // r13
  unsigned int v5; // r15d
  DirectUI::Element **v8; // rdi
  unsigned int v9; // ebp
  DirectUI::Element *v10; // rbx
  unsigned __int16 v11; // ax
  DirectUI::Element *Descendent; // rax
  unsigned int i; // ebx
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rax
  unsigned __int16 ID; // r14
  __int64 j; // rdx
  bool v18; // bp
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  DirectUI::Element *v21; // rax
  DirectUI::Element *v22; // [rsp+30h] [rbp-48h]
  struct DirectUI::Element *v23; // [rsp+38h] [rbp-40h]
  __int64 v24; // [rsp+80h] [rbp+8h]
  __int64 v26; // [rsp+98h] [rbp+20h]

  v3 = 0;
  v4 = (DirectUI::Element **)((char *)this + 16);
  v5 = 0;
  v8 = (DirectUI::Element **)((char *)this + 16);
  v9 = 2;
  do
  {
    if ( v5 >= 4 )
      break;
    v8 = (DirectUI::Element **)((char *)this + 16);
    v10 = (DirectUI::Element *)*((_QWORD *)this + 2);
    v26 = 2LL * v5;
    v11 = StrToID((&off_18001C228)[v26]);
    Descendent = DirectUI::Element::FindDescendent(v10, v11);
    v22 = Descendent;
    if ( Descendent && DirectUI::Element::IsDescendent(Descendent, *a2) )
    {
      for ( i = 0; !v3 && i < 0xC; ++i )
      {
        v24 = 4LL * i;
        if ( CompareStringOrdinal((&off_18001C228)[v26], -1, off_18001C268[v24], -1, 1) == 2 )
        {
          v14 = StrToID((&off_18001C270)[v24]);
          v15 = DirectUI::Element::FindDescendent(v22, v14);
          v23 = v15;
          if ( v15 )
          {
            if ( DirectUI::Element::IsDescendent(v15, *a2) )
            {
              ID = DirectUI::Element::GetID(*a2);
              if ( (unsigned __int16)StrToID(L"Button0") == ID )
              {
                v9 = 0;
                goto LABEL_22;
              }
              if ( (unsigned __int16)StrToID(L"Button1") == ID )
              {
                v9 = 1;
LABEL_22:
                *((_DWORD *)this + 2 * SLODWORD(qword_18001C260[v24]) + 9) = v9;
                CAdvancedPage::_EnsureCheckbox((CAdvancedPage *)&_ImageBase, v23, v9);
                goto LABEL_23;
              }
              if ( (unsigned __int16)StrToID(L"Button2") == ID )
                goto LABEL_22;
              v3 = 1;
              if ( a3 == (unsigned __int16)StrToID(L"Button0OptionCheckbox")
                && CompareStringOrdinal((&off_18001C270)[v24], -1, L"NetworkDiscoverySetting", -1, 1) == 2 )
              {
                *((_DWORD *)this + 31) = DirectUI::Element::GetSelected(*a2);
                goto LABEL_23;
              }
            }
          }
        }
      }
    }
    ++v5;
  }
  while ( !v3 );
LABEL_23:
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    v18 = 0;
    if ( (unsigned int)j >= 0xC )
      break;
    v8 = v4;
    if ( *((_DWORD *)this + 2 * j + 8) != *((_DWORD *)this + 2 * j + 9) )
    {
      v18 = 1;
      break;
    }
  }
  v19 = *v8;
  v20 = StrToID(L"ButtonSaveChanges");
  v21 = DirectUI::Element::FindDescendent(v19, v20);
  DirectUI::Element::SetEnabled(v21, v18);
}

```

## disassembly

```asm
0x180009ff0  mov     [rsp+arg_8], rbx
0x180009ff5  mov     [rsp+arg_10], r8w
0x180009ffb  push    rbp
0x180009ffc  push    rsi
0x180009ffd  push    rdi
0x180009ffe  push    r12
0x18000a000  push    r13
0x18000a002  push    r14
0x18000a004  push    r15
0x18000a006  sub     rsp, 40h
0x18000a00a  xor     r14b, r14b
0x18000a00d  lea     r13, [rcx+10h]
0x18000a011  xor     r15d, r15d
0x18000a014  mov     r12, rdx
0x18000a017  mov     rsi, rcx
0x18000a01a  mov     rdi, r13
0x18000a01d  lea     ebp, [r15+2]
0x18000a021  lea     rcx, __ImageBase
0x18000a028  cmp     r15d, 4
0x18000a02c  jnb     loc_18000A22C
0x18000a032  mov     eax, r15d
0x18000a035  lea     rdi, [rsi+10h]
0x18000a039  mov     rbx, [rdi]
0x18000a03c  shl     rax, 4
0x18000a040  mov     [rsp+78h+arg_18], rax
0x18000a048  mov     rcx, [rax+rcx+1C228h]
0x18000a050  call    cs:__imp_StrToID
0x18000a056  movzx   edx, ax
0x18000a059  mov     rcx, rbx
0x18000a05c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a062  mov     [rsp+78h+var_48], rax
0x18000a067  test    rax, rax
0x18000a06a  jz      loc_18000A1DC
0x18000a070  mov     rdx, [r12]
0x18000a074  mov     rcx, rax
0x18000a077  call    cs:__imp_?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z; DirectUI::Element::IsDescendent(DirectUI::Element *)
0x18000a07d  test    al, al
0x18000a07f  jz      loc_18000A1DC
0x18000a085  xor     ebx, ebx
0x18000a087  jmp     loc_18000A1D3
0x18000a08c  cmp     ebx, 0Ch
0x18000a08f  jnb     loc_18000A1DC
0x18000a095  lea     rcx, __ImageBase
0x18000a09c  mov     eax, ebx
0x18000a09e  shl     rax, 5
0x18000a0a2  or      edx, 0FFFFFFFFh; cchCount1
0x18000a0a5  mov     [rsp+78h+arg_0], rax
0x18000a0ad  mov     r9d, edx; cchCount2
0x18000a0b0  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a0b8  mov     r8, [rax+rcx+1C268h]; lpString2
0x18000a0c0  mov     rax, [rsp+78h+arg_18]
0x18000a0c8  mov     rcx, [rax+rcx+1C228h]; lpString1
0x18000a0d0  call    cs:__imp_CompareStringOrdinal
0x18000a0d6  cmp     eax, ebp
0x18000a0d8  jnz     loc_18000A1D1
0x18000a0de  mov     rcx, [rsp+78h+arg_0]
0x18000a0e6  lea     rax, __ImageBase
0x18000a0ed  mov     rcx, [rcx+rax+1C270h]
0x18000a0f5  call    cs:__imp_StrToID
0x18000a0fb  mov     rcx, [rsp+78h+var_48]
0x18000a100  movzx   edx, ax
0x18000a103  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a109  mov     [rsp+78h+var_40], rax
0x18000a10e  test    rax, rax
0x18000a111  jz      loc_18000A1D1
0x18000a117  mov     rdx, [r12]
0x18000a11b  mov     rcx, rax
0x18000a11e  call    cs:__imp_?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z; DirectUI::Element::IsDescendent(DirectUI::Element *)
0x18000a124  test    al, al
0x18000a126  jz      loc_18000A1D1
0x18000a12c  mov     rcx, [r12]
0x18000a130  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18000a136  lea     rcx, aButton0; "Button0"
0x18000a13d  movzx   r14d, ax
0x18000a141  call    cs:__imp_StrToID
0x18000a147  cmp     ax, r14w
0x18000a14b  jz      loc_18000A202
0x18000a151  lea     rcx, aButton1; "Button1"
0x18000a158  call    cs:__imp_StrToID
0x18000a15e  cmp     ax, r14w
0x18000a162  jz      loc_18000A1FB
0x18000a168  lea     rcx, aButton2; "Button2"
0x18000a16f  call    cs:__imp_StrToID
0x18000a175  cmp     ax, r14w
0x18000a179  jz      loc_18000A204
0x18000a17f  lea     rcx, aButton0optionc; "Button0OptionCheckbox"
0x18000a186  mov     r14b, 1
0x18000a189  call    cs:__imp_StrToID
0x18000a18f  cmp     [rsp+78h+arg_10], ax
0x18000a197  jnz     short loc_18000A1D1
0x18000a199  or      eax, 0FFFFFFFFh
0x18000a19c  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000a1a4  mov     r9d, eax; cchCount2
0x18000a1a7  lea     rcx, __ImageBase
0x18000a1ae  mov     edx, eax; cchCount1
0x18000a1b0  lea     r8, String2; "NetworkDiscoverySetting"
0x18000a1b7  mov     rax, [rsp+78h+arg_0]
0x18000a1bf  mov     rcx, [rax+rcx+1C270h]; lpString1
0x18000a1c7  call    cs:__imp_CompareStringOrdinal
0x18000a1cd  cmp     eax, ebp
0x18000a1cf  jz      short loc_18000A1E9
0x18000a1d1  inc     ebx
0x18000a1d3  test    r14b, r14b
0x18000a1d6  jz      loc_18000A08C
0x18000a1dc  inc     r15d
0x18000a1df  test    r14b, r14b
0x18000a1e2  jnz     short loc_18000A22C
0x18000a1e4  jmp     loc_18000A021
0x18000a1e9  mov     rcx, [r12]
0x18000a1ed  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18000a1f3  movzx   eax, al
0x18000a1f6  mov     [rsi+7Ch], eax
0x18000a1f9  jmp     short loc_18000A22C
0x18000a1fb  mov     ebp, 1
0x18000a200  jmp     short loc_18000A204
0x18000a202  xor     ebp, ebp
0x18000a204  mov     rax, [rsp+78h+arg_0]
0x18000a20c  lea     rcx, __ImageBase; this
0x18000a213  mov     rdx, [rsp+78h+var_40]; struct DirectUI::Element *
0x18000a218  mov     r8d, ebp; unsigned int
0x18000a21b  movsxd  rax, dword ptr [rax+rcx+1C260h]
0x18000a223  mov     [rsi+rax*8+24h], ebp
0x18000a227  call    ?_EnsureCheckbox@CAdvancedPage@@AEAAXPEAVElement@DirectUI@@K@Z; CAdvancedPage::_EnsureCheckbox(DirectUI::Element *,ulong)
0x18000a22c  xor     edx, edx
0x18000a22e  xor     bpl, bpl
0x18000a231  cmp     edx, 0Ch
0x18000a234  jnb     short loc_18000A24A
0x18000a236  mov     eax, [rsi+rdx*8+24h]
0x18000a23a  mov     rdi, r13
0x18000a23d  cmp     [rsi+rdx*8+20h], eax
0x18000a241  jnz     short loc_18000A247
0x18000a243  inc     edx
0x18000a245  jmp     short loc_18000A22E
0x18000a247  mov     bpl, 1
0x18000a24a  mov     rbx, [rdi]
0x18000a24d  lea     rcx, aButtonsavechan; "ButtonSaveChanges"
0x18000a254  call    cs:__imp_StrToID
0x18000a25a  movzx   edx, ax
0x18000a25d  mov     rcx, rbx
0x18000a260  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a266  mov     rcx, rax
0x18000a269  mov     dl, bpl
0x18000a26c  mov     rbx, [rsp+78h+arg_8]
0x18000a274  add     rsp, 40h
0x18000a278  pop     r15
0x18000a27a  pop     r14
0x18000a27c  pop     r13
0x18000a27e  pop     r12
0x18000a280  pop     rdi
0x18000a281  pop     rsi
0x18000a282  pop     rbp
0x18000a283  jmp     cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
```
