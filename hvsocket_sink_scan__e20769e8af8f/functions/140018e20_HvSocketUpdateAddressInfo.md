# HvSocketUpdateAddressInfo

- ea: `0x140018e20`
- end: `0x1400190c1`
- name: `HvSocketUpdateAddressInfo`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140009df0`
- `0x140009fa4`
- `0x14000bfa0`
- `0x140018e20`
- `0x1400190c8`
- `0x14001d304`
- `0x14001df1c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018f46`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019047`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019064`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018f46`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019047`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019064`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018f3a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001903b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019058`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140018f3a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001903b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019058`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018efd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018fb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018efd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018fb2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018f0d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018fc5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018f0d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018fc5`

## string_xrefs

- `0x14001902c`: `HvSocketUpdateAddressInfo`
- `0x140019090`: `HvSocketUpdateAddressInfo`
- `0x140018f60`: `Update address info.`

## pseudocode

```c
__int64 __fastcall HvSocketUpdateAddressInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  _QWORD *v5; // rsi
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r14
  __int64 v11; // rax
  int v12; // eax
  _BYTE v14[16]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v15; // [rsp+30h] [rbp-38h] BYREF

  v2 = a1 + 104;
  if ( *(_QWORD *)a2 == *(_QWORD *)(a1 + 104) && *(_QWORD *)(a2 + 8) == *(_QWORD *)(a1 + 112) )
  {
    v5 = (_QWORD *)(a2 + 16);
    v6 = *(_QWORD *)(a2 + 16) - *(_QWORD *)&HV_GUID_ZERO.Data1;
    if ( !v6 )
      v6 = *(_QWORD *)(a2 + 24) - *(_QWORD *)HV_GUID_ZERO.Data4;
    if ( !v6
      || *(_QWORD *)(a2 + 32) == *(_QWORD *)&HV_GUID_ZERO.Data1 && *(_QWORD *)(a2 + 40) == *(_QWORD *)HV_GUID_ZERO.Data4 )
    {
      if ( *v5 != *(_QWORD *)&HV_GUID_ZERO.Data1
        || *(_QWORD *)(a2 + 24) != *(_QWORD *)HV_GUID_ZERO.Data4
        || *(_QWORD *)(a2 + 32) != *(_QWORD *)&HV_GUID_ZERO.Data1
        || *(_QWORD *)(a2 + 40) != *(_QWORD *)HV_GUID_ZERO.Data4 )
      {
        v10 = *(_QWORD *)(a1 + 96);
        KeEnterCriticalRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
        *(_OWORD *)v2 = *(_OWORD *)a2;
        *(_OWORD *)(v2 + 16) = *(_OWORD *)(a2 + 16);
        *(_OWORD *)(v2 + 32) = *(_OWORD *)(a2 + 32);
        *(_DWORD *)(v2 + 48) = *(_DWORD *)(a2 + 48);
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
        KeLeaveCriticalRegion();
        if ( (unsigned int)dword_140013058 > 4 )
          HvsocketTraceMessage("Update address info.", a2);
        if ( (*(_DWORD *)(a2 + 48) & 1) == 0
          || *v5 == *(_QWORD *)&HV_GUID_ZERO.Data1 && v5[1] == *(_QWORD *)HV_GUID_ZERO.Data4 )
        {
          v15 = 0;
          v15 = *(_OWORD *)HvsocketAddressInfoToPartitionId(v14, a2);
          KeEnterCriticalRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
          if ( !HvSocketPartitionExists(v10, (__int64)&v15) )
          {
            v11 = *(_QWORD *)(a2 + 32) - *(_QWORD *)&HV_GUID_ZERO.Data1;
            if ( !v11 )
              v11 = *(_QWORD *)(a2 + 40) - *(_QWORD *)HV_GUID_ZERO.Data4;
            v12 = HvSocketCreateUninitializedPartition(v10, &v15, v11 == 0);
            v7 = v12;
            if ( v12 < 0 )
            {
              if ( (unsigned int)dword_140013058 > 2 )
                HvsocketTraceGuidError("HvSocketUpdateAddressInfo", 309, (unsigned int)v12, &v15);
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
              KeLeaveCriticalRegion();
              return v7;
            }
          }
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
          KeLeaveCriticalRegion();
        }
        return 0;
      }
      v7 = -1073741811;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v8 = a2;
        v9 = 283;
        goto LABEL_32;
      }
    }
    else
    {
      v7 = -1073741811;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v8 = a2 + 16;
        v9 = 272;
LABEL_32:
        HvsocketTraceGuidError("HvSocketUpdateAddressInfo", v9, 3221225485LL, v8);
      }
    }
  }
  else
  {
    v7 = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v8 = a1 + 104;
      v9 = 261;
      goto LABEL_32;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140018e20  mov     [rsp+arg_10], rbx
0x140018e25  mov     [rsp+arg_18], rbp
0x140018e2a  push    rsi
0x140018e2b  push    rdi
0x140018e2c  push    r14
0x140018e2e  sub     rsp, 50h
0x140018e32  mov     rax, cs:__security_cookie
0x140018e39  xor     rax, rsp
0x140018e3c  mov     [rsp+68h+var_28], rax
0x140018e41  mov     rax, [rdx]
0x140018e44  lea     rbp, [rcx+68h]
0x140018e48  mov     rdi, rdx
0x140018e4b  mov     rbx, rcx
0x140018e4e  cmp     rax, [rbp+0]
0x140018e52  jnz     loc_140019074
0x140018e58  mov     rax, [rdx+8]
0x140018e5c  cmp     rax, [rbp+8]
0x140018e60  jnz     loc_140019074
0x140018e66  mov     rcx, qword ptr cs:HV_GUID_ZERO.Data4
0x140018e6d  lea     rsi, [rdx+10h]
0x140018e71  mov     rax, [rsi]
0x140018e74  mov     rdx, qword ptr cs:HV_GUID_ZERO.Data1
0x140018e7b  sub     rax, rdx
0x140018e7e  jnz     short loc_140018E87
0x140018e80  mov     rax, [rsi+8]
0x140018e84  sub     rax, rcx
0x140018e87  test    rax, rax
0x140018e8a  jz      short loc_140018EBD
0x140018e8c  cmp     [rdi+20h], rdx
0x140018e90  jnz     short loc_140018E98
0x140018e92  cmp     [rdi+28h], rcx
0x140018e96  jz      short loc_140018EBD
0x140018e98  mov     eax, cs:dword_140013058
0x140018e9e  mov     r8d, 0C000000Dh
0x140018ea4  mov     ebx, r8d
0x140018ea7  cmp     eax, 2
0x140018eaa  jbe     loc_14001909C
0x140018eb0  mov     r9, rsi
0x140018eb3  mov     edx, 110h
0x140018eb8  jmp     loc_140019090
0x140018ebd  cmp     [rsi], rdx
0x140018ec0  jnz     short loc_140018EF9
0x140018ec2  cmp     [rsi+8], rcx
0x140018ec6  jnz     short loc_140018EF9
0x140018ec8  cmp     [rdi+20h], rdx
0x140018ecc  jnz     short loc_140018EF9
0x140018ece  cmp     [rdi+28h], rcx
0x140018ed2  jnz     short loc_140018EF9
0x140018ed4  mov     eax, cs:dword_140013058
0x140018eda  mov     r8d, 0C000000Dh
0x140018ee0  mov     ebx, r8d
0x140018ee3  cmp     eax, 2
0x140018ee6  jbe     loc_14001909C
0x140018eec  mov     r9, rdi
0x140018eef  mov     edx, 11Bh
0x140018ef4  jmp     loc_140019090
0x140018ef9  mov     r14, [rbx+60h]
0x140018efd  call    cs:__imp_KeEnterCriticalRegion
0x140018f04  nop     dword ptr [rax+rax+00h]
0x140018f09  lea     rcx, [rbx+10h]; FastMutex
0x140018f0d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018f14  nop     dword ptr [rax+rax+00h]
0x140018f19  movups  xmm0, xmmword ptr [rdi]
0x140018f1c  lea     rcx, [rbx+10h]; FastMutex
0x140018f20  movups  xmmword ptr [rbp+0], xmm0
0x140018f24  movups  xmm1, xmmword ptr [rdi+10h]
0x140018f28  movups  xmmword ptr [rbp+10h], xmm1
0x140018f2c  movups  xmm0, xmmword ptr [rdi+20h]
0x140018f30  movups  xmmword ptr [rbp+20h], xmm0
0x140018f34  mov     eax, [rdi+30h]
0x140018f37  mov     [rbp+30h], eax
0x140018f3a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018f41  nop     dword ptr [rax+rax+00h]
0x140018f46  call    cs:__imp_KeLeaveCriticalRegion
0x140018f4d  nop     dword ptr [rax+rax+00h]
0x140018f52  mov     eax, cs:dword_140013058
0x140018f58  cmp     eax, 4
0x140018f5b  jbe     short loc_140018F6C
0x140018f5d  mov     rdx, rdi
0x140018f60  lea     rcx, aUpdateAddressI; "Update address info."
0x140018f67  call    HvsocketTraceMessage
0x140018f6c  mov     eax, [rdi+30h]
0x140018f6f  test    al, 1
0x140018f71  jz      short loc_140018F94
0x140018f73  mov     rax, [rsi]
0x140018f76  cmp     rax, qword ptr cs:HV_GUID_ZERO.Data1
0x140018f7d  jnz     loc_140019070
0x140018f83  mov     rax, [rsi+8]
0x140018f87  cmp     rax, qword ptr cs:HV_GUID_ZERO.Data4
0x140018f8e  jnz     loc_140019070
0x140018f94  xorps   xmm0, xmm0
0x140018f97  lea     rcx, [rsp+68h+var_48]
0x140018f9c  mov     rdx, rdi
0x140018f9f  movups  [rsp+68h+var_38], xmm0
0x140018fa4  call    HvsocketAddressInfoToPartitionId
0x140018fa9  movups  xmm1, xmmword ptr [rax]
0x140018fac  movdqu  [rsp+68h+var_38], xmm1
0x140018fb2  call    cs:__imp_KeEnterCriticalRegion
0x140018fb9  nop     dword ptr [rax+rax+00h]
0x140018fbe  lea     rsi, [r14+10h]
0x140018fc2  mov     rcx, rsi; FastMutex
0x140018fc5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018fcc  nop     dword ptr [rax+rax+00h]
0x140018fd1  lea     rdx, [rsp+68h+var_38]
0x140018fd6  mov     rcx, r14
0x140018fd9  call    HvSocketPartitionExists
0x140018fde  test    al, al
0x140018fe0  jnz     short loc_140019055
0x140018fe2  mov     rax, [rdi+20h]
0x140018fe6  sub     rax, qword ptr cs:HV_GUID_ZERO.Data1
0x140018fed  jnz     short loc_140018FFA
0x140018fef  mov     rax, [rdi+28h]
0x140018ff3  sub     rax, qword ptr cs:HV_GUID_ZERO.Data4
0x140018ffa  test    rax, rax
0x140018ffd  lea     rdx, [rsp+68h+var_38]
0x140019002  mov     rcx, r14
0x140019005  setz    r8b
0x140019009  call    HvSocketCreateUninitializedPartition
0x14001900e  mov     ebx, eax
0x140019010  test    eax, eax
0x140019012  jns     short loc_140019055
0x140019014  mov     edx, cs:dword_140013058
0x14001901a  cmp     edx, 2
0x14001901d  jbe     short loc_140019038
0x14001901f  lea     r9, [rsp+68h+var_38]
0x140019024  mov     r8d, eax
0x140019027  mov     edx, 135h
0x14001902c  lea     rcx, aHvsocketupdate_2; "HvSocketUpdateAddressInfo"
0x140019033  call    HvsocketTraceGuidError
0x140019038  mov     rcx, rsi; FastMutex
0x14001903b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140019042  nop     dword ptr [rax+rax+00h]
0x140019047  call    cs:__imp_KeLeaveCriticalRegion
0x14001904e  nop     dword ptr [rax+rax+00h]
0x140019053  jmp     short loc_14001909C
0x140019055  mov     rcx, rsi; FastMutex
0x140019058  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001905f  nop     dword ptr [rax+rax+00h]
0x140019064  call    cs:__imp_KeLeaveCriticalRegion
0x14001906b  nop     dword ptr [rax+rax+00h]
0x140019070  xor     ebx, ebx
0x140019072  jmp     short loc_14001909C
0x140019074  mov     eax, cs:dword_140013058
0x14001907a  mov     r8d, 0C000000Dh
0x140019080  mov     ebx, r8d
0x140019083  cmp     eax, 2
0x140019086  jbe     short loc_14001909C
0x140019088  mov     r9, rbp
0x14001908b  mov     edx, 105h
0x140019090  lea     rcx, aHvsocketupdate_2; "HvSocketUpdateAddressInfo"
0x140019097  call    HvsocketTraceGuidError
0x14001909c  mov     eax, ebx
0x14001909e  mov     rcx, [rsp+68h+var_28]
0x1400190a3  xor     rcx, rsp; StackCookie
0x1400190a6  call    __security_check_cookie
0x1400190ab  lea     r11, [rsp+68h+var_18]
0x1400190b0  mov     rbx, [r11+30h]
0x1400190b4  mov     rbp, [r11+38h]
0x1400190b8  mov     rsp, r11
0x1400190bb  pop     r14
0x1400190bd  pop     rdi
0x1400190be  pop     rsi
0x1400190bf  retn
```
