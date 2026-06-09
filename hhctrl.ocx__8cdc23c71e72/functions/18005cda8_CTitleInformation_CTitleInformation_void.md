# CTitleInformation::~CTitleInformation(void)

- ea: `0x18005cda8`
- end: `0x18005cef2`
- name: `??1CTitleInformation@@QEAA@XZ`
- size: `330`
- prototype: `void __fastcall(CTitleInformation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005f8c4`

## callees

- `0x18005cda8`

## import_xrefs

- `msvcrt!free` at `0x18005cdc3`
- `msvcrt!free` at `0x18005cdd2`
- `msvcrt!free` at `0x18005cde9`
- `msvcrt!free` at `0x18005ce00`
- `msvcrt!free` at `0x18005ce17`
- `msvcrt!free` at `0x18005ce2e`
- `msvcrt!free` at `0x18005ce45`
- `msvcrt!free` at `0x18005ce5c`
- `msvcrt!free` at `0x18005ce87`
- `msvcrt!free` at `0x18005ce98`
- `msvcrt!free` at `0x18005ceaf`
- `msvcrt!free` at `0x18005cdc3`
- `msvcrt!free` at `0x18005cdd2`
- `msvcrt!free` at `0x18005cde9`
- `msvcrt!free` at `0x18005ce00`
- `msvcrt!free` at `0x18005ce17`
- `msvcrt!free` at `0x18005ce2e`
- `msvcrt!free` at `0x18005ce45`
- `msvcrt!free` at `0x18005ce5c`
- `msvcrt!free` at `0x18005ce87`
- `msvcrt!free` at `0x18005ce98`
- `msvcrt!free` at `0x18005ceaf`
- `GDI32!DeleteObject` at `0x18005ceca`
- `GDI32!DeleteObject` at `0x18005cedc`
- `GDI32!DeleteObject` at `0x18005ceca`
- `GDI32!DeleteObject` at `0x18005cedc`

## pseudocode

```c
void __fastcall CTitleInformation::~CTitleInformation(CTitleInformation *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  unsigned int i; // esi
  void *v11; // rcx
  void *v12; // rcx

  v2 = (void *)*((_QWORD *)this + 15);
  if ( v2 )
    free(v2);
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 8) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 10) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 11) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 12);
  if ( v7 )
  {
    free(v7);
    *((_QWORD *)this + 12) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 7);
  if ( v8 )
  {
    free(v8);
    *((_QWORD *)this + 7) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 14);
  if ( v9 )
    free(v9);
  if ( *((_QWORD *)this + 529) )
  {
    for ( i = 0; i < *((_DWORD *)this + 1057); ++i )
    {
      free(*(void **)(*((_QWORD *)this + 529) + 16LL * i + 8));
      free(*(void **)(*((_QWORD *)this + 529) + 16LL * i));
    }
    free(*((void **)this + 529));
  }
  v11 = (void *)*((_QWORD *)this + 533);
  if ( v11 && v11 != *((void **)this + 532) )
    DeleteObject(v11);
  v12 = (void *)*((_QWORD *)this + 532);
  if ( v12 )
    DeleteObject(v12);
}

```

## disassembly

```asm
0x18005cda8  mov     [rsp+arg_0], rbx
0x18005cdad  mov     [rsp+arg_8], rsi
0x18005cdb2  push    rdi
0x18005cdb3  sub     rsp, 20h
0x18005cdb7  mov     rdi, rcx
0x18005cdba  mov     rcx, [rcx+78h]; Block
0x18005cdbe  test    rcx, rcx
0x18005cdc1  jz      short loc_18005CDC9
0x18005cdc3  call    cs:__imp_free
0x18005cdc9  mov     rcx, [rdi+40h]; Block
0x18005cdcd  test    rcx, rcx
0x18005cdd0  jz      short loc_18005CDE0
0x18005cdd2  call    cs:__imp_free
0x18005cdd8  mov     qword ptr [rdi+40h], 0
0x18005cde0  mov     rcx, [rdi+48h]; Block
0x18005cde4  test    rcx, rcx
0x18005cde7  jz      short loc_18005CDF7
0x18005cde9  call    cs:__imp_free
0x18005cdef  mov     qword ptr [rdi+48h], 0
0x18005cdf7  mov     rcx, [rdi+50h]; Block
0x18005cdfb  test    rcx, rcx
0x18005cdfe  jz      short loc_18005CE0E
0x18005ce00  call    cs:__imp_free
0x18005ce06  mov     qword ptr [rdi+50h], 0
0x18005ce0e  mov     rcx, [rdi+58h]; Block
0x18005ce12  test    rcx, rcx
0x18005ce15  jz      short loc_18005CE25
0x18005ce17  call    cs:__imp_free
0x18005ce1d  mov     qword ptr [rdi+58h], 0
0x18005ce25  mov     rcx, [rdi+60h]; Block
0x18005ce29  test    rcx, rcx
0x18005ce2c  jz      short loc_18005CE3C
0x18005ce2e  call    cs:__imp_free
0x18005ce34  mov     qword ptr [rdi+60h], 0
0x18005ce3c  mov     rcx, [rdi+38h]; Block
0x18005ce40  test    rcx, rcx
0x18005ce43  jz      short loc_18005CE53
0x18005ce45  call    cs:__imp_free
0x18005ce4b  mov     qword ptr [rdi+38h], 0
0x18005ce53  mov     rcx, [rdi+70h]; Block
0x18005ce57  test    rcx, rcx
0x18005ce5a  jz      short loc_18005CE62
0x18005ce5c  call    cs:__imp_free
0x18005ce62  cmp     qword ptr [rdi+1088h], 0
0x18005ce6a  jz      short loc_18005CEB5
0x18005ce6c  xor     esi, esi
0x18005ce6e  cmp     [rdi+1084h], esi
0x18005ce74  jbe     short loc_18005CEA8
0x18005ce76  mov     rcx, [rdi+1088h]
0x18005ce7d  mov     ebx, esi
0x18005ce7f  add     rbx, rbx
0x18005ce82  mov     rcx, [rcx+rbx*8+8]; Block
0x18005ce87  call    cs:__imp_free
0x18005ce8d  mov     rcx, [rdi+1088h]
0x18005ce94  mov     rcx, [rcx+rbx*8]; Block
0x18005ce98  call    cs:__imp_free
0x18005ce9e  inc     esi
0x18005cea0  cmp     esi, [rdi+1084h]
0x18005cea6  jb      short loc_18005CE76
0x18005cea8  mov     rcx, [rdi+1088h]; Block
0x18005ceaf  call    cs:__imp_free
0x18005ceb5  mov     rcx, [rdi+10A8h]; ho
0x18005cebc  test    rcx, rcx
0x18005cebf  jz      short loc_18005CED0
0x18005cec1  cmp     rcx, [rdi+10A0h]
0x18005cec8  jz      short loc_18005CED0
0x18005ceca  call    cs:__imp_DeleteObject
0x18005ced0  mov     rcx, [rdi+10A0h]; ho
0x18005ced7  test    rcx, rcx
0x18005ceda  jz      short loc_18005CEE2
0x18005cedc  call    cs:__imp_DeleteObject
0x18005cee2  mov     rbx, [rsp+28h+arg_0]
0x18005cee7  mov     rsi, [rsp+28h+arg_8]
0x18005ceec  add     rsp, 20h
0x18005cef0  pop     rdi
0x18005cef1  retn
```
