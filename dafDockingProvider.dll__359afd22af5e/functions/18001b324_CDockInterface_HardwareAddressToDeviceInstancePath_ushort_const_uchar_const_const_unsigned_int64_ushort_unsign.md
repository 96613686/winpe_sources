# CDockInterface::HardwareAddressToDeviceInstancePath(ushort const *,uchar const * const,unsigned __int64,ushort *,unsigned __int64 *)

- ea: `0x18001b324`
- end: `0x18001b422`
- name: `?HardwareAddressToDeviceInstancePath@CDockInterface@@AEAAJPEBGQEBE_KPEAGPEA_K@Z`
- size: `254`
- prototype: `__int64 __fastcall(CDockInterface *__hidden this, const unsigned __int16 *, const unsigned __int8 *const, unsigned __int64, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b22c`

## callees

- `0x18000c348`
- `0x18001b324`
- `0x18001bfb0`

## pseudocode

```c
__int64 __fastcall CDockInterface::HardwareAddressToDeviceInstancePath(
        CDockInterface *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *const a3,
        unsigned __int64 a4,
        unsigned __int16 *a5,
        unsigned __int64 *a6)
{
  int v6; // r9d
  int v8; // ebx
  int v9; // r10d
  int v10; // r11d
  int v11; // edi
  int v13; // [rsp+38h] [rbp-40h]
  int v14; // [rsp+40h] [rbp-38h]
  int v15; // [rsp+48h] [rbp-30h]
  int v16; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+60h] [rbp-18h]
  unsigned __int16 *v19; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp+20h] BYREF

  v20 = a4;
  v6 = a3[4];
  v8 = a3[1];
  v9 = a3[3];
  v10 = a3[2];
  v20 = 0;
  v18 = a3[5];
  v17 = v6;
  v16 = v9;
  v15 = v10;
  v14 = v8;
  v13 = *a3;
  v11 = StringCchPrintfExW(
          a5,
          0x104u,
          &v19,
          &v20,
          0,
          L"SWD\\Docking\\WirelessDocking#(%s){%0.2x%0.2x%0.2x%0.2x%0.2x%0.2x}",
          a2,
          v13,
          v14,
          v15,
          v16,
          v17,
          v18);
  if ( v11 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_b415491bb2933ebae3e7436051291308_Traceguids, this, v11);
  }
  *a6 = 260 - v20;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b324  mov     rax, rsp
0x18001b327  mov     [rax+8], rbx
0x18001b32b  mov     [rax+10h], rsi
0x18001b32f  mov     [rax+20h], r9
0x18001b333  push    rdi
0x18001b334  sub     rsp, 70h
0x18001b338  movzx   r9d, byte ptr [r8+4]
0x18001b33d  mov     rsi, rcx
0x18001b340  movzx   ebx, byte ptr [r8+1]
0x18001b345  movzx   r10d, byte ptr [r8+3]
0x18001b34a  movzx   r11d, byte ptr [r8+2]
0x18001b34f  mov     rcx, [rsp+78h+arg_20]; unsigned __int16 *
0x18001b357  mov     qword ptr [rax+20h], 0
0x18001b35f  movzx   eax, byte ptr [r8+5]
0x18001b364  movzx   r8d, byte ptr [r8]
0x18001b368  mov     [rsp+78h+var_18], eax
0x18001b36c  lea     rax, aSwdDockingWire; "SWD\\Docking\\WirelessDocking#(%s){%0.2"...
0x18001b373  mov     [rsp+78h+var_20], r9d
0x18001b378  lea     r9, [rsp+78h+arg_18]; unsigned __int64 *
0x18001b380  mov     [rsp+78h+var_28], r10d
0x18001b385  mov     [rsp+78h+var_30], r11d
0x18001b38a  mov     [rsp+78h+var_38], ebx
0x18001b38e  mov     ebx, 104h
0x18001b393  mov     [rsp+78h+var_40], r8d
0x18001b398  lea     r8, [rsp+78h+arg_10]; unsigned __int16 **
0x18001b3a0  mov     [rsp+78h+var_48], rdx
0x18001b3a5  mov     edx, ebx; unsigned __int64
0x18001b3a7  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x18001b3ac  mov     qword ptr [rsp+78h+var_58], 0; unsigned int
0x18001b3b5  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001b3ba  mov     edi, eax
0x18001b3bc  test    eax, eax
0x18001b3be  jns     short loc_18001B3FB
0x18001b3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3c7  lea     rax, WPP_GLOBAL_Control
0x18001b3ce  cmp     rcx, rax
0x18001b3d1  jz      short loc_18001B3FB
0x18001b3d3  cmp     byte ptr [rcx+19h], 1
0x18001b3d7  jb      short loc_18001B3FB
0x18001b3d9  test    byte ptr [rcx+1Ch], 1
0x18001b3dd  jz      short loc_18001B3FB
0x18001b3df  mov     rcx, [rcx+10h]
0x18001b3e3  lea     r8, WPP_b415491bb2933ebae3e7436051291308_Traceguids
0x18001b3ea  mov     edx, 25h ; '%'
0x18001b3ef  mov     [rsp+78h+var_58], edi
0x18001b3f3  mov     r9, rsi
0x18001b3f6  call    WPP_SF_qD
0x18001b3fb  mov     rax, [rsp+78h+arg_28]
0x18001b403  lea     r11, [rsp+78h+var_8]
0x18001b408  sub     rbx, [rsp+78h+arg_18]
0x18001b410  mov     rsi, [r11+18h]
0x18001b414  mov     [rax], rbx
0x18001b417  mov     eax, edi
0x18001b419  mov     rbx, [r11+10h]
0x18001b41d  mov     rsp, r11
0x18001b420  pop     rdi
0x18001b421  retn
```
