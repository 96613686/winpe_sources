# CSpellContextHandler::InsertAlternates(HMENU__ *,IEnumString *,bool)

- ea: `0x180279718`
- end: `0x180279a46`
- name: `?InsertAlternates@CSpellContextHandler@@AEAAJPEAUHMENU__@@PEAUIEnumString@@_N@Z`
- size: `814`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this, HMENU, struct IEnumString *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18027a7a8`
- `0x18027abe4`

## callees

- `0x18006ad18`
- `0x180278a28`
- `0x180278bd8`
- `0x180278c74`
- `0x180278d34`
- `0x180279718`
- `0x180279a4c`
- `0x180279aec`
- `0x180279c28`
- `0x180279c98`
- `0x18027f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18027988e`
- `OLEAUT32!__imp_SysFreeString` at `0x18027988e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027985b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027985b`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::InsertAlternates(
        CSpellContextHandler *this,
        HMENU a2,
        struct IEnumString *a3,
        char a4)
{
  __int64 v7; // rcx
  int Command; // ebx
  unsigned int v9; // esi
  struct IEnumStringVtbl *lpVtbl; // rax
  __int64 v11; // r12
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  UINT v13; // esi
  bool inserted; // bl
  unsigned int v15; // esi
  __int64 v16; // rdx
  bool v17; // al
  HMENU LanguageSubmenu; // rax
  unsigned int v20; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  char v23; // [rsp+90h] [rbp+40h] BYREF
  char v24; // [rsp+98h] [rbp+48h]

  v24 = a4;
  if ( !a3 )
  {
    v7 = *((_QWORD *)this + 6);
    if ( v7 )
      goto LABEL_5;
    return 2147549183LL;
  }
  if ( *((_QWORD *)this + 6) )
    return 2147549183LL;
  v7 = 0;
LABEL_5:
  Command = 0;
  v20 = *((_DWORD *)this + 18) - *((_DWORD *)this + 16) + 1;
  if ( v7 )
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 40LL))(v7, &v20);
  v9 = *((_DWORD *)this + 16);
  v23 = 0;
  while ( v9 <= *((_DWORD *)this + 18) )
  {
    pv[0] = 0;
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      LODWORD(v21) = 0;
      Command = ((__int64 (__fastcall *)(struct IEnumString *, __int64, LPVOID *, __int64 *))lpVtbl->Next)(
                  a3,
                  1,
                  pv,
                  &v21);
    }
    else
    {
      v11 = *((_QWORD *)this + 6);
      if ( v11 )
      {
        v21 = 0;
        v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 32LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        Command = v12(v11, v9 - *((_DWORD *)this + 16), &v21);
        if ( Command >= 0 )
          Command = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v21 + 24LL))(v21, pv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      }
    }
    if ( Command < 0 )
      goto LABEL_28;
    if ( !pv[0] )
      break;
    if ( a2 )
    {
      if ( !CSpellContextHandler::InsertMenuItemFromString(
              a2,
              v9 - *((_DWORD *)this + 16),
              (unsigned __int16 *)pv[0],
              v9) )
        goto LABEL_19;
LABEL_24:
      v23 = 1;
      goto LABEL_20;
    }
    if ( !*((_QWORD *)this + 18) )
    {
LABEL_19:
      Command = -2147418113;
      goto LABEL_20;
    }
    Command = CSpellContextHandler::CreateCommand(this, (PCWSTR)pv[0], v9);
    if ( Command >= 0 )
      goto LABEL_24;
LABEL_20:
    if ( a3 )
      CoTaskMemFree(pv[0]);
    else
      SysFreeString((BSTR)pv[0]);
    if ( Command >= 0 )
      ++v9;
LABEL_28:
    if ( v20 < v9 - *((_DWORD *)this + 16) + 1 || Command < 0 )
      break;
  }
  v13 = v9 - *((_DWORD *)this + 16);
  if ( !v23 )
    goto LABEL_37;
  if ( Command < 0 )
    return (unsigned int)Command;
  if ( a2 )
  {
    if ( CSpellContextHandler::InsertSeparator(a2, v13) )
    {
      ++v13;
      goto LABEL_37;
    }
    return (unsigned int)Command;
  }
  if ( !*((_QWORD *)this + 18) )
    return (unsigned int)-2147418113;
  Command = CSpellContextHandler::CreateCommandSeparator(this);
LABEL_37:
  if ( Command >= 0 )
  {
    if ( a2 )
    {
      inserted = CSpellContextHandler::InsertMenuItemFromResource(
                   this,
                   a2,
                   v13,
                   *((_DWORD *)this + 25),
                   *((_DWORD *)this + 21));
      if ( inserted )
      {
        v15 = v13 + 1;
        if ( *((_BYTE *)this + 158) )
          goto LABEL_47;
        inserted = CSpellContextHandler::InsertMenuItemFromResource(
                     this,
                     a2,
                     v15,
                     *((_DWORD *)this + 26),
                     *((_DWORD *)this + 22));
        v23 = 0;
        ++v15;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 256LL))(
               *(_QWORD *)(*((_QWORD *)this + 3) + 72LL),
               &v23) )
        {
          if ( v23 )
          {
            v17 = CSpellContextHandler::InsertMenuItemFromResource(
                    this,
                    a2,
                    v15,
                    *((_DWORD *)this + 34),
                    *((_DWORD *)this + 23));
          }
          else
          {
            LanguageSubmenu = CSpellContextHandler::CreateLanguageSubmenu(this, v16);
            v17 = CSpellContextHandler::InsertSubMenuFromResource(
                    this,
                    a2,
                    v15,
                    *((_DWORD *)this + 31),
                    LanguageSubmenu);
          }
          ++v15;
          inserted = v17;
        }
        if ( inserted )
        {
LABEL_47:
          if ( v24 )
            inserted = CSpellContextHandler::InsertSeparator(a2, v15);
        }
      }
      return !inserted ? 0x8000FFFF : 0;
    }
    if ( *((_QWORD *)this + 18) )
    {
      Command = CSpellContextHandler::CreateCommandFromResource(this, *((_DWORD *)this + 25), *((_DWORD *)this + 21));
      if ( Command >= 0 && !*((_BYTE *)this + 158) )
        return (unsigned int)CSpellContextHandler::CreateCommandFromResource(
                               this,
                               *((_DWORD *)this + 26),
                               *((_DWORD *)this + 22));
      return (unsigned int)Command;
    }
    return (unsigned int)-2147418113;
  }
  return (unsigned int)Command;
}

```

