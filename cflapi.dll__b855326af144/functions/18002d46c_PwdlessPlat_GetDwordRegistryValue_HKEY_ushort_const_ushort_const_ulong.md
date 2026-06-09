# PwdlessPlat::GetDwordRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18002d46c`
- end: `0x18002d506`
- name: `?GetDwordRegistryValue@PwdlessPlat@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `154`
- prototype: `__int64 __fastcall(PwdlessPlat *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d50c`

## callees

- `0x1800067c4`
- `0x18002d46c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d4b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d4b4`

## string_xrefs

- `0x18002d4db`: `onecore\ds\security\pwdless\customization\lib\pwdlessplatimagecustomizations.cpp`

## pseudocode

```c
__int64 __fastcall PwdlessPlat::GetDwordRegistryValue(
        PwdlessPlat *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  LSTATUS ValueW; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-38h]
  DWORD v9[6]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v11; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+64h] [rbp+Ch]

  v12 = HIDWORD(this);
  v11 = 0;
  v9[0] = 4;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 0x10u, 0, &v11, v9);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
    *(_DWORD *)a4 = v11;
    return 0;
  }
  else
  {
    result = 2147942402LL;
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF,
        (unsigned int)"onecore\\ds\\security\\pwdless\\customization\\lib\\pwdlessplatimagecustomizations.cpp",
        (const char *)v6,
        v8);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d46c  mov     r11, rsp
0x18002d46f  mov     [r11+10h], rbx
0x18002d473  mov     [r11+8], rcx
0x18002d477  push    rdi
0x18002d478  sub     rsp, 50h
0x18002d47c  lea     rax, [r11-18h]
0x18002d480  mov     [rsp+58h+arg_0], 0
0x18002d488  mov     [r11-28h], rax
0x18002d48c  mov     rdi, r9
0x18002d48f  lea     rax, [r11+8]
0x18002d493  mov     [rsp+58h+var_18], 4
0x18002d49b  mov     [r11-30h], rax
0x18002d49f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002d4a6  mov     r9d, 10h; dwFlags
0x18002d4ac  mov     qword ptr [r11-38h], 0
0x18002d4b4  call    cs:__imp_RegGetValueW
0x18002d4ba  mov     ebx, eax
0x18002d4bc  test    eax, eax
0x18002d4be  jle     short loc_18002D4C9
0x18002d4c0  movzx   ebx, ax
0x18002d4c3  or      ebx, 80070000h
0x18002d4c9  test    ebx, ebx
0x18002d4cb  jns     short loc_18002D4F3
0x18002d4cd  mov     eax, 80070002h
0x18002d4d2  cmp     ebx, eax
0x18002d4d4  jz      short loc_18002D4FB
0x18002d4d6  mov     rcx, [rsp+58h]; this
0x18002d4db  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\pwdless\\customi"...
0x18002d4e2  mov     r9d, ebx; char *
0x18002d4e5  mov     edx, 0Fh; void *
0x18002d4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d4ef  mov     eax, ebx
0x18002d4f1  jmp     short loc_18002D4FB
0x18002d4f3  mov     eax, [rsp+58h+arg_0]
0x18002d4f7  mov     [rdi], eax
0x18002d4f9  xor     eax, eax
0x18002d4fb  mov     rbx, [rsp+58h+arg_8]
0x18002d500  add     rsp, 50h
0x18002d504  pop     rdi
0x18002d505  retn
```
