# StateSeparation::SetString(ushort const *,ushort const *,ushort const *)

- ea: `0x140032684`
- end: `0x140032873`
- name: `?SetString@StateSeparation@@QEAAKPEBG00@Z`
- size: `495`
- prototype: `unsigned int(StateSeparation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x140032434`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140013e64`
- `0x140014700`
- `0x1400167fc`
- `0x14002690c`
- `0x140032684`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140032817`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140032817`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall StateSeparation::SetString(
        StateSeparation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  LPCWSTR *v9; // r9
  unsigned __int64 v10; // r8
  _QWORD *v11; // rax
  __int128 v12; // xmm7
  __int128 v13; // xmm6
  __int64 v14; // rax
  const unsigned __int16 *v15; // rcx
  __int64 cbData; // rax
  const WCHAR *v17; // rdx
  unsigned int v18; // ebx
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-90h]
  _OWORD v22[2]; // [rsp+68h] [rbp-80h] BYREF
  char *Src[4]; // [rsp+88h] [rbp-60h] BYREF

  *(_OWORD *)lpSubKey = 0;
  v21 = 0;
  v6 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(StateSeparation **)this;
  std::wstring::_Construct<2,unsigned short const *>((__int64)lpSubKey, this, v6);
  if ( a2 && *a2 )
  {
    if ( (_QWORD)v21 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v9 = lpSubKey;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v9 = (LPCWSTR *)lpSubKey[0];
    std::wstring::wstring(Src, v7, v8, v9, v21);
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v11 = std::wstring::_Append<unsigned short>(Src, a2, v10);
    v22[0] = *(_OWORD *)v11;
    v12 = v22[0];
    v13 = *((_OWORD *)v11 + 1);
    *(_WORD *)v11 = 0;
    v11[2] = 0;
    v11[3] = 7;
    std::wstring::_Tidy_deallocate((char **)lpSubKey);
    *(_OWORD *)lpSubKey = v12;
    v21 = v13;
    v22[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v22[0]) = 0;
    std::wstring::_Tidy_deallocate((char **)v22);
    std::wstring::_Tidy_deallocate(Src);
  }
  if ( !a4 )
    goto LABEL_19;
  v14 = 0x7FFFFFFF;
  v15 = a4;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( v14 )
  {
    cbData = ((2 * (0x7FFFFFFF - v14)) & -(__int64)(v14 != 0)) + 2;
    v17 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v17 = lpSubKey[0];
    v18 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v17, L"imsi", 1u, a4, cbData);
    std::wstring::_Tidy_deallocate((char **)lpSubKey);
    return v18;
  }
  else
  {
LABEL_19:
    std::wstring::_Tidy_deallocate((char **)lpSubKey);
    return 87;
  }
}

```

## disassembly

