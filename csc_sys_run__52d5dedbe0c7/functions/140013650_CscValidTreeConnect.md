# CscValidTreeConnect

- ea: `0x140013650`
- end: `0x14001388c`
- name: `CscValidTreeConnect`
- size: `572`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x14000a64c`
- `0x14000f8b0`
- `0x140013650`
- `0x140018930`
- `0x1400190ec`
- `0x14001d9f4`
- `0x14002f010`
- `0x14002f440`
- `0x140075350`

## import_xrefs

- `rdbss!RxFindEa` at `0x140013696`
- `rdbss!RxFindEa` at `0x140013696`

## string_xrefs

- `0x14001367d`: `DFSCreate`

## pseudocode

```c
__int64 __fastcall CscValidTreeConnect(__int64 a1)
{
  unsigned int InformationEntry; // ebx
  int v3; // esi
  __int64 Ea; // rax
  __int64 v5; // rbp
  int v6; // edx
  int Entry; // eax
  __int64 v8; // rbp
  char v9; // di
  __int64 v11; // [rsp+50h] [rbp-98h] BYREF
  __int128 v12; // [rsp+58h] [rbp-90h] BYREF
  _DWORD v13[20]; // [rsp+70h] [rbp-78h] BYREF

  InformationEntry = 0;
  v3 = 0;
  Ea = RxFindEa(*(_QWORD *)(a1 + 696), *(unsigned int *)(a1 + 712), "DFSCreate", 10);
  v11 = 0;
  v5 = Ea;
  memset(v13, 0, sizeof(v13));
  v12 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v6) = v5 != 0 ? 89 : 78;
    WPP_SF_qqZZc(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      *(_QWORD *)(a1 + 648),
      a1,
      *(_QWORD *)(a1 + 648),
      *(_QWORD *)(*(_QWORD *)(a1 + 648) + 88LL),
      a1 + 816,
      v6);
  }
  if ( v5 )
  {
    Entry = CscStorepFindOrCreateEntryEx((unsigned int)&v11, 0, 0, (int)a1 + 816, 128, 0, 0, 0, (__int64)&v12, 0);
    v8 = v11;
    InformationEntry = Entry;
    if ( Entry >= 0 )
    {
      InformationEntry = CscStoreQueryInformationEntryEx(v11, 0, (__int64)v13, 0, 0, 0, 0);
      if ( (InformationEntry & 0x80000000) == 0 )
      {
        v9 = v13[1];
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v13[1]);
        }
        if ( (v9 & 1) == 0 )
        {
          InformationEntry = -1073741634;
          v3 = 2052;
        }
      }
      else
      {
        v3 = 2043;
      }
    }
    else
    {
      v3 = 2037;
    }
    if ( v8 )
      CscEnDereferenceEntry(&v11);
    if ( (int)(InformationEntry + 0x80000000) >= 0 && InformationEntry != -1073741634 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          57,
          WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
          InformationEntry);
      InformationEntry = -1073741634;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      58,
      WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      InformationEntry,
      v3);
  return InformationEntry;
}

