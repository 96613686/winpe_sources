# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a168`
- end: `0x18000a332`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180004f80`

## callees

- `0x18000a168`
- `0x18000a448`
- `0x18000a4c0`
- `0x18000ac8e`
- `0x18000ad30`
- `0x18000adf0`

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
0x18000a168  push    rbp
0x18000a16a  push    rbx
0x18000a16b  push    rsi
0x18000a16c  push    rdi
0x18000a16d  push    r12
0x18000a16f  push    r14
0x18000a171  lea     rbp, [rsp-0F68h]
0x18000a179  mov     eax, 1068h
0x18000a17e  call    _alloca_probe
0x18000a183  sub     rsp, rax
0x18000a186  mov     rax, cs:__security_cookie
0x18000a18d  xor     rax, rsp
0x18000a190  mov     [rbp+0F90h+var_40], rax
0x18000a197  mov     rax, [rcx+8]
0x18000a19b  xor     ebx, ebx
0x18000a19d  sub     rax, [rcx]
0x18000a1a0  xor     edi, edi
0x18000a1a2  mov     r14, rcx
0x18000a1a5  cmp     rax, 0Ch
0x18000a1a9  jb      loc_18000A30C
0x18000a1af  xor     esi, esi
0x18000a1b1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000a1bb  xor     edx, edx; Val
0x18000a1bd  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a1c2  mov     r8d, 1000h; Size
0x18000a1c8  call    memset_0
0x18000a1cd  lea     rax, [rsp+1090h+var_1050]
0x18000a1d2  mov     [rsp+1090h+var_1050], 1000h
0x18000a1da  mov     [rsp+1090h+var_1068], rax
0x18000a1df  lea     r9, [rsp+1090h+var_104C]
0x18000a1e4  lea     rax, [rsp+1090h+var_1040]
0x18000a1e9  mov     [rsp+1090h+var_104C], 0
0x18000a1f1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a1f8  mov     [rsp+1090h+var_1070], rax
0x18000a1fd  call    wil_details_NtQueryWnfStateData
0x18000a202  mov     ebx, eax
0x18000a204  test    eax, eax
0x18000a206  jnz     loc_18000A2F5
0x18000a20c  mov     r9d, [rsp+1090h+var_1050]
0x18000a211  mov     rax, r12
0x18000a214  mul     r9
0x18000a217  shr     rdx, 3
0x18000a21b  lea     rcx, [rdx+rdx*2]
0x18000a21f  shl     rcx, 2
0x18000a223  cmp     r9, rcx
0x18000a226  jz      short loc_18000A230
0x18000a228  xor     r9d, r9d
0x18000a22b  mov     [rsp+1090h+var_1050], r9d
0x18000a230  mov     r8, [r14]
0x18000a233  mov     rax, r12
0x18000a236  mov     ecx, r9d
0x18000a239  mul     rcx
0x18000a23c  mov     rcx, [r14+8]
0x18000a240  mov     rax, r12
0x18000a243  mov     r11, rdx
0x18000a246  sub     rcx, r8
0x18000a249  mul     rcx
0x18000a24c  shr     r11, 3
0x18000a250  shr     rdx, 3
0x18000a254  lea     rax, [rdx+rdx*2]
0x18000a258  lea     rdi, [r8+rax*4]
0x18000a25c  jmp     short loc_18000A2CA
0x18000a25e  mov     eax, r11d
0x18000a261  lea     r10, [rsp+1090h+var_1040]
0x18000a266  lea     rcx, [rax+rax*2]
0x18000a26a  lea     r10, [r10+rcx*4]
0x18000a26e  cmp     rdx, r10
0x18000a271  jz      short loc_18000A299
0x18000a273  mov     eax, [r8]
0x18000a276  cmp     [rdx], eax
0x18000a278  jnz     short loc_18000A285
0x18000a27a  movzx   eax, word ptr [r8+4]
0x18000a27f  cmp     [rdx+4], ax
0x18000a283  jz      short loc_18000A28B
0x18000a285  add     rdx, 0Ch
0x18000a289  jmp     short loc_18000A26E
0x18000a28b  mov     eax, [r8+8]
0x18000a28f  add     [rdx+8], eax
0x18000a292  mov     r9d, [rsp+1090h+var_1050]
0x18000a297  jmp     short loc_18000A2C6
0x18000a299  mov     eax, r9d
0x18000a29c  add     rax, 0Ch
0x18000a2a0  cmp     rax, 1000h
0x18000a2a6  ja      short loc_18000A2C6
0x18000a2a8  movsd   xmm0, qword ptr [r8]
0x18000a2ad  add     r9d, 0Ch
0x18000a2b1  movsd   qword ptr [r10], xmm0
0x18000a2b6  inc     r11d
0x18000a2b9  mov     eax, [r8+8]
0x18000a2bd  mov     [r10+8], eax
0x18000a2c1  mov     [rsp+1090h+var_1050], r9d
0x18000a2c6  add     r8, 0Ch
0x18000a2ca  lea     rdx, [rsp+1090h+var_1040]
0x18000a2cf  cmp     r8, rdi
0x18000a2d2  jnz     short loc_18000A25E
0x18000a2d4  mov     eax, [rsp+1090h+var_104C]
0x18000a2d8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a2df  mov     [rsp+1090h+var_1060], 1
0x18000a2e7  mov     r8d, r9d
0x18000a2ea  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a2ee  call    wil_details_NtUpdateWnfStateData
0x18000a2f3  mov     edi, eax
0x18000a2f5  cmp     edi, 0C0000001h
0x18000a2fb  jnz     short loc_18000A30C
0x18000a2fd  inc     esi
0x18000a2ff  cmp     esi, 64h ; 'd'
0x18000a302  jge     short loc_18000A30C
0x18000a304  test    ebx, ebx
0x18000a306  jz      loc_18000A1BB
0x18000a30c  test    ebx, ebx
0x18000a30e  cmovz   ebx, edi
0x18000a311  mov     eax, ebx
0x18000a313  mov     rcx, [rbp+0F90h+var_40]
0x18000a31a  xor     rcx, rsp; StackCookie
0x18000a31d  call    __security_check_cookie
0x18000a322  add     rsp, 1068h
0x18000a329  pop     r14
0x18000a32b  pop     r12
0x18000a32d  pop     rdi
0x18000a32e  pop     rsi
0x18000a32f  pop     rbx
0x18000a330  pop     rbp
0x18000a331  retn
```
