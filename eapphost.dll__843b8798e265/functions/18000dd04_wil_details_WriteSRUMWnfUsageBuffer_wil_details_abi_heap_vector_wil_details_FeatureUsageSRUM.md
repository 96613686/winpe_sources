# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000dd04`
- end: `0x18000decf`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a760`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x18000dd04`
- `0x18000e650`
- `0x18000e6c8`
- `0x1800350c0`

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
0x18000dd04  push    rbp
0x18000dd06  push    rbx
0x18000dd07  push    rsi
0x18000dd08  push    rdi
0x18000dd09  push    r12
0x18000dd0b  push    r14
0x18000dd0d  lea     rbp, [rsp-0F68h]
0x18000dd15  mov     eax, 1068h
0x18000dd1a  call    _alloca_probe
0x18000dd1f  sub     rsp, rax
0x18000dd22  mov     rax, cs:__security_cookie
0x18000dd29  xor     rax, rsp
0x18000dd2c  mov     [rbp+0F90h+var_40], rax
0x18000dd33  mov     rax, [rcx+8]
0x18000dd37  xor     ebx, ebx
0x18000dd39  sub     rax, [rcx]
0x18000dd3c  xor     edi, edi
0x18000dd3e  mov     r14, rcx
0x18000dd41  cmp     rax, 0Ch
0x18000dd45  jb      loc_18000DEA8
0x18000dd4b  xor     esi, esi
0x18000dd4d  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000dd57  xor     edx, edx; Val
0x18000dd59  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000dd5e  mov     r8d, 1000h; Size
0x18000dd64  call    memset_0
0x18000dd69  lea     rax, [rsp+1090h+var_1050]
0x18000dd6e  mov     [rsp+1090h+var_1050], 1000h
0x18000dd76  mov     [rsp+1090h+var_1068], rax
0x18000dd7b  lea     r9, [rsp+1090h+var_104C]
0x18000dd80  lea     rax, [rsp+1090h+var_1040]
0x18000dd85  mov     [rsp+1090h+var_104C], 0
0x18000dd8d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000dd94  mov     [rsp+1090h+var_1070], rax
0x18000dd99  call    wil_details_NtQueryWnfStateData
0x18000dd9e  mov     ebx, eax
0x18000dda0  test    eax, eax
0x18000dda2  jnz     loc_18000DE91
0x18000dda8  mov     r9d, [rsp+1090h+var_1050]
0x18000ddad  mov     rax, r12
0x18000ddb0  mul     r9
0x18000ddb3  shr     rdx, 3
0x18000ddb7  lea     rcx, [rdx+rdx*2]
0x18000ddbb  shl     rcx, 2
0x18000ddbf  cmp     r9, rcx
0x18000ddc2  jz      short loc_18000DDCC
0x18000ddc4  xor     r9d, r9d
0x18000ddc7  mov     [rsp+1090h+var_1050], r9d
0x18000ddcc  mov     r8, [r14]
0x18000ddcf  mov     rax, r12
0x18000ddd2  mov     ecx, r9d
0x18000ddd5  mul     rcx
0x18000ddd8  mov     rcx, [r14+8]
0x18000dddc  mov     rax, r12
0x18000dddf  mov     r11, rdx
0x18000dde2  sub     rcx, r8
0x18000dde5  mul     rcx
0x18000dde8  shr     r11, 3
0x18000ddec  shr     rdx, 3
0x18000ddf0  lea     rax, [rdx+rdx*2]
0x18000ddf4  lea     rdi, [r8+rax*4]
0x18000ddf8  jmp     short loc_18000DE66
0x18000ddfa  mov     eax, r11d
0x18000ddfd  lea     r10, [rsp+1090h+var_1040]
0x18000de02  lea     rcx, [rax+rax*2]
0x18000de06  lea     r10, [r10+rcx*4]
0x18000de0a  cmp     rdx, r10
0x18000de0d  jz      short loc_18000DE35
0x18000de0f  mov     eax, [r8]
0x18000de12  cmp     [rdx], eax
0x18000de14  jnz     short loc_18000DE21
0x18000de16  movzx   eax, word ptr [r8+4]
0x18000de1b  cmp     [rdx+4], ax
0x18000de1f  jz      short loc_18000DE27
0x18000de21  add     rdx, 0Ch
0x18000de25  jmp     short loc_18000DE0A
0x18000de27  mov     eax, [r8+8]
0x18000de2b  add     [rdx+8], eax
0x18000de2e  mov     r9d, [rsp+1090h+var_1050]
0x18000de33  jmp     short loc_18000DE62
0x18000de35  mov     eax, r9d
0x18000de38  add     rax, 0Ch
0x18000de3c  cmp     rax, 1000h
0x18000de42  ja      short loc_18000DE62
0x18000de44  movsd   xmm0, qword ptr [r8]
0x18000de49  add     r9d, 0Ch
0x18000de4d  movsd   qword ptr [r10], xmm0
0x18000de52  inc     r11d
0x18000de55  mov     eax, [r8+8]
0x18000de59  mov     [r10+8], eax
0x18000de5d  mov     [rsp+1090h+var_1050], r9d
0x18000de62  add     r8, 0Ch
0x18000de66  lea     rdx, [rsp+1090h+var_1040]
0x18000de6b  cmp     r8, rdi
0x18000de6e  jnz     short loc_18000DDFA
0x18000de70  mov     eax, [rsp+1090h+var_104C]
0x18000de74  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000de7b  mov     [rsp+1090h+var_1060], 1
0x18000de83  mov     r8d, r9d
0x18000de86  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000de8a  call    wil_details_NtUpdateWnfStateData
0x18000de8f  mov     edi, eax
0x18000de91  cmp     edi, 0C0000001h
0x18000de97  jnz     short loc_18000DEA8
0x18000de99  inc     esi
0x18000de9b  cmp     esi, 64h ; 'd'
0x18000de9e  jge     short loc_18000DEA8
0x18000dea0  test    ebx, ebx
0x18000dea2  jz      loc_18000DD57
0x18000dea8  test    ebx, ebx
0x18000deaa  cmovz   ebx, edi
0x18000dead  mov     eax, ebx
0x18000deaf  mov     rcx, [rbp+0F90h+var_40]
0x18000deb6  xor     rcx, rsp; StackCookie
0x18000deb9  call    __security_check_cookie
0x18000debe  add     rsp, 1068h
0x18000dec5  pop     r14
0x18000dec7  pop     r12
0x18000dec9  pop     rdi
0x18000deca  pop     rsi
0x18000decb  pop     rbx
0x18000decc  pop     rbp
0x18000decd  retn
```
