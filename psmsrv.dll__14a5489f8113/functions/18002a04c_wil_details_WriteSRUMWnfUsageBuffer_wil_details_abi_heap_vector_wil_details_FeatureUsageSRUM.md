# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002a04c`
- end: `0x18002a216`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180025940`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x18002a04c`
- `0x18002cc04`
- `0x18002cc7c`
- `0x18002e110`

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
0x18002a04c  push    rbp
0x18002a04e  push    rbx
0x18002a04f  push    rsi
0x18002a050  push    rdi
0x18002a051  push    r12
0x18002a053  push    r14
0x18002a055  lea     rbp, [rsp-0F68h]
0x18002a05d  mov     eax, 1068h
0x18002a062  call    _alloca_probe
0x18002a067  sub     rsp, rax
0x18002a06a  mov     rax, cs:__security_cookie
0x18002a071  xor     rax, rsp
0x18002a074  mov     [rbp+0F90h+var_40], rax
0x18002a07b  mov     rax, [rcx+8]
0x18002a07f  xor     ebx, ebx
0x18002a081  sub     rax, [rcx]
0x18002a084  xor     edi, edi
0x18002a086  mov     r14, rcx
0x18002a089  cmp     rax, 0Ch
0x18002a08d  jb      loc_18002A1F0
0x18002a093  xor     esi, esi
0x18002a095  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002a09f  xor     edx, edx; Val
0x18002a0a1  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002a0a6  mov     r8d, 1000h; Size
0x18002a0ac  call    memset_0
0x18002a0b1  lea     rax, [rsp+1090h+var_1050]
0x18002a0b6  mov     [rsp+1090h+var_1050], 1000h
0x18002a0be  mov     [rsp+1090h+var_1068], rax
0x18002a0c3  lea     r9, [rsp+1090h+var_104C]
0x18002a0c8  lea     rax, [rsp+1090h+var_1040]
0x18002a0cd  mov     [rsp+1090h+var_104C], 0
0x18002a0d5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002a0dc  mov     [rsp+1090h+var_1070], rax
0x18002a0e1  call    wil_details_NtQueryWnfStateData
0x18002a0e6  mov     ebx, eax
0x18002a0e8  test    eax, eax
0x18002a0ea  jnz     loc_18002A1D9
0x18002a0f0  mov     r9d, [rsp+1090h+var_1050]
0x18002a0f5  mov     rax, r12
0x18002a0f8  mul     r9
0x18002a0fb  shr     rdx, 3
0x18002a0ff  lea     rcx, [rdx+rdx*2]
0x18002a103  shl     rcx, 2
0x18002a107  cmp     r9, rcx
0x18002a10a  jz      short loc_18002A114
0x18002a10c  xor     r9d, r9d
0x18002a10f  mov     [rsp+1090h+var_1050], r9d
0x18002a114  mov     r8, [r14]
0x18002a117  mov     rax, r12
0x18002a11a  mov     ecx, r9d
0x18002a11d  mul     rcx
0x18002a120  mov     rcx, [r14+8]
0x18002a124  mov     rax, r12
0x18002a127  mov     r11, rdx
0x18002a12a  sub     rcx, r8
0x18002a12d  mul     rcx
0x18002a130  shr     r11, 3
0x18002a134  shr     rdx, 3
0x18002a138  lea     rax, [rdx+rdx*2]
0x18002a13c  lea     rdi, [r8+rax*4]
0x18002a140  jmp     short loc_18002A1AE
0x18002a142  mov     eax, r11d
0x18002a145  lea     r10, [rsp+1090h+var_1040]
0x18002a14a  lea     rcx, [rax+rax*2]
0x18002a14e  lea     r10, [r10+rcx*4]
0x18002a152  cmp     rdx, r10
0x18002a155  jz      short loc_18002A17D
0x18002a157  mov     eax, [r8]
0x18002a15a  cmp     [rdx], eax
0x18002a15c  jnz     short loc_18002A169
0x18002a15e  movzx   eax, word ptr [r8+4]
0x18002a163  cmp     [rdx+4], ax
0x18002a167  jz      short loc_18002A16F
0x18002a169  add     rdx, 0Ch
0x18002a16d  jmp     short loc_18002A152
0x18002a16f  mov     eax, [r8+8]
0x18002a173  add     [rdx+8], eax
0x18002a176  mov     r9d, [rsp+1090h+var_1050]
0x18002a17b  jmp     short loc_18002A1AA
0x18002a17d  mov     eax, r9d
0x18002a180  add     rax, 0Ch
0x18002a184  cmp     rax, 1000h
0x18002a18a  ja      short loc_18002A1AA
0x18002a18c  movsd   xmm0, qword ptr [r8]
0x18002a191  add     r9d, 0Ch
0x18002a195  movsd   qword ptr [r10], xmm0
0x18002a19a  inc     r11d
0x18002a19d  mov     eax, [r8+8]
0x18002a1a1  mov     [r10+8], eax
0x18002a1a5  mov     [rsp+1090h+var_1050], r9d
0x18002a1aa  add     r8, 0Ch
0x18002a1ae  lea     rdx, [rsp+1090h+var_1040]
0x18002a1b3  cmp     r8, rdi
0x18002a1b6  jnz     short loc_18002A142
0x18002a1b8  mov     eax, [rsp+1090h+var_104C]
0x18002a1bc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002a1c3  mov     [rsp+1090h+var_1060], 1
0x18002a1cb  mov     r8d, r9d
0x18002a1ce  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002a1d2  call    wil_details_NtUpdateWnfStateData
0x18002a1d7  mov     edi, eax
0x18002a1d9  cmp     edi, 0C0000001h
0x18002a1df  jnz     short loc_18002A1F0
0x18002a1e1  inc     esi
0x18002a1e3  cmp     esi, 64h ; 'd'
0x18002a1e6  jge     short loc_18002A1F0
0x18002a1e8  test    ebx, ebx
0x18002a1ea  jz      loc_18002A09F
0x18002a1f0  test    ebx, ebx
0x18002a1f2  cmovz   ebx, edi
0x18002a1f5  mov     eax, ebx
0x18002a1f7  mov     rcx, [rbp+0F90h+var_40]
0x18002a1fe  xor     rcx, rsp; StackCookie
0x18002a201  call    __security_check_cookie
0x18002a206  add     rsp, 1068h
0x18002a20d  pop     r14
0x18002a20f  pop     r12
0x18002a211  pop     rdi
0x18002a212  pop     rsi
0x18002a213  pop     rbx
0x18002a214  pop     rbp
0x18002a215  retn
```
