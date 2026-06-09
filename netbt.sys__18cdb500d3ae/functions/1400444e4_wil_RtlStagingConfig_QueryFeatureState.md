# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1400444e4`
- end: `0x14004459f`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002b790`

## callees

- `0x140030f40`
- `0x1400444e4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140044524`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140044524`

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
0x1400444e4  mov     r11, rsp
0x1400444e7  push    rbx
0x1400444e8  sub     rsp, 40h
0x1400444ec  mov     rax, cs:__security_cookie
0x1400444f3  xor     rax, rsp
0x1400444f6  mov     [rsp+48h+var_10], rax
0x1400444fb  mov     eax, edx
0x1400444fd  mov     qword ptr [r11-28h], 0
0x140044505  mov     rbx, rcx
0x140044508  lea     r9, [r11-20h]
0x14004450c  xor     ecx, ecx
0x14004450e  xor     edx, edx
0x140044510  test    r8d, r8d
0x140044513  mov     [r11-20h], rcx
0x140044517  mov     [rsp+48h+var_18], ecx
0x14004451b  lea     r8, [r11-28h]
0x14004451f  setz    dl
0x140044522  mov     ecx, eax
0x140044524  call    cs:__imp_RtlQueryFeatureConfiguration
0x14004452b  nop     dword ptr [rax+rax+00h]
0x140044530  test    eax, eax
0x140044532  jnz     short loc_14004456F
0x140044534  mov     ecx, [rsp+48h+var_1C]
0x140044538  mov     edx, 1
0x14004453d  mov     eax, ecx
0x14004453f  shr     eax, 4
0x140044542  and     eax, 3
0x140044545  mov     [rbx], eax
0x140044547  mov     eax, ecx
0x140044549  shr     eax, 8
0x14004454c  and     al, 3Fh
0x14004454e  mov     [rbx+4], al
0x140044551  mov     eax, [rsp+48h+var_18]
0x140044555  mov     [rbx+0Ch], eax
0x140044558  mov     eax, ecx
0x14004455a  shr     eax, 0Eh
0x14004455d  and     eax, 3
0x140044560  mov     [rbx+8], eax
0x140044563  mov     eax, ecx
0x140044565  shr     eax, 6
0x140044568  and     eax, edx
0x14004456a  mov     [rbx+14h], eax
0x14004456d  jmp     short loc_140044581
0x14004456f  xor     edx, edx
0x140044571  cmp     eax, 117h
0x140044576  jnz     short loc_140044589
0x140044578  mov     ecx, [rsp+48h+var_1C]
0x14004457c  mov     edx, 1
0x140044581  shr     ecx, 7
0x140044584  and     ecx, edx
0x140044586  mov     [rbx+10h], ecx
0x140044589  mov     eax, edx
0x14004458b  mov     rcx, [rsp+48h+var_10]
0x140044590  xor     rcx, rsp; StackCookie
0x140044593  call    __security_check_cookie
0x140044598  add     rsp, 40h
0x14004459c  pop     rbx
0x14004459d  retn
```