## disassembly

```asm
0x180279718  mov     [rsp-28h+arg_0], rbx
0x18027971d  mov     [rsp-28h+arg_8], rsi
0x180279722  mov     [rsp-28h+arg_18], r9b
0x180279727  push    rbp
0x180279728  push    rdi
0x180279729  push    r12
0x18027972b  push    r13
0x18027972d  push    r14
0x18027972f  mov     rbp, rsp
0x180279732  sub     rsp, 50h
0x180279736  mov     r13, r8
0x180279739  mov     r14, rdx
0x18027973c  mov     rdi, rcx
0x18027973f  test    r8, r8
0x180279742  jz      short loc_180279753
0x180279744  cmp     qword ptr [rcx+30h], 0
0x180279749  jnz     loc_180279A27
0x18027974f  xor     ecx, ecx
0x180279751  jmp     short loc_180279760
0x180279753  mov     rcx, [rcx+30h]
0x180279757  test    rcx, rcx
0x18027975a  jz      loc_180279A27
0x180279760  mov     eax, [rdi+48h]
0x180279763  xor     ebx, ebx
0x180279765  sub     eax, [rdi+40h]
0x180279768  inc     eax
0x18027976a  mov     [rbp+var_20], eax
0x18027976d  test    rcx, rcx
0x180279770  jz      short loc_180279782
0x180279772  mov     rax, [rcx]
0x180279775  lea     rdx, [rbp+var_20]
0x180279779  mov     rax, [rax+28h]
0x18027977d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180279782  mov     esi, [rdi+40h]
0x180279785  xor     al, al
0x180279787  mov     [rbp+arg_10], al
0x18027978a  cmp     esi, [rdi+48h]
0x18027978d  ja      loc_1802798B4
0x180279793  mov     [rbp+pv], 0
0x18027979b  test    r13, r13
0x18027979e  jz      short loc_1802797C8
0x1802797a0  mov     rax, [r13+0]
0x1802797a4  lea     r9, [rbp+var_18]
0x1802797a8  lea     r8, [rbp+pv]
0x1802797ac  mov     dword ptr [rbp+var_18], 0
0x1802797b3  mov     edx, 1
0x1802797b8  mov     rcx, r13
0x1802797bb  mov     rax, [rax+18h]
0x1802797bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802797c4  mov     ebx, eax
0x1802797c6  jmp     short loc_180279823
0x1802797c8  mov     r12, [rdi+30h]
0x1802797cc  test    r12, r12
0x1802797cf  jz      short loc_180279823
0x1802797d1  mov     [rbp+var_18], 0
0x1802797d9  lea     rcx, [rbp+var_18]
0x1802797dd  mov     rax, [r12]
0x1802797e1  mov     rbx, [rax+20h]
0x1802797e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802797ea  mov     edx, esi
0x1802797ec  lea     r8, [rbp+var_18]
0x1802797f0  sub     edx, [rdi+40h]
0x1802797f3  mov     rcx, r12
0x1802797f6  mov     rax, rbx
0x1802797f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802797fe  mov     ebx, eax
0x180279800  test    eax, eax
0x180279802  js      short loc_18027981A
0x180279804  mov     rcx, [rbp+var_18]
0x180279808  lea     rdx, [rbp+pv]
0x18027980c  mov     rax, [rcx]
0x18027980f  mov     rax, [rax+18h]
0x180279813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180279818  mov     ebx, eax
0x18027981a  lea     rcx, [rbp+var_18]
0x18027981e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180279823  test    ebx, ebx
0x180279825  js      short loc_1802798A0
0x180279827  mov     r8, [rbp+pv]; unsigned __int16 *
0x18027982b  test    r8, r8
0x18027982e  jz      loc_1802798B4
0x180279834  test    r14, r14
0x180279837  jz      short loc_180279869
0x180279839  mov     edx, esi
0x18027983b  mov     r9d, esi; unsigned int
0x18027983e  sub     edx, [rdi+40h]; item
0x180279841  mov     rcx, r14; hmenu
0x180279844  call    ?InsertMenuItemFromString@CSpellContextHandler@@CA_NPEAUHMENU__@@IPEAGI@Z; CSpellContextHandler::InsertMenuItemFromString(HMENU__ *,uint,ushort *,uint)
0x180279849  test    al, al
0x18027984b  jnz     short loc_180279888
0x18027984d  mov     ebx, 8000FFFFh
0x180279852  mov     rcx, [rbp+pv]; bstrString
0x180279856  test    r13, r13
0x180279859  jz      short loc_18027988E
0x18027985b  call    cs:__imp_CoTaskMemFree
0x180279862  nop     dword ptr [rax+rax+00h]
0x180279867  jmp     short loc_18027989A
0x180279869  cmp     qword ptr [rdi+90h], 0
0x180279871  jz      short loc_18027984D
0x180279873  mov     rdx, [rbp+pv]; sourceString
0x180279877  mov     r8d, esi; unsigned int
0x18027987a  mov     rcx, rdi; this
0x18027987d  call    ?CreateCommand@CSpellContextHandler@@AEAAJPEBGH@Z; CSpellContextHandler::CreateCommand(ushort const *,int)
0x180279882  mov     ebx, eax
0x180279884  test    eax, eax
0x180279886  js      short loc_180279852
0x180279888  mov     [rbp+arg_10], 1
0x18027988c  jmp     short loc_180279852
0x18027988e  call    cs:__imp_SysFreeString
0x180279895  nop     dword ptr [rax+rax+00h]
0x18027989a  test    ebx, ebx
0x18027989c  js      short loc_1802798A0
0x18027989e  inc     esi
0x1802798a0  mov     eax, esi
0x1802798a2  sub     eax, [rdi+40h]
0x1802798a5  inc     eax
0x1802798a7  cmp     [rbp+var_20], eax
0x1802798aa  jb      short loc_1802798B4
0x1802798ac  test    ebx, ebx
0x1802798ae  jns     loc_18027978A
0x1802798b4  sub     esi, [rdi+40h]
0x1802798b7  cmp     [rbp+arg_10], 0
0x1802798bb  jz      short loc_1802798F8
0x1802798bd  test    ebx, ebx
0x1802798bf  js      loc_180279A23
0x1802798c5  test    r14, r14
0x1802798c8  jz      short loc_1802798E0
0x1802798ca  mov     edx, esi; item
0x1802798cc  mov     rcx, r14; hmenu
0x1802798cf  call    ?InsertSeparator@CSpellContextHandler@@CA_NPEAUHMENU__@@I@Z; CSpellContextHandler::InsertSeparator(HMENU__ *,uint)
0x1802798d4  test    al, al
0x1802798d6  jz      loc_180279A23
0x1802798dc  inc     esi
0x1802798de  jmp     short loc_1802798F8
0x1802798e0  cmp     qword ptr [rdi+90h], 0
0x1802798e8  jz      loc_180279A1E
0x1802798ee  mov     rcx, rdi; this
0x1802798f1  call    ?CreateCommandSeparator@CSpellContextHandler@@AEAAJXZ; CSpellContextHandler::CreateCommandSeparator(void)
0x1802798f6  mov     ebx, eax
0x1802798f8  test    ebx, ebx
0x1802798fa  js      loc_180279A23
0x180279900  test    r14, r14
0x180279903  jz      loc_1802799E3
0x180279909  mov     eax, [rdi+54h]
0x18027990c  mov     r8d, esi; unsigned int
0x18027990f  mov     r9d, [rdi+64h]; unsigned int
0x180279913  mov     rdx, r14; HMENU
0x180279916  mov     rcx, rdi; this
0x180279919  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x18027991d  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x180279922  mov     bl, al
0x180279924  test    al, al
0x180279926  jz      loc_1802799D5
0x18027992c  inc     esi
0x18027992e  cmp     byte ptr [rdi+9Eh], 0
0x180279935  jnz     loc_1802799C3
0x18027993b  mov     eax, [rdi+58h]
0x18027993e  mov     r8d, esi; unsigned int
0x180279941  mov     r9d, [rdi+68h]; unsigned int
0x180279945  mov     rdx, r14; HMENU
0x180279948  mov     rcx, rdi; this
0x18027994b  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x18027994f  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x180279954  mov     bl, al
0x180279956  mov     [rbp+arg_10], 0
0x18027995a  mov     rax, [rdi+18h]
0x18027995e  lea     rdx, [rbp+arg_10]
0x180279962  inc     esi
0x180279964  mov     rcx, [rax+48h]
0x180279968  mov     rax, [rcx]
0x18027996b  mov     rax, [rax+100h]
0x180279972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180279977  test    al, al
0x180279979  jz      short loc_1802799BF
0x18027997b  cmp     [rbp+arg_10], 0
0x18027997f  mov     rcx, rdi; this
0x180279982  jz      short loc_18027999F
0x180279984  mov     eax, [rdi+5Ch]
0x180279987  mov     r8d, esi; unsigned int
0x18027998a  mov     r9d, [rdi+88h]; unsigned int
0x180279991  mov     rdx, r14; HMENU
0x180279994  mov     dword ptr [rsp+50h+var_30], eax; unsigned int
0x180279998  call    ?InsertMenuItemFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@III@Z; CSpellContextHandler::InsertMenuItemFromResource(HMENU__ *,uint,uint,uint)
0x18027999d  jmp     short loc_1802799BB
0x18027999f  call    ?CreateLanguageSubmenu@CSpellContextHandler@@AEAAPEAUHMENU__@@XZ; CSpellContextHandler::CreateLanguageSubmenu(void)
0x1802799a4  mov     r9d, [rdi+7Ch]; unsigned int
0x1802799a8  mov     r8d, esi; unsigned int
0x1802799ab  mov     rdx, r14; HMENU
0x1802799ae  mov     [rsp+50h+var_30], rax; HMENU
0x1802799b3  mov     rcx, rdi; this
0x1802799b6  call    ?InsertSubMenuFromResource@CSpellContextHandler@@AEAA_NPEAUHMENU__@@II0@Z; CSpellContextHandler::InsertSubMenuFromResource(HMENU__ *,uint,uint,HMENU__ *)
0x1802799bb  inc     esi
0x1802799bd  mov     bl, al
0x1802799bf  test    bl, bl
0x1802799c1  jz      short loc_1802799D5
0x1802799c3  cmp     [rbp+arg_18], 0
0x1802799c7  jz      short loc_1802799D5
0x1802799c9  mov     edx, esi; item
0x1802799cb  mov     rcx, r14; hmenu
0x1802799ce  call    ?InsertSeparator@CSpellContextHandler@@CA_NPEAUHMENU__@@I@Z; CSpellContextHandler::InsertSeparator(HMENU__ *,uint)
0x1802799d3  mov     bl, al
0x1802799d5  neg     bl
0x1802799d7  sbb     ebx, ebx
0x1802799d9  not     ebx
0x1802799db  and     ebx, 8000FFFFh
0x1802799e1  jmp     short loc_180279A23
0x1802799e3  cmp     qword ptr [rdi+90h], 0
0x1802799eb  jz      short loc_180279A1E
0x1802799ed  mov     r8d, [rdi+54h]; unsigned int
0x1802799f1  mov     rcx, rdi; this
0x1802799f4  mov     edx, [rdi+64h]; uID
0x1802799f7  call    ?CreateCommandFromResource@CSpellContextHandler@@AEAAJIH@Z; CSpellContextHandler::CreateCommandFromResource(uint,int)
0x1802799fc  mov     ebx, eax
0x1802799fe  test    eax, eax
0x180279a00  js      short loc_180279A23
0x180279a02  cmp     byte ptr [rdi+9Eh], 0
0x180279a09  jnz     short loc_180279A23
0x180279a0b  mov     r8d, [rdi+58h]; unsigned int
0x180279a0f  mov     rcx, rdi; this
0x180279a12  mov     edx, [rdi+68h]; uID
0x180279a15  call    ?CreateCommandFromResource@CSpellContextHandler@@AEAAJIH@Z; CSpellContextHandler::CreateCommandFromResource(uint,int)
0x180279a1a  mov     ebx, eax
0x180279a1c  jmp     short loc_180279A23
0x180279a1e  mov     ebx, 8000FFFFh
0x180279a23  mov     eax, ebx
0x180279a25  jmp     short loc_180279A2C
0x180279a27  mov     eax, 8000FFFFh
0x180279a2c  lea     r11, [rsp+50h+var_s0]
0x180279a31  mov     rbx, [r11+30h]
0x180279a35  mov     rsi, [r11+38h]
0x180279a39  mov     rsp, r11
0x180279a3c  pop     r14
0x180279a3e  pop     r13
0x180279a40  pop     r12
0x180279a42  pop     rdi
0x180279a43  pop     rbp
0x180279a44  retn
```
