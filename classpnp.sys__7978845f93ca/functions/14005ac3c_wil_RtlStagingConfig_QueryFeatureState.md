# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14005ac3c`
- end: `0x14005acf7`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140028708`

## callees

- `0x14003e430`
- `0x14005ac3c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005ac7c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005ac7c`

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
0x14005ac3c  mov     r11, rsp
0x14005ac3f  push    rbx
0x14005ac40  sub     rsp, 40h
0x14005ac44  mov     rax, cs:__security_cookie
0x14005ac4b  xor     rax, rsp
0x14005ac4e  mov     [rsp+48h+var_10], rax
0x14005ac53  mov     eax, edx
0x14005ac55  mov     qword ptr [r11-28h], 0
0x14005ac5d  mov     rbx, rcx
0x14005ac60  lea     r9, [r11-20h]
0x14005ac64  xor     ecx, ecx
0x14005ac66  xor     edx, edx
0x14005ac68  test    r8d, r8d
0x14005ac6b  mov     [r11-20h], rcx
0x14005ac6f  mov     [rsp+48h+var_18], ecx
0x14005ac73  lea     r8, [r11-28h]
0x14005ac77  setz    dl
0x14005ac7a  mov     ecx, eax
0x14005ac7c  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005ac83  nop     dword ptr [rax+rax+00h]
0x14005ac88  test    eax, eax
0x14005ac8a  jnz     short loc_14005ACC7
0x14005ac8c  mov     ecx, [rsp+48h+var_1C]
0x14005ac90  mov     edx, 1
0x14005ac95  mov     eax, ecx
0x14005ac97  shr     eax, 4
0x14005ac9a  and     eax, 3
0x14005ac9d  mov     [rbx], eax
0x14005ac9f  mov     eax, ecx
0x14005aca1  shr     eax, 8
0x14005aca4  and     al, 3Fh
0x14005aca6  mov     [rbx+4], al
0x14005aca9  mov     eax, [rsp+48h+var_18]
0x14005acad  mov     [rbx+0Ch], eax
0x14005acb0  mov     eax, ecx
0x14005acb2  shr     eax, 0Eh
0x14005acb5  and     eax, 3
0x14005acb8  mov     [rbx+8], eax
0x14005acbb  mov     eax, ecx
0x14005acbd  shr     eax, 6
0x14005acc0  and     eax, edx
0x14005acc2  mov     [rbx+14h], eax
0x14005acc5  jmp     short loc_14005ACD9
0x14005acc7  xor     edx, edx
0x14005acc9  cmp     eax, 117h
0x14005acce  jnz     short loc_14005ACE1
0x14005acd0  mov     ecx, [rsp+48h+var_1C]
0x14005acd4  mov     edx, 1
0x14005acd9  shr     ecx, 7
0x14005acdc  and     ecx, edx
0x14005acde  mov     [rbx+10h], ecx
0x14005ace1  mov     eax, edx
0x14005ace3  mov     rcx, [rsp+48h+var_10]
0x14005ace8  xor     rcx, rsp; StackCookie
0x14005aceb  call    __security_check_cookie
0x14005acf0  add     rsp, 40h
0x14005acf4  pop     rbx
0x14005acf5  retn
```
