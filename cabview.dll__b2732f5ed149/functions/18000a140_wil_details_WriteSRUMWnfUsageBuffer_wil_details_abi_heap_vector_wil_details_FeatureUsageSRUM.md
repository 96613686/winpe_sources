# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a140`
- end: `0x18000a30a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800030d0`

## callees

- `0x180002620`
- `0x180002f40`
- `0x18000a140`
- `0x18000a9ec`
- `0x18000aa64`
- `0x180012a20`

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
0x18000a140  push    rbp
0x18000a142  push    rbx
0x18000a143  push    rsi
0x18000a144  push    rdi
0x18000a145  push    r12
0x18000a147  push    r14
0x18000a149  lea     rbp, [rsp-0F68h]
0x18000a151  mov     eax, 1068h
0x18000a156  call    _alloca_probe
0x18000a15b  sub     rsp, rax
0x18000a15e  mov     rax, cs:__security_cookie
0x18000a165  xor     rax, rsp
0x18000a168  mov     [rbp+0F90h+var_40], rax
0x18000a16f  mov     rax, [rcx+8]
0x18000a173  xor     ebx, ebx
0x18000a175  sub     rax, [rcx]
0x18000a178  xor     edi, edi
0x18000a17a  mov     r14, rcx
0x18000a17d  cmp     rax, 0Ch
0x18000a181  jb      loc_18000A2E4
0x18000a187  xor     esi, esi
0x18000a189  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000a193  xor     edx, edx; Val
0x18000a195  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a19a  mov     r8d, 1000h; Size
0x18000a1a0  call    memset_0
0x18000a1a5  lea     rax, [rsp+1090h+var_1050]
0x18000a1aa  mov     [rsp+1090h+var_1050], 1000h
0x18000a1b2  mov     [rsp+1090h+var_1068], rax
0x18000a1b7  lea     r9, [rsp+1090h+var_104C]
0x18000a1bc  lea     rax, [rsp+1090h+var_1040]
0x18000a1c1  mov     [rsp+1090h+var_104C], 0
0x18000a1c9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a1d0  mov     [rsp+1090h+var_1070], rax
0x18000a1d5  call    wil_details_NtQueryWnfStateData
0x18000a1da  mov     ebx, eax
0x18000a1dc  test    eax, eax
0x18000a1de  jnz     loc_18000A2CD
0x18000a1e4  mov     r9d, [rsp+1090h+var_1050]
0x18000a1e9  mov     rax, r12
0x18000a1ec  mul     r9
0x18000a1ef  shr     rdx, 3
0x18000a1f3  lea     rcx, [rdx+rdx*2]
0x18000a1f7  shl     rcx, 2
0x18000a1fb  cmp     r9, rcx
0x18000a1fe  jz      short loc_18000A208
0x18000a200  xor     r9d, r9d
0x18000a203  mov     [rsp+1090h+var_1050], r9d
0x18000a208  mov     r8, [r14]
0x18000a20b  mov     rax, r12
0x18000a20e  mov     ecx, r9d
0x18000a211  mul     rcx
0x18000a214  mov     rcx, [r14+8]
0x18000a218  mov     rax, r12
0x18000a21b  mov     r11, rdx
0x18000a21e  sub     rcx, r8
0x18000a221  mul     rcx
0x18000a224  shr     r11, 3
0x18000a228  shr     rdx, 3
0x18000a22c  lea     rax, [rdx+rdx*2]
0x18000a230  lea     rdi, [r8+rax*4]
0x18000a234  jmp     short loc_18000A2A2
0x18000a236  mov     eax, r11d
0x18000a239  lea     r10, [rsp+1090h+var_1040]
0x18000a23e  lea     rcx, [rax+rax*2]
0x18000a242  lea     r10, [r10+rcx*4]
0x18000a246  cmp     rdx, r10
0x18000a249  jz      short loc_18000A271
0x18000a24b  mov     eax, [r8]
0x18000a24e  cmp     [rdx], eax
0x18000a250  jnz     short loc_18000A25D
0x18000a252  movzx   eax, word ptr [r8+4]
0x18000a257  cmp     [rdx+4], ax
0x18000a25b  jz      short loc_18000A263
0x18000a25d  add     rdx, 0Ch
0x18000a261  jmp     short loc_18000A246
0x18000a263  mov     eax, [r8+8]
0x18000a267  add     [rdx+8], eax
0x18000a26a  mov     r9d, [rsp+1090h+var_1050]
0x18000a26f  jmp     short loc_18000A29E
0x18000a271  mov     eax, r9d
0x18000a274  add     rax, 0Ch
0x18000a278  cmp     rax, 1000h
0x18000a27e  ja      short loc_18000A29E
0x18000a280  movsd   xmm0, qword ptr [r8]
0x18000a285  add     r9d, 0Ch
0x18000a289  movsd   qword ptr [r10], xmm0
0x18000a28e  inc     r11d
0x18000a291  mov     eax, [r8+8]
0x18000a295  mov     [r10+8], eax
0x18000a299  mov     [rsp+1090h+var_1050], r9d
0x18000a29e  add     r8, 0Ch
0x18000a2a2  lea     rdx, [rsp+1090h+var_1040]
0x18000a2a7  cmp     r8, rdi
0x18000a2aa  jnz     short loc_18000A236
0x18000a2ac  mov     eax, [rsp+1090h+var_104C]
0x18000a2b0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a2b7  mov     [rsp+1090h+var_1060], 1
0x18000a2bf  mov     r8d, r9d
0x18000a2c2  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a2c6  call    wil_details_NtUpdateWnfStateData
0x18000a2cb  mov     edi, eax
0x18000a2cd  cmp     edi, 0C0000001h
0x18000a2d3  jnz     short loc_18000A2E4
0x18000a2d5  inc     esi
0x18000a2d7  cmp     esi, 64h ; 'd'
0x18000a2da  jge     short loc_18000A2E4
0x18000a2dc  test    ebx, ebx
0x18000a2de  jz      loc_18000A193
0x18000a2e4  test    ebx, ebx
0x18000a2e6  cmovz   ebx, edi
0x18000a2e9  mov     eax, ebx
0x18000a2eb  mov     rcx, [rbp+0F90h+var_40]
0x18000a2f2  xor     rcx, rsp; StackCookie
0x18000a2f5  call    __security_check_cookie
0x18000a2fa  add     rsp, 1068h
0x18000a301  pop     r14
0x18000a303  pop     r12
0x18000a305  pop     rdi
0x18000a306  pop     rsi
0x18000a307  pop     rbx
0x18000a308  pop     rbp
0x18000a309  retn
```
