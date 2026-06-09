# MintValue_ToErrorString

- ea: `0x180011160`
- end: `0x18001132f`
- name: `MintValue_ToErrorString`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000e010`

## callees

- `0x180006e64`
- `0x180007ad0`
- `0x180007b30`
- `0x18000ee20`
- `0x180010a50`
- `0x180011160`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180011236`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800112ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180011236`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800112ca`

## string_xrefs

- `0x18001122b`: `mpunits.dll`
- `0x1800112bf`: `mpunits.dll`

## pseudocode

```c
_OWORD *__fastcall MintValue_ToErrorString(_OWORD *a1, unsigned int *a2)
{
  __int64 TypeName; // r14
  const wchar_t *v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // r8d
  __int64 v8; // rsi
  unsigned int v9; // ecx
  int *v10; // rdx
  __int64 v11; // rax
  HMODULE v12; // rax
  __int64 v13; // rax
  int ResultCallback; // eax
  HMODULE ModuleHandleA; // rax
  bool v16; // cc
  int v17; // eax
  unsigned __int64 v19; // [rsp+30h] [rbp-48h] BYREF
  int *v20; // [rsp+38h] [rbp-40h]
  __int128 v21; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-28h] BYREF
  int v23; // [rsp+60h] [rbp-18h]
  int v24; // [rsp+64h] [rbp-14h]

  v19 = 271;
  v20 = 0;
  TypeName = MintValue_GetTypeName(a2);
  *a1 = 0;
  if ( (*a2 & 0x100) == 0 )
  {
    v6 = SuppressErrorDetails();
    v7 = *a2;
    v8 = v6;
    v9 = a2[1];
    v10 = (int *)*((_QWORD *)a2 + 1);
    if ( (unsigned __int8)*a2 != 13 || (v7 & 0x100) != 0 )
    {
      DWORD1(v21) = a2[1];
      *((_QWORD *)&v21 + 1) = v10;
      LODWORD(v21) = v7;
      v11 = MintValue_CoerceToStringImpl(v22, &v21);
      v7 = *(_DWORD *)v11;
      v9 = *(_DWORD *)(v11 + 4);
      v10 = *(int **)(v11 + 8);
    }
    else if ( *v10 != -1 )
    {
      ++*v10;
    }
    v19 = __PAIR64__(v9, v7);
    v20 = v10;
    RevertErrorDetails(v8);
    if ( (_BYTE)v19 != 13 || (v19 & 0x100) != 0 )
    {
      if ( (_BYTE)v19 == 0xFE && NITS_PRESENCE_STUB != 1 )
      {
        ResultCallback = JobQueryResultCallback();
        v22[0] = 0;
        v23 = 1144;
        v24 = -1;
        v22[1] = "admin\\wmi\\winomi\\mp\\basicops\\mint.value.c";
        AssertW_Checked(
          ResultCallback == 0,
          (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
          (int)L"Ignoring error deliberately",
          (int)v22,
          0);
      }
    }
    else
    {
      v5 = (const wchar_t *)*((_QWORD *)v20 + 2);
      if ( v5 )
        goto LABEL_11;
    }
    v21 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v13 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2114, TypeName);
    goto LABEL_16;
  }
  v5 = L"$null";
LABEL_11:
  v21 = 0;
  v12 = GetModuleHandleA("mpunits.dll");
  v13 = Intlstr_FormatString_FormatMessage(v12, 2115, v5);
LABEL_16:
  v16 = (char)v19 < 12;
  *(_QWORD *)&v21 = v13;
  BYTE8(v21) = 1;
  *a1 = v21;
  if ( !v16 && (v19 & 0x100) == 0 && *v20 != -1 )
  {
    v17 = *v20 - 1;
    *v20 = v17;
    if ( !v17 )
      (*((void (__fastcall **)(unsigned __int64 *))v20 + 1))(&v19);
  }
  return a1;
}

```

## disassembly

