# CHostObj::Create(CHost *,int,ushort const * *,CHostObj * *)

- ea: `0x140001bd0`
- end: `0x140001e13`
- name: `?Create@CHostObj@@SAJPEAVCHost@@HPEAPEBGPEAPEAV1@@Z`
- size: `579`
- prototype: `static int(struct CHost *, int, const unsigned __int16 **, struct CHostObj **)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1400014b0`

## callees

- `0x140001bd0`
- `0x140002180`
- `0x14000275c`
- `0x140007580`
- `0x140008ccc`
- `0x140009c70`
- `0x14001385c`
- `0x140016182`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140001c53`
- `OLEAUT32!__imp_SysAllocString` at `0x140001ce3`
- `OLEAUT32!__imp_SysAllocString` at `0x140001c53`
- `OLEAUT32!__imp_SysAllocString` at `0x140001ce3`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140001d15`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140001d15`

## pseudocode

```c
__int64 __fastcall CHostObj::Create(
        const OLECHAR *a1,
        signed int a2,
        const unsigned __int16 **a3,
        struct CHostObj **a4)
{
  CArguments *v7; // r14
  CHostObj *v9; // rax
  struct IUnknown *v10; // rdx
  CHostObj *v11; // rax
  CHostObj *v12; // rdi
  const OLECHAR *v13; // rsi
  BSTR v14; // rax
  OLECHAR v15; // ax
  const OLECHAR *v16; // rdx
  char *i; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  char *v20; // rdx
  __int64 v21; // rbx
  BSTR v22; // rax
  HRESULT v23; // ebx
  int v24; // eax
  ITypeLib *pptlib; // [rsp+20h] [rbp-268h] BYREF
  CArguments *v27; // [rsp+28h] [rbp-260h] BYREF
  OLECHAR psz[264]; // [rsp+30h] [rbp-258h] BYREF

