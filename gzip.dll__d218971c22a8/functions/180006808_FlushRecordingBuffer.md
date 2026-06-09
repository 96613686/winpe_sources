# FlushRecordingBuffer

- ea: `0x180006808`
- end: `0x180006895`
- name: `FlushRecordingBuffer`
- size: `141`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180006808`

## pseudocode

```c
__int64 __fastcall FlushRecordingBuffer(__int64 a1)
{
  __int64 v1; // rax
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 80);
  if ( v1 )
  {
    **(_BYTE **)(v1 + 181016) = *(_BYTE *)(v1 + 181004);
    *(_BYTE *)++*(_QWORD *)(*(_QWORD *)(a1 + 80) + 181016LL) = BYTE1(*(_DWORD *)(*(_QWORD *)(a1 + 80) + 181004LL));
    result = *(_QWORD *)(a1 + 80);
    ++*(_QWORD *)(result + 181016);
  }
  else
  {
    result = *(_QWORD *)(a1 + 88);
    if ( result )
    {
      **(_BYTE **)(result + 541176) = *(_BYTE *)(result + 541164);
      *(_BYTE *)++*(_QWORD *)(*(_QWORD *)(a1 + 88) + 541176LL) = BYTE1(*(_DWORD *)(*(_QWORD *)(a1 + 88) + 541164LL));
      result = *(_QWORD *)(a1 + 88);
      ++*(_QWORD *)(result + 541176);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006808  mov     rax, [rcx+50h]
0x18000680c  mov     r8, rcx
0x18000680f  test    rax, rax
0x180006812  jz      short loc_180006850
0x180006814  mov     rdx, [rax+2C318h]
0x18000681b  mov     al, [rax+2C30Ch]
0x180006821  mov     [rdx], al
0x180006823  mov     rax, [rcx+50h]
0x180006827  inc     qword ptr [rax+2C318h]
0x18000682e  mov     rax, [rcx+50h]
0x180006832  mov     ecx, [rax+2C30Ch]
0x180006838  mov     rax, [rax+2C318h]
0x18000683f  shr     ecx, 8
0x180006842  mov     [rax], cl
0x180006844  mov     rax, [r8+50h]
0x180006848  inc     qword ptr [rax+2C318h]
0x18000684f  retn
0x180006850  mov     rax, [rcx+58h]
0x180006854  test    rax, rax
0x180006857  jz      short locret_180006894
0x180006859  mov     rcx, [rax+841F8h]
0x180006860  mov     al, [rax+841ECh]
0x180006866  mov     [rcx], al
0x180006868  mov     rax, [r8+58h]
0x18000686c  inc     qword ptr [rax+841F8h]
0x180006873  mov     rax, [r8+58h]
0x180006877  mov     ecx, [rax+841ECh]
0x18000687d  mov     rax, [rax+841F8h]
0x180006884  shr     ecx, 8
0x180006887  mov     [rax], cl
0x180006889  mov     rax, [r8+58h]
0x18000688d  inc     qword ptr [rax+841F8h]
0x180006894  retn
```
