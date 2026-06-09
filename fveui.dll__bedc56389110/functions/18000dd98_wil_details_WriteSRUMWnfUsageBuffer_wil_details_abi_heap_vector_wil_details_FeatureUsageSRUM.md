# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000dd98`
- end: `0x18000df62`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003960`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000dd98`
- `0x18000e96c`
- `0x18000e9e4`
- `0x18002c1d0`

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
0x18000dd98  push    rbp
0x18000dd9a  push    rbx
0x18000dd9b  push    rsi
0x18000dd9c  push    rdi
0x18000dd9d  push    r12
0x18000dd9f  push    r14
0x18000dda1  lea     rbp, [rsp-0F68h]
0x18000dda9  mov     eax, 1068h
0x18000ddae  call    _alloca_probe
0x18000ddb3  sub     rsp, rax
0x18000ddb6  mov     rax, cs:__security_cookie
0x18000ddbd  xor     rax, rsp
0x18000ddc0  mov     [rbp+0F90h+var_40], rax
0x18000ddc7  mov     rax, [rcx+8]
0x18000ddcb  xor     ebx, ebx
0x18000ddcd  sub     rax, [rcx]
0x18000ddd0  xor     edi, edi
0x18000ddd2  mov     r14, rcx
0x18000ddd5  cmp     rax, 0Ch
0x18000ddd9  jb      loc_18000DF3C
0x18000dddf  xor     esi, esi
0x18000dde1  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000ddeb  xor     edx, edx; Val
0x18000dded  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ddf2  mov     r8d, 1000h; Size
0x18000ddf8  call    memset_0
0x18000ddfd  lea     rax, [rsp+1090h+var_1050]
0x18000de02  mov     [rsp+1090h+var_1050], 1000h
0x18000de0a  mov     [rsp+1090h+var_1068], rax
0x18000de0f  lea     r9, [rsp+1090h+var_104C]
0x18000de14  lea     rax, [rsp+1090h+var_1040]
0x18000de19  mov     [rsp+1090h+var_104C], 0
0x18000de21  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000de28  mov     [rsp+1090h+var_1070], rax
0x18000de2d  call    wil_details_NtQueryWnfStateData
0x18000de32  mov     ebx, eax
0x18000de34  test    eax, eax
0x18000de36  jnz     loc_18000DF25
0x18000de3c  mov     r9d, [rsp+1090h+var_1050]
0x18000de41  mov     rax, r12
0x18000de44  mul     r9
0x18000de47  shr     rdx, 3
0x18000de4b  lea     rcx, [rdx+rdx*2]
0x18000de4f  shl     rcx, 2
0x18000de53  cmp     r9, rcx
0x18000de56  jz      short loc_18000DE60
0x18000de58  xor     r9d, r9d
0x18000de5b  mov     [rsp+1090h+var_1050], r9d
0x18000de60  mov     r8, [r14]
0x18000de63  mov     rax, r12
0x18000de66  mov     ecx, r9d
0x18000de69  mul     rcx
0x18000de6c  mov     rcx, [r14+8]
0x18000de70  mov     rax, r12
0x18000de73  mov     r11, rdx
0x18000de76  sub     rcx, r8
0x18000de79  mul     rcx
0x18000de7c  shr     r11, 3
0x18000de80  shr     rdx, 3
0x18000de84  lea     rax, [rdx+rdx*2]
0x18000de88  lea     rdi, [r8+rax*4]
0x18000de8c  jmp     short loc_18000DEFA
0x18000de8e  mov     eax, r11d
0x18000de91  lea     r10, [rsp+1090h+var_1040]
0x18000de96  lea     rcx, [rax+rax*2]
0x18000de9a  lea     r10, [r10+rcx*4]
0x18000de9e  cmp     rdx, r10
0x18000dea1  jz      short loc_18000DEC9
0x18000dea3  mov     eax, [r8]
0x18000dea6  cmp     [rdx], eax
0x18000dea8  jnz     short loc_18000DEB5
0x18000deaa  movzx   eax, word ptr [r8+4]
0x18000deaf  cmp     [rdx+4], ax
0x18000deb3  jz      short loc_18000DEBB
0x18000deb5  add     rdx, 0Ch
0x18000deb9  jmp     short loc_18000DE9E
0x18000debb  mov     eax, [r8+8]
0x18000debf  add     [rdx+8], eax
0x18000dec2  mov     r9d, [rsp+1090h+var_1050]
0x18000dec7  jmp     short loc_18000DEF6
0x18000dec9  mov     eax, r9d
0x18000decc  add     rax, 0Ch
0x18000ded0  cmp     rax, 1000h
0x18000ded6  ja      short loc_18000DEF6
0x18000ded8  movsd   xmm0, qword ptr [r8]
0x18000dedd  add     r9d, 0Ch
0x18000dee1  movsd   qword ptr [r10], xmm0
0x18000dee6  inc     r11d
0x18000dee9  mov     eax, [r8+8]
0x18000deed  mov     [r10+8], eax
0x18000def1  mov     [rsp+1090h+var_1050], r9d
0x18000def6  add     r8, 0Ch
0x18000defa  lea     rdx, [rsp+1090h+var_1040]
0x18000deff  cmp     r8, rdi
0x18000df02  jnz     short loc_18000DE8E
0x18000df04  mov     eax, [rsp+1090h+var_104C]
0x18000df08  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000df0f  mov     [rsp+1090h+var_1060], 1
0x18000df17  mov     r8d, r9d
0x18000df1a  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000df1e  call    wil_details_NtUpdateWnfStateData
0x18000df23  mov     edi, eax
0x18000df25  cmp     edi, 0C0000001h
0x18000df2b  jnz     short loc_18000DF3C
0x18000df2d  inc     esi
0x18000df2f  cmp     esi, 64h ; 'd'
0x18000df32  jge     short loc_18000DF3C
0x18000df34  test    ebx, ebx
0x18000df36  jz      loc_18000DDEB
0x18000df3c  test    ebx, ebx
0x18000df3e  cmovz   ebx, edi
0x18000df41  mov     eax, ebx
0x18000df43  mov     rcx, [rbp+0F90h+var_40]
0x18000df4a  xor     rcx, rsp; StackCookie
0x18000df4d  call    __security_check_cookie
0x18000df52  add     rsp, 1068h
0x18000df59  pop     r14
0x18000df5b  pop     r12
0x18000df5d  pop     rdi
0x18000df5e  pop     rsi
0x18000df5f  pop     rbx
0x18000df60  pop     rbp
0x18000df61  retn
```
