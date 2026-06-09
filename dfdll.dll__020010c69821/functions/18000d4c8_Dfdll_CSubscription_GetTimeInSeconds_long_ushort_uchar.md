# Dfdll::CSubscription::GetTimeInSeconds(long &,ushort,uchar)

- ea: `0x18000d4c8`
- end: `0x18000d4fe`
- name: `?GetTimeInSeconds@CSubscription@Dfdll@@IEAAJAEAJGE@Z`
- size: `54`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, int *, unsigned __int16, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009c44`

## callees

- `0x18000d4c8`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::GetTimeInSeconds(
        Dfdll::CSubscription *this,
        int *a2,
        unsigned __int16 a3,
        char a4)
{
  int v4; // ecx

  v4 = a3;
  *a2 = a3;
  if ( a4 != 1 )
  {
    if ( a4 != 2 )
    {
      if ( a4 != 3 )
        return 2147942487LL;
      v4 = 7 * a3;
    }
    v4 *= 24;
  }
  *a2 = 3600 * v4;
  return 0;
}

```

## disassembly

```asm
0x18000d4c8  movzx   ecx, r8w
0x18000d4cc  movzx   r8d, r9b
0x18000d4d0  mov     [rdx], ecx
0x18000d4d2  sub     r8d, 1
0x18000d4d6  jz      short loc_18000D4F3
0x18000d4d8  sub     r8d, 1
0x18000d4dc  jz      short loc_18000D4ED
0x18000d4de  cmp     r8d, 1
0x18000d4e2  jz      short loc_18000D4EA
0x18000d4e4  mov     eax, 80070057h
0x18000d4e9  retn
0x18000d4ea  imul    ecx, 7
0x18000d4ed  lea     ecx, [rcx+rcx*2]
0x18000d4f0  shl     ecx, 3
0x18000d4f3  imul    eax, ecx, 0E10h
0x18000d4f9  mov     [rdx], eax
0x18000d4fb  xor     eax, eax
0x18000d4fd  retn
```
