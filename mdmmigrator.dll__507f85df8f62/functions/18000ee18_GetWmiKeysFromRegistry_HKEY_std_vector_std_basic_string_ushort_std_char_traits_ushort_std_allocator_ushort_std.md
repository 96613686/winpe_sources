# GetWmiKeysFromRegistry(HKEY__ *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000ee18`
- end: `0x18000effd`
- name: `?GetWmiKeysFromRegistry@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `485`
- prototype: `LSTATUS __fastcall(HKEY hkey, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180010864`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x1800034f0`
- `0x180006c98`
- `0x180007720`
- `0x180007b38`
- `0x18000cf04`
- `0x18000ee18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000eecc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ef21`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000eecc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ef21`

## pseudocode

```c
LSTATUS __fastcall GetWmiKeysFromRegistry(HKEY hkey, __int64 a2)
{
  LSTATUS ValueW; // ebx
  unsigned int v5; // r15d
  char **v6; // rsi
  char **v7; // r14
  LSTATUS result; // eax
  void *pvData; // rsi
  const struct std::nothrow_t *v10; // rdx
  unsigned __int64 v11; // r8
  _OWORD *v12; // rdx
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  void *v14; // [rsp+48h] [rbp-21h]
  __int128 v15; // [rsp+50h] [rbp-19h] BYREF
  __int128 v16; // [rsp+60h] [rbp-9h]
  WCHAR Value[12]; // [rsp+70h] [rbp+7h] BYREF

  ValueW = 0;
  pcbData = 0;
  v5 = 0;
  v6 = *(char ***)a2;
  v7 = *(char ***)(a2 + 8);
  if ( *(char ***)a2 != v7 )
  {
    do
    {
      std::wstring::~wstring(v6);
      v6 += 4;
    }
    while ( v6 != v7 );
    *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
  }
  while ( !ValueW )
  {
    result = StringCchPrintfW(Value, 0xAu, L"Key%d", v5);
    if ( result < 0 )
      return result;
    pcbData = 0;
    result = RegGetValueW(hkey, 0, Value, 2u, 0, 0, &pcbData);
    if ( result == 2 )
      return 0;
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
    v14 = pvData;
    ValueW = RegGetValueW(hkey, 0, Value, 2u, 0, pvData, &pcbData);
    if ( !ValueW )
    {
      v15 = 0;
      v16 = 0u;
      v11 = -1;
      do
        ++v11;
      while ( *((_WORD *)pvData + v11) );
      std::wstring::_Construct<1,unsigned short const *>(&v15, pvData, v11);
      v12 = *(_OWORD **)(a2 + 8);
      if ( v12 == *(_OWORD **)(a2 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a2, v12, &v15);
      }
      else
      {
        *v12 = v15;
        v12[1] = v16;
        *(_QWORD *)&v16 = 0;
        *((_QWORD *)&v16 + 1) = 7;
        LOWORD(v15) = 0;
        *(_QWORD *)(a2 + 8) += 32LL;
      }
      std::wstring::~wstring((char **)&v15);
    }
    ++v5;
    operator delete(pvData, v10);
    if ( ValueW == 2 )
      return 0;
  }
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return ValueW;
}

```

## disassembly

```asm
0x18000ee18  mov     [rsp-8+arg_10], rbx
0x18000ee1d  push    rbp
0x18000ee1e  push    rsi
0x18000ee1f  push    rdi
0x18000ee20  push    r12
0x18000ee22  push    r13
0x18000ee24  push    r14
0x18000ee26  push    r15
0x18000ee28  lea     rbp, [rsp-27h]
0x18000ee2d  sub     rsp, 90h
0x18000ee34  mov     rax, cs:__security_cookie
0x18000ee3b  xor     rax, rsp
0x18000ee3e  mov     [rbp+57h+var_38], rax
0x18000ee42  mov     rdi, rdx
0x18000ee45  mov     r12, rcx
0x18000ee48  xor     r13d, r13d
0x18000ee4b  mov     ebx, r13d
0x18000ee4e  mov     [rbp+57h+var_80], r13d
0x18000ee52  mov     r15d, r13d
0x18000ee55  mov     rsi, [rdx]
0x18000ee58  mov     r14, [rdx+8]
0x18000ee5c  cmp     rsi, r14
0x18000ee5f  jz      short loc_18000EE79
0x18000ee61  mov     rcx, rsi; void *
0x18000ee64  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ee69  add     rsi, 20h ; ' '
0x18000ee6d  cmp     rsi, r14
0x18000ee70  jnz     short loc_18000EE61
0x18000ee72  mov     rax, [rdi]
0x18000ee75  mov     [rdi+8], rax
0x18000ee79  mov     r14d, 2
0x18000ee7f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ee83  test    ebx, ebx
0x18000ee85  jnz     loc_18000EFC9
0x18000ee8b  mov     r9d, r15d
0x18000ee8e  lea     r8, aKeyD; "Key%d"
0x18000ee95  lea     edx, [rbx+0Ah]; unsigned __int64
0x18000ee98  lea     rcx, [rbp+57h+Value]; unsigned __int16 *
0x18000ee9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eea1  test    eax, eax
0x18000eea3  js      loc_18000EFD6
0x18000eea9  mov     [rbp+57h+var_80], r13d
0x18000eead  lea     rax, [rbp+57h+var_80]
0x18000eeb1  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000eeb6  mov     [rsp+0C0h+pvData], r13; pvData
0x18000eebb  mov     [rsp+0C0h+pdwType], r13; pdwType
0x18000eec0  mov     r9d, r14d; dwFlags
0x18000eec3  lea     r8, [rbp+57h+Value]; lpValue
0x18000eec7  xor     edx, edx; lpSubKey
0x18000eec9  mov     rcx, r12; hkey
0x18000eecc  call    cs:__imp_RegGetValueW
0x18000eed2  cmp     eax, r14d
0x18000eed5  jz      loc_18000EFB9
0x18000eedb  test    eax, eax
0x18000eedd  jnz     loc_18000EFBD
0x18000eee3  mov     ecx, [rbp+57h+var_80]
0x18000eee6  shr     rcx, 1
0x18000eee9  mov     rax, r14
0x18000eeec  mul     rcx
0x18000eeef  cmovb   rax, rsi
0x18000eef3  mov     rcx, rax; unsigned __int64
0x18000eef6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000eefb  mov     rsi, rax
0x18000eefe  mov     [rbp+57h+var_78], rax
0x18000ef02  lea     rax, [rbp+57h+var_80]
0x18000ef06  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000ef0b  mov     [rsp+0C0h+pvData], rsi; pvData
0x18000ef10  mov     [rsp+0C0h+pdwType], r13; pdwType
0x18000ef15  mov     r9d, r14d; dwFlags
0x18000ef18  lea     r8, [rbp+57h+Value]; lpValue
0x18000ef1c  xor     edx, edx; lpSubKey
0x18000ef1e  mov     rcx, r12; hkey
0x18000ef21  call    cs:__imp_RegGetValueW
0x18000ef27  mov     ebx, eax
0x18000ef29  test    eax, eax
0x18000ef2b  jnz     short loc_18000EF9E
0x18000ef2d  xorps   xmm0, xmm0
0x18000ef30  movups  [rbp+57h+var_70], xmm0
0x18000ef34  mov     qword ptr [rbp+57h+var_60], r13
0x18000ef38  mov     qword ptr [rbp+57h+var_60+8], r13
0x18000ef3c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ef40  inc     r8
0x18000ef43  cmp     [rsi+r8*2], r13w
0x18000ef48  jnz     short loc_18000EF40
0x18000ef4a  mov     rdx, rsi
0x18000ef4d  lea     rcx, [rbp+57h+var_70]
0x18000ef51  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ef56  nop
0x18000ef57  mov     rdx, [rdi+8]
0x18000ef5b  cmp     rdx, [rdi+10h]
0x18000ef5f  jz      short loc_18000EF88
0x18000ef61  movups  xmm0, [rbp+57h+var_70]
0x18000ef65  movups  xmmword ptr [rdx], xmm0
0x18000ef68  movups  xmm1, [rbp+57h+var_60]
0x18000ef6c  movups  xmmword ptr [rdx+10h], xmm1
0x18000ef70  mov     qword ptr [rbp+57h+var_60], r13
0x18000ef74  mov     qword ptr [rbp+57h+var_60+8], 7
0x18000ef7c  mov     word ptr [rbp+57h+var_70], r13w
0x18000ef81  add     qword ptr [rdi+8], 20h ; ' '
0x18000ef86  jmp     short loc_18000EF95
0x18000ef88  lea     r8, [rbp+57h+var_70]
0x18000ef8c  mov     rcx, rdi
0x18000ef8f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18000ef94  nop
0x18000ef95  lea     rcx, [rbp+57h+var_70]; void *
0x18000ef99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ef9e  inc     r15d
0x18000efa1  mov     rcx, rsi; void *
0x18000efa4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000efa9  cmp     ebx, r14d
0x18000efac  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000efb3  jnz     loc_18000EE83
0x18000efb9  xor     eax, eax
0x18000efbb  jmp     short loc_18000EFD6
0x18000efbd  jle     short loc_18000EFD6
0x18000efbf  movzx   eax, ax
0x18000efc2  or      eax, 80070000h
0x18000efc7  jmp     short loc_18000EFD6
0x18000efc9  jle     short loc_18000EFD4
0x18000efcb  movzx   ebx, bx
0x18000efce  or      ebx, 80070000h
0x18000efd4  mov     eax, ebx
0x18000efd6  mov     rcx, [rbp+57h+var_38]
0x18000efda  xor     rcx, rsp; StackCookie
0x18000efdd  call    __security_check_cookie
0x18000efe2  mov     rbx, [rsp+0C0h+arg_10]
0x18000efea  add     rsp, 90h
0x18000eff1  pop     r15
0x18000eff3  pop     r14
0x18000eff5  pop     r13
0x18000eff7  pop     r12
0x18000eff9  pop     rdi
0x18000effa  pop     rsi
0x18000effb  pop     rbp
0x18000effc  retn
```
