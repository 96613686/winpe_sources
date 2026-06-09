# EtwpGuidToString(ushort *,ulong,_GUID const *)

- ea: `0x180013d90`
- end: `0x180013e22`
- name: `?EtwpGuidToString@@YAPEAGPEAGKPEBU_GUID@@@Z`
- size: `146`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, unsigned int, const struct _GUID *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bbe0`
- `0x18000bf60`
- `0x180013e28`

## callees

- `0x1800143dc`

## pseudocode

```c
unsigned __int16 *__fastcall EtwpGuidToString(unsigned __int16 *a1, __int64 a2, const struct _GUID *a3)
{
  int Data2; // [rsp+20h] [rbp-88h]
  int Data3; // [rsp+28h] [rbp-80h]
  int v7; // [rsp+30h] [rbp-78h]
  int v8; // [rsp+38h] [rbp-70h]
  int v9; // [rsp+40h] [rbp-68h]
  int v10; // [rsp+48h] [rbp-60h]
  int v11; // [rsp+50h] [rbp-58h]
  int v12; // [rsp+58h] [rbp-50h]
  int v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]

  v14 = a3->Data4[7];
  v13 = a3->Data4[6];
  v12 = a3->Data4[5];
  v11 = a3->Data4[4];
  v10 = a3->Data4[3];
  v9 = a3->Data4[2];
  v8 = a3->Data4[1];
  v7 = a3->Data4[0];
  Data3 = a3->Data3;
  Data2 = a3->Data2;
  StringCbPrintfW(
    a1,
    0x4Au,
    L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    a3->Data1,
    Data2,
    Data3,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12,
    v13,
    v14);
  return a1;
}

```

## disassembly

```asm
0x180013d90  push    rbx
0x180013d92  push    rbp
0x180013d93  push    rsi
0x180013d94  push    rdi
0x180013d95  push    r14
0x180013d97  push    r15
0x180013d99  sub     rsp, 78h
0x180013d9d  movzx   edx, byte ptr [r8+0Eh]
0x180013da2  mov     r15, rcx
0x180013da5  movzx   r9d, byte ptr [r8+0Dh]
0x180013daa  movzx   eax, byte ptr [r8+0Fh]
0x180013daf  movzx   r10d, byte ptr [r8+0Ch]
0x180013db4  movzx   r11d, byte ptr [r8+0Bh]
0x180013db9  movzx   ebx, byte ptr [r8+0Ah]
0x180013dbe  movzx   edi, byte ptr [r8+9]
0x180013dc3  movzx   esi, byte ptr [r8+8]
0x180013dc8  movzx   ebp, word ptr [r8+6]
0x180013dcd  movzx   r14d, word ptr [r8+4]
0x180013dd2  mov     [rsp+0A8h+var_40], eax
0x180013dd6  mov     [rsp+0A8h+var_48], edx
0x180013dda  mov     edx, 4Ah ; 'J'; unsigned __int64
0x180013ddf  mov     [rsp+0A8h+var_50], r9d
0x180013de4  mov     r9d, [r8]
0x180013de7  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180013dee  mov     [rsp+0A8h+var_58], r10d
0x180013df3  mov     [rsp+0A8h+var_60], r11d
0x180013df8  mov     [rsp+0A8h+var_68], ebx
0x180013dfc  mov     [rsp+0A8h+var_70], edi
0x180013e00  mov     [rsp+0A8h+var_78], esi
0x180013e04  mov     [rsp+0A8h+var_80], ebp
0x180013e08  mov     [rsp+0A8h+var_88], r14d
0x180013e0d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013e12  mov     rax, r15
0x180013e15  add     rsp, 78h
0x180013e19  pop     r15
0x180013e1b  pop     r14
0x180013e1d  pop     rdi
0x180013e1e  pop     rsi
0x180013e1f  pop     rbp
0x180013e20  pop     rbx
0x180013e21  retn
```
