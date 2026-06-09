# CMediaType::SetFormat(uchar *,ulong)

- ea: `0x10030181`
- end: `0x100301e9`
- name: `?SetFormat@CMediaType@@QAEHPAEK@Z`
- size: `104`
- prototype: `int __thiscall(CMediaType *__hidden this, unsigned __int8 *Src, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1001c3e4`
- `0x1001ffa0`

## callees

- `0x10030181`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10030198`
- `ole32!CoTaskMemAlloc` at `0x10030198`
- `ole32!CoTaskMemFree` at `0x100301c6`
- `ole32!CoTaskMemFree` at `0x100301c6`

## pseudocode

```c
int __thiscall CMediaType::SetFormat(CMediaType *this, unsigned __int8 *Src, unsigned int cb)
{
  CMediaType *v4; // ebx
  unsigned __int8 *pbFormat; // ebx

  if ( this->cbFormat == cb )
  {
    v4 = this;
  }
  else
  {
    pbFormat = (unsigned __int8 *)CoTaskMemAlloc(cb);
    if ( pbFormat )
    {
      if ( this->cbFormat )
        CoTaskMemFree(this->pbFormat);
      this->cbFormat = cb;
      this->pbFormat = pbFormat;
      goto LABEL_11;
    }
    if ( cb > this->cbFormat )
      return 0;
    v4 = this;
  }
  pbFormat = v4->pbFormat;
  if ( !this->pbFormat )
    return 0;
LABEL_11:
  memcpy(pbFormat, Src, cb);
  return 1;
}

```

## disassembly

```asm
0x10030181  mov     edi, edi
0x10030183  push    ebp
0x10030184  mov     ebp, esp
0x10030186  push    ebx
0x10030187  push    esi
0x10030188  mov     esi, ecx
0x1003018a  push    edi
0x1003018b  mov     edi, [ebp+cb]
0x1003018e  cmp     [esi+40h], edi
0x10030191  jnz     short loc_10030197
0x10030193  mov     ebx, ecx
0x10030195  jmp     short loc_100301AB
0x10030197  push    edi; cb
0x10030198  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1003019e  mov     ebx, eax
0x100301a0  test    ebx, ebx
0x100301a2  jnz     short loc_100301BD
0x100301a4  cmp     edi, [esi+40h]
0x100301a7  ja      short loc_100301B9
0x100301a9  mov     ebx, esi
0x100301ab  push    44h ; 'D'
0x100301ad  pop     eax
0x100301ae  mov     ecx, eax
0x100301b0  cmp     dword ptr [esi+eax], 0
0x100301b4  mov     ebx, [ebx+ecx]
0x100301b7  jnz     short loc_100301D2
0x100301b9  xor     eax, eax
0x100301bb  jmp     short loc_100301E2
0x100301bd  cmp     dword ptr [esi+40h], 0
0x100301c1  jz      short loc_100301CC
0x100301c3  push    dword ptr [esi+44h]; pv
0x100301c6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100301cc  mov     [esi+40h], edi
0x100301cf  mov     [esi+44h], ebx
0x100301d2  push    edi; Size
0x100301d3  push    [ebp+Src]; Src
0x100301d6  push    ebx; void *
0x100301d7  call    _memcpy
0x100301dc  xor     eax, eax
0x100301de  add     esp, 0Ch
0x100301e1  inc     eax
0x100301e2  pop     edi
0x100301e3  pop     esi
0x100301e4  pop     ebx
0x100301e5  pop     ebp
0x100301e6  retn    8
```
