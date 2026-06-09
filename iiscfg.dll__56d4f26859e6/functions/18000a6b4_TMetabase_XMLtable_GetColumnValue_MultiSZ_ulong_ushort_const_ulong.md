# TMetabase_XMLtable::GetColumnValue_MultiSZ(ulong,ushort const *,ulong)

- ea: `0x18000a6b4`
- end: `0x18000a892`
- name: `?GetColumnValue_MultiSZ@TMetabase_XMLtable@@AEAAJKPEBGK@Z`
- size: `478`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009acc`

## callees

- `0x18000a6b4`
- `0x18000bdf4`

## pseudocode

```c
__int64 __fastcall TMetabase_XMLtable::GetColumnValue_MultiSZ(
        LPVOID *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v7; // r14
  __int64 v8; // rsi
  unsigned __int16 *v9; // rdx
  char v10; // r10
  __int64 v11; // r8
  char v12; // r9
  unsigned __int16 v13; // ax
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // r9
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // r8

  if ( a3 && a4 )
  {
    v7 = a2;
    TGrowableBuffer::Grow(&this[2 * a2 + 174], 2LL * (a4 + 2));
    v8 = v7;
    v9 = (unsigned __int16 *)this[2 * v7 + 174];
    this[v7 + 101] = v9;
    if ( a4 )
    {
      v10 = 1;
      LODWORD(v11) = 0;
      v12 = 1;
      while ( 1 )
      {
        switch ( a3[(unsigned int)v11] )
        {
          case 9u:
            goto LABEL_26;
          case 0xAu:
          case 0xDu:
            if ( !v12 )
            {
              do
              {
                v14 = v9;
                v15 = v9--;
              }
              while ( v9 > this[v8 + 101] && (*v9 == 32 || *v9 == 9) );
              if ( *v9 )
              {
                *v15 = 0;
                v9 = v14 + 1;
              }
              else
              {
                v9 = v14;
              }
              v10 = 1;
              v12 = 1;
            }
            break;
          case 0x20u:
LABEL_26:
            v12 = 0;
            if ( !v10 )
LABEL_27:
              *v9++ = a3[(unsigned int)v11];
            break;
          default:
            v12 = 0;
            v10 = 0;
            switch ( a3[(unsigned int)v11] )
            {
              case 0xD800u:
                v11 = (unsigned int)(v11 + 1);
                v13 = a3[v11] + 9216;
                break;
              case 0xD836u:
                v11 = (unsigned int)(v11 + 1);
                *v9 = a3[v11] & 0xFBFF;
                goto LABEL_28;
              case 0xD837u:
                LODWORD(v11) = v11 + 1;
                v13 = a3[(unsigned int)v11];
                break;
              case 0xD83Fu:
                v11 = (unsigned int)(v11 + 1);
                v13 = a3[v11] | 0x2000;
                break;
              default:
                goto LABEL_27;
            }
            *v9 = v13;
            break;
        }
LABEL_28:
        LODWORD(v11) = v11 + 1;
        if ( (unsigned int)v11 >= a4 )
          goto LABEL_29;
      }
    }
    do
    {
LABEL_29:
      v16 = v9;
      v17 = v9--;
    }
    while ( v9 > this[v8 + 101] && (*v9 == 32 || *v9 == 9) );
    if ( *v9 )
    {
      *v17 = 0;
      ++v16;
    }
    *v16 = 0;
    *((_DWORD *)this + v7 + 320) = (_DWORD)v16 - LODWORD(this[v7 + 101]) + 2;
  }
  else
  {
    this[a2 + 101] = &TMetabase_XMLtable::m_kZero;
    *((_DWORD *)this + a2 + 320) = 4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a6b4  mov     [rsp+arg_0], rbx
0x18000a6b9  mov     [rsp+arg_8], rbp
0x18000a6be  push    rsi
0x18000a6bf  push    rdi
0x18000a6c0  push    r12
0x18000a6c2  push    r14
0x18000a6c4  push    r15
0x18000a6c6  sub     rsp, 20h
0x18000a6ca  xor     r15d, r15d
0x18000a6cd  mov     ebp, r9d
0x18000a6d0  mov     rdi, r8
0x18000a6d3  mov     rbx, rcx
0x18000a6d6  test    r8, r8
0x18000a6d9  jz      loc_18000A85D
0x18000a6df  test    r9d, r9d
0x18000a6e2  jz      loc_18000A85D
0x18000a6e8  mov     r14d, edx
0x18000a6eb  lea     edx, [r9+2]
0x18000a6ef  add     rdx, rdx; unsigned __int64
0x18000a6f2  lea     rcx, [r14+57h]
0x18000a6f6  shl     rcx, 4
0x18000a6fa  add     rcx, rbx; this
0x18000a6fd  call    ?Grow@TGrowableBuffer@@QEAAX_K@Z; TGrowableBuffer::Grow(unsigned __int64)
0x18000a702  lea     rax, [r14+57h]
0x18000a706  add     rax, rax
0x18000a709  lea     rsi, ds:0[r14*8]
0x18000a711  lea     r12d, [r15+9]
0x18000a715  mov     rdx, [rbx+rax*8]
0x18000a719  mov     [rbx+r14*8+328h], rdx
0x18000a721  test    ebp, ebp
0x18000a723  jz      loc_18000A816
0x18000a729  mov     r10b, 1
0x18000a72c  mov     r8d, r15d
0x18000a72f  mov     r9b, r10b
0x18000a732  mov     eax, r8d
0x18000a735  movzx   r11d, word ptr [rdi+rax*2]
0x18000a73a  mov     ecx, r11d
0x18000a73d  sub     ecx, r12d
0x18000a740  jz      loc_18000A7FA
0x18000a746  sub     ecx, 1
0x18000a749  jz      short loc_18000A7BA
0x18000a74b  sub     ecx, 3
0x18000a74e  jz      short loc_18000A7BA
0x18000a750  sub     ecx, 13h
0x18000a753  jz      loc_18000A7FA
0x18000a759  mov     r9b, r15b
0x18000a75c  mov     r10b, r15b
0x18000a75f  sub     ecx, 0D7E0h
0x18000a765  jz      short loc_18000A7AB
0x18000a767  sub     ecx, 36h ; '6'
0x18000a76a  jz      short loc_18000A796
0x18000a76c  sub     ecx, 1
0x18000a76f  jz      short loc_18000A789
0x18000a771  cmp     ecx, 8
0x18000a774  jnz     loc_18000A802
0x18000a77a  inc     r8d
0x18000a77d  mov     eax, 2000h
0x18000a782  or      ax, [rdi+r8*2]
0x18000a787  jmp     short loc_18000A791
0x18000a789  inc     r8d
0x18000a78c  movzx   eax, word ptr [rdi+r8*2]
0x18000a791  mov     [rdx], ax
0x18000a794  jmp     short loc_18000A80A
0x18000a796  inc     r8d
0x18000a799  mov     eax, 0FBFFh
0x18000a79e  movzx   ecx, word ptr [rdi+r8*2]
0x18000a7a3  and     cx, ax
0x18000a7a6  mov     [rdx], cx
0x18000a7a9  jmp     short loc_18000A80A
0x18000a7ab  inc     r8d
0x18000a7ae  mov     eax, 2400h
0x18000a7b3  add     ax, [rdi+r8*2]
0x18000a7b8  jmp     short loc_18000A791
0x18000a7ba  test    r9b, r9b
0x18000a7bd  jnz     short loc_18000A80A
0x18000a7bf  mov     rcx, rdx
0x18000a7c2  mov     r9, rdx
0x18000a7c5  sub     rdx, 2
0x18000a7c9  cmp     rdx, [rsi+rbx+328h]
0x18000a7d1  jbe     short loc_18000A7DF
0x18000a7d3  cmp     word ptr [rdx], 20h ; ' '
0x18000a7d7  jz      short loc_18000A7BF
0x18000a7d9  cmp     [rdx], r12w
0x18000a7dd  jz      short loc_18000A7BF
0x18000a7df  cmp     [rdx], r15w
0x18000a7e3  jnz     short loc_18000A7EA
0x18000a7e5  mov     rdx, rcx
0x18000a7e8  jmp     short loc_18000A7F2
0x18000a7ea  mov     [r9], r15w
0x18000a7ee  lea     rdx, [rcx+2]
0x18000a7f2  mov     r10b, 1
0x18000a7f5  mov     r9b, r10b
0x18000a7f8  jmp     short loc_18000A80A
0x18000a7fa  mov     r9b, r15b
0x18000a7fd  test    r10b, r10b
0x18000a800  jnz     short loc_18000A80A
0x18000a802  mov     [rdx], r11w
0x18000a806  add     rdx, 2
0x18000a80a  inc     r8d
0x18000a80d  cmp     r8d, ebp
0x18000a810  jb      loc_18000A732
0x18000a816  mov     rcx, rdx
0x18000a819  mov     r8, rdx
0x18000a81c  sub     rdx, 2
0x18000a820  cmp     rdx, [rsi+rbx+328h]
0x18000a828  jbe     short loc_18000A836
0x18000a82a  cmp     word ptr [rdx], 20h ; ' '
0x18000a82e  jz      short loc_18000A816
0x18000a830  cmp     [rdx], r12w
0x18000a834  jz      short loc_18000A816
0x18000a836  cmp     [rdx], r15w
0x18000a83a  jz      short loc_18000A844
0x18000a83c  mov     [r8], r15w
0x18000a840  add     rcx, 2
0x18000a844  mov     [rcx], r15w
0x18000a848  sub     ecx, [rbx+r14*8+328h]
0x18000a850  add     ecx, 2
0x18000a853  mov     [rbx+r14*4+500h], ecx
0x18000a85b  jmp     short loc_18000A879
0x18000a85d  mov     eax, edx
0x18000a85f  lea     rcx, ?m_kZero@TMetabase_XMLtable@@0KA; ulong TMetabase_XMLtable::m_kZero
0x18000a866  mov     [rbx+rax*8+328h], rcx
0x18000a86e  mov     dword ptr [rbx+rax*4+500h], 4
0x18000a879  mov     rbx, [rsp+48h+arg_0]
0x18000a87e  xor     eax, eax
0x18000a880  mov     rbp, [rsp+48h+arg_8]
0x18000a885  add     rsp, 20h
0x18000a889  pop     r15
0x18000a88b  pop     r14
0x18000a88d  pop     r12
0x18000a88f  pop     rdi
0x18000a890  pop     rsi
0x18000a891  retn
```
