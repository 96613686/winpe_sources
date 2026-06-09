# _PCW_BUFFER::AddCounter(void const *,_PCW_COUNTER_DESCRIPTOR const *)

- ea: `0x140008224`
- end: `0x1400082e4`
- name: `?AddCounter@_PCW_BUFFER@@AEAAJPEBXPEBU_PCW_COUNTER_DESCRIPTOR@@@Z`
- size: `192`
- prototype: `int __fastcall(_PCW_BUFFER *this, char *, const struct _PCW_COUNTER_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008840`

## callees

- `0x140001370`
- `0x140008224`
- `0x140008fb0`
- `0x140008fd0`

## pseudocode

```c
int __fastcall _PCW_BUFFER::AddCounter(_PCW_BUFFER *this, char *a2, const struct _PCW_COUNTER_DESCRIPTOR *a3)
{
  USHORT Id; // ax
  int Size; // r8d
  int result; // eax
  __int64 v8; // r11
  char *v9; // rbx
  int v10; // eax
  int v11; // ecx
  void *v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h] BYREF
  int v14; // [rsp+30h] [rbp-28h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  Id = a3->Id;
  Size = a3->Size;
  HIWORD(v13) = Size;
  WORD2(v13) = Id;
  LODWORD(v13) = (Size + 15) & 0xFFFFFFF8;
  result = _PCW_BUFFER::ReserveSpaceVoid(this, &v12, v13);
  if ( result >= 0 )
  {
    v9 = (char *)v12;
    if ( v12 )
    {
      ++*(_DWORD *)(v8 + 28);
      result = PcwpWriteToUserBuffer(v9, &v13, 8u);
      if ( result >= 0 )
      {
        v10 = PcwpWriteToUserBuffer(v9 + 8, &a2[a3->Offset], a3->Size);
        v11 = 0;
        if ( v10 < 0 )
          return v10;
        return v11;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008224  push    rbx
0x140008226  push    rsi
0x140008227  push    rdi
0x140008228  sub     rsp, 40h
0x14000822c  mov     rax, cs:__security_cookie
0x140008233  xor     rax, rsp
0x140008236  mov     [rsp+58h+var_20], rax
0x14000823b  xor     eax, eax
0x14000823d  mov     [rsp+58h+var_38], 0
0x140008246  mov     [rsp+58h+var_30], rax
0x14000824b  mov     rdi, r8
0x14000824e  mov     [rsp+58h+var_28], eax
0x140008252  mov     rsi, rdx
0x140008255  movzx   eax, word ptr [r8]
0x140008259  lea     rdx, [rsp+58h+var_38]; void **
0x14000825e  movzx   r8d, word ptr [r8+6]
0x140008263  mov     r11, rcx
0x140008266  mov     word ptr [rsp+58h+var_30+6], r8w
0x14000826c  add     r8d, 0Fh
0x140008270  and     r8d, 0FFFFFFF8h; unsigned int
0x140008274  mov     word ptr [rsp+58h+var_30+4], ax
0x140008279  mov     dword ptr [rsp+58h+var_30], r8d
0x14000827e  call    ?ReserveSpaceVoid@_PCW_BUFFER@@AEAAJPEAPEAXK@Z; _PCW_BUFFER::ReserveSpaceVoid(void * *,ulong)
0x140008283  test    eax, eax
0x140008285  js      short loc_1400082CE
0x140008287  mov     rbx, [rsp+58h+var_38]
0x14000828c  test    rbx, rbx
0x14000828f  jz      short loc_1400082CC
0x140008291  inc     dword ptr [r11+1Ch]
0x140008295  lea     rdx, [rsp+58h+var_30]; void *
0x14000829a  mov     r8d, 8; unsigned int
0x1400082a0  mov     rcx, rbx; void *
0x1400082a3  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x1400082a8  test    eax, eax
0x1400082aa  js      short loc_1400082CE
0x1400082ac  movzx   edx, word ptr [rdi+4]
0x1400082b0  lea     rcx, [rbx+8]; void *
0x1400082b4  movzx   r8d, word ptr [rdi+6]; unsigned int
0x1400082b9  add     rdx, rsi; void *
0x1400082bc  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x1400082c1  xor     ecx, ecx
0x1400082c3  test    eax, eax
0x1400082c5  cmovs   ecx, eax
0x1400082c8  mov     eax, ecx
0x1400082ca  jmp     short loc_1400082CE
0x1400082cc  xor     eax, eax
0x1400082ce  mov     rcx, [rsp+58h+var_20]
0x1400082d3  xor     rcx, rsp; StackCookie
0x1400082d6  call    __security_check_cookie
0x1400082db  add     rsp, 40h
0x1400082df  pop     rdi
0x1400082e0  pop     rsi
0x1400082e1  pop     rbx
0x1400082e2  retn
```
