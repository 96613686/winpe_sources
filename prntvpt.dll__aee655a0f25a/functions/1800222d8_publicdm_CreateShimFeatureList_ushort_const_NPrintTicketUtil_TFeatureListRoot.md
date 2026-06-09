# publicdm::CreateShimFeatureList(ushort const *,NPrintTicketUtil::TFeatureListRoot * *)

- ea: `0x1800222d8`
- end: `0x18002245a`
- name: `?CreateShimFeatureList@publicdm@@YAJPEBGPEAPEAUTFeatureListRoot@NPrintTicketUtil@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(OLECHAR *psz, unsigned __int16 *, struct NPrintTicketUtil::TFeatureListRoot **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008498`

## callees

- `0x180005aa4`
- `0x1800060fc`
- `0x18000fd6c`
- `0x1800221c4`
- `0x1800222d8`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800223d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800223e5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800223d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800223e5`

## pseudocode

```c
__int64 __fastcall publicdm::CreateShimFeatureList(
        OLECHAR *psz,
        unsigned __int16 *a2,
        struct NPrintTicketUtil::TFeatureListRoot **a3)
{
  struct NPrintTicketUtil::TFeatureListEntry **v5; // rax
  struct NPrintTicketUtil::TFeatureListEntry **v6; // rsi
  int FeatureListEntriesFromStringList; // edi
  _QWORD *v8; // rbx
  BSTR v9; // rax
  BSTR v10; // rax
  struct NPrintTicketUtil::TFeatureListEntry **v12; // [rsp+50h] [rbp+18h] BYREF

