# StringCbCopyA(char *,unsigned __int64,char const *)

- ea: `0x180003610`
- end: `0x180003678`
- name: `?StringCbCopyA@@YAJPEAD_KPEBD@Z`
- size: `104`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b50`

## callees

- `0x180003610`

## pseudocode

```c
__int64 __fastcall StringCbCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  char *v3; // r9
  __int64 v4; // rax
  char *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003610  mov     r9, rcx
0x180003613  test    rdx, rdx
0x180003616  jz      short loc_180003662
0x180003618  cmp     rdx, 7FFFFFFFh
0x18000361f  ja      short loc_180003671
0x180003621  mov     eax, 7FFFFFFEh
0x180003626  test    rax, rax
0x180003629  jz      short loc_180003645
0x18000362b  movzx   ecx, byte ptr [r8]
0x18000362f  test    cl, cl
0x180003631  jz      short loc_180003645
0x180003633  mov     [r9], cl
0x180003636  inc     r8
0x180003639  inc     r9
0x18000363c  dec     rax
0x18000363f  sub     rdx, 1
0x180003643  jnz     short loc_180003626
0x180003645  test    rdx, rdx
0x180003648  lea     rax, [r9-1]
0x18000364c  cmovnz  rax, r9
0x180003650  xor     ecx, ecx
0x180003652  test    rdx, rdx
0x180003655  mov     byte ptr [rax], 0
0x180003658  mov     eax, 8007007Ah
0x18000365d  cmovnz  eax, ecx
0x180003660  retn
0x180003662  mov     eax, 80070057h
0x180003667  test    rdx, rdx
0x18000366a  jz      short locret_180003660
0x18000366c  mov     byte ptr [rcx], 0
0x18000366f  retn
0x180003671  mov     eax, 80070057h
0x180003676  jmp     short loc_18000366C
```
