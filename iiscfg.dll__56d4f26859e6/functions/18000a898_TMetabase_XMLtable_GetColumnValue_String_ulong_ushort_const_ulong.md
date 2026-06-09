# TMetabase_XMLtable::GetColumnValue_String(ulong,ushort const *,ulong)

- ea: `0x18000a898`
- end: `0x18000a9ab`
- name: `?GetColumnValue_String@TMetabase_XMLtable@@AEAAJKPEBGK@Z`
- size: `275`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009acc`

## callees

- `0x18000a898`
- `0x18000bdf4`

## pseudocode

```c
__int64 __fastcall TMetabase_XMLtable::GetColumnValue_String(
        LPVOID *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v4; // edi
  const unsigned __int16 *v5; // rbx
  __int64 v7; // rbp
  _WORD *v8; // rdx
  int v9; // r8d
  __int16 v10; // ax
  __int64 result; // rax

  v4 = a4;
  v5 = a3;
  if ( a3 && a4 )
  {
    v7 = a2;
    TGrowableBuffer::Grow(&this[2 * a2 + 174], 2LL * (unsigned int)(a4 + 1));
    this[v7 + 101] = this[2 * v7 + 174];
    v8 = this[2 * v7 + 174];
    while ( 1 )
    {
      v9 = *v5;
      if ( (v9 & 0xD800) != 0xD800 )
        break;
      switch ( v9 )
      {
        case 55296:
          v10 = *++v5 + 9216;
          break;
        case 55350:
          v10 = *++v5 & 0xFBFF;
          break;
        case 55351:
          v10 = *++v5;
          break;
        case 55359:
          v10 = *++v5 | 0x2000;
          break;
        default:
          goto LABEL_14;
      }
      *v8 = v10;
      --v4;
LABEL_15:
      ++v5;
      ++v8;
      if ( !--v4 )
      {
        result = 0;
        *v8 = 0;
        *((_DWORD *)this + v7 + 320) = (_DWORD)v8 - LODWORD(this[v7 + 101]) + 2;
        return result;
      }
    }
LABEL_14:
    *v8 = v9;
    goto LABEL_15;
  }
  this[a2 + 101] = &TMetabase_XMLtable::m_kZero;
  *((_DWORD *)this + a2 + 320) = 2;
  return 0;
}

```

## disassembly

```asm
0x18000a898  push    rbx
0x18000a89a  push    rbp
0x18000a89b  push    rsi
0x18000a89c  push    rdi
0x18000a89d  sub     rsp, 28h
0x18000a8a1  mov     edi, r9d
0x18000a8a4  mov     rbx, r8
0x18000a8a7  mov     rsi, rcx
0x18000a8aa  test    r8, r8
0x18000a8ad  jz      loc_18000A984
0x18000a8b3  test    r9d, r9d
0x18000a8b6  jz      loc_18000A984
0x18000a8bc  mov     ebp, edx
0x18000a8be  lea     edx, [r9+1]
0x18000a8c2  add     rdx, rdx; unsigned __int64
0x18000a8c5  lea     rcx, [rbp+57h]
0x18000a8c9  shl     rcx, 4
0x18000a8cd  add     rcx, rsi; this
0x18000a8d0  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000a8d5  lea     rcx, [rbp+57h]
0x18000a8d9  mov     r10d, 0D800h
0x18000a8df  add     rcx, rcx
0x18000a8e2  or      r9d, 0FFFFFFFFh
0x18000a8e6  mov     rax, [rsi+rcx*8]
0x18000a8ea  mov     [rsi+rbp*8+328h], rax
0x18000a8f2  mov     rdx, [rsi+rcx*8]
0x18000a8f6  movzx   r8d, word ptr [rbx]
0x18000a8fa  movzx   eax, r8w
0x18000a8fe  and     ax, r10w
0x18000a902  cmp     ax, r10w
0x18000a906  jnz     short loc_18000A95B
0x18000a908  mov     ecx, r8d
0x18000a90b  sub     ecx, r10d
0x18000a90e  jz      short loc_18000A947
0x18000a910  sub     ecx, 36h ; '6'
0x18000a913  jz      short loc_18000A936
0x18000a915  sub     ecx, 1
0x18000a918  jz      short loc_18000A92D
0x18000a91a  cmp     ecx, 8
0x18000a91d  jnz     short loc_18000A95B
0x18000a91f  add     rbx, 2
0x18000a923  mov     eax, 2000h
0x18000a928  or      ax, [rbx]
0x18000a92b  jmp     short loc_18000A953
0x18000a92d  add     rbx, 2
0x18000a931  movzx   eax, word ptr [rbx]
0x18000a934  jmp     short loc_18000A953
0x18000a936  add     rbx, 2
0x18000a93a  mov     ecx, 0FBFFh
0x18000a93f  movzx   eax, word ptr [rbx]
0x18000a942  and     ax, cx
0x18000a945  jmp     short loc_18000A953
0x18000a947  add     rbx, 2
0x18000a94b  mov     eax, 2400h
0x18000a950  add     ax, [rbx]
0x18000a953  mov     [rdx], ax
0x18000a956  add     edi, r9d
0x18000a959  jmp     short loc_18000A95F
0x18000a95b  mov     [rdx], r8w
0x18000a95f  add     rbx, 2
0x18000a963  add     rdx, 2
0x18000a967  add     edi, r9d
0x18000a96a  jnz     short loc_18000A8F6
0x18000a96c  xor     eax, eax
0x18000a96e  mov     [rdx], ax
0x18000a971  sub     edx, [rsi+rbp*8+328h]
0x18000a978  add     edx, 2
0x18000a97b  mov     [rsi+rbp*4+500h], edx
0x18000a982  jmp     short loc_18000A9A2
0x18000a984  mov     eax, edx
0x18000a986  lea     rcx, ?m_kZero@TMetabase_XMLtable@@0KA; ulong TMetabase_XMLtable::m_kZero
0x18000a98d  mov     [rsi+rax*8+328h], rcx
0x18000a995  mov     dword ptr [rsi+rax*4+500h], 2
0x18000a9a0  xor     eax, eax
0x18000a9a2  add     rsp, 28h
0x18000a9a6  pop     rdi
0x18000a9a7  pop     rsi
0x18000a9a8  pop     rbp
0x18000a9a9  pop     rbx
0x18000a9aa  retn
```
