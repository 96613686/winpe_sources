# CdCommonDirControl

- ea: `0x140010ee0`
- end: `0x140010f5f`
- name: `CdCommonDirControl`
- size: `127`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x140010ee0`
- `0x140011674`
- `0x140011744`

## pseudocode

```c
__int64 __fastcall CdCommonDirControl(void *a1, __int64 a2)
{
  __int64 v2; // r11
  __int64 v3; // r9
  unsigned int v4; // ebx

  v2 = *(_QWORD *)(a2 + 184);
  v3 = *(_QWORD *)(v2 + 48);
  if ( (*(_DWORD *)(v3 + 32) & 7) == 3 )
  {
    if ( *(_BYTE *)(v2 + 1) == 1 )
    {
      return (unsigned int)CdQueryDirectory(
                             (__int64)a1,
                             a2,
                             v2,
                             *(_QWORD *)(v3 + 24),
                             *(_QWORD *)(v3 + 32) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      if ( *(_BYTE *)(v2 + 1) != 2 )
      {
        v4 = -1073741808;
        goto LABEL_6;
      }
      return (unsigned int)CdNotifyChangeDirectory(
                             (__int64)a1,
                             (IRP *)a2,
                             *(_QWORD *)(a2 + 184),
                             (void *)(*(_QWORD *)(v3 + 32) & 0xFFFFFFFFFFFFFFF8uLL));
    }
  }
  v4 = -1073741811;
LABEL_6:
  CdCompleteRequest(a1, (IRP *)a2, v4);
  return v4;
}

```

## disassembly

```asm
0x140010ee0  push    rbx
0x140010ee2  sub     rsp, 30h
0x140010ee6  mov     r11, [rdx+0B8h]
0x140010eed  mov     r10, rcx
0x140010ef0  mov     r9, [r11+30h]
0x140010ef4  mov     ecx, [r9+20h]
0x140010ef8  and     ecx, 7
0x140010efb  cmp     ecx, 3
0x140010efe  jz      short loc_140010F0A
0x140010f00  mov     ebx, 0C000000Dh
0x140010f05  mov     rcx, r10
0x140010f08  jmp     short loc_140010F29
0x140010f0a  mov     r8, [r9+20h]
0x140010f0e  movzx   ecx, byte ptr [r11+1]
0x140010f13  and     r8, 0FFFFFFFFFFFFFFF8h
0x140010f17  sub     ecx, 1
0x140010f1a  jz      short loc_140010F40
0x140010f1c  cmp     ecx, 1
0x140010f1f  mov     rcx, r10
0x140010f22  jz      short loc_140010F33
0x140010f24  mov     ebx, 0C0000010h
0x140010f29  mov     r8d, ebx
0x140010f2c  call    CdCompleteRequest
0x140010f31  jmp     short loc_140010F56
0x140010f33  mov     r9, r8
0x140010f36  mov     r8, r11
0x140010f39  call    CdNotifyChangeDirectory
0x140010f3e  jmp     short loc_140010F54
0x140010f40  mov     r9, [r9+18h]
0x140010f44  mov     rcx, r10; int
0x140010f47  mov     [rsp+38h+var_18], r8; __int64
0x140010f4c  mov     r8, r11
0x140010f4f  call    CdQueryDirectory
0x140010f54  mov     ebx, eax
0x140010f56  mov     eax, ebx
0x140010f58  add     rsp, 30h
0x140010f5c  pop     rbx
0x140010f5d  retn
```
