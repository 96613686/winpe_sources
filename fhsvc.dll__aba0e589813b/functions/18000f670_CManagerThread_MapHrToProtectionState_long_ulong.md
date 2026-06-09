# CManagerThread::MapHrToProtectionState(long,ulong *)

- ea: `0x18000f670`
- end: `0x18000f6b2`
- name: `?MapHrToProtectionState@CManagerThread@@AEAAHJPEAK@Z`
- size: `66`
- prototype: `__int64 __fastcall(CManagerThread *__hidden this, int, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f00`
- `0x1800065c0`
- `0x180007330`

## callees

- `0x18000f670`

## pseudocode

```c
__int64 __fastcall CManagerThread::MapHrToProtectionState(CManagerThread *this, int a2, unsigned int *a3)
{
  switch ( a2 )
  {
    case -2147219967:
    case -2147219966:
      *a3 = 1;
      break;
    case -2147219965:
      *a3 = 2;
      break;
    case -2147219964:
      *a3 = 3;
      break;
    default:
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000f670  cmp     edx, 80040601h
0x18000f676  jz      short loc_18000F6A5
0x18000f678  cmp     edx, 80040602h
0x18000f67e  jz      short loc_18000F6A5
0x18000f680  cmp     edx, 80040603h
0x18000f686  jz      short loc_18000F69C
0x18000f688  cmp     edx, 80040604h
0x18000f68e  jz      short loc_18000F693
0x18000f690  xor     eax, eax
0x18000f692  retn
0x18000f693  mov     dword ptr [r8], 3
0x18000f69a  jmp     short loc_18000F6AC
0x18000f69c  mov     dword ptr [r8], 2
0x18000f6a3  jmp     short loc_18000F6AC
0x18000f6a5  mov     dword ptr [r8], 1
0x18000f6ac  mov     eax, 1
0x18000f6b1  retn
```
