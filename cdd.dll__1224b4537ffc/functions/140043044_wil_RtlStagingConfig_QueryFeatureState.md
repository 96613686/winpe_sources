# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140043044`
- end: `0x1400430ff`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140029bd0`

## callees

- `0x1400371f0`
- `0x140043044`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140043084`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140043084`

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
0x140043044  mov     r11, rsp
0x140043047  push    rbx
0x140043048  sub     rsp, 40h
0x14004304c  mov     rax, cs:__security_cookie
0x140043053  xor     rax, rsp
0x140043056  mov     [rsp+48h+var_10], rax
0x14004305b  mov     eax, edx
0x14004305d  mov     qword ptr [r11-28h], 0
0x140043065  mov     rbx, rcx
0x140043068  lea     r9, [r11-20h]
0x14004306c  xor     ecx, ecx
0x14004306e  xor     edx, edx
0x140043070  test    r8d, r8d
0x140043073  mov     [r11-20h], rcx
0x140043077  mov     [rsp+48h+var_18], ecx
0x14004307b  lea     r8, [r11-28h]
0x14004307f  setz    dl
0x140043082  mov     ecx, eax
0x140043084  call    cs:__imp_RtlQueryFeatureConfiguration
0x14004308b  nop     dword ptr [rax+rax+00h]
0x140043090  test    eax, eax
0x140043092  jnz     short loc_1400430CF
0x140043094  mov     ecx, [rsp+48h+var_1C]
0x140043098  mov     edx, 1
0x14004309d  mov     eax, ecx
0x14004309f  shr     eax, 4
0x1400430a2  and     eax, 3
0x1400430a5  mov     [rbx], eax
0x1400430a7  mov     eax, ecx
0x1400430a9  shr     eax, 8
0x1400430ac  and     al, 3Fh
0x1400430ae  mov     [rbx+4], al
0x1400430b1  mov     eax, [rsp+48h+var_18]
0x1400430b5  mov     [rbx+0Ch], eax
0x1400430b8  mov     eax, ecx
0x1400430ba  shr     eax, 0Eh
0x1400430bd  and     eax, 3
0x1400430c0  mov     [rbx+8], eax
0x1400430c3  mov     eax, ecx
0x1400430c5  shr     eax, 6
0x1400430c8  and     eax, edx
0x1400430ca  mov     [rbx+14h], eax
0x1400430cd  jmp     short loc_1400430E1
0x1400430cf  xor     edx, edx
0x1400430d1  cmp     eax, 117h
0x1400430d6  jnz     short loc_1400430E9
0x1400430d8  mov     ecx, [rsp+48h+var_1C]
0x1400430dc  mov     edx, 1
0x1400430e1  shr     ecx, 7
0x1400430e4  and     ecx, edx
0x1400430e6  mov     [rbx+10h], ecx
0x1400430e9  mov     eax, edx
0x1400430eb  mov     rcx, [rsp+48h+var_10]
0x1400430f0  xor     rcx, rsp; StackCookie
0x1400430f3  call    __security_check_cookie
0x1400430f8  add     rsp, 40h
0x1400430fc  pop     rbx
0x1400430fd  retn
```
