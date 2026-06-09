# Nsi::UpdateInterfaceCorporateLocation(_NET_LUID_LH const &,bool)

- ea: `0x180027070`
- end: `0x180027233`
- name: `?UpdateInterfaceCorporateLocation@Nsi@@YA_NAEBT_NET_LUID_LH@@_N@Z`
- size: `451`
- prototype: `bool __fastcall(Nsi *__hidden this, const union _NET_LUID_LH *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001c310`
- `0x180059fc4`

## callees

- `0x180013e48`
- `0x180027070`
- `0x18002723c`
- `0x180047240`
- `0x180047f78`

## import_xrefs

- `NSI!NsiSetAllParameters` at `0x180027188`
- `NSI!NsiSetAllParameters` at `0x1800271bf`
- `NSI!NsiSetAllParameters` at `0x180027188`
- `NSI!NsiSetAllParameters` at `0x1800271bf`

## string_xrefs

- `0x1800270e0`: `Outside`
- `0x1800270eb`: `Inside`

## pseudocode

```c
char __fastcall Nsi::UpdateInterfaceCorporateLocation(Nsi *this, const union _NET_LUID_LH *a2)
{
  char v2; // bl
  const char *v4; // rax
  char v5; // bl
  unsigned int v6; // esi
  int v7; // edi
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h]
  int v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+C8h] [rbp-38h]
  BOOL v14; // [rsp+F8h] [rbp-8h]
  int v15; // [rsp+128h] [rbp+28h]

  v2 = (char)a2;
  v9[0] = 0;
  memset_0(v10, 0, 0xF0u);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x200) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v4 = "Inside";
    if ( !v2 )
      v4 = "Outside";
    WPP_SF_is(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      (unsigned int)WPP_4397259b75113402c37345bc294ea466_Traceguids,
      *(_QWORD *)this,
      (__int64)v4);
  }
  v9[0] = *(_QWORD *)this;
  memset_0(v10, 255, 0xF0u);
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = v2 != 0;
  v15 = 0;
  v5 = 1;
  v6 = ((__int64 (__fastcall *)(__int64, _QWORD, const NPI_MODULEID *, __int64, _QWORD *, int, _BYTE *, int))NsiSetAllParameters)(
         1,
         0,
         &NPI_MS_IPV4_MODULEID,
         7,
         v9,
         8,
         v10,
         240);
  v7 = ((__int64 (__fastcall *)(__int64, _QWORD, const NPI_MODULEID *, __int64, _QWORD *, int, _BYTE *, int))NsiSetAllParameters)(
         1,
         0,
         &NPI_MS_IPV6_MODULEID,
         7,
         v9,
         8,
         v10,
         240);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x200) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_4397259b75113402c37345bc294ea466_Traceguids, v6, v7);
  }
  if ( v6 && v7 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x180027070  mov     [rsp-8+arg_8], rbx
0x180027075  mov     [rsp-8+arg_10], rsi
0x18002707a  push    rbp
0x18002707b  push    rdi
0x18002707c  push    r13
0x18002707e  lea     rbp, [rsp-50h]
0x180027083  sub     rsp, 150h
0x18002708a  mov     rax, cs:__security_cookie
0x180027091  xor     rax, rsp
0x180027094  mov     [rbp+60h+var_20], rax
0x180027098  mov     bl, dl
0x18002709a  mov     [rsp+160h+var_120], 0
0x1800270a3  mov     rdi, rcx
0x1800270a6  mov     r13d, 0F0h
0x1800270ac  mov     r8d, r13d; Size
0x1800270af  lea     rcx, [rsp+160h+var_110]; void *
0x1800270b4  xor     edx, edx; Val
0x1800270b6  call    memset_0
0x1800270bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270c2  lea     rax, WPP_GLOBAL_Control
0x1800270c9  cmp     rcx, rax
0x1800270cc  jz      short loc_18002710E
0x1800270ce  test    dword ptr [rcx+1Ch], 200h
0x1800270d5  jz      short loc_18002710E
0x1800270d7  cmp     byte ptr [rcx+19h], 4
0x1800270db  jb      short loc_18002710E
0x1800270dd  mov     r9, [rdi]
0x1800270e0  lea     rdx, aOutside; "Outside"
0x1800270e7  mov     rcx, [rcx+10h]
0x1800270eb  lea     rax, aInside; "Inside"
0x1800270f2  test    bl, bl
0x1800270f4  lea     r8, WPP_4397259b75113402c37345bc294ea466_Traceguids
0x1800270fb  cmovz   rax, rdx
0x1800270ff  mov     edx, 0Ah
0x180027104  mov     [rsp+160h+var_140], rax
0x180027109  call    WPP_SF_is
0x18002710e  mov     rax, [rdi]
0x180027111  lea     rcx, [rsp+160h+var_110]; void *
0x180027116  mov     r8, r13; Size
0x180027119  mov     [rsp+160h+var_120], rax
0x18002711e  mov     edx, 0FFh; Val
0x180027123  call    memset_0
0x180027128  xor     eax, eax
0x18002712a  mov     [rsp+160h+var_128], r13d
0x18002712f  test    bl, bl
0x180027131  mov     [rsp+160h+var_F0], 0
0x18002713a  mov     edi, 7
0x18002713f  mov     [rsp+160h+var_E8], 0
0x180027147  setnz   al
0x18002714a  mov     [rbp+60h+var_98], 0
0x180027151  mov     [rbp+60h+var_68], eax
0x180027154  lea     r8, NPI_MS_IPV4_MODULEID
0x18002715b  lea     rax, [rsp+160h+var_110]
0x180027160  mov     [rbp+60h+var_38], 0
0x180027167  mov     [rsp+160h+var_130], rax
0x18002716c  lea     ebx, [rdi-6]
0x18002716f  lea     rax, [rsp+160h+var_120]
0x180027174  mov     [rsp+160h+var_138], 8
0x18002717c  mov     r9d, edi
0x18002717f  mov     [rsp+160h+var_140], rax
0x180027184  xor     edx, edx
0x180027186  mov     ecx, ebx
0x180027188  call    cs:__imp_NsiSetAllParameters
0x18002718e  mov     [rsp+160h+var_128], r13d
0x180027193  lea     r8, NPI_MS_IPV6_MODULEID
0x18002719a  mov     esi, eax
0x18002719c  mov     r9d, edi
0x18002719f  lea     rax, [rsp+160h+var_110]
0x1800271a4  xor     edx, edx
0x1800271a6  mov     [rsp+160h+var_130], rax
0x1800271ab  mov     ecx, ebx
0x1800271ad  lea     rax, [rsp+160h+var_120]
0x1800271b2  mov     [rsp+160h+var_138], 8
0x1800271ba  mov     [rsp+160h+var_140], rax
0x1800271bf  call    cs:__imp_NsiSetAllParameters
0x1800271c5  mov     edi, eax
0x1800271c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271ce  lea     rax, WPP_GLOBAL_Control
0x1800271d5  cmp     rcx, rax
0x1800271d8  jz      short loc_180027203
0x1800271da  test    dword ptr [rcx+1Ch], 200h
0x1800271e1  jz      short loc_180027203
0x1800271e3  cmp     byte ptr [rcx+19h], 4
0x1800271e7  jb      short loc_180027203
0x1800271e9  mov     rcx, [rcx+10h]
0x1800271ed  lea     edx, [rbx+0Ah]
0x1800271f0  mov     r9d, esi
0x1800271f3  mov     dword ptr [rsp+160h+var_140], edi
0x1800271f7  lea     r8, WPP_4397259b75113402c37345bc294ea466_Traceguids
0x1800271fe  call    WPP_SF_dd
0x180027203  test    esi, esi
0x180027205  jz      short loc_18002720D
0x180027207  test    edi, edi
0x180027209  jz      short loc_18002720D
0x18002720b  xor     bl, bl
0x18002720d  mov     al, bl
0x18002720f  mov     rcx, [rbp+60h+var_20]
0x180027213  xor     rcx, rsp; StackCookie
0x180027216  call    __security_check_cookie
0x18002721b  lea     r11, [rsp+160h+var_10]
0x180027223  mov     rbx, [r11+28h]
0x180027227  mov     rsi, [r11+30h]
0x18002722b  mov     rsp, r11
0x18002722e  pop     r13
0x180027230  pop     rdi
0x180027231  pop     rbp
0x180027232  retn
```
