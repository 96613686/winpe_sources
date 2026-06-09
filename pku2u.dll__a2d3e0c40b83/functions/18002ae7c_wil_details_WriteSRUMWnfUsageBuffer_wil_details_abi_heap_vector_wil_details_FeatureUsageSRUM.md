# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18002ae7c`
- end: `0x18002b046`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800272e0`

## callees

- `0x1800210f0`
- `0x180021a54`
- `0x18002ae7c`
- `0x18002bd24`
- `0x18002bd9c`
- `0x180044f20`

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
0x18002ae7c  push    rbp
0x18002ae7e  push    rbx
0x18002ae7f  push    rsi
0x18002ae80  push    rdi
0x18002ae81  push    r12
0x18002ae83  push    r14
0x18002ae85  lea     rbp, [rsp-0F68h]
0x18002ae8d  mov     eax, 1068h
0x18002ae92  call    _alloca_probe
0x18002ae97  sub     rsp, rax
0x18002ae9a  mov     rax, cs:__security_cookie
0x18002aea1  xor     rax, rsp
0x18002aea4  mov     [rbp+0F90h+var_40], rax
0x18002aeab  mov     rax, [rcx+8]
0x18002aeaf  xor     ebx, ebx
0x18002aeb1  sub     rax, [rcx]
0x18002aeb4  xor     edi, edi
0x18002aeb6  mov     r14, rcx
0x18002aeb9  cmp     rax, 0Ch
0x18002aebd  jb      loc_18002B020
0x18002aec3  xor     esi, esi
0x18002aec5  mov     r12, 0AAAAAAAAAAAAAAABh
0x18002aecf  xor     edx, edx; Val
0x18002aed1  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002aed6  mov     r8d, 1000h; Size
0x18002aedc  call    memset_0
0x18002aee1  lea     rax, [rsp+1090h+var_1050]
0x18002aee6  mov     [rsp+1090h+var_1050], 1000h
0x18002aeee  mov     [rsp+1090h+var_1068], rax
0x18002aef3  lea     r9, [rsp+1090h+var_104C]
0x18002aef8  lea     rax, [rsp+1090h+var_1040]
0x18002aefd  mov     [rsp+1090h+var_104C], 0
0x18002af05  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002af0c  mov     [rsp+1090h+var_1070], rax
0x18002af11  call    wil_details_NtQueryWnfStateData
0x18002af16  mov     ebx, eax
0x18002af18  test    eax, eax
0x18002af1a  jnz     loc_18002B009
0x18002af20  mov     r9d, [rsp+1090h+var_1050]
0x18002af25  mov     rax, r12
0x18002af28  mul     r9
0x18002af2b  shr     rdx, 3
0x18002af2f  lea     rcx, [rdx+rdx*2]
0x18002af33  shl     rcx, 2
0x18002af37  cmp     r9, rcx
0x18002af3a  jz      short loc_18002AF44
0x18002af3c  xor     r9d, r9d
0x18002af3f  mov     [rsp+1090h+var_1050], r9d
0x18002af44  mov     r8, [r14]
0x18002af47  mov     rax, r12
0x18002af4a  mov     ecx, r9d
0x18002af4d  mul     rcx
0x18002af50  mov     rcx, [r14+8]
0x18002af54  mov     rax, r12
0x18002af57  mov     r11, rdx
0x18002af5a  sub     rcx, r8
0x18002af5d  mul     rcx
0x18002af60  shr     r11, 3
0x18002af64  shr     rdx, 3
0x18002af68  lea     rax, [rdx+rdx*2]
0x18002af6c  lea     rdi, [r8+rax*4]
0x18002af70  jmp     short loc_18002AFDE
0x18002af72  mov     eax, r11d
0x18002af75  lea     r10, [rsp+1090h+var_1040]
0x18002af7a  lea     rcx, [rax+rax*2]
0x18002af7e  lea     r10, [r10+rcx*4]
0x18002af82  cmp     rdx, r10
0x18002af85  jz      short loc_18002AFAD
0x18002af87  mov     eax, [r8]
0x18002af8a  cmp     [rdx], eax
0x18002af8c  jnz     short loc_18002AF99
0x18002af8e  movzx   eax, word ptr [r8+4]
0x18002af93  cmp     [rdx+4], ax
0x18002af97  jz      short loc_18002AF9F
0x18002af99  add     rdx, 0Ch
0x18002af9d  jmp     short loc_18002AF82
0x18002af9f  mov     eax, [r8+8]
0x18002afa3  add     [rdx+8], eax
0x18002afa6  mov     r9d, [rsp+1090h+var_1050]
0x18002afab  jmp     short loc_18002AFDA
0x18002afad  mov     eax, r9d
0x18002afb0  add     rax, 0Ch
0x18002afb4  cmp     rax, 1000h
0x18002afba  ja      short loc_18002AFDA
0x18002afbc  movsd   xmm0, qword ptr [r8]
0x18002afc1  add     r9d, 0Ch
0x18002afc5  movsd   qword ptr [r10], xmm0
0x18002afca  inc     r11d
0x18002afcd  mov     eax, [r8+8]
0x18002afd1  mov     [r10+8], eax
0x18002afd5  mov     [rsp+1090h+var_1050], r9d
0x18002afda  add     r8, 0Ch
0x18002afde  lea     rdx, [rsp+1090h+var_1040]
0x18002afe3  cmp     r8, rdi
0x18002afe6  jnz     short loc_18002AF72
0x18002afe8  mov     eax, [rsp+1090h+var_104C]
0x18002afec  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002aff3  mov     [rsp+1090h+var_1060], 1
0x18002affb  mov     r8d, r9d
0x18002affe  mov     dword ptr [rsp+1090h+var_1068], eax
0x18002b002  call    wil_details_NtUpdateWnfStateData
0x18002b007  mov     edi, eax
0x18002b009  cmp     edi, 0C0000001h
0x18002b00f  jnz     short loc_18002B020
0x18002b011  inc     esi
0x18002b013  cmp     esi, 64h ; 'd'
0x18002b016  jge     short loc_18002B020
0x18002b018  test    ebx, ebx
0x18002b01a  jz      loc_18002AECF
0x18002b020  test    ebx, ebx
0x18002b022  cmovz   ebx, edi
0x18002b025  mov     eax, ebx
0x18002b027  mov     rcx, [rbp+0F90h+var_40]
0x18002b02e  xor     rcx, rsp; StackCookie
0x18002b031  call    __security_check_cookie
0x18002b036  add     rsp, 1068h
0x18002b03d  pop     r14
0x18002b03f  pop     r12
0x18002b041  pop     rdi
0x18002b042  pop     rsi
0x18002b043  pop     rbx
0x18002b044  pop     rbp
0x18002b045  retn
```
