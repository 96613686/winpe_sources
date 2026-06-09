# MupiFindOrCreateUncHardeningConfigurationEntry

- ea: `0x140015750`
- end: `0x1400157e1`
- name: `MupiFindOrCreateUncHardeningConfigurationEntry`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140015930`

## callees

- `0x140015610`
- `0x140015750`
- `0x1400157e8`

## pseudocode

```c
__int64 __fastcall MupiFindOrCreateUncHardeningConfigurationEntry(
        __int64 a1,
        const UNICODE_STRING *a2,
        UNICODE_STRING *a3,
        __int64 a4,
        const UNICODE_STRING **a5)
{
  __int64 result; // rax
  const UNICODE_STRING *v9; // rcx
  PWSTR **v10; // rdx
  PWSTR *p_Buffer; // rax
  const UNICODE_STRING *v12[7]; // [rsp+30h] [rbp-38h] BYREF

  v12[0] = 0;
  *a5 = 0;
  result = MupiFindUncHardeningConfigurationEntry(a1, a2, a3, a4, v12);
  if ( (int)result >= 0 )
  {
    v9 = v12[0];
    if ( !v12[0] )
    {
      result = MupiCreateUncHardeningConfigurationEntry(a2, (__int16 *)a3, v12);
      if ( (int)result < 0 )
        return result;
      v10 = *(PWSTR ***)(a1 + 8);
      if ( *v10 != (PWSTR *)a1 )
        __fastfail(3u);
      v9 = v12[0];
      p_Buffer = &v12[0]->Buffer;
      v12[0]->Buffer = (PWSTR)a1;
      p_Buffer[1] = (PWSTR)v10;
      *v10 = p_Buffer;
      *(_QWORD *)(a1 + 8) = p_Buffer;
    }
    result = 0;
    *a5 = v9;
  }
  return result;
}

```

## disassembly

```asm
0x140015750  push    rbx
0x140015752  push    rbp
0x140015753  push    rsi
0x140015754  push    rdi
0x140015755  sub     rsp, 48h
0x140015759  mov     rdi, [rsp+68h+arg_20]
0x140015761  lea     rax, [rsp+68h+var_38]
0x140015766  mov     rsi, r8
0x140015769  mov     [rsp+68h+var_38], 0
0x140015772  mov     rbp, rdx
0x140015775  mov     [rsp+68h+var_48], rax
0x14001577a  mov     rbx, rcx
0x14001577d  mov     qword ptr [rdi], 0
0x140015784  call    MupiFindUncHardeningConfigurationEntry
0x140015789  test    eax, eax
0x14001578b  js      short loc_1400157D7
0x14001578d  mov     rcx, [rsp+68h+var_38]
0x140015792  test    rcx, rcx
0x140015795  jnz     short loc_1400157D2
0x140015797  lea     r8, [rsp+68h+var_38]
0x14001579c  mov     rdx, rsi
0x14001579f  mov     rcx, rbp; StringIn
0x1400157a2  call    MupiCreateUncHardeningConfigurationEntry
0x1400157a7  test    eax, eax
0x1400157a9  js      short loc_1400157D7
0x1400157ab  mov     rdx, [rbx+8]
0x1400157af  cmp     [rdx], rbx
0x1400157b2  jz      short loc_1400157BB
0x1400157b4  mov     ecx, 3
0x1400157b9  int     29h; Win8: RtlFailFast(ecx)
0x1400157bb  mov     rcx, [rsp+68h+var_38]
0x1400157c0  lea     rax, [rcx+8]
0x1400157c4  mov     [rax], rbx
0x1400157c7  mov     [rax+8], rdx
0x1400157cb  mov     [rdx], rax
0x1400157ce  mov     [rbx+8], rax
0x1400157d2  xor     eax, eax
0x1400157d4  mov     [rdi], rcx
0x1400157d7  add     rsp, 48h
0x1400157db  pop     rdi
0x1400157dc  pop     rsi
0x1400157dd  pop     rbp
0x1400157de  pop     rbx
0x1400157df  retn
```
