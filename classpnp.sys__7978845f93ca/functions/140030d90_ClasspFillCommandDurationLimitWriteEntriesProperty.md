# ClasspFillCommandDurationLimitWriteEntriesProperty

- ea: `0x140030d90`
- end: `0x140030ec6`
- name: `ClasspFillCommandDurationLimitWriteEntriesProperty`
- size: `310`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140033924`

## callees

- `0x14002c674`
- `0x140030d90`
- `0x140030f14`

## pseudocode

```c
void __fastcall ClasspFillCommandDurationLimitWriteEntriesProperty(__int64 a1, __int64 a2)
{
  unsigned __int8 v2; // di
  __int64 i; // r11
  __int64 v5; // r10
  int v6; // ecx
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // r10
  __int64 v14; // r9
  __int64 v15; // r11
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r10
  __int64 v19; // r9
  __int64 v20; // r11
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r10
  __int64 v24; // r9
  __int64 v25; // r11
  __int64 v26; // rcx
  int CommandDurationLimitPolicy; // eax
  __int64 v28; // r10
  __int64 v29; // r9
  __int64 v30; // r11
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // r10
  __int64 v34; // r9
  __int64 v35; // r11
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // r10

  v2 = 0;
  for ( i = a2; v2 < *(_BYTE *)(i + 9); *(_DWORD *)(v38 + a1 + 48) = v37 )
  {
    v5 = 56LL * v2;
    v6 = *(_DWORD *)(v5 + a1 + 8);
    *(_DWORD *)(v5 + a1) = 56;
    *(_DWORD *)(v5 + a1 + 4) = 56;
    v7 = v6 ^ ((unsigned __int8)v6 ^ (unsigned __int8)(*(_DWORD *)(i + 20LL * v2 + 16) >> 1)) & 1;
    *(_DWORD *)(v5 + a1 + 8) = v7;
    v8 = v7 ^ ((unsigned __int8)v7 ^ (unsigned __int8)(*(_DWORD *)(i + 20LL * v2 + 16) >> 1)) & 2;
    *(_DWORD *)(v5 + a1 + 8) = v8;
    v9 = v8 ^ ((unsigned __int8)v8 ^ (unsigned __int8)(*(_DWORD *)(i + 20LL * v2 + 16) >> 1)) & 4;
    *(_DWORD *)(v5 + a1 + 8) = v9;
    v10 = v9 ^ ((unsigned __int8)v9 ^ (unsigned __int8)(*(_DWORD *)(i + 20LL * v2 + 16) >> 1)) & 8u;
    *(_DWORD *)(v5 + a1 + 8) = v10;
    v11 = v10 ^ ((unsigned __int8)v10 ^ (unsigned __int8)(*(_DWORD *)(i + 20LL * v2 + 16) >> 1)) & 0x10;
    *(_DWORD *)(v5 + a1 + 8) = v11;
    *(_DWORD *)(v5 + a1 + 8) = v11
                             ^ ((unsigned __int8)v11
                              ^ (unsigned __int8)(*(_DWORD *)(i + 20LL * v2 + 16) >> 1))
                             & 0x20;
    LOBYTE(v10) = *(_BYTE *)(i + 20LL * v2 + 20);
    v12 = ClasspConvertCommandLimitDurationTo100ns(v10, *(unsigned __int16 *)(i + 20LL * v2 + 24));
    *(_QWORD *)(v13 + a1 + 16) = v12;
    LOBYTE(v16) = *(_BYTE *)(v15 + 4 * v14 + 20);
    v17 = ClasspConvertCommandLimitDurationTo100ns(v16, *(unsigned __int16 *)(v15 + 4 * v14 + 26));
    *(_QWORD *)(v18 + a1 + 24) = v17;
    LOBYTE(v21) = *(_BYTE *)(v20 + 4 * v19 + 20);
    v22 = ClasspConvertCommandLimitDurationTo100ns(v21, *(unsigned __int16 *)(v20 + 4 * v19 + 28));
    *(_QWORD *)(v23 + a1 + 32) = v22;
    LOBYTE(v26) = *(_BYTE *)(v25 + 4 * v24 + 21);
    CommandDurationLimitPolicy = ClasspGetCommandDurationLimitPolicy(v26);
    *(_DWORD *)(v28 + a1 + 40) = CommandDurationLimitPolicy;
    LOBYTE(v31) = *(_BYTE *)(v30 + 4 * v29 + 22);
    v32 = ClasspGetCommandDurationLimitPolicy(v31);
    *(_DWORD *)(v33 + a1 + 44) = v32;
    LOBYTE(v36) = *(_BYTE *)(v35 + 4 * v34 + 23);
    v37 = ClasspGetCommandDurationLimitPolicy(v36);
    ++v2;
  }
}

