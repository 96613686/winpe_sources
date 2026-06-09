# SipFile::InitReadContentLoop(void)

- ea: `0x180004650`
- end: `0x1800046f8`
- name: `?InitReadContentLoop@SipFile@@QEAAKXZ`
- size: `168`
- prototype: `unsigned int __fastcall(SipFile *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002540`
- `0x180002c00`

## callees

- `0x1800034d4`
- `0x180003c70`
- `0x180004650`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SipFile::InitReadContentLoop(void **this)
{
  void (__fastcall **v1)(SipFile *); // rax
  unsigned int v2; // edi
  unsigned int Contents; // esi
  LPCCH *v5; // r15
  LPCCH *v6; // r14
  LPCCH v7; // rcx
  unsigned int *v8; // rbp
  unsigned int v10; // [rsp+70h] [rbp+8h] BYREF

  v1 = (void (__fastcall **)(SipFile *))*this;
  v2 = 0;
  v10 = 0;
  Contents = 0;
  v1[7]((SipFile *)this);
  v5 = (LPCCH *)(this + 8);
  if ( !this[8] )
  {
    Contents = SipFile::GetContents(this, (unsigned __int8 **)this + 8, &v10);
    if ( Contents )
      return Contents;
    v2 = v10;
  }
  v6 = (LPCCH *)(this + 9);
  v7 = (LPCCH)this[9];
  if ( v7 )
  {
LABEL_10:
    this[11] = (void *)v7;
    *((_WORD *)this + 48) = 0;
    return Contents;
  }
  v8 = (unsigned int *)(this + 10);
  Contents = SipFile::ConvertFileEncodedStringToUnicode(
               (SipFile *)this,
               *v5,
               v2,
               (unsigned __int16 **)this + 9,
               (unsigned int *)this + 20);
  if ( !Contents )
  {
    v7 = *v6;
    if ( !*v6 )
    {
      if ( *v8 )
      {
        v7 = 0;
      }
      else
      {
        v7 = *v5;
        *v6 = *v5;
        *v8 = v2 >> 1;
      }
    }
    goto LABEL_10;
  }
  return Contents;
}

```

## disassembly

```asm
0x180004650  push    rbx
0x180004652  push    rbp
0x180004653  push    rsi
0x180004654  push    rdi
0x180004655  push    r14
0x180004657  push    r15
0x180004659  sub     rsp, 38h
0x18000465d  mov     rax, [rcx]
0x180004660  xor     edi, edi
0x180004662  mov     rbx, rcx
0x180004665  mov     [rsp+68h+arg_0], edi
0x180004669  xor     esi, esi
0x18000466b  mov     rax, [rax+38h]
0x18000466f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004674  lea     r15, [rbx+40h]
0x180004678  cmp     [r15], rsi
0x18000467b  jnz     short loc_180004697
0x18000467d  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x180004682  mov     rdx, r15; unsigned __int8 **
0x180004685  mov     rcx, rbx; this
0x180004688  call    ?GetContents@SipFile@@QEAAKPEAPEAEPEAK@Z; SipFile::GetContents(uchar * *,ulong *)
0x18000468d  mov     esi, eax
0x18000468f  test    eax, eax
0x180004691  jnz     short loc_1800046E9
0x180004693  mov     edi, [rsp+68h+arg_0]
0x180004697  lea     r14, [rbx+48h]
0x18000469b  mov     rcx, [r14]
0x18000469e  test    rcx, rcx
0x1800046a1  jnz     short loc_1800046DF
0x1800046a3  mov     rdx, [r15]; lpMultiByteStr
0x1800046a6  lea     rbp, [rbx+50h]
0x1800046aa  mov     r9, r14; unsigned __int16 **
0x1800046ad  mov     [rsp+68h+var_48], rbp; unsigned int *
0x1800046b2  mov     r8d, edi; cbMultiByte
0x1800046b5  mov     rcx, rbx; this
0x1800046b8  call    ?ConvertFileEncodedStringToUnicode@SipFile@@IEAAKPEBEKPEAPEAGPEAK@Z; SipFile::ConvertFileEncodedStringToUnicode(uchar const *,ulong,ushort * *,ulong *)
0x1800046bd  mov     esi, eax
0x1800046bf  test    eax, eax
0x1800046c1  jnz     short loc_1800046E9
0x1800046c3  mov     rcx, [r14]
0x1800046c6  test    rcx, rcx
0x1800046c9  jnz     short loc_1800046DF
0x1800046cb  cmp     [rbp+0], ecx
0x1800046ce  jnz     short loc_1800046DD
0x1800046d0  mov     rcx, [r15]
0x1800046d3  shr     edi, 1
0x1800046d5  mov     [r14], rcx
0x1800046d8  mov     [rbp+0], edi
0x1800046db  jmp     short loc_1800046DF
0x1800046dd  xor     ecx, ecx
0x1800046df  xor     eax, eax
0x1800046e1  mov     [rbx+58h], rcx
0x1800046e5  mov     [rbx+60h], ax
0x1800046e9  mov     eax, esi
0x1800046eb  add     rsp, 38h
0x1800046ef  pop     r15
0x1800046f1  pop     r14
0x1800046f3  pop     rdi
0x1800046f4  pop     rsi
0x1800046f5  pop     rbp
0x1800046f6  pop     rbx
0x1800046f7  retn
```
