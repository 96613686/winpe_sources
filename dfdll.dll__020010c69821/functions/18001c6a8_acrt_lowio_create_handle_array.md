# __acrt_lowio_create_handle_array

- ea: `0x18001c6a8`
- end: `0x18001c73d`
- name: `__acrt_lowio_create_handle_array`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c790`

## callees

- `0x180018f64`
- `0x180019590`
- `0x180019608`
- `0x18001c6a8`

## pseudocode

```c
char *_acrt_lowio_create_handle_array()
{
  char *v0; // rax
  char *v1; // rsi
  char *v2; // rbx
  char *v3; // rbp
  char *v4; // rdi

  v0 = (char *)calloc_base(0x40u, 0x40u);
  v1 = 0;
  v2 = v0;
  if ( v0 )
  {
    v3 = v0 + 4096;
    v4 = v0 + 48;
    do
    {
      _acrt_InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 - 48), 0xFA0u);
      *((_QWORD *)v4 - 1) = -1;
      *(_QWORD *)v4 = 0;
      *((_DWORD *)v4 + 2) = 168427520;
      v4[12] = 10;
      v4[13] &= 0xF8u;
      v4[14] = 0;
      v4 += 64;
    }
    while ( v4 - 48 != v3 );
    v1 = v2;
  }
  free_base(0);
  return v1;
}

```

## disassembly

```asm
0x18001c6a8  mov     [rsp+arg_0], rbx
0x18001c6ad  mov     [rsp+arg_8], rbp
0x18001c6b2  mov     [rsp+arg_10], rsi
0x18001c6b7  push    rdi
0x18001c6b8  sub     rsp, 20h
0x18001c6bc  mov     edx, 40h ; '@'; Size
0x18001c6c1  mov     ecx, edx; Count
0x18001c6c3  call    _calloc_base
0x18001c6c8  xor     esi, esi
0x18001c6ca  mov     rbx, rax
0x18001c6cd  test    rax, rax
0x18001c6d0  jz      short loc_18001C71E
0x18001c6d2  lea     rbp, [rax+1000h]
0x18001c6d9  cmp     rax, rbp
0x18001c6dc  jz      short loc_18001C71B
0x18001c6de  lea     rdi, [rax+30h]
0x18001c6e2  lea     rcx, [rdi-30h]; lpCriticalSection
0x18001c6e6  xor     r8d, r8d
0x18001c6e9  mov     edx, 0FA0h; dwSpinCount
0x18001c6ee  call    __acrt_InitializeCriticalSectionEx
0x18001c6f3  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x18001c6f8  mov     [rdi], rsi
0x18001c6fb  mov     dword ptr [rdi+8], 0A0A0000h
0x18001c702  mov     byte ptr [rdi+0Ch], 0Ah
0x18001c706  and     byte ptr [rdi+0Dh], 0F8h
0x18001c70a  mov     [rdi+0Eh], sil
0x18001c70e  lea     rdi, [rdi+40h]
0x18001c712  lea     rax, [rdi-30h]
0x18001c716  cmp     rax, rbp
0x18001c719  jnz     short loc_18001C6E2
0x18001c71b  mov     rsi, rbx
0x18001c71e  xor     ecx, ecx; Block
0x18001c720  call    _free_base
0x18001c725  mov     rbx, [rsp+28h+arg_0]
0x18001c72a  mov     rax, rsi
0x18001c72d  mov     rsi, [rsp+28h+arg_10]
0x18001c732  mov     rbp, [rsp+28h+arg_8]
0x18001c737  add     rsp, 20h
0x18001c73b  pop     rdi
0x18001c73c  retn
```
