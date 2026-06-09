# FillBitCache

- ea: `0x1800363f0`
- end: `0x18003649f`
- name: `FillBitCache`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `39`
- callee_count: `1`
- tags: ``

## callers

- `0x180019d60`
- `0x1800364b0`
- `0x180036520`
- `0x1800367b0`
- `0x180036910`
- `0x180036c60`
- `0x1800371b0`
- `0x1800373b0`
- `0x180037410`
- `0x180037490`
- `0x180037930`
- `0x180038550`
- `0x18003ab30`
- `0x18003acd0`
- `0x18003b370`
- `0x18003b660`
- `0x18003b700`
- `0x18003ba30`
- `0x18003bcc0`
- `0x18003bf10`
- `0x18003c060`
- `0x18003d620`
- `0x18003ffc0`
- `0x180074560`
- `0x180075a20`
- `0x180078d40`
- `0x180078f40`
- `0x180079090`
- `0x18007d2d0`
- `0x18007d4e0`
- `0x18007e8c0`
- `0x18007edc0`
- `0x18007f0d0`
- `0x18007f140`
- `0x18007f350`
- `0x18007f9e0`
- `0x180080100`
- `0x180080800`
- `0x180081fd0`

## callees

- `0x1800363f0`

## pseudocode

```c
unsigned int *__fastcall FillBitCache(int *a1, unsigned int a2)
{
  unsigned int *v2; // r8
  unsigned int *result; // rax
  unsigned __int64 v4; // r9
  unsigned int v6; // r10d
  unsigned int v7; // r11d
  unsigned int v8; // r9d
  int v9; // edx
  int v10; // ecx

  v2 = (unsigned int *)*((_QWORD *)a1 + 2);
  result = (unsigned int *)a1;
  v4 = *((_QWORD *)a1 + 1);
  v6 = *a1;
  if ( (unsigned __int64)v2 > v4 - 4 )
  {
    v9 = a1[1];
    do
    {
      if ( (unsigned __int64)v2 >= v4 )
      {
        v2 = (unsigned int *)*((_QWORD *)result + 3);
        *((_QWORD *)result + 2) = v2;
        result[11] = 1;
      }
      v10 = *(unsigned __int8 *)v2;
      v6 += 8;
      v2 = (unsigned int *)((char *)v2 + 1);
      v9 = v10 | (v9 << 8);
      *((_QWORD *)result + 2) = v2;
      result[1] = v9;
      *result = v6;
    }
    while ( v6 < a2 );
  }
  else
  {
    v7 = (32 - v6) & 0xFFFFFFF8;
    v8 = _byteswap_ulong(*v2);
    if ( v6 )
      v8 = (a1[1] << v7) | (v8 >> (32 - v7));
    a1[1] = v8;
    *a1 = v7 + v6;
    *((_QWORD *)a1 + 2) = (char *)v2 + (v7 >> 3);
  }
  return result;
}

```

## disassembly

```asm
0x1800363f0  sub     rsp, 8
0x1800363f4  mov     r8, [rcx+10h]
0x1800363f8  mov     rax, rcx
0x1800363fb  mov     r9, [rcx+8]
0x1800363ff  mov     r11d, edx
0x180036402  mov     r10d, [rcx]
0x180036405  lea     rcx, [r9-4]
0x180036409  cmp     r8, rcx
0x18003640c  ja      short loc_180036463
0x18003640e  mov     r9d, [r8]
0x180036411  mov     ecx, 20h ; ' '
0x180036416  sub     ecx, r10d
0x180036419  mov     [rsp+8+var_8], rbx
0x18003641d  and     ecx, 0FFFFFFF8h
0x180036420  mov     ebx, ecx
0x180036422  mov     r11d, ecx
0x180036425  shr     ebx, 3
0x180036428  bswap   r9d
0x18003642b  test    r10d, r10d
0x18003642e  jz      short loc_180036446
0x180036430  mov     edx, [rax+4]
0x180036433  mov     ecx, 20h ; ' '
0x180036438  sub     cl, r11b
0x18003643b  shr     r9d, cl
0x18003643e  mov     ecx, r11d
0x180036441  shl     edx, cl
0x180036443  or      r9d, edx
0x180036446  mov     [rax+4], r9d
0x18003644a  lea     ecx, [r11+r10]
0x18003644e  mov     [rax], ecx
0x180036450  mov     ecx, ebx
0x180036452  mov     rbx, [rsp+8+var_8]
0x180036456  add     rcx, r8
0x180036459  mov     [rax+10h], rcx
0x18003645d  add     rsp, 8
0x180036461  retn
0x180036463  mov     edx, [rax+4]
0x180036466  cmp     r8, r9
0x180036469  jb      short loc_18003647A
0x18003646b  mov     r8, [rax+18h]
0x18003646f  mov     [rax+10h], r8
0x180036473  mov     dword ptr [rax+2Ch], 1
0x18003647a  movzx   ecx, byte ptr [r8]
0x18003647e  add     r10d, 8
0x180036482  shl     edx, 8
0x180036485  inc     r8
0x180036488  or      edx, ecx
0x18003648a  mov     [rax+10h], r8
0x18003648e  mov     [rax+4], edx
0x180036491  mov     [rax], r10d
0x180036494  cmp     r10d, r11d
0x180036497  jb      short loc_180036466
0x180036499  add     rsp, 8
0x18003649d  retn
```
