# ColumnLv::FindOrCreateLvObject(tagColParams *,Err &)

- ea: `0x10018200`
- end: `0x1001830a`
- name: `?FindOrCreateLvObject@ColumnLv@@QAEPAVLongValue@@PAUtagColParams@@AAVErr@@@Z`
- size: `266`
- prototype: `struct LongValue *__thiscall(ColumnLv *__hidden this, struct tagColParams *, struct Err *)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x10018310`
- `0x10018370`
- `0x100185d0`
- `0x1001b4e0`
- `0x10030730`
- `0x10030950`
- `0x10030b00`

## callees

- `0x10012dd0`
- `0x10018200`
- `0x10025ee0`
- `0x1003e6d0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
struct LongValue *__thiscall ColumnLv::FindOrCreateLvObject(ColumnLv *this, struct tagColParams *a2, struct Err *a3)
{
  int v3; // edx
  int v4; // ebx
  unsigned int v5; // esi
  int v6; // edi
  int v7; // ebx
  int v8; // ecx
  int v9; // ecx
  LongValue *v10; // edi
  Collection *v11; // esi
  unsigned int v12; // ecx
  LongValue *Block; // [esp+10h] [ebp-14h]

  v3 = 0;
  v4 = *((_DWORD *)a2 + 3);
  v5 = *(_DWORD *)(v4 + 356);
  if ( v5 )
  {
    v6 = *((_DWORD *)this + 3);
    v7 = *(_DWORD *)(v4 + 348);
    while ( 1 )
    {
      v8 = *(_DWORD *)(v7 + 4 * v3);
      if ( *(_DWORD *)(*(_DWORD *)(v8 + 12) + 12) == v6 )
        break;
      if ( ++v3 >= v5 )
        goto LABEL_5;
    }
    if ( v8 )
      return *(struct LongValue **)(v7 + 4 * v3);
  }
LABEL_5:
  Block = (LongValue *)operator new(0x34u);
  v10 = LongValue::LongValue(Block, *((struct Cursor **)a2 + 3), this, a3);
  if ( !v10 )
    Err::SetError(a3, -1011, v9);
  if ( (*(_BYTE *)a3 & 8) == 0 )
  {
    v11 = (Collection *)(*((_DWORD *)a2 + 3) + 348);
    v12 = *(_DWORD *)(*((_DWORD *)a2 + 3) + 356);
    if ( v12 < *(_DWORD *)(*((_DWORD *)a2 + 3) + 352) || (Collection::Grow(v11, v12 + 1, a3), (*(_BYTE *)a3 & 8) == 0) )
      *(_DWORD *)(*(_DWORD *)v11 + 4 * (*((_DWORD *)v11 + 2))++) = v10;
  }
  return v10;
}

```

## disassembly

