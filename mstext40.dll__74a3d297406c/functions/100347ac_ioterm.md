# __ioterm

- ea: `0x100347ac`
- end: `0x100347fe`
- name: `__ioterm`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1002e1ef`

## callees

- `0x1002df32`
- `0x100347ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100347cd`
- `KERNEL32!DeleteCriticalSection` at `0x100347cd`

## pseudocode

```c
void _ioterm()
{
  void **v0; // esi
  char *v1; // edi
  struct _RTL_CRITICAL_SECTION *v2; // edi

  v0 = (void **)__pioinfo;
  do
  {
    v1 = (char *)*v0;
    if ( *v0 )
    {
      if ( v1 < v1 + 2048 )
      {
        v2 = (struct _RTL_CRITICAL_SECTION *)(v1 + 12);
        do
        {
          if ( v2[-1].SpinCount )
            DeleteCriticalSection(v2);
          v2 = (struct _RTL_CRITICAL_SECTION *)((char *)v2 + 64);
        }
        while ( &v2[-1].OwningThread < (HANDLE *)((char *)*v0 + 2048) );
      }
      free(*v0);
      *v0 = 0;
    }
    ++v0;
  }
  while ( (int)v0 < (int)byte_10044EB8 );
}

```

## disassembly

```asm
0x100347ac  push    esi
0x100347ad  push    edi
0x100347ae  mov     esi, offset ___pioinfo
0x100347b3  mov     edi, [esi]
0x100347b5  test    edi, edi
0x100347b7  jz      short loc_100347F0
0x100347b9  lea     eax, [edi+800h]
0x100347bf  cmp     edi, eax
0x100347c1  jnb     short loc_100347E5
0x100347c3  add     edi, 0Ch
0x100347c6  cmp     dword ptr [edi-4], 0
0x100347ca  jz      short loc_100347D3
0x100347cc  push    edi; lpCriticalSection
0x100347cd  call    ds:__imp__DeleteCriticalSection@4
0x100347d3  mov     ecx, [esi]
0x100347d5  add     edi, 40h ; '@'
0x100347d8  add     ecx, 800h
0x100347de  lea     eax, [edi-0Ch]
0x100347e1  cmp     eax, ecx
0x100347e3  jb      short loc_100347C6
0x100347e5  push    dword ptr [esi]; Block
0x100347e7  call    _free
0x100347ec  and     dword ptr [esi], 0
0x100347ef  pop     ecx
0x100347f0  add     esi, 4
0x100347f3  cmp     esi, offset byte_10044EB8
0x100347f9  jl      short loc_100347B3
0x100347fb  pop     edi
0x100347fc  pop     esi
0x100347fd  retn
```
