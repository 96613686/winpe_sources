# CJetILockBytes::WriteAt(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x10030950`
- end: `0x10030abf`
- name: `?WriteAt@CJetILockBytes@@UAGJT_ULARGE_INTEGER@@PBXKPAK@Z`
- size: `367`
- prototype: `int(CJetILockBytes *__hidden this, union _ULARGE_INTEGER, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x1000f750`
- `0x10018200`
- `0x10025ee0`
- `0x100261a0`
- `0x10030950`
- `0x1003eca0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __stdcall CJetILockBytes::WriteAt(
        CJetILockBytes *this,
        union _ULARGE_INTEGER a2,
        const void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  int v5; // esi
  int v6; // eax
  int v7; // edx
  _DWORD *v8; // ecx
  struct tagColParams *v9; // ebx
  ColumnLv *v10; // ecx
  LongValue *LvObject; // eax
  unsigned int v13; // [esp+0h] [ebp-34h]
  struct Err *v14; // [esp+4h] [ebp-30h]
  void *Block[4]; // [esp+10h] [ebp-24h] BYREF
  void *v16; // [esp+20h] [ebp-14h]
  int v17; // [esp+24h] [ebp-10h]
  int v18; // [esp+30h] [ebp-4h]

  Block[0] = (void *)1;
  v18 = 0;
  if ( a5 )
    *a5 = 0;
  if ( *((_DWORD *)this + 3) )
  {
    v5 = -2147418113;
    goto LABEL_24;
  }
  if ( !*((_DWORD *)this + 2) )
  {
    v5 = -2147467259;
    goto LABEL_24;
  }
  if ( a2.HighPart )
  {
    v5 = -2147467259;
    goto LABEL_24;
  }
  v6 = *((_DWORD *)this + 4);
  v7 = *(_DWORD *)(v6 + 12);
  v8 = *(_DWORD **)(v6 + 8);
  if ( v7 <= -1 || (v17 = v8[3], v7 >= *(_DWORD *)(v17 + 12)) )
  {
    *(_OWORD *)Block = _xmm;
    v16 = 0;
  }
  else if ( v8[11] == 3 )
  {
    Err::SetError(Block, -1609, v8);
  }
  else
  {
    v9 = (struct tagColParams *)(v8 + 24);
    v8[24] = v8[13];
    v8[25] = a3;
    v8[26] = a4;
    v8[28] = a2.LowPart;
    if ( (unsigned int)v7 >= 0xFF )
      v10 = 0;
    else
      v10 = *(ColumnLv **)(v17 + 4 * v7 + 376);
    *((_DWORD *)v9 + 5) = v10;
    LvObject = ColumnLv::FindOrCreateLvObject(v10, v9, (struct Err *)Block);
    if ( ((int)Block[0] & 8) != 0 )
      goto LABEL_20;
    LongValue::WriteAt(LvObject, v9, (struct Err *)Block);
  }
  if ( ((int)Block[0] & 8) != 0 )
  {
LABEL_20:
    ErrIsamErrToJetErr(v13, v14);
    v5 = -2147467259;
    goto LABEL_24;
  }
  if ( a5 )
    *a5 = a4;
  v5 = 0;
LABEL_24:
  if ( ((int)Block[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block[3] )
      operator delete[](Block[3]);
    if ( v16 )
      operator delete[](v16);
  }
  return v5;
}

```

## disassembly

