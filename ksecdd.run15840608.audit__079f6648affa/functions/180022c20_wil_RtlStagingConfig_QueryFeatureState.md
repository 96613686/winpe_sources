# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180022c20`
- end: `0x180022cdb`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f230`

## callees

- `0x1800108a0`
- `0x180022c20`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180022c60`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180022c60`

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
0x180022c20  mov     r11, rsp
0x180022c23  push    rbx
0x180022c24  sub     rsp, 40h
0x180022c28  mov     rax, cs:__security_cookie
0x180022c2f  xor     rax, rsp
0x180022c32  mov     [rsp+48h+var_10], rax
0x180022c37  mov     eax, edx
0x180022c39  mov     qword ptr [r11-28h], 0
0x180022c41  mov     rbx, rcx
0x180022c44  lea     r9, [r11-20h]
0x180022c48  xor     ecx, ecx
0x180022c4a  xor     edx, edx
0x180022c4c  test    r8d, r8d
0x180022c4f  mov     [r11-20h], rcx
0x180022c53  mov     [rsp+48h+var_18], ecx
0x180022c57  lea     r8, [r11-28h]
0x180022c5b  setz    dl
0x180022c5e  mov     ecx, eax
0x180022c60  call    cs:__imp_RtlQueryFeatureConfiguration
0x180022c67  nop     dword ptr [rax+rax+00h]
0x180022c6c  test    eax, eax
0x180022c6e  jnz     short loc_180022CAB
0x180022c70  mov     ecx, [rsp+48h+var_1C]
0x180022c74  mov     edx, 1
0x180022c79  mov     eax, ecx
0x180022c7b  shr     eax, 4
0x180022c7e  and     eax, 3
0x180022c81  mov     [rbx], eax
0x180022c83  mov     eax, ecx
0x180022c85  shr     eax, 8
0x180022c88  and     al, 3Fh
0x180022c8a  mov     [rbx+4], al
0x180022c8d  mov     eax, [rsp+48h+var_18]
0x180022c91  mov     [rbx+0Ch], eax
0x180022c94  mov     eax, ecx
0x180022c96  shr     eax, 0Eh
0x180022c99  and     eax, 3
0x180022c9c  mov     [rbx+8], eax
0x180022c9f  mov     eax, ecx
0x180022ca1  shr     eax, 6
0x180022ca4  and     eax, edx
0x180022ca6  mov     [rbx+14h], eax
0x180022ca9  jmp     short loc_180022CBD
0x180022cab  xor     edx, edx
0x180022cad  cmp     eax, 117h
0x180022cb2  jnz     short loc_180022CC5
0x180022cb4  mov     ecx, [rsp+48h+var_1C]
0x180022cb8  mov     edx, 1
0x180022cbd  shr     ecx, 7
0x180022cc0  and     ecx, edx
0x180022cc2  mov     [rbx+10h], ecx
0x180022cc5  mov     eax, edx
0x180022cc7  mov     rcx, [rsp+48h+var_10]
0x180022ccc  xor     rcx, rsp; StackCookie
0x180022ccf  call    __security_check_cookie
0x180022cd4  add     rsp, 40h
0x180022cd8  pop     rbx
0x180022cd9  retn
```
