# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180039118`
- end: `0x1800391d3`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e0b4`

## callees

- `0x180027ba0`
- `0x180039118`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180039158`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180039158`

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
0x180039118  mov     r11, rsp
0x18003911b  push    rbx
0x18003911c  sub     rsp, 40h
0x180039120  mov     rax, cs:__security_cookie
0x180039127  xor     rax, rsp
0x18003912a  mov     [rsp+48h+var_10], rax
0x18003912f  mov     eax, edx
0x180039131  mov     qword ptr [r11-28h], 0
0x180039139  mov     rbx, rcx
0x18003913c  lea     r9, [r11-20h]
0x180039140  xor     ecx, ecx
0x180039142  xor     edx, edx
0x180039144  test    r8d, r8d
0x180039147  mov     [r11-20h], rcx
0x18003914b  mov     [rsp+48h+var_18], ecx
0x18003914f  lea     r8, [r11-28h]
0x180039153  setz    dl
0x180039156  mov     ecx, eax
0x180039158  call    cs:__imp_RtlQueryFeatureConfiguration
0x18003915f  nop     dword ptr [rax+rax+00h]
0x180039164  test    eax, eax
0x180039166  jnz     short loc_1800391A3
0x180039168  mov     ecx, [rsp+48h+var_1C]
0x18003916c  mov     edx, 1
0x180039171  mov     eax, ecx
0x180039173  shr     eax, 4
0x180039176  and     eax, 3
0x180039179  mov     [rbx], eax
0x18003917b  mov     eax, ecx
0x18003917d  shr     eax, 8
0x180039180  and     al, 3Fh
0x180039182  mov     [rbx+4], al
0x180039185  mov     eax, [rsp+48h+var_18]
0x180039189  mov     [rbx+0Ch], eax
0x18003918c  mov     eax, ecx
0x18003918e  shr     eax, 0Eh
0x180039191  and     eax, 3
0x180039194  mov     [rbx+8], eax
0x180039197  mov     eax, ecx
0x180039199  shr     eax, 6
0x18003919c  and     eax, edx
0x18003919e  mov     [rbx+14h], eax
0x1800391a1  jmp     short loc_1800391B5
0x1800391a3  xor     edx, edx
0x1800391a5  cmp     eax, 117h
0x1800391aa  jnz     short loc_1800391BD
0x1800391ac  mov     ecx, [rsp+48h+var_1C]
0x1800391b0  mov     edx, 1
0x1800391b5  shr     ecx, 7
0x1800391b8  and     ecx, edx
0x1800391ba  mov     [rbx+10h], ecx
0x1800391bd  mov     eax, edx
0x1800391bf  mov     rcx, [rsp+48h+var_10]
0x1800391c4  xor     rcx, rsp; StackCookie
0x1800391c7  call    __security_check_cookie
0x1800391cc  add     rsp, 40h
0x1800391d0  pop     rbx
0x1800391d1  retn
```
