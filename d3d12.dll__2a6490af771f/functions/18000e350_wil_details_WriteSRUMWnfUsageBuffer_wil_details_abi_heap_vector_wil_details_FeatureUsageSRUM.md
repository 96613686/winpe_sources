# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000e350`
- end: `0x18000e51a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c360`

## callees

- `0x18000a228`
- `0x18000a320`
- `0x18000b410`
- `0x18000be78`
- `0x18000e350`
- `0x180013a50`

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
0x18000e350  push    rbp
0x18000e352  push    rbx
0x18000e353  push    rsi
0x18000e354  push    rdi
0x18000e355  push    r12
0x18000e357  push    r14
0x18000e359  lea     rbp, [rsp-0F68h]
0x18000e361  mov     eax, 1068h
0x18000e366  call    _alloca_probe
0x18000e36b  sub     rsp, rax
0x18000e36e  mov     rax, cs:__security_cookie
0x18000e375  xor     rax, rsp
0x18000e378  mov     [rbp+0F90h+var_40], rax
0x18000e37f  mov     rax, [rcx+8]
0x18000e383  xor     ebx, ebx
0x18000e385  sub     rax, [rcx]
0x18000e388  xor     edi, edi
0x18000e38a  mov     r14, rcx
0x18000e38d  cmp     rax, 0Ch
0x18000e391  jb      loc_18000E4F4
0x18000e397  xor     esi, esi
0x18000e399  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000e3a3  xor     edx, edx; Val
0x18000e3a5  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000e3aa  mov     r8d, 1000h; Size
0x18000e3b0  call    memset_0
0x18000e3b5  lea     rax, [rsp+1090h+var_1050]
0x18000e3ba  mov     [rsp+1090h+var_1050], 1000h
0x18000e3c2  mov     [rsp+1090h+var_1068], rax
0x18000e3c7  lea     r9, [rsp+1090h+var_104C]
0x18000e3cc  lea     rax, [rsp+1090h+var_1040]
0x18000e3d1  mov     [rsp+1090h+var_104C], 0
0x18000e3d9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e3e0  mov     [rsp+1090h+var_1070], rax
0x18000e3e5  call    wil_details_NtQueryWnfStateData
0x18000e3ea  mov     ebx, eax
0x18000e3ec  test    eax, eax
0x18000e3ee  jnz     loc_18000E4DD
0x18000e3f4  mov     r9d, [rsp+1090h+var_1050]
0x18000e3f9  mov     rax, r12
0x18000e3fc  mul     r9
0x18000e3ff  shr     rdx, 3
0x18000e403  lea     rcx, [rdx+rdx*2]
0x18000e407  shl     rcx, 2
0x18000e40b  cmp     r9, rcx
0x18000e40e  jz      short loc_18000E418
0x18000e410  xor     r9d, r9d
0x18000e413  mov     [rsp+1090h+var_1050], r9d
0x18000e418  mov     r8, [r14]
0x18000e41b  mov     rax, r12
0x18000e41e  mov     ecx, r9d
0x18000e421  mul     rcx
0x18000e424  mov     rcx, [r14+8]
0x18000e428  mov     rax, r12
0x18000e42b  mov     r11, rdx
0x18000e42e  sub     rcx, r8
0x18000e431  mul     rcx
0x18000e434  shr     r11, 3
0x18000e438  shr     rdx, 3
0x18000e43c  lea     rax, [rdx+rdx*2]
0x18000e440  lea     rdi, [r8+rax*4]
0x18000e444  jmp     short loc_18000E4B2
0x18000e446  mov     eax, r11d
0x18000e449  lea     r10, [rsp+1090h+var_1040]
0x18000e44e  lea     rcx, [rax+rax*2]
0x18000e452  lea     r10, [r10+rcx*4]
0x18000e456  cmp     rdx, r10
0x18000e459  jz      short loc_18000E481
0x18000e45b  mov     eax, [r8]
0x18000e45e  cmp     [rdx], eax
0x18000e460  jnz     short loc_18000E46D
0x18000e462  movzx   eax, word ptr [r8+4]
0x18000e467  cmp     [rdx+4], ax
0x18000e46b  jz      short loc_18000E473
0x18000e46d  add     rdx, 0Ch
0x18000e471  jmp     short loc_18000E456
0x18000e473  mov     eax, [r8+8]
0x18000e477  add     [rdx+8], eax
0x18000e47a  mov     r9d, [rsp+1090h+var_1050]
0x18000e47f  jmp     short loc_18000E4AE
0x18000e481  mov     eax, r9d
0x18000e484  add     rax, 0Ch
0x18000e488  cmp     rax, 1000h
0x18000e48e  ja      short loc_18000E4AE
0x18000e490  movsd   xmm0, qword ptr [r8]
0x18000e495  add     r9d, 0Ch
0x18000e499  movsd   qword ptr [r10], xmm0
0x18000e49e  inc     r11d
0x18000e4a1  mov     eax, [r8+8]
0x18000e4a5  mov     [r10+8], eax
0x18000e4a9  mov     [rsp+1090h+var_1050], r9d
0x18000e4ae  add     r8, 0Ch
0x18000e4b2  lea     rdx, [rsp+1090h+var_1040]
0x18000e4b7  cmp     r8, rdi
0x18000e4ba  jnz     short loc_18000E446
0x18000e4bc  mov     eax, [rsp+1090h+var_104C]
0x18000e4c0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e4c7  mov     [rsp+1090h+var_1060], 1
0x18000e4cf  mov     r8d, r9d
0x18000e4d2  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000e4d6  call    wil_details_NtUpdateWnfStateData
0x18000e4db  mov     edi, eax
0x18000e4dd  cmp     edi, 0C0000001h
0x18000e4e3  jnz     short loc_18000E4F4
0x18000e4e5  inc     esi
0x18000e4e7  cmp     esi, 64h ; 'd'
0x18000e4ea  jge     short loc_18000E4F4
0x18000e4ec  test    ebx, ebx
0x18000e4ee  jz      loc_18000E3A3
0x18000e4f4  test    ebx, ebx
0x18000e4f6  cmovz   ebx, edi
0x18000e4f9  mov     eax, ebx
0x18000e4fb  mov     rcx, [rbp+0F90h+var_40]
0x18000e502  xor     rcx, rsp; StackCookie
0x18000e505  call    __security_check_cookie
0x18000e50a  add     rsp, 1068h
0x18000e511  pop     r14
0x18000e513  pop     r12
0x18000e515  pop     rdi
0x18000e516  pop     rsi
0x18000e517  pop     rbx
0x18000e518  pop     rbp
0x18000e519  retn
```
