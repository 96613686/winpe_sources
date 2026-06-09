# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000aae0`
- end: `0x18000acaa`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800079b0`

## callees

- `0x18000aae0`
- `0x18000b3fc`
- `0x18000b474`
- `0x18001b30a`
- `0x18001b340`
- `0x18001b3d0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r11d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // r10
  _DWORD *v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v15 = 4096;
      v16 = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (unsigned int)&v16,
                       (__int64)v17,
                       (__int64)&v15);
      if ( !WnfStateData )
      {
        v7 = v15;
        if ( v15 != 12 * (v15 / 0xCuLL) )
        {
          v7 = 0;
          v15 = 0;
        }
        v8 = *a1;
        v9 = (unsigned int)v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( 1 )
        {
          v12 = v17;
          if ( v8 == v10 )
            break;
          v11 = &v17[3 * v9];
          while ( v12 != v11 )
          {
            if ( *v12 == *(_DWORD *)v8 && *((_WORD *)v12 + 2) == *(_WORD *)(v8 + 4) )
            {
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v15;
              goto LABEL_15;
            }
            v12 += 3;
          }
          if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
          {
            v7 = (unsigned int)(v7 + 12);
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v17,
                    v7,
                    v7,
                    v14,
                    v16,
                    1);
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x18000aae0  push    rbp
0x18000aae2  push    rbx
0x18000aae3  push    rsi
0x18000aae4  push    rdi
0x18000aae5  push    r12
0x18000aae7  push    r14
0x18000aae9  lea     rbp, [rsp-0F68h]
0x18000aaf1  mov     eax, 1068h
0x18000aaf6  call    _alloca_probe
0x18000aafb  sub     rsp, rax
0x18000aafe  mov     rax, cs:__security_cookie
0x18000ab05  xor     rax, rsp
0x18000ab08  mov     [rbp+0F90h+var_40], rax
0x18000ab0f  mov     rax, [rcx+8]
0x18000ab13  xor     ebx, ebx
0x18000ab15  sub     rax, [rcx]
0x18000ab18  xor     edi, edi
0x18000ab1a  mov     r14, rcx
0x18000ab1d  cmp     rax, 0Ch
0x18000ab21  jb      loc_18000AC84
0x18000ab27  xor     esi, esi
0x18000ab29  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ab33  xor     edx, edx; Val
0x18000ab35  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ab3a  mov     r8d, 1000h; Size
0x18000ab40  call    memset_0
0x18000ab45  lea     rax, [rsp+1090h+var_1050]
0x18000ab4a  mov     [rsp+1090h+var_1050], 1000h
0x18000ab52  mov     [rsp+1090h+var_1068], rax
0x18000ab57  lea     r9, [rsp+1090h+var_104C]
0x18000ab5c  lea     rax, [rsp+1090h+var_1040]
0x18000ab61  mov     [rsp+1090h+var_104C], 0
0x18000ab69  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ab70  mov     [rsp+1090h+var_1070], rax
0x18000ab75  call    wil_details_NtQueryWnfStateData
0x18000ab7a  mov     ebx, eax
0x18000ab7c  test    eax, eax
0x18000ab7e  jnz     loc_18000AC6D
0x18000ab84  mov     r9d, [rsp+1090h+var_1050]
0x18000ab89  mov     rax, r12
0x18000ab8c  mul     r9
0x18000ab8f  shr     rdx, 3
0x18000ab93  lea     rcx, [rdx+rdx*2]
0x18000ab97  shl     rcx, 2
0x18000ab9b  cmp     r9, rcx
0x18000ab9e  jz      short loc_18000ABA8
0x18000aba0  xor     r9d, r9d
0x18000aba3  mov     [rsp+1090h+var_1050], r9d
0x18000aba8  mov     r8, [r14]
0x18000abab  mov     rax, r12
0x18000abae  mov     ecx, r9d
0x18000abb1  mul     rcx
0x18000abb4  mov     rcx, [r14+8]
0x18000abb8  mov     rax, r12
0x18000abbb  mov     r11, rdx
0x18000abbe  sub     rcx, r8
0x18000abc1  mul     rcx
0x18000abc4  shr     r11, 3
0x18000abc8  shr     rdx, 3
0x18000abcc  lea     rax, [rdx+rdx*2]
0x18000abd0  lea     rdi, [r8+rax*4]
0x18000abd4  jmp     short loc_18000AC42
0x18000abd6  mov     eax, r11d
0x18000abd9  lea     r10, [rsp+1090h+var_1040]
0x18000abde  lea     rcx, [rax+rax*2]
0x18000abe2  lea     r10, [r10+rcx*4]
0x18000abe6  cmp     rdx, r10
0x18000abe9  jz      short loc_18000AC11
0x18000abeb  mov     eax, [r8]
0x18000abee  cmp     [rdx], eax
0x18000abf0  jnz     short loc_18000ABFD
0x18000abf2  movzx   eax, word ptr [r8+4]
0x18000abf7  cmp     [rdx+4], ax
0x18000abfb  jz      short loc_18000AC03
0x18000abfd  add     rdx, 0Ch
0x18000ac01  jmp     short loc_18000ABE6
0x18000ac03  mov     eax, [r8+8]
0x18000ac07  add     [rdx+8], eax
0x18000ac0a  mov     r9d, [rsp+1090h+var_1050]
0x18000ac0f  jmp     short loc_18000AC3E
0x18000ac11  mov     eax, r9d
0x18000ac14  add     rax, 0Ch
0x18000ac18  cmp     rax, 1000h
0x18000ac1e  ja      short loc_18000AC3E
0x18000ac20  movsd   xmm0, qword ptr [r8]
0x18000ac25  add     r9d, 0Ch
0x18000ac29  movsd   qword ptr [r10], xmm0
0x18000ac2e  inc     r11d
0x18000ac31  mov     eax, [r8+8]
0x18000ac35  mov     [r10+8], eax
0x18000ac39  mov     [rsp+1090h+var_1050], r9d
0x18000ac3e  add     r8, 0Ch
0x18000ac42  lea     rdx, [rsp+1090h+var_1040]
0x18000ac47  cmp     r8, rdi
0x18000ac4a  jnz     short loc_18000ABD6
0x18000ac4c  mov     eax, [rsp+1090h+var_104C]
0x18000ac50  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ac57  mov     [rsp+1090h+var_1060], 1
0x18000ac5f  mov     r8d, r9d
0x18000ac62  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000ac66  call    wil_details_NtUpdateWnfStateData
0x18000ac6b  mov     edi, eax
0x18000ac6d  cmp     edi, 0C0000001h
0x18000ac73  jnz     short loc_18000AC84
0x18000ac75  inc     esi
0x18000ac77  cmp     esi, 64h ; 'd'
0x18000ac7a  jge     short loc_18000AC84
0x18000ac7c  test    ebx, ebx
0x18000ac7e  jz      loc_18000AB33
0x18000ac84  test    ebx, ebx
0x18000ac86  cmovz   ebx, edi
0x18000ac89  mov     eax, ebx
0x18000ac8b  mov     rcx, [rbp+0F90h+var_40]
0x18000ac92  xor     rcx, rsp; StackCookie
0x18000ac95  call    __security_check_cookie
0x18000ac9a  add     rsp, 1068h
0x18000aca1  pop     r14
0x18000aca3  pop     r12
0x18000aca5  pop     rdi
0x18000aca6  pop     rsi
0x18000aca7  pop     rbx
0x18000aca8  pop     rbp
0x18000aca9  retn
```
