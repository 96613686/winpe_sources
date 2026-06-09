# CRasGcwLUA::DeleteRASEntry(_RASNCWINFO * const)

- ea: `0x180012570`
- end: `0x18001260f`
- name: `?DeleteRASEntry@CRasGcwLUA@@UEAAJQEAU_RASNCWINFO@@@Z`
- size: `159`
- prototype: `signed int __fastcall(CRasGcwLUA *this, struct _RASNCWINFO *const)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012570`

## import_xrefs

- `RASAPI32!RasValidateEntryNameW` at `0x18001259d`
- `RASAPI32!RasValidateEntryNameW` at `0x18001259d`
- `RASAPI32!RasGetEntryHrasconnW` at `0x1800125be`
- `RASAPI32!RasGetEntryHrasconnW` at `0x1800125be`
- `RASAPI32!RasDeleteEntryW` at `0x1800125f2`
- `RASAPI32!RasDeleteEntryW` at `0x1800125f2`
- `RASAPI32!RasHangUpW` at `0x1800125d9`
- `RASAPI32!RasHangUpW` at `0x1800125d9`

## pseudocode

```c
signed int __fastcall CRasGcwLUA::DeleteRASEntry(CRasGcwLUA *this, struct _RASNCWINFO *const a2)
{
  unsigned __int64 v2; // rbx
  const WCHAR *v3; // rdi
  signed int result; // eax
  bool v5; // cc
  HRASCONN v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (unsigned __int64)a2 + 12;
  v6 = 0;
  v3 = (const WCHAR *)((char *)a2 + 1038);
  result = RasValidateEntryNameW(
             (LPCWSTR)(((unsigned __int64)a2 + 12) & -(__int64)(*((_WORD *)a2 + 6) != 0)),
             (LPCWSTR)a2 + 519);
  if ( result == 183 )
  {
    result = RasGetEntryHrasconnW(v2 & -(__int64)(*(_WORD *)v2 != 0), v3, &v6);
    if ( !result || result == 668 )
    {
      if ( v6 )
      {
        result = RasHangUpW(v6);
        v5 = result <= 0;
        if ( result )
          goto LABEL_8;
      }
      result = RasDeleteEntryW((LPCWSTR)(v2 & -(__int64)(*(_WORD *)v2 != 0)), v3);
    }
  }
  v5 = result <= 0;
LABEL_8:
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180012570  mov     [rsp+arg_0], rbx
0x180012575  push    rdi
0x180012576  sub     rsp, 20h
0x18001257a  lea     rbx, [rdx+0Ch]
0x18001257e  mov     [rsp+28h+arg_8], 0
0x180012587  movzx   eax, word ptr [rbx]
0x18001258a  lea     rdi, [rdx+40Eh]
0x180012591  neg     ax
0x180012594  mov     rdx, rdi; LPCWSTR
0x180012597  sbb     rcx, rcx
0x18001259a  and     rcx, rbx; LPCWSTR
0x18001259d  call    cs:__imp_RasValidateEntryNameW
0x1800125a3  cmp     eax, 0B7h
0x1800125a8  jnz     short loc_1800125F8
0x1800125aa  movzx   eax, word ptr [rbx]
0x1800125ad  lea     r8, [rsp+28h+arg_8]
0x1800125b2  neg     ax
0x1800125b5  mov     rdx, rdi
0x1800125b8  sbb     rcx, rcx
0x1800125bb  and     rcx, rbx
0x1800125be  call    cs:__imp_RasGetEntryHrasconnW
0x1800125c4  test    eax, eax
0x1800125c6  jz      short loc_1800125CF
0x1800125c8  cmp     eax, 29Ch
0x1800125cd  jnz     short loc_1800125F8
0x1800125cf  mov     rcx, [rsp+28h+arg_8]; HRASCONN
0x1800125d4  test    rcx, rcx
0x1800125d7  jz      short loc_1800125E3
0x1800125d9  call    cs:__imp_RasHangUpW
0x1800125df  test    eax, eax
0x1800125e1  jnz     short loc_1800125FA
0x1800125e3  movzx   eax, word ptr [rbx]
0x1800125e6  mov     rdx, rdi; LPCWSTR
0x1800125e9  neg     ax
0x1800125ec  sbb     rcx, rcx
0x1800125ef  and     rcx, rbx; LPCWSTR
0x1800125f2  call    cs:__imp_RasDeleteEntryW
0x1800125f8  test    eax, eax
0x1800125fa  jle     short loc_180012604
0x1800125fc  movzx   eax, ax
0x1800125ff  or      eax, 80070000h
0x180012604  mov     rbx, [rsp+28h+arg_0]
0x180012609  add     rsp, 20h
0x18001260d  pop     rdi
0x18001260e  retn
```
