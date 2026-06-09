# DiscpGetTargetAddress

- ea: `0x180006a84`
- end: `0x180006c2a`
- name: `DiscpGetTargetAddress`
- size: `422`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, __int64, char, int, volatile signed __int32 **)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800074e8`
- `0x18000eeb0`
- `0x18000f388`
- `0x180010770`

## callees

- `0x1800060e0`
- `0x180006a84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006af6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006af6`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x180006aba`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x180006aba`
- `ISCSIUM!DiscpFreeMemory` at `0x180006bb1`
- `ISCSIUM!DiscpFreeMemory` at `0x180006bc6`
- `ISCSIUM!DiscpFreeMemory` at `0x180006bb1`
- `ISCSIUM!DiscpFreeMemory` at `0x180006bc6`
- `ntdll!RtlLeaveCriticalSection` at `0x180006c06`
- `ntdll!RtlLeaveCriticalSection` at `0x180006c06`
- `ntdll!RtlEnterCriticalSection` at `0x180006ad1`
- `ntdll!RtlEnterCriticalSection` at `0x180006ad1`

## pseudocode

```c
__int64 __fastcall DiscpGetTargetAddress(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        __int64 a3,
        char a4,
        int a5,
        volatile signed __int32 **a6)
{
  int v7; // r15d
  volatile signed __int32 *v8; // rdi
  unsigned int v11; // esi
  volatile signed __int32 *i; // rbx
  void *v13; // rdx
  unsigned int v14; // eax
  volatile signed __int32 **v15; // rax
  void *v16; // rcx
  void *v17; // rcx
  volatile signed __int32 *v19; // [rsp+20h] [rbp-78h] BYREF
  _DWORD v20[28]; // [rsp+28h] [rbp-70h] BYREF

  v7 = a2;
  memset(v20, 0, 28);
  v8 = 0;
  LOBYTE(a2) = 1;
  v19 = 0;
  v11 = DiscpTextAddrToBinary(pszSrc, a2, v20);
  if ( !v11 )
  {
    RtlEnterCriticalSection(&DiscpCritSection);
    for ( i = (volatile signed __int32 *)DiscpTargetAddressList;
          i != (volatile signed __int32 *)&DiscpTargetAddressList;
          i = *(volatile signed __int32 **)i )
    {
      v13 = (void *)*((_QWORD *)i + 6);
      v8 = i;
      v19 = i;
      if ( !(unsigned int)_o__wcsicmp(pszSrc, v13) || v20[0] == *((_DWORD *)i + 14) && v20[1] == *((_DWORD *)i + 15) )
      {
        if ( a5 )
        {
          if ( a5 == 1 )
          {
            if ( (i[5] & 0x10) == 0 )
            {
              v16 = (void *)*((_QWORD *)i + 11);
              if ( v16 )
                DiscpFreeMemory(v16);
              *((_QWORD *)i + 11) = a3;
            }
          }
          else if ( a5 != 2 )
          {
            if ( a5 == 3 )
              v11 = -268500941;
            else
              v11 = 87;
            goto LABEL_30;
          }
        }
        else
        {
          v17 = (void *)*((_QWORD *)i + 11);
          if ( v17 )
            DiscpFreeMemory(v17);
          *((_QWORD *)i + 11) = a3;
          *((_DWORD *)i + 6) = v7;
        }
        v11 = 0;
        _InterlockedIncrement(i + 4);
        goto LABEL_30;
      }
    }
    v11 = -268500981;
    if ( a4 )
    {
      if ( TargetAddressCount >= (unsigned int)MaxTargetAddressCountLimit )
      {
        v8 = 0;
        v11 = 1292;
      }
      else
      {
        _InterlockedIncrement(&TargetAddressCount);
        v14 = DiscpCreateTargetAddress(pszSrc, v7, a3, &v19);
        v8 = v19;
        v11 = v14;
        if ( v14 )
        {
          _InterlockedDecrement(&TargetAddressCount);
        }
        else
        {
          *((_DWORD *)v19 + 5) |= 1u;
          v15 = (volatile signed __int32 **)off_180027028[0];
          if ( *(_UNKNOWN ***)off_180027028[0] != &DiscpTargetAddressList )
            __fastfail(3u);
          *(_QWORD *)v8 = &DiscpTargetAddressList;
          *((_QWORD *)v8 + 1) = v15;
          *v15 = v8;
          off_180027028[0] = (_UNKNOWN **)v8;
        }
      }
    }
LABEL_30:
    RtlLeaveCriticalSection(&DiscpCritSection);
    *a6 = v8;
  }
  return v11;
}

