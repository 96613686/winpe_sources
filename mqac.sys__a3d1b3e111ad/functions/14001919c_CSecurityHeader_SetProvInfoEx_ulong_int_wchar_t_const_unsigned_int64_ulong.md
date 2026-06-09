# CSecurityHeader::SetProvInfoEx(ulong,int,wchar_t const *,unsigned __int64,ulong)

- ea: `0x14001919c`
- end: `0x14001924e`
- name: `?SetProvInfoEx@CSecurityHeader@@QEAAXKHPEB_W_KK@Z`
- size: `178`
- prototype: `void(CSecurityHeader *__hidden this, unsigned int, int, const wchar_t *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012dc4`

## callees

- `0x14000eb60`
- `0x14001919c`

## pseudocode

```c
void __fastcall CSecurityHeader::SetProvInfoEx(
        CSecurityHeader *this,
        unsigned int a2,
        char a3,
        wchar_t *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  CSecurityHeader *v7; // r11
  int v8; // edi
  __int64 v9; // rcx

  v7 = this;
  *(_WORD *)this ^= ((unsigned __int8)*(_WORD *)this ^ (unsigned __int8)(a3 << 6)) & 0x40;
  if ( (a3 & 1) == 0 )
  {
    v8 = 0;
    v9 = ((*((_DWORD *)this + 2) + 3) & 0xFFFFFFFC)
       + ((*((unsigned __int16 *)this + 1) + 3) & 0xFFFFFFFC)
       + ((*((unsigned __int16 *)this + 2) + 3) & 0xFFFFFFFC)
       + ((*((unsigned __int16 *)this + 3) + 3) & 0xFFFFFFFC);
    *(_DWORD *)((char *)v7 + v9 + 16) = a6;
    if ( a4 )
    {
      v8 = a5 + 1;
      StringCchCopyW((wchar_t *)((char *)v7 + (unsigned int)v9 + 20), a5 + 1, a4);
    }
    *((_DWORD *)v7 + 3) = 2 * v8 + 4;
  }
  if ( a2 )
  {
    if ( a2 > *((_DWORD *)v7 + 3) )
      *((_DWORD *)v7 + 3) = a2;
  }
}

```

## disassembly

```asm
0x14001919c  mov     [rsp+arg_0], rbx
0x1400191a1  push    rdi
0x1400191a2  sub     rsp, 20h
0x1400191a6  movzx   r10d, word ptr [rcx]
0x1400191aa  movzx   eax, r8w
0x1400191ae  shl     ax, 6
0x1400191b2  mov     ebx, edx
0x1400191b4  xor     ax, r10w
0x1400191b8  mov     r11, rcx
0x1400191bb  and     ax, 40h
0x1400191bf  xor     ax, r10w
0x1400191c3  mov     [rcx], ax
0x1400191c6  test    r8b, 1
0x1400191ca  jnz     short loc_140019234
0x1400191cc  movzx   ecx, word ptr [rcx+6]
0x1400191d0  mov     edx, 0FFFFFFFCh
0x1400191d5  movzx   eax, word ptr [r11+4]
0x1400191da  add     ecx, 3
0x1400191dd  add     eax, 3
0x1400191e0  and     ecx, edx
0x1400191e2  and     eax, edx
0x1400191e4  xor     edi, edi
0x1400191e6  add     ecx, eax
0x1400191e8  movzx   eax, word ptr [r11+2]
0x1400191ed  add     eax, 3
0x1400191f0  and     eax, edx
0x1400191f2  add     ecx, eax
0x1400191f4  mov     eax, [r11+8]
0x1400191f8  add     eax, 3
0x1400191fb  and     eax, edx
0x1400191fd  add     ecx, eax
0x1400191ff  mov     eax, [rsp+28h+arg_28]
0x140019203  mov     edx, ecx
0x140019205  mov     [rcx+r11+10h], eax
0x14001920a  test    r9, r9
0x14001920d  jz      short loc_140019229
0x14001920f  mov     rdi, [rsp+28h+arg_20]
0x140019214  lea     rcx, [r11+14h]
0x140019218  inc     rdi
0x14001921b  add     rcx, rdx; wchar_t *
0x14001921e  mov     rdx, rdi; unsigned __int64
0x140019221  mov     r8, r9; wchar_t *
0x140019224  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140019229  lea     eax, ds:4[rdi*2]
0x140019230  mov     [r11+0Ch], eax
0x140019234  test    ebx, ebx
0x140019236  jz      short loc_140019242
0x140019238  cmp     ebx, [r11+0Ch]
0x14001923c  jbe     short loc_140019242
0x14001923e  mov     [r11+0Ch], ebx
0x140019242  mov     rbx, [rsp+28h+arg_0]
0x140019247  add     rsp, 20h
0x14001924b  pop     rdi
0x14001924c  retn
```
