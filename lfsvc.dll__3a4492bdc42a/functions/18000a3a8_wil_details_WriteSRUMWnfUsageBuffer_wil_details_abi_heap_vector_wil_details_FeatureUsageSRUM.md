# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a3a8`
- end: `0x18000a572`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180004e80`

## callees

- `0x180004310`
- `0x180004d48`
- `0x18000a3a8`
- `0x18000a6ac`
- `0x18000a724`
- `0x18000b360`

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
0x18000a3a8  push    rbp
0x18000a3aa  push    rbx
0x18000a3ab  push    rsi
0x18000a3ac  push    rdi
0x18000a3ad  push    r12
0x18000a3af  push    r14
0x18000a3b1  lea     rbp, [rsp-0F68h]
0x18000a3b9  mov     eax, 1068h
0x18000a3be  call    _alloca_probe
0x18000a3c3  sub     rsp, rax
0x18000a3c6  mov     rax, cs:__security_cookie
0x18000a3cd  xor     rax, rsp
0x18000a3d0  mov     [rbp+0F90h+var_40], rax
0x18000a3d7  mov     rax, [rcx+8]
0x18000a3db  xor     ebx, ebx
0x18000a3dd  sub     rax, [rcx]
0x18000a3e0  xor     edi, edi
0x18000a3e2  mov     r14, rcx
0x18000a3e5  cmp     rax, 0Ch
0x18000a3e9  jb      loc_18000A54C
0x18000a3ef  xor     esi, esi
0x18000a3f1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000a3fb  xor     edx, edx; Val
0x18000a3fd  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a402  mov     r8d, 1000h; Size
0x18000a408  call    memset_0
0x18000a40d  lea     rax, [rsp+1090h+var_1050]
0x18000a412  mov     [rsp+1090h+var_1050], 1000h
0x18000a41a  mov     [rsp+1090h+var_1068], rax
0x18000a41f  lea     r9, [rsp+1090h+var_104C]
0x18000a424  lea     rax, [rsp+1090h+var_1040]
0x18000a429  mov     [rsp+1090h+var_104C], 0
0x18000a431  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a438  mov     [rsp+1090h+var_1070], rax
0x18000a43d  call    wil_details_NtQueryWnfStateData
0x18000a442  mov     ebx, eax
0x18000a444  test    eax, eax
0x18000a446  jnz     loc_18000A535
0x18000a44c  mov     r9d, [rsp+1090h+var_1050]
0x18000a451  mov     rax, r12
0x18000a454  mul     r9
0x18000a457  shr     rdx, 3
0x18000a45b  lea     rcx, [rdx+rdx*2]
0x18000a45f  shl     rcx, 2
0x18000a463  cmp     r9, rcx
0x18000a466  jz      short loc_18000A470
0x18000a468  xor     r9d, r9d
0x18000a46b  mov     [rsp+1090h+var_1050], r9d
0x18000a470  mov     r8, [r14]
0x18000a473  mov     rax, r12
0x18000a476  mov     ecx, r9d
0x18000a479  mul     rcx
0x18000a47c  mov     rcx, [r14+8]
0x18000a480  mov     rax, r12
0x18000a483  mov     r11, rdx
0x18000a486  sub     rcx, r8
0x18000a489  mul     rcx
0x18000a48c  shr     r11, 3
0x18000a490  shr     rdx, 3
0x18000a494  lea     rax, [rdx+rdx*2]
0x18000a498  lea     rdi, [r8+rax*4]
0x18000a49c  jmp     short loc_18000A50A
0x18000a49e  mov     eax, r11d
0x18000a4a1  lea     r10, [rsp+1090h+var_1040]
0x18000a4a6  lea     rcx, [rax+rax*2]
0x18000a4aa  lea     r10, [r10+rcx*4]
0x18000a4ae  cmp     rdx, r10
0x18000a4b1  jz      short loc_18000A4D9
0x18000a4b3  mov     eax, [r8]
0x18000a4b6  cmp     [rdx], eax
0x18000a4b8  jnz     short loc_18000A4C5
0x18000a4ba  movzx   eax, word ptr [r8+4]
0x18000a4bf  cmp     [rdx+4], ax
0x18000a4c3  jz      short loc_18000A4CB
0x18000a4c5  add     rdx, 0Ch
0x18000a4c9  jmp     short loc_18000A4AE
0x18000a4cb  mov     eax, [r8+8]
0x18000a4cf  add     [rdx+8], eax
0x18000a4d2  mov     r9d, [rsp+1090h+var_1050]
0x18000a4d7  jmp     short loc_18000A506
0x18000a4d9  mov     eax, r9d
0x18000a4dc  add     rax, 0Ch
0x18000a4e0  cmp     rax, 1000h
0x18000a4e6  ja      short loc_18000A506
0x18000a4e8  movsd   xmm0, qword ptr [r8]
0x18000a4ed  add     r9d, 0Ch
0x18000a4f1  movsd   qword ptr [r10], xmm0
0x18000a4f6  inc     r11d
0x18000a4f9  mov     eax, [r8+8]
0x18000a4fd  mov     [r10+8], eax
0x18000a501  mov     [rsp+1090h+var_1050], r9d
0x18000a506  add     r8, 0Ch
0x18000a50a  lea     rdx, [rsp+1090h+var_1040]
0x18000a50f  cmp     r8, rdi
0x18000a512  jnz     short loc_18000A49E
0x18000a514  mov     eax, [rsp+1090h+var_104C]
0x18000a518  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a51f  mov     [rsp+1090h+var_1060], 1
0x18000a527  mov     r8d, r9d
0x18000a52a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a52e  call    wil_details_NtUpdateWnfStateData
0x18000a533  mov     edi, eax
0x18000a535  cmp     edi, 0C0000001h
0x18000a53b  jnz     short loc_18000A54C
0x18000a53d  inc     esi
0x18000a53f  cmp     esi, 64h ; 'd'
0x18000a542  jge     short loc_18000A54C
0x18000a544  test    ebx, ebx
0x18000a546  jz      loc_18000A3FB
0x18000a54c  test    ebx, ebx
0x18000a54e  cmovz   ebx, edi
0x18000a551  mov     eax, ebx
0x18000a553  mov     rcx, [rbp+0F90h+var_40]
0x18000a55a  xor     rcx, rsp; StackCookie
0x18000a55d  call    __security_check_cookie
0x18000a562  add     rsp, 1068h
0x18000a569  pop     r14
0x18000a56b  pop     r12
0x18000a56d  pop     rdi
0x18000a56e  pop     rsi
0x18000a56f  pop     rbx
0x18000a570  pop     rbp
0x18000a571  retn
```