```

## disassembly

```asm
0x180006a84  mov     rax, rsp
0x180006a87  push    rbx
0x180006a88  push    rbp
0x180006a89  push    rsi
0x180006a8a  push    rdi
0x180006a8b  push    r12
0x180006a8d  push    r13
0x180006a8f  push    r14
0x180006a91  push    r15
0x180006a93  sub     rsp, 58h
0x180006a97  xorps   xmm0, xmm0
0x180006a9a  mov     rbp, r8
0x180006a9d  mov     r15d, edx
0x180006aa0  lea     r8, [rax-70h]
0x180006aa4  movups  xmmword ptr [rax-70h], xmm0
0x180006aa8  xor     edi, edi
0x180006aaa  mov     dl, 1
0x180006aac  movups  xmmword ptr [rax-64h], xmm0
0x180006ab0  mov     r12b, r9b
0x180006ab3  mov     [rax-78h], rdi
0x180006ab7  mov     r14, rcx
0x180006aba  call    cs:__imp_DiscpTextAddrToBinary
0x180006ac0  mov     esi, eax
0x180006ac2  test    eax, eax
0x180006ac4  jnz     loc_180006C17
0x180006aca  lea     rcx, DiscpCritSection; CriticalSection
0x180006ad1  call    cs:__imp_RtlEnterCriticalSection
0x180006ad7  mov     rbx, cs:DiscpTargetAddressList
0x180006ade  lea     r13, DiscpTargetAddressList
0x180006ae5  jmp     short loc_180006B15
0x180006ae7  mov     rdx, [rbx+30h]
0x180006aeb  mov     rcx, r14
0x180006aee  mov     rdi, rbx
0x180006af1  mov     [rsp+98h+var_78], rbx
0x180006af6  call    cs:__imp__o__wcsicmp
0x180006afc  test    eax, eax
0x180006afe  jz      short loc_180006B7A
0x180006b00  mov     eax, [rbx+38h]
0x180006b03  cmp     [rsp+98h+var_70], eax
0x180006b07  jnz     short loc_180006B12
0x180006b09  mov     eax, [rbx+3Ch]
0x180006b0c  cmp     [rsp+98h+var_6C], eax
0x180006b10  jz      short loc_180006B7A
0x180006b12  mov     rbx, [rbx]
0x180006b15  cmp     rbx, r13
0x180006b18  jnz     short loc_180006AE7
0x180006b1a  mov     esi, 0EFFF000Bh
0x180006b1f  test    r12b, r12b
0x180006b22  jz      loc_180006BFF
0x180006b28  mov     ecx, cs:MaxTargetAddressCountLimit
0x180006b2e  mov     eax, cs:TargetAddressCount
0x180006b34  cmp     eax, ecx
0x180006b36  jnb     loc_180006BF8
0x180006b3c  lock inc cs:TargetAddressCount
0x180006b43  lea     r9, [rsp+98h+var_78]
0x180006b48  mov     r8, rbp
0x180006b4b  mov     edx, r15d
0x180006b4e  mov     rcx, r14; pszSrc
0x180006b51  call    DiscpCreateTargetAddress
0x180006b56  mov     rdi, [rsp+98h+var_78]
0x180006b5b  mov     esi, eax
0x180006b5d  test    eax, eax
0x180006b5f  jnz     loc_180006BEF
0x180006b65  or      dword ptr [rdi+14h], 1
0x180006b69  mov     rax, cs:off_180027028
0x180006b70  cmp     [rax], r13
0x180006b73  jz      short loc_180006BDC
0x180006b75  lea     ecx, [rsi+3]
0x180006b78  int     29h; Win8: RtlFailFast(ecx)
0x180006b7a  mov     ecx, [rsp+98h+arg_20]
0x180006b81  test    ecx, ecx
0x180006b83  jz      short loc_180006BBD
0x180006b85  sub     ecx, 1
0x180006b88  jz      short loc_180006BA2
0x180006b8a  sub     ecx, 1
0x180006b8d  jz      short loc_180006BD4
0x180006b8f  cmp     ecx, 1
0x180006b92  jz      short loc_180006B9B
0x180006b94  mov     esi, 57h ; 'W'
0x180006b99  jmp     short loc_180006BFF
0x180006b9b  mov     esi, 0EFFF0033h
0x180006ba0  jmp     short loc_180006BFF
0x180006ba2  test    byte ptr [rbx+14h], 10h
0x180006ba6  jnz     short loc_180006BD4
0x180006ba8  mov     rcx, [rbx+58h]
0x180006bac  test    rcx, rcx
0x180006baf  jz      short loc_180006BB7
0x180006bb1  call    cs:__imp_DiscpFreeMemory
0x180006bb7  mov     [rbx+58h], rbp
0x180006bbb  jmp     short loc_180006BD4
0x180006bbd  mov     rcx, [rbx+58h]
0x180006bc1  test    rcx, rcx
0x180006bc4  jz      short loc_180006BCC
0x180006bc6  call    cs:__imp_DiscpFreeMemory
0x180006bcc  mov     [rbx+58h], rbp
0x180006bd0  mov     [rbx+18h], r15d
0x180006bd4  xor     esi, esi
0x180006bd6  lock inc dword ptr [rbx+10h]
0x180006bda  jmp     short loc_180006BFF
0x180006bdc  mov     [rdi], r13
0x180006bdf  mov     [rdi+8], rax
0x180006be3  mov     [rax], rdi
0x180006be6  mov     cs:off_180027028, rdi
0x180006bed  jmp     short loc_180006BFF
0x180006bef  lock dec cs:TargetAddressCount
0x180006bf6  jmp     short loc_180006BFF
0x180006bf8  xor     edi, edi
0x180006bfa  mov     esi, 50Ch
0x180006bff  lea     rcx, DiscpCritSection; CriticalSection
0x180006c06  call    cs:__imp_RtlLeaveCriticalSection
0x180006c0c  mov     rax, [rsp+98h+arg_28]
0x180006c14  mov     [rax], rdi
0x180006c17  mov     eax, esi
0x180006c19  add     rsp, 58h
0x180006c1d  pop     r15
0x180006c1f  pop     r14
0x180006c21  pop     r13
0x180006c23  pop     r12
0x180006c25  pop     rdi
0x180006c26  pop     rsi
0x180006c27  pop     rbp
0x180006c28  pop     rbx
0x180006c29  retn
```
