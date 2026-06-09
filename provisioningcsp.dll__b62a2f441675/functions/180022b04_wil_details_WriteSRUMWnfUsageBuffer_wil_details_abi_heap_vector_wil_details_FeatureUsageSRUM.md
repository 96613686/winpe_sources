# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180022b04`
- end: `0x180022cda`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180013730`

## callees

- `0x180022b04`
- `0x180022ce0`
- `0x180022d88`
- `0x18003586a`
- `0x1800358a0`
- `0x180035960`

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
0x180022b04  push    rbp
0x180022b06  push    rbx
0x180022b07  push    rsi
0x180022b08  push    rdi
0x180022b09  push    r12
0x180022b0b  push    r14
0x180022b0d  lea     rbp, [rsp-0F68h]
0x180022b15  mov     eax, 1068h
0x180022b1a  call    _alloca_probe
0x180022b1f  sub     rsp, rax
0x180022b22  mov     rax, cs:__security_cookie
0x180022b29  xor     rax, rsp
0x180022b2c  mov     [rbp+0F90h+var_40], rax
0x180022b33  mov     rax, [rcx+8]
0x180022b37  xor     ebx, ebx
0x180022b39  sub     rax, [rcx]
0x180022b3c  xor     edi, edi
0x180022b3e  mov     r14, rcx
0x180022b41  cmp     rax, 0Ch
0x180022b45  jb      loc_180022CA5
0x180022b4b  xor     esi, esi
0x180022b4d  mov     r12, 0AAAAAAAAAAAAAAABh
0x180022b57  xor     edx, edx; Val
0x180022b59  lea     rcx, [rsp+1090h+var_1040]; void *
0x180022b5e  mov     r8d, 1000h; Size
0x180022b64  call    memset_0
0x180022b69  lea     rax, [rsp+1090h+var_1050]
0x180022b6e  mov     [rsp+1090h+var_1050], 1000h
0x180022b76  mov     [rsp+1090h+var_1068], rax
0x180022b7b  lea     r9, [rsp+1090h+var_104C]
0x180022b80  lea     rax, [rsp+1090h+var_1040]
0x180022b85  mov     [rsp+1090h+var_104C], 0
0x180022b8d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022b94  mov     [rsp+1090h+var_1070], rax
0x180022b99  call    wil_details_NtQueryWnfStateData
0x180022b9e  mov     ebx, eax
0x180022ba0  test    eax, eax
0x180022ba2  jnz     loc_180022C8E
0x180022ba8  mov     r9d, [rsp+1090h+var_1050]
0x180022bad  mov     rax, r12
0x180022bb0  mul     r9
0x180022bb3  shr     rdx, 3
0x180022bb7  lea     rcx, [rdx+rdx*2]
0x180022bbb  shl     rcx, 2
0x180022bbf  cmp     r9, rcx
0x180022bc2  jz      short loc_180022BCC
0x180022bc4  xor     r9d, r9d
0x180022bc7  mov     [rsp+1090h+var_1050], r9d
0x180022bcc  mov     r8, [r14]
0x180022bcf  mov     rax, r12
0x180022bd2  mov     ecx, r9d
0x180022bd5  mul     rcx
0x180022bd8  mov     rcx, [r14+8]
0x180022bdc  mov     rax, r12
0x180022bdf  mov     r10, rdx
0x180022be2  sub     rcx, r8
0x180022be5  mul     rcx
0x180022be8  shr     r10, 3
0x180022bec  shr     rdx, 3
0x180022bf0  lea     rax, [rdx+rdx*2]
0x180022bf4  lea     rdi, [r8+rax*4]
0x180022bf8  jmp     short loc_180022C63
0x180022bfa  mov     eax, r10d
0x180022bfd  lea     rcx, [rax+rax*2]
0x180022c01  lea     rdx, [rdx+rcx*4]
0x180022c05  lea     rax, [rsp+1090h+var_1040]
0x180022c0a  cmp     rax, rdx
0x180022c0d  jz      short loc_180022C34
0x180022c0f  mov     r11d, [r8]
0x180022c12  lea     rcx, [rsp+1090h+var_1040]
0x180022c17  cmp     [rcx], r11d
0x180022c1a  jnz     short loc_180022C2B
0x180022c1c  movzx   eax, word ptr [r8+4]
0x180022c21  cmp     [rcx+4], ax
0x180022c25  jz      loc_180022CCC
0x180022c2b  add     rcx, 0Ch
0x180022c2f  cmp     rcx, rdx
0x180022c32  jnz     short loc_180022C17
0x180022c34  mov     eax, r9d
0x180022c37  add     rax, 0Ch
0x180022c3b  cmp     rax, 1000h
0x180022c41  ja      short loc_180022C5F
0x180022c43  movsd   xmm0, qword ptr [r8]
0x180022c48  add     r9d, 0Ch
0x180022c4c  movsd   qword ptr [rdx], xmm0
0x180022c50  inc     r10d
0x180022c53  mov     eax, [r8+8]
0x180022c57  mov     [rdx+8], eax
0x180022c5a  mov     [rsp+1090h+var_1050], r9d
0x180022c5f  add     r8, 0Ch
0x180022c63  lea     rdx, [rsp+1090h+var_1040]
0x180022c68  cmp     r8, rdi
0x180022c6b  jnz     short loc_180022BFA
0x180022c6d  mov     eax, [rsp+1090h+var_104C]
0x180022c71  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022c78  mov     [rsp+1090h+var_1060], 1
0x180022c80  mov     r8d, r9d
0x180022c83  mov     dword ptr [rsp+1090h+var_1068], eax
0x180022c87  call    wil_details_NtUpdateWnfStateData
0x180022c8c  mov     edi, eax
0x180022c8e  cmp     edi, 0C0000001h
0x180022c94  jnz     short loc_180022CA5
0x180022c96  inc     esi
0x180022c98  cmp     esi, 64h ; 'd'
0x180022c9b  jge     short loc_180022CA5
0x180022c9d  test    ebx, ebx
0x180022c9f  jz      loc_180022B57
0x180022ca5  test    ebx, ebx
0x180022ca7  cmovz   ebx, edi
0x180022caa  mov     eax, ebx
0x180022cac  mov     rcx, [rbp+0F90h+var_40]
0x180022cb3  xor     rcx, rsp; StackCookie
0x180022cb6  call    __security_check_cookie
0x180022cbb  add     rsp, 1068h
0x180022cc2  pop     r14
0x180022cc4  pop     r12
0x180022cc6  pop     rdi
0x180022cc7  pop     rsi
0x180022cc8  pop     rbx
0x180022cc9  pop     rbp
0x180022cca  retn
0x180022ccc  mov     eax, [r8+8]
0x180022cd0  add     [rcx+8], eax
0x180022cd3  mov     r9d, [rsp+1090h+var_1050]
0x180022cd8  jmp     short loc_180022C5F
```
