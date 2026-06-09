# CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::RemoveAll(void)

- ea: `0x18000e090`
- end: `0x18000e129`
- name: `?RemoveAll@?$CMap@PEB_WPEB_WPEAUHKEY__@@AEAPEAU1@@@QEAAXXZ`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cbcc`
- `0x18000e1a0`

## callees

- `0x180001010`
- `0x18000e090`

## import_xrefs

- `msvcrt!free` at `0x18000e0d5`
- `msvcrt!free` at `0x18000e0ef`
- `msvcrt!free` at `0x18000e0d5`
- `msvcrt!free` at `0x18000e0ef`
- `ADVAPI32!RegCloseKey` at `0x18000e0c2`
- `ADVAPI32!RegCloseKey` at `0x18000e0c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::RemoveAll(__int64 a1)
{
  __int64 i; // rsi
  __int64 *j; // rdi
  HKEY *v4; // r14
  int v5; // ebp

  if ( *(_QWORD *)(a1 + 8) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      for ( j = *(__int64 **)(*(_QWORD *)(a1 + 8) + 8 * i); j; j = (__int64 *)*j )
      {
        v4 = (HKEY *)(j + 3);
        v5 = 1;
        do
        {
          RegCloseKey(*v4++);
          --v5;
        }
        while ( v5 );
        free((void *)j[2]);
      }
    }
  }
  free(*(void **)(a1 + 8));
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 20) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  CPlexNew::FreeDataChain(*(CPlexNew **)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
}

```

## disassembly

```asm
0x18000e090  push    rbx
0x18000e092  push    rbp
0x18000e093  push    rsi
0x18000e094  push    rdi
0x18000e095  push    r14
0x18000e097  sub     rsp, 20h
0x18000e09b  mov     rbx, rcx
0x18000e09e  cmp     qword ptr [rcx+8], 0
0x18000e0a3  jz      short loc_18000E0EB
0x18000e0a5  xor     esi, esi
0x18000e0a7  cmp     [rcx+10h], esi
0x18000e0aa  jbe     short loc_18000E0EB
0x18000e0ac  mov     rax, [rbx+8]
0x18000e0b0  mov     rdi, [rax+rsi*8]
0x18000e0b4  jmp     short loc_18000E0DF
0x18000e0b6  lea     r14, [rdi+18h]
0x18000e0ba  mov     ebp, 1
0x18000e0bf  mov     rcx, [r14]; hKey
0x18000e0c2  call    cs:__imp_RegCloseKey
0x18000e0c8  lea     r14, [r14+8]
0x18000e0cc  sub     ebp, 1
0x18000e0cf  jnz     short loc_18000E0BF
0x18000e0d1  mov     rcx, [rdi+10h]; Block
0x18000e0d5  call    cs:__imp_free
0x18000e0db  nop
0x18000e0dc  mov     rdi, [rdi]
0x18000e0df  test    rdi, rdi
0x18000e0e2  jnz     short loc_18000E0B6
0x18000e0e4  inc     esi
0x18000e0e6  cmp     esi, [rbx+10h]
0x18000e0e9  jb      short loc_18000E0AC
0x18000e0eb  mov     rcx, [rbx+8]; Block
0x18000e0ef  call    cs:__imp_free
0x18000e0f5  nop
0x18000e0f6  mov     qword ptr [rbx+8], 0
0x18000e0fe  mov     dword ptr [rbx+14h], 0
0x18000e105  mov     qword ptr [rbx+18h], 0
0x18000e10d  mov     rcx, [rbx+20h]; this
0x18000e111  call    ?FreeDataChain@CPlexNew@@QEAAXXZ; CPlexNew::FreeDataChain(void)
0x18000e116  mov     qword ptr [rbx+20h], 0
0x18000e11e  add     rsp, 20h
0x18000e122  pop     r14
0x18000e124  pop     rdi
0x18000e125  pop     rsi
0x18000e126  pop     rbp
0x18000e127  pop     rbx
0x18000e128  retn
```
