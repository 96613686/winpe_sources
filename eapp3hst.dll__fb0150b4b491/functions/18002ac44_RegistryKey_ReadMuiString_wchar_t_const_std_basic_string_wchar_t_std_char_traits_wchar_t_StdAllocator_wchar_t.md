# RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)

- ea: `0x18002ac44`
- end: `0x18002adf0`
- name: `?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002bc04`
- `0x18002c06c`
- `0x18002ca50`
- `0x18002d040`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x1800126f8`
- `0x1800216dc`
- `0x18002ac44`
- `0x18002adf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18002acdf`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18002acdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryKey::ReadMuiString(HKEY *a1, const WCHAR *a2, __int64 a3)
{
  DWORD v6; // eax
  DWORD v7; // edi
  LSTATUS v8; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  void *v11[3]; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR pszOutBuf[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[512]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v14; // [rsp+270h] [rbp+170h]

  pszOutBuf[0] = (LPWSTR)v13;
  v6 = 512;
  pszOutBuf[1] = (LPWSTR)512;
  v14 = 0;
  v11[0] = 0;
  v11[1] = 0;
  pcbData = 512;
  v7 = 0;
  while ( 1 )
  {
    PodVector<unsigned char,-1>::Reserve(pszOutBuf, v6);
    v8 = RegLoadMUIStringW(*a1, a2, pszOutBuf[0], v7, &pcbData, 0, 0);
    if ( !v8 )
      break;
    if ( v8 == 2 )
      goto LABEL_14;
    if ( v8 == 13 )
    {
      HeapAllocator::Free(0);
      if ( (_BYTE *)pszOutBuf[0] != v13 )
        HeapAllocator::Free(pszOutBuf[0]);
      return 2;
    }
    if ( v8 != 234 )
    {
LABEL_14:
      HeapAllocator::Free(0);
      if ( (_BYTE *)pszOutBuf[0] != v13 )
        HeapAllocator::Free(pszOutBuf[0]);
      return 1;
    }
    v7 = pcbData;
    if ( pcbData > 0xFFF )
    {
      HeapAllocator::Free(0);
      if ( (_BYTE *)pszOutBuf[0] != v13 )
        HeapAllocator::Free(pszOutBuf[0]);
      return 4;
    }
    v6 = pcbData;
  }
  TempBuffer<0>::Assign((__int64)v11, pcbData, pszOutBuf[0]);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(a3, v11[0]);
  HeapAllocator::Free(v11[0]);
  if ( (_BYTE *)pszOutBuf[0] != v13 )
    HeapAllocator::Free(pszOutBuf[0]);
  return 0;
}

```

## disassembly

