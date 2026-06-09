# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800080bc`
- end: `0x180008292`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180002780`

## callees

- `0x1800080bc`
- `0x1800082a4`
- `0x18000834c`
- `0x180014dce`
- `0x180014e00`
- `0x180014ec0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
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
      v16[0] = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
                    v16[0],
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
0x1800080bc  push    rbp
0x1800080be  push    rbx
0x1800080bf  push    rsi
0x1800080c0  push    rdi
0x1800080c1  push    r12
0x1800080c3  push    r14
0x1800080c5  lea     rbp, [rsp-0F68h]
0x1800080cd  mov     eax, 1068h
0x1800080d2  call    _alloca_probe
0x1800080d7  sub     rsp, rax
0x1800080da  mov     rax, cs:__security_cookie
0x1800080e1  xor     rax, rsp
0x1800080e4  mov     [rbp+0F90h+var_40], rax
0x1800080eb  mov     rax, [rcx+8]
0x1800080ef  xor     ebx, ebx
0x1800080f1  sub     rax, [rcx]
0x1800080f4  xor     edi, edi
0x1800080f6  mov     r14, rcx
0x1800080f9  cmp     rax, 0Ch
0x1800080fd  jb      loc_18000825D
0x180008103  xor     esi, esi
0x180008105  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000810f  xor     edx, edx; Val
0x180008111  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008116  mov     r8d, 1000h; Size
0x18000811c  call    memset_0
0x180008121  lea     rax, [rsp+1090h+var_1050]
0x180008126  mov     [rsp+1090h+var_1050], 1000h
0x18000812e  mov     [rsp+1090h+var_1068], rax
0x180008133  lea     r9, [rsp+1090h+var_104C]
0x180008138  lea     rax, [rsp+1090h+var_1040]
0x18000813d  mov     [rsp+1090h+var_104C], 0
0x180008145  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000814c  mov     [rsp+1090h+var_1070], rax
0x180008151  call    wil_details_NtQueryWnfStateData
0x180008156  mov     ebx, eax
0x180008158  test    eax, eax
0x18000815a  jnz     loc_180008246
0x180008160  mov     r9d, [rsp+1090h+var_1050]
0x180008165  mov     rax, r12
0x180008168  mul     r9
0x18000816b  shr     rdx, 3
0x18000816f  lea     rcx, [rdx+rdx*2]
0x180008173  shl     rcx, 2
0x180008177  cmp     r9, rcx
0x18000817a  jz      short loc_180008184
0x18000817c  xor     r9d, r9d
0x18000817f  mov     [rsp+1090h+var_1050], r9d
0x180008184  mov     r8, [r14]
0x180008187  mov     rax, r12
0x18000818a  mov     ecx, r9d
0x18000818d  mul     rcx
0x180008190  mov     rcx, [r14+8]
0x180008194  mov     rax, r12
0x180008197  mov     r10, rdx
0x18000819a  sub     rcx, r8
0x18000819d  mul     rcx
0x1800081a0  shr     r10, 3
0x1800081a4  shr     rdx, 3
0x1800081a8  lea     rax, [rdx+rdx*2]
0x1800081ac  lea     rdi, [r8+rax*4]
0x1800081b0  jmp     short loc_18000821B
0x1800081b2  mov     eax, r10d
0x1800081b5  lea     rcx, [rax+rax*2]
0x1800081b9  lea     rdx, [rdx+rcx*4]
0x1800081bd  lea     rax, [rsp+1090h+var_1040]
0x1800081c2  cmp     rax, rdx
0x1800081c5  jz      short loc_1800081EC
0x1800081c7  mov     r11d, [r8]
0x1800081ca  lea     rcx, [rsp+1090h+var_1040]
0x1800081cf  cmp     [rcx], r11d
0x1800081d2  jnz     short loc_1800081E3
0x1800081d4  movzx   eax, word ptr [r8+4]
0x1800081d9  cmp     [rcx+4], ax
0x1800081dd  jz      loc_180008284
0x1800081e3  add     rcx, 0Ch
0x1800081e7  cmp     rcx, rdx
0x1800081ea  jnz     short loc_1800081CF
0x1800081ec  mov     eax, r9d
0x1800081ef  add     rax, 0Ch
0x1800081f3  cmp     rax, 1000h
0x1800081f9  ja      short loc_180008217
0x1800081fb  movsd   xmm0, qword ptr [r8]
0x180008200  add     r9d, 0Ch
0x180008204  movsd   qword ptr [rdx], xmm0
0x180008208  inc     r10d
0x18000820b  mov     eax, [r8+8]
0x18000820f  mov     [rdx+8], eax
0x180008212  mov     [rsp+1090h+var_1050], r9d
0x180008217  add     r8, 0Ch
0x18000821b  lea     rdx, [rsp+1090h+var_1040]
0x180008220  cmp     r8, rdi
0x180008223  jnz     short loc_1800081B2
0x180008225  mov     eax, [rsp+1090h+var_104C]
0x180008229  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008230  mov     [rsp+1090h+var_1060], 1
0x180008238  mov     r8d, r9d
0x18000823b  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000823f  call    wil_details_NtUpdateWnfStateData
0x180008244  mov     edi, eax
0x180008246  cmp     edi, 0C0000001h
0x18000824c  jnz     short loc_18000825D
0x18000824e  inc     esi
0x180008250  cmp     esi, 64h ; 'd'
0x180008253  jge     short loc_18000825D
0x180008255  test    ebx, ebx
0x180008257  jz      loc_18000810F
0x18000825d  test    ebx, ebx
0x18000825f  cmovz   ebx, edi
0x180008262  mov     eax, ebx
0x180008264  mov     rcx, [rbp+0F90h+var_40]
0x18000826b  xor     rcx, rsp; StackCookie
0x18000826e  call    __security_check_cookie
0x180008273  add     rsp, 1068h
0x18000827a  pop     r14
0x18000827c  pop     r12
0x18000827e  pop     rdi
0x18000827f  pop     rsi
0x180008280  pop     rbx
0x180008281  pop     rbp
0x180008282  retn
0x180008284  mov     eax, [r8+8]
0x180008288  add     [rcx+8], eax
0x18000828b  mov     r9d, [rsp+1090h+var_1050]
0x180008290  jmp     short loc_180008217
```
