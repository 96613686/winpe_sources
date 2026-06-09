# CSimpleTableDispenser::GetTable(ushort const *,ushort const *,void *,void *,ulong,ulong,void * *)

- ea: `0x180003ad0`
- end: `0x180003dfb`
- name: `?GetTable@CSimpleTableDispenser@@UEAAJPEBG0PEAX1KKPEAPEAX@Z`
- size: `811`
- prototype: `__int64 __fastcall(CSimpleTableDispenser *this, const unsigned __int16 *, wchar_t *, _DWORD *, unsigned int *, unsigned int, unsigned int, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003ad0`
- `0x180003e04`
- `0x180003fd0`
- `0x180029ab4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003b86`
- `msvcrt!_wcsicmp` at `0x180003bf6`
- `msvcrt!_wcsicmp` at `0x180003c10`
- `msvcrt!_wcsicmp` at `0x180003c53`
- `msvcrt!_wcsicmp` at `0x180003c8c`
- `msvcrt!_wcsicmp` at `0x180003ce7`
- `msvcrt!_wcsicmp` at `0x180003cfb`
- `msvcrt!_wcsicmp` at `0x180003d66`
- `msvcrt!_wcsicmp` at `0x180003b86`
- `msvcrt!_wcsicmp` at `0x180003bf6`
- `msvcrt!_wcsicmp` at `0x180003c10`
- `msvcrt!_wcsicmp` at `0x180003c53`
- `msvcrt!_wcsicmp` at `0x180003c8c`
- `msvcrt!_wcsicmp` at `0x180003ce7`
- `msvcrt!_wcsicmp` at `0x180003cfb`
- `msvcrt!_wcsicmp` at `0x180003d66`
- `IisRTL!PuDbgPrint` at `0x180003b3b`
- `IisRTL!PuDbgPrint` at `0x180003b3b`

## string_xrefs

- `0x180003b34`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`

## pseudocode

```c
__int64 __fastcall CSimpleTableDispenser::GetTable(
        CSimpleTableDispenser *this,
        const unsigned __int16 *a2,
        wchar_t *a3,
        _DWORD *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int a7,
        void **a8)
{
  void **v12; // rdi
  __int64 result; // rax
  unsigned int v14; // r14d
  unsigned int *v15; // rbp
  const wchar_t *v16; // r9
  const wchar_t *v17; // r8
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-78h]
  _DWORD *v20; // [rsp+28h] [rbp-70h]
  unsigned int *v21; // [rsp+30h] [rbp-68h]
  unsigned int v22; // [rsp+A8h] [rbp+10h] BYREF

  v22 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v12 = a8;
  if ( !a8 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
        117,
        "CSimpleTableDispenser::GetTable",
        "Bad out parameter");
    return 2147942487LL;
  }
  v14 = a6;
  *a8 = 0;
  if ( v14 - 1 <= 1 || v14 >= 5 )
    return 2149648396LL;
  if ( _wcsicmp(a2, L"META") )
  {
    if ( _wcsicmp(a2, L"PACKEDSCHEMA") )
    {
      result = TFixedPackedSchemaInterceptor::GetTableID(a3, &v22);
      if ( (int)result >= 0 )
        return CSimpleTableDispenser::InternalGetTable(this, a2, a3, v22, a4, a5, v14, a7, v12);
      return result;
    }
    v17 = a2;
    v21 = a5;
    v20 = a4;
    goto LABEL_33;
  }
  if ( (a7 & 0x200000) != 0 )
    return 2149648397LL;
  v15 = a5;
  if ( !a5 || !*a5 )
  {
    if ( _wcsicmp(a3, L"SERVERWIRINGMETA") && _wcsicmp(a3, L"SERVERWIRING_META") )
    {
      v21 = 0;
      v20 = 0;
      goto LABEL_31;
    }
    v17 = L"META";
    v21 = 0;
    v20 = 0;
LABEL_33:
    v16 = a3;
    v19 = 0;
    goto LABEL_34;
  }
  if ( a4 && ((a4[3] & 0xF0000000) != 0 || !_wcsicmp(a3, L"TABLEMETA") && !a4[3]) )
  {
    v21 = v15;
    v20 = a4;
LABEL_31:
    v19 = 0;
    v16 = a3;
    v17 = L"META";
    v18 = 2;
    return CSimpleTableDispenser::HardCodedIntercept(this, v18, v17, v16, v19, v20, v21);
  }
  if ( !_wcsicmp(a3, L"COLUMNMETA") )
  {
    v16 = L"PROPERTY_META";
    v21 = v15;
    v20 = a4;
    v19 = -514174464;
LABEL_22:
    v17 = L"PACKEDSCHEMA";
LABEL_34:
    v18 = 10;
    return CSimpleTableDispenser::HardCodedIntercept(this, v18, v17, v16, v19, v20, v21);
  }
  if ( !_wcsicmp(a3, L"TABLEMETA") )
  {
    v16 = L"COLLECTION_META";
    v21 = v15;
    v20 = a4;
    v19 = 710941440;
    goto LABEL_22;
  }
  if ( _wcsicmp(a3, L"TAGMETA") )
    return CSimpleTableDispenser::HardCodedIntercept(this, 2, L"META", a3, 0, a4, v15);
  else
    return CSimpleTableDispenser::HardCodedIntercept(this, 10, L"PACKEDSCHEMA", L"TAG_META", -850017536, a4, v15);
}

