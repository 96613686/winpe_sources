# SystemManagedAccountUtil::GenerateComplexSuffix(ushort * *)

- ea: `0x18001d938`
- end: `0x18001dada`
- name: `?GenerateComplexSuffix@SystemManagedAccountUtil@@YAJPEAPEAG@Z`
- size: `418`
- prototype: `__int64 __fastcall(SystemManagedAccountUtil *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d29c`

## callees

- `0x180003a60`
- `0x180003ac8`
- `0x1800067c4`
- `0x18001d938`
- `0x1800215f8`
- `0x180021cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18001d9f0`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18001d9f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da5d`

## pseudocode

```c
__int64 __fastcall SystemManagedAccountUtil::GenerateComplexSuffix(
        SystemManagedAccountUtil *this,
        unsigned __int16 **a2)
{
  __int64 v2; // rdx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // ebx
  unsigned __int64 v9; // rdi
  __int64 v10; // r14
  int v11; // eax
  unsigned int v12; // edi
  LPVOID pv[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int16 v15; // [rsp+60h] [rbp+8h] BYREF
  __int16 v16; // [rsp+62h] [rbp+Ah]

  v2 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  *(_QWORD *)this = 0;
  if ( dword_18003F978 > *(_DWORD *)(ThreadLocalStoragePointer[v2] + 4LL) )
  {
    Init_thread_header(&dword_18003F978);
    if ( dword_18003F978 == -1 )
    {
      qword_18003F920[0] = (__int64)L"ABCDEFGHIJKLMNOPQRSTUVWXYZ";
      qword_18003F928 = (__int64)L"abcdefghijklmnopqrstuvwxyz";
      qword_18003F930 = (__int64)L"0123456789";
      qword_18003F938 = (__int64)L"`~!@#$%^&*_-+=|\\{}[]:;\"'<>,.?";
      Init_thread_footer(&dword_18003F978);
    }
  }
  memset(pv, 0, 24);
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         pv,
         &dword_1800328FC,
         -1);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = -1;
      v10 = qword_18003F920[v8];
      do
        ++v9;
      while ( *(_WORD *)(v10 + 2 * v9) );
      v15 = *(_WORD *)(v10 + 2 * (rand() % v9));
      v16 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(pv, &v15);
      v12 = v11;
      if ( v11 < 0 )
        break;
      if ( (unsigned int)++v8 >= 4 )
      {
        *(LPVOID *)this = pv[0];
        return 0;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
      (const char *)(unsigned int)v11,
      (int)pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v12;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
      (const char *)(unsigned int)v5,
      (int)pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v6;
  }
}

