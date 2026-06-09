# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001acc8`
- end: `0x18001ae9d`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180015260`

## callees

- `0x180014130`
- `0x180014ff0`
- `0x18001acc8`
- `0x18001b11c`
- `0x18001b194`
- `0x180023310`

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
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
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
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
            if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
            {
              v7 = (unsigned int)(v7 + 12);
              *(_QWORD *)v11 = *(_QWORD *)v8;
              ++v9;
              v11[2] = *(_DWORD *)(v8 + 8);
              v15 = v7;
            }
          }
          else
          {
            v12 = v17;
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_12;
            }
            v12[2] += *(_DWORD *)(v8 + 8);
            v7 = v15;
          }
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
0x18001acc8  push    rbp
0x18001acca  push    rbx
0x18001accb  push    rsi
0x18001accc  push    rdi
0x18001accd  push    r12
0x18001accf  push    r14
0x18001acd1  lea     rbp, [rsp-0F68h]
0x18001acd9  mov     eax, 1068h
0x18001acde  call    _alloca_probe
0x18001ace3  sub     rsp, rax
0x18001ace6  mov     rax, cs:__security_cookie
0x18001aced  xor     rax, rsp
0x18001acf0  mov     [rbp+0F90h+var_40], rax
0x18001acf7  mov     rax, [rcx+8]
0x18001acfb  xor     ebx, ebx
0x18001acfd  sub     rax, [rcx]
0x18001ad00  xor     edi, edi
0x18001ad02  mov     r14, rcx
0x18001ad05  cmp     rax, 0Ch
0x18001ad09  jb      loc_18001AE69
0x18001ad0f  xor     esi, esi
0x18001ad11  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001ad1b  xor     edx, edx; Val
0x18001ad1d  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001ad22  mov     r8d, 1000h; Size
0x18001ad28  call    memset_0
0x18001ad2d  lea     rax, [rsp+1090h+var_1050]
0x18001ad32  mov     [rsp+1090h+var_1050], 1000h
0x18001ad3a  mov     [rsp+1090h+var_1068], rax
0x18001ad3f  lea     r9, [rsp+1090h+var_104C]
0x18001ad44  lea     rax, [rsp+1090h+var_1040]
0x18001ad49  mov     [rsp+1090h+var_104C], 0
0x18001ad51  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ad58  mov     [rsp+1090h+var_1070], rax
0x18001ad5d  call    wil_details_NtQueryWnfStateData
0x18001ad62  mov     ebx, eax
0x18001ad64  test    eax, eax
0x18001ad66  jnz     loc_18001AE52
0x18001ad6c  mov     r9d, [rsp+1090h+var_1050]
0x18001ad71  mov     rax, r12
0x18001ad74  mul     r9
0x18001ad77  shr     rdx, 3
0x18001ad7b  lea     rcx, [rdx+rdx*2]
0x18001ad7f  shl     rcx, 2
0x18001ad83  cmp     r9, rcx
0x18001ad86  jz      short loc_18001AD90
0x18001ad88  xor     r9d, r9d
0x18001ad8b  mov     [rsp+1090h+var_1050], r9d
0x18001ad90  mov     r8, [r14]
0x18001ad93  mov     rax, r12
0x18001ad96  mov     ecx, r9d
0x18001ad99  mul     rcx
0x18001ad9c  mov     rcx, [r14+8]
0x18001ada0  mov     rax, r12
0x18001ada3  mov     r10, rdx
0x18001ada6  sub     rcx, r8
0x18001ada9  mul     rcx
0x18001adac  shr     r10, 3
0x18001adb0  shr     rdx, 3
0x18001adb4  lea     rax, [rdx+rdx*2]
0x18001adb8  lea     rdi, [r8+rax*4]
0x18001adbc  jmp     short loc_18001AE27
0x18001adbe  mov     eax, r10d
0x18001adc1  lea     rcx, [rax+rax*2]
0x18001adc5  lea     rdx, [rdx+rcx*4]
0x18001adc9  lea     rax, [rsp+1090h+var_1040]
0x18001adce  cmp     rax, rdx
0x18001add1  jz      short loc_18001ADF8
0x18001add3  mov     r11d, [r8]
0x18001add6  lea     rcx, [rsp+1090h+var_1040]
0x18001addb  cmp     [rcx], r11d
0x18001adde  jnz     short loc_18001ADEF
0x18001ade0  movzx   eax, word ptr [r8+4]
0x18001ade5  cmp     [rcx+4], ax
0x18001ade9  jz      loc_18001AE8F
0x18001adef  add     rcx, 0Ch
0x18001adf3  cmp     rcx, rdx
0x18001adf6  jnz     short loc_18001ADDB
0x18001adf8  mov     eax, r9d
0x18001adfb  add     rax, 0Ch
0x18001adff  cmp     rax, 1000h
0x18001ae05  ja      short loc_18001AE23
0x18001ae07  movsd   xmm0, qword ptr [r8]
0x18001ae0c  add     r9d, 0Ch
0x18001ae10  movsd   qword ptr [rdx], xmm0
0x18001ae14  inc     r10d
0x18001ae17  mov     eax, [r8+8]
0x18001ae1b  mov     [rdx+8], eax
0x18001ae1e  mov     [rsp+1090h+var_1050], r9d
0x18001ae23  add     r8, 0Ch
0x18001ae27  lea     rdx, [rsp+1090h+var_1040]
0x18001ae2c  cmp     r8, rdi
0x18001ae2f  jnz     short loc_18001ADBE
0x18001ae31  mov     eax, [rsp+1090h+var_104C]
0x18001ae35  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ae3c  mov     [rsp+1090h+var_1060], 1
0x18001ae44  mov     r8d, r9d
0x18001ae47  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001ae4b  call    wil_details_NtUpdateWnfStateData
0x18001ae50  mov     edi, eax
0x18001ae52  cmp     edi, 0C0000001h
0x18001ae58  jnz     short loc_18001AE69
0x18001ae5a  inc     esi
0x18001ae5c  cmp     esi, 64h ; 'd'
0x18001ae5f  jge     short loc_18001AE69
0x18001ae61  test    ebx, ebx
0x18001ae63  jz      loc_18001AD1B
0x18001ae69  test    ebx, ebx
0x18001ae6b  cmovz   ebx, edi
0x18001ae6e  mov     eax, ebx
0x18001ae70  mov     rcx, [rbp+0F90h+var_40]
0x18001ae77  xor     rcx, rsp; StackCookie
0x18001ae7a  call    __security_check_cookie
0x18001ae7f  add     rsp, 1068h
0x18001ae86  pop     r14
0x18001ae88  pop     r12
0x18001ae8a  pop     rdi
0x18001ae8b  pop     rsi
0x18001ae8c  pop     rbx
0x18001ae8d  pop     rbp
0x18001ae8e  retn
0x18001ae8f  mov     eax, [r8+8]
0x18001ae93  add     [rcx+8], eax
0x18001ae96  mov     r9d, [rsp+1090h+var_1050]
0x18001ae9b  jmp     short loc_18001AE23
```
