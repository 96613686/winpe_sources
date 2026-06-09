# CCertEncodeStringArray::_Cleanup(void)

- ea: `0x18000405c`
- end: `0x1800040ee`
- name: `?_Cleanup@CCertEncodeStringArray@@AEAAXXZ`
- size: `146`
- prototype: `void __fastcall(CCertEncodeStringArray *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000374c`
- `0x180003790`
- `0x180003e90`

## callees

- `0x18000405c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040bd`

## pseudocode

```c
void __fastcall CCertEncodeStringArray::_Cleanup(CCertEncodeStringArray *this)
{
  _DWORD *v1; // rsi
  _DWORD *v3; // rdi
  int i; // ebp
  _QWORD *v5; // rcx
  void *v6; // rcx

  v1 = (_DWORD *)((char *)this + 72);
  v3 = (_DWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 8) )
  {
    for ( i = 0; i < *v1; ++i )
    {
      v5 = *(_QWORD **)(*((_QWORD *)this + 8) + 8LL * i);
      if ( *v3 )
      {
        v5 = (_QWORD *)v5[2];
        if ( !v5 )
          continue;
      }
      LocalFree(v5);
    }
    if ( *v3 )
    {
      v6 = (void *)**((_QWORD **)this + 8);
      if ( v6 )
        LocalFree(v6);
    }
    LocalFree(*((HLOCAL *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  *v1 = 0;
  *((_DWORD *)this + 19) = 0;
  *v3 = 0;
  *((_DWORD *)this + 21) = 7;
}

```

## disassembly

```asm
0x18000405c  push    rbx
0x18000405e  push    rbp
0x18000405f  push    rsi
0x180004060  push    rdi
0x180004061  sub     rsp, 28h
0x180004065  cmp     qword ptr [rcx+40h], 0
0x18000406a  lea     rsi, [rcx+48h]
0x18000406e  mov     rbx, rcx
0x180004071  lea     rdi, [rcx+50h]
0x180004075  jz      short loc_1800040CB
0x180004077  xor     ebp, ebp
0x180004079  cmp     [rsi], ebp
0x18000407b  jle     short loc_1800040A2
0x18000407d  cmp     dword ptr [rdi], 0
0x180004080  mov     rax, [rbx+40h]
0x180004084  movsxd  rcx, ebp
0x180004087  mov     rcx, [rax+rcx*8]
0x18000408b  jz      short loc_180004096
0x18000408d  mov     rcx, [rcx+10h]; hMem
0x180004091  test    rcx, rcx
0x180004094  jz      short loc_18000409C
0x180004096  call    cs:__imp_LocalFree
0x18000409c  inc     ebp
0x18000409e  cmp     ebp, [rsi]
0x1800040a0  jl      short loc_18000407D
0x1800040a2  cmp     dword ptr [rdi], 0
0x1800040a5  jz      short loc_1800040B9
0x1800040a7  mov     rax, [rbx+40h]
0x1800040ab  mov     rcx, [rax]; hMem
0x1800040ae  test    rcx, rcx
0x1800040b1  jz      short loc_1800040B9
0x1800040b3  call    cs:__imp_LocalFree
0x1800040b9  mov     rcx, [rbx+40h]; hMem
0x1800040bd  call    cs:__imp_LocalFree
0x1800040c3  mov     qword ptr [rbx+40h], 0
0x1800040cb  mov     dword ptr [rsi], 0
0x1800040d1  mov     dword ptr [rbx+4Ch], 0
0x1800040d8  mov     dword ptr [rdi], 0
0x1800040de  mov     dword ptr [rbx+54h], 7
0x1800040e5  add     rsp, 28h
0x1800040e9  pop     rdi
0x1800040ea  pop     rsi
0x1800040eb  pop     rbp
0x1800040ec  pop     rbx
0x1800040ed  retn
```
