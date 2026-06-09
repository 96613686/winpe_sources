# CopyBufferClear(x)

- ea: `0x10031f44`
- end: `0x10031fb1`
- name: `_CopyBufferClear@4`
- size: `109`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x10029730`
- `0x10029aad`
- `0x1002a530`
- `0x1002c79f`
- `0x1002c918`
- `0x1002cbc4`
- `0x1002cd40`
- `0x1002da00`
- `0x1002db68`

## callees

- `0x10025ab7`
- `0x10031ef2`
- `0x10031f44`

## pseudocode

```c
int __thiscall CopyBufferClear(_DWORD *this)
{
  char *v2; // esi
  char *v3; // ebx
  _DWORD *v4; // ecx
  int result; // eax
  int v6; // [esp+8h] [ebp-4h]

  v2 = (char *)this[10];
  if ( v2 )
  {
    do
    {
      v3 = *(char **)v2;
      if ( v2[8] < 0 )
      {
        v6 = AssociatedColumnMemo(this, (unsigned __int8)v2[4]);
        v4 = *(_DWORD **)(v6 + 12);
        if ( v4 )
        {
          MemFree(v4);
          *(_DWORD *)(v6 + 12) = 0;
        }
      }
      *(_DWORD *)v2 = dword_1003AE78;
      dword_1003AE78 = v2;
      v2 = v3;
    }
    while ( v3 );
  }
  this[12] = 0;
  result = 0;
  this[10] = 0;
  this[11] = 0;
  return result;
}

```

## disassembly

```asm
0x10031f44  mov     edi, edi
0x10031f46  push    ebp
0x10031f47  mov     ebp, esp
0x10031f49  push    ecx
0x10031f4a  push    esi
0x10031f4b  push    edi
0x10031f4c  mov     edi, ecx
0x10031f4e  mov     esi, [edi+28h]
0x10031f51  test    esi, esi
0x10031f53  jz      short loc_10031F96
0x10031f55  push    ebx
0x10031f56  test    byte ptr [esi+8], 80h
0x10031f5a  mov     ebx, [esi]
0x10031f5c  jz      short loc_10031F82
0x10031f5e  movzx   edx, byte ptr [esi+4]
0x10031f62  mov     ecx, edi
0x10031f64  call    _AssociatedColumnMemo@8; AssociatedColumnMemo(x,x)
0x10031f69  mov     [ebp+var_4], eax
0x10031f6c  mov     ecx, [eax+0Ch]
0x10031f6f  test    ecx, ecx
0x10031f71  jz      short loc_10031F82
0x10031f73  call    _MemFree@4; MemFree(x)
0x10031f78  mov     eax, [ebp+var_4]
0x10031f7b  mov     dword ptr [eax+0Ch], 0
0x10031f82  mov     eax, dword_1003AE78
0x10031f87  mov     [esi], eax
0x10031f89  mov     dword_1003AE78, esi
0x10031f8f  mov     esi, ebx
0x10031f91  test    ebx, ebx
0x10031f93  jnz     short loc_10031F56
0x10031f95  pop     ebx
0x10031f96  mov     dword ptr [edi+30h], 0
0x10031f9d  xor     eax, eax
0x10031f9f  mov     dword ptr [edi+28h], 0
0x10031fa6  mov     dword ptr [edi+2Ch], 0
0x10031fad  pop     edi
0x10031fae  pop     esi
0x10031faf  leave
0x10031fb0  retn
```
