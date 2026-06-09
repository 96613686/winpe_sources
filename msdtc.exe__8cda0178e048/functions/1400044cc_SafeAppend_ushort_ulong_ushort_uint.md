# SafeAppend(ushort *,ulong,ushort *,uint *)

- ea: `0x1400044cc`
- end: `0x140004505`
- name: `?SafeAppend@@YAXPEAGK0PEAI@Z`
- size: `57`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031c0`
- `0x1400033b4`
- `0x1400034b0`
- `0x140003534`
- `0x140003624`

## callees

- `0x1400044cc`
- `0x14000450c`

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
0x1400044cc  mov     r11, rsp
0x1400044cf  mov     [r11+18h], r8
0x1400044d3  push    rbx
0x1400044d4  sub     rsp, 30h
0x1400044d8  cmp     dword ptr [r9], 0
0x1400044dc  mov     rbx, r9
0x1400044df  jz      short loc_1400044FF
0x1400044e1  lea     rax, [r11+18h]
0x1400044e5  mov     qword ptr [r11+18h], 0
0x1400044ed  mov     r8, rcx; unsigned __int16 *
0x1400044f0  mov     [r11-18h], rax
0x1400044f4  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1400044f9  mov     eax, dword ptr [rsp+38h+arg_10]
0x1400044fd  mov     [rbx], eax
0x1400044ff  add     rsp, 30h
0x140004503  pop     rbx
0x140004504  retn
```
