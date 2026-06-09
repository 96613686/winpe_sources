# MintValue_CoerceToStringImpl

- ea: `0x18000ee20`
- end: `0x18000f036`
- name: `MintValue_CoerceToStringImpl`
- size: `534`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000c550`
- `0x18000db80`
- `0x180011160`
- `0x180011db4`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000da24`
- `0x18000ee20`
- `0x1800104f0`
- `0x180010a50`
- `0x180043270`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000ef06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000ef06`

## string_xrefs

- `0x18000eefb`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CoerceToStringImpl(__int64 a1, char *a2)
{
  bool v2; // zf
  wchar_t *v5; // rdx
  int v6; // ecx
  HMODULE ModuleHandleA; // rax
  __int64 TypeName; // rax
  _OWORD *v9; // rax
  __int128 v11; // [rsp+30h] [rbp-9h] BYREF
  wchar_t Buffer[32]; // [rsp+40h] [rbp+7h] BYREF

  v2 = *a2 == -1;
  *(_OWORD *)a1 = 0;
  if ( v2 || (*(_DWORD *)a2 & 0x100) != 0 )
  {
    v5 = (wchar_t *)&dword_18005C6C4;
    goto LABEL_19;
  }
  if ( !*a2 )
  {
    v5 = L"True";
    if ( !a2[8] )
      v5 = L"False";
    goto LABEL_19;
  }
  if ( ((*a2 - 2) & 0xF9) == 0 || (unsigned __int8)*a2 <= 0xBu && (v6 = 2218, _bittest(&v6, *a2)) )
  {
    Swprintf_CultureInvariant(Buffer, 0x19u);
    v5 = Buffer;
LABEL_19:
    v9 = (_OWORD *)MintValue_CreateViaStrdup(&v11, v5);
    goto LABEL_20;
  }
  if ( (unsigned __int8)(*a2 - 9) <= 1u )
  {
    Swprintf_CultureInvariant(Buffer, 0x1Eu);
    v5 = Buffer;
    goto LABEL_19;
  }
  if ( *a2 != 15 || !((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL)) )
  {
    TypeName = MintValue_GetTypeName(a2);
    v9 = (_OWORD *)CoercionNotImplemented_Impl(&v11, TypeName, L"String");
LABEL_20:
    *(_OWORD *)a1 = *v9;
    return a1;
  }
  v11 = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  *(_QWORD *)&v11 = Intlstr_GetString_LoadString(ModuleHandleA, 2066);
  BYTE8(v11) = 0;
  MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x18000ee20  mov     [rsp-8+arg_0], rbx
0x18000ee25  mov     [rsp-8+arg_10], rdi
0x18000ee2a  push    rbp
0x18000ee2b  lea     rbp, [rsp-57h]
0x18000ee30  sub     rsp, 90h
0x18000ee37  mov     rax, cs:__security_cookie
0x18000ee3e  xor     rax, rsp
0x18000ee41  mov     [rbp+57h+var_10], rax
0x18000ee45  cmp     byte ptr [rdx], 0FFh
0x18000ee48  xorps   xmm0, xmm0
0x18000ee4b  movups  xmmword ptr [rcx], xmm0
0x18000ee4e  mov     rdi, rdx
0x18000ee51  mov     rbx, rcx
0x18000ee54  jz      loc_18000EFFB
0x18000ee5a  test    dword ptr [rdx], 100h
0x18000ee60  jnz     loc_18000EFFB
0x18000ee66  cmp     byte ptr [rdx], 0
0x18000ee69  jnz     short loc_18000EE86
0x18000ee6b  cmp     byte ptr [rdi+8], 0
0x18000ee6f  lea     rax, aFalse; "False"
0x18000ee76  lea     rdx, aTrue; "True"
0x18000ee7d  cmovz   rdx, rax
0x18000ee81  jmp     loc_18000F002
0x18000ee86  mov     al, [rdx]
0x18000ee88  sub     al, 2
0x18000ee8a  test    al, 0F9h
0x18000ee8c  jz      loc_18000EFEF
0x18000ee92  cmp     byte ptr [rdx], 0Bh
0x18000ee95  ja      short loc_18000EEC6
0x18000ee97  movsx   eax, byte ptr [rdx]
0x18000ee9a  mov     ecx, 8AAh
0x18000ee9f  bt      ecx, eax
0x18000eea2  jnb     short loc_18000EEC6
0x18000eea4  lea     r8, aI64u; "%I64u"
0x18000eeab  mov     r9, [rdx+8]
0x18000eeaf  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18000eeb3  mov     edx, 19h; BufferCount
0x18000eeb8  call    Swprintf_CultureInvariant
0x18000eebd  lea     rdx, [rbp+57h+Buffer]
0x18000eec1  jmp     loc_18000F002
0x18000eec6  mov     al, [rdx]
0x18000eec8  sub     al, 9
0x18000eeca  cmp     al, 1
0x18000eecc  jbe     loc_18000EF92
0x18000eed2  cmp     byte ptr [rdx], 0Fh
0x18000eed5  jnz     loc_18000EF75
0x18000eedb  mov     rcx, [rdx+8]
0x18000eedf  mov     rax, cs:off_180047B90
0x18000eee6  mov     rcx, [rcx+18h]
0x18000eeea  mov     rax, [rax+8]
0x18000eeee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef3  test    rax, rax
0x18000eef6  jz      short loc_18000EF75
0x18000eef8  xorps   xmm0, xmm0
0x18000eefb  lea     rcx, ModuleName; "mpunits.dll"
0x18000ef02  movups  [rbp+57h+var_60], xmm0
0x18000ef06  call    cs:__imp_GetModuleHandleA
0x18000ef0c  mov     rcx, rax
0x18000ef0f  mov     edx, 812h
0x18000ef14  call    _Intlstr_GetString_LoadString
0x18000ef19  mov     qword ptr [rbp+57h+var_60], rax
0x18000ef1d  lea     r9, [rbp+57h+var_60]
0x18000ef21  mov     byte ptr [rbp+57h+var_60+8], 0
0x18000ef25  lea     rdx, aMi; "MI"
0x18000ef2c  movaps  xmm0, [rbp+57h+var_60]
0x18000ef30  mov     r8d, 0Bh
0x18000ef36  mov     [rsp+90h+var_68], 0; __int64
0x18000ef3f  movdqa  [rbp+57h+var_60], xmm0
0x18000ef44  mov     [rsp+90h+var_70], 0; __int64
0x18000ef4d  lea     ecx, [r8-4]; int
0x18000ef51  call    MI_ReportErrorDetails_ForCustomError
0x18000ef56  xor     edx, edx
0x18000ef58  xor     ecx, ecx
0x18000ef5a  mov     eax, 0FFh
0x18000ef5f  mov     [rbx+4], edx
0x18000ef62  and     eax, 0FFFFFFFEh
0x18000ef65  mov     [rbx+8], rcx
0x18000ef69  or      eax, 0FEh
0x18000ef6e  mov     [rbx], eax
0x18000ef70  jmp     loc_18000F012
0x18000ef75  mov     rcx, rdi
0x18000ef78  call    MintValue_GetTypeName
0x18000ef7d  mov     r8, cs:off_1800538E8; "String"
0x18000ef84  lea     rcx, [rbp+57h+var_60]
0x18000ef88  mov     rdx, rax
0x18000ef8b  call    CoercionNotImplemented_Impl
0x18000ef90  jmp     short loc_18000F00B
0x18000ef92  movsd   xmm3, qword ptr [rdx+8]
0x18000ef97  ucomisd xmm3, xmm3
0x18000ef9b  jnp     short loc_18000EFA6
0x18000ef9d  lea     rdx, aNan; "NaN"
0x18000efa4  jmp     short loc_18000F002
0x18000efa6  movaps  xmm0, xmm3
0x18000efa9  subsd   xmm0, xmm3
0x18000efad  ucomisd xmm0, xmm0
0x18000efb1  jnp     short loc_18000EFCF
0x18000efb3  comisd  xmm3, cs:__real@0000000000000000
0x18000efbb  lea     rdx, aInfinity; "Infinity"
0x18000efc2  lea     rax, aInfinity_0; "-Infinity"
0x18000efc9  cmovbe  rdx, rax
0x18000efcd  jmp     short loc_18000F002
0x18000efcf  movq    r9, xmm3
0x18000efd4  lea     r8, aG; "%g"
0x18000efdb  mov     edx, 1Eh; BufferCount
0x18000efe0  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18000efe4  call    Swprintf_CultureInvariant
0x18000efe9  lea     rdx, [rbp+57h+Buffer]
0x18000efed  jmp     short loc_18000F002
0x18000efef  lea     r8, aI64d; "%I64d"
0x18000eff6  jmp     loc_18000EEAB
0x18000effb  lea     rdx, dword_18005C6C4
0x18000f002  lea     rcx, [rbp+57h+var_60]
0x18000f006  call    MintValue_CreateViaStrdup
0x18000f00b  movups  xmm0, xmmword ptr [rax]
0x18000f00e  movdqu  xmmword ptr [rbx], xmm0
0x18000f012  mov     rax, rbx
0x18000f015  mov     rcx, [rbp+57h+var_10]
0x18000f019  xor     rcx, rsp; StackCookie
0x18000f01c  call    __security_check_cookie
0x18000f021  lea     r11, [rsp+90h+var_s0]
0x18000f029  mov     rbx, [r11+10h]
0x18000f02d  mov     rdi, [r11+20h]
0x18000f031  mov     rsp, r11
0x18000f034  pop     rbp
0x18000f035  retn
```
