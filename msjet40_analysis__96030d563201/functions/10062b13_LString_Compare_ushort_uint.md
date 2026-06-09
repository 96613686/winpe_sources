# LString::Compare(ushort *,uint)

- ea: `0x10062b13`
- end: `0x10062ba6`
- name: `?Compare@LString@@QAE?AW4LCmp@@PAGI@Z`
- size: `147`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1001b1c0`
- `0x100479d0`
- `0x1004f14f`
- `0x1004fadd`
- `0x10059f97`
- `0x1005acd5`
- `0x1005b1a6`
- `0x1005c0a9`
- `0x1005c16b`
- `0x1007760d`

## callees

- `0x10062b13`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x10062b91`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10062b91`

## pseudocode

```c
int __thiscall LString::Compare(_DWORD *this, int a2, unsigned int a3)
{
  int v4; // edi
  int v5; // eax
  unsigned int v6; // esi
  int v7; // ecx
  int v8; // eax
  int v9; // eax

  v4 = this[2];
  v5 = this[3];
  if ( v5 == -1 )
  {
    v5 = 196609;
    this[3] = 196609;
  }
  v6 = v5 + (v4 & 0x80000000);
  v7 = this[1] >> 1;
  v8 = a3 >> 1;
  if ( (v4 & 0xA0000000) == 0 )
  {
    if ( v7 )
    {
      do
      {
        if ( *(_WORD *)(*this + 2 * v7 - 2) != 32 )
          break;
        --v7;
      }
      while ( v7 > 0 );
    }
    if ( v8 )
    {
      do
      {
        if ( *(_WORD *)(a2 + 2 * v8 - 2) != 32 )
          break;
        --v8;
      }
      while ( v8 > 0 );
    }
  }
  v9 = DBCompareStringW(v4 & 0xFFFEFF, v6, *this, v7, a2, v8);
  return v9 != 0 ? v9 - 2 : 0;
}

```

## disassembly

```asm
0x10062b13  mov     edi, edi
0x10062b15  push    ebp
0x10062b16  mov     ebp, esp
0x10062b18  push    ecx
0x10062b19  mov     edx, ecx
0x10062b1b  push    esi
0x10062b1c  push    edi
0x10062b1d  mov     edi, [edx+8]
0x10062b20  mov     esi, edi
0x10062b22  mov     eax, [edx+0Ch]
0x10062b25  and     esi, 80000000h
0x10062b2b  cmp     eax, 0FFFFFFFFh
0x10062b2e  jnz     short loc_10062B38
0x10062b30  mov     eax, 30001h
0x10062b35  mov     [edx+0Ch], eax
0x10062b38  mov     ecx, [edx+4]
0x10062b3b  add     esi, eax
0x10062b3d  mov     eax, [ebp+arg_4]
0x10062b40  shr     ecx, 1
0x10062b42  shr     eax, 1
0x10062b44  mov     [ebp+var_4], esi
0x10062b47  test    edi, 0A0000000h
0x10062b4d  jnz     short loc_10062B82
0x10062b4f  push    ebx
0x10062b50  test    ecx, ecx
0x10062b52  jz      short loc_10062B68
0x10062b54  mov     ebx, [edx]
0x10062b56  push    20h ; ' '
0x10062b58  pop     esi
0x10062b59  cmp     [ebx+ecx*2-2], si
0x10062b5e  jnz     short loc_10062B65
0x10062b60  dec     ecx
0x10062b61  test    ecx, ecx
0x10062b63  jg      short loc_10062B59
0x10062b65  mov     esi, [ebp+var_4]
0x10062b68  test    eax, eax
0x10062b6a  jz      short loc_10062B81
0x10062b6c  mov     ebx, [ebp+arg_0]
0x10062b6f  push    20h ; ' '
0x10062b71  pop     esi
0x10062b72  cmp     [ebx+eax*2-2], si
0x10062b77  jnz     short loc_10062B7E
0x10062b79  dec     eax
0x10062b7a  test    eax, eax
0x10062b7c  jg      short loc_10062B72
0x10062b7e  mov     esi, [ebp+var_4]
0x10062b81  pop     ebx
0x10062b82  push    eax
0x10062b83  push    [ebp+arg_0]
0x10062b86  and     edi, 0FFFEFFh
0x10062b8c  push    ecx
0x10062b8d  push    dword ptr [edx]
0x10062b8f  push    esi
0x10062b90  push    edi
0x10062b91  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x10062b97  pop     edi
0x10062b98  pop     esi
0x10062b99  lea     ecx, [eax-2]
0x10062b9c  neg     eax
0x10062b9e  sbb     eax, eax
0x10062ba0  and     eax, ecx
0x10062ba2  leave
0x10062ba3  retn    8
```
