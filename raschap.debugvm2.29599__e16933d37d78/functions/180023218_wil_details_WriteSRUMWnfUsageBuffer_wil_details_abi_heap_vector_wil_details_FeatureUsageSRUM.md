# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180023218`
- end: `0x1800233e2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001e660`

## callees

- `0x180013b20`
- `0x180014610`
- `0x180023218`
- `0x1800236ac`
- `0x180023724`
- `0x180025e90`

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
0x180023218  push    rbp
0x18002321a  push    rbx
0x18002321b  push    rsi
0x18002321c  push    rdi
0x18002321d  push    r12
0x18002321f  push    r14
0x180023221  lea     rbp, [rsp-0F68h]
0x180023229  mov     eax, 1068h
0x18002322e  call    _alloca_probe
0x180023233  sub     rsp, rax
0x180023236  mov     rax, cs:__security_cookie
0x18002323d  xor     rax, rsp
0x180023240  mov     [rbp+0F90h+var_40], rax
0x180023247  mov     rax, [rcx+8]
0x18002324b  xor     ebx, ebx
0x18002324d  sub     rax, [rcx]
0x180023250  xor     edi, edi
0x180023252  mov     r14, rcx
0x180023255  cmp     rax, 0Ch
0x180023259  jb      loc_1800233BC
0x18002325f  xor     esi, esi
0x180023261  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002326b  xor     edx, edx; Val
0x18002326d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180023272  mov     r8d, 1000h; Size
0x180023278  call    memset_0
0x18002327d  lea     rax, [rsp+1090h+var_1050]
0x180023282  mov     [rsp+1090h+var_1050], 1000h
0x18002328a  mov     [rsp+1090h+var_1068], rax
0x18002328f  lea     r9, [rsp+1090h+var_104C]
0x180023294  lea     rax, [rsp+1090h+var_1040]
0x180023299  mov     [rsp+1090h+var_104C], 0
0x1800232a1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800232a8  mov     [rsp+1090h+var_1070], rax
0x1800232ad  call    wil_details_NtQueryWnfStateData
0x1800232b2  mov     ebx, eax
0x1800232b4  test    eax, eax
0x1800232b6  jnz     loc_1800233A5
0x1800232bc  mov     r9d, [rsp+1090h+var_1050]
0x1800232c1  mov     rax, r12
0x1800232c4  mul     r9
0x1800232c7  shr     rdx, 3
0x1800232cb  lea     rcx, [rdx+rdx*2]
0x1800232cf  shl     rcx, 2
0x1800232d3  cmp     r9, rcx
0x1800232d6  jz      short loc_1800232E0
0x1800232d8  xor     r9d, r9d
0x1800232db  mov     [rsp+1090h+var_1050], r9d
0x1800232e0  mov     r8, [r14]
0x1800232e3  mov     rax, r12
0x1800232e6  mov     ecx, r9d
0x1800232e9  mul     rcx
0x1800232ec  mov     rcx, [r14+8]
0x1800232f0  mov     rax, r12
0x1800232f3  mov     r11, rdx
0x1800232f6  sub     rcx, r8
0x1800232f9  mul     rcx
0x1800232fc  shr     r11, 3
0x180023300  shr     rdx, 3
0x180023304  lea     rax, [rdx+rdx*2]
0x180023308  lea     rdi, [r8+rax*4]
0x18002330c  jmp     short loc_18002337A
0x18002330e  mov     eax, r11d
0x180023311  lea     r10, [rsp+1090h+var_1040]
0x180023316  lea     rcx, [rax+rax*2]
0x18002331a  lea     r10, [r10+rcx*4]
0x18002331e  cmp     rdx, r10
0x180023321  jz      short loc_180023349
0x180023323  mov     eax, [r8]
0x180023326  cmp     [rdx], eax
0x180023328  jnz     short loc_180023335
0x18002332a  movzx   eax, word ptr [r8+4]
0x18002332f  cmp     [rdx+4], ax
0x180023333  jz      short loc_18002333B
0x180023335  add     rdx, 0Ch
0x180023339  jmp     short loc_18002331E
0x18002333b  mov     eax, [r8+8]
0x18002333f  add     [rdx+8], eax
0x180023342  mov     r9d, [rsp+1090h+var_1050]
0x180023347  jmp     short loc_180023376
0x180023349  mov     eax, r9d
0x18002334c  add     rax, 0Ch
0x180023350  cmp     rax, 1000h
0x180023356  ja      short loc_180023376
0x180023358  movsd   xmm0, qword ptr [r8]
0x18002335d  add     r9d, 0Ch
0x180023361  movsd   qword ptr [r10], xmm0
0x180023366  inc     r11d
0x180023369  mov     eax, [r8+8]
0x18002336d  mov     [r10+8], eax
0x180023371  mov     [rsp+1090h+var_1050], r9d
0x180023376  add     r8, 0Ch
0x18002337a  lea     rdx, [rsp+1090h+var_1040]
0x18002337f  cmp     r8, rdi
0x180023382  jnz     short loc_18002330E
0x180023384  mov     eax, [rsp+1090h+var_104C]
0x180023388  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002338f  mov     [rsp+1090h+var_1060], 1
0x180023397  mov     r8d, r9d
0x18002339a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002339e  call    wil_details_NtUpdateWnfStateData
0x1800233a3  mov     edi, eax
0x1800233a5  cmp     edi, 0C0000001h
0x1800233ab  jnz     short loc_1800233BC
0x1800233ad  inc     esi
0x1800233af  cmp     esi, 64h ; 'd'
0x1800233b2  jge     short loc_1800233BC
0x1800233b4  test    ebx, ebx
0x1800233b6  jz      loc_18002326B
0x1800233bc  test    ebx, ebx
0x1800233be  cmovz   ebx, edi
0x1800233c1  mov     eax, ebx
0x1800233c3  mov     rcx, [rbp+0F90h+var_40]
0x1800233ca  xor     rcx, rsp; StackCookie
0x1800233cd  call    __security_check_cookie
0x1800233d2  add     rsp, 1068h
0x1800233d9  pop     r14
0x1800233db  pop     r12
0x1800233dd  pop     rdi
0x1800233de  pop     rsi
0x1800233df  pop     rbx
0x1800233e0  pop     rbp
0x1800233e1  retn
```
