# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012438`
- end: `0x180012602`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000d040`

## callees

- `0x18000be40`
- `0x18000c7e8`
- `0x180012438`
- `0x180012a3c`
- `0x180012ab4`
- `0x180021550`

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
0x180012438  push    rbp
0x18001243a  push    rbx
0x18001243b  push    rsi
0x18001243c  push    rdi
0x18001243d  push    r12
0x18001243f  push    r14
0x180012441  lea     rbp, [rsp-0F68h]
0x180012449  mov     eax, 1068h
0x18001244e  call    _alloca_probe
0x180012453  sub     rsp, rax
0x180012456  mov     rax, cs:__security_cookie
0x18001245d  xor     rax, rsp
0x180012460  mov     [rbp+0F90h+var_40], rax
0x180012467  mov     rax, [rcx+8]
0x18001246b  xor     ebx, ebx
0x18001246d  sub     rax, [rcx]
0x180012470  xor     edi, edi
0x180012472  mov     r14, rcx
0x180012475  cmp     rax, 0Ch
0x180012479  jb      loc_1800125DC
0x18001247f  xor     esi, esi
0x180012481  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001248b  xor     edx, edx; Val
0x18001248d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012492  mov     r8d, 1000h; Size
0x180012498  call    memset_0
0x18001249d  lea     rax, [rsp+1090h+var_1050]
0x1800124a2  mov     [rsp+1090h+var_1050], 1000h
0x1800124aa  mov     [rsp+1090h+var_1068], rax
0x1800124af  lea     r9, [rsp+1090h+var_104C]
0x1800124b4  lea     rax, [rsp+1090h+var_1040]
0x1800124b9  mov     [rsp+1090h+var_104C], 0
0x1800124c1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800124c8  mov     [rsp+1090h+var_1070], rax
0x1800124cd  call    wil_details_NtQueryWnfStateData
0x1800124d2  mov     ebx, eax
0x1800124d4  test    eax, eax
0x1800124d6  jnz     loc_1800125C5
0x1800124dc  mov     r9d, [rsp+1090h+var_1050]
0x1800124e1  mov     rax, r12
0x1800124e4  mul     r9
0x1800124e7  shr     rdx, 3
0x1800124eb  lea     rcx, [rdx+rdx*2]
0x1800124ef  shl     rcx, 2
0x1800124f3  cmp     r9, rcx
0x1800124f6  jz      short loc_180012500
0x1800124f8  xor     r9d, r9d
0x1800124fb  mov     [rsp+1090h+var_1050], r9d
0x180012500  mov     r8, [r14]
0x180012503  mov     rax, r12
0x180012506  mov     ecx, r9d
0x180012509  mul     rcx
0x18001250c  mov     rcx, [r14+8]
0x180012510  mov     rax, r12
0x180012513  mov     r11, rdx
0x180012516  sub     rcx, r8
0x180012519  mul     rcx
0x18001251c  shr     r11, 3
0x180012520  shr     rdx, 3
0x180012524  lea     rax, [rdx+rdx*2]
0x180012528  lea     rdi, [r8+rax*4]
0x18001252c  jmp     short loc_18001259A
0x18001252e  mov     eax, r11d
0x180012531  lea     r10, [rsp+1090h+var_1040]
0x180012536  lea     rcx, [rax+rax*2]
0x18001253a  lea     r10, [r10+rcx*4]
0x18001253e  cmp     rdx, r10
0x180012541  jz      short loc_180012569
0x180012543  mov     eax, [r8]
0x180012546  cmp     [rdx], eax
0x180012548  jnz     short loc_180012555
0x18001254a  movzx   eax, word ptr [r8+4]
0x18001254f  cmp     [rdx+4], ax
0x180012553  jz      short loc_18001255B
0x180012555  add     rdx, 0Ch
0x180012559  jmp     short loc_18001253E
0x18001255b  mov     eax, [r8+8]
0x18001255f  add     [rdx+8], eax
0x180012562  mov     r9d, [rsp+1090h+var_1050]
0x180012567  jmp     short loc_180012596
0x180012569  mov     eax, r9d
0x18001256c  add     rax, 0Ch
0x180012570  cmp     rax, 1000h
0x180012576  ja      short loc_180012596
0x180012578  movsd   xmm0, qword ptr [r8]
0x18001257d  add     r9d, 0Ch
0x180012581  movsd   qword ptr [r10], xmm0
0x180012586  inc     r11d
0x180012589  mov     eax, [r8+8]
0x18001258d  mov     [r10+8], eax
0x180012591  mov     [rsp+1090h+var_1050], r9d
0x180012596  add     r8, 0Ch
0x18001259a  lea     rdx, [rsp+1090h+var_1040]
0x18001259f  cmp     r8, rdi
0x1800125a2  jnz     short loc_18001252E
0x1800125a4  mov     eax, [rsp+1090h+var_104C]
0x1800125a8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800125af  mov     [rsp+1090h+var_1060], 1
0x1800125b7  mov     r8d, r9d
0x1800125ba  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800125be  call    wil_details_NtUpdateWnfStateData
0x1800125c3  mov     edi, eax
0x1800125c5  cmp     edi, 0C0000001h
0x1800125cb  jnz     short loc_1800125DC
0x1800125cd  inc     esi
0x1800125cf  cmp     esi, 64h ; 'd'
0x1800125d2  jge     short loc_1800125DC
0x1800125d4  test    ebx, ebx
0x1800125d6  jz      loc_18001248B
0x1800125dc  test    ebx, ebx
0x1800125de  cmovz   ebx, edi
0x1800125e1  mov     eax, ebx
0x1800125e3  mov     rcx, [rbp+0F90h+var_40]
0x1800125ea  xor     rcx, rsp; StackCookie
0x1800125ed  call    __security_check_cookie
0x1800125f2  add     rsp, 1068h
0x1800125f9  pop     r14
0x1800125fb  pop     r12
0x1800125fd  pop     rdi
0x1800125fe  pop     rsi
0x1800125ff  pop     rbx
0x180012600  pop     rbp
0x180012601  retn
```
