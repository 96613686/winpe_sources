# MupiFreeUncHardeningConfigurationEntryList

- ea: `0x1400158f4`
- end: `0x14001594b`
- name: `MupiFreeUncHardeningConfigurationEntryList`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140010f18`
- `0x140014bc0`
- `0x140014ef0`

## callees

- `0x140015760`
- `0x1400158f4`
- `0x14001ea40`

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
0x1400158f4  push    rbx
0x1400158f6  sub     rsp, 20h
0x1400158fa  mov     rbx, rcx
0x1400158fd  jmp     short loc_140015933
0x1400158ff  lea     rdx, [rax+8]
0x140015903  mov     r8, [rdx]
0x140015906  cmp     r8, rdx
0x140015909  jz      short loc_140015928
0x14001590b  cmp     [r8+8], rdx
0x14001590f  jnz     short loc_140015944
0x140015911  mov     rcx, [rdx+8]
0x140015915  cmp     [rcx], rdx
0x140015918  jnz     short loc_140015944
0x14001591a  mov     [rcx], r8
0x14001591d  mov     [r8+8], rcx
0x140015921  mov     [rax+10h], rdx
0x140015925  mov     [rdx], rdx
0x140015928  mov     rcx, rax; P
0x14001592b  call    MupiDereferenceUncHardeningConfigurationEntry
0x140015930  mov     rcx, rbx
0x140015933  call    MupiGetFirstUncHardeningConfigurationEntry
0x140015938  test    rax, rax
0x14001593b  jnz     short loc_1400158FF
0x14001593d  add     rsp, 20h
0x140015941  pop     rbx
0x140015942  retn
0x140015944  mov     ecx, 3
0x140015949  int     29h; Win8: RtlFailFast(ecx)
```
