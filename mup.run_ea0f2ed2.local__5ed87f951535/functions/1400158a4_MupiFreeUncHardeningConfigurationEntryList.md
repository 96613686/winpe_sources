# MupiFreeUncHardeningConfigurationEntryList

- ea: `0x1400158a4`
- end: `0x1400158fb`
- name: `MupiFreeUncHardeningConfigurationEntryList`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140010f18`
- `0x140014b70`
- `0x140014ea0`

## callees

- `0x140015710`
- `0x1400158a4`
- `0x14001e9f0`

## pseudocode

```c
_QWORD *__fastcall MupiFreeUncHardeningConfigurationEntryList(__int64 a1)
{
  __int64 i; // rbx
  _QWORD *v2; // rdx
  __int64 v3; // r8
  _QWORD *v4; // rcx
  _QWORD *result; // rax

  for ( i = a1; ; a1 = i )
  {
    result = (_QWORD *)MupiGetFirstUncHardeningConfigurationEntry(a1);
    if ( !result )
      break;
    v2 = result + 1;
    v3 = result[1];
    if ( (_QWORD *)v3 != result + 1 )
    {
      if ( *(_QWORD **)(v3 + 8) != v2 || (v4 = (_QWORD *)result[2], (_QWORD *)*v4 != v2) )
        __fastfail(3u);
      *v4 = v3;
      *(_QWORD *)(v3 + 8) = v4;
      result[2] = v2;
      *v2 = v2;
    }
    MupiDereferenceUncHardeningConfigurationEntry(result);
  }
  return result;
}

```

## disassembly

```asm
0x1400158a4  push    rbx
0x1400158a6  sub     rsp, 20h
0x1400158aa  mov     rbx, rcx
0x1400158ad  jmp     short loc_1400158E3
0x1400158af  lea     rdx, [rax+8]
0x1400158b3  mov     r8, [rdx]
0x1400158b6  cmp     r8, rdx
0x1400158b9  jz      short loc_1400158D8
0x1400158bb  cmp     [r8+8], rdx
0x1400158bf  jnz     short loc_1400158F4
0x1400158c1  mov     rcx, [rdx+8]
0x1400158c5  cmp     [rcx], rdx
0x1400158c8  jnz     short loc_1400158F4
0x1400158ca  mov     [rcx], r8
0x1400158cd  mov     [r8+8], rcx
0x1400158d1  mov     [rax+10h], rdx
0x1400158d5  mov     [rdx], rdx
0x1400158d8  mov     rcx, rax; P
0x1400158db  call    MupiDereferenceUncHardeningConfigurationEntry
0x1400158e0  mov     rcx, rbx
0x1400158e3  call    MupiGetFirstUncHardeningConfigurationEntry
0x1400158e8  test    rax, rax
0x1400158eb  jnz     short loc_1400158AF
0x1400158ed  add     rsp, 20h
0x1400158f1  pop     rbx
0x1400158f2  retn
0x1400158f4  mov     ecx, 3
0x1400158f9  int     29h; Win8: RtlFailFast(ecx)
```