```

## disassembly

```asm
0x140030d90  mov     [rsp+arg_0], rbx
0x140030d95  push    rdi
0x140030d96  sub     rsp, 20h
0x140030d9a  xor     dil, dil
0x140030d9d  mov     r11, rdx
0x140030da0  mov     rbx, rcx
0x140030da3  cmp     [rdx+9], dil
0x140030da7  jbe     loc_140030EBA
0x140030dad  movzx   eax, dil
0x140030db1  imul    r10, rax, 38h ; '8'
0x140030db5  lea     r9, [rax+rax*4]
0x140030db9  mov     ecx, [r10+rbx+8]
0x140030dbe  mov     dword ptr [r10+rbx], 38h ; '8'
0x140030dc6  mov     dword ptr [r10+rbx+4], 38h ; '8'
0x140030dcf  mov     eax, [r11+r9*4+10h]
0x140030dd4  shr     eax, 1
0x140030dd6  xor     eax, ecx
0x140030dd8  and     eax, 1
0x140030ddb  xor     eax, ecx
0x140030ddd  mov     [r10+rbx+8], eax
0x140030de2  mov     ecx, [r11+r9*4+10h]
0x140030de7  shr     ecx, 1
0x140030de9  xor     ecx, eax
0x140030deb  and     ecx, 2
0x140030dee  xor     ecx, eax
0x140030df0  mov     [r10+rbx+8], ecx
0x140030df5  mov     eax, [r11+r9*4+10h]
0x140030dfa  shr     eax, 1
0x140030dfc  xor     eax, ecx
0x140030dfe  and     eax, 4
0x140030e01  xor     eax, ecx
0x140030e03  mov     [r10+rbx+8], eax
0x140030e08  mov     ecx, [r11+r9*4+10h]
0x140030e0d  shr     ecx, 1
0x140030e0f  xor     ecx, eax
0x140030e11  and     ecx, 8
0x140030e14  xor     ecx, eax
0x140030e16  mov     [r10+rbx+8], ecx
0x140030e1b  mov     edx, [r11+r9*4+10h]
0x140030e20  shr     edx, 1
0x140030e22  xor     edx, ecx
0x140030e24  and     edx, 10h
0x140030e27  xor     edx, ecx
0x140030e29  mov     [r10+rbx+8], edx
0x140030e2e  mov     eax, [r11+r9*4+10h]
0x140030e33  shr     eax, 1
0x140030e35  xor     eax, edx
0x140030e37  and     eax, 20h
0x140030e3a  xor     eax, edx
0x140030e3c  mov     [r10+rbx+8], eax
0x140030e41  movzx   edx, word ptr [r11+r9*4+18h]
0x140030e47  mov     cl, [r11+r9*4+14h]
0x140030e4c  call    ClasspConvertCommandLimitDurationTo100ns
0x140030e51  mov     [r10+rbx+10h], rax
0x140030e56  movzx   edx, word ptr [r11+r9*4+1Ah]
0x140030e5c  mov     cl, [r11+r9*4+14h]
0x140030e61  call    ClasspConvertCommandLimitDurationTo100ns
0x140030e66  mov     [r10+rbx+18h], rax
0x140030e6b  movzx   edx, word ptr [r11+r9*4+1Ch]
0x140030e71  mov     cl, [r11+r9*4+14h]
0x140030e76  call    ClasspConvertCommandLimitDurationTo100ns
0x140030e7b  mov     [r10+rbx+20h], rax
0x140030e80  mov     cl, [r11+r9*4+15h]
0x140030e85  call    ClasspGetCommandDurationLimitPolicy
0x140030e8a  mov     [r10+rbx+28h], eax
0x140030e8f  mov     cl, [r11+r9*4+16h]
0x140030e94  call    ClasspGetCommandDurationLimitPolicy
0x140030e99  mov     [r10+rbx+2Ch], eax
0x140030e9e  mov     cl, [r11+r9*4+17h]
0x140030ea3  call    ClasspGetCommandDurationLimitPolicy
0x140030ea8  inc     dil
0x140030eab  mov     [r10+rbx+30h], eax
0x140030eb0  cmp     dil, [r11+9]
0x140030eb4  jb      loc_140030DAD
0x140030eba  mov     rbx, [rsp+28h+arg_0]
0x140030ebf  add     rsp, 20h
0x140030ec3  pop     rdi
0x140030ec4  retn
```