  v5 = (struct NPrintTicketUtil::TFeatureListEntry **)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
  }
  else
  {
    v6 = 0;
  }
  v12 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(&v12);
  v12 = v6;
  if ( !v6 )
  {
    FeatureListEntriesFromStringList = -2147024882;
    goto LABEL_16;
  }
  FeatureListEntriesFromStringList = CreateFeatureListEntriesFromStringList(
                                       (const unsigned __int16 **)&off_180031600,
                                       v6);
  if ( FeatureListEntriesFromStringList >= 0 )
  {
    FeatureListEntriesFromStringList = CreateFeatureListEntriesFromStringList(
                                         (const unsigned __int16 **)&off_180031670,
                                         v6 + 1);
    if ( FeatureListEntriesFromStringList >= 0 )
    {
      v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v8 )
      {
        v8[1] = 0;
        *v8 = &NPrintTicketUtil::TFeatureListEntry::`vftable';
        v8[2] = 0;
        v8[3] = 0;
        v8[4] = 0;
        *((_DWORD *)v8 + 10) = 0;
        v8[6] = 0;
        v9 = SysAllocString(L"PageDevmodeSnapshot");
        v8[3] = v9;
        if ( v9 )
        {
          v10 = SysAllocString(psz);
          v8[2] = v10;
          if ( v10 )
          {
            FeatureListEntriesFromStringList = NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix((NPrintTicketUtil::TFeatureListEntry *)v8);
            if ( FeatureListEntriesFromStringList >= 0 )
            {
              v8[1] = v6[1];
              v6[1] = (struct NPrintTicketUtil::TFeatureListEntry *)v8;
              *(_QWORD *)a2 = v6;
              v12 = 0;
              goto LABEL_16;
            }
LABEL_15:
            (*(void (__fastcall **)(_QWORD *, __int64))*v8)(v8, 1);
            goto LABEL_16;
          }
        }
      }
      else
      {
        v8 = 0;
      }
      FeatureListEntriesFromStringList = -2147024882;
      if ( !v8 )
        goto LABEL_16;
      goto LABEL_15;
    }
  }
LABEL_16:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(&v12);
  return (unsigned int)FeatureListEntriesFromStringList;
}

```

## disassembly

```asm
0x1800222d8  mov     [rsp+arg_0], rbx
0x1800222dd  mov     [rsp+arg_8], rbp
0x1800222e2  push    rsi
0x1800222e3  push    rdi
0x1800222e4  push    r14
0x1800222e6  sub     rsp, 20h
0x1800222ea  mov     r14, rdx
0x1800222ed  mov     rbp, rcx
0x1800222f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800222f7  mov     ecx, 10h; unsigned __int64
0x1800222fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022301  mov     rsi, rax
0x180022304  test    rax, rax
0x180022307  jz      short loc_18002231A
0x180022309  mov     qword ptr [rax], 0
0x180022310  mov     qword ptr [rax+8], 0
0x180022318  jmp     short loc_18002231C
0x18002231a  xor     esi, esi
0x18002231c  lea     rcx, [rsp+38h+arg_10]
0x180022321  mov     [rsp+38h+arg_10], 0
0x18002232a  call    ?Reset@?$TGenericSP@UTFeatureListRoot@NPrintTicketUtil@@VTAutoPtrFeatureList@2@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(void)
0x18002232f  mov     [rsp+38h+arg_10], rsi
0x180022334  test    rsi, rsi
0x180022337  jnz     short loc_180022343
0x180022339  mov     edi, 8007000Eh
0x18002233e  jmp     loc_18002243B
0x180022343  mov     rdx, rsi; struct NPrintTicketUtil::TFeatureListEntry **
0x180022346  lea     rcx, off_180031600; unsigned __int16 **
0x18002234d  call    ?CreateFeatureListEntriesFromStringList@@YAJPEAPEBGPEAPEAVTFeatureListEntry@NPrintTicketUtil@@@Z; CreateFeatureListEntriesFromStringList(ushort const * *,NPrintTicketUtil::TFeatureListEntry * *)
0x180022352  mov     edi, eax
0x180022354  test    eax, eax
0x180022356  js      loc_18002243B
0x18002235c  lea     rdx, [rsi+8]; struct NPrintTicketUtil::TFeatureListEntry **
0x180022360  lea     rcx, off_180031670; unsigned __int16 **
0x180022367  call    ?CreateFeatureListEntriesFromStringList@@YAJPEAPEBGPEAPEAVTFeatureListEntry@NPrintTicketUtil@@@Z; CreateFeatureListEntriesFromStringList(ushort const * *,NPrintTicketUtil::TFeatureListEntry * *)
0x18002236c  mov     edi, eax
0x18002236e  test    eax, eax
0x180022370  js      loc_18002243B
0x180022376  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002237d  mov     ecx, 38h ; '8'; unsigned __int64
0x180022382  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022387  mov     rbx, rax
0x18002238a  test    rax, rax
0x18002238d  jz      loc_18002241C
0x180022393  lea     rax, ??_7TFeatureListEntry@NPrintTicketUtil@@6B@; const NPrintTicketUtil::TFeatureListEntry::`vftable'
0x18002239a  mov     qword ptr [rbx+8], 0
0x1800223a2  lea     rcx, aPagedevmodesna_0; "PageDevmodeSnapshot"
0x1800223a9  mov     [rbx], rax
0x1800223ac  mov     qword ptr [rbx+10h], 0
0x1800223b4  mov     qword ptr [rbx+18h], 0
0x1800223bc  mov     qword ptr [rbx+20h], 0
0x1800223c4  mov     dword ptr [rbx+28h], 0
0x1800223cb  mov     qword ptr [rbx+30h], 0
0x1800223d3  call    cs:__imp_SysAllocString
0x1800223d9  mov     [rbx+18h], rax
0x1800223dd  test    rax, rax
0x1800223e0  jz      short loc_18002241E
0x1800223e2  mov     rcx, rbp; psz
0x1800223e5  call    cs:__imp_SysAllocString
0x1800223eb  mov     [rbx+10h], rax
0x1800223ef  test    rax, rax
0x1800223f2  jz      short loc_18002241E
0x1800223f4  mov     rcx, rbx; this
0x1800223f7  call    ?ConfigureScopePrefix@TFeatureListEntry@NPrintTicketUtil@@QEAAJXZ; NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix(void)
0x1800223fc  mov     edi, eax
0x1800223fe  test    eax, eax
0x180022400  js      short loc_180022428
0x180022402  mov     rax, [rsi+8]
0x180022406  mov     [rbx+8], rax
0x18002240a  mov     [rsi+8], rbx
0x18002240e  mov     [r14], rsi
0x180022411  mov     [rsp+38h+arg_10], 0
0x18002241a  jmp     short loc_18002243B
0x18002241c  xor     ebx, ebx
0x18002241e  mov     edi, 8007000Eh
0x180022423  test    rbx, rbx
0x180022426  jz      short loc_18002243B
0x180022428  mov     rax, [rbx]
0x18002242b  mov     edx, 1
0x180022430  mov     rcx, rbx
0x180022433  mov     rax, [rax]
0x180022436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002243b  lea     rcx, [rsp+38h+arg_10]
0x180022440  call    ?Reset@?$TGenericSP@UTFeatureListRoot@NPrintTicketUtil@@VTAutoPtrFeatureList@2@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::TFeatureListRoot,NPrintTicketUtil::TAutoPtrFeatureList,NPrintTicketUtil::TFeatureListRoot *,0,NPrintTicketUtil::TFeatureListRoot const *>::Reset(void)
0x180022445  mov     rbx, [rsp+38h+arg_0]
0x18002244a  mov     eax, edi
0x18002244c  mov     rbp, [rsp+38h+arg_8]
0x180022451  add     rsp, 20h
0x180022455  pop     r14
0x180022457  pop     rdi
0x180022458  pop     rsi
0x180022459  retn
```
