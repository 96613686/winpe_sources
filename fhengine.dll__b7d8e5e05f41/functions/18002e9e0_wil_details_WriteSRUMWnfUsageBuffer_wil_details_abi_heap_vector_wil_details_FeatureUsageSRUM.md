# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002e9e0`
- end: `0x18002ebb5`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180026980`

## callees

- `0x18002e9e0`
- `0x18002f16c`
- `0x18002f1e4`
- `0x180031642`
- `0x180031680`
- `0x180031740`

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
0x18002e9e0  push    rbp
0x18002e9e2  push    rbx
0x18002e9e3  push    rsi
0x18002e9e4  push    rdi
0x18002e9e5  push    r12
0x18002e9e7  push    r14
0x18002e9e9  lea     rbp, [rsp-0F68h]
0x18002e9f1  mov     eax, 1068h
0x18002e9f6  call    _alloca_probe
0x18002e9fb  sub     rsp, rax
0x18002e9fe  mov     rax, cs:__security_cookie
0x18002ea05  xor     rax, rsp
0x18002ea08  mov     [rbp+0F90h+var_40], rax
0x18002ea0f  mov     rax, [rcx+8]
0x18002ea13  xor     ebx, ebx
0x18002ea15  sub     rax, [rcx]
0x18002ea18  xor     edi, edi
0x18002ea1a  mov     r14, rcx
0x18002ea1d  cmp     rax, 0Ch
0x18002ea21  jb      loc_18002EB81
0x18002ea27  xor     esi, esi
0x18002ea29  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002ea33  xor     edx, edx; Val
0x18002ea35  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002ea3a  mov     r8d, 1000h; Size
0x18002ea40  call    memset_0
0x18002ea45  lea     rax, [rsp+1090h+var_1050]
0x18002ea4a  mov     [rsp+1090h+var_1050], 1000h
0x18002ea52  mov     [rsp+1090h+var_1068], rax
0x18002ea57  lea     r9, [rsp+1090h+var_104C]
0x18002ea5c  lea     rax, [rsp+1090h+var_1040]
0x18002ea61  mov     [rsp+1090h+var_104C], 0
0x18002ea69  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002ea70  mov     [rsp+1090h+var_1070], rax
0x18002ea75  call    wil_details_NtQueryWnfStateData
0x18002ea7a  mov     ebx, eax
0x18002ea7c  test    eax, eax
0x18002ea7e  jnz     loc_18002EB6A
0x18002ea84  mov     r9d, [rsp+1090h+var_1050]
0x18002ea89  mov     rax, r12
0x18002ea8c  mul     r9
0x18002ea8f  shr     rdx, 3
0x18002ea93  lea     rcx, [rdx+rdx*2]
0x18002ea97  shl     rcx, 2
0x18002ea9b  cmp     r9, rcx
0x18002ea9e  jz      short loc_18002EAA8
0x18002eaa0  xor     r9d, r9d
0x18002eaa3  mov     [rsp+1090h+var_1050], r9d
0x18002eaa8  mov     r8, [r14]
0x18002eaab  mov     rax, r12
0x18002eaae  mov     ecx, r9d
0x18002eab1  mul     rcx
0x18002eab4  mov     rcx, [r14+8]
0x18002eab8  mov     rax, r12
0x18002eabb  mov     r10, rdx
0x18002eabe  sub     rcx, r8
0x18002eac1  mul     rcx
0x18002eac4  shr     r10, 3
0x18002eac8  shr     rdx, 3
0x18002eacc  lea     rax, [rdx+rdx*2]
0x18002ead0  lea     rdi, [r8+rax*4]
0x18002ead4  jmp     short loc_18002EB3F
0x18002ead6  mov     eax, r10d
0x18002ead9  lea     rcx, [rax+rax*2]
0x18002eadd  lea     rdx, [rdx+rcx*4]
0x18002eae1  lea     rax, [rsp+1090h+var_1040]
0x18002eae6  cmp     rax, rdx
0x18002eae9  jz      short loc_18002EB10
0x18002eaeb  mov     r11d, [r8]
0x18002eaee  lea     rcx, [rsp+1090h+var_1040]
0x18002eaf3  cmp     [rcx], r11d
0x18002eaf6  jnz     short loc_18002EB07
0x18002eaf8  movzx   eax, word ptr [r8+4]
0x18002eafd  cmp     [rcx+4], ax
0x18002eb01  jz      loc_18002EBA7
0x18002eb07  add     rcx, 0Ch
0x18002eb0b  cmp     rcx, rdx
0x18002eb0e  jnz     short loc_18002EAF3
0x18002eb10  mov     eax, r9d
0x18002eb13  add     rax, 0Ch
0x18002eb17  cmp     rax, 1000h
0x18002eb1d  ja      short loc_18002EB3B
0x18002eb1f  movsd   xmm0, qword ptr [r8]
0x18002eb24  add     r9d, 0Ch
0x18002eb28  movsd   qword ptr [rdx], xmm0
0x18002eb2c  inc     r10d
0x18002eb2f  mov     eax, [r8+8]
0x18002eb33  mov     [rdx+8], eax
0x18002eb36  mov     [rsp+1090h+var_1050], r9d
0x18002eb3b  add     r8, 0Ch
0x18002eb3f  lea     rdx, [rsp+1090h+var_1040]
0x18002eb44  cmp     r8, rdi
0x18002eb47  jnz     short loc_18002EAD6
0x18002eb49  mov     eax, [rsp+1090h+var_104C]
0x18002eb4d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002eb54  mov     [rsp+1090h+var_1060], 1
0x18002eb5c  mov     r8d, r9d
0x18002eb5f  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002eb63  call    wil_details_NtUpdateWnfStateData
0x18002eb68  mov     edi, eax
0x18002eb6a  cmp     edi, 0C0000001h
0x18002eb70  jnz     short loc_18002EB81
0x18002eb72  inc     esi
0x18002eb74  cmp     esi, 64h ; 'd'
0x18002eb77  jge     short loc_18002EB81
0x18002eb79  test    ebx, ebx
0x18002eb7b  jz      loc_18002EA33
0x18002eb81  test    ebx, ebx
0x18002eb83  cmovz   ebx, edi
0x18002eb86  mov     eax, ebx
0x18002eb88  mov     rcx, [rbp+0F90h+var_40]
0x18002eb8f  xor     rcx, rsp; StackCookie
0x18002eb92  call    __security_check_cookie
0x18002eb97  add     rsp, 1068h
0x18002eb9e  pop     r14
0x18002eba0  pop     r12
0x18002eba2  pop     rdi
0x18002eba3  pop     rsi
0x18002eba4  pop     rbx
0x18002eba5  pop     rbp
0x18002eba6  retn
0x18002eba7  mov     eax, [r8+8]
0x18002ebab  add     [rcx+8], eax
0x18002ebae  mov     r9d, [rsp+1090h+var_1050]
0x18002ebb3  jmp     short loc_18002EB3B
```