```

## disassembly

```asm
0x180003ad0  mov     r11, rsp
0x180003ad3  push    rbx
0x180003ad4  push    rbp
0x180003ad5  push    rsi
0x180003ad6  push    rdi
0x180003ad7  push    r12
0x180003ad9  push    r13
0x180003adb  push    r14
0x180003add  push    r15
0x180003adf  sub     rsp, 58h
0x180003ae3  xor     r12d, r12d
0x180003ae6  mov     rsi, r9
0x180003ae9  mov     [r11+10h], r12d
0x180003aed  mov     rbx, r8
0x180003af0  mov     rbp, rdx
0x180003af3  mov     r15, rcx
0x180003af6  test    rdx, rdx
0x180003af9  jz      short loc_180003B41
0x180003afb  test    rbx, rbx
0x180003afe  jz      short loc_180003B41
0x180003b00  mov     rdi, [rsp+98h+arg_38]
0x180003b08  test    rdi, rdi
0x180003b0b  jnz     short loc_180003B57
0x180003b0d  test    byte ptr cs:g_dwDebugFlags, 3
0x180003b14  jz      short loc_180003B41
0x180003b16  mov     rcx, cs:g_pDebug
0x180003b1d  lea     rax, aBadOutParamete; "Bad out parameter"
0x180003b24  lea     r9, aCsimpletabledi_1; "CSimpleTableDispenser::GetTable"
0x180003b2b  mov     [r11-78h], rax
0x180003b2f  lea     r8d, [r12+75h]
0x180003b34  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x180003b3b  call    cs:__imp_PuDbgPrint
0x180003b41  mov     eax, 80070057h
0x180003b46  add     rsp, 58h
0x180003b4a  pop     r15
0x180003b4c  pop     r14
0x180003b4e  pop     r13
0x180003b50  pop     r12
0x180003b52  pop     rdi
0x180003b53  pop     rsi
0x180003b54  pop     rbp
0x180003b55  pop     rbx
0x180003b56  retn
0x180003b57  mov     r14d, [rsp+98h+arg_28]
0x180003b5f  mov     [rdi], r12
0x180003b62  lea     eax, [r14-1]
0x180003b66  cmp     eax, 1
0x180003b69  jbe     loc_180003DF1
0x180003b6f  cmp     r14d, 5
0x180003b73  jnb     loc_180003DF1
0x180003b79  lea     r13, aMeta; "META"
0x180003b80  mov     rcx, rbp; String1
0x180003b83  mov     rdx, r13; String2
0x180003b86  call    cs:__imp__wcsicmp
0x180003b8c  test    eax, eax
0x180003b8e  jnz     loc_180003D5C
0x180003b94  mov     r14d, [rsp+98h+arg_30]
0x180003b9c  bt      r14d, 15h
0x180003ba1  jnb     short loc_180003BAA
0x180003ba3  mov     eax, 8021080Dh
0x180003ba8  jmp     short loc_180003B46
0x180003baa  mov     rbp, [rsp+98h+arg_20]
0x180003bb2  test    rbp, rbp
0x180003bb5  jz      loc_180003CDD
0x180003bbb  cmp     [rbp+0], r12d
0x180003bbf  jz      loc_180003CDD
0x180003bc5  test    rsi, rsi
0x180003bc8  jz      short loc_180003C06
0x180003bca  test    dword ptr [rsi+0Ch], 0F0000000h
0x180003bd1  jz      short loc_180003BEC
0x180003bd3  mov     [rsp+98h+var_50], rdi
0x180003bd8  mov     dword ptr [rsp+98h+var_58], r14d
0x180003bdd  mov     qword ptr [rsp+98h+var_68], rbp
0x180003be2  mov     [rsp+98h+var_70], rsi
0x180003be7  jmp     loc_180003D19
0x180003bec  lea     rdx, aTablemeta; "TABLEMETA"
0x180003bf3  mov     rcx, rbx; String1
0x180003bf6  call    cs:__imp__wcsicmp
0x180003bfc  test    eax, eax
0x180003bfe  jnz     short loc_180003C06
0x180003c00  cmp     [rsi+0Ch], r12d
0x180003c04  jz      short loc_180003BD3
0x180003c06  lea     rdx, aColumnmeta; "COLUMNMETA"
0x180003c0d  mov     rcx, rbx; String1
0x180003c10  call    cs:__imp__wcsicmp
0x180003c16  test    eax, eax
0x180003c18  jnz     short loc_180003C49
0x180003c1a  mov     [rsp+98h+var_50], rdi
0x180003c1f  lea     r9, aPropertyMeta; "PROPERTY_META"
0x180003c26  mov     dword ptr [rsp+98h+var_58], r14d
0x180003c2b  mov     qword ptr [rsp+98h+var_68], rbp
0x180003c30  mov     [rsp+98h+var_70], rsi
0x180003c35  mov     dword ptr [rsp+98h+var_78], 0E15A5200h
0x180003c3d  lea     r8, aPackedschema; "PACKEDSCHEMA"
0x180003c44  jmp     loc_180003D4A
0x180003c49  lea     rdx, aTablemeta; "TABLEMETA"
0x180003c50  mov     rcx, rbx; String1
0x180003c53  call    cs:__imp__wcsicmp
0x180003c59  test    eax, eax
0x180003c5b  jnz     short loc_180003C82
0x180003c5d  mov     [rsp+98h+var_50], rdi
0x180003c62  lea     r9, aCollectionMeta; "COLLECTION_META"
0x180003c69  mov     dword ptr [rsp+98h+var_58], r14d
0x180003c6e  mov     qword ptr [rsp+98h+var_68], rbp
0x180003c73  mov     [rsp+98h+var_70], rsi
0x180003c78  mov     dword ptr [rsp+98h+var_78], 2A601B00h
0x180003c80  jmp     short loc_180003C3D
0x180003c82  lea     rdx, aTagmeta; "TAGMETA"
0x180003c89  mov     rcx, rbx; String1
0x180003c8c  call    cs:__imp__wcsicmp
0x180003c92  mov     [rsp+98h+var_50], rdi
0x180003c97  mov     rcx, r15
0x180003c9a  mov     dword ptr [rsp+98h+var_58], r14d
0x180003c9f  mov     qword ptr [rsp+98h+var_68], rbp
0x180003ca4  mov     [rsp+98h+var_70], rsi
0x180003ca9  test    eax, eax
0x180003cab  jnz     short loc_180003CCB
0x180003cad  mov     dword ptr [rsp+98h+var_78], 0CD55C300h
0x180003cb5  lea     r9, aTagMeta; "TAG_META"
0x180003cbc  lea     r8, aPackedschema; "PACKEDSCHEMA"
0x180003cc3  lea     edx, [rax+0Ah]
0x180003cc6  jmp     loc_180003D52
0x180003ccb  mov     dword ptr [rsp+98h+var_78], r12d
0x180003cd0  mov     r9, rbx
0x180003cd3  mov     r8, r13
0x180003cd6  mov     edx, 2
0x180003cdb  jmp     short loc_180003D52
0x180003cdd  lea     rdx, aServerwiringme; "SERVERWIRINGMETA"
0x180003ce4  mov     rcx, rbx; String1
0x180003ce7  call    cs:__imp__wcsicmp
0x180003ced  test    eax, eax
0x180003cef  jz      short loc_180003D2B
0x180003cf1  lea     rdx, aServerwiringMe; "SERVERWIRING_META"
0x180003cf8  mov     rcx, rbx; String1
0x180003cfb  call    cs:__imp__wcsicmp
0x180003d01  test    eax, eax
0x180003d03  jz      short loc_180003D2B
0x180003d05  mov     [rsp+98h+var_50], rdi
0x180003d0a  mov     dword ptr [rsp+98h+var_58], r14d
0x180003d0f  mov     qword ptr [rsp+98h+var_68], r12
0x180003d14  mov     [rsp+98h+var_70], r12
0x180003d19  mov     dword ptr [rsp+98h+var_78], r12d
0x180003d1e  mov     r9, rbx
0x180003d21  mov     r8, r13
0x180003d24  mov     edx, 2
0x180003d29  jmp     short loc_180003D4F
0x180003d2b  mov     [rsp+98h+var_50], rdi
0x180003d30  mov     r8, r13
0x180003d33  mov     dword ptr [rsp+98h+var_58], r14d
0x180003d38  mov     qword ptr [rsp+98h+var_68], r12
0x180003d3d  mov     [rsp+98h+var_70], r12
0x180003d42  mov     r9, rbx
0x180003d45  mov     dword ptr [rsp+98h+var_78], r12d
0x180003d4a  mov     edx, 0Ah
0x180003d4f  mov     rcx, r15
0x180003d52  call    ?HardCodedIntercept@CSimpleTableDispenser@@AEBAJW4eSERVERWIRINGMETA_Interceptor@@PEBG1KPEAX2KKPEAPEAX@Z; CSimpleTableDispenser::HardCodedIntercept(eSERVERWIRINGMETA_Interceptor,ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void * *)
0x180003d57  jmp     loc_180003B46
0x180003d5c  lea     rdx, aPackedschema; "PACKEDSCHEMA"
0x180003d63  mov     rcx, rbp; String1
0x180003d66  call    cs:__imp__wcsicmp
0x180003d6c  test    eax, eax
0x180003d6e  jnz     short loc_180003D97
0x180003d70  mov     eax, [rsp+98h+arg_30]
0x180003d77  mov     r8, rbp
0x180003d7a  mov     [rsp+98h+var_50], rdi
0x180003d7f  mov     dword ptr [rsp+98h+var_58], eax
0x180003d83  mov     rax, [rsp+98h+arg_20]
0x180003d8b  mov     qword ptr [rsp+98h+var_68], rax
0x180003d90  mov     [rsp+98h+var_70], rsi
0x180003d95  jmp     short loc_180003D42
0x180003d97  lea     rdx, [rsp+98h+arg_8]; unsigned int *
0x180003d9f  mov     rcx, rbx; String2
0x180003da2  call    ?GetTableID@TFixedPackedSchemaInterceptor@@SAJPEBGAEAK@Z; TFixedPackedSchemaInterceptor::GetTableID(ushort const *,ulong &)
0x180003da7  test    eax, eax
0x180003da9  js      loc_180003B46
0x180003daf  mov     eax, [rsp+98h+arg_30]
0x180003db6  mov     r8, rbx; unsigned __int16 *
0x180003db9  mov     r9d, [rsp+98h+arg_8]; unsigned int
0x180003dc1  mov     rdx, rbp; unsigned __int16 *
0x180003dc4  mov     [rsp+98h+var_58], rdi; void **
0x180003dc9  mov     rcx, r15; this
0x180003dcc  mov     [rsp+98h+var_60], eax; unsigned int
0x180003dd0  mov     rax, [rsp+98h+arg_20]
0x180003dd8  mov     [rsp+98h+var_68], r14d; unsigned int
0x180003ddd  mov     [rsp+98h+var_70], rax; void *
0x180003de2  mov     [rsp+98h+var_78], rsi; void *
0x180003de7  call    ?InternalGetTable@CSimpleTableDispenser@@AEAAJPEBG0KPEAX1KKPEAPEAX@Z; CSimpleTableDispenser::InternalGetTable(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void * *)
0x180003dec  jmp     loc_180003B46
0x180003df1  mov     eax, 8021080Ch
0x180003df6  jmp     loc_180003B46
```