```asm
0x180011160  push    rbp
0x180011162  push    rbx
0x180011163  push    rsi
0x180011164  push    rdi
0x180011165  push    r12
0x180011167  push    r14
0x180011169  mov     rbp, rsp
0x18001116c  sub     rsp, 78h
0x180011170  mov     rdi, rcx
0x180011173  mov     [rbp+var_48], 10Fh
0x18001117b  mov     rcx, rdx
0x18001117e  mov     [rbp+var_40], 0
0x180011186  mov     rbx, rdx
0x180011189  call    MintValue_GetTypeName
0x18001118e  mov     r12d, 100h
0x180011194  xorps   xmm0, xmm0
0x180011197  mov     r14, rax
0x18001119a  movups  xmmword ptr [rdi], xmm0
0x18001119d  test    [rbx], r12d
0x1800111a0  jz      short loc_1800111AB
0x1800111a2  lea     rbx, aNull_0; "$null"
0x1800111a9  jmp     short loc_180011228
0x1800111ab  call    SuppressErrorDetails
0x1800111b0  mov     r8d, [rbx]
0x1800111b3  mov     rsi, rax
0x1800111b6  mov     ecx, [rbx+4]
0x1800111b9  mov     rdx, [rbx+8]
0x1800111bd  cmp     r8b, 0Dh
0x1800111c1  jnz     short loc_1800111D5
0x1800111c3  test    r12d, r8d
0x1800111c6  jnz     short loc_1800111D5
0x1800111c8  mov     eax, [rdx]
0x1800111ca  cmp     eax, 0FFFFFFFFh
0x1800111cd  jz      short loc_1800111F7
0x1800111cf  inc     eax
0x1800111d1  mov     [rdx], eax
0x1800111d3  jmp     short loc_1800111F7
0x1800111d5  mov     dword ptr [rbp+var_38+4], ecx
0x1800111d8  lea     rcx, [rbp+var_28]
0x1800111dc  mov     qword ptr [rbp+var_38+8], rdx
0x1800111e0  lea     rdx, [rbp+var_38]
0x1800111e4  mov     dword ptr [rbp+var_38], r8d
0x1800111e8  call    MintValue_CoerceToStringImpl
0x1800111ed  mov     r8d, [rax]
0x1800111f0  mov     ecx, [rax+4]
0x1800111f3  mov     rdx, [rax+8]
0x1800111f7  mov     dword ptr [rbp+var_48+4], ecx
0x1800111fa  mov     rcx, rsi
0x1800111fd  mov     dword ptr [rbp+var_48], r8d
0x180011201  mov     [rbp+var_40], rdx
0x180011205  call    RevertErrorDetails
0x18001120a  mov     al, byte ptr [rbp+var_48]
0x18001120d  cmp     al, 0Dh
0x18001120f  jnz     short loc_180011254
0x180011211  test    dword ptr [rbp+var_48], r12d
0x180011215  jnz     short loc_180011254
0x180011217  mov     rax, [rbp+var_40]
0x18001121b  mov     rbx, [rax+10h]
0x18001121f  test    rbx, rbx
0x180011222  jz      loc_1800112BC
0x180011228  xorps   xmm0, xmm0
0x18001122b  lea     rcx, ModuleName; "mpunits.dll"
0x180011232  movups  [rbp+var_38], xmm0
0x180011236  call    cs:__imp_GetModuleHandleA
0x18001123c  mov     r9, r14
0x18001123f  mov     r8, rbx
0x180011242  mov     rcx, rax
0x180011245  mov     edx, 843h
0x18001124a  call    _Intlstr_FormatString_FormatMessage
0x18001124f  jmp     loc_1800112E0
0x180011254  cmp     al, 0FEh
0x180011256  jnz     short loc_1800112BC
0x180011258  cmp     cs:NITS_PRESENCE_STUB, 1
0x180011260  jz      short loc_1800112BC
0x180011262  mov     rax, cs:off_180047AB8
0x180011269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001126e  xor     ecx, ecx
0x180011270  mov     [rbp+var_28], 0
0x180011278  test    eax, eax
0x18001127a  mov     [rbp+var_18], 478h
0x180011281  lea     rax, aAdminWmiWinomi_2; "admin\\wmi\\winomi\\mp\\basicops\\mint."...
0x180011288  mov     [rbp+var_14], 0FFFFFFFFh
0x18001128f  mov     [rbp+var_20], rax
0x180011293  lea     r9, [rbp+var_28]
0x180011297  mov     rax, cs:off_180047A80
0x18001129e  lea     r8, aIgnoringErrorD; "Ignoring error deliberately"
0x1800112a5  setz    cl
0x1800112a8  mov     [rsp+78h+var_58], 0
0x1800112b0  lea     rdx, aNitsPresenceSt_0; "!((NITS_PRESENCE_STUB != NitsStubbedOut"...
0x1800112b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112bc  xorps   xmm0, xmm0
0x1800112bf  lea     rcx, ModuleName; "mpunits.dll"
0x1800112c6  movups  [rbp+var_38], xmm0
0x1800112ca  call    cs:__imp_GetModuleHandleA
0x1800112d0  mov     r8, r14
0x1800112d3  mov     edx, 842h
0x1800112d8  mov     rcx, rax
0x1800112db  call    _Intlstr_FormatString_FormatMessage
0x1800112e0  cmp     byte ptr [rbp+var_48], 0Ch
0x1800112e4  mov     qword ptr [rbp+var_38], rax
0x1800112e8  mov     byte ptr [rbp+var_38+8], 1
0x1800112ec  movups  xmm0, [rbp+var_38]
0x1800112f0  movdqu  xmmword ptr [rdi], xmm0
0x1800112f4  jl      short loc_18001131F
0x1800112f6  test    dword ptr [rbp+var_48], r12d
0x1800112fa  jnz     short loc_18001131F
0x1800112fc  mov     rcx, [rbp+var_40]
0x180011300  mov     eax, [rcx]
0x180011302  cmp     eax, 0FFFFFFFFh
0x180011305  jz      short loc_18001131F
0x180011307  sub     eax, 1
0x18001130a  mov     [rcx], eax
0x18001130c  jnz     short loc_18001131F
0x18001130e  mov     rax, [rbp+var_40]
0x180011312  lea     rcx, [rbp+var_48]
0x180011316  mov     rax, [rax+8]
0x18001131a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001131f  mov     rax, rdi
0x180011322  add     rsp, 78h
0x180011326  pop     r14
0x180011328  pop     r12
0x18001132a  pop     rdi
0x18001132b  pop     rsi
0x18001132c  pop     rbx
0x18001132d  pop     rbp
0x18001132e  retn
```
