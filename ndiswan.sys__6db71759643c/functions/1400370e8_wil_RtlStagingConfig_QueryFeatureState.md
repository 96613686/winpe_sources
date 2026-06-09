# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1400370e8`
- end: `0x1400371a3`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000ae3c`

## callees

- `0x1400161f0`
- `0x1400370e8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140037128`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140037128`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // edx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+30h] [rbp-18h]

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v4 = RtlQueryFeatureConfiguration(a2, a3 == 0, &v8, &v9);
  if ( !v4 )
  {
    v5 = HIDWORD(v9);
    v6 = 1;
    *(_DWORD *)a1 = (HIDWORD(v9) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v5) & 0x3F;
    *(_DWORD *)(a1 + 12) = v10;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v5 >> 14;
    *(_DWORD *)(a1 + 20) = (v5 >> 6) & 1;
LABEL_5:
    *(_DWORD *)(a1 + 16) = (v5 >> 7) & 1;
    return v6;
  }
  v6 = 0;
  if ( v4 == 279 )
  {
    v5 = HIDWORD(v9);
    v6 = 1;
    goto LABEL_5;
  }
  return v6;
}

```

## disassembly

```asm
0x1400370e8  mov     r11, rsp
0x1400370eb  push    rbx
0x1400370ec  sub     rsp, 40h
0x1400370f0  mov     rax, cs:__security_cookie
0x1400370f7  xor     rax, rsp
0x1400370fa  mov     [rsp+48h+var_10], rax
0x1400370ff  mov     eax, edx
0x140037101  mov     qword ptr [r11-28h], 0
0x140037109  mov     rbx, rcx
0x14003710c  lea     r9, [r11-20h]
0x140037110  xor     ecx, ecx
0x140037112  xor     edx, edx
0x140037114  test    r8d, r8d
0x140037117  mov     [r11-20h], rcx
0x14003711b  mov     [rsp+48h+var_18], ecx
0x14003711f  lea     r8, [r11-28h]
0x140037123  setz    dl
0x140037126  mov     ecx, eax
0x140037128  call    cs:__imp_RtlQueryFeatureConfiguration
0x14003712f  nop     dword ptr [rax+rax+00h]
0x140037134  test    eax, eax
0x140037136  jnz     short loc_140037173
0x140037138  mov     ecx, [rsp+48h+var_1C]
0x14003713c  mov     edx, 1
0x140037141  mov     eax, ecx
0x140037143  shr     eax, 4
0x140037146  and     eax, 3
0x140037149  mov     [rbx], eax
0x14003714b  mov     eax, ecx
0x14003714d  shr     eax, 8
0x140037150  and     al, 3Fh
0x140037152  mov     [rbx+4], al
0x140037155  mov     eax, [rsp+48h+var_18]
0x140037159  mov     [rbx+0Ch], eax
0x14003715c  mov     eax, ecx
0x14003715e  shr     eax, 0Eh
0x140037161  and     eax, 3
0x140037164  mov     [rbx+8], eax
0x140037167  mov     eax, ecx
0x140037169  shr     eax, 6
0x14003716c  and     eax, edx
0x14003716e  mov     [rbx+14h], eax
0x140037171  jmp     short loc_140037185
0x140037173  xor     edx, edx
0x140037175  cmp     eax, 117h
0x14003717a  jnz     short loc_14003718D
0x14003717c  mov     ecx, [rsp+48h+var_1C]
0x140037180  mov     edx, 1
0x140037185  shr     ecx, 7
0x140037188  and     ecx, edx
0x14003718a  mov     [rbx+10h], ecx
0x14003718d  mov     eax, edx
0x14003718f  mov     rcx, [rsp+48h+var_10]
0x140037194  xor     rcx, rsp; StackCookie
0x140037197  call    __security_check_cookie
0x14003719c  add     rsp, 40h
0x1400371a0  pop     rbx
0x1400371a1  retn
```