```asm
0x140032684  mov     rax, rsp
0x140032687  push    rbx
0x140032688  push    rsi
0x140032689  push    rdi
0x14003268a  sub     rsp, 0D0h
0x140032691  movaps  xmmword ptr [rax-28h], xmm6
0x140032695  movaps  xmmword ptr [rax-38h], xmm7
0x140032699  mov     rax, cs:__security_cookie
0x1400326a0  xor     rax, rsp
0x1400326a3  mov     [rsp+0E8h+var_40], rax
0x1400326ab  mov     rdi, r9
0x1400326ae  mov     rbx, rdx
0x1400326b1  xor     esi, esi
0x1400326b3  xorps   xmm0, xmm0
0x1400326b6  movups  xmmword ptr [rsp+0E8h+lpSubKey], xmm0
0x1400326bb  xorps   xmm1, xmm1
0x1400326be  movdqu  [rsp+0E8h+var_90], xmm1
0x1400326c4  mov     r8, [rcx+10h]
0x1400326c8  cmp     qword ptr [rcx+18h], 7
0x1400326cd  jbe     short loc_1400326D2
0x1400326cf  mov     rcx, [rcx]
0x1400326d2  mov     rdx, rcx
0x1400326d5  lea     rcx, [rsp+0E8h+lpSubKey]
0x1400326da  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1400326df  nop
0x1400326e0  test    rbx, rbx
0x1400326e3  jz      loc_1400327B3
0x1400326e9  cmp     [rbx], si
0x1400326ec  jz      loc_1400327B3
0x1400326f2  mov     rcx, qword ptr [rsp+0E8h+var_90]
0x1400326f7  mov     rax, 7FFFFFFFFFFFFFFEh
0x140032701  sub     rax, rcx
0x140032704  cmp     rax, 1
0x140032708  jb      loc_14003286C
0x14003270e  lea     r9, [rsp+0E8h+lpSubKey]
0x140032713  cmp     qword ptr [rsp+0E8h+var_90+8], 7
0x140032719  cmova   r9, [rsp+0E8h+lpSubKey]
0x14003271f  mov     [rsp+0E8h+var_B8], 1
0x140032728  mov     [rsp+0E8h+lpData], rcx
0x14003272d  lea     rcx, [rsp+0E8h+Src]
0x140032735  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14003273a  nop
0x14003273b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003273f  inc     r8
0x140032742  cmp     [rbx+r8*2], si
0x140032747  jnz     short loc_14003273F
0x140032749  mov     rdx, rbx
0x14003274c  lea     rcx, [rsp+0E8h+Src]; Src
0x140032754  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x140032759  movups  xmm7, xmmword ptr [rax]
0x14003275c  movups  [rsp+0E8h+var_80], xmm7
0x140032761  movups  xmm6, xmmword ptr [rax+10h]
0x140032765  mov     [rax], si
0x140032768  mov     [rax+10h], rsi
0x14003276c  mov     qword ptr [rax+18h], 7
0x140032774  lea     rcx, [rsp+0E8h+lpSubKey]
0x140032779  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003277e  movups  xmmword ptr [rsp+0E8h+lpSubKey], xmm7
0x140032783  movups  [rsp+0E8h+var_90], xmm6
0x140032788  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140032790  movdqu  [rsp+0E8h+var_70], xmm0
0x140032796  mov     word ptr [rsp+0E8h+var_80], si
0x14003279b  lea     rcx, [rsp+0E8h+var_80]
0x1400327a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400327a5  nop
0x1400327a6  lea     rcx, [rsp+0E8h+Src]
0x1400327ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400327b3  test    rdi, rdi
0x1400327b6  jz      short loc_14003282C
0x1400327b8  mov     edx, 7FFFFFFFh
0x1400327bd  mov     eax, edx
0x1400327bf  mov     rcx, rdi
0x1400327c2  cmp     [rcx], si
0x1400327c5  jz      short loc_1400327D1
0x1400327c7  add     rcx, 2
0x1400327cb  sub     rax, 1
0x1400327cf  jnz     short loc_1400327C2
0x1400327d1  test    rax, rax
0x1400327d4  jz      short loc_14003282C
0x1400327d6  sub     rdx, rax
0x1400327d9  add     rdx, rdx
0x1400327dc  neg     rax
0x1400327df  sbb     rax, rax
0x1400327e2  and     rax, rdx
0x1400327e5  add     rax, 2
0x1400327e9  lea     rdx, [rsp+0E8h+lpSubKey]
0x1400327ee  cmp     qword ptr [rsp+0E8h+var_90+8], 7
0x1400327f4  cmova   rdx, [rsp+0E8h+lpSubKey]; lpSubKey
0x1400327fa  mov     [rsp+0E8h+cbData], eax; cbData
0x1400327fe  mov     [rsp+0E8h+lpData], rdi; lpData
0x140032803  mov     r9d, 1; dwType
0x140032809  lea     r8, ?strImsi@ESIMPM@@3QBGB; "imsi"
0x140032810  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140032817  call    cs:__imp_RegSetKeyValueW
0x14003281d  mov     ebx, eax
0x14003281f  lea     rcx, [rsp+0E8h+lpSubKey]
0x140032824  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032829  nop
0x14003282a  jmp     short loc_140032841
0x14003282c  lea     rcx, [rsp+0E8h+lpSubKey]
0x140032831  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032836  mov     eax, 57h ; 'W'
0x14003283b  jmp     short loc_140032843
0x14003283d  mov     ebx, [rsp+0E8h+var_A8]
0x140032841  mov     eax, ebx
0x140032843  mov     rcx, [rsp+0E8h+var_40]
0x14003284b  xor     rcx, rsp; StackCookie
0x14003284e  call    __security_check_cookie
0x140032853  lea     r11, [rsp+0E8h+var_18]
0x14003285b  movaps  xmm6, xmmword ptr [r11-10h]
0x140032860  movaps  xmm7, xmmword ptr [r11-20h]
0x140032865  mov     rsp, r11
0x140032868  pop     rdi
0x140032869  pop     rsi
0x14003286a  pop     rbx
0x14003286b  retn
0x14003286c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
