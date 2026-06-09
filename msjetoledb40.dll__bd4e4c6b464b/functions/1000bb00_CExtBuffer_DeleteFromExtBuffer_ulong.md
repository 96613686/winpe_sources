# CExtBuffer::DeleteFromExtBuffer(ulong)

- ea: `0x1000bb00`
- end: `0x1000bb6b`
- name: `?DeleteFromExtBuffer@CExtBuffer@@QAGXK@Z`
- size: `107`
- prototype: `void(CExtBuffer *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1000cff0`
- `0x10015dc0`
- `0x10016040`
- `0x10029a90`
- `0x10030ed0`
- `0x100338a0`
- `0x100340d0`

## callees

- `0x1000bb00`
- `0x1000e9f0`

## pseudocode

```c
void __fastcall CExtBuffer::DeleteFromExtBuffer(_DWORD *a1, unsigned int a2)
{
  int v4; // edx
  unsigned int v5; // edi

  v4 = a1[6];
  v5 = 8 * a1[5];
  if ( a2 <= v5 + v4 - 1
    && (*(_BYTE *)(((a2 - v4) >> 3) + a1[4]) & *((_BYTE *)&Bitmap::ThisBit + ((a2 - v4) & 7))) == 0
    && (a2 - v4 < v5 || DynaBitmap::Grow((DynaBitmap *)(a1 + 4), a2) >= 0) )
  {
    *(_BYTE *)(a1[4] + ((a2 - a1[6]) >> 3)) |= *((_BYTE *)&Bitmap::ThisBit + ((a2 - a1[6]) & 7));
  }
}

```

## disassembly

```asm
0x1000bb00  mov     edi, edi
0x1000bb02  push    ebp
0x1000bb03  mov     ebp, esp
0x1000bb05  push    ecx
0x1000bb06  push    ebx
0x1000bb07  mov     ebx, ecx
0x1000bb09  push    esi
0x1000bb0a  mov     esi, edx
0x1000bb0c  push    edi
0x1000bb0d  mov     edx, [ebx+18h]
0x1000bb10  mov     edi, [ebx+14h]
0x1000bb13  shl     edi, 3
0x1000bb16  lea     eax, [edx-1]
0x1000bb19  add     eax, edi
0x1000bb1b  cmp     esi, eax
0x1000bb1d  ja      short loc_1000BB64
0x1000bb1f  mov     eax, [ebx+10h]
0x1000bb22  mov     ecx, esi
0x1000bb24  sub     ecx, edx
0x1000bb26  mov     edx, ecx
0x1000bb28  mov     [ebp+var_4], ecx
0x1000bb2b  shr     edx, 3
0x1000bb2e  and     ecx, 7
0x1000bb31  mov     al, [edx+eax]
0x1000bb34  test    ds:?ThisBit@Bitmap@@1QBEB[ecx], al; uchar const * const Bitmap::ThisBit
0x1000bb3a  jnz     short loc_1000BB64
0x1000bb3c  cmp     [ebp+var_4], edi
0x1000bb3f  jb      short loc_1000BB4E
0x1000bb41  push    esi; unsigned int
0x1000bb42  lea     ecx, [ebx+10h]; this
0x1000bb45  call    ?Grow@DynaBitmap@@AAEJK@Z; DynaBitmap::Grow(ulong)
0x1000bb4a  test    eax, eax
0x1000bb4c  js      short loc_1000BB64
0x1000bb4e  sub     esi, [ebx+18h]
0x1000bb51  mov     ecx, esi
0x1000bb53  and     esi, 7
0x1000bb56  shr     ecx, 3
0x1000bb59  add     ecx, [ebx+10h]
0x1000bb5c  mov     al, ds:?ThisBit@Bitmap@@1QBEB[esi]; uchar const * const Bitmap::ThisBit
0x1000bb62  or      [ecx], al
0x1000bb64  pop     edi
0x1000bb65  pop     esi
0x1000bb66  pop     ebx
0x1000bb67  mov     esp, ebp
0x1000bb69  pop     ebp
0x1000bb6a  retn
```
