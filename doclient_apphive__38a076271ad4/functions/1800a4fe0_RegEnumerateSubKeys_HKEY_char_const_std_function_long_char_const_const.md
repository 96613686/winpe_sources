# RegEnumerateSubKeys(HKEY__ *,char const *,std::function<long (char const *)> const &)

- ea: `0x1800a4fe0`
- end: `0x1800a521c`
- name: `?RegEnumerateSubKeys@@YAXPEAUHKEY__@@PEBDAEBV?$function@$$A6AJPEBD@Z@std@@@Z`
- size: `572`
- prototype: `__int64 __fastcall(HKEY hKey, LPCSTR lpSubKey)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180031fe8`
- `0x180096370`
- `0x18009fbf0`

## callees

- `0x18000d228`
- `0x1800195e8`
- `0x1800196f0`
- `0x1800a1f08`
- `0x1800a4fe0`
- `0x1800a5558`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x1800a51bd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x1800a51bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a51d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a51d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a5050`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a5050`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x1800a5082`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x1800a5082`

## string_xrefs

- `0x1800a50d8`: `Failed enumerating key: %s; will be deleted shortly`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegEnumerateSubKeys(HKEY hKey, LPCSTR lpSubKey, __int64 a3)
{
  _QWORD *v6; // rax
  LSTATUS v7; // eax
  DWORD v8; // r14d
  signed int v9; // ecx
  LSTATUS v10; // eax
  signed int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rsi
  _OWORD *v15; // rdi
  __int64 v16; // r8
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  _QWORD *i; // rbx
  const CHAR *v20; // rdx
  CHAR *v22; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Name[272]; // [rsp+60h] [rbp-A0h] BYREF

  v24 = 0;
  v6 = operator new(0x30u);
  *v6 = v6;
  v6[1] = v6;
  *(_QWORD *)&v24 = v6;
  hKeya = 0;
  v7 = RegOpenKeyExA(hKey, lpSubKey, 0, 8u, &hKeya);
  v8 = 0;
  v9 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    v9 = v7;
  if ( v9 >= 0 )
  {
    do
    {
      v10 = RegEnumKeyA(hKeya, v8, Name, 0x104u);
      v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        v11 = v10;
      if ( v11 >= 0 )
      {
        v22 = Name;
        v12 = *(_QWORD *)(a3 + 56);
        if ( !v12 )
          std::_Xbad_function_call();
        v13 = (*(__int64 (__fastcall **)(__int64, CHAR **))(*(_QWORD *)v12 + 16LL))(v12, &v22);
        if ( v13 < 0 )
        {
          LogResult(4u, "RegEnumerateSubKeys", 0xB6u, v13, "Failed enumerating key: %s; will be deleted shortly", Name);
          v14 = v24;
          if ( *((_QWORD *)&v24 + 1) == 0x555555555555555LL )
            std::_Xlength_error("list too long");
          v15 = operator new(0x30u);
          v15[1] = 0;
          *((_QWORD *)v15 + 4) = 0;
          *((_QWORD *)v15 + 5) = 0;
          v16 = -1;
          do
            ++v16;
          while ( Name[v16] );
          std::string::_Construct<1,char const *>(v15 + 1, Name);
          ++*((_QWORD *)&v24 + 1);
          v17 = *(_QWORD **)(v14 + 8);
          *(_QWORD *)v15 = v14;
          *((_QWORD *)v15 + 1) = v17;
          *(_QWORD *)(v14 + 8) = v15;
          *v17 = v15;
        }
      }
      ++v8;
    }
    while ( v11 >= 0 );
  }
  v18 = (_QWORD *)v24;
  for ( i = *(_QWORD **)v24; i != v18; i = (_QWORD *)*i )
  {
    v20 = (const CHAR *)(i + 2);
    if ( i[5] > 0xFu )
      v20 = *(const CHAR **)v20;
    RegDeleteTreeA(hKeya, v20);
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return std::list<std::string>::~list<std::string>(&v24);
}

```

## disassembly

```asm
0x1800a4fe0  mov     [rsp-8+arg_18], rbx
0x1800a4fe5  push    rbp
0x1800a4fe6  push    rsi
0x1800a4fe7  push    rdi
0x1800a4fe8  push    r14
0x1800a4fea  push    r15
0x1800a4fec  lea     rbp, [rsp-80h]
0x1800a4ff1  sub     rsp, 180h
0x1800a4ff8  mov     rax, cs:__security_cookie
0x1800a4fff  xor     rax, rsp
0x1800a5002  mov     [rbp+0A0h+var_30], rax
0x1800a5006  mov     r15, r8
0x1800a5009  mov     rdi, rdx
0x1800a500c  mov     rbx, rcx
0x1800a500f  xorps   xmm1, xmm1
0x1800a5012  movdqu  [rsp+1A0h+var_150], xmm1
0x1800a5018  mov     ecx, 30h ; '0'; Size
0x1800a501d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a5022  mov     [rax], rax
0x1800a5025  mov     [rax+8], rax
0x1800a5029  mov     qword ptr [rsp+1A0h+var_150], rax
0x1800a502e  mov     [rsp+1A0h+hKey], 0
0x1800a5037  lea     rax, [rsp+1A0h+hKey]
0x1800a503c  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800a5041  mov     r9d, 8; samDesired
0x1800a5047  xor     r8d, r8d; ulOptions
0x1800a504a  mov     rdx, rdi; lpSubKey
0x1800a504d  mov     rcx, rbx; hKey
0x1800a5050  call    cs:__imp_RegOpenKeyExA
0x1800a5056  xor     r14d, r14d
0x1800a5059  movzx   ecx, ax
0x1800a505c  or      ecx, 80070000h
0x1800a5062  test    eax, eax
0x1800a5064  cmovle  ecx, eax
0x1800a5067  test    ecx, ecx
0x1800a5069  js      loc_1800A51A0
0x1800a506f  mov     r9d, 104h; cchName
0x1800a5075  lea     r8, [rsp+1A0h+Name]; lpName
0x1800a507a  mov     edx, r14d; dwIndex
0x1800a507d  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800a5082  call    cs:__imp_RegEnumKeyA
0x1800a5088  movzx   ebx, ax
0x1800a508b  or      ebx, 80070000h
0x1800a5091  test    eax, eax
0x1800a5093  cmovle  ebx, eax
0x1800a5096  test    ebx, ebx
0x1800a5098  js      loc_1800A5195
0x1800a509e  lea     rax, [rsp+1A0h+Name]
0x1800a50a3  mov     [rsp+1A0h+var_160], rax
0x1800a50a8  mov     rcx, [r15+38h]
0x1800a50ac  test    rcx, rcx
0x1800a50af  jz      loc_1800A5209
0x1800a50b5  mov     rax, [rcx]
0x1800a50b8  lea     rdx, [rsp+1A0h+var_160]
0x1800a50bd  mov     rax, [rax+10h]
0x1800a50c1  call    _guard_dispatch_icall
0x1800a50c6  test    eax, eax
0x1800a50c8  jns     loc_1800A5195
0x1800a50ce  lea     rcx, [rsp+1A0h+Name]
0x1800a50d3  mov     [rsp+1A0h+var_178], rcx
0x1800a50d8  lea     rcx, aFailedEnumerat; "Failed enumerating key: %s; will be del"...
0x1800a50df  mov     [rsp+1A0h+phkResult], rcx; char *
0x1800a50e4  mov     r9d, eax; int
0x1800a50e7  mov     r8d, 0B6h; unsigned int
0x1800a50ed  lea     rdx, aRegenumeratesu; "RegEnumerateSubKeys"
0x1800a50f4  mov     ecx, 4; unsigned __int8
0x1800a50f9  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800a50fe  mov     rsi, qword ptr [rsp+1A0h+var_150]
0x1800a5103  mov     rax, 555555555555555h
0x1800a510d  cmp     qword ptr [rsp+1A0h+var_150+8], rax
0x1800a5112  jz      loc_1800A520F
0x1800a5118  lea     rax, [rsp+1A0h+var_150]
0x1800a511d  mov     [rsp+1A0h+var_170], rax
0x1800a5122  mov     [rsp+1A0h+var_168], 0
0x1800a512b  mov     ecx, 30h ; '0'; Size
0x1800a5130  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a5135  mov     rdi, rax
0x1800a5138  mov     [rsp+1A0h+var_168], rax
0x1800a513d  lea     rcx, [rax+10h]
0x1800a5141  xorps   xmm0, xmm0
0x1800a5144  movups  xmmword ptr [rcx], xmm0
0x1800a5147  mov     qword ptr [rcx+10h], 0
0x1800a514f  mov     qword ptr [rcx+18h], 0
0x1800a5157  lea     rax, [rsp+1A0h+Name]
0x1800a515c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a5160  inc     r8
0x1800a5163  cmp     byte ptr [rax+r8], 0
0x1800a5168  jnz     short loc_1800A5160
0x1800a516a  lea     rdx, [rsp+1A0h+Name]
0x1800a516f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800a5174  nop
0x1800a5175  inc     qword ptr [rsp+1A0h+var_150+8]
0x1800a517a  mov     rax, [rsi+8]
0x1800a517e  mov     [rdi], rsi
0x1800a5181  mov     [rdi+8], rax
0x1800a5185  mov     [rsp+1A0h+var_168], 0
0x1800a518e  mov     [rsi+8], rdi
0x1800a5192  mov     [rax], rdi
0x1800a5195  inc     r14d
0x1800a5198  test    ebx, ebx
0x1800a519a  jns     loc_1800A506F
0x1800a51a0  mov     rdi, qword ptr [rsp+1A0h+var_150]
0x1800a51a5  mov     rbx, [rdi]
0x1800a51a8  jmp     short loc_1800A51C6
0x1800a51aa  lea     rdx, [rbx+10h]
0x1800a51ae  cmp     qword ptr [rbx+28h], 0Fh
0x1800a51b3  jbe     short loc_1800A51B8
0x1800a51b5  mov     rdx, [rdx]; lpSubKey
0x1800a51b8  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800a51bd  call    cs:__imp_RegDeleteTreeA
0x1800a51c3  mov     rbx, [rbx]
0x1800a51c6  cmp     rbx, rdi
0x1800a51c9  jnz     short loc_1800A51AA
0x1800a51cb  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800a51d0  test    rcx, rcx
0x1800a51d3  jz      short loc_1800A51DC
0x1800a51d5  call    cs:__imp_RegCloseKey
0x1800a51db  nop
0x1800a51dc  lea     rcx, [rsp+1A0h+var_150]
0x1800a51e1  call    ??1?$list@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ; std::list<std::string>::~list<std::string>(void)
0x1800a51e6  mov     rcx, [rbp+0A0h+var_30]
0x1800a51ea  xor     rcx, rsp; StackCookie
0x1800a51ed  call    __security_check_cookie
0x1800a51f2  mov     rbx, [rsp+1A0h+arg_18]
0x1800a51fa  add     rsp, 180h
0x1800a5201  pop     r15
0x1800a5203  pop     r14
0x1800a5205  pop     rdi
0x1800a5206  pop     rsi
0x1800a5207  pop     rbp
0x1800a5208  retn
0x1800a5209  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800a520f  lea     rcx, aListTooLong; "list too long"
0x1800a5216  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