```

## disassembly

```asm
0x18001d938  mov     [rsp+arg_8], rbx
0x18001d93d  mov     [rsp+arg_10], rbp
0x18001d942  push    rsi
0x18001d943  push    rdi
0x18001d944  push    r14
0x18001d946  sub     rsp, 40h
0x18001d94a  mov     edx, cs:_tls_index
0x18001d950  xor     ebp, ebp
0x18001d952  mov     rax, gs:58h
0x18001d95b  mov     rsi, rcx
0x18001d95e  mov     [rcx], rbp
0x18001d961  mov     ecx, 4
0x18001d966  mov     rax, [rax+rdx*8]
0x18001d96a  mov     eax, [rcx+rax]
0x18001d96d  cmp     cs:dword_18003F978, eax
0x18001d973  jg      loc_18001DA78
0x18001d979  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d97d  mov     [rsp+58h+pv], rbp; int
0x18001d982  lea     rdx, dword_1800328FC
0x18001d989  mov     [rsp+58h+var_30], rbp
0x18001d98e  lea     rcx, [rsp+58h+pv]
0x18001d993  mov     [rsp+58h+var_28], rbp
0x18001d998  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001d99d  mov     ebx, eax
0x18001d99f  test    eax, eax
0x18001d9a1  jns     short loc_18001D9D3
0x18001d9a3  mov     rcx, [rsp+58h]; this
0x18001d9a8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d9af  mov     r9d, eax; char *
0x18001d9b2  mov     edx, 2Dh ; '-'; void *
0x18001d9b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9bc  mov     rcx, [rsp+58h+pv]; pv
0x18001d9c1  test    rcx, rcx
0x18001d9c4  jz      short loc_18001D9CC
0x18001d9c6  call    cs:__imp_CoTaskMemFree
0x18001d9cc  mov     eax, ebx
0x18001d9ce  jmp     loc_18001DA65
0x18001d9d3  mov     ebx, ebp
0x18001d9d5  mov     eax, ebx
0x18001d9d7  lea     r14, qword_18003F920
0x18001d9de  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d9e2  mov     r14, [r14+rax*8]
0x18001d9e6  inc     rdi
0x18001d9e9  cmp     [r14+rdi*2], bp
0x18001d9ee  jnz     short loc_18001D9E6
0x18001d9f0  call    cs:__imp_rand
0x18001d9f6  cdqe
0x18001d9f8  xor     edx, edx
0x18001d9fa  lea     rcx, [rsp+58h+pv]
0x18001d9ff  div     rdi
0x18001da02  movzx   eax, word ptr [r14+rdx*2]
0x18001da07  lea     rdx, [rsp+58h+arg_0]
0x18001da0c  mov     [rsp+58h+arg_0], ax
0x18001da11  xor     eax, eax
0x18001da13  mov     [rsp+58h+arg_2], ax
0x18001da18  lea     r8d, [rax+1]
0x18001da1c  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001da21  mov     edi, eax
0x18001da23  test    eax, eax
0x18001da25  js      short loc_18001DA3A
0x18001da27  inc     ebx
0x18001da29  cmp     ebx, 4
0x18001da2c  jb      short loc_18001D9D5
0x18001da2e  mov     rax, [rsp+58h+pv]
0x18001da33  mov     [rsi], rax
0x18001da36  xor     eax, eax
0x18001da38  jmp     short loc_18001DA65
0x18001da3a  mov     rcx, [rsp+58h]; this
0x18001da3f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001da46  mov     r9d, edi; char *
0x18001da49  mov     edx, 31h ; '1'; void *
0x18001da4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da53  mov     rcx, [rsp+58h+pv]; pv
0x18001da58  test    rcx, rcx
0x18001da5b  jz      short loc_18001DA63
0x18001da5d  call    cs:__imp_CoTaskMemFree
0x18001da63  mov     eax, edi
0x18001da65  mov     rbx, [rsp+58h+arg_8]
0x18001da6a  mov     rbp, [rsp+58h+arg_10]
0x18001da6f  add     rsp, 40h
0x18001da73  pop     r14
0x18001da75  pop     rdi
0x18001da76  pop     rsi
0x18001da77  retn
0x18001da78  lea     rcx, dword_18003F978
0x18001da7f  call    _Init_thread_header
0x18001da84  cmp     cs:dword_18003F978, 0FFFFFFFFh
0x18001da8b  jnz     loc_18001D979
0x18001da91  lea     rax, aAbcdefghijklmn_0; "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
0x18001da98  mov     cs:qword_18003F920, rax
0x18001da9f  lea     rcx, dword_18003F978
0x18001daa6  lea     rax, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyz"
0x18001daad  mov     cs:qword_18003F928, rax
0x18001dab4  lea     rax, a0123456789; "0123456789"
0x18001dabb  mov     cs:qword_18003F930, rax
0x18001dac2  lea     rax, asc_180032A30; "`~!@#$%^&*_-+=|\\{}[]:;\"'<>,.?"
0x18001dac9  mov     cs:qword_18003F938, rax
0x18001dad0  call    _Init_thread_footer
0x18001dad5  jmp     loc_18001D979
```
