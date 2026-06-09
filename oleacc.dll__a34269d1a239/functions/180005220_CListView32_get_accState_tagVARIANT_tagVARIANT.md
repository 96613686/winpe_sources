# CListView32::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x180005220`
- end: `0x18000544c`
- name: `?get_accState@CListView32@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CListView32 *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180005220`
- `0x1800056a4`
- `0x180005ca0`
- `0x18000612c`
- `0x180006510`
- `0x18000b890`
- `0x18000baa0`
- `0x18000ce1c`
- `0x18000d2b0`
- `0x180019d38`
- `0x180049010`

## import_xrefs

- `USER32!GetWindowLongW` at `0x18000530b`
- `USER32!GetWindowLongW` at `0x18000530b`

## string_xrefs

- `0x18000537a`: `CAccessible::AccSendMessageTimeout`

## pseudocode

```c
__int64 __fastcall CListView32::get_accState(HWND *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  __int64 result; // rax
  LONG lVal; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  HWND v9; // r8
  __int16 v10; // r14
  HWND v11; // rbx
  HWND v12; // r12
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // edx
  unsigned int v16; // r8d
  HWND v17; // rcx
  HWND v18; // rcx
  int v19; // [rsp+28h] [rbp-48h]
  int v20[4]; // [rsp+40h] [rbp-30h] BYREF
  struct tagVARIANT v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v23; // [rsp+B0h] [rbp+40h] BYREF
  int v24; // [rsp+B4h] [rbp+44h]

  a3->vt = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *))*this + 30))(this) )
    return 2147942487LL;
  lVal = a2->lVal;
  if ( lVal )
  {
    v9 = this[10];
    v22 = 0;
    result = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v9, 0x102Cu, lVal - 1, 0xFFFFFFFFLL, &v22);
    if ( (int)result >= 0 )
    {
      v10 = v22;
      a3->vt = 3;
      a3->lVal = 0x100000;
      v11 = this[10];
      if ( MyGetFocus() == v11 && (v10 & 1) != 0 )
        a3->lVal |= 4u;
      a3->lVal |= 0x200000u;
      if ( (GetWindowLongW(this[10], -16) & 4) == 0 )
        a3->lVal |= 0x1000000u;
      if ( (v10 & 2) != 0 )
        a3->lVal |= 2u;
      if ( (v10 & 8) != 0 )
        a3->lVal |= 0x80u;
      v12 = this[10];
      v23 = *((_DWORD *)this + 25);
      v24 = *((_DWORD *)this + 17);
      v13 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)&v23, v12, 0x1037u, 0, 0, &v22);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( (v22 & 4) != 0 && (v10 & 0xF000) == 0x2000 )
          a3->lVal |= 0x10u;
        if ( IsClippedByWindow((struct IAccessible *)this, a2, this[10]) )
          a3->lVal |= 0x18000u;
        if ( (unsigned int)LVGetImageIndex(this[10], a2->lVal - 1, v20) )
        {
          v17 = this[10];
          LODWORD(v22) = 0;
          *(GUID *)&v21.vt = PROPID_ACC_STATEMAP;
          if ( (unsigned int)CheckDWORDMap(v17, v15, v16, (struct _GUID *)&v21, v20, v19, (unsigned int *)&v22)
            || (v18 = this[10], v23 = 0, (unsigned int)GetStateImageMapEnt(v18, v20[0], (unsigned int *)&v22, &v23)) )
          {
            a3->lVal |= v22;
          }
        }
        return 0;
      }
      else
      {
        Error::IAccessibleError(0, L"CAccessible::AccSendMessageTimeout", v13, v12, 5002);
        return v14;
      }
    }
  }
  else
  {
    pRecInfo = a2->pRecInfo;
    *(_OWORD *)&v21.vt = *(_OWORD *)&a2->vt;
    v21.pRecInfo = pRecInfo;
    return CClient::get_accState((CClient *)this, &v21, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180005220  mov     [rsp-28h+arg_8], rbx
0x180005225  mov     [rsp-28h+arg_18], rsi
0x18000522a  push    rbp
0x18000522b  push    rdi
0x18000522c  push    r12
0x18000522e  push    r14
0x180005230  push    r15
0x180005232  mov     rbp, rsp
0x180005235  sub     rsp, 70h
0x180005239  xor     eax, eax
0x18000523b  mov     rdi, r8
0x18000523e  mov     [r8], ax
0x180005242  mov     r15, rdx
0x180005245  mov     rax, [rcx]
0x180005248  mov     rsi, rcx
0x18000524b  mov     rax, [rax+0F0h]
0x180005252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005257  test    eax, eax
0x180005259  jnz     short loc_180005265
0x18000525b  mov     eax, 80070057h
0x180005260  jmp     loc_180005433
0x180005265  mov     eax, [r15+8]
0x180005269  test    eax, eax
0x18000526b  jnz     short loc_180005294
0x18000526d  movups  xmm0, xmmword ptr [r15]
0x180005271  lea     rdx, [rbp+var_20]; struct tagVARIANT
0x180005275  mov     r8, rdi; struct tagVARIANT *
0x180005278  movsd   xmm1, qword ptr [r15+10h]
0x18000527e  mov     rcx, rsi; this
0x180005281  movaps  xmmword ptr [rbp+var_20], xmm0
0x180005285  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18000528a  call    ?get_accState@CClient@@UEAAJUtagVARIANT@@PEAU2@@Z; CClient::get_accState(tagVARIANT,tagVARIANT *)
0x18000528f  jmp     loc_180005433
0x180005294  mov     r8, [rsi+50h]; HWND
0x180005298  dec     eax
0x18000529a  movsxd  rcx, eax
0x18000529d  mov     r9d, 102Ch; unsigned int
0x1800052a3  lea     rax, [rbp+arg_0]
0x1800052a7  mov     [rbp+arg_0], 0
0x1800052af  mov     [rsp+70h+var_40], rax; __int64 *
0x1800052b4  xor     edx, edx; bool
0x1800052b6  mov     eax, 0FFFFFFFFh
0x1800052bb  mov     [rsp+70h+var_48], rax; __int64
0x1800052c0  mov     [rsp+70h+var_50], rcx; unsigned __int64
0x1800052c5  mov     rcx, rsi; this
0x1800052c8  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800052cd  test    eax, eax
0x1800052cf  js      loc_180005433
0x1800052d5  mov     r14d, dword ptr [rbp+arg_0]
0x1800052d9  mov     word ptr [rdi], 3
0x1800052de  mov     dword ptr [rdi+8], 100000h
0x1800052e5  mov     rbx, [rsi+50h]
0x1800052e9  call    ?MyGetFocus@@YAPEAUHWND__@@XZ; MyGetFocus(void)
0x1800052ee  cmp     rax, rbx
0x1800052f1  jnz     short loc_1800052FD
0x1800052f3  test    r14b, 1
0x1800052f7  jz      short loc_1800052FD
0x1800052f9  or      dword ptr [rdi+8], 4
0x1800052fd  bts     dword ptr [rdi+8], 15h
0x180005302  mov     edx, 0FFFFFFF0h; nIndex
0x180005307  mov     rcx, [rsi+50h]; hWnd
0x18000530b  call    cs:__imp_GetWindowLongW
0x180005311  test    al, 4
0x180005313  jnz     short loc_18000531A
0x180005315  bts     dword ptr [rdi+8], 18h
0x18000531a  test    r14b, 2
0x18000531e  jz      short loc_180005324
0x180005320  or      dword ptr [rdi+8], 2
0x180005324  test    r14b, 8
0x180005328  jz      short loc_18000532F
0x18000532a  bts     dword ptr [rdi+8], 7
0x18000532f  mov     eax, [rsi+64h]
0x180005332  lea     rcx, [rbp+arg_10]; struct OLEACC_TIMEOUTDATA *
0x180005336  mov     r12, [rsi+50h]
0x18000533a  xor     r9d, r9d; unsigned __int64
0x18000533d  mov     [rbp+arg_10], eax
0x180005340  mov     r8d, 1037h; unsigned int
0x180005346  mov     eax, [rsi+44h]
0x180005349  mov     rdx, r12; HWND
0x18000534c  mov     [rbp+arg_14], eax
0x18000534f  lea     rax, [rbp+arg_0]
0x180005353  mov     [rsp+70h+var_48], rax; int
0x180005358  mov     [rsp+70h+var_50], 0; __int64
0x180005361  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180005366  mov     ebx, eax
0x180005368  test    eax, eax
0x18000536a  jns     short loc_18000538F
0x18000536c  mov     r9, r12; HWND
0x18000536f  mov     dword ptr [rsp+70h+var_50], 138Ah; int
0x180005377  mov     r8d, eax; int
0x18000537a  lea     rdx, aCaccessibleAcc; "CAccessible::AccSendMessageTimeout"
0x180005381  xor     ecx, ecx; struct IUnknown *
0x180005383  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x180005388  mov     eax, ebx
0x18000538a  jmp     loc_180005433
0x18000538f  test    byte ptr [rbp+arg_0], 4
0x180005393  jz      short loc_1800053A9
0x180005395  and     r14d, 0F000h
0x18000539c  cmp     r14d, 2000h
0x1800053a3  jnz     short loc_1800053A9
0x1800053a5  or      dword ptr [rdi+8], 10h
0x1800053a9  mov     r8, [rsi+50h]; HWND
0x1800053ad  mov     rdx, r15; struct tagVARIANT *
0x1800053b0  mov     rcx, rsi; struct IAccessible *
0x1800053b3  call    ?IsClippedByWindow@@YAHPEAUIAccessible@@AEAUtagVARIANT@@PEAUHWND__@@@Z; IsClippedByWindow(IAccessible *,tagVARIANT &,HWND__ *)
0x1800053b8  test    eax, eax
0x1800053ba  jz      short loc_1800053C3
0x1800053bc  or      dword ptr [rdi+8], 18000h
0x1800053c3  mov     edx, [r15+8]
0x1800053c7  lea     r8, [rbp+var_30]; int *
0x1800053cb  mov     rcx, [rsi+50h]; HWND
0x1800053cf  dec     edx; int
0x1800053d1  call    ?LVGetImageIndex@@YAHPEAUHWND__@@HQEAH@Z; LVGetImageIndex(HWND__ *,int,int * const)
0x1800053d6  test    eax, eax
0x1800053d8  jz      short loc_180005431
0x1800053da  movups  xmm0, xmmword ptr cs:PROPID_ACC_STATEMAP.Data1
0x1800053e1  mov     rcx, [rsi+50h]; HWND
0x1800053e5  lea     rax, [rbp+arg_0]
0x1800053e9  mov     [rsp+70h+var_40], rax; unsigned int *
0x1800053ee  lea     r9, [rbp+var_20]; struct _GUID *
0x1800053f2  lea     rax, [rbp+var_30]
0x1800053f6  mov     dword ptr [rbp+arg_0], 0
0x1800053fd  mov     [rsp+70h+var_50], rax; int *
0x180005402  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180005407  call    ?CheckDWORDMap@@YAHPEAUHWND__@@KKU_GUID@@PEAHHPEAK@Z; CheckDWORDMap(HWND__ *,ulong,ulong,_GUID,int *,int,ulong *)
0x18000540c  test    eax, eax
0x18000540e  jnz     short loc_18000542B
0x180005410  mov     edx, [rbp+var_30]; int
0x180005413  lea     r9, [rbp+arg_10]; unsigned int *
0x180005417  mov     rcx, [rsi+50h]; HWND
0x18000541b  lea     r8, [rbp+arg_0]; unsigned int *
0x18000541f  mov     [rbp+arg_10], eax
0x180005422  call    ?GetStateImageMapEnt@@YAHPEAUHWND__@@HPEAK1@Z; GetStateImageMapEnt(HWND__ *,int,ulong *,ulong *)
0x180005427  test    eax, eax
0x180005429  jz      short loc_180005431
0x18000542b  mov     eax, dword ptr [rbp+arg_0]
0x18000542e  or      [rdi+8], eax
0x180005431  xor     eax, eax
0x180005433  lea     r11, [rsp+70h+var_s0]
0x180005438  mov     rbx, [r11+38h]
0x18000543c  mov     rsi, [r11+48h]
0x180005440  mov     rsp, r11
0x180005443  pop     r15
0x180005445  pop     r14
0x180005447  pop     r12
0x180005449  pop     rdi
0x18000544a  pop     rbp
0x18000544b  retn
```
