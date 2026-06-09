# SafeAppend(ushort *,ulong,ushort *,uint *)

- ea: `0x18000fb34`
- end: `0x18000fb6d`
- name: `?SafeAppend@@YAXPEAGK0PEAI@Z`
- size: `57`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e828`
- `0x18000ea1c`
- `0x18000eb18`
- `0x18000eb9c`
- `0x18000ec8c`

## callees

- `0x18000fb34`
- `0x18000fb74`

## pseudocode

```c
void __fastcall SafeAppend(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3, unsigned __int16 **a4)
{
  unsigned int v5; // [rsp+28h] [rbp-10h]
  unsigned __int16 *v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  if ( *(_DWORD *)a4 )
  {
    v6 = 0;
    StringCchCatExW(a1, a2, a1, a4, (unsigned __int64 *)&v6, v5);
    *(_DWORD *)a4 = (_DWORD)v6;
  }
}

```

## disassembly

```asm
0x18000fb34  mov     r11, rsp
0x18000fb37  mov     [r11+18h], r8
0x18000fb3b  push    rbx
0x18000fb3c  sub     rsp, 30h
0x18000fb40  cmp     dword ptr [r9], 0
0x18000fb44  mov     rbx, r9
0x18000fb47  jz      short loc_18000FB67
0x18000fb49  lea     rax, [r11+18h]
0x18000fb4d  mov     qword ptr [r11+18h], 0
0x18000fb55  mov     r8, rcx; unsigned __int16 *
0x18000fb58  mov     [r11-18h], rax
0x18000fb5c  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000fb61  mov     eax, dword ptr [rsp+38h+arg_10]
0x18000fb65  mov     [rbx], eax
0x18000fb67  add     rsp, 30h
0x18000fb6b  pop     rbx
0x18000fb6c  retn
```
