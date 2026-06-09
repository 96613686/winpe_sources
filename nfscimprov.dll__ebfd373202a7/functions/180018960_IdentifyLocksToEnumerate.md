# IdentifyLocksToEnumerate

- ea: `0x180018960`
- end: `0x180018b20`
- name: `IdentifyLocksToEnumerate`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018b64`
- `0x180019c74`

## callees

- `0x18000eae4`
- `0x18000ec88`
- `0x18000efc8`
- `0x180018380`
- `0x180018960`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018a8e`
- `ntdll!RtlInitUnicodeString` at `0x180018a8e`
- `ntdll!RtlGUIDFromString` at `0x180018a9c`
- `ntdll!RtlGUIDFromString` at `0x180018a9c`

## string_xrefs

- `0x1800189f4`: `ClientComputer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IdentifyLocksToEnumerate(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v4; // eax
  unsigned int v5; // ebx
  char v6; // r14
  __int64 v7; // rax
  __int64 v8; // rcx
  char v9; // r12
  bool v10; // r15
  NTSTATUS v11; // r15d
  int v13; // [rsp+30h] [rbp-79h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-71h] BYREF
  _OWORD v15[2]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v16; // [rsp+68h] [rbp-41h]
  PCWSTR SourceString[2]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v18; // [rsp+80h] [rbp-29h]
  __int64 v19; // [rsp+90h] [rbp-19h]
  GUID Guid; // [rsp+98h] [rbp-11h] BYREF
  _WORD v21[8]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+Fh]
  __int64 v23; // [rsp+C0h] [rbp+17h]

  v2 = a2;
  Guid = GUID_NULL;
  v23 = 7;
  v22 = 0;
  v21[0] = 0;
  v13 = 0;
  memset(v15, 0, sizeof(v15));
  v16 = 0;
  *(_OWORD *)SourceString = 0;
  v18 = 0;
  v19 = 0;
  if ( !a1 || !*(_QWORD *)a1 )
    goto LABEL_16;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _OWORD *))(*(_QWORD *)a1 + 136LL))(
         a1,
         L"ClientComputer",
         &v13,
         v15);
  v5 = v4;
  if ( v4 || v13 != 13 )
  {
    v6 = 1;
    if ( v4 != 6 && v4 )
      goto LABEL_17;
  }
  else
  {
    v6 = 0;
    v7 = std::char_traits<unsigned short>::length(*(_QWORD *)&v15[0]);
    std::wstring::assign(v21, v8, v7);
  }
  if ( !*(_QWORD *)a1 )
  {
LABEL_16:
    v5 = 4;
    goto LABEL_17;
  }
  v9 = 1;
  v10 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, PCWSTR *))(*(_QWORD *)a1 + 136LL))(
         a1,
         L"StateId",
         &v13,
         SourceString);
  if ( v5 )
  {
    if ( v5 == 6 )
    {
      v5 = 0;
LABEL_15:
      *(_BYTE *)(v2 + 57) = v9;
      *(_BYTE *)(v2 + 58) = v6;
      *(GUID *)(v2 + 40) = Guid;
      std::wstring::operator=(v2 + 8, v21);
      *(_BYTE *)(v2 + 56) = v10;
    }
  }
  else
  {
    if ( v13 != 13 )
      goto LABEL_15;
    v9 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString[0]);
    v11 = RtlGUIDFromString(&DestinationString, &Guid);
    v5 = v11 < 0;
    v10 = v11 >= 0;
    if ( !v5 )
      goto LABEL_15;
  }
LABEL_17:
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v21, a2, 0);
  return v5;
}

```

## disassembly

