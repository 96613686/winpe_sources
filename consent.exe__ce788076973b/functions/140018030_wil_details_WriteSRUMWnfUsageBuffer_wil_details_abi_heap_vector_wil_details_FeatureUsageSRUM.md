# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140018030`
- end: `0x1400181fa`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140013c30`

## callees

- `0x140010ad3`
- `0x140018030`
- `0x1400187a4`
- `0x14001881c`
- `0x14001e050`
- `0x14001e110`

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
0x140018030  push    rbp
0x140018032  push    rbx
0x140018033  push    rsi
0x140018034  push    rdi
0x140018035  push    r12
0x140018037  push    r14
0x140018039  lea     rbp, [rsp-0F68h]
0x140018041  mov     eax, 1068h
0x140018046  call    _alloca_probe
0x14001804b  sub     rsp, rax
0x14001804e  mov     rax, cs:__security_cookie
0x140018055  xor     rax, rsp
0x140018058  mov     [rbp+0F90h+var_40], rax
0x14001805f  mov     rax, [rcx+8]
0x140018063  xor     ebx, ebx
0x140018065  sub     rax, [rcx]
0x140018068  xor     edi, edi
0x14001806a  mov     r14, rcx
0x14001806d  cmp     rax, 0Ch
0x140018071  jb      loc_1400181D4
0x140018077  xor     esi, esi
0x140018079  mov     r12, 0AAAAAAAAAAAAAAABh
0x140018083  xor     edx, edx; Val
0x140018085  lea     rcx, [rsp+1090h+var_1040]; void *
0x14001808a  mov     r8d, 1000h; Size
0x140018090  call    memset_0
0x140018095  lea     rax, [rsp+1090h+var_1050]
0x14001809a  mov     [rsp+1090h+var_1050], 1000h
0x1400180a2  mov     [rsp+1090h+var_1068], rax
0x1400180a7  lea     r9, [rsp+1090h+var_104C]
0x1400180ac  lea     rax, [rsp+1090h+var_1040]
0x1400180b1  mov     [rsp+1090h+var_104C], 0
0x1400180b9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400180c0  mov     [rsp+1090h+var_1070], rax
0x1400180c5  call    wil_details_NtQueryWnfStateData
0x1400180ca  mov     ebx, eax
0x1400180cc  test    eax, eax
0x1400180ce  jnz     loc_1400181BD
0x1400180d4  mov     r9d, [rsp+1090h+var_1050]
0x1400180d9  mov     rax, r12
0x1400180dc  mul     r9
0x1400180df  shr     rdx, 3
0x1400180e3  lea     rcx, [rdx+rdx*2]
0x1400180e7  shl     rcx, 2
0x1400180eb  cmp     r9, rcx
0x1400180ee  jz      short loc_1400180F8
0x1400180f0  xor     r9d, r9d
0x1400180f3  mov     [rsp+1090h+var_1050], r9d
0x1400180f8  mov     r8, [r14]
0x1400180fb  mov     rax, r12
0x1400180fe  mov     ecx, r9d
0x140018101  mul     rcx
0x140018104  mov     rcx, [r14+8]
0x140018108  mov     rax, r12
0x14001810b  mov     r11, rdx
0x14001810e  sub     rcx, r8
0x140018111  mul     rcx
0x140018114  shr     r11, 3
0x140018118  shr     rdx, 3
0x14001811c  lea     rax, [rdx+rdx*2]
0x140018120  lea     rdi, [r8+rax*4]
0x140018124  jmp     short loc_140018192
0x140018126  mov     eax, r11d
0x140018129  lea     r10, [rsp+1090h+var_1040]
0x14001812e  lea     rcx, [rax+rax*2]
0x140018132  lea     r10, [r10+rcx*4]
0x140018136  cmp     rdx, r10
0x140018139  jz      short loc_140018161
0x14001813b  mov     eax, [r8]
0x14001813e  cmp     [rdx], eax
0x140018140  jnz     short loc_14001814D
0x140018142  movzx   eax, word ptr [r8+4]
0x140018147  cmp     [rdx+4], ax
0x14001814b  jz      short loc_140018153
0x14001814d  add     rdx, 0Ch
0x140018151  jmp     short loc_140018136
0x140018153  mov     eax, [r8+8]
0x140018157  add     [rdx+8], eax
0x14001815a  mov     r9d, [rsp+1090h+var_1050]
0x14001815f  jmp     short loc_14001818E
0x140018161  mov     eax, r9d
0x140018164  add     rax, 0Ch
0x140018168  cmp     rax, 1000h
0x14001816e  ja      short loc_14001818E
0x140018170  movsd   xmm0, qword ptr [r8]
0x140018175  add     r9d, 0Ch
0x140018179  movsd   qword ptr [r10], xmm0
0x14001817e  inc     r11d
0x140018181  mov     eax, [r8+8]
0x140018185  mov     [r10+8], eax
0x140018189  mov     [rsp+1090h+var_1050], r9d
0x14001818e  add     r8, 0Ch
0x140018192  lea     rdx, [rsp+1090h+var_1040]
0x140018197  cmp     r8, rdi
0x14001819a  jnz     short loc_140018126
0x14001819c  mov     eax, [rsp+1090h+var_104C]
0x1400181a0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400181a7  mov     [rsp+1090h+var_1060], 1
0x1400181af  mov     r8d, r9d
0x1400181b2  mov     dword ptr [rsp+1090h+var_1068], eax
0x1400181b6  call    wil_details_NtUpdateWnfStateData
0x1400181bb  mov     edi, eax
0x1400181bd  cmp     edi, 0C0000001h
0x1400181c3  jnz     short loc_1400181D4
0x1400181c5  inc     esi
0x1400181c7  cmp     esi, 64h ; 'd'
0x1400181ca  jge     short loc_1400181D4
0x1400181cc  test    ebx, ebx
0x1400181ce  jz      loc_140018083
0x1400181d4  test    ebx, ebx
0x1400181d6  cmovz   ebx, edi
0x1400181d9  mov     eax, ebx
0x1400181db  mov     rcx, [rbp+0F90h+var_40]
0x1400181e2  xor     rcx, rsp; StackCookie
0x1400181e5  call    __security_check_cookie
0x1400181ea  add     rsp, 1068h
0x1400181f1  pop     r14
0x1400181f3  pop     r12
0x1400181f5  pop     rdi
0x1400181f6  pop     rsi
0x1400181f7  pop     rbx
0x1400181f8  pop     rbp
0x1400181f9  retn
```