```asm
0x10030950  mov     edi, edi
0x10030952  push    ebp
0x10030953  mov     ebp, esp
0x10030955  push    0FFFFFFFFh
0x10030957  push    offset ?WriteAt@CJetILockBytes@@UAGJT_ULARGE_INTEGER@@PBXKPAK@Z_SEH
0x1003095c  mov     eax, large fs:0
0x10030962  push    eax
0x10030963  sub     esp, 18h
0x10030966  push    ebx
0x10030967  push    esi
0x10030968  push    edi; struct Err *
0x10030969  mov     eax, ___security_cookie
0x1003096e  xor     eax, ebp
0x10030970  push    eax; unsigned int
0x10030971  lea     eax, [ebp+var_C]
0x10030974  mov     large fs:0, eax
0x1003097a  mov     [ebp+Block], 1
0x10030981  mov     esi, [ebp+arg_14]
0x10030984  mov     [ebp+var_4], 0
0x1003098b  test    esi, esi
0x1003098d  jz      short loc_10030995
0x1003098f  mov     dword ptr [esi], 0
0x10030995  mov     edi, [ebp+this]
0x10030998  cmp     dword ptr [edi+0Ch], 0
0x1003099c  jz      short loc_100309A8
0x1003099e  mov     esi, 8000FFFFh
0x100309a3  jmp     loc_10030A80
0x100309a8  cmp     dword ptr [edi+8], 0
0x100309ac  jnz     short loc_100309B8
0x100309ae  mov     esi, 80004005h
0x100309b3  jmp     loc_10030A80
0x100309b8  cmp     dword ptr [ebp+arg_4+4], 0
0x100309bc  jz      short loc_100309C8
0x100309be  mov     esi, 80004005h
0x100309c3  jmp     loc_10030A80
0x100309c8  mov     eax, [edi+10h]
0x100309cb  mov     edx, [eax+0Ch]
0x100309ce  mov     ecx, [eax+8]
0x100309d1  cmp     edx, 0FFFFFFFFh
0x100309d4  jle     short loc_10030A48
0x100309d6  mov     eax, [ecx+0Ch]
0x100309d9  mov     [ebp+var_10], eax
0x100309dc  cmp     edx, [eax+0Ch]
0x100309df  jge     short loc_10030A48
0x100309e1  cmp     dword ptr [ecx+2Ch], 3
0x100309e5  jz      short loc_10030A38
0x100309e7  mov     eax, [ecx+34h]
0x100309ea  lea     ebx, [ecx+60h]
0x100309ed  mov     [ebx], eax
0x100309ef  mov     eax, [ebp+arg_C]
0x100309f2  mov     [ecx+64h], eax
0x100309f5  mov     eax, [ebp+arg_10]
0x100309f8  mov     [ecx+68h], eax
0x100309fb  mov     eax, dword ptr [ebp+arg_4]
0x100309fe  mov     [ecx+70h], eax
0x10030a01  cmp     edx, 0FFh
0x10030a07  jnb     short loc_10030A15
0x10030a09  mov     ecx, [ebp+var_10]
0x10030a0c  mov     ecx, [ecx+edx*4+178h]
0x10030a13  jmp     short loc_10030A17
0x10030a15  xor     ecx, ecx; this
0x10030a17  lea     eax, [ebp+Block]
0x10030a1a  mov     [ebx+14h], ecx
0x10030a1d  push    eax; struct Err *
0x10030a1e  push    ebx; struct tagColParams *
0x10030a1f  call    ?FindOrCreateLvObject@ColumnLv@@QAEPAVLongValue@@PAUtagColParams@@AAVErr@@@Z; ColumnLv::FindOrCreateLvObject(tagColParams *,Err &)
0x10030a24  test    byte ptr [ebp+Block], 8
0x10030a28  jnz     short loc_10030A60
0x10030a2a  lea     ecx, [ebp+Block]
0x10030a2d  push    ecx; struct Err *
0x10030a2e  push    ebx; struct tagColParams *
0x10030a2f  mov     ecx, eax; this
0x10030a31  call    ?WriteAt@LongValue@@QAEKPAUtagColParams@@AAVErr@@@Z; LongValue::WriteAt(tagColParams *,Err &)
0x10030a36  jmp     short loc_10030A5A
0x10030a38  push    ecx
0x10030a39  push    0FFFFF9B7h
0x10030a3e  lea     ecx, [ebp+Block]
0x10030a41  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10030a46  jmp     short loc_10030A5A
0x10030a48  movaps  xmm0, ds:__xmm@0000000000000000fffffb4a00000008
0x10030a4f  movups  xmmword ptr [ebp+Block], xmm0
0x10030a53  mov     [ebp+var_14], 0
0x10030a5a  test    byte ptr [ebp+Block], 8
0x10030a5e  jz      short loc_10030A75
0x10030a60  mov     ecx, [edi+10h]
0x10030a63  lea     edx, [ebp+Block]
0x10030a66  mov     ecx, [ecx+4]
0x10030a69  call    ?ErrIsamErrToJetErr@@YGJKAAVErr@@@Z; ErrIsamErrToJetErr(ulong,Err &)
0x10030a6e  mov     esi, 80004005h
0x10030a73  jmp     short loc_10030A80
0x10030a75  test    esi, esi
0x10030a77  jz      short loc_10030A7E
0x10030a79  mov     eax, [ebp+arg_10]
0x10030a7c  mov     [esi], eax
0x10030a7e  xor     esi, esi
0x10030a80  test    [ebp+Block], 0FFFFFFFEh
0x10030a87  jz      short loc_10030AA9
0x10030a89  mov     eax, [ebp+Block+0Ch]
0x10030a8c  test    eax, eax
0x10030a8e  jz      short loc_10030A99
0x10030a90  push    eax; Block
0x10030a91  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10030a96  add     esp, 4
0x10030a99  mov     eax, [ebp+var_14]
0x10030a9c  test    eax, eax
0x10030a9e  jz      short loc_10030AA9
0x10030aa0  push    eax; Block
0x10030aa1  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10030aa6  add     esp, 4
0x10030aa9  mov     eax, esi
0x10030aab  mov     ecx, [ebp+var_C]
0x10030aae  mov     large fs:0, ecx
0x10030ab5  pop     ecx
0x10030ab6  pop     edi
0x10030ab7  pop     esi
0x10030ab8  pop     ebx
0x10030ab9  mov     esp, ebp
0x10030abb  pop     ebp
0x10030abc  retn    18h
0x1005feb0  lea     ecx, [ebp+var_24]; this
0x1005feb3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1005febd  nop
0x1005febe  nop
0x1005febf  mov     edx, [esp-4+arg_4]
0x1005fec3  lea     eax, [edx+0Ch]
0x1005fec6  mov     ecx, [edx-28h]
0x1005fec9  xor     ecx, eax; StackCookie
0x1005fecb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fed0  mov     eax, offset stru_10062F54
0x1005fed5  jmp     ___CxxFrameHandler3
```
