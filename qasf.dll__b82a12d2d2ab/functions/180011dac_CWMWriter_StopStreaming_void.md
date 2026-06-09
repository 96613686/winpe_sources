# CWMWriter::StopStreaming(void)

- ea: `0x180011dac`
- end: `0x180011f4b`
- name: `?StopStreaming@CWMWriter@@IEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011d40`

## callees

- `0x180010224`
- `0x180011dac`
- `0x18001f010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180011e19`
- `KERNEL32!SetEvent` at `0x180011e19`

## pseudocode

```c
__int64 __fastcall CWMWriter::StopStreaming(CWMWriter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rsi
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rcx

  if ( *((_DWORD *)this + 76)
    && (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 50) + 32LL))(
         *((_QWORD *)this + 50),
         ((unsigned __int64)this + 200) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
         0) >= 0 )
  {
    *((_DWORD *)this + 76) = 0;
  }
  v2 = *((_QWORD *)this + 51);
  if ( v2 )
  {
    do
    {
      v3 = *(_QWORD *)(v2 + 8);
      SetEvent(*(HANDLE *)(*(_QWORD *)(v2 + 16) + 336LL));
      v2 = v3;
    }
    while ( v3 );
  }
  if ( *((_DWORD *)this + 99) && (v4 = *((_QWORD *)this + 51), (v5 = v4) != 0) )
  {
    while ( !*(_DWORD *)(*(_QWORD *)(v5 + 16) + 464LL) )
    {
      v5 = *(_QWORD *)(v5 + 8);
      if ( !v5 )
        goto LABEL_10;
    }
    *((_DWORD *)this + 56) = 1;
    do
    {
      v8 = *(_QWORD *)(v4 + 8);
      v9 = *(_QWORD *)(v4 + 16);
      v10 = *(_DWORD *)(v9 + 464);
      if ( v10 )
      {
        *(_DWORD *)(v9 + 464) = v10 - 1;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 44) + 56LL))(
          *((_QWORD *)this + 44),
          *(unsigned int *)(v9 + 396),
          0);
      }
      v4 = v8;
    }
    while ( v8 );
    *((_DWORD *)this + 56) = 0;
  }
  else
  {
LABEL_10:
    v6 = *((_QWORD *)this + 39);
    *((_DWORD *)this + 57) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 96LL))(v6);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 41) + 112LL))(*((_QWORD *)this + 41));
    *((_DWORD *)this + 54) = 1;
    if ( v7 >= 0 && *((_DWORD *)this + 53) )
    {
      if ( *((_DWORD *)this + 55) )
      {
        v11 = *((_QWORD *)this + 13);
        if ( v11 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v11 + 24LL))(v11, 593, 13);
      }
      else
      {
        CWMWriter::IndexFile(this);
      }
    }
  }
  *((_DWORD *)this + 131) = 0;
  return 0;
}

```

## disassembly

