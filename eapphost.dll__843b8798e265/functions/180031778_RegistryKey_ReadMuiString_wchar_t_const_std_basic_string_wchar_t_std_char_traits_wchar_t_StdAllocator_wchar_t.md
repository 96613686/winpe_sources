# RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)

- ea: `0x180031778`
- end: `0x1800318c5`
- name: `?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `333`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001acdc`
- `0x18001b14c`
- `0x18001bc10`
- `0x18001c1e4`

## callees

- `0x180002af0`
- `0x180007564`
- `0x18001cf5c`
- `0x180030c84`
- `0x180030f54`
- `0x180031778`
- `0x1800318cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180031813`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180031813`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryKey::ReadMuiString(HKEY *a1, const WCHAR *a2, __int64 a3)
{
  DWORD v6; // eax
  void *v7; // rdi
  DWORD v8; // ebx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR pszOutBuf[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v15; // [rsp+70h] [rbp-90h] BYREF
  __int64 v16; // [rsp+270h] [rbp+170h]

  pszOutBuf[0] = (LPWSTR)&v15;
  v6 = 512;
  pszOutBuf[1] = (LPWSTR)512;
  v16 = 0;
  v7 = 0;
  v13[0] = 0;
  v13[1] = 0;
  pcbData = 512;
  v8 = 0;
  while ( 1 )
  {
    PodVector<unsigned char,-1>::Reserve(pszOutBuf, v6);
    v9 = RegLoadMUIStringW(*a1, a2, pszOutBuf[0], v8, &pcbData, 0, 0);
    if ( !v9 )
      break;
    if ( v9 == 2 )
      goto LABEL_9;
    if ( v9 == 13 )
    {
      v10 = 2;
      goto LABEL_12;
    }
    if ( v9 != 234 )
    {
LABEL_9:
      v10 = 1;
      goto LABEL_12;
    }
    v8 = pcbData;
    if ( pcbData > 0xFFF )
    {
      v10 = 4;
      goto LABEL_12;
    }
    v6 = pcbData;
  }
  TempBuffer<0>::Assign((__int64)v13, pcbData, pszOutBuf[0]);
  v7 = (void *)v13[0];
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(a3, v13[0]);
  v10 = 0;
LABEL_12:
  HeapAllocator::Free(v7);
  TempBuffer<520>::Destroy(pszOutBuf);
  return v10;
}

```

## disassembly

```asm
0x180031778  mov     [rsp-8+arg_18], rbx
0x18003177d  push    rbp
0x18003177e  push    rsi
0x18003177f  push    rdi
0x180031780  push    r14
0x180031782  push    r15
0x180031784  lea     rbp, [rsp-190h]
0x18003178c  sub     rsp, 290h
0x180031793  mov     rax, cs:__security_cookie
0x18003179a  xor     rax, rsp
0x18003179d  mov     [rbp+1B0h+var_30], rax
0x1800317a4  mov     rsi, r8
0x1800317a7  mov     r15, rdx
0x1800317aa  mov     r14, rcx
0x1800317ad  lea     rax, [rsp+2B0h+var_240]
0x1800317b2  mov     [rsp+2B0h+pszOutBuf], rax
0x1800317b7  mov     eax, 200h
0x1800317bc  mov     [rsp+2B0h+var_248], rax
0x1800317c1  mov     [rbp+1B0h+var_40], 0
0x1800317cc  xor     edi, edi
0x1800317ce  mov     [rsp+2B0h+var_268], rdi
0x1800317d3  mov     [rsp+2B0h+var_260], rdi
0x1800317d8  mov     [rsp+2B0h+var_270], eax
0x1800317dc  xor     ebx, ebx
0x1800317de  mov     edx, eax
0x1800317e0  lea     rcx, [rsp+2B0h+pszOutBuf]
0x1800317e5  call    ?Reserve@?$PodVector@E$0?0@@QEAAX_K@Z; PodVector<uchar,-1>::Reserve(unsigned __int64)
0x1800317ea  mov     [rsp+2B0h+pszDirectory], 0; pszDirectory
0x1800317f3  mov     [rsp+2B0h+Flags], 0; Flags
0x1800317fb  lea     rax, [rsp+2B0h+var_270]
0x180031800  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180031805  mov     r9d, ebx; cbOutBuf
0x180031808  mov     r8, [rsp+2B0h+pszOutBuf]; pszOutBuf
0x18003180d  mov     rdx, r15; pszValue
0x180031810  mov     rcx, [r14]; hKey
0x180031813  call    cs:__imp_RegLoadMUIStringW
0x18003181a  nop     dword ptr [rax+rax+00h]
0x18003181f  test    eax, eax
0x180031821  jz      short loc_180031859
0x180031823  cmp     eax, 2
0x180031826  jz      short loc_18003184B
0x180031828  cmp     eax, 0Dh
0x18003182b  jz      short loc_180031852
0x18003182d  cmp     eax, 0EAh
0x180031832  jnz     short loc_18003184B
0x180031834  mov     ebx, [rsp+2B0h+var_270]
0x180031838  cmp     ebx, 0FFFh
0x18003183e  ja      short loc_180031844
0x180031840  mov     eax, ebx
0x180031842  jmp     short loc_1800317DE
0x180031844  mov     ebx, 4
0x180031849  jmp     short loc_180031889
0x18003184b  mov     ebx, 1
0x180031850  jmp     short loc_180031889
0x180031852  mov     ebx, 2
0x180031857  jmp     short loc_180031889
0x180031859  mov     edx, [rsp+2B0h+var_270]
0x18003185d  mov     r8, [rsp+2B0h+pszOutBuf]
0x180031862  lea     rcx, [rsp+2B0h+var_268]
0x180031867  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18003186c  mov     r8, [rsp+2B0h+var_260]
0x180031871  shr     r8, 1
0x180031874  dec     r8
0x180031877  mov     rdi, [rsp+2B0h+var_268]
0x18003187c  mov     rdx, rdi
0x18003187f  mov     rcx, rsi
0x180031882  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x180031887  xor     ebx, ebx
0x180031889  mov     rcx, rdi; void *
0x18003188c  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180031891  nop
0x180031892  lea     rcx, [rsp+2B0h+pszOutBuf]
0x180031897  call    ?Destroy@?$TempBuffer@$0CAI@@@AEAAXXZ; TempBuffer<520>::Destroy(void)
0x18003189c  mov     eax, ebx
0x18003189e  mov     rcx, [rbp+1B0h+var_30]
0x1800318a5  xor     rcx, rsp; StackCookie
0x1800318a8  call    __security_check_cookie
0x1800318ad  mov     rbx, [rsp+2B0h+arg_18]
0x1800318b5  add     rsp, 290h
0x1800318bc  pop     r15
0x1800318be  pop     r14
0x1800318c0  pop     rdi
0x1800318c1  pop     rsi
0x1800318c2  pop     rbp
0x1800318c3  retn
```
