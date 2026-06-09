# _PCW_BUFFER::CollectInstance(_PCW_REGISTRATION const *,_UNICODE_STRING const *,ulong,ulong,void const * const *,_PCW_DATA const *)

- ea: `0x140008840`
- end: `0x1400089c4`
- name: `?CollectInstance@_PCW_BUFFER@@QEAAJPEBU_PCW_REGISTRATION@@PEBU_UNICODE_STRING@@KKPEBQEBXPEBU_PCW_DATA@@@Z`
- size: `388`
- prototype: `int __fastcall(_PCW_BUFFER *this, const struct _PCW_REGISTRATION *, const struct _UNICODE_STRING *, int, unsigned int, const void *const *, const struct _PCW_DATA *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400089cc`
- `0x14000da40`

## callees

- `0x140001370`
- `0x140008224`
- `0x140008840`
- `0x140008fb0`
- `0x140008fd0`

## pseudocode

```c
int __fastcall _PCW_BUFFER::CollectInstance(
        _PCW_BUFFER *this,
        const struct _PCW_REGISTRATION *a2,
        const struct _UNICODE_STRING *a3,
        int a4,
        unsigned int a5,
        const void *const *a6,
        const struct _PCW_DATA *a7)
{
  int v7; // r11d
  unsigned int v10; // r8d
  int result; // eax
  int v14; // r11d
  __int64 v15; // rdi
  const struct _PCW_COUNTER_DESCRIPTOR *v16; // r8
  __int64 v17; // rax
  __int64 StructIndex; // rax
  const void *Data; // rdx
  char *v20; // rdi
  __int16 v21; // [rsp+20h] [rbp-38h] BYREF
  void *v22; // [rsp+28h] [rbp-30h] BYREF
  int v23; // [rsp+30h] [rbp-28h] BYREF
  __int128 v24; // [rsp+34h] [rbp-24h]

  v7 = *((_DWORD *)this + 2);
  v10 = (a3->Length + 27) & 0xFFFFFFF8;
  v22 = 0;
  v23 = v7;
  v24 = 0;
  DWORD1(v24) = v10;
  result = _PCW_BUFFER::ReserveSpaceVoid(this, &v22, v10);
  if ( result >= 0 )
  {
    v15 = 0;
    *((_QWORD *)this + 7) &= *((_QWORD *)a2 + 2);
    *((_DWORD *)this + 7) = 0;
    if ( *((_DWORD *)a2 + 6) )
    {
      while ( 1 )
      {
        v16 = (const struct _PCW_COUNTER_DESCRIPTOR *)(*((_QWORD *)a2 + 8) + 8 * v15);
        v17 = *((_QWORD *)this + 7);
        if ( _bittest64(&v17, LOBYTE(v16->Id)) )
        {
          StructIndex = v16->StructIndex;
          if ( (unsigned int)StructIndex >= a5 )
            return -1073741306;
          if ( a6 )
          {
            Data = a6[StructIndex];
          }
          else
          {
            if ( a7[v16->StructIndex].Size < v16->Offset + (unsigned int)v16->Size )
              return -1073741306;
            Data = a7[v16->StructIndex].Data;
          }
          result = _PCW_BUFFER::AddCounter(this, Data, v16);
          if ( result < 0 )
            return result;
        }
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= *((_DWORD *)a2 + 6) )
        {
          v14 = v23;
          break;
        }
      }
    }
    v20 = (char *)v22;
    if ( !v22 )
      return 0;
    v23 = v14 - *((_DWORD *)this + 2);
    v21 = 0;
    DWORD2(v24) = *((_DWORD *)this + 7);
    LODWORD(v24) = a4;
    result = PcwpWriteToUserBuffer(v22, &v23, 0x10u);
    if ( result >= 0 )
    {
      result = PcwpWriteToUserBuffer(v20 + 16, a3->Buffer, a3->Length);
      if ( result >= 0 )
      {
        result = PcwpWriteToUserBuffer(&v20[2 * ((unsigned __int64)a3->Length >> 1) + 16], &v21, 2u);
        if ( result >= 0 )
        {
          ++*((_DWORD *)this + 6);
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008840  push    rbp
0x140008842  push    rbx
0x140008843  push    rsi
0x140008844  push    rdi
0x140008845  push    r12
0x140008847  push    r13
0x140008849  push    r14
0x14000884b  push    r15
0x14000884d  mov     rbp, rsp
0x140008850  sub     rsp, 58h
0x140008854  mov     rax, cs:__security_cookie
0x14000885b  xor     rax, rsp
0x14000885e  mov     [rbp+var_10], rax
0x140008862  mov     r11d, [rcx+8]
0x140008866  mov     rsi, r8
0x140008869  movzx   r8d, word ptr [r8]
0x14000886d  mov     r14, rdx
0x140008870  mov     r15, [rbp+arg_28]
0x140008874  lea     rdx, [rbp+var_30]; void **
0x140008878  mov     r12, [rbp+arg_30]
0x14000887c  add     r8d, 1Bh
0x140008880  and     r8d, 0FFFFFFF8h; unsigned int
0x140008884  mov     [rbp+var_30], 0
0x14000888c  xorps   xmm0, xmm0
0x14000888f  mov     [rbp+var_28], r11d
0x140008893  movdqu  [rbp+var_24], xmm0
0x140008898  mov     dword ptr [rbp+var_24+4], r8d
0x14000889c  mov     r13d, r9d
0x14000889f  mov     rbx, rcx
0x1400088a2  call    ?ReserveSpaceVoid@_PCW_BUFFER@@AEAAJPEAPEAXK@Z; _PCW_BUFFER::ReserveSpaceVoid(void * *,ulong)
0x1400088a7  test    eax, eax
0x1400088a9  js      loc_14000899F
0x1400088af  mov     rax, [r14+10h]
0x1400088b3  xor     edi, edi
0x1400088b5  and     [rbx+38h], rax
0x1400088b9  mov     dword ptr [rbx+1Ch], 0
0x1400088c0  cmp     [r14+18h], edi
0x1400088c4  jbe     short loc_14000892D
0x1400088c6  mov     rax, [r14+40h]
0x1400088ca  lea     r8, [rax+rdi*8]; struct _PCW_COUNTER_DESCRIPTOR *
0x1400088ce  mov     rax, [rbx+38h]
0x1400088d2  movzx   ecx, byte ptr [r8]
0x1400088d6  bt      rax, rcx
0x1400088da  jnb     short loc_140008921
0x1400088dc  movzx   eax, word ptr [r8+2]
0x1400088e1  cmp     eax, [rbp+arg_20]
0x1400088e4  jnb     loc_1400089BD
0x1400088ea  mov     edx, eax
0x1400088ec  test    r15, r15
0x1400088ef  jz      short loc_1400088F7
0x1400088f1  mov     rdx, [r15+rax*8]
0x1400088f5  jmp     short loc_140008915
0x1400088f7  movzx   ecx, word ptr [r8+6]
0x1400088fc  add     rdx, rdx
0x1400088ff  movzx   eax, word ptr [r8+4]
0x140008904  add     ecx, eax
0x140008906  cmp     [r12+rdx*8+8], ecx
0x14000890b  jb      loc_1400089BD
0x140008911  mov     rdx, [r12+rdx*8]; void *
0x140008915  mov     rcx, rbx; this
0x140008918  call    ?AddCounter@_PCW_BUFFER@@AEAAJPEBXPEBU_PCW_COUNTER_DESCRIPTOR@@@Z; _PCW_BUFFER::AddCounter(void const *,_PCW_COUNTER_DESCRIPTOR const *)
0x14000891d  test    eax, eax
0x14000891f  js      short loc_14000899F
0x140008921  inc     edi
0x140008923  cmp     edi, [r14+18h]
0x140008927  jb      short loc_1400088C6
0x140008929  mov     r11d, [rbp+var_28]
0x14000892d  mov     rdi, [rbp+var_30]
0x140008931  test    rdi, rdi
0x140008934  jz      short loc_14000899D
0x140008936  sub     r11d, [rbx+8]
0x14000893a  lea     rdx, [rbp+var_28]; void *
0x14000893e  xor     eax, eax
0x140008940  mov     [rbp+var_28], r11d
0x140008944  mov     [rbp+var_38], ax
0x140008948  mov     r8d, 10h; unsigned int
0x14000894e  mov     eax, [rbx+1Ch]
0x140008951  mov     rcx, rdi; void *
0x140008954  mov     dword ptr [rbp+var_24+8], eax
0x140008957  mov     dword ptr [rbp+var_24], r13d
0x14000895b  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x140008960  test    eax, eax
0x140008962  js      short loc_14000899F
0x140008964  movzx   r8d, word ptr [rsi]; unsigned int
0x140008968  lea     rcx, [rdi+10h]; void *
0x14000896c  mov     rdx, [rsi+8]; void *
0x140008970  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x140008975  test    eax, eax
0x140008977  js      short loc_14000899F
0x140008979  movzx   eax, word ptr [rsi]
0x14000897c  lea     rdx, [rbp+var_38]; void *
0x140008980  shr     rax, 1
0x140008983  mov     r8d, 2; unsigned int
0x140008989  add     rax, 8
0x14000898d  lea     rcx, [rdi+rax*2]; void *
0x140008991  call    ?PcwpWriteToUserBuffer@@YAJPEAXPEBXK@Z; PcwpWriteToUserBuffer(void *,void const *,ulong)
0x140008996  test    eax, eax
0x140008998  js      short loc_14000899F
0x14000899a  inc     dword ptr [rbx+18h]
0x14000899d  xor     eax, eax
0x14000899f  mov     rcx, [rbp+var_10]
0x1400089a3  xor     rcx, rsp; StackCookie
0x1400089a6  call    __security_check_cookie
0x1400089ab  add     rsp, 58h
0x1400089af  pop     r15
0x1400089b1  pop     r14
0x1400089b3  pop     r13
0x1400089b5  pop     r12
0x1400089b7  pop     rdi
0x1400089b8  pop     rsi
0x1400089b9  pop     rbx
0x1400089ba  pop     rbp
0x1400089bb  retn
0x1400089bd  mov     eax, 0C0000206h
0x1400089c2  jmp     short loc_14000899F
```