```asm
0x180011dac  mov     [rsp+arg_0], rbx
0x180011db1  mov     [rsp+arg_8], rsi
0x180011db6  push    rdi
0x180011db7  sub     rsp, 30h
0x180011dbb  cmp     dword ptr [rcx+130h], 0
0x180011dc2  mov     rdi, rcx
0x180011dc5  jz      short loc_180011DFE
0x180011dc7  mov     rcx, [rcx+190h]
0x180011dce  lea     r8, [rdi+0C8h]
0x180011dd5  mov     rax, rdi
0x180011dd8  neg     rax
0x180011ddb  mov     r9, [rcx]
0x180011dde  sbb     rdx, rdx
0x180011de1  and     rdx, r8
0x180011de4  xor     r8d, r8d
0x180011de7  mov     rax, [r9+20h]
0x180011deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011df0  test    eax, eax
0x180011df2  js      short loc_180011DFE
0x180011df4  mov     dword ptr [rdi+130h], 0
0x180011dfe  mov     rcx, [rdi+198h]
0x180011e05  test    rcx, rcx
0x180011e08  jz      short loc_180011E27
0x180011e0a  mov     rbx, [rcx+8]
0x180011e0e  mov     rcx, [rcx+10h]
0x180011e12  mov     rcx, [rcx+150h]; hEvent
0x180011e19  call    cs:__imp_SetEvent
0x180011e1f  mov     rcx, rbx
0x180011e22  test    rbx, rbx
0x180011e25  jnz     short loc_180011E0A
0x180011e27  cmp     dword ptr [rdi+18Ch], 0
0x180011e2e  jz      short loc_180011E55
0x180011e30  mov     rdx, [rdi+198h]
0x180011e37  mov     rcx, rdx
0x180011e3a  test    rdx, rdx
0x180011e3d  jz      short loc_180011E55
0x180011e3f  mov     rax, [rcx+10h]
0x180011e43  cmp     dword ptr [rax+1D0h], 0
0x180011e4a  ja      short loc_180011EB3
0x180011e4c  mov     rcx, [rcx+8]
0x180011e50  test    rcx, rcx
0x180011e53  jnz     short loc_180011E3F
0x180011e55  mov     rcx, [rdi+138h]
0x180011e5c  xor     ebx, ebx
0x180011e5e  mov     [rdi+0E4h], ebx
0x180011e64  mov     rax, [rcx]
0x180011e67  mov     rax, [rax+60h]
0x180011e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e70  mov     rcx, [rdi+148h]
0x180011e77  mov     rax, [rcx]
0x180011e7a  mov     rax, [rax+70h]
0x180011e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e83  mov     dword ptr [rdi+0D8h], 1
0x180011e8d  test    eax, eax
0x180011e8f  js      loc_180011F2F
0x180011e95  cmp     [rdi+0D4h], ebx
0x180011e9b  jz      loc_180011F2F
0x180011ea1  cmp     [rdi+0DCh], ebx
0x180011ea7  jnz     short loc_180011F0E
0x180011ea9  mov     rcx, rdi; this
0x180011eac  call    ?IndexFile@CWMWriter@@IEAAJXZ; CWMWriter::IndexFile(void)
0x180011eb1  jmp     short loc_180011F2F
0x180011eb3  mov     dword ptr [rdi+0E0h], 1
0x180011ebd  xor     ebx, ebx
0x180011ebf  mov     rsi, [rdx+8]
0x180011ec3  mov     rdx, [rdx+10h]
0x180011ec7  mov     eax, [rdx+1D0h]
0x180011ecd  test    eax, eax
0x180011ecf  jz      short loc_180011EFA
0x180011ed1  dec     eax
0x180011ed3  xor     r8d, r8d
0x180011ed6  mov     [rdx+1D0h], eax
0x180011edc  mov     rcx, [rdi+160h]
0x180011ee3  mov     edx, [rdx+18Ch]
0x180011ee9  mov     rax, [rcx]
0x180011eec  mov     rax, [rax+38h]
0x180011ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef5  test    ebx, ebx
0x180011ef7  cmovs   ebx, eax
0x180011efa  mov     rdx, rsi
0x180011efd  test    rsi, rsi
0x180011f00  jnz     short loc_180011EBF
0x180011f02  mov     [rdi+0E0h], esi
0x180011f08  test    ebx, ebx
0x180011f0a  jns     short loc_180011F2F
0x180011f0c  jmp     short loc_180011F39
0x180011f0e  mov     rcx, [rdi+68h]
0x180011f12  test    rcx, rcx
0x180011f15  jz      short loc_180011F2F
0x180011f17  mov     rdx, [rcx]
0x180011f1a  xor     r9d, r9d
0x180011f1d  mov     rax, [rdx+18h]
0x180011f21  lea     r8d, [r9+0Dh]
0x180011f25  mov     edx, 251h
0x180011f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f2f  mov     dword ptr [rdi+20Ch], 0
0x180011f39  mov     rsi, [rsp+38h+arg_8]
0x180011f3e  mov     eax, ebx
0x180011f40  mov     rbx, [rsp+38h+arg_0]
0x180011f45  add     rsp, 30h
0x180011f49  pop     rdi
0x180011f4a  retn
```
