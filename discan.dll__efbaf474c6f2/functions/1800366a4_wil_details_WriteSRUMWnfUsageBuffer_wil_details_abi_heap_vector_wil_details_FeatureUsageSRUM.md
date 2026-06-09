# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800366a4`
- end: `0x18003686e`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180031490`

## callees

- `0x1800366a4`
- `0x1800369cc`
- `0x180036a44`
- `0x1800375ee`
- `0x180037620`
- `0x1800376e0`

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
0x1800366a4  push    rbp
0x1800366a6  push    rbx
0x1800366a7  push    rsi
0x1800366a8  push    rdi
0x1800366a9  push    r12
0x1800366ab  push    r14
0x1800366ad  lea     rbp, [rsp-0F68h]
0x1800366b5  mov     eax, 1068h
0x1800366ba  call    _alloca_probe
0x1800366bf  sub     rsp, rax
0x1800366c2  mov     rax, cs:__security_cookie
0x1800366c9  xor     rax, rsp
0x1800366cc  mov     [rbp+0F90h+var_40], rax
0x1800366d3  mov     rax, [rcx+8]
0x1800366d7  xor     ebx, ebx
0x1800366d9  sub     rax, [rcx]
0x1800366dc  xor     edi, edi
0x1800366de  mov     r14, rcx
0x1800366e1  cmp     rax, 0Ch
0x1800366e5  jb      loc_180036848
0x1800366eb  xor     esi, esi
0x1800366ed  mov     r12, 0AAAAAAAAAAAAAAABh
0x1800366f7  xor     edx, edx; Val
0x1800366f9  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800366fe  mov     r8d, 1000h; Size
0x180036704  call    memset_0
0x180036709  lea     rax, [rsp+1090h+var_1050]
0x18003670e  mov     [rsp+1090h+var_1050], 1000h
0x180036716  mov     [rsp+1090h+var_1068], rax
0x18003671b  lea     r9, [rsp+1090h+var_104C]
0x180036720  lea     rax, [rsp+1090h+var_1040]
0x180036725  mov     [rsp+1090h+var_104C], 0
0x18003672d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180036734  mov     [rsp+1090h+var_1070], rax
0x180036739  call    wil_details_NtQueryWnfStateData
0x18003673e  mov     ebx, eax
0x180036740  test    eax, eax
0x180036742  jnz     loc_180036831
0x180036748  mov     r9d, [rsp+1090h+var_1050]
0x18003674d  mov     rax, r12
0x180036750  mul     r9
0x180036753  shr     rdx, 3
0x180036757  lea     rcx, [rdx+rdx*2]
0x18003675b  shl     rcx, 2
0x18003675f  cmp     r9, rcx
0x180036762  jz      short loc_18003676C
0x180036764  xor     r9d, r9d
0x180036767  mov     [rsp+1090h+var_1050], r9d
0x18003676c  mov     r8, [r14]
0x18003676f  mov     rax, r12
0x180036772  mov     ecx, r9d
0x180036775  mul     rcx
0x180036778  mov     rcx, [r14+8]
0x18003677c  mov     rax, r12
0x18003677f  mov     r11, rdx
0x180036782  sub     rcx, r8
0x180036785  mul     rcx
0x180036788  shr     r11, 3
0x18003678c  shr     rdx, 3
0x180036790  lea     rax, [rdx+rdx*2]
0x180036794  lea     rdi, [r8+rax*4]
0x180036798  jmp     short loc_180036806
0x18003679a  mov     eax, r11d
0x18003679d  lea     r10, [rsp+1090h+var_1040]
0x1800367a2  lea     rcx, [rax+rax*2]
0x1800367a6  lea     r10, [r10+rcx*4]
0x1800367aa  cmp     rdx, r10
0x1800367ad  jz      short loc_1800367D5
0x1800367af  mov     eax, [r8]
0x1800367b2  cmp     [rdx], eax
0x1800367b4  jnz     short loc_1800367C1
0x1800367b6  movzx   eax, word ptr [r8+4]
0x1800367bb  cmp     [rdx+4], ax
0x1800367bf  jz      short loc_1800367C7
0x1800367c1  add     rdx, 0Ch
0x1800367c5  jmp     short loc_1800367AA
0x1800367c7  mov     eax, [r8+8]
0x1800367cb  add     [rdx+8], eax
0x1800367ce  mov     r9d, [rsp+1090h+var_1050]
0x1800367d3  jmp     short loc_180036802
0x1800367d5  mov     eax, r9d
0x1800367d8  add     rax, 0Ch
0x1800367dc  cmp     rax, 1000h
0x1800367e2  ja      short loc_180036802
0x1800367e4  movsd   xmm0, qword ptr [r8]
0x1800367e9  add     r9d, 0Ch
0x1800367ed  movsd   qword ptr [r10], xmm0
0x1800367f2  inc     r11d
0x1800367f5  mov     eax, [r8+8]
0x1800367f9  mov     [r10+8], eax
0x1800367fd  mov     [rsp+1090h+var_1050], r9d
0x180036802  add     r8, 0Ch
0x180036806  lea     rdx, [rsp+1090h+var_1040]
0x18003680b  cmp     r8, rdi
0x18003680e  jnz     short loc_18003679A
0x180036810  mov     eax, [rsp+1090h+var_104C]
0x180036814  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18003681b  mov     [rsp+1090h+var_1060], 1
0x180036823  mov     r8d, r9d
0x180036826  mov     dword ptr [rsp+1090h+var_1068], eax
0x18003682a  call    wil_details_NtUpdateWnfStateData
0x18003682f  mov     edi, eax
0x180036831  cmp     edi, 0C0000001h
0x180036837  jnz     short loc_180036848
0x180036839  inc     esi
0x18003683b  cmp     esi, 64h ; 'd'
0x18003683e  jge     short loc_180036848
0x180036840  test    ebx, ebx
0x180036842  jz      loc_1800366F7
0x180036848  test    ebx, ebx
0x18003684a  cmovz   ebx, edi
0x18003684d  mov     eax, ebx
0x18003684f  mov     rcx, [rbp+0F90h+var_40]
0x180036856  xor     rcx, rsp; StackCookie
0x180036859  call    __security_check_cookie
0x18003685e  add     rsp, 1068h
0x180036865  pop     r14
0x180036867  pop     r12
0x180036869  pop     rdi
0x18003686a  pop     rsi
0x18003686b  pop     rbx
0x18003686c  pop     rbp
0x18003686d  retn
```
