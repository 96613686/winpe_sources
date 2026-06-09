# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140015078`
- end: `0x140015133`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140002f34`

## callees

- `0x140005bb0`
- `0x140015078`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400150b8`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400150b8`

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
  v4 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(a2, a3 == 0, &v8, &v9);
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
0x140015078  mov     r11, rsp
0x14001507b  push    rbx
0x14001507c  sub     rsp, 40h
0x140015080  mov     rax, cs:__security_cookie
0x140015087  xor     rax, rsp
0x14001508a  mov     [rsp+48h+var_10], rax
0x14001508f  mov     eax, edx
0x140015091  mov     qword ptr [r11-28h], 0
0x140015099  mov     rbx, rcx
0x14001509c  lea     r9, [r11-20h]
0x1400150a0  xor     ecx, ecx
0x1400150a2  xor     edx, edx
0x1400150a4  test    r8d, r8d
0x1400150a7  mov     [r11-20h], rcx
0x1400150ab  mov     [rsp+48h+var_18], ecx
0x1400150af  lea     r8, [r11-28h]
0x1400150b3  setz    dl
0x1400150b6  mov     ecx, eax
0x1400150b8  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400150bf  nop     dword ptr [rax+rax+00h]
0x1400150c4  test    eax, eax
0x1400150c6  jnz     short loc_140015103
0x1400150c8  mov     ecx, [rsp+48h+var_1C]
0x1400150cc  mov     edx, 1
0x1400150d1  mov     eax, ecx
0x1400150d3  shr     eax, 4
0x1400150d6  and     eax, 3
0x1400150d9  mov     [rbx], eax
0x1400150db  mov     eax, ecx
0x1400150dd  shr     eax, 8
0x1400150e0  and     al, 3Fh
0x1400150e2  mov     [rbx+4], al
0x1400150e5  mov     eax, [rsp+48h+var_18]
0x1400150e9  mov     [rbx+0Ch], eax
0x1400150ec  mov     eax, ecx
0x1400150ee  shr     eax, 0Eh
0x1400150f1  and     eax, 3
0x1400150f4  mov     [rbx+8], eax
0x1400150f7  mov     eax, ecx
0x1400150f9  shr     eax, 6
0x1400150fc  and     eax, edx
0x1400150fe  mov     [rbx+14h], eax
0x140015101  jmp     short loc_140015115
0x140015103  xor     edx, edx
0x140015105  cmp     eax, 117h
0x14001510a  jnz     short loc_14001511D
0x14001510c  mov     ecx, [rsp+48h+var_1C]
0x140015110  mov     edx, 1
0x140015115  shr     ecx, 7
0x140015118  and     ecx, edx
0x14001511a  mov     [rbx+10h], ecx
0x14001511d  mov     eax, edx
0x14001511f  mov     rcx, [rsp+48h+var_10]
0x140015124  xor     rcx, rsp; StackCookie
0x140015127  call    __security_check_cookie
0x14001512c  add     rsp, 40h
0x140015130  pop     rbx
0x140015131  retn
```
