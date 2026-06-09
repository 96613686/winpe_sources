# CVDecompressBegin(x,x,x,x,x)

- ea: `0x100053b2`
- end: `0x1000548b`
- name: `_CVDecompressBegin@20`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100101f2`

## callees

- `0x100053b2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1000547c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1000547c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100053cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10005449`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100053cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10005449`

## pseudocode

```c
int (__stdcall **__fastcall CVDecompressBegin(
        __int16 a1,
        __int16 a2,
        int a3,
        __int16 a4,
        int (__stdcall *a5)(int, int, int, int)))(int, int, int, int)
{
  __int16 v5; // si
  __int16 v6; // di
  int (__stdcall **v7)(int, int, int, int); // ebx
  int (__stdcall **v8)(int, int, int, int); // esi
  SIZE_T v9; // eax
  char *v10; // eax
  int (__stdcall **result)(int, int, int, int); // eax

  v5 = a2;
  v6 = a1;
  v7 = (int (__stdcall **)(int, int, int, int))LocalAlloc(0x40u, 0x40u);
  if ( !v7 )
    return 0;
  switch ( a3 )
  {
    case 0:
      v8 = Dispatch;
      if ( a4 == 2 )
        v8 = off_1000108C;
      goto LABEL_13;
    case 1:
      v8 = off_1000101C;
      goto LABEL_13;
    case 2:
      v8 = off_10001038;
      goto LABEL_13;
    case 3:
      v8 = off_10001054;
      goto LABEL_13;
    case 4:
      v8 = off_10001070;
LABEL_13:
      qmemcpy(v7, v8, 0x1Cu);
      v6 = a1;
      v5 = a2;
      break;
  }
  v9 = 24576;
  if ( !a3 )
    v9 = 25600;
  v10 = (char *)LocalAlloc(0x40u, v9);
  v7[7] = (int (__stdcall *)(int, int, int, int))v10;
  if ( v10 )
  {
    v7[8] = (int (__stdcall *)(int, int, int, int))v10;
    v7[13] = (int (__stdcall *)(int, int, int, int))(v10 + 24576);
    v7[9] = a5;
    result = v7;
    *((_WORD *)v7 + 20) = v6;
    *((_WORD *)v7 + 21) = v5;
    *((_WORD *)v7 + 23) = a4;
    return result;
  }
  LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x100053b2  mov     edi, edi
0x100053b4  push    ebp
0x100053b5  mov     ebp, esp
0x100053b7  push    ecx
0x100053b8  push    ebx
0x100053b9  push    esi
0x100053ba  push    edi
0x100053bb  push    40h ; '@'; uBytes
0x100053bd  mov     si, dx
0x100053c0  mov     di, cx
0x100053c3  push    40h ; '@'; uFlags
0x100053c5  mov     [ebp+var_2], si
0x100053c9  mov     [ebp+var_4], di
0x100053cd  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x100053d3  mov     ebx, eax
0x100053d5  test    ebx, ebx
0x100053d7  jz      loc_10005482
0x100053dd  mov     eax, [ebp+arg_0]
0x100053e0  sub     eax, 0
0x100053e3  jz      short loc_10005415
0x100053e5  sub     eax, 1
0x100053e8  jz      short loc_1000540E
0x100053ea  sub     eax, 1
0x100053ed  jz      short loc_10005407
0x100053ef  sub     eax, 1
0x100053f2  jz      short loc_10005400
0x100053f4  sub     eax, 1
0x100053f7  jnz     short loc_10005435
0x100053f9  mov     esi, offset off_10001070
0x100053fe  jmp     short loc_10005426
0x10005400  mov     esi, offset off_10001054
0x10005405  jmp     short loc_10005426
0x10005407  mov     esi, offset off_10001038
0x1000540c  jmp     short loc_10005426
0x1000540e  mov     esi, offset off_1000101C
0x10005413  jmp     short loc_10005426
0x10005415  cmp     [ebp+arg_4], 2
0x1000541a  mov     esi, offset _Dispatch
0x1000541f  jnz     short loc_10005426
0x10005421  mov     esi, offset off_1000108C
0x10005426  push    7
0x10005428  pop     ecx
0x10005429  mov     edi, ebx
0x1000542b  rep movsd
0x1000542d  mov     di, [ebp+var_4]
0x10005431  mov     si, [ebp+var_2]
0x10005435  cmp     [ebp+arg_0], 0
0x10005439  mov     ecx, 6400h
0x1000543e  mov     eax, 6000h
0x10005443  cmovz   eax, ecx
0x10005446  push    eax; uBytes
0x10005447  push    40h ; '@'; uFlags
0x10005449  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x1000544f  mov     [ebx+1Ch], eax
0x10005452  test    eax, eax
0x10005454  jz      short loc_1000547B
0x10005456  mov     cx, [ebp+arg_4]
0x1000545a  mov     [ebx+20h], eax
0x1000545d  add     eax, 6000h
0x10005462  mov     [ebx+34h], eax
0x10005465  mov     eax, [ebp+arg_8]
0x10005468  mov     [ebx+24h], eax
0x1000546b  mov     eax, ebx
0x1000546d  mov     [ebx+28h], di
0x10005471  mov     [ebx+2Ah], si
0x10005475  mov     [ebx+2Eh], cx
0x10005479  jmp     short loc_10005484
0x1000547b  push    ebx; hMem
0x1000547c  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10005482  xor     eax, eax
0x10005484  pop     edi
0x10005485  pop     esi
0x10005486  pop     ebx
0x10005487  leave
0x10005488  retn    0Ch
```