```

## disassembly

```asm
0x140013650  mov     [rsp+arg_8], rbx
0x140013655  mov     [rsp+arg_10], rbp
0x14001365a  push    rsi
0x14001365b  push    rdi
0x14001365c  push    r13
0x14001365e  sub     rsp, 0D0h
0x140013665  mov     rax, cs:__security_cookie
0x14001366c  xor     rax, rsp
0x14001366f  mov     [rsp+0E8h+var_28], rax
0x140013677  mov     edx, [rcx+2C8h]
0x14001367d  lea     r8, aDfscreate; "DFSCreate"
0x140013684  mov     rdi, rcx
0x140013687  xor     ebx, ebx
0x140013689  mov     rcx, [rcx+2B8h]
0x140013690  xor     esi, esi
0x140013692  lea     r9d, [rbx+0Ah]
0x140013696  call    cs:__imp_RxFindEa
0x14001369d  nop     dword ptr [rax+rax+00h]
0x1400136a2  xor     edx, edx; Val
0x1400136a4  mov     [rsp+0E8h+var_98], rbx
0x1400136a9  lea     r8d, [rbx+50h]; Size
0x1400136ad  mov     rbp, rax
0x1400136b0  lea     rcx, [rsp+0E8h+var_78]; void *
0x1400136b5  call    memset
0x1400136ba  xorps   xmm0, xmm0
0x1400136bd  movups  [rsp+0E8h+var_90], xmm0
0x1400136c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400136c9  lea     r13, WPP_GLOBAL_Control
0x1400136d0  cmp     rcx, r13
0x1400136d3  jz      short loc_14001371B
0x1400136d5  mov     eax, [rcx+2Ch]
0x1400136d8  test    al, 20h
0x1400136da  jz      short loc_14001371B
0x1400136dc  mov     r8, [rdi+288h]
0x1400136e3  mov     rax, rbp
0x1400136e6  mov     rcx, [rcx+18h]
0x1400136ea  neg     rax
0x1400136ed  lea     rax, [rdi+330h]
0x1400136f4  mov     r9, rdi
0x1400136f7  sbb     dl, dl
0x1400136f9  and     dl, 0Bh
0x1400136fc  add     dl, 4Eh ; 'N'
0x1400136ff  mov     byte ptr [rsp+0E8h+var_B0], dl
0x140013703  mov     [rsp+0E8h+var_B8], rax
0x140013708  mov     rax, [r8+58h]
0x14001370c  mov     [rsp+0E8h+var_C0], rax
0x140013711  mov     [rsp+0E8h+var_C8], r8
0x140013716  call    WPP_SF_qqZZc
0x14001371b  test    rbp, rbp
0x14001371e  jz      loc_140013832
0x140013724  mov     [rsp+0E8h+var_A0], rbx
0x140013729  lea     rax, [rsp+0E8h+var_90]
0x14001372e  mov     [rsp+0E8h+var_A8], rax
0x140013733  lea     r9, [rdi+330h]
0x14001373a  mov     [rsp+0E8h+var_B0], rbx
0x14001373f  lea     rcx, [rsp+0E8h+var_98]
0x140013744  mov     [rsp+0E8h+var_B8], rbx
0x140013749  xor     r8d, r8d
0x14001374c  mov     [rsp+0E8h+var_C0], rbx
0x140013751  xor     edx, edx
0x140013753  mov     dword ptr [rsp+0E8h+var_C8], 80h
0x14001375b  call    CscStorepFindOrCreateEntryEx
0x140013760  mov     rbp, [rsp+0E8h+var_98]
0x140013765  mov     ebx, eax
0x140013767  test    eax, eax
0x140013769  jns     short loc_140013772
0x14001376b  mov     esi, 7F5h
0x140013770  jmp     short loc_1400137DF
0x140013772  mov     [rsp+0E8h+var_B8], rsi
0x140013777  lea     r8, [rsp+0E8h+var_78]
0x14001377c  mov     [rsp+0E8h+var_C0], rsi
0x140013781  xor     r9d, r9d
0x140013784  xor     edx, edx
0x140013786  mov     [rsp+0E8h+var_C8], rsi
0x14001378b  mov     rcx, rbp
0x14001378e  call    CscStoreQueryInformationEntryEx
0x140013793  mov     ebx, eax
0x140013795  test    eax, eax
0x140013797  jns     short loc_1400137A0
0x140013799  mov     esi, 7FBh
0x14001379e  jmp     short loc_1400137DF
0x1400137a0  mov     edi, [rsp+0E8h+var_74]
0x1400137a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137ab  cmp     rcx, r13
0x1400137ae  jz      short loc_1400137CF
0x1400137b0  mov     eax, [rcx+2Ch]
0x1400137b3  test    al, 40h
0x1400137b5  jz      short loc_1400137CF
0x1400137b7  mov     rcx, [rcx+18h]
0x1400137bb  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400137c2  mov     edx, 38h ; '8'
0x1400137c7  mov     r9d, edi
0x1400137ca  call    WPP_SF_d
0x1400137cf  test    dil, 1
0x1400137d3  jnz     short loc_1400137DF
0x1400137d5  mov     ebx, 0C00000BEh
0x1400137da  mov     esi, 804h
0x1400137df  test    rbp, rbp
0x1400137e2  jz      short loc_1400137EE
0x1400137e4  lea     rcx, [rsp+0E8h+var_98]
0x1400137e9  call    CscEnDereferenceEntry
0x1400137ee  mov     ecx, 80000000h
0x1400137f3  lea     eax, [rbx+rcx]
0x1400137f6  test    ecx, eax
0x1400137f8  jnz     short loc_140013832
0x1400137fa  cmp     ebx, 0C00000BEh
0x140013800  jz      short loc_140013832
0x140013802  mov     rcx, cs:WPP_GLOBAL_Control
0x140013809  cmp     rcx, r13
0x14001380c  jz      short loc_14001382D
0x14001380e  mov     eax, [rcx+2Ch]
0x140013811  test    al, 20h
0x140013813  jz      short loc_14001382D
0x140013815  mov     rcx, [rcx+18h]
0x140013819  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140013820  mov     edx, 39h ; '9'
0x140013825  mov     r9d, ebx
0x140013828  call    WPP_SF_d
0x14001382d  mov     ebx, 0C00000BEh
0x140013832  mov     rcx, cs:WPP_GLOBAL_Control
0x140013839  cmp     rcx, r13
0x14001383c  jz      short loc_140013861
0x14001383e  mov     eax, [rcx+2Ch]
0x140013841  test    al, 20h
0x140013843  jz      short loc_140013861
0x140013845  mov     rcx, [rcx+18h]
0x140013849  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140013850  mov     edx, 3Ah ; ':'
0x140013855  mov     dword ptr [rsp+0E8h+var_C8], esi
0x140013859  mov     r9d, ebx
0x14001385c  call    WPP_SF_Dd
0x140013861  mov     eax, ebx
0x140013863  mov     rcx, [rsp+0E8h+var_28]
0x14001386b  xor     rcx, rsp; StackCookie
0x14001386e  call    __security_check_cookie
0x140013873  lea     r11, [rsp+0E8h+var_18]
0x14001387b  mov     rbx, [r11+28h]
0x14001387f  mov     rbp, [r11+30h]
0x140013883  mov     rsp, r11
0x140013886  pop     r13
0x140013888  pop     rdi
0x140013889  pop     rsi
0x14001388a  retn
```
