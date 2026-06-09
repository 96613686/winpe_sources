# MintValue_CoerceToTimestampImpl

- ea: `0x18000f040`
- end: `0x18000f18e`
- name: `MintValue_CoerceToTimestampImpl`
- size: `334`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000bf80`
- `0x18000db80`
- `0x180017418`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000da24`
- `0x18000f040`
- `0x180010a50`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000f095`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000f134`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000f095`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000f134`

## string_xrefs

- `0x18000f089`: `mpunits.dll`
- `0x18000f12a`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CoerceToTimestampImpl(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax
  __int64 TypeName; // rbx
  HMODULE v6; // rax
  __int64 String_LoadString; // rax
  const wchar_t *v8; // r8
  __int128 v9; // xmm0
  __int128 v11; // [rsp+30h] [rbp-18h] BYREF

  if ( *(_BYTE *)a2 == 15
    && (*(_DWORD *)a2 & 0x100) == 0
    && ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL)) )
  {
    v11 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v11 = Intlstr_GetString_LoadString(ModuleHandleA, 2066);
    BYTE8(v11) = 0;
    MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
  }
  else
  {
    if ( (__CFSHR__(*(_DWORD *)a2, 9) || (unsigned __int8)(*(_BYTE *)a2 - 1) > 0xAu)
      && (*(_BYTE *)a2 != 13 || __CFSHR__(*(_DWORD *)a2, 9)) )
    {
      v11 = 0xFFu;
      v9 = 0xFFu;
    }
    else
    {
      TypeName = MintValue_GetTypeName(a2);
      v6 = GetModuleHandleA("mpunits.dll");
      String_LoadString = Intlstr_GetString_LoadString(v6, 2084);
      v8 = L"timestamp";
      if ( String_LoadString )
        v8 = (const wchar_t *)String_LoadString;
      v9 = *(_OWORD *)CoercionNotImplemented_Impl(&v11, TypeName, v8);
    }
    *(_OWORD *)a1 = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f040  mov     [rsp+arg_0], rbx
0x18000f045  push    rdi
0x18000f046  sub     rsp, 40h
0x18000f04a  cmp     byte ptr [rdx], 0Fh
0x18000f04d  mov     rbx, rdx
0x18000f050  mov     rdi, rcx
0x18000f053  jnz     loc_18000F106
0x18000f059  test    dword ptr [rdx], 100h
0x18000f05f  jnz     loc_18000F106
0x18000f065  mov     rcx, [rdx+8]
0x18000f069  mov     rax, cs:off_180047B90
0x18000f070  mov     rcx, [rcx+18h]
0x18000f074  mov     rax, [rax+8]
0x18000f078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f07d  test    rax, rax
0x18000f080  jz      loc_18000F106
0x18000f086  xorps   xmm0, xmm0
0x18000f089  lea     rcx, ModuleName; "mpunits.dll"
0x18000f090  movups  [rsp+48h+var_18], xmm0
0x18000f095  call    cs:__imp_GetModuleHandleA
0x18000f09b  mov     rcx, rax
0x18000f09e  mov     edx, 812h
0x18000f0a3  call    _Intlstr_GetString_LoadString
0x18000f0a8  mov     qword ptr [rsp+48h+var_18], rax
0x18000f0ad  lea     r9, [rsp+48h+var_18]
0x18000f0b2  mov     byte ptr [rsp+48h+var_18+8], 0
0x18000f0b7  lea     rdx, aMi; "MI"
0x18000f0be  movaps  xmm0, [rsp+48h+var_18]
0x18000f0c3  mov     r8d, 0Bh
0x18000f0c9  mov     [rsp+48h+var_20], 0; __int64
0x18000f0d2  movdqa  [rsp+48h+var_18], xmm0
0x18000f0d8  mov     [rsp+48h+var_28], 0; __int64
0x18000f0e1  lea     ecx, [r8-4]; int
0x18000f0e5  call    MI_ReportErrorDetails_ForCustomError
0x18000f0ea  xor     edx, edx
0x18000f0ec  xor     ecx, ecx
0x18000f0ee  mov     eax, 0FFh
0x18000f0f3  mov     [rdi+4], edx
0x18000f0f6  and     eax, 0FFFFFFFEh
0x18000f0f9  mov     [rdi+8], rcx
0x18000f0fd  or      eax, 0FEh
0x18000f102  mov     [rdi], eax
0x18000f104  jmp     short loc_18000F180
0x18000f106  mov     ecx, [rbx]
0x18000f108  shr     ecx, 9
0x18000f10b  sbb     ecx, ecx
0x18000f10d  test    ecx, ecx
0x18000f10f  jnz     short loc_18000F119
0x18000f111  mov     al, [rbx]
0x18000f113  dec     al
0x18000f115  cmp     al, 0Ah
0x18000f117  jbe     short loc_18000F122
0x18000f119  cmp     byte ptr [rbx], 0Dh
0x18000f11c  jnz     short loc_18000F167
0x18000f11e  test    ecx, ecx
0x18000f120  jnz     short loc_18000F167
0x18000f122  mov     rcx, rbx
0x18000f125  call    MintValue_GetTypeName
0x18000f12a  lea     rcx, ModuleName; "mpunits.dll"
0x18000f131  mov     rbx, rax
0x18000f134  call    cs:__imp_GetModuleHandleA
0x18000f13a  mov     rcx, rax
0x18000f13d  mov     edx, 824h
0x18000f142  call    _Intlstr_GetString_LoadString
0x18000f147  test    rax, rax
0x18000f14a  lea     r8, aTimestamp; "timestamp"
0x18000f151  mov     rdx, rbx
0x18000f154  lea     rcx, [rsp+48h+var_18]
0x18000f159  cmovnz  r8, rax
0x18000f15d  call    CoercionNotImplemented_Impl
0x18000f162  movups  xmm0, xmmword ptr [rax]
0x18000f165  jmp     short loc_18000F17C
0x18000f167  xor     eax, eax
0x18000f169  mov     qword ptr [rsp+48h+var_18], 0FFh
0x18000f172  mov     qword ptr [rsp+48h+var_18+8], rax
0x18000f177  movups  xmm0, [rsp+48h+var_18]
0x18000f17c  movdqu  xmmword ptr [rdi], xmm0
0x18000f180  mov     rbx, [rsp+48h+arg_0]
0x18000f185  mov     rax, rdi
0x18000f188  add     rsp, 40h
0x18000f18c  pop     rdi
0x18000f18d  retn
```
