# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000cdd8`
- end: `0x18000cfa2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006a70`

## callees

- `0x180001640`
- `0x180001f78`
- `0x18000cdd8`
- `0x18000d2bc`
- `0x18000d334`
- `0x180025330`

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
0x18000cdd8  push    rbp
0x18000cdda  push    rbx
0x18000cddb  push    rsi
0x18000cddc  push    rdi
0x18000cddd  push    r12
0x18000cddf  push    r14
0x18000cde1  lea     rbp, [rsp-0F68h]
0x18000cde9  mov     eax, 1068h
0x18000cdee  call    _alloca_probe
0x18000cdf3  sub     rsp, rax
0x18000cdf6  mov     rax, cs:__security_cookie
0x18000cdfd  xor     rax, rsp
0x18000ce00  mov     [rbp+0F90h+var_40], rax
0x18000ce07  mov     rax, [rcx+8]
0x18000ce0b  xor     ebx, ebx
0x18000ce0d  sub     rax, [rcx]
0x18000ce10  xor     edi, edi
0x18000ce12  mov     r14, rcx
0x18000ce15  cmp     rax, 0Ch
0x18000ce19  jb      loc_18000CF7C
0x18000ce1f  xor     esi, esi
0x18000ce21  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ce2b  xor     edx, edx; Val
0x18000ce2d  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ce32  mov     r8d, 1000h; Size
0x18000ce38  call    memset_0
0x18000ce3d  lea     rax, [rsp+1090h+var_1050]
0x18000ce42  mov     [rsp+1090h+var_1050], 1000h
0x18000ce4a  mov     [rsp+1090h+var_1068], rax
0x18000ce4f  lea     r9, [rsp+1090h+var_104C]
0x18000ce54  lea     rax, [rsp+1090h+var_1040]
0x18000ce59  mov     [rsp+1090h+var_104C], 0
0x18000ce61  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ce68  mov     [rsp+1090h+var_1070], rax
0x18000ce6d  call    wil_details_NtQueryWnfStateData
0x18000ce72  mov     ebx, eax
0x18000ce74  test    eax, eax
0x18000ce76  jnz     loc_18000CF65
0x18000ce7c  mov     r9d, [rsp+1090h+var_1050]
0x18000ce81  mov     rax, r12
0x18000ce84  mul     r9
0x18000ce87  shr     rdx, 3
0x18000ce8b  lea     rcx, [rdx+rdx*2]
0x18000ce8f  shl     rcx, 2
0x18000ce93  cmp     r9, rcx
0x18000ce96  jz      short loc_18000CEA0
0x18000ce98  xor     r9d, r9d
0x18000ce9b  mov     [rsp+1090h+var_1050], r9d
0x18000cea0  mov     r8, [r14]
0x18000cea3  mov     rax, r12
0x18000cea6  mov     ecx, r9d
0x18000cea9  mul     rcx
0x18000ceac  mov     rcx, [r14+8]
0x18000ceb0  mov     rax, r12
0x18000ceb3  mov     r11, rdx
0x18000ceb6  sub     rcx, r8
0x18000ceb9  mul     rcx
0x18000cebc  shr     r11, 3
0x18000cec0  shr     rdx, 3
0x18000cec4  lea     rax, [rdx+rdx*2]
0x18000cec8  lea     rdi, [r8+rax*4]
0x18000cecc  jmp     short loc_18000CF3A
0x18000cece  mov     eax, r11d
0x18000ced1  lea     r10, [rsp+1090h+var_1040]
0x18000ced6  lea     rcx, [rax+rax*2]
0x18000ceda  lea     r10, [r10+rcx*4]
0x18000cede  cmp     rdx, r10
0x18000cee1  jz      short loc_18000CF09
0x18000cee3  mov     eax, [r8]
0x18000cee6  cmp     [rdx], eax
0x18000cee8  jnz     short loc_18000CEF5
0x18000ceea  movzx   eax, word ptr [r8+4]
0x18000ceef  cmp     [rdx+4], ax
0x18000cef3  jz      short loc_18000CEFB
0x18000cef5  add     rdx, 0Ch
0x18000cef9  jmp     short loc_18000CEDE
0x18000cefb  mov     eax, [r8+8]
0x18000ceff  add     [rdx+8], eax
0x18000cf02  mov     r9d, [rsp+1090h+var_1050]
0x18000cf07  jmp     short loc_18000CF36
0x18000cf09  mov     eax, r9d
0x18000cf0c  add     rax, 0Ch
0x18000cf10  cmp     rax, 1000h
0x18000cf16  ja      short loc_18000CF36
0x18000cf18  movsd   xmm0, qword ptr [r8]
0x18000cf1d  add     r9d, 0Ch
0x18000cf21  movsd   qword ptr [r10], xmm0
0x18000cf26  inc     r11d
0x18000cf29  mov     eax, [r8+8]
0x18000cf2d  mov     [r10+8], eax
0x18000cf31  mov     [rsp+1090h+var_1050], r9d
0x18000cf36  add     r8, 0Ch
0x18000cf3a  lea     rdx, [rsp+1090h+var_1040]
0x18000cf3f  cmp     r8, rdi
0x18000cf42  jnz     short loc_18000CECE
0x18000cf44  mov     eax, [rsp+1090h+var_104C]
0x18000cf48  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cf4f  mov     [rsp+1090h+var_1060], 1
0x18000cf57  mov     r8d, r9d
0x18000cf5a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cf5e  call    wil_details_NtUpdateWnfStateData
0x18000cf63  mov     edi, eax
0x18000cf65  cmp     edi, 0C0000001h
0x18000cf6b  jnz     short loc_18000CF7C
0x18000cf6d  inc     esi
0x18000cf6f  cmp     esi, 64h ; 'd'
0x18000cf72  jge     short loc_18000CF7C
0x18000cf74  test    ebx, ebx
0x18000cf76  jz      loc_18000CE2B
0x18000cf7c  test    ebx, ebx
0x18000cf7e  cmovz   ebx, edi
0x18000cf81  mov     eax, ebx
0x18000cf83  mov     rcx, [rbp+0F90h+var_40]
0x18000cf8a  xor     rcx, rsp; StackCookie
0x18000cf8d  call    __security_check_cookie
0x18000cf92  add     rsp, 1068h
0x18000cf99  pop     r14
0x18000cf9b  pop     r12
0x18000cf9d  pop     rdi
0x18000cf9e  pop     rsi
0x18000cf9f  pop     rbx
0x18000cfa0  pop     rbp
0x18000cfa1  retn
```