```asm
0x18002ac44  mov     [rsp-8+arg_18], rbx
0x18002ac49  push    rbp
0x18002ac4a  push    rsi
0x18002ac4b  push    rdi
0x18002ac4c  push    r14
0x18002ac4e  push    r15
0x18002ac50  lea     rbp, [rsp-190h]
0x18002ac58  sub     rsp, 290h
0x18002ac5f  mov     rax, cs:__security_cookie
0x18002ac66  xor     rax, rsp
0x18002ac69  mov     [rbp+1B0h+var_30], rax
0x18002ac70  mov     rsi, r8
0x18002ac73  mov     r15, rdx
0x18002ac76  mov     r14, rcx
0x18002ac79  lea     rax, [rsp+2B0h+var_240]
0x18002ac7e  mov     [rsp+2B0h+pszOutBuf], rax
0x18002ac83  mov     eax, 200h
0x18002ac88  mov     [rsp+2B0h+var_248], rax
0x18002ac8d  mov     [rbp+1B0h+var_40], 0
0x18002ac98  xor     ebx, ebx
0x18002ac9a  mov     [rsp+2B0h+var_268], rbx
0x18002ac9f  mov     [rsp+2B0h+var_260], rbx
0x18002aca4  mov     [rsp+2B0h+var_270], eax
0x18002aca8  xor     edi, edi
0x18002acaa  mov     edx, eax
0x18002acac  lea     rcx, [rsp+2B0h+pszOutBuf]
0x18002acb1  call    ?Reserve@?$PodVector@E$0?0@@QEAAX_K@Z; PodVector<uchar,-1>::Reserve(unsigned __int64)
0x18002acb6  mov     [rsp+2B0h+pszDirectory], 0; pszDirectory
0x18002acbf  mov     [rsp+2B0h+Flags], 0; Flags
0x18002acc7  lea     rax, [rsp+2B0h+var_270]
0x18002accc  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18002acd1  mov     r9d, edi; cbOutBuf
0x18002acd4  mov     r8, [rsp+2B0h+pszOutBuf]; pszOutBuf
0x18002acd9  mov     rdx, r15; pszValue
0x18002acdc  mov     rcx, [r14]; hKey
0x18002acdf  call    cs:__imp_RegLoadMUIStringW
0x18002ace5  test    eax, eax
0x18002ace7  jz      loc_18002AD7D
0x18002aced  cmp     eax, 2
0x18002acf0  jz      short loc_18002AD59
0x18002acf2  cmp     eax, 0Dh
0x18002acf5  jz      short loc_18002AD35
0x18002acf7  cmp     eax, 0EAh
0x18002acfc  jnz     short loc_18002AD59
0x18002acfe  mov     edi, [rsp+2B0h+var_270]
0x18002ad02  cmp     edi, 0FFFh
0x18002ad08  ja      short loc_18002AD0E
0x18002ad0a  mov     eax, edi
0x18002ad0c  jmp     short loc_18002ACAA
0x18002ad0e  mov     rcx, rbx; void *
0x18002ad11  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ad16  nop
0x18002ad17  lea     rax, [rsp+2B0h+var_240]
0x18002ad1c  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x18002ad21  cmp     rcx, rax
0x18002ad24  jz      short loc_18002AD2B
0x18002ad26  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ad2b  mov     eax, 4
0x18002ad30  jmp     loc_18002ADCA
0x18002ad35  mov     rcx, rbx; void *
0x18002ad38  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ad3d  nop
0x18002ad3e  lea     rdx, [rsp+2B0h+var_240]
0x18002ad43  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x18002ad48  cmp     rcx, rdx
0x18002ad4b  jz      short loc_18002AD52
0x18002ad4d  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ad52  mov     eax, 2
0x18002ad57  jmp     short loc_18002ADCA
0x18002ad59  mov     rcx, rbx; void *
0x18002ad5c  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ad61  nop
0x18002ad62  lea     rax, [rsp+2B0h+var_240]
0x18002ad67  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x18002ad6c  cmp     rcx, rax
0x18002ad6f  jz      short loc_18002AD76
0x18002ad71  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ad76  mov     eax, 1
0x18002ad7b  jmp     short loc_18002ADCA
0x18002ad7d  mov     edx, [rsp+2B0h+var_270]
0x18002ad81  mov     r8, [rsp+2B0h+pszOutBuf]
0x18002ad86  lea     rcx, [rsp+2B0h+var_268]
0x18002ad8b  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18002ad90  mov     r8, [rsp+2B0h+var_260]
0x18002ad95  shr     r8, 1
0x18002ad98  dec     r8
0x18002ad9b  mov     rdx, [rsp+2B0h+var_268]
0x18002ada0  mov     rcx, rsi
0x18002ada3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18002ada8  nop
0x18002ada9  mov     rcx, [rsp+2B0h+var_268]; void *
0x18002adae  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002adb3  nop
0x18002adb4  lea     rax, [rsp+2B0h+var_240]
0x18002adb9  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x18002adbe  cmp     rcx, rax
0x18002adc1  jz      short loc_18002ADC8
0x18002adc3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002adc8  xor     eax, eax
0x18002adca  mov     rcx, [rbp+1B0h+var_30]
0x18002add1  xor     rcx, rsp; StackCookie
0x18002add4  call    __security_check_cookie
0x18002add9  mov     rbx, [rsp+2B0h+arg_18]
0x18002ade1  add     rsp, 290h
0x18002ade8  pop     r15
0x18002adea  pop     r14
0x18002adec  pop     rdi
0x18002aded  pop     rsi
0x18002adee  pop     rbp
0x18002adef  retn
```
