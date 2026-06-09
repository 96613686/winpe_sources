# MupiFindOrCreateUncHardeningConfigurationEntry

- ea: `0x1400157a0`
- end: `0x140015831`
- name: `MupiFindOrCreateUncHardeningConfigurationEntry`
- size: `145`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, UNICODE_STRING *, __int64, const UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140015980`

## callees

- `0x140015660`
- `0x1400157a0`
- `0x140015838`

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
0x1400157a0  push    rbx
0x1400157a2  push    rbp
0x1400157a3  push    rsi
0x1400157a4  push    rdi
0x1400157a5  sub     rsp, 48h
0x1400157a9  mov     rdi, [rsp+68h+arg_20]
0x1400157b1  lea     rax, [rsp+68h+var_38]
0x1400157b6  mov     rsi, r8
0x1400157b9  mov     [rsp+68h+var_38], 0
0x1400157c2  mov     rbp, rdx
0x1400157c5  mov     [rsp+68h+var_48], rax
0x1400157ca  mov     rbx, rcx
0x1400157cd  mov     qword ptr [rdi], 0
0x1400157d4  call    MupiFindUncHardeningConfigurationEntry
0x1400157d9  test    eax, eax
0x1400157db  js      short loc_140015827
0x1400157dd  mov     rcx, [rsp+68h+var_38]
0x1400157e2  test    rcx, rcx
0x1400157e5  jnz     short loc_140015822
0x1400157e7  lea     r8, [rsp+68h+var_38]
0x1400157ec  mov     rdx, rsi
0x1400157ef  mov     rcx, rbp; StringIn
0x1400157f2  call    MupiCreateUncHardeningConfigurationEntry
0x1400157f7  test    eax, eax
0x1400157f9  js      short loc_140015827
0x1400157fb  mov     rdx, [rbx+8]
0x1400157ff  cmp     [rdx], rbx
0x140015802  jz      short loc_14001580B
0x140015804  mov     ecx, 3
0x140015809  int     29h; Win8: RtlFailFast(ecx)
0x14001580b  mov     rcx, [rsp+68h+var_38]
0x140015810  lea     rax, [rcx+8]
0x140015814  mov     [rax], rbx
0x140015817  mov     [rax+8], rdx
0x14001581b  mov     [rdx], rax
0x14001581e  mov     [rbx+8], rax
0x140015822  xor     eax, eax
0x140015824  mov     [rdi], rcx
0x140015827  add     rsp, 48h
0x14001582b  pop     rdi
0x14001582c  pop     rsi
0x14001582d  pop     rbp
0x14001582e  pop     rbx
0x14001582f  retn
```
