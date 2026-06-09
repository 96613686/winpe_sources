# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180015a7c`
- end: `0x180015c46`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180011570`

## callees

- `0x18000e2f0`
- `0x18000ec40`
- `0x180015a7c`
- `0x18001621c`
- `0x180016294`
- `0x180017490`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // r9d
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
        v9 = v7 / 0xC;
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
          if ( (unsigned __int64)v7 + 12 <= 0x1000 )
          {
            v7 += 12;
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (unsigned int)v17,
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
0x180015a7c  push    rbp
0x180015a7e  push    rbx
0x180015a7f  push    rsi
0x180015a80  push    rdi
0x180015a81  push    r12
0x180015a83  push    r14
0x180015a85  lea     rbp, [rsp-0F68h]
0x180015a8d  mov     eax, 1068h
0x180015a92  call    _alloca_probe
0x180015a97  sub     rsp, rax
0x180015a9a  mov     rax, cs:__security_cookie
0x180015aa1  xor     rax, rsp
0x180015aa4  mov     [rbp+0F90h+var_40], rax
0x180015aab  mov     rax, [rcx+8]
0x180015aaf  xor     ebx, ebx
0x180015ab1  sub     rax, [rcx]
0x180015ab4  xor     edi, edi
0x180015ab6  mov     r14, rcx
0x180015ab9  cmp     rax, 0Ch
0x180015abd  jb      loc_180015C20
0x180015ac3  xor     esi, esi
0x180015ac5  mov     r12, 0AAAAAAAAAAAAAAABh
0x180015acf  xor     edx, edx; Val
0x180015ad1  lea     rcx, [rsp+1090h+var_1040]; void *
0x180015ad6  mov     r8d, 1000h; Size
0x180015adc  call    memset_0
0x180015ae1  lea     rax, [rsp+1090h+var_1050]
0x180015ae6  mov     [rsp+1090h+var_1050], 1000h
0x180015aee  mov     [rsp+1090h+var_1068], rax
0x180015af3  lea     r9, [rsp+1090h+var_104C]
0x180015af8  lea     rax, [rsp+1090h+var_1040]
0x180015afd  mov     [rsp+1090h+var_104C], 0
0x180015b05  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015b0c  mov     [rsp+1090h+var_1070], rax
0x180015b11  call    wil_details_NtQueryWnfStateData
0x180015b16  mov     ebx, eax
0x180015b18  test    eax, eax
0x180015b1a  jnz     loc_180015C09
0x180015b20  mov     r9d, [rsp+1090h+var_1050]
0x180015b25  mov     rax, r12
0x180015b28  mul     r9
0x180015b2b  shr     rdx, 3
0x180015b2f  lea     rcx, [rdx+rdx*2]
0x180015b33  shl     rcx, 2
0x180015b37  cmp     r9, rcx
0x180015b3a  jz      short loc_180015B44
0x180015b3c  xor     r9d, r9d
0x180015b3f  mov     [rsp+1090h+var_1050], r9d
0x180015b44  mov     r8, [r14]
0x180015b47  mov     rax, r12
0x180015b4a  mov     ecx, r9d
0x180015b4d  mul     rcx
0x180015b50  mov     rcx, [r14+8]
0x180015b54  mov     rax, r12
0x180015b57  mov     r11, rdx
0x180015b5a  sub     rcx, r8
0x180015b5d  mul     rcx
0x180015b60  shr     r11, 3
0x180015b64  shr     rdx, 3
0x180015b68  lea     rax, [rdx+rdx*2]
0x180015b6c  lea     rdi, [r8+rax*4]
0x180015b70  jmp     short loc_180015BDE
0x180015b72  mov     eax, r11d
0x180015b75  lea     r10, [rsp+1090h+var_1040]
0x180015b7a  lea     rcx, [rax+rax*2]
0x180015b7e  lea     r10, [r10+rcx*4]
0x180015b82  cmp     rdx, r10
0x180015b85  jz      short loc_180015BAD
0x180015b87  mov     eax, [r8]
0x180015b8a  cmp     [rdx], eax
0x180015b8c  jnz     short loc_180015B99
0x180015b8e  movzx   eax, word ptr [r8+4]
0x180015b93  cmp     [rdx+4], ax
0x180015b97  jz      short loc_180015B9F
0x180015b99  add     rdx, 0Ch
0x180015b9d  jmp     short loc_180015B82
0x180015b9f  mov     eax, [r8+8]
0x180015ba3  add     [rdx+8], eax
0x180015ba6  mov     r9d, [rsp+1090h+var_1050]
0x180015bab  jmp     short loc_180015BDA
0x180015bad  mov     eax, r9d
0x180015bb0  add     rax, 0Ch
0x180015bb4  cmp     rax, 1000h
0x180015bba  ja      short loc_180015BDA
0x180015bbc  movsd   xmm0, qword ptr [r8]
0x180015bc1  add     r9d, 0Ch
0x180015bc5  movsd   qword ptr [r10], xmm0
0x180015bca  inc     r11d
0x180015bcd  mov     eax, [r8+8]
0x180015bd1  mov     [r10+8], eax
0x180015bd5  mov     [rsp+1090h+var_1050], r9d
0x180015bda  add     r8, 0Ch
0x180015bde  lea     rdx, [rsp+1090h+var_1040]
0x180015be3  cmp     r8, rdi
0x180015be6  jnz     short loc_180015B72
0x180015be8  mov     eax, [rsp+1090h+var_104C]
0x180015bec  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015bf3  mov     [rsp+1090h+var_1060], 1
0x180015bfb  mov     r8d, r9d
0x180015bfe  mov     dword ptr [rsp+1090h+var_1068], eax
0x180015c02  call    wil_details_NtUpdateWnfStateData
0x180015c07  mov     edi, eax
0x180015c09  cmp     edi, 0C0000001h
0x180015c0f  jnz     short loc_180015C20
0x180015c11  inc     esi
0x180015c13  cmp     esi, 64h ; 'd'
0x180015c16  jge     short loc_180015C20
0x180015c18  test    ebx, ebx
0x180015c1a  jz      loc_180015ACF
0x180015c20  test    ebx, ebx
0x180015c22  cmovz   ebx, edi
0x180015c25  mov     eax, ebx
0x180015c27  mov     rcx, [rbp+0F90h+var_40]
0x180015c2e  xor     rcx, rsp; StackCookie
0x180015c31  call    __security_check_cookie
0x180015c36  add     rsp, 1068h
0x180015c3d  pop     r14
0x180015c3f  pop     r12
0x180015c41  pop     rdi
0x180015c42  pop     rsi
0x180015c43  pop     rbx
0x180015c44  pop     rbp
0x180015c45  retn
```