```asm
0x10018200  mov     edi, edi
0x10018202  push    ebp
0x10018203  mov     ebp, esp
0x10018205  push    0FFFFFFFFh
0x10018207  push    offset ?FindOrCreateLvObject@ColumnLv@@QAEPAVLongValue@@PAUtagColParams@@AAVErr@@@Z_SEH
0x1001820c  mov     eax, large fs:0
0x10018212  push    eax
0x10018213  sub     esp, 8
0x10018216  push    ebx
0x10018217  push    esi
0x10018218  push    edi
0x10018219  mov     eax, ___security_cookie
0x1001821e  xor     eax, ebp
0x10018220  push    eax
0x10018221  lea     eax, [ebp+var_C]
0x10018224  mov     large fs:0, eax
0x1001822a  mov     eax, ecx
0x1001822c  mov     [ebp+var_10], eax
0x1001822f  mov     ebx, [ebp+arg_0]
0x10018232  xor     edx, edx
0x10018234  mov     ebx, [ebx+0Ch]
0x10018237  mov     esi, [ebx+164h]
0x1001823d  test    esi, esi
0x1001823f  jz      short loc_10018264
0x10018241  mov     edi, [eax+0Ch]
0x10018244  mov     ebx, [ebx+15Ch]
0x1001824a  nop     word ptr [eax+eax+00h]
0x10018250  mov     ecx, [ebx+edx*4]
0x10018253  mov     eax, [ecx+0Ch]
0x10018256  cmp     [eax+0Ch], edi
0x10018259  jz      loc_100182EC
0x1001825f  inc     edx
0x10018260  cmp     edx, esi
0x10018262  jb      short loc_10018250
0x10018264  push    34h ; '4'; Size
0x10018266  call    ??2@YAPAXI@Z; operator new(uint)
0x1001826b  add     esp, 4
0x1001826e  mov     [ebp+Block], eax
0x10018271  mov     ebx, [ebp+arg_4]
0x10018274  mov     ecx, eax; this
0x10018276  mov     esi, [ebp+arg_0]
0x10018279  push    ebx; struct Err *
0x1001827a  push    [ebp+var_10]; struct ColumnLv *
0x1001827d  mov     [ebp+var_4], 0
0x10018284  push    dword ptr [esi+0Ch]; struct Cursor *
0x10018287  call    ??0LongValue@@QAE@PAVCursor@@PAVColumnLv@@AAVErr@@@Z; LongValue::LongValue(Cursor *,ColumnLv *,Err &)
0x1001828c  mov     edi, eax
0x1001828e  mov     [ebp+var_4], 0FFFFFFFFh
0x10018295  test    edi, edi
0x10018297  jnz     short loc_100182A6
0x10018299  push    ecx
0x1001829a  push    0FFFFFC0Dh
0x1001829f  mov     ecx, ebx
0x100182a1  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100182a6  test    byte ptr [ebx], 8
0x100182a9  jnz     short loc_100182D6
0x100182ab  mov     esi, [esi+0Ch]
0x100182ae  add     esi, 15Ch
0x100182b4  mov     ecx, [esi+8]
0x100182b7  cmp     ecx, [esi+4]
0x100182ba  jb      short loc_100182CB
0x100182bc  inc     ecx
0x100182bd  push    ebx; struct Err *
0x100182be  push    ecx; unsigned int
0x100182bf  mov     ecx, esi; this
0x100182c1  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x100182c6  test    byte ptr [ebx], 8
0x100182c9  jnz     short loc_100182D6
0x100182cb  mov     ecx, [esi+8]
0x100182ce  mov     eax, [esi]
0x100182d0  mov     [eax+ecx*4], edi
0x100182d3  inc     dword ptr [esi+8]
0x100182d6  mov     eax, edi
0x100182d8  mov     ecx, [ebp+var_C]
0x100182db  mov     large fs:0, ecx
0x100182e2  pop     ecx
0x100182e3  pop     edi
0x100182e4  pop     esi
0x100182e5  pop     ebx
0x100182e6  mov     esp, ebp
0x100182e8  pop     ebp
0x100182e9  retn    8
0x100182ec  test    ecx, ecx
0x100182ee  jz      loc_10018264
0x100182f4  mov     eax, ecx
0x100182f6  mov     ecx, [ebp+var_C]
0x100182f9  mov     large fs:0, ecx
0x10018300  pop     ecx
0x10018301  pop     edi
0x10018302  pop     esi
0x10018303  pop     ebx
0x10018304  mov     esp, ebp
0x10018306  pop     ebp
0x10018307  retn    8
0x1005fbf0  push    34h ; '4'; unsigned int
0x1005fbf2  mov     eax, [ebp+Block]
0x1005fbf5  push    eax; Block
0x1005fbf6  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005fbfb  add     esp, 8
0x1005fbfe  retn
0x1005fc04  nop
0x1005fc05  nop
0x1005fc06  mov     edx, [esp-4+arg_4]
0x1005fc0a  lea     eax, [edx+0Ch]
0x1005fc0d  mov     ecx, [edx-18h]
0x1005fc10  xor     ecx, eax; StackCookie
0x1005fc12  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fc17  mov     eax, offset stru_10062D84
0x1005fc1c  jmp     ___CxxFrameHandler3
```
