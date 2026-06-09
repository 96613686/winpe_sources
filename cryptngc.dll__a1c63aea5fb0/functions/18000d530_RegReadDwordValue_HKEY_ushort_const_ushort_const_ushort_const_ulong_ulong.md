# RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)

- ea: `0x18000d530`
- end: `0x18000d693`
- name: `?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z`
- size: `355`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a2a0`
- `0x18000d2f0`

## callees

- `0x18000c190`
- `0x18000d530`
- `0x180027448`
- `0x18002c23c`
- `0x180044a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d588`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d588`

## string_xrefs

- `0x18000d5cb`: `RegReadDwordValue`
- `0x18000d5fb`: `RegReadDwordValue`
- `0x18000d67b`: `RegReadDwordValue`
- `0x18000d5af`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x18000d682`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18000d646`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned int a6)
{
  LSTATUS ValueW; // eax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // edi
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  const wchar_t *v13; // r9
  int v15; // eax
  const wchar_t *v16; // r9
  __int64 v17; // [rsp+20h] [rbp-58h]
  __int64 v18; // [rsp+28h] [rbp-50h]
  unsigned int v19; // [rsp+40h] [rbp-38h] BYREF
  DWORD v20[13]; // [rsp+44h] [rbp-34h] BYREF

  a6 = 0;
  v19 = 0;
  v20[0] = 4;
  if ( a5 )
  {
    ValueW = RegGetValueW(a1, a2, a3, 0xFFFFu, &a6, &v19, v20);
    v10 = ValueW;
    if ( ValueW == 2 )
    {
      v11 = !a3 || !*a3;
      LODWORD(v18) = 2;
      v12 = L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.";
    }
    else
    {
      if ( ValueW != 234 )
      {
        if ( ValueW )
        {
          Logger::WriteRegistryFailureEvent(ValueW, v9, a4, a3);
          v15 = IsEmptyString(a3);
          LODWORD(v17) = v10;
          v16 = L"(default)";
          if ( !v15 )
            v16 = a3;
          Logger::TraceWarning(
            L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
            L"RegReadDwordValue",
            a4,
            v16,
            v17);
          goto LABEL_10;
        }
        if ( a6 == 4 )
        {
LABEL_10:
          *a5 = v19;
          return v10;
        }
      }
      v11 = IsEmptyString(a3);
      LODWORD(v18) = v10;
      v12 = L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.";
    }
    LODWORD(v17) = 0;
    v13 = L"(default)";
    if ( !v11 )
      v13 = a3;
    Logger::TraceWarning(v12, L"RegReadDwordValue", a4, v13, v17, v18);
    v10 = 0;
    goto LABEL_10;
  }
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadDwordValue", L"pData");
  return 87;
}

```

## disassembly

```asm
0x18000d530  mov     r11, rsp
0x18000d533  push    rbx
0x18000d534  push    rbp
0x18000d535  push    rsi
0x18000d536  push    r14
0x18000d538  sub     rsp, 58h
0x18000d53c  mov     rsi, [rsp+78h+arg_20]
0x18000d544  xor     r14d, r14d
0x18000d547  mov     [r11+30h], r14d
0x18000d54b  mov     rbp, r9
0x18000d54e  mov     [r11-38h], r14d
0x18000d552  mov     rbx, r8
0x18000d555  mov     [rsp+78h+var_34], 4
0x18000d55d  test    rsi, rsi
0x18000d560  jz      loc_18000D5F4
0x18000d566  lea     rax, [r11-34h]
0x18000d56a  mov     [r11+8], rdi
0x18000d56e  mov     [r11-48h], rax
0x18000d572  mov     r9d, 0FFFFh; dwFlags
0x18000d578  lea     rax, [r11-38h]
0x18000d57c  mov     [r11-50h], rax
0x18000d580  lea     rax, [r11+30h]
0x18000d584  mov     [r11-58h], rax
0x18000d588  call    cs:__imp_RegGetValueW
0x18000d58e  mov     edi, eax
0x18000d590  cmp     eax, 2
0x18000d593  jnz     loc_18000D624
0x18000d599  test    rbx, rbx
0x18000d59c  jz      short loc_18000D61D
0x18000d59e  cmp     [rbx], r14w
0x18000d5a2  jz      short loc_18000D61D
0x18000d5a4  mov     eax, r14d
0x18000d5a7  mov     dword ptr [rsp+78h+var_50], 2
0x18000d5af  lea     rcx, aSTheRegistryKe_2; "%s: The registry key value \"%s@%s\" do"...
0x18000d5b6  test    eax, eax
0x18000d5b8  mov     dword ptr [rsp+78h+var_58], r14d
0x18000d5bd  lea     r9, aDefault; "(default)"
0x18000d5c4  mov     r8, rbp
0x18000d5c7  cmovz   r9, rbx
0x18000d5cb  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x18000d5d2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d5d7  mov     edi, r14d
0x18000d5da  mov     eax, [rsp+78h+var_38]
0x18000d5de  mov     [rsi], eax
0x18000d5e0  mov     eax, edi
0x18000d5e2  mov     rdi, [rsp+78h+arg_0]
0x18000d5ea  add     rsp, 58h
0x18000d5ee  pop     r14
0x18000d5f0  pop     rsi
0x18000d5f1  pop     rbp
0x18000d5f2  pop     rbx
0x18000d5f3  retn
0x18000d5f4  lea     r8, aPdata; "pData"
0x18000d5fb  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x18000d602  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000d609  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d60e  mov     eax, 57h ; 'W'
0x18000d613  add     rsp, 58h
0x18000d617  pop     r14
0x18000d619  pop     rsi
0x18000d61a  pop     rbp
0x18000d61b  pop     rbx
0x18000d61c  retn
0x18000d61d  mov     eax, 1
0x18000d622  jmp     short loc_18000D5A7
0x18000d624  cmp     edi, 0EAh
0x18000d62a  jz      short loc_18000D63A
0x18000d62c  test    edi, edi
0x18000d62e  jnz     short loc_18000D652
0x18000d630  cmp     [rsp+78h+arg_28], 4
0x18000d638  jz      short loc_18000D5DA
0x18000d63a  mov     rcx, rbx; unsigned __int16 *
0x18000d63d  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000d642  mov     dword ptr [rsp+78h+var_50], edi
0x18000d646  lea     rcx, aSTheRegistryKe_6; "%s: The registry key value \"%s@%s\" is"...
0x18000d64d  jmp     loc_18000D5B6
0x18000d652  mov     r9, rbx; unsigned __int16 *
0x18000d655  mov     r8, rbp; unsigned __int16 *
0x18000d658  mov     ecx, edi; unsigned int
0x18000d65a  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18000d65f  mov     rcx, rbx; unsigned __int16 *
0x18000d662  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000d667  test    eax, eax
0x18000d669  mov     dword ptr [rsp+78h+var_58], edi
0x18000d66d  lea     r9, aDefault; "(default)"
0x18000d674  mov     r8, rbp
0x18000d677  cmovz   r9, rbx
0x18000d67b  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x18000d682  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18000d689  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d68e  jmp     loc_18000D5DA
```