```asm
0x180018960  mov     [rsp-8+arg_10], rbx
0x180018965  push    rbp
0x180018966  push    rsi
0x180018967  push    rdi
0x180018968  push    r12
0x18001896a  push    r13
0x18001896c  push    r14
0x18001896e  push    r15
0x180018970  lea     rbp, [rsp-27h]
0x180018975  sub     rsp, 0D0h
0x18001897c  mov     rax, cs:__security_cookie
0x180018983  xor     rax, rsp
0x180018986  mov     [rbp+57h+var_38], rax
0x18001898a  mov     rdi, rdx
0x18001898d  mov     rsi, rcx
0x180018990  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180018997  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x18001899c  mov     [rbp+57h+var_40], 7
0x1800189a4  mov     [rbp+57h+var_48], 0
0x1800189ac  xor     eax, eax
0x1800189ae  mov     [rbp+57h+var_58], ax
0x1800189b2  mov     [rbp+57h+var_D0], eax
0x1800189b5  xorps   xmm0, xmm0
0x1800189b8  movups  [rbp+57h+var_B8], xmm0
0x1800189bc  movups  [rbp+57h+var_A8], xmm0
0x1800189c0  mov     [rbp+57h+var_98], rax
0x1800189c4  xorps   xmm1, xmm1
0x1800189c7  movups  xmmword ptr [rbp+57h+SourceString], xmm1
0x1800189cb  movups  [rbp+57h+var_80], xmm1
0x1800189cf  mov     [rbp+57h+var_70], rax
0x1800189d3  lea     r13d, [rax+1]
0x1800189d7  test    rcx, rcx
0x1800189da  jz      loc_180018AE3
0x1800189e0  mov     rax, [rcx]
0x1800189e3  test    rax, rax
0x1800189e6  jz      loc_180018AE3
0x1800189ec  lea     r9, [rbp+57h+var_B8]
0x1800189f0  lea     r8, [rbp+57h+var_D0]
0x1800189f4  lea     rdx, aClientcomputer; "ClientComputer"
0x1800189fb  mov     rax, [rax+88h]
0x180018a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a07  mov     ebx, eax
0x180018a09  test    eax, eax
0x180018a0b  jnz     short loc_180018A30
0x180018a0d  cmp     [rbp+57h+var_D0], 0Dh
0x180018a11  jnz     short loc_180018A30
0x180018a13  xor     r14b, r14b
0x180018a16  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180018a1a  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180018a1f  mov     r8, rax
0x180018a22  mov     rdx, rcx
0x180018a25  lea     rcx, [rbp+57h+var_58]
0x180018a29  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180018a2e  jmp     short loc_180018A40
0x180018a30  mov     r14b, r13b
0x180018a33  cmp     eax, 6
0x180018a36  jz      short loc_180018A40
0x180018a38  test    ebx, ebx
0x180018a3a  jnz     loc_180018AE8
0x180018a40  mov     rax, [rsi]
0x180018a43  test    rax, rax
0x180018a46  jz      loc_180018AE3
0x180018a4c  mov     r12b, r13b
0x180018a4f  xor     r15b, r15b
0x180018a52  lea     r9, [rbp+57h+SourceString]
0x180018a56  lea     r8, [rbp+57h+var_D0]
0x180018a5a  lea     rdx, aStateid; "StateId"
0x180018a61  mov     rcx, rsi
0x180018a64  mov     rax, [rax+88h]
0x180018a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a70  mov     ebx, eax
0x180018a72  test    eax, eax
0x180018a74  jnz     short loc_180018AB8
0x180018a76  cmp     [rbp+57h+var_D0], 0Dh
0x180018a7a  jnz     short loc_180018ABF
0x180018a7c  xor     r12b, r12b
0x180018a7f  xorps   xmm0, xmm0
0x180018a82  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180018a86  mov     rdx, [rbp+57h+SourceString]; SourceString
0x180018a8a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180018a8e  call    cs:__imp_RtlInitUnicodeString
0x180018a94  lea     rdx, [rbp+57h+Guid]; Guid
0x180018a98  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x180018a9c  call    cs:__imp_RtlGUIDFromString
0x180018aa2  mov     r15d, eax
0x180018aa5  test    eax, eax
0x180018aa7  cmovs   ebx, r13d
0x180018aab  shr     r15d, 1Fh
0x180018aaf  xor     r15b, r13b
0x180018ab2  test    ebx, ebx
0x180018ab4  jnz     short loc_180018AE8
0x180018ab6  jmp     short loc_180018ABF
0x180018ab8  cmp     ebx, 6
0x180018abb  jnz     short loc_180018AE8
0x180018abd  xor     ebx, ebx
0x180018abf  mov     [rdi+39h], r12b
0x180018ac3  mov     [rdi+3Ah], r14b
0x180018ac7  movups  xmm0, xmmword ptr [rbp+57h+Guid.Data1]
0x180018acb  movdqu  xmmword ptr [rdi+28h], xmm0
0x180018ad0  lea     rcx, [rdi+8]
0x180018ad4  lea     rdx, [rbp+57h+var_58]
0x180018ad8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180018add  mov     [rdi+38h], r15b
0x180018ae1  jmp     short loc_180018AE8
0x180018ae3  mov     ebx, 4
0x180018ae8  xor     r8d, r8d
0x180018aeb  mov     dl, r13b
0x180018aee  lea     rcx, [rbp+57h+var_58]
0x180018af2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018af7  mov     eax, ebx
0x180018af9  mov     rcx, [rbp+57h+var_38]
0x180018afd  xor     rcx, rsp; StackCookie
0x180018b00  call    __security_check_cookie
0x180018b05  mov     rbx, [rsp+100h+arg_10]
0x180018b0d  add     rsp, 0D0h
0x180018b14  pop     r15
0x180018b16  pop     r14
0x180018b18  pop     r13
0x180018b1a  pop     r12
0x180018b1c  pop     rdi
0x180018b1d  pop     rsi
0x180018b1e  pop     rbp
0x180018b1f  retn
```
