# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180022bd0`
- end: `0x180022c8b`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f190`

## callees

- `0x180010840`
- `0x180022bd0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180022c10`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180022c10`

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
0x180022bd0  mov     r11, rsp
0x180022bd3  push    rbx
0x180022bd4  sub     rsp, 40h
0x180022bd8  mov     rax, cs:__security_cookie
0x180022bdf  xor     rax, rsp
0x180022be2  mov     [rsp+48h+var_10], rax
0x180022be7  mov     eax, edx
0x180022be9  mov     qword ptr [r11-28h], 0
0x180022bf1  mov     rbx, rcx
0x180022bf4  lea     r9, [r11-20h]
0x180022bf8  xor     ecx, ecx
0x180022bfa  xor     edx, edx
0x180022bfc  test    r8d, r8d
0x180022bff  mov     [r11-20h], rcx
0x180022c03  mov     [rsp+48h+var_18], ecx
0x180022c07  lea     r8, [r11-28h]
0x180022c0b  setz    dl
0x180022c0e  mov     ecx, eax
0x180022c10  call    cs:__imp_RtlQueryFeatureConfiguration
0x180022c17  nop     dword ptr [rax+rax+00h]
0x180022c1c  test    eax, eax
0x180022c1e  jnz     short loc_180022C5B
0x180022c20  mov     ecx, [rsp+48h+var_1C]
0x180022c24  mov     edx, 1
0x180022c29  mov     eax, ecx
0x180022c2b  shr     eax, 4
0x180022c2e  and     eax, 3
0x180022c31  mov     [rbx], eax
0x180022c33  mov     eax, ecx
0x180022c35  shr     eax, 8
0x180022c38  and     al, 3Fh
0x180022c3a  mov     [rbx+4], al
0x180022c3d  mov     eax, [rsp+48h+var_18]
0x180022c41  mov     [rbx+0Ch], eax
0x180022c44  mov     eax, ecx
0x180022c46  shr     eax, 0Eh
0x180022c49  and     eax, 3
0x180022c4c  mov     [rbx+8], eax
0x180022c4f  mov     eax, ecx
0x180022c51  shr     eax, 6
0x180022c54  and     eax, edx
0x180022c56  mov     [rbx+14h], eax
0x180022c59  jmp     short loc_180022C6D
0x180022c5b  xor     edx, edx
0x180022c5d  cmp     eax, 117h
0x180022c62  jnz     short loc_180022C75
0x180022c64  mov     ecx, [rsp+48h+var_1C]
0x180022c68  mov     edx, 1
0x180022c6d  shr     ecx, 7
0x180022c70  and     ecx, edx
0x180022c72  mov     [rbx+10h], ecx
0x180022c75  mov     eax, edx
0x180022c77  mov     rcx, [rsp+48h+var_10]
0x180022c7c  xor     rcx, rsp; StackCookie
0x180022c7f  call    __security_check_cookie
0x180022c84  add     rsp, 40h
0x180022c88  pop     rbx
0x180022c89  retn
```
