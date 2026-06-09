# RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)

- ea: `0x180030564`
- end: `0x180030710`
- name: `?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001a2f0`
- `0x18001a758`
- `0x18001b200`
- `0x18001b7cc`

## callees

- `0x180002a90`
- `0x1800072cc`
- `0x18001c4f0`
- `0x18002fd44`
- `0x180030564`
- `0x180030718`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800305ff`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800305ff`

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
0x180030564  mov     [rsp-8+arg_18], rbx
0x180030569  push    rbp
0x18003056a  push    rsi
0x18003056b  push    rdi
0x18003056c  push    r14
0x18003056e  push    r15
0x180030570  lea     rbp, [rsp-190h]
0x180030578  sub     rsp, 290h
0x18003057f  mov     rax, cs:__security_cookie
0x180030586  xor     rax, rsp
0x180030589  mov     [rbp+1B0h+var_30], rax
0x180030590  mov     rsi, r8
0x180030593  mov     r15, rdx
0x180030596  mov     r14, rcx
0x180030599  lea     rax, [rsp+2B0h+var_240]
0x18003059e  mov     [rsp+2B0h+pszOutBuf], rax
0x1800305a3  mov     eax, 200h
0x1800305a8  mov     [rsp+2B0h+var_248], rax
0x1800305ad  mov     [rbp+1B0h+var_40], 0
0x1800305b8  xor     ebx, ebx
0x1800305ba  mov     [rsp+2B0h+var_268], rbx
0x1800305bf  mov     [rsp+2B0h+var_260], rbx
0x1800305c4  mov     [rsp+2B0h+var_270], eax
0x1800305c8  xor     edi, edi
0x1800305ca  mov     edx, eax
0x1800305cc  lea     rcx, [rsp+2B0h+pszOutBuf]
0x1800305d1  call    ?Reserve@?$PodVector@E$0?0@@QEAAX_K@Z; PodVector<uchar,-1>::Reserve(unsigned __int64)
0x1800305d6  mov     [rsp+2B0h+pszDirectory], 0; pszDirectory
0x1800305df  mov     [rsp+2B0h+Flags], 0; Flags
0x1800305e7  lea     rax, [rsp+2B0h+var_270]
0x1800305ec  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800305f1  mov     r9d, edi; cbOutBuf
0x1800305f4  mov     r8, [rsp+2B0h+pszOutBuf]; pszOutBuf
0x1800305f9  mov     rdx, r15; pszValue
0x1800305fc  mov     rcx, [r14]; hKey
0x1800305ff  call    cs:__imp_RegLoadMUIStringW
0x180030605  test    eax, eax
0x180030607  jz      loc_18003069D
0x18003060d  cmp     eax, 2
0x180030610  jz      short loc_180030679
0x180030612  cmp     eax, 0Dh
0x180030615  jz      short loc_180030655
0x180030617  cmp     eax, 0EAh
0x18003061c  jnz     short loc_180030679
0x18003061e  mov     edi, [rsp+2B0h+var_270]
0x180030622  cmp     edi, 0FFFh
0x180030628  ja      short loc_18003062E
0x18003062a  mov     eax, edi
0x18003062c  jmp     short loc_1800305CA
0x18003062e  mov     rcx, rbx; void *
0x180030631  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030636  nop
0x180030637  lea     rax, [rsp+2B0h+var_240]
0x18003063c  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x180030641  cmp     rcx, rax
0x180030644  jz      short loc_18003064B
0x180030646  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18003064b  mov     eax, 4
0x180030650  jmp     loc_1800306EA
0x180030655  mov     rcx, rbx; void *
0x180030658  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18003065d  nop
0x18003065e  lea     rdx, [rsp+2B0h+var_240]
0x180030663  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x180030668  cmp     rcx, rdx
0x18003066b  jz      short loc_180030672
0x18003066d  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030672  mov     eax, 2
0x180030677  jmp     short loc_1800306EA
0x180030679  mov     rcx, rbx; void *
0x18003067c  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030681  nop
0x180030682  lea     rax, [rsp+2B0h+var_240]
0x180030687  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x18003068c  cmp     rcx, rax
0x18003068f  jz      short loc_180030696
0x180030691  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030696  mov     eax, 1
0x18003069b  jmp     short loc_1800306EA
0x18003069d  mov     edx, [rsp+2B0h+var_270]
0x1800306a1  mov     r8, [rsp+2B0h+pszOutBuf]
0x1800306a6  lea     rcx, [rsp+2B0h+var_268]
0x1800306ab  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800306b0  mov     r8, [rsp+2B0h+var_260]
0x1800306b5  shr     r8, 1
0x1800306b8  dec     r8
0x1800306bb  mov     rdx, [rsp+2B0h+var_268]
0x1800306c0  mov     rcx, rsi
0x1800306c3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x1800306c8  nop
0x1800306c9  mov     rcx, [rsp+2B0h+var_268]; void *
0x1800306ce  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800306d3  nop
0x1800306d4  lea     rax, [rsp+2B0h+var_240]
0x1800306d9  mov     rcx, [rsp+2B0h+pszOutBuf]; void *
0x1800306de  cmp     rcx, rax
0x1800306e1  jz      short loc_1800306E8
0x1800306e3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800306e8  xor     eax, eax
0x1800306ea  mov     rcx, [rbp+1B0h+var_30]
0x1800306f1  xor     rcx, rsp; StackCookie
0x1800306f4  call    __security_check_cookie
0x1800306f9  mov     rbx, [rsp+2B0h+arg_18]
0x180030701  add     rsp, 290h
0x180030708  pop     r15
0x18003070a  pop     r14
0x18003070c  pop     rdi
0x18003070d  pop     rsi
0x18003070e  pop     rbp
0x18003070f  retn
```
