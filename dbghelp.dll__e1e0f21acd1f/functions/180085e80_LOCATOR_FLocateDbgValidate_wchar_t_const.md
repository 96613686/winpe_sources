# LOCATOR::FLocateDbgValidate(wchar_t const *)

- ea: `0x180085e80`
- end: `0x180086178`
- name: `?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z`
- size: `760`
- prototype: `bool(LOCATOR *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180084420`
- `0x180085360`
- `0x1800859f0`

## callees

- `0x180085e80`
- `0x180087c50`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180086071`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180086071`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x180085eb0`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x180085eb0`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180086023`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18008616b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180086023`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18008616b`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180085eec`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180085fa3`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800860e3`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180085eec`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180085fa3`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800860e3`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180085f23`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18008609f`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180085f23`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18008609f`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x180085f54`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x180085f54`

## pseudocode

```c
char __fastcall LOCATOR::FLocateDbgValidate(LOCATOR *this, const wchar_t *a2)
{
  FILE *v4; // rax
  FILE *v5; // rsi
  int v7; // r14d
  unsigned __int64 v8; // rdi
  int v9; // ecx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned __int64 v12; // rdi
  __int64 (__fastcall *v13)(_QWORD, _QWORD); // rax
  __int64 v14; // rax
  void (__fastcall *v15)(_QWORD, _QWORD, _BYTE *); // rax
  _BYTE v16[10]; // [rsp+20h] [rbp-88h] BYREF
  __int16 v17; // [rsp+2Ah] [rbp-7Eh]
  int v18; // [rsp+2Ch] [rbp-7Ch]
  int v19; // [rsp+30h] [rbp-78h]
  int v20; // [rsp+38h] [rbp-70h]
  __int16 Buffer; // [rsp+40h] [rbp-68h] BYREF
  int v22; // [rsp+48h] [rbp-60h]
  int v23; // [rsp+58h] [rbp-50h]
  int v24; // [rsp+5Ch] [rbp-4Ch]
  unsigned int v25; // [rsp+60h] [rbp-48h]

  v4 = _wfsopen(a2, L"rb", 32);
  v5 = v4;
  if ( !v4 )
  {
    LOCATOR::NotifyOpenDBG(this, a2, 18, 0);
    return 0;
  }
  if ( fread(&Buffer, 0x30u, 1u, v4) != 1 || Buffer != 18756 || fseek(v5, v24 + 40 * v23, 1) )
  {
    LOCATOR::NotifyOpenDBG(this, a2, 11, 0);
    fclose(v5);
    return 0;
  }
  v7 = _o_ftell(v5);
  v8 = v25 / 0x1CuLL;
  if ( v8 )
  {
    while ( fread(v16, 0x1Cu, 1u, v5) == 1 )
    {
      --v8;
      if ( !*((_BYTE *)this + 3352) && v18 == 2 )
      {
        *((_DWORD *)this + 839) = v19;
        *((_DWORD *)this + 841) = v20;
        *((_WORD *)this + 1684) = v17;
        *((_DWORD *)this + 840) = 0;
      }
      if ( !v8 )
        goto LABEL_12;
    }
    v10 = 11;
    goto LABEL_16;
  }
LABEL_12:
  if ( v22 != *((_DWORD *)this + 830) )
  {
    v9 = *((_DWORD *)this + 831);
    if ( !v9 || v22 != v9 )
    {
      v10 = 20;
LABEL_16:
      LOCATOR::NotifyOpenDBG(this, a2, v10, 0);
      fclose(v5);
      return 0;
    }
  }
  v11 = _o__wcsdup(a2);
  *((_QWORD *)this + 417) = v5;
  *((_QWORD *)this + 418) = v11;
  LOCATOR::NotifyOpenDBG(this, a2, 0, 0);
  if ( !fseek(v5, v7, 0) )
  {
    v12 = v25 / 0x1CuLL;
    while ( v12 )
    {
      if ( fread(v16, 0x1Cu, 1u, v5) != 1 )
        break;
      --v12;
      if ( !*((_BYTE *)this + 2072) )
      {
        *((_BYTE *)this + 2072) = 1;
        v13 = (__int64 (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 258);
        if ( v13 )
          v14 = v13(*((_QWORD *)this + 257), 0);
        else
          v14 = 0;
        *((_QWORD *)this + 260) = v14;
      }
      v15 = (void (__fastcall *)(_QWORD, _QWORD, _BYTE *))*((_QWORD *)this + 260);
      if ( v15 )
        v15(*((_QWORD *)this + 257), 0, v16);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180085e80  push    rbx
0x180085e82  push    rbp
0x180085e83  push    rsi
0x180085e84  sub     rsp, 90h
0x180085e8b  mov     rax, cs:__security_cookie
0x180085e92  xor     rax, rsp
0x180085e95  mov     [rsp+0A8h+var_38], rax
0x180085e9a  mov     rbp, rdx
0x180085e9d  mov     rbx, rcx
0x180085ea0  mov     rcx, rbp; FileName
0x180085ea3  lea     rdx, aRb; "rb"
0x180085eaa  mov     r8d, 20h ; ' '; ShFlag
0x180085eb0  call    cs:__imp__wfsopen
0x180085eb6  mov     rsi, rax
0x180085eb9  test    rax, rax
0x180085ebc  jnz     short loc_180085ED9
0x180085ebe  xor     r9d, r9d
0x180085ec1  mov     r8d, 12h
0x180085ec7  mov     rdx, rbp
0x180085eca  mov     rcx, rbx
0x180085ecd  call    ?NotifyOpenDBG@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenDBG(wchar_t const *,PDBErrors,wchar_t const *)
0x180085ed2  xor     al, al
0x180085ed4  jmp     loc_18008604B
0x180085ed9  mov     r9, rsi; Stream
0x180085edc  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x180085ee1  mov     edx, 30h ; '0'; ElementSize
0x180085ee6  mov     r8d, 1; ElementCount
0x180085eec  call    cs:__imp_fread
0x180085ef2  cmp     rax, 1
0x180085ef6  jnz     loc_180086154
0x180085efc  mov     eax, 4944h
0x180085f01  cmp     [rsp+0A8h+Buffer], ax
0x180085f06  jnz     loc_180086154
0x180085f0c  mov     eax, [rsp+0A8h+var_50]
0x180085f10  mov     r8d, 1; Origin
0x180085f16  lea     ecx, [rax+rax*4]
0x180085f19  mov     eax, [rsp+0A8h+var_4C]
0x180085f1d  lea     edx, [rax+rcx*8]; Offset
0x180085f20  mov     rcx, rsi; Stream
0x180085f23  call    cs:__imp_fseek
0x180085f29  test    eax, eax
0x180085f2b  jnz     loc_180086154
0x180085f31  mov     [rsp+0A8h+arg_10], rdi
0x180085f39  mov     rcx, rsi
0x180085f3c  mov     [rsp+0A8h+arg_18], r12
0x180085f44  mov     [rsp+0A8h+var_20], r14
0x180085f4c  mov     [rsp+0A8h+var_28], r15
0x180085f54  call    cs:__imp__o_ftell
0x180085f5a  mov     edi, [rsp+0A8h+var_48]
0x180085f5e  mov     r12, 2492492492492493h
0x180085f68  mov     r14d, eax
0x180085f6b  xor     r15d, r15d
0x180085f6e  mov     rax, r12
0x180085f71  mul     rdi
0x180085f74  sub     rdi, rdx
0x180085f77  shr     rdi, 1
0x180085f7a  add     rdi, rdx
0x180085f7d  shr     rdi, 4
0x180085f81  test    rdi, rdi
0x180085f84  jz      short loc_180085FF2
0x180085f86  nop     word ptr [rax+rax+00000000h]
0x180085f90  mov     r9, rsi; Stream
0x180085f93  lea     rcx, [rsp+0A8h+var_88]; Buffer
0x180085f98  mov     edx, 1Ch; ElementSize
0x180085f9d  mov     r8d, 1; ElementCount
0x180085fa3  call    cs:__imp_fread
0x180085fa9  cmp     rax, 1
0x180085fad  jnz     loc_180086063
0x180085fb3  dec     rdi
0x180085fb6  cmp     [rbx+0D18h], r15b
0x180085fbd  jnz     short loc_180085FED
0x180085fbf  cmp     [rsp+0A8h+var_7C], 2
0x180085fc4  jnz     short loc_180085FED
0x180085fc6  mov     eax, [rsp+0A8h+var_78]
0x180085fca  mov     [rbx+0D1Ch], eax
0x180085fd0  mov     eax, [rsp+0A8h+var_70]
0x180085fd4  mov     [rbx+0D24h], eax
0x180085fda  movzx   eax, [rsp+0A8h+var_7E]
0x180085fdf  mov     [rbx+0D28h], ax
0x180085fe6  mov     [rbx+0D20h], r15d
0x180085fed  test    rdi, rdi
0x180085ff0  jnz     short loc_180085F90
0x180085ff2  mov     eax, [rsp+0A8h+var_60]
0x180085ff6  cmp     eax, [rbx+0CF8h]
0x180085ffc  jz      short loc_18008606E
0x180085ffe  mov     ecx, [rbx+0CFCh]
0x180086004  test    ecx, ecx
0x180086006  jz      short loc_18008600C
0x180086008  cmp     eax, ecx
0x18008600a  jz      short loc_18008606E
0x18008600c  xor     r9d, r9d
0x18008600f  mov     r8d, 14h
0x180086015  mov     rdx, rbp
0x180086018  mov     rcx, rbx
0x18008601b  call    ?NotifyOpenDBG@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenDBG(wchar_t const *,PDBErrors,wchar_t const *)
0x180086020  mov     rcx, rsi; Stream
0x180086023  call    cs:__imp_fclose
0x180086029  xor     al, al
0x18008602b  mov     r14, [rsp+0A8h+var_20]
0x180086033  mov     r12, [rsp+0A8h+arg_18]
0x18008603b  mov     rdi, [rsp+0A8h+arg_10]
0x180086043  mov     r15, [rsp+0A8h+var_28]
0x18008604b  mov     rcx, [rsp+0A8h+var_38]
0x180086050  xor     rcx, rsp; StackCookie
0x180086053  call    __security_check_cookie
0x180086058  add     rsp, 90h
0x18008605f  pop     rsi
0x180086060  pop     rbp
0x180086061  pop     rbx
0x180086062  retn
0x180086063  xor     r9d, r9d
0x180086066  mov     r8d, 0Bh
0x18008606c  jmp     short loc_180086015
0x18008606e  mov     rcx, rbp
0x180086071  call    cs:__imp__o__wcsdup
0x180086077  xor     r9d, r9d
0x18008607a  mov     [rbx+0D08h], rsi
0x180086081  xor     r8d, r8d
0x180086084  mov     [rbx+0D10h], rax
0x18008608b  mov     rdx, rbp
0x18008608e  mov     rcx, rbx
0x180086091  call    ?NotifyOpenDBG@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenDBG(wchar_t const *,PDBErrors,wchar_t const *)
0x180086096  xor     r8d, r8d; Origin
0x180086099  mov     edx, r14d; Offset
0x18008609c  mov     rcx, rsi; Stream
0x18008609f  call    cs:__imp_fseek
0x1800860a5  test    eax, eax
0x1800860a7  jnz     loc_18008614D
0x1800860ad  mov     edi, [rsp+0A8h+var_48]
0x1800860b1  mov     rax, r12
0x1800860b4  mul     rdi
0x1800860b7  sub     rdi, rdx
0x1800860ba  shr     rdi, 1
0x1800860bd  add     rdi, rdx
0x1800860c0  shr     rdi, 4
0x1800860c4  test    rdi, rdi
0x1800860c7  jz      loc_18008614D
0x1800860cd  nop     dword ptr [rax]
0x1800860d0  mov     r9, rsi; Stream
0x1800860d3  lea     rcx, [rsp+0A8h+var_88]; Buffer
0x1800860d8  mov     edx, 1Ch; ElementSize
0x1800860dd  mov     r8d, 1; ElementCount
0x1800860e3  call    cs:__imp_fread
0x1800860e9  cmp     rax, 1
0x1800860ed  jnz     short loc_18008614D
0x1800860ef  dec     rdi
0x1800860f2  cmp     [rbx+818h], r15b
0x1800860f9  jnz     short loc_180086128
0x1800860fb  mov     [rbx+818h], al
0x180086101  mov     rax, [rbx+810h]
0x180086108  test    rax, rax
0x18008610b  jnz     short loc_180086112
0x18008610d  mov     rax, r15
0x180086110  jmp     short loc_180086121
0x180086112  mov     rcx, [rbx+808h]
0x180086119  xor     edx, edx
0x18008611b  call    cs:__guard_dispatch_icall_fptr
0x180086121  mov     [rbx+820h], rax
0x180086128  mov     rax, [rbx+820h]
0x18008612f  test    rax, rax
0x180086132  jz      short loc_180086148
0x180086134  mov     rcx, [rbx+808h]
0x18008613b  lea     r8, [rsp+0A8h+var_88]
0x180086140  xor     edx, edx
0x180086142  call    cs:__guard_dispatch_icall_fptr
0x180086148  test    rdi, rdi
0x18008614b  jnz     short loc_1800860D0
0x18008614d  mov     al, 1
0x18008614f  jmp     loc_18008602B
0x180086154  xor     r9d, r9d
0x180086157  mov     r8d, 0Bh
0x18008615d  mov     rdx, rbp
0x180086160  mov     rcx, rbx
0x180086163  call    ?NotifyOpenDBG@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenDBG(wchar_t const *,PDBErrors,wchar_t const *)
0x180086168  mov     rcx, rsi; Stream
0x18008616b  call    cs:__imp_fclose
0x180086171  xor     al, al
0x180086173  jmp     loc_18008604B
```