  v7 = 0;
  v27 = 0;
  pptlib = 0;
  v9 = (CHostObj *)operator new(0x88u);
  if ( !v9 )
  {
    v12 = 0;
LABEL_24:
    v23 = -2147024882;
    goto LABEL_25;
  }
  v11 = CHostObj::CHostObj(v9, v10);
  v12 = v11;
  if ( !v11 )
    goto LABEL_24;
  v13 = a1 + 40;
  *((_QWORD *)v11 + 16) = a1;
  v14 = SysAllocString(a1 + 40);
  *((_QWORD *)v12 + 10) = v14;
  if ( !v14 )
    goto LABEL_24;
  v15 = *v13;
  v16 = a1 + 40;
  for ( i = (char *)(a1 + 40); v15; i += 2 )
  {
    if ( v15 == 47 || v15 == 92 )
      v16 = (const OLECHAR *)i;
    v15 = *((_WORD *)i + 1);
  }
  psz[0] = 0;
  if ( v16 != v13 )
  {
    v18 = (unsigned __int64)((char *)v16 - (char *)v13) >> 1;
    if ( (_DWORD)v18 )
    {
      if ( (unsigned int)(v18 + 1) >= 0x104 )
        goto LABEL_15;
    }
    else
    {
      LODWORD(v18) = 1;
    }
    v19 = (unsigned int)v18;
    v20 = (char *)(a1 + 40);
    v21 = v19;
    memcpy_0(psz, v20, 2 * v19);
    psz[v21] = 0;
    goto LABEL_15;
  }
  *(_DWORD *)psz = 46;
LABEL_15:
  v22 = SysAllocString(psz);
  *((_QWORD *)v12 + 11) = v22;
  if ( !v22 )
    goto LABEL_24;
  LoadStr((unsigned __int16 **)v12 + 9, Global::g_lResourceBase + 1);
  if ( !*((_QWORD *)v12 + 9) )
    goto LABEL_24;
  v23 = LoadTypeLib(v13, &pptlib);
  if ( v23 >= 0 )
  {
    v23 = CDispatch::CacheTypeInfo((CHostObj *)((char *)v12 + 16), pptlib);
    if ( v23 >= 0 )
    {
      v24 = CArguments::Create(a2, a3, &v27);
      v7 = v27;
      v23 = v24;
      if ( v24 >= 0 )
      {
        v23 = CArguments::CacheTypeInfo(v27, pptlib);
        if ( v23 >= 0 )
        {
          v23 = (**(__int64 (__fastcall ***)(CArguments *, GUID *, __int64))v7)(v7, &IID_IArguments2, (__int64)v12 + 96);
          if ( v23 >= 0 )
          {
            *a4 = v12;
            v12 = 0;
            v23 = 0;
          }
        }
      }
    }
  }
LABEL_25:
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  if ( v7 )
    (*(void (__fastcall **)(CArguments *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v12 )
    (*(void (__fastcall **)(CHostObj *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140001bd0  mov     r11, rsp
0x140001bd3  push    rbx
0x140001bd4  push    rdi
0x140001bd5  sub     rsp, 278h
0x140001bdc  mov     rax, cs:__security_cookie
0x140001be3  xor     rax, rsp
0x140001be6  mov     [rsp+288h+var_48], rax
0x140001bee  mov     [r11-18h], rbp
0x140001bf2  mov     rbx, rcx
0x140001bf5  mov     [r11-20h], rsi
0x140001bf9  mov     ecx, 88h; Size
0x140001bfe  mov     [r11-28h], r12
0x140001c02  mov     ebp, edx
0x140001c04  mov     [r11-30h], r14
0x140001c08  mov     r12, r8
0x140001c0b  mov     [r11-38h], r15
0x140001c0f  xor     r14d, r14d
0x140001c12  mov     [rsp+288h+var_260], r14
0x140001c17  mov     r15, r9
0x140001c1a  mov     [rsp+288h+pptlib], 0
0x140001c23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001c28  test    rax, rax
0x140001c2b  jz      loc_140001D8A
0x140001c31  mov     rcx, rax; this
0x140001c34  call    ??0CHostObj@@AEAA@PEAUIUnknown@@@Z; CHostObj::CHostObj(IUnknown *)
0x140001c39  mov     rdi, rax
0x140001c3c  test    rax, rax
0x140001c3f  jz      loc_140001D8C
0x140001c45  lea     rsi, [rbx+50h]
0x140001c49  mov     [rax+80h], rbx
0x140001c50  mov     rcx, rsi; psz
0x140001c53  call    cs:__imp_SysAllocString
0x140001c59  mov     [rdi+50h], rax
0x140001c5d  test    rax, rax
0x140001c60  jz      loc_140001D8C
0x140001c66  movzx   eax, word ptr [rsi]
0x140001c69  mov     rdx, rsi
0x140001c6c  mov     rcx, rsi
0x140001c6f  test    ax, ax
0x140001c72  jz      short loc_140001C90
0x140001c74  cmp     ax, 2Fh ; '/'
0x140001c78  jz      short loc_140001C80
0x140001c7a  cmp     ax, 5Ch ; '\'
0x140001c7e  jnz     short loc_140001C83
0x140001c80  mov     rdx, rcx
0x140001c83  movzx   eax, word ptr [rcx+2]
0x140001c87  add     rcx, 2
0x140001c8b  test    ax, ax
0x140001c8e  jnz     short loc_140001C74
0x140001c90  xor     eax, eax
0x140001c92  mov     [rsp+288h+psz], ax
0x140001c97  cmp     rdx, rsi
0x140001c9a  jnz     short loc_140001CA6
0x140001c9c  mov     dword ptr [rsp+288h+psz], 2Eh ; '.'
0x140001ca4  jmp     short loc_140001CDE
0x140001ca6  sub     rdx, rsi
0x140001ca9  shr     rdx, 1
0x140001cac  test    edx, edx
0x140001cae  jnz     short loc_140001CB7
0x140001cb0  mov     edx, 1
0x140001cb5  jmp     short loc_140001CC1
0x140001cb7  lea     eax, [rdx+1]
0x140001cba  cmp     eax, 104h
0x140001cbf  jnb     short loc_140001CDE
0x140001cc1  mov     eax, edx
0x140001cc3  lea     rcx, [rsp+288h+psz]; void *
0x140001cc8  mov     rdx, rsi; Src
0x140001ccb  lea     rbx, [rax+rax]
0x140001ccf  mov     r8, rbx; Size
0x140001cd2  call    memcpy_0
0x140001cd7  xor     eax, eax
0x140001cd9  mov     [rsp+rbx+288h+psz], ax
0x140001cde  lea     rcx, [rsp+288h+psz]; psz
0x140001ce3  call    cs:__imp_SysAllocString
0x140001ce9  mov     [rdi+58h], rax
0x140001ced  test    rax, rax
0x140001cf0  jz      loc_140001D8C
0x140001cf6  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140001cfc  lea     rcx, [rdi+48h]; unsigned __int16 **
0x140001d00  inc     edx; unsigned int
0x140001d02  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x140001d07  cmp     [rdi+48h], r14
0x140001d0b  jz      short loc_140001D8C
0x140001d0d  lea     rdx, [rsp+288h+pptlib]; pptlib
0x140001d12  mov     rcx, rsi; szFile
0x140001d15  call    cs:__imp_LoadTypeLib
0x140001d1b  mov     ebx, eax
0x140001d1d  test    eax, eax
0x140001d1f  js      short loc_140001D91
0x140001d21  mov     rdx, [rsp+288h+pptlib]; struct ITypeLib *
0x140001d26  lea     rcx, [rdi+10h]; this
0x140001d2a  call    ?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z; CDispatch::CacheTypeInfo(ITypeLib *)
0x140001d2f  mov     ebx, eax
0x140001d31  test    eax, eax
0x140001d33  js      short loc_140001D91
0x140001d35  lea     r8, [rsp+288h+var_260]; struct CArguments **
0x140001d3a  mov     rdx, r12; unsigned __int16 **
0x140001d3d  mov     ecx, ebp; int
0x140001d3f  call    ?Create@CArguments@@SAJJPEAPEBGPEAPEAV1@@Z; CArguments::Create(long,ushort const * *,CArguments * *)
0x140001d44  mov     r14, [rsp+288h+var_260]
0x140001d49  mov     ebx, eax
0x140001d4b  test    eax, eax
0x140001d4d  js      short loc_140001D91
0x140001d4f  mov     rdx, [rsp+288h+pptlib]; struct ITypeLib *
0x140001d54  mov     rcx, r14; this
0x140001d57  call    ?CacheTypeInfo@CArguments@@QEAAJPEAUITypeLib@@@Z; CArguments::CacheTypeInfo(ITypeLib *)
0x140001d5c  mov     ebx, eax
0x140001d5e  test    eax, eax
0x140001d60  js      short loc_140001D91
0x140001d62  mov     rax, [r14]
0x140001d65  lea     r8, [rdi+60h]
0x140001d69  lea     rdx, IID_IArguments2
0x140001d70  mov     rcx, r14
0x140001d73  mov     rax, [rax]
0x140001d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d7b  mov     ebx, eax
0x140001d7d  test    eax, eax
0x140001d7f  js      short loc_140001D91
0x140001d81  mov     [r15], rdi
0x140001d84  xor     edi, edi
0x140001d86  xor     ebx, ebx
0x140001d88  jmp     short loc_140001D91
0x140001d8a  xor     edi, edi
0x140001d8c  mov     ebx, 8007000Eh
0x140001d91  mov     rcx, [rsp+288h+pptlib]
0x140001d96  mov     r15, [rsp+288h+var_38]
0x140001d9e  mov     r12, [rsp+288h+var_28]
0x140001da6  mov     rsi, [rsp+288h+var_20]
0x140001dae  mov     rbp, [rsp+288h+var_18]
0x140001db6  test    rcx, rcx
0x140001db9  jz      short loc_140001DC7
0x140001dbb  mov     rax, [rcx]
0x140001dbe  mov     rax, [rax+10h]
0x140001dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001dc7  test    r14, r14
0x140001dca  jz      short loc_140001DDB
0x140001dcc  mov     rax, [r14]
0x140001dcf  mov     rcx, r14
0x140001dd2  mov     rax, [rax+10h]
0x140001dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ddb  mov     r14, [rsp+288h+var_30]
0x140001de3  test    rdi, rdi
0x140001de6  jz      short loc_140001DF7
0x140001de8  mov     rax, [rdi]
0x140001deb  mov     rcx, rdi
0x140001dee  mov     rax, [rax+10h]
0x140001df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001df7  mov     eax, ebx
0x140001df9  mov     rcx, [rsp+288h+var_48]
0x140001e01  xor     rcx, rsp; StackCookie
0x140001e04  call    __security_check_cookie
0x140001e09  add     rsp, 278h
0x140001e10  pop     rdi
0x140001e11  pop     rbx
0x140001e12  retn
```
