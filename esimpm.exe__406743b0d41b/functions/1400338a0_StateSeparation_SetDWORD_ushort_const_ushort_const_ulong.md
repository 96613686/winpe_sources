# StateSeparation::SetDWORD(ushort const *,ushort const *,ulong)

- ea: `0x1400338a0`
- end: `0x140033a36`
- name: `?SetDWORD@StateSeparation@@QEAAKPEBG0K@Z`
- size: `406`
- prototype: `unsigned int __fastcall(StateSeparation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140033a3c`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140013e64`
- `0x140014700`
- `0x1400167fc`
- `0x14002690c`
- `0x1400338a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400339ed`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400339ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateSeparation::SetDWORD(
        StateSeparation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  LPCWSTR *v7; // r9
  _QWORD *v8; // rax
  __int128 v9; // xmm7
  __int128 v10; // xmm6
  const WCHAR *v11; // rdx
  unsigned int v12; // ebx
  _DWORD Data[4]; // [rsp+40h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-98h] BYREF
  __int128 v16; // [rsp+60h] [rbp-88h]
  _OWORD v17[2]; // [rsp+70h] [rbp-78h] BYREF
  char *Src[4]; // [rsp+90h] [rbp-58h] BYREF

  Data[0] = a4;
  *(_OWORD *)lpSubKey = 0;
  v16 = 0;
  v4 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(StateSeparation **)this;
  try
  {
    std::wstring::_Construct<2,unsigned short const *>((__int64)lpSubKey, this, v4);
    if ( (_QWORD)v16 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v7 = lpSubKey;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      v7 = (LPCWSTR *)lpSubKey[0];
    std::wstring::wstring(Src, v5, v6, v7, v16);
    v8 = std::wstring::_Append<unsigned short>(Src, L"SIUFTriggerData", 0xFu);
    v17[0] = *(_OWORD *)v8;
    v9 = v17[0];
    v10 = *((_OWORD *)v8 + 1);
    *(_WORD *)v8 = 0;
    v8[2] = 0;
    v8[3] = 7;
    std::wstring::_Tidy_deallocate((char **)lpSubKey);
    *(_OWORD *)lpSubKey = v9;
    v16 = v10;
    v17[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17[0]) = 0;
    std::wstring::_Tidy_deallocate((char **)v17);
    std::wstring::_Tidy_deallocate(Src);
    v11 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      v11 = lpSubKey[0];
    v12 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v11, L"LastShownSIUF", 4u, Data, 4u);
    std::wstring::_Tidy_deallocate((char **)lpSubKey);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v12;
}

```

## disassembly

```asm
0x1400338a0  mov     rax, rsp
0x1400338a3  push    rbx
0x1400338a4  sub     rsp, 0E0h
0x1400338ab  movaps  xmmword ptr [rax-18h], xmm6
0x1400338af  movaps  xmmword ptr [rax-28h], xmm7
0x1400338b3  mov     rax, cs:__security_cookie
0x1400338ba  xor     rax, rsp
0x1400338bd  mov     [rsp+0E8h+var_38], rax
0x1400338c5  mov     [rsp+0E8h+Data], r9d
0x1400338ca  xorps   xmm0, xmm0
0x1400338cd  movups  xmmword ptr [rsp+0E8h+lpSubKey], xmm0
0x1400338d2  xorps   xmm1, xmm1
0x1400338d5  movdqu  [rsp+0E8h+var_88], xmm1
0x1400338db  mov     r8, [rcx+10h]
0x1400338df  mov     ebx, 7
0x1400338e4  cmp     [rcx+18h], rbx
0x1400338e8  jbe     short loc_1400338ED
0x1400338ea  mov     rcx, [rcx]
0x1400338ed  mov     rdx, rcx
0x1400338f0  lea     rcx, [rsp+0E8h+lpSubKey]
0x1400338f5  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1400338fa  nop
0x1400338fb  mov     rcx, qword ptr [rsp+0E8h+var_88]
0x140033900  mov     rax, 7FFFFFFFFFFFFFFEh
0x14003390a  sub     rax, rcx
0x14003390d  cmp     rax, 1
0x140033911  jb      loc_140033A2F
0x140033917  lea     r9, [rsp+0E8h+lpSubKey]
0x14003391c  cmp     qword ptr [rsp+0E8h+var_88+8], rbx
0x140033921  cmova   r9, [rsp+0E8h+lpSubKey]
0x140033927  mov     [rsp+0E8h+var_B8], 1
0x140033930  mov     [rsp+0E8h+lpData], rcx
0x140033935  lea     rcx, [rsp+0E8h+Src]
0x14003393d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140033942  nop
0x140033943  mov     r8d, 0Fh
0x140033949  lea     rdx, aSiuftriggerdat; "SIUFTriggerData"
0x140033950  lea     rcx, [rsp+0E8h+Src]; Src
0x140033958  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14003395d  movups  xmm7, xmmword ptr [rax]
0x140033960  movups  [rsp+0E8h+var_78], xmm7
0x140033965  movups  xmm6, xmmword ptr [rax+10h]
0x140033969  xor     ecx, ecx
0x14003396b  mov     [rax], cx
0x14003396e  mov     [rax+10h], rcx
0x140033972  mov     [rax+18h], rbx
0x140033976  lea     rcx, [rsp+0E8h+lpSubKey]
0x14003397b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140033980  movups  xmmword ptr [rsp+0E8h+lpSubKey], xmm7
0x140033985  movups  [rsp+0E8h+var_88], xmm6
0x14003398a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140033992  movdqu  [rsp+0E8h+var_68], xmm0
0x14003399b  xor     eax, eax
0x14003399d  mov     word ptr [rsp+0E8h+var_78], ax
0x1400339a2  lea     rcx, [rsp+0E8h+var_78]
0x1400339a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400339ac  nop
0x1400339ad  lea     rcx, [rsp+0E8h+Src]
0x1400339b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400339ba  lea     rdx, [rsp+0E8h+lpSubKey]
0x1400339bf  cmp     qword ptr [rsp+0E8h+var_88+8], rbx
0x1400339c4  cmova   rdx, [rsp+0E8h+lpSubKey]; lpSubKey
0x1400339ca  mov     r9d, 4; dwType
0x1400339d0  mov     [rsp+0E8h+cbData], r9d; cbData
0x1400339d5  lea     rax, [rsp+0E8h+Data]
0x1400339da  mov     [rsp+0E8h+lpData], rax; lpData
0x1400339df  lea     r8, ValueName; "LastShownSIUF"
0x1400339e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400339ed  call    cs:__imp_RegSetKeyValueW
0x1400339f3  mov     ebx, eax
0x1400339f5  lea     rcx, [rsp+0E8h+lpSubKey]
0x1400339fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400339ff  nop
0x140033a00  jmp     short loc_140033A06
0x140033a02  mov     ebx, [rsp+0E8h+Data]
0x140033a06  mov     eax, ebx
0x140033a08  mov     rcx, [rsp+0E8h+var_38]
0x140033a10  xor     rcx, rsp; StackCookie
0x140033a13  call    __security_check_cookie
0x140033a18  lea     r11, [rsp+0E8h+var_8]
0x140033a20  movaps  xmm6, xmmword ptr [r11-10h]
0x140033a25  movaps  xmm7, xmmword ptr [r11-20h]
0x140033a2a  mov     rsp, r11
0x140033a2d  pop     rbx
0x140033a2e  retn
0x140033a2f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
